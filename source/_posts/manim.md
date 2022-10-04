---
title: manim常用语句以及欧几里得几何原本中勾股定理证明代码
date: 2022-05-05 19:13:43
tags: manim
---
### manim我常用的语句
`os.getcwd()`用这个改变python指定路径
`python ./manim.py Euler.py Euler -pl `运行的语句
`self.play(ShowCreation(triangle1))`用于展示图形
`self.play(ReplacementTransform(triangle2_2, square1_1))`用于图型转变
<!--more-->
### 欧几里得几何原本中勾股定理的证明
``` bash
from sre_parse import WHITESPACE
from turtle import color
from matplotlib.transforms import Transform
import numpy as np
from pyparsing import White
from sympy import Circle
from manimlib import *
from manimlib.animation.creation import ShowCreation
from manimlib.animation.transform import ReplacementTransform
from manimlib.mobject.geometry import Polygon, Square, Triangle
from manimlib.scene.scene import Scene

class SquareToCircle(Scene):
    def construct(self):
        #绘制一个直角三角形
        triangle1 = Polygon(np.array([-0.45,0,0]), np.array([0.8,0,0]), np.array([0,0.6,0]),color="#FFFFFF")
        self.play(ShowCreation(triangle1))
        self.wait()
        #三边作正方形
        square1 = Polygon(np.array([-0.45,0,0]), np.array([-1.05,0.45,0]), np.array([-0.6,1.05,0]), np.array([0,0.6,0]), color="#FFFFFF")
        square1_1 = Polygon(np.array([-0.45,0,0]), np.array([-1.05,0.45,0]), np.array([-0.6,1.05,0]), np.array([0,0.6,0]), color="#FFFF00")
        self.play(ShowCreation(square1))
        self.wait()
        square2 = Polygon(np.array([0.8,0,0]), np.array([1.4,0.8,0]), np.array([0.6,1.4,0]), np.array([0,0.6,0]), color="#FFFFFF")
        square2_1 = Polygon(np.array([0.8,0,0]), np.array([1.4,0.8,0]), np.array([0.6,1.4,0]), np.array([0,0.6,0]), color="#F7A1A3")
        square2_2 = Polygon(np.array([0.8,0,0]), np.array([1.4,0.8,0]), np.array([0.6,1.4,0]), np.array([0,0.6,0]), color="#F7A1A3")
        self.play(ShowCreation(square2))
        self.wait()
        square3 = Polygon(np.array([-0.45,0,0]), np.array([-0.45,-1.25,0]), np.array([0.8,-1.25,0]), np.array([0.8,0,0]), color="#FFFFFF")
        self.play(ShowCreation(square3))
        self.wait()
        #绘制两个全等三角形
        triangle2_1 = Polygon(np.array([-0.45,0,0]), np.array([-0.45,-1.25,0]), np.array([0,0.6,0]),color="#FFFF00")
        self.play(ShowCreation(triangle2_1))
        self.wait()
        triangle2_2 = Polygon(np.array([-0.45,0,0]), np.array([0.8,0,0]), np.array([-1.05,0.45,0]),color="#FFFF00")
        self.play(ShowCreation(triangle2_2))
        self.wait()
        #绘制line
        line = Polygon(np.array([0,0.6,0]), np.array([0,-1.25,0]),color="#FFFFFF")
        self.play(ShowCreation(line))
        self.wait()
        #定义两个面积区域
        square4 = Polygon(np.array([-0.45,0,0]), np.array([0,0,0]), np.array([0,-1.25,0]), np.array([-0.45,-1.25,0]), color="#FFFF00")
        square5 = Polygon(np.array([0.8,0,0]), np.array([0,0,0]), np.array([0,-1.25,0]), np.array([0.8,-1.25,0]), color="#F7A1A3")
        self.play(ReplacementTransform(triangle2_1, square4))
        self.wait()
        self.play(ReplacementTransform(triangle2_2, square1_1))
        self.wait()
        self.play(ShowCreation(square2_1))
        self.wait()
        self.play(ReplacementTransform(square2_2, square5))
        self.wait()
        
```