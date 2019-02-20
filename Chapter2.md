## 大概
### Basic Style Rules
#### Element Selectors
Selecting element using the element selector
``` css
p {
  color: gray;
}
```

#### 选择器
1. **[foo~="bar"]** 选择空格间隔的包含 bar 的属性
2. **[foo\*="bar"]** 选择字符里包含 bar 的属性
3. **[foo^="bar"]** 选择字符串开头为 bar 的属性
4. **[foo$="bar"]** 选择字符串结尾为 bar 的属性
5. **[foo|="bar"]** 选择字符串开头为 bar 且或包含 "-" 的属性
6. **[href\$='.PDF' i]** 添加 i 来忽略大小写
7. :root 选择最顶层的 HTML 元素
8. :empty 选择无子元素的元素，包含 文本 和 空格
9. :first-child, :last-child, :only-child, 常用于子节点，第一个元素，最后，或者唯一一个 元素
10. :first-type, :last-type, :only-of-type, 常用于选择元素, 但不局限于是否第一个元素，而是元素类型的第一个
11. 上述规则在 document 或者 body 节点下不生效
12. :nth-child(n), nth-last-child n 从 1 开始, 选择第 n 个元素
13. :nth-child(2n+1), nth-last-child 选择偶数
14. :nth-of-type
15. a:link, a:visited link pseudo-classes
16. :focus, :hover, :active 事件 pseudo-classes
17. :target selector
18. UI-state pseudo-classes
19. Pseudo-Element Selectors
    
    
