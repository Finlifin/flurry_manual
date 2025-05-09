# Flurry: 为下一代基础设施而生

欢迎来到 Flurry 的世界！Flurry 并非又一个通用编程语言，它的诞生承载着一个明确的使命：为构建未来**高性能、高可靠性、高安全性**的计算基础设施提供坚实的基础。

## 问题域：系统编程的困境

现代数字世界的基石——操作系统、网络协议栈、数据库、虚拟机、云平台——都依赖于系统级编程语言来构建。这些基础设施软件对正确性、性能和资源利用率有着极致的要求。然而，长期以来，主流的系统级语言，特别是 C 和 C++，虽然赋予了开发者无与伦比的底层控制能力，但也因其固有的内存安全问题和并发处理复杂性，成为了无数严重软件缺陷和安全漏洞的温床 [^1]。

近年来，像 Rust 这样的语言通过引入所有权和借用检查等创新机制，在编译时提供了强大的内存和线程安全保证，极大地改善了现状。但这并非终点。为了实现必要的底层控制和极致性能，即使是 Rust 也需要 `unsafe` 代码块，这道“后门”重新引入了对形式化验证的需求，以确保安全边界的稳固[^2]。此外，仅仅保证内存和线程安全是不够的，基础设施软件还需要深层次的**功能正确性**——即程序必须精确地按照其复杂规范运行。现有的验证技术在面对系统编程的复杂性（指针算术、细粒度并发、硬件交互、复杂的别名）时，往往捉襟见肘[^3]。

我们相信，是时候需要一种新的系统级编程语言了——它不仅要提供现代语言的安全性与开发效率，还要在设计之初就**内建对高级验证和复杂系统建模的支持**，并提供无与伦比的**编译时能力**来消除抽象开销和实现深度优化。

## Flurry 的答案：安全、性能与表现力的融合

Flurry 正是为此而设计的。它旨在成为构建下一代操作系统、网络栈、数据库内核、嵌入式系统以及其他关键基础设施的理想选择。Flurry 的核心理念是在以下几个关键维度上取得突破性的进展：

1.  **内建安全性与验证支持**:
    *   **分级安全模型**: 提供 `unsafe`, `safe`, `verified` 三个安全级别，允许开发者明确风险并逐步提升代码可信度。
    *   **创新的安全机制**: 超越传统借用检查，探索结合**仿射类型、可达性类型系统和副作用系统**，旨在提供灵活且强大的静态安全保证。
    *   **面向验证的设计**: 语言核心特性（如代数效应、`comptime` 元编程）的设计考虑了与形式化方法（如 Outcome Separation Logic, Reachability Logic, Matching Logic）的集成可能性，目标是让深度验证更加可行。

2.  **极致的编译时能力 (`comptime`)**:
    *   **图灵完备的编译时执行**: Flurry 拥有一个功能强大的编译时运行时，允许在编译阶段执行任意复杂的计算、代码生成和静态检查。
    *   **零成本抽象**: 泛型、元编程和高级抽象通过编译时计算实现单态化和优化，不引入运行时开销。
    *   **编译时配置与构建**: 包管理、特性标志、甚至构建逻辑都可以使用 Flurry 自身的 `comptime` 代码定义，提供无与伦比的灵活性。

3.  **富有表现力且一致的语法**:
    *   **现代特性**: 吸收并改进了代数效应、强大的模式匹配、Trait 系统、层级化枚举等现代语言特性。
    *   **创新语法**: 引入 `expr object` DSL 构建、`expr ' image` 取像、`extend` 作用域扩展、`.tagged_polymorphic` 多态等独特语法，旨在提升特定场景下的表达力和简洁性。
    *   **一致性**: 追求语法元素（如 `.`, `^`, `'`）在不同上下文中的一致语义。

4.  **性能与控制力**:
    *   **系统级定位**: 提供必要的底层控制能力（如指针操作，但需在 `unsafe` 中或得到验证）。
    *   **面向性能的设计**: 编译时计算、潜在的优化（如 `tagged_polymorphic` 分派）都旨在生成高效的本地代码。

## 为什么选择 Flurry？(Teaser)

*   **超越 Rust 的安全边界**: 在提供 `safe` 基础的同时，为 `unsafe` 和功能正确性提供内建的、更强大的验证路径。
*   **Zig 级别的编译时能力，甚至更强**: `comptime` 是 Flurry 的核心支柱，深度集成到类型系统、元编程和构建过程中。
*   **代数效应带来的结构化并发与控制流**: 提供比传统回调、Promise、async/await 更灵活、更可组合的副作用和控制流管理。
*   **独特的 DSL 构建能力**: `expr object` 和 `extend` 字面量拓展等特性使得构建嵌入式领域特定语言极其自然。
*   **为复杂系统而生的模块化与验证支持**: 从包管理到形式化方法集成，都旨在应对大型、关键系统的挑战。

Flurry 是一项雄心勃勃的探索，它试图站在现有系统语言的肩膀上，融合最新的编程语言理论研究，为未来构建更安全、更可靠、更高效的数字基础设施提供下一代利器。我们邀请您一同踏上这段激动人心的旅程！

---
[^1]: Memory-Safe Programming Languages and National Cybersecurity ...
[^2]: Surveying the Rust Verification Landscape - arXiv
[^3]: Concurrent Separation Logic