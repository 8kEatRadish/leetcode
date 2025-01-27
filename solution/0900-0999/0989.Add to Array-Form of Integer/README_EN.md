# [989. Add to Array-Form of Integer](https://leetcode.com/problems/add-to-array-form-of-integer)

[中文文档](/solution/0900-0999/0989.Add%20to%20Array-Form%20of%20Integer/README.md)

## Description

<p>For a non-negative integer <code>X</code>, the&nbsp;<em>array-form of <code>X</code></em>&nbsp;is an array of its digits in left to right order.&nbsp; For example, if <code>X = 1231</code>, then the array form is&nbsp;<code>[1,2,3,1]</code>.</p>

<p>Given the array-form <code>A</code> of a non-negative&nbsp;integer <code>X</code>, return the array-form of the integer <code>X+K</code>.</p>

<p>&nbsp;</p>

<ol>

</ol>

<div>

<p><strong>Example 1:</strong></p>

<pre>

<strong>Input: </strong>A = <span id="example-input-1-1">[1,2,0,0]</span>, K = 34

<strong>Output: </strong><span id="example-output-1">[1,2,3,4]</span>

<strong>Explanation: </strong>1200 + 34 = 1234

</pre>

<div>

<p><strong>Example 2:</strong></p>

<pre>

<strong>Input: </strong>A = <span id="example-input-2-1">[2,7,4]</span>, K = <span id="example-input-2-2">181</span>

<strong>Output: </strong><span id="example-output-2">[4,5,5]</span>

<strong>Explanation: </strong>274 + 181 = 455

</pre>

<div>

<p><strong>Example 3:</strong></p>

<pre>

<strong>Input: </strong>A = <span id="example-input-3-1">[2,1,5]</span>, K = <span id="example-input-3-2">806</span>

<strong>Output: </strong><span id="example-output-3">[1,0,2,1]</span>

<strong>Explanation: </strong>215 + 806 = 1021

</pre>

<div>

<p><strong>Example 4:</strong></p>

<pre>

<strong>Input: </strong>A = <span id="example-input-4-1">[9,9,9,9,9,9,9,9,9,9]</span>, K = <span id="example-input-4-2">1</span>

<strong>Output: </strong><span id="example-output-4">[1,0,0,0,0,0,0,0,0,0,0]</span>

<strong>Explanation: </strong>9999999999 + 1 = 10000000000

</pre>

<p>&nbsp;</p>

<p><strong>Note：</strong></p>

<ol>
    <li><code>1 &lt;= A.length &lt;= 10000</code></li>
    <li><code>0 &lt;= A[i] &lt;= 9</code></li>
    <li><code>0 &lt;= K &lt;= 10000</code></li>
    <li>If <code>A.length &gt; 1</code>, then <code>A[0] != 0</code></li>
</ol>

</div>

</div>

</div>

</div>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def addToArrayForm(self, A: List[int], K: int) -> List[int]:
        n = len(A) - 1
        carry, res = 0, []
        while n >= 0 or K != 0 or carry != 0:
            carry += (0 if n < 0 else A[n]) + (K % 10)
            res.append(carry % 10)
            K //= 10
            carry //= 10
            n -= 1
        return res[::-1]
```

### **Java**

```java
class Solution {
    public List<Integer> addToArrayForm(int[] A, int K) {
        int n = A.length - 1;
        List<Integer> res = new ArrayList<>();
        int carry = 0;
        while (n >= 0 || K != 0 || carry != 0) {
            carry += (n < 0 ? 0 : A[n]) + (K % 10);
            res.add(carry % 10);
            K /= 10;
            carry /= 10;
            --n;
        }
        Collections.reverse(res);
        return res;
    }
}
```

### **...**

```

```

<!-- tabs:end -->
