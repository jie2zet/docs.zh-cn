---
title: 指针相关运算符 - C# 参考
description: 了解在使用指针时可以使用的 C# 运算符。
ms.date: 05/20/2019
author: pkulikov
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- pointer related operators [C#]
- address-of operator [C#]
- '& operator [C#]'
- pointer indirection operator [C#]
- dereference operator [C#]
- '* operator [C#]'
- pointer member access operator [C#]
- -> operator [C#]
- pointer element access [C#]
- '[] operator [C#]'
- pointer arithmetic [C#]
- pointer increment [C#]
- pointer decrement [C#]
- pointer comparison [C#]
ms.openlocfilehash: 012e4fe9b8ee49f3b6b7240ac4ccb21dba70a8a9
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882775"
---
# <a name="pointer-related-operators-c-reference"></a><span data-ttu-id="5bf51-103">指针相关运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5bf51-103">Pointer related operators (C# Reference)</span></span>

<span data-ttu-id="5bf51-104">可以使用以下运算符来使用指针：</span><span class="sxs-lookup"><span data-stu-id="5bf51-104">You can use the following operators to work with pointers:</span></span>

- <span data-ttu-id="5bf51-105">一元 [`&` (address-of) ](#address-of-operator-)运算符：用于获取变量的地址</span><span class="sxs-lookup"><span data-stu-id="5bf51-105">Unary [`&` (address-of)](#address-of-operator-) operator: to get the address of a variable</span></span>
- <span data-ttu-id="5bf51-106">一元 [`*`（指针间接）](#pointer-indirection-operator-)运算符：用于获取指针指向的变量</span><span class="sxs-lookup"><span data-stu-id="5bf51-106">Unary [`*` (pointer indirection)](#pointer-indirection-operator-) operator: to obtain the variable pointed by a pointer</span></span>
- <span data-ttu-id="5bf51-107">[`->`（成员访问）](#pointer-member-access-operator--)和 [`[]`（元素访问）](#pointer-element-access-operator-)运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-107">The [`->` (member access)](#pointer-member-access-operator--) and [`[]` (element access)](#pointer-element-access-operator-) operators</span></span>
- <span data-ttu-id="5bf51-108">算术运算符 [`+`、`-`、`++` 和 `--`](#pointer-arithmetic-operators)</span><span class="sxs-lookup"><span data-stu-id="5bf51-108">Arithmetic operators [`+`, `-`, `++`, and `--`](#pointer-arithmetic-operators)</span></span>
- <span data-ttu-id="5bf51-109">比较运算符 [`==`、`!=`、`<`、`>`、`<=` 和 `>=`](#pointer-comparison-operators)</span><span class="sxs-lookup"><span data-stu-id="5bf51-109">Comparison operators [`==`, `!=`, `<`, `>`, `<=`, and `>=`](#pointer-comparison-operators)</span></span>

<span data-ttu-id="5bf51-110">有关指针类型的信息，请参阅[指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)。</span><span class="sxs-lookup"><span data-stu-id="5bf51-110">For information about pointer types, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5bf51-111">任何带指针的运算都需要使用[不安全的](../keywords/unsafe.md)上下文。</span><span class="sxs-lookup"><span data-stu-id="5bf51-111">Any operation with pointers requires [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="5bf51-112">必须使用 [`-unsafe`](../compiler-options/unsafe-compiler-option.md) 编译器选项编译包含不安全块的代码。</span><span class="sxs-lookup"><span data-stu-id="5bf51-112">The code that contains unsafe blocks must be compiled with the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

## <a name="address-of-operator-amp"></a><span data-ttu-id="5bf51-113">Address-of 运算符 &amp;</span><span class="sxs-lookup"><span data-stu-id="5bf51-113">Address-of operator &amp;</span></span>

<span data-ttu-id="5bf51-114">一元 `&` 运算符返回其操作数的地址：</span><span class="sxs-lookup"><span data-stu-id="5bf51-114">The unary `&` operator returns the address of its operand:</span></span>

[!code-csharp[address of local](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#AddressOf)]

<span data-ttu-id="5bf51-115">`&` 运算符的操作数必须是固定变量。</span><span class="sxs-lookup"><span data-stu-id="5bf51-115">The operand of the `&` operator must be a fixed variable.</span></span> <span data-ttu-id="5bf51-116">固定变量是驻留在不受[垃圾回收器](../../../standard/garbage-collection/index.md)操作影响的存储位置的变量。</span><span class="sxs-lookup"><span data-stu-id="5bf51-116">*Fixed* variables are variables that reside in storage locations that are unaffected by operation of the [garbage collector](../../../standard/garbage-collection/index.md).</span></span> <span data-ttu-id="5bf51-117">在上述示例中，局部变量 `number` 是固定变量，因为它驻留在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="5bf51-117">In the preceding example, the local variable `number` is a fixed variable, because it resides on the stack.</span></span> <span data-ttu-id="5bf51-118">驻留在可能受垃圾回收器影响的存储位置的变量（如重定位）称为可移动变量。</span><span class="sxs-lookup"><span data-stu-id="5bf51-118">Variables that reside in storage locations that can be affected by the garbage collector (for example, relocated) are called *movable* variables.</span></span> <span data-ttu-id="5bf51-119">对象字段和数组元素是可移动变量的示例。</span><span class="sxs-lookup"><span data-stu-id="5bf51-119">Object fields and array elements are examples of movable variables.</span></span> <span data-ttu-id="5bf51-120">如果使用[固定](../keywords/fixed-statement.md)语句“固定”，则可以获取可移动变量的地址。</span><span class="sxs-lookup"><span data-stu-id="5bf51-120">You can get the address of a movable variable if you "fix", or "pin", it with the [fixed](../keywords/fixed-statement.md) statement.</span></span> <span data-ttu-id="5bf51-121">获取的地址仅在 `fixed` 语句块的持续时间内有效。</span><span class="sxs-lookup"><span data-stu-id="5bf51-121">The obtained address is valid only for the duration of the `fixed` statement block.</span></span> <span data-ttu-id="5bf51-122">以下示例显示如何使用 `fixed` 语句和 `&` 运算符：</span><span class="sxs-lookup"><span data-stu-id="5bf51-122">The following example shows how to use the `fixed` statement and the `&` operator:</span></span>

[!code-csharp[address of fixed](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#AddressOfFixed)]

<span data-ttu-id="5bf51-123">你也无法获取常量或值的地址。</span><span class="sxs-lookup"><span data-stu-id="5bf51-123">You can't get the address of a constant or a value.</span></span>

<span data-ttu-id="5bf51-124">有关固定变量和可移动变量的详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[固定变量和可移动变量](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)部分。</span><span class="sxs-lookup"><span data-stu-id="5bf51-124">For more information about fixed and movable variables, see the [Fixed and moveable variables](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="5bf51-125">二进制 `&` 运算符计算其布尔操作数的[逻辑 AND](boolean-logical-operators.md#logical-and-operator-) 或其整型操作数的[位逻辑 AND](bitwise-and-shift-operators.md#logical-and-operator-)。</span><span class="sxs-lookup"><span data-stu-id="5bf51-125">The binary `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its Boolean operands or the [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) of its integral operands.</span></span>

## <a name="pointer-indirection-operator-"></a><span data-ttu-id="5bf51-126">指针间接运算符 \*</span><span class="sxs-lookup"><span data-stu-id="5bf51-126">Pointer indirection operator \*</span></span>

<span data-ttu-id="5bf51-127">一元指针间接运算符 `*` 获取其操作数指向的变量。</span><span class="sxs-lookup"><span data-stu-id="5bf51-127">The unary pointer indirection operator `*` obtains the variable to which its operand points.</span></span> <span data-ttu-id="5bf51-128">它也称为取消引用运算符。</span><span class="sxs-lookup"><span data-stu-id="5bf51-128">It's also known as the dereference operator.</span></span> <span data-ttu-id="5bf51-129">`*` 运算符的操作数必须是指针类型。</span><span class="sxs-lookup"><span data-stu-id="5bf51-129">The operand of the `*` operator must be of a pointer type.</span></span>

[!code-csharp[pointer indirection](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#PointerIndirection)]

<span data-ttu-id="5bf51-130">不能将 `*` 运算符应用于类型 `void*` 的表达式。</span><span class="sxs-lookup"><span data-stu-id="5bf51-130">You cannot apply the `*` operator to an expression of type `void*`.</span></span>

<span data-ttu-id="5bf51-131">二进制 `*` 运算符计算其数值操作数的[乘积](arithmetic-operators.md#multiplication-operator-)。</span><span class="sxs-lookup"><span data-stu-id="5bf51-131">The binary `*` operator computes the [product](arithmetic-operators.md#multiplication-operator-) of its numeric operands.</span></span>

## <a name="pointer-member-access-operator--"></a><span data-ttu-id="5bf51-132">指针成员访问运算符 -></span><span class="sxs-lookup"><span data-stu-id="5bf51-132">Pointer member access operator -></span></span>

<span data-ttu-id="5bf51-133">`->` 运算符将[指针间接](#pointer-indirection-operator-)和[成员访问](member-access-operators.md#member-access-operator-)合并。</span><span class="sxs-lookup"><span data-stu-id="5bf51-133">The `->` operator combines [pointer indirection](#pointer-indirection-operator-) and [member access](member-access-operators.md#member-access-operator-).</span></span> <span data-ttu-id="5bf51-134">也就是说，如果 `x` 是类型为 `T*` 的指针且 `y` 是 `T` 的可访问成员，则形式的表达式</span><span class="sxs-lookup"><span data-stu-id="5bf51-134">That is, if `x` is a pointer of type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="5bf51-135">等效于</span><span class="sxs-lookup"><span data-stu-id="5bf51-135">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="5bf51-136">下面的示例演示 `->` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="5bf51-136">The following example demonstrates the usage of the `->` operator:</span></span>

[!code-csharp[pointer member access](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#MemberAccess)]

<span data-ttu-id="5bf51-137">不能将 `->` 运算符应用于类型 `void*` 的表达式。</span><span class="sxs-lookup"><span data-stu-id="5bf51-137">You cannot apply the `->` operator to an expression of type `void*`.</span></span>

## <a name="pointer-element-access-operator-"></a><span data-ttu-id="5bf51-138">指针元素访问运算符 []</span><span class="sxs-lookup"><span data-stu-id="5bf51-138">Pointer element access operator []</span></span>

<span data-ttu-id="5bf51-139">对于指针类型的表达式 `p`，`p[n]` 形式的指针元素访问计算方式为 `*(p + n)`，其中 `n` 必须是可隐式转换为 `int`、`uint`、`long` 或 `ulong` 的类型。</span><span class="sxs-lookup"><span data-stu-id="5bf51-139">For an expression `p` of a pointer type, a pointer element access of the form `p[n]` is evaluated as `*(p + n)`, where `n` must be of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="5bf51-140">有关带有指针的 `+` 运算符的行为的信息，请参阅[向指针中增加或从指针中减少整数值](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer)部分。</span><span class="sxs-lookup"><span data-stu-id="5bf51-140">For information about the behavior of the `+` operator with pointers, see the [Addition or subtraction of an integral value to or from a pointer](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) section.</span></span>

<span data-ttu-id="5bf51-141">以下示例演示如何使用指针和 `[]` 运算符访问数组元素：</span><span class="sxs-lookup"><span data-stu-id="5bf51-141">The following example demonstrates how to access array elements with a pointer and the `[]` operator:</span></span>

[!code-csharp[pointer element access](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#ElementAccess)]

<span data-ttu-id="5bf51-142">该示例使用 [`stackalloc` 运算符](../keywords/stackalloc.md)在堆栈上分配内存块。</span><span class="sxs-lookup"><span data-stu-id="5bf51-142">The example uses the [`stackalloc` operator](../keywords/stackalloc.md) to allocate a block of memory on the stack.</span></span>

> [!NOTE]
> <span data-ttu-id="5bf51-143">指针元素访问运算符不检查越界错误。</span><span class="sxs-lookup"><span data-stu-id="5bf51-143">The pointer element access operator doesn't check for out-of-bounds errors.</span></span>

<span data-ttu-id="5bf51-144">不能将 `[]` 用于带有类型为 `void*` 的表达式的指针元素访问。</span><span class="sxs-lookup"><span data-stu-id="5bf51-144">You cannot use `[]` for pointer element access with an expression of type `void*`.</span></span>

<span data-ttu-id="5bf51-145">还可以将 `[]` 运算符用于[数组元素或索引器访问](member-access-operators.md#indexer-operator-)。</span><span class="sxs-lookup"><span data-stu-id="5bf51-145">You also can use the `[]` operator for [array element or indexer access](member-access-operators.md#indexer-operator-).</span></span>

## <a name="pointer-arithmetic-operators"></a><span data-ttu-id="5bf51-146">指针算术运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-146">Pointer arithmetic operators</span></span>

<span data-ttu-id="5bf51-147">可以使用指针执行以下算术运算：</span><span class="sxs-lookup"><span data-stu-id="5bf51-147">You can perform the following arithmetic operations with pointers:</span></span>

- <span data-ttu-id="5bf51-148">向指针增加或从指针中减少一个整数值</span><span class="sxs-lookup"><span data-stu-id="5bf51-148">Add or subtract an integral value to or from a pointer</span></span>
- <span data-ttu-id="5bf51-149">减少两个指针</span><span class="sxs-lookup"><span data-stu-id="5bf51-149">Subtract two pointers</span></span>
- <span data-ttu-id="5bf51-150">增量或减量指针</span><span class="sxs-lookup"><span data-stu-id="5bf51-150">Increment or decrement a pointer</span></span>

<span data-ttu-id="5bf51-151">无法使用类型为 `void*` 的指针执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="5bf51-151">You cannot perform those operations with pointers of type `void*`.</span></span>

<span data-ttu-id="5bf51-152">有关带数值类型的受支持的算术运算的信息，请参阅[算术运算符](arithmetic-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="5bf51-152">For information about supported arithmetic operations with numeric types, see [Arithmetic operators](arithmetic-operators.md).</span></span>

### <a name="addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer"></a><span data-ttu-id="5bf51-153">向指针增加或从指针中减少整数值</span><span class="sxs-lookup"><span data-stu-id="5bf51-153">Addition or subtraction of an integral value to or from a pointer</span></span>

<span data-ttu-id="5bf51-154">对于类型为 `T*` 的指针`p`和可隐式转换为 `int`、`uint`、`long` 或 `ulong` 的类型的表达式 `n`，加法和减法定义如下：</span><span class="sxs-lookup"><span data-stu-id="5bf51-154">For a pointer `p` of type `T*` and an expression `n` of a type implicitly convertible to `int`, `uint`, `long`, or `ulong`, addition and subtraction are defined as follows:</span></span>

- <span data-ttu-id="5bf51-155">`p + n` 和 `n + p` 表达式都生成 `T*` 类型的指针，该指针是将 `n * sizeof(T)` 添加到 `p` 给出的地址得到的。</span><span class="sxs-lookup"><span data-stu-id="5bf51-155">Both `p + n` and `n + p` expressions produce a pointer of type `T*` that results from adding `n * sizeof(T)` to the address given by `p`.</span></span>
- <span data-ttu-id="5bf51-156">`p - n` 表达式生成类型为 `T*` 的指针，该指针是从 `p` 给出的地址中减去 `n * sizeof(T)` 得到的。</span><span class="sxs-lookup"><span data-stu-id="5bf51-156">The `p - n` expression produces a pointer of type `T*` that results from subtracting `n * sizeof(T)` from the address given by `p`.</span></span>

<span data-ttu-id="5bf51-157">[`sizeof` 运算符](../keywords/sizeof.md)获取类型的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5bf51-157">The [`sizeof` operator](../keywords/sizeof.md) obtains the size of a type in bytes.</span></span>

<span data-ttu-id="5bf51-158">以下示例演示了 `+` 运算符与指针的用法：</span><span class="sxs-lookup"><span data-stu-id="5bf51-158">The following example demonstrates the usage of the `+` operator with a pointer:</span></span>

[!code-csharp[pointer addition](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#AddNumber)]

### <a name="pointer-subtraction"></a><span data-ttu-id="5bf51-159">指针减法</span><span class="sxs-lookup"><span data-stu-id="5bf51-159">Pointer subtraction</span></span>

<span data-ttu-id="5bf51-160">对于类型为 `T*` 的两个指针 `p1` 和 `p2`，表达式 `p1 - p2` 生成 `p1` 和 `p2` 给出的地址之间的差除以 `sizeof(T)` 的值。</span><span class="sxs-lookup"><span data-stu-id="5bf51-160">For two pointers `p1` and `p2` of type `T*`, the expression `p1 - p2` produces the difference between the addresses given by `p1` and `p2` divided by `sizeof(T)`.</span></span> <span data-ttu-id="5bf51-161">结果的类型为 `long`。</span><span class="sxs-lookup"><span data-stu-id="5bf51-161">The type of the result is `long`.</span></span> <span data-ttu-id="5bf51-162">即 `p1 - p2` 计算公式为 `((long)(p1) - (long)(p2)) / sizeof(T)`。</span><span class="sxs-lookup"><span data-stu-id="5bf51-162">That is, `p1 - p2` is computed as `((long)(p1) - (long)(p2)) / sizeof(T)`.</span></span>

<span data-ttu-id="5bf51-163">以下示例演示了指针减法：</span><span class="sxs-lookup"><span data-stu-id="5bf51-163">The following example demonstrates the pointer subtraction:</span></span>

[!code-csharp[pointer subtraction](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#SubtractPointers)]

### <a name="pointer-increment-and-decrement"></a><span data-ttu-id="5bf51-164">指针增量和减量</span><span class="sxs-lookup"><span data-stu-id="5bf51-164">Pointer increment and decrement</span></span>

<span data-ttu-id="5bf51-165">`++` 增量运算符将 1 [添加](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer)到其指针操作数。</span><span class="sxs-lookup"><span data-stu-id="5bf51-165">The `++` increment operator [adds](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 to its pointer operand.</span></span> <span data-ttu-id="5bf51-166">`--` 减量运算符从其指针操作数中[减去](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1。</span><span class="sxs-lookup"><span data-stu-id="5bf51-166">The `--` decrement operator [subtracts](#addition-or-subtraction-of-an-integral-value-to-or-from-a-pointer) 1 from its pointer operand.</span></span>

<span data-ttu-id="5bf51-167">两种运算符都支持两种形式：后缀（`p++` 和 `p--`）和前缀（`++p` 和 `--p`）。</span><span class="sxs-lookup"><span data-stu-id="5bf51-167">Both operators are supported in two forms: postfix (`p++` and `p--`) and prefix (`++p` and `--p`).</span></span> <span data-ttu-id="5bf51-168">`p++` 和 `p--` 的结果是该运算之前 `p` 的值。</span><span class="sxs-lookup"><span data-stu-id="5bf51-168">The result of `p++` and `p--` is the value of `p` *before* the operation.</span></span> <span data-ttu-id="5bf51-169">`++p` 和 `--p` 的结果是该运算之后 `p` 的值。</span><span class="sxs-lookup"><span data-stu-id="5bf51-169">The result of `++p` and `--p` is the value of `p` *after* the operation.</span></span>

<span data-ttu-id="5bf51-170">以下示例演示了后缀和前缀增量运算符的行为：</span><span class="sxs-lookup"><span data-stu-id="5bf51-170">The following example demonstrates the behavior of both postfix and prefix increment operators:</span></span>

[!code-csharp[pointer increment](~/samples/snippets/csharp/language-reference/operators/PointerOperators.cs#Increment)]

## <a name="pointer-comparison-operators"></a><span data-ttu-id="5bf51-171">指针比较运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-171">Pointer comparison operators</span></span>

<span data-ttu-id="5bf51-172">可以使用 `==`、`!=`、`<``>`、`<=` 和 `>=` 运算符来比较任何指针类型（包括 `void*`）的操作数。</span><span class="sxs-lookup"><span data-stu-id="5bf51-172">You can use the `==`, `!=`, `<`, `>`, `<=`, and `>=` operators to compare operands of any pointer type, including `void*`.</span></span> <span data-ttu-id="5bf51-173">这些运算符将两个操作数给出的地址进行比较，就好像它们是无符号整数一样。</span><span class="sxs-lookup"><span data-stu-id="5bf51-173">Those operators compare the addresses given by the two operands as if they were unsigned integers.</span></span>

<span data-ttu-id="5bf51-174">有关这些运算符对其他类型操作数的行为的信息，请参阅[等式运算符](equality-operators.md)和[比较运算符](comparison-operators.md)一文。</span><span class="sxs-lookup"><span data-stu-id="5bf51-174">For information about the behavior of those operators for operands of other types, see the [Equality operators](equality-operators.md) and [Comparison operators](comparison-operators.md) articles.</span></span>

## <a name="operator-precedence"></a><span data-ttu-id="5bf51-175">运算符优先级</span><span class="sxs-lookup"><span data-stu-id="5bf51-175">Operator precedence</span></span>

<span data-ttu-id="5bf51-176">以下列表按优先级从高到低的顺序对指针相关运算符进行排序：</span><span class="sxs-lookup"><span data-stu-id="5bf51-176">The following list orders pointer related operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="5bf51-177">后缀增量 `x++` 和减量 `x--` 运算符以及 `->` 和 `[]` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-177">Postfix increment `x++` and decrement `x--` operators and the `->` and `[]` operators</span></span>
- <span data-ttu-id="5bf51-178">前缀增量 `++x` 和减量 `--x` 运算符以及 `&` 和 `*` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-178">Prefix increment `++x` and decrement `--x` operators and the `&` and `*` operators</span></span>
- <span data-ttu-id="5bf51-179">加法 `+` 和 `-` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-179">Additive `+` and `-` operators</span></span>
- <span data-ttu-id="5bf51-180">比较 `<`、`>`、`<=` 和 `>=` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-180">Comparison `<`, `>`, `<=`, and `>=` operators</span></span>
- <span data-ttu-id="5bf51-181">等式 `==` 和 `!=` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-181">Equality `==` and `!=` operators</span></span>

<span data-ttu-id="5bf51-182">使用括号 `()` 更改运算符优先级所施加的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="5bf51-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence.</span></span>

<span data-ttu-id="5bf51-183">要了解按优先级排序的完整 C# 运算符列表，请参阅 [C# 运算符](index.md)。</span><span class="sxs-lookup"><span data-stu-id="5bf51-183">For the complete list of C# operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5bf51-184">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="5bf51-184">Operator overloadability</span></span>

<span data-ttu-id="5bf51-185">用户定义的类型不能重载与指针相关的运算符 `&`、`*`、`->` 和 `[]`。</span><span class="sxs-lookup"><span data-stu-id="5bf51-185">A user-defined type cannot overload the pointer related operators `&`, `*`, `->`, and `[]`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5bf51-186">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5bf51-186">C# language specification</span></span>

<span data-ttu-id="5bf51-187">有关更多信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的以下部分：</span><span class="sxs-lookup"><span data-stu-id="5bf51-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="5bf51-188">固定和可移动变量</span><span class="sxs-lookup"><span data-stu-id="5bf51-188">Fixed and moveable variables</span></span>](~/_csharplang/spec/unsafe-code.md#fixed-and-moveable-variables)
- [<span data-ttu-id="5bf51-189">address-of 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-189">The address-of operator</span></span>](~/_csharplang/spec/unsafe-code.md#the-address-of-operator)
- [<span data-ttu-id="5bf51-190">指针间接</span><span class="sxs-lookup"><span data-stu-id="5bf51-190">Pointer indirection</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-indirection)
- [<span data-ttu-id="5bf51-191">指针成员访问</span><span class="sxs-lookup"><span data-stu-id="5bf51-191">Pointer member access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-member-access)
- [<span data-ttu-id="5bf51-192">指针元素访问</span><span class="sxs-lookup"><span data-stu-id="5bf51-192">Pointer element access</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-element-access)
- [<span data-ttu-id="5bf51-193">指针算术</span><span class="sxs-lookup"><span data-stu-id="5bf51-193">Pointer arithmetic</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-arithmetic)
- [<span data-ttu-id="5bf51-194">指针增量和减量</span><span class="sxs-lookup"><span data-stu-id="5bf51-194">Pointer increment and decrement</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-increment-and-decrement)
- [<span data-ttu-id="5bf51-195">指针比较</span><span class="sxs-lookup"><span data-stu-id="5bf51-195">Pointer comparison</span></span>](~/_csharplang/spec/unsafe-code.md#pointer-comparison)

## <a name="see-also"></a><span data-ttu-id="5bf51-196">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bf51-196">See also</span></span>

- [<span data-ttu-id="5bf51-197">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5bf51-197">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5bf51-198">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5bf51-198">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5bf51-199">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-199">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5bf51-200">指针类型</span><span class="sxs-lookup"><span data-stu-id="5bf51-200">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="5bf51-201">`unsafe` 关键字</span><span class="sxs-lookup"><span data-stu-id="5bf51-201">`unsafe` keyword</span></span>](../keywords/unsafe.md)
- [<span data-ttu-id="5bf51-202">`fixed` 关键字</span><span class="sxs-lookup"><span data-stu-id="5bf51-202">`fixed` keyword</span></span>](../keywords/fixed-statement.md)
- [<span data-ttu-id="5bf51-203">`stackalloc` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-203">`stackalloc` operator</span></span>](../keywords/stackalloc.md)
- [<span data-ttu-id="5bf51-204">`sizeof` 运算符</span><span class="sxs-lookup"><span data-stu-id="5bf51-204">`sizeof` operator</span></span>](../keywords/sizeof.md)