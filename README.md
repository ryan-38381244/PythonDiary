# PythonDiary

## 創作理念

練習做網頁

## 首頁展示

 
![](https://github.com/ryan-38381244/PythonDiary/raw/master/%E7%B6%B2%E7%AB%99%E6%88%AA%E5%9C%96.png)

# 網站傳送門
[![](https://github.com/ryan-38381244/PythonDiary/raw/master/iconfinder_Missile_rocket_rocket_launch_spacecraft_spaceship_4801275.png)](https://diarypython.herokuapp.com)

## 使用技術

工具名稱 | 用途
------------------
Python 3 | 主要組成網站
Flask(Python) | 幫助建立伺服器
HTML/CSS | 網頁顯示與排版
Heroku | 託管網頁
Github | 存放原始碼

## 原始碼片段

```python
@app.route("/category/<c>")
def category(c):
  fs = glob.glob("articles/" + c + "/*.txt")
  fill = []
  
  for i, f in enumerate(fs):
    a = open(f)
    article = a.read()
    a.close()
    fp = f.split("/")[-1].replace(".txt", "")
    utc = datetime.utcfromtimestamp(os.path.getmtime(f))
    t = (i, fp, str(utc), article)
    fill.append(t)
  return render_template("category.html", cat=fill, title=c)
```
