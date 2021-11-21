## The problem
If any of you is using BSPWM and tries to open any java-based application, you will likely encounter some GUI errors.

In my case, I had trouble working with **BurpSuite** and **OWASP-ZAP**

If you have a look at the following image, you can see that there's a blank space at the right of the window. You can literally only use half of your screen. In addition, some tabs were not working at all (for example,.I couldn't use the intruder)

<img src="https://i.ibb.co/D5w4cWc/Virtual-Box-Kali-VM-21-11-2021-23-38-49.png">

I tried OWASP-ZAP as an alternative, but turns out it also uses java and it didn't work at all. The GUI was fully empty, and I could do nothing.

## The easy solution
Exporting this in your terminal before launching any java app will do the trick.

> export _JAVA_AWT_WM_NONREPARENTING=1

However, it's very tedious to export this every time you have to run an app so I've gone for a more user-friendly solution.

## The user friendly solution
Open your `sxhkdrc` file located in `/.config/sxhkd`

You can create some shortcuts there to launch applications. In my case, I've created shortcuts to launch Burpsuite and Owasp-zap.
```bash
.......
# ---------------------------------------------
# CUSTOM
# ---------------------------------------------

# Google-Chrome

super + shift + g
	google-chrome

super + shift + b
	export _JAVA_AWT_WM_NONREPARENTING=1; burpsuite

super + shift + h
	xfce4-screenshooter

super + shift + o
	export _JAVA_AWT_WM_NONREPARENTING=1; owasp-zap

```

Now, if you use the shortcuts to launch the applications, the variable will be exported first automatically.

And voila, stuff works again


<img src="https://imgur.com/qlq8dUB.png">
<img src="https://imgur.com/fF05LGD.png">
