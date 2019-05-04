# 替换空格

## 题目

[牛客网](https://www.nowcoder.com/questionTerminal/4060ac7e3e404ad1a894ef3e17650423)

请实现一个函数，将一个字符串中的每个空格替换成`“%20”`。例如，当字符串为`We Are Happy.`则经过替换之后的字符串为 `We%20Are%20Happy`。

## 解题思路

  1. 通过字符串中空格的个数，计算新字符串长度
  2. 两个指针进行字符串拷贝，当遇到`‘ ’`时替换为 `%20`

```
public String replaceSpace(StringBuffer str) {
    char[] chars = str.toString().toCharArray();
    int spaceCount = 0;

    for (char c : chars) {
        if (c == ' ') spaceCount++;
    }

    char[] res = new char[chars.length + spaceCount * 2];

    for (int i = 0, j = 0; i < chars.length; i++) {
        if (chars[i] == ' ') {
            res[j++] = '%';
            res[j++] = '2';
            res[j++] = '0';
        } else {
            res[j++] = chars[i];
        }
    }

    return new String(res);
}
```
