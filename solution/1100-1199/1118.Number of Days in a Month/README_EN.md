# [1118. Number of Days in a Month](https://leetcode.com/problems/number-of-days-in-a-month)

[中文文档](/solution/1100-1199/1118.Number%20of%20Days%20in%20a%20Month/README.md)

## Description

<p>Given a year <code>Y</code> and a month <code>M</code>, return how many days there are in that month.</p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre>

<strong>Input: </strong>Y = <span id="example-input-1-1">1992</span>, M = <span id="example-input-1-2">7</span>

<strong>Output: </strong><span id="example-output-1">31</span>

</pre>

<p><strong>Example 2:</strong></p>

<pre>

<strong>Input: </strong>Y = <span id="example-input-2-1">2000</span>, M = <span id="example-input-2-2">2</span>

<strong>Output: </strong><span id="example-output-2">29</span>

</pre>

<p><strong>Example 3:</strong></p>

<pre>

<strong>Input: </strong>Y = <span id="example-input-3-1">1900</span>, M = <span id="example-input-3-2">2</span>

<strong>Output: </strong><span id="example-output-3">28</span>

</pre>

<p>&nbsp;</p>

<p><strong>Note:</strong></p>

<ol>
	<li><code>1583 &lt;= Y &lt;= 2100</code></li>
	<li><code>1 &lt;= M &lt;= 12</code></li>
</ol>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def numberOfDays(self, year: int, month: int) -> int:
        leap = (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)
        days = [0, 31, 29 if leap else 28, 31,
                30, 31, 30, 31, 31, 30, 31, 30, 31]
        return days[month]
```

### **Java**

```java
class Solution {
    public int numberOfDays(int year, int month) {
        boolean leap = (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
        int[] days = new int[]{0, 31, leap ? 29 : 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
        return days[month];
    }
}
```

### **C++**

```cpp
class Solution {
public:
    int numberOfDays(int year, int month) {
        bool leap = (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
        vector<int> days = {0, 31, leap ? 29 : 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
        return days[month];
    }
};
```

### **Go**

```go
func numberOfDays(year int, month int) int {
	leap := (year%4 == 0 && year%100 != 0) || (year%400 == 0)
	x := 28
	if leap {
		x = 29
	}
	days := []int{0, 31, x, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31}
	return days[month]
}
```

### **...**

```

```

<!-- tabs:end -->
