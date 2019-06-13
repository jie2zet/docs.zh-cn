---
title: true 和 false 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/10/2018
helpviewer_keywords:
- false operator [C#]
- true operator [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: b1acf9a16dd977ec49a7f1dc3bea4ee41792e9be
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758138"
---
# <a name="true-and-false-operators-c-reference"></a><span data-ttu-id="8f635-102">true 和 false 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8f635-102">true and false operators (C# Reference)</span></span>

<span data-ttu-id="8f635-103">`true` 运算符返回 [bool](../keywords/bool.md) 值 `true`，以指明操作数一定为 true。</span><span class="sxs-lookup"><span data-stu-id="8f635-103">The `true` operator returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span> <span data-ttu-id="8f635-104">`false` 运算符返回 `bool` 值 `true`，以指明操作数一定为 false。</span><span class="sxs-lookup"><span data-stu-id="8f635-104">The `false` operator returns the `bool` value `true` to indicate that an operand is definitely false.</span></span> <span data-ttu-id="8f635-105">无法确保 `true` 和 `false` 运算符互补。</span><span class="sxs-lookup"><span data-stu-id="8f635-105">The `true` and `false` operators are not guaranteed to complement each other.</span></span> <span data-ttu-id="8f635-106">也就是说，`true` 和 `false` 运算符可能同时针对同一个操作数返回 `bool` 值 `false`。</span><span class="sxs-lookup"><span data-stu-id="8f635-106">That is, both the `true` and `false` operator might return the `bool` value `false` for the same operand.</span></span> <span data-ttu-id="8f635-107">如果某类型定义这两个运算符之一，它还必须定义另一个运算符。</span><span class="sxs-lookup"><span data-stu-id="8f635-107">If a type defines one of the two operators, it must also define another operator.</span></span>

<span data-ttu-id="8f635-108">如果包含已定义 `true` 和 `false` 运算符的类型以某种方式[重载](../keywords/operator.md)[逻辑 OR 运算符](boolean-logical-operators.md#logical-or-operator-) `|` 或[逻辑 AND 运算符](boolean-logical-operators.md#logical-and-operator-) `&`，可以对相应类型的操作数分别执行[条件逻辑 OR 运算符](boolean-logical-operators.md#conditional-logical-or-operator-) `||` 或[条件逻辑 AND 运算符](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` 运算。</span><span class="sxs-lookup"><span data-stu-id="8f635-108">If a type with the defined `true` and `false` operators [overloads](../keywords/operator.md) the [logical OR operator](boolean-logical-operators.md#logical-or-operator-) `|` or the [logical AND operator](boolean-logical-operators.md#logical-and-operator-) `&` in a certain way, the [conditional logical OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||` or [conditional logical AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&`, respectively, can be evaluated for the operands of that type.</span></span> <span data-ttu-id="8f635-109">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="8f635-109">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="8f635-110">包含已定义 `true` 运算符的类型可以是 [if](../keywords/if-else.md)、[do](../keywords/do.md)、[while](../keywords/while.md) 和 [for](../keywords/for.md) 语句以及[条件运算符 `?:`](conditional-operator.md) 中控制条件表达式的结果的类型。</span><span class="sxs-lookup"><span data-stu-id="8f635-110">A type with the defined `true` operator can be the type of a result of a controlling conditional expression in the [if](../keywords/if-else.md), [do](../keywords/do.md), [while](../keywords/while.md), and [for](../keywords/for.md) statements and in the [conditional operator `?:`](conditional-operator.md).</span></span> <span data-ttu-id="8f635-111">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的 [Boolean 表达式](~/_csharplang/spec/expressions.md#boolean-expressions)部分。</span><span class="sxs-lookup"><span data-stu-id="8f635-111">For more information, see the [Boolean expressions](~/_csharplang/spec/expressions.md#boolean-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

> [!TIP]
> <span data-ttu-id="8f635-112">如需支持三值逻辑（例如，在使用支持三值布尔类型的数据库时），请使用 `bool?` 类型。</span><span class="sxs-lookup"><span data-stu-id="8f635-112">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="8f635-113">C# 提供 `&` 和 `|` 运算符，它们通过 `bool?` 操作数支持三值逻辑。</span><span class="sxs-lookup"><span data-stu-id="8f635-113">C# provides the `&` and `|` operators that support the three-valued logic with the `bool?` operands.</span></span> <span data-ttu-id="8f635-114">有关详细信息，请参阅[布尔逻辑运算符](boolean-logical-operators.md)一文的[可以为 null 的布尔逻辑运算符](boolean-logical-operators.md#nullable-boolean-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="8f635-114">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

<span data-ttu-id="8f635-115">下面的示例展示了定义 `true` 和 `false` 运算符的类型。</span><span class="sxs-lookup"><span data-stu-id="8f635-115">The following example presents the type that defines both `true` and `false` operators.</span></span> <span data-ttu-id="8f635-116">此外，它还重载了逻辑 AND 运算符 `&`，因此也可以对相应类型的操作数执行运算符 `&&` 运算。</span><span class="sxs-lookup"><span data-stu-id="8f635-116">Moreover, it overloads the logical AND operator `&` in such a way that the operator `&&` also can be evaluated for the operands of that type.</span></span>

[!code-csharp[true and false operators example](~/samples/csharp/language-reference/operators/TrueFalseOperators.cs)]

<span data-ttu-id="8f635-117">请注意 `&&` 运算符的短路行为。</span><span class="sxs-lookup"><span data-stu-id="8f635-117">Notice the short-circuiting behavior of the `&&` operator.</span></span> <span data-ttu-id="8f635-118">当 `GetFuelLaunchStatus` 方法返回 `LaunchStatus.Red` 时，不会计算 `&&` 运算符的第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="8f635-118">When the `GetFuelLaunchStatus` method returns `LaunchStatus.Red`, the second operand of the `&&` operator is not evaluated.</span></span> <span data-ttu-id="8f635-119">这是因为 `LaunchStatus.Red` 一定为 false。</span><span class="sxs-lookup"><span data-stu-id="8f635-119">That is because `LaunchStatus.Red` is definitely false.</span></span> <span data-ttu-id="8f635-120">然后，逻辑 AND 运算符的结果不依赖第二个操作数的值。</span><span class="sxs-lookup"><span data-stu-id="8f635-120">Then the result of the logical AND doesn't depend on the value of the second operand.</span></span> <span data-ttu-id="8f635-121">示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f635-121">The output of the example is as follows:</span></span>

```console
Getting fuel launch status...
Wait!
```

## <a name="see-also"></a><span data-ttu-id="8f635-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f635-122">See also</span></span>

- [<span data-ttu-id="8f635-123">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8f635-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8f635-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8f635-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8f635-125">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="8f635-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="8f635-126">`true` 文本</span><span class="sxs-lookup"><span data-stu-id="8f635-126">`true` literal</span></span>](../keywords/true-literal.md)
- [<span data-ttu-id="8f635-127">`false` 文本</span><span class="sxs-lookup"><span data-stu-id="8f635-127">`false` literal</span></span>](../keywords/false-literal.md)