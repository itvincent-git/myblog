---
title: android-constraint-layout
categories:
keywords:
tags:
---

ConstraintLayout is available in an API library that's compatible with Android 2.3 (API level 9) and higher.

Android Studio 2.3 or higher

```
dependencies {
    compile 'com.android.support.constraint:constraint-layout:1.0.2'
}
```

When creating constraints, remember the following rules:

- Every view must have at least two constraints: one horizontal and one vertical.每个View必须要有一个水平和一个垂直的约束
- You can create constraints only between a constraint handle and an anchor point that share the same plane. So a vertical plane (the left and right sides) of a view can be constrained only to another vertical plane; and baselines can constrain only to other baselines.垂直必须跟垂直的约束搭配，水平跟水平的约束搭配。
- Each constraint handle can be used for just one constraint, but you can create multiple constraints (from different views) to the same anchor point.
