---
title: 算术运算符 - C# 参考
description: 了解对数值类型执行乘法、除法、余数、加法和减法运算的 C# 运算符。
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: 192acf6fea0c6014aaf092077f8deaa844dfd2ec
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58633798"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="3297e-103">算术运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3297e-103">Arithmetic operators (C# Reference)</span></span>

<span data-ttu-id="3297e-104">以下运算符对数值类型执行算术运算：</span><span class="sxs-lookup"><span data-stu-id="3297e-104">The following operators perform arithmetic operations with numeric types:</span></span>

- <span data-ttu-id="3297e-105">一元 [`++`（增量）](#increment-operator-)、[`--`（减量）](#decrement-operator---)、[`+`（加）](#unary-plus-and-minus-operators) 和 [`-`（减）](#unary-plus-and-minus-operators)运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators.</span></span>
- <span data-ttu-id="3297e-106">二元 [`*`（乘）](#multiplication-operator-)[`/`（除）](#division-operator-)[`%`（余数）](#remainder-operator-)[`+`（加）](#addition-operator-) 和 [`-`（减）](#subtraction-operator--) 运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators.</span></span>

<span data-ttu-id="3297e-107">这些运算符支持所有[整型](../keywords/integral-types-table.md)和[浮动](../keywords/floating-point-types-table.md)数值类型。</span><span class="sxs-lookup"><span data-stu-id="3297e-107">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="3297e-108">增量运算符 ++</span><span class="sxs-lookup"><span data-stu-id="3297e-108">Increment operator ++</span></span>

<span data-ttu-id="3297e-109">一元增量运算符 `++` 按 1 递增其操作数。</span><span class="sxs-lookup"><span data-stu-id="3297e-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="3297e-110">操作数必须是变量、[属性](../../programming-guide/classes-and-structs/properties.md)访问或[索引器](../../../csharp/programming-guide/indexers/index.md)访问。</span><span class="sxs-lookup"><span data-stu-id="3297e-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="3297e-111">增量运算符以两种形式进行支持：后缀增量运算符 `x++` 和前缀增量运算符 `++x`。</span><span class="sxs-lookup"><span data-stu-id="3297e-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="3297e-112">后缀递增运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-112">Postfix increment operator</span></span>

<span data-ttu-id="3297e-113">`x++` 的结果是此操作前的 `x` 的值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3297e-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="3297e-114">前缀增量运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-114">Prefix increment operator</span></span>

<span data-ttu-id="3297e-115">`++x` 的结果是此操作后的 `x` 的值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3297e-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="3297e-116">减量运算符 --</span><span class="sxs-lookup"><span data-stu-id="3297e-116">Decrement operator --</span></span>

<span data-ttu-id="3297e-117">一元减量运算符 `--` 按 1 递减其操作数。</span><span class="sxs-lookup"><span data-stu-id="3297e-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="3297e-118">操作数必须是变量、[属性](../../programming-guide/classes-and-structs/properties.md)访问或[索引器](../../../csharp/programming-guide/indexers/index.md)访问。</span><span class="sxs-lookup"><span data-stu-id="3297e-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="3297e-119">减量运算符以两种形式进行支持：后缀减量运算符`x--` 和前缀减量运算符 `--x`。</span><span class="sxs-lookup"><span data-stu-id="3297e-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="3297e-120">后缀递减运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-120">Postfix decrement operator</span></span>

<span data-ttu-id="3297e-121">`x--` 的结果是此操作前的 `x` 的值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3297e-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="3297e-122">前缀减量运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-122">Prefix decrement operator</span></span>

<span data-ttu-id="3297e-123">`--x` 的结果是此操作后的 `x` 的值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3297e-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="3297e-124">一元加和减运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-124">Unary plus and minus operators</span></span>

<span data-ttu-id="3297e-125">一元 `+` 运算符返回其操作数的值。</span><span class="sxs-lookup"><span data-stu-id="3297e-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="3297e-126">一元 `-` 运算符对其操作数的数值取负。</span><span class="sxs-lookup"><span data-stu-id="3297e-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="3297e-127">一元 `-` 运算符不支持 [ulong](../keywords/ulong.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="3297e-127">The unary `-` operator doesn't support the [ulong](../keywords/ulong.md) type.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="3297e-128">乘法运算符 \*</span><span class="sxs-lookup"><span data-stu-id="3297e-128">Multiplication operator \*</span></span>

<span data-ttu-id="3297e-129">乘法运算符 `*` 计算其操作数的乘积：</span><span class="sxs-lookup"><span data-stu-id="3297e-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="3297e-130">一元 `*` 运算符是[指针间接运算符](multiplication-operator.md#pointer-indirection-operator)。</span><span class="sxs-lookup"><span data-stu-id="3297e-130">The unary `*` operator is a [pointer indirection operator](multiplication-operator.md#pointer-indirection-operator).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="3297e-131">除法运算符 /</span><span class="sxs-lookup"><span data-stu-id="3297e-131">Division operator /</span></span>

<span data-ttu-id="3297e-132">除法运算符 `/` 用它的第一个操作数除以第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="3297e-132">The division operator `/` divides its first operand by its second operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="3297e-133">整数除法</span><span class="sxs-lookup"><span data-stu-id="3297e-133">Integer division</span></span>

<span data-ttu-id="3297e-134">对于整数类型的操作数，`/` 运算符的结果为整数类型，并且等于两个操作数之商向零舍入后的结果：</span><span class="sxs-lookup"><span data-stu-id="3297e-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="3297e-135">若要获取浮点数形式的两个操作数之商，请使用 `float`、`double` 或 `decimal` 类型：</span><span class="sxs-lookup"><span data-stu-id="3297e-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="3297e-136">浮点除法</span><span class="sxs-lookup"><span data-stu-id="3297e-136">Floating-point division</span></span>

<span data-ttu-id="3297e-137">对于 `float`、`double` 和 `decimal` 类型，`/` 运算符的结果为两个操作数之商：</span><span class="sxs-lookup"><span data-stu-id="3297e-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="3297e-138">如果操作数之一为 `decimal`，那么另一个操作数不得为 `float` 和 `double`，因为 `float` 和 `double` 都无法隐式转换为 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="3297e-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="3297e-139">必须将 `float` 或 `double` 操作数显式转换为 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="3297e-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="3297e-140">若要详细了解数值类型之间的隐式转换，请参阅[隐式数值转换表](../keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="3297e-140">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="3297e-141">余数运算符 %</span><span class="sxs-lookup"><span data-stu-id="3297e-141">Remainder operator %</span></span>

<span data-ttu-id="3297e-142">余数运算符 `%` 计算第一个操作数除以第二个操作数后的余数。</span><span class="sxs-lookup"><span data-stu-id="3297e-142">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="3297e-143">整数余数</span><span class="sxs-lookup"><span data-stu-id="3297e-143">Integer remainder</span></span>
  
<span data-ttu-id="3297e-144">对于整数类型的操作数，`a % b` 的结果是 `a - (a / b) * b` 得出的值。</span><span class="sxs-lookup"><span data-stu-id="3297e-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="3297e-145">非零余数的符号与第一个操作数的符号相同，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="3297e-145">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="3297e-146">使用 <xref:System.Math.DivRem%2A?displayProperty=nameWithType> 方法计算整数除法和余数结果。</span><span class="sxs-lookup"><span data-stu-id="3297e-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="3297e-147">浮点余数</span><span class="sxs-lookup"><span data-stu-id="3297e-147">Floating-point remainder</span></span>

<span data-ttu-id="3297e-148">对于 `float` 和 `double` 操作数，有限的 `x` 和 `y` 的 `x % y` 的结果是值 `z`，因此</span><span class="sxs-lookup"><span data-stu-id="3297e-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="3297e-149">`z`（如果不为零）的符号与 `x` 的符号相同。</span><span class="sxs-lookup"><span data-stu-id="3297e-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="3297e-150">`z` 的绝对值是 `|x| - n * |y|` 得出的值，其中 `n` 是小于或等于 `|x| / |y|` 的最大可能整数，`|x|` 和 `|y|` 分别是 `x` 和 `y` 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="3297e-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="3297e-151">计算余数的此方法类似于用于整数操作数的方法，但与 IEEE 754 不同。</span><span class="sxs-lookup"><span data-stu-id="3297e-151">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="3297e-152">如果需要符合 IEEE 754 的余数运算，使用 <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="3297e-152">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="3297e-153">有关非限定操作数的 `%` 运算符行为的信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[余数运算符](~/_csharplang/spec/expressions.md#remainder-operator)章节。</span><span class="sxs-lookup"><span data-stu-id="3297e-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="3297e-154">对于 `decimal` 操作数，余数运算符 `%` 等效于 <xref:System.Decimal?displayProperty=nameWithType> 类型的[余数运算符](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>)。</span><span class="sxs-lookup"><span data-stu-id="3297e-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="3297e-155">以下示例演示了具有浮动操作数的余数运算符的行为：</span><span class="sxs-lookup"><span data-stu-id="3297e-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="3297e-156">加法运算符 +</span><span class="sxs-lookup"><span data-stu-id="3297e-156">Addition operator +</span></span>

<span data-ttu-id="3297e-157">加法运算符 `+` 计算其操作数的和。</span><span class="sxs-lookup"><span data-stu-id="3297e-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="3297e-158">还可以将 `+` 运算符用于字符串串联和委托组合。</span><span class="sxs-lookup"><span data-stu-id="3297e-158">You also can use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="3297e-159">有关详细信息，请参阅[`+`运算符](addition-operator.md)一文。</span><span class="sxs-lookup"><span data-stu-id="3297e-159">For more information, see the [`+` operator](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="3297e-160">减法运算符 -</span><span class="sxs-lookup"><span data-stu-id="3297e-160">Subtraction operator -</span></span>

<span data-ttu-id="3297e-161">减法运算符 `-` 从其第一个操作数中减去其第二个操作数：</span><span class="sxs-lookup"><span data-stu-id="3297e-161">The subtraction operator `-` subtracts its second operand from its first operand:</span></span>

[!code-csharp-interactive[subtraction operator](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="3297e-162">还可以使用 `-` 运算符删除委托。</span><span class="sxs-lookup"><span data-stu-id="3297e-162">You also can use the `-` operator for delegate removal.</span></span> <span data-ttu-id="3297e-163">有关详细信息，请参阅[`-`运算符](subtraction-operator.md)一文。</span><span class="sxs-lookup"><span data-stu-id="3297e-163">For more information, see the [`-` operator](subtraction-operator.md) article.</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="3297e-164">运算符优先级和关联性</span><span class="sxs-lookup"><span data-stu-id="3297e-164">Operator precedence and associativity</span></span>

<span data-ttu-id="3297e-165">以下列表对优先级由高到低的顺序对算术运算符进行排序：</span><span class="sxs-lookup"><span data-stu-id="3297e-165">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="3297e-166">后缀增量 `x++` 和减量 `x--` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-166">Postfix increment `x++` and decrement `x--` operators.</span></span>
- <span data-ttu-id="3297e-167">前缀增量 `++x` 和减量 `--x` 以及一元 `+` 和 `-` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-167">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators.</span></span>
- <span data-ttu-id="3297e-168">乘法 `*`、`/` 和 `%` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-168">Multiplicative `*`, `/`, and `%` operators.</span></span>
- <span data-ttu-id="3297e-169">加法 `+` 和 `-` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-169">Additive `+` and `-` operators.</span></span>

<span data-ttu-id="3297e-170">二元算数运算符是左结合运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-170">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="3297e-171">也就是说，具有相同优先级的运算符按从左至右的顺序计算。</span><span class="sxs-lookup"><span data-stu-id="3297e-171">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="3297e-172">使用括号 `()` 更改由运算符优先级和关联性决定的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="3297e-172">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="3297e-173">要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="3297e-173">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="3297e-174">复合赋值</span><span class="sxs-lookup"><span data-stu-id="3297e-174">Compound assignment</span></span>

<span data-ttu-id="3297e-175">对于二元运算符 `op`，窗体的复合赋值表达式</span><span class="sxs-lookup"><span data-stu-id="3297e-175">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="3297e-176">等效于</span><span class="sxs-lookup"><span data-stu-id="3297e-176">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="3297e-177">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="3297e-177">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="3297e-178">以下示例使用算术运算符演示了复合赋值的用法：</span><span class="sxs-lookup"><span data-stu-id="3297e-178">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="3297e-179">还可以使用 `+=` 和 `-=` 运算符订阅和取消订阅[事件](../keywords/event.md)。</span><span class="sxs-lookup"><span data-stu-id="3297e-179">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from [events](../keywords/event.md).</span></span> <span data-ttu-id="3297e-180">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="3297e-180">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="3297e-181">算术溢出和被零除</span><span class="sxs-lookup"><span data-stu-id="3297e-181">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="3297e-182">当算术运算的结果超出所涉及数值类型的可能有限值范围时，算术运算符的行为取决于其操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="3297e-182">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="3297e-183">整数算术溢出</span><span class="sxs-lookup"><span data-stu-id="3297e-183">Integer arithmetic overflow</span></span>

<span data-ttu-id="3297e-184">整数被零除总是引发 <xref:System.DivideByZeroException>。</span><span class="sxs-lookup"><span data-stu-id="3297e-184">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="3297e-185">在整数算术溢出的情况下，溢出检查上下文（可能[已检查或未检查](../keywords/checked-and-unchecked.md)）将控制引发的行为：</span><span class="sxs-lookup"><span data-stu-id="3297e-185">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="3297e-186">在已检查的上下文中，如果在常数表达式中发生溢出，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="3297e-186">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="3297e-187">否则，当在运行时执行此运算时，则引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="3297e-187">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="3297e-188">在未检查的上下文中，会通过丢弃任何不适应目标类型的高序位来将结果截断。</span><span class="sxs-lookup"><span data-stu-id="3297e-188">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="3297e-189">在使用[已检查和未检查的](../keywords/checked-and-unchecked.md)语句时，可以使用 `checked` 和 `unchecked` 运算符来控制溢出检查上下文，在该上下文中将计算一个表达式：</span><span class="sxs-lookup"><span data-stu-id="3297e-189">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="3297e-190">默认情况下，算术运算发生在 *unchecked* 上下文中。</span><span class="sxs-lookup"><span data-stu-id="3297e-190">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="3297e-191">浮点运算溢出</span><span class="sxs-lookup"><span data-stu-id="3297e-191">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="3297e-192">使用 `float` 和 `double` 类型的算术运算永远不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="3297e-192">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="3297e-193">使用这些类型的算术运算的结果可能是表示无穷大和非数字的特殊值之一：</span><span class="sxs-lookup"><span data-stu-id="3297e-193">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="3297e-194">对于 `decimal` 类型的操作数，算术溢出始终会引发 <xref:System.OverflowException>，并且被零除始终会引发 <xref:System.DivideByZeroException>。</span><span class="sxs-lookup"><span data-stu-id="3297e-194">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="3297e-195">舍入误差</span><span class="sxs-lookup"><span data-stu-id="3297e-195">Round-off errors</span></span>

<span data-ttu-id="3297e-196">由于实数和浮点运算的浮点表达形式的常规限制，在使用浮点类型的计算中可能会发生舍入误差。</span><span class="sxs-lookup"><span data-stu-id="3297e-196">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, the round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="3297e-197">也就是说，表达式得出的结果可能与预期的数学运算结果不同。</span><span class="sxs-lookup"><span data-stu-id="3297e-197">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="3297e-198">以下示例演示了几种此类情况：</span><span class="sxs-lookup"><span data-stu-id="3297e-198">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](~/samples/snippets/csharp/language-reference/operators/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="3297e-199">有关详细信息，请参阅 [System.Double](/dotnet/api/system.double#remarks)、[System.Single](/dotnet/api/system.single#remarks) 或 [System.Decimal](/dotnet/api/system.decimal#remarks) 参考页面上的注解。</span><span class="sxs-lookup"><span data-stu-id="3297e-199">For more information, see remarks at [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3297e-200">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="3297e-200">Operator overloadability</span></span>

<span data-ttu-id="3297e-201">用户定义类型可以[重载](../keywords/operator.md)一元（`++`、`--`、`+` 和 `-`）和二元（`*`、`/`、`%``+` 和 `-`）算术运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-201">User-defined types can [overload](../keywords/operator.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="3297e-202">重载二元运算符时，对应的复合赋值运算符也会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="3297e-202">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="3297e-203">用户定义类型不能显式重载复合赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="3297e-203">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3297e-204">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3297e-204">C# language specification</span></span>

<span data-ttu-id="3297e-205">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="3297e-205">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="3297e-206">后缀增量和减量运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-206">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="3297e-207">前缀增量和减量运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-207">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="3297e-208">一元加运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-208">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="3297e-209">一元减运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-209">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="3297e-210">乘法运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-210">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="3297e-211">除法运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-211">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="3297e-212">余数运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-212">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="3297e-213">加法运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-213">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="3297e-214">减法运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-214">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="3297e-215">复合赋值</span><span class="sxs-lookup"><span data-stu-id="3297e-215">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="3297e-216">checked 和 unchecked 运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-216">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)

## <a name="see-also"></a><span data-ttu-id="3297e-217">请参阅</span><span class="sxs-lookup"><span data-stu-id="3297e-217">See also</span></span>

- [<span data-ttu-id="3297e-218">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3297e-218">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3297e-219">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3297e-219">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3297e-220">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3297e-220">C# Operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="3297e-221">.NET 中的数字</span><span class="sxs-lookup"><span data-stu-id="3297e-221">Numerics in .NET</span></span>](../../../standard/numerics.md)