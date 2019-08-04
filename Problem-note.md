# Personal note on how I solved the problems

### Jun 22, 2018

#### Git

**Issue**

My commit log to GitHub is not shown with my profile avatar and name properly.

**How to solve**

Email config needed to set locally.
[GitHub Help page](https://help.github.com/articles/setting-your-commit-email-address-in-git/)
 helped me to solve the issue.

********

### Jun 8, 2019

#### CSS

**Issue**

Even though I used `@media (max-width: 767px)` in CSS, in the mobile device it bypasses the media query. On desktop browser, it works fine.

**How to solve**

After searching, I found out that I have to set viewport as below.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

********

### Aug 4, 2019

#### Java

**Issue**

Install openjdk on macOS.

**How to solve**

Download latest JDK from [jdk.java.net](http://jdk.java.net).

Copy the extracted folder to following folder.
```
/Library/Java/JavaVirtualMachines/
```

Edit paths file.
```
sudo nano /etc/paths
```
Add below line.
```
/Library/Java/JavaVirtualMachines/jdk?.?.?_???.jdk/Contents/Home/bin
```

Edit profile file.
```
sudo nano /etc/profile
```
Add below lines.
```
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk?.?.?_???.jdk/Contents/Home
export CLASSPATH=.:$JAVA_HOME/lib/tools.jar
```

