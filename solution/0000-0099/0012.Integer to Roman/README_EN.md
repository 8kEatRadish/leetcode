# [12. Integer to Roman](https://leetcode.com/problems/integer-to-roman)

[中文文档](/solution/0000-0099/0012.Integer%20to%20Roman/README.md)

## Description

<p>Roman numerals are represented by seven different symbols:&nbsp;<code>I</code>, <code>V</code>, <code>X</code>, <code>L</code>, <code>C</code>, <code>D</code> and <code>M</code>.</p>

<pre>

<strong>Symbol</strong>       <strong>Value</strong>

I             1

V             5

X             10

L             50

C             100

D             500

M             1000</pre>

<p>For example,&nbsp;two is written as <code>II</code>&nbsp;in Roman numeral, just two one&#39;s added together. Twelve is written as, <code>XII</code>, which is simply <code>X</code> + <code>II</code>. The number twenty seven is written as <code>XXVII</code>, which is <code>XX</code> + <code>V</code> + <code>II</code>.</p>

<p>Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not <code>IIII</code>. Instead, the number four is written as <code>IV</code>. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as <code>IX</code>. There are six instances where subtraction is used:</p>

<ul>
    <li><code>I</code> can be placed before <code>V</code> (5) and <code>X</code> (10) to make 4 and 9.&nbsp;</li>
    <li><code>X</code> can be placed before <code>L</code> (50) and <code>C</code> (100) to make 40 and 90.&nbsp;</li>
    <li><code>C</code> can be placed before <code>D</code> (500) and <code>M</code> (1000) to make 400 and 900.</li>
</ul>

<p>Given an integer, convert it to a roman numeral. Input is guaranteed to be within the range from 1 to 3999.</p>

<p><strong>Example 1:</strong></p>

<pre>

<strong>Input:</strong>&nbsp;3

<strong>Output:</strong> &quot;III&quot;</pre>

<p><strong>Example 2:</strong></p>

<pre>

<strong>Input:</strong>&nbsp;4

<strong>Output:</strong> &quot;IV&quot;</pre>

<p><strong>Example 3:</strong></p>

<pre>

<strong>Input:</strong>&nbsp;9

<strong>Output:</strong> &quot;IX&quot;</pre>

<p><strong>Example 4:</strong></p>

<pre>

<strong>Input:</strong>&nbsp;58

<strong>Output:</strong> &quot;LVIII&quot;

<strong>Explanation:</strong> L = 50, V = 5, III = 3.

</pre>

<p><strong>Example 5:</strong></p>

<pre>

<strong>Input:</strong>&nbsp;1994

<strong>Output:</strong> &quot;MCMXCIV&quot;

<strong>Explanation:</strong> M = 1000, CM = 900, XC = 90 and IV = 4.</pre>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def intToRoman(self, num: int) -> str:
        nums = [(1000, 'M'), (900, 'CM'), (500, 'D'), (400, 'CD'), (100, 'C'), (90, 'XC'), (50, 'L'), (40, 'XL'), (10, 'X'), (9, 'IX'), (5, 'V'), (4, 'IV'), (1, 'I')]
        res = []
        for k, v in nums:
            while num >= k:
                num -= k
                res.append(v)
        return ''.join(res)
```

### **Java**

```java
class Solution {
    public String intToRoman(int num) {
        int[] nums = new int[]{1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        String[] romans = new String[]{"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < nums.length; ++i) {
            while (num >= nums[i]) {
                num -= nums[i];
                sb.append(romans[i]);
            }
        }
        return sb.toString();
    }
}
```

### **...**

```

```

<!-- tabs:end -->
