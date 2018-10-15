# 10.15.1
类的公有继承
// 10.15.1.cpp : 定义控制台应用程序的入口点。
//

#include "stdafx.h"
#include"RecTangle.h"
#include<iostream>
using namespace std;
int main()
{
	RecTangle rect;
	rect.initRecTangle(2, 3, 4, 5);
	rect.Move(3, 6);
	cout << rect.getX() << ", " << rect.getY() << ", " << rect.getW() << ", " << rect.getH() << ", " << endl;
    return 0;
}

//Point.h文件
#ifndef _1
#define _1

class Point {
public:
	void InitPoint(double x=0, double y=0) {
		this->x = x;
		this->y = y;
	}
	void Move(double OFFx, double OFFy) {
		x += OFFx;
		y += OFFy;
	}
	double  getX() const { return x; }
	double  getY() const { return y; }
private:
	double x, y;
};

#endif // !_1

//RecTangle.h文件
#pragma once
#include"Point.h"

class RecTangle :public Point { //公有继承Point类

public: //新增公有成员函数
	void initRecTangle(double x,double y, double w, double h) {
		InitPoint(x, y);//调用基类成员函数
		this->w/* 这里是class RecTangle类中的private成员w*/ = w;
		this->h = h;
	};
	double  getW() const { return w; }
	double  getH() const { return h; }
private:
	double w, h;
	
};
