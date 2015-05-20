---
layout: post
title: 深入浅出Android的回调方法
description: 回调方法在Android中使用非常频繁
permalink: /android-callback/
categories: [blog, 博客]
tags: [Android, 回调, Callback]
date: 2015-05-17 10:00:00
--- 

回调就是外部设置一个方法给一个对象, 这个对象可以执行外部设置的方法, 通常这个方法是定义在接口中的抽象方法, 外部设置的时候直接设置这个接口对象即可。

例如给安卓添加按钮点击事件, 我们创建了OnClickListener接口 实现了其中的onClick方法, 在合适的时机(按钮被点击的时候) , 就会执行我们实现的onClick()方法，这个方法就被回调了。

## 1. 如何定义一个回调

a. 定义接口 : 在类中定义一个Interface, 并在接口中定义一个抽象方法;
b. 接口对象 : 在类中定义一个该接口的成员变量;
c. 设置对象 : 在类中定义一个公共的方法, 可以设置这个接口的对象, 调用该方法给接口对象成员变量赋值;
d. 调用方法 : 在合适的位置调用接口对象中的方法;

## 2. 代码实例

```java
public class Employee {
	/*
	 * 定义回调接口的成员变量
	 */
	private Callback mCallback;
	/*
	 * 声明回调接口
	 */
	public interface Callback{
		public abstract void work();
	}
	/*
	 * 设置回调接口对象成员变量
	 */
	public void setCallback(Callback callback) {
		this.mCallback = callback;
	}
	/*
	 * 调用回调接口对象中的方法
	 */
	public void doWork() {
		mCallback.work();
	}
}
```

```java
public class Boss {
	private Employee employee;
	/*
	 * 为Employee设置回调函数, 在这里定义具体的回调方法
	 */
	public void setCallback() {
		employee.setCallback(new Employee.Callback() {
			@Override
			public void work() {
				System.out.println("work");
			}
		});
	}
}
```