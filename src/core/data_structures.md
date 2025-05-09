# 数据结构 (Data Structures)

数据结构是组织和存储数据的方式，是构建任何复杂程序的基础。Flurry 提供了多种内置的数据结构类型，用于表示不同形式的数据集合，并允许开发者定义自己的复杂数据类型。

Flurry 的一个核心设计理念是，**类型定义本身就是一个完备的命名空间**。这意味着像结构体 (`struct`)、枚举 (`enum`)、联合体 (`union`) 甚至模块 (`mod`) 这些用于定义类型的关键字，它们所创建的不仅仅是数据的蓝图，更是一个可以包含常量、静态变量、嵌套类型定义以及关联函数（方法）的作用域。

本章将深入探讨 Flurry 中主要的内置和用户自定义数据结构：

-   **结构体 (Structs)**: 将不同类型的数据组合成一个逻辑单元。
-   **枚举 (Enums)**: 定义一个可以持有多种不同变体之一的类型。
-   **联合体 (Unions)**: 允许多个字段共享同一块内存空间（需要谨慎使用）。
-   **数组与切片 (Arrays & Slices)**: 处理固定大小和动态大小的同质数据序列。
-   **元组 (Tuples)**: 轻量级的、匿名的、固定大小的异质数据序列。
-   **模块作为类型 (Modules as Types)**: 理解模块本身也是一种包含成员的类型。
-   **Newtypes**: 创建基于现有类型的新类型，以增强类型安全。

理解这些数据结构及其作为命名空间的行为，是掌握 Flurry 类型系统和组织复杂代码的关键。