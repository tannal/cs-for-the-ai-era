# 第一课：指令、状态、编程（从 `foo.c` 到汇编指令）

📺 **成片视频下载（v002 克隆声线正式版）**：[GitHub Release `ep01-v002`](https://github.com/tannal/cs-for-the-ai-era/releases/tag/ep01-v002)

## 本课核心模型

1. **指令序列（Instruction Stream）**：剥掉框架与语法糖，程序本质是一条接一条排好队的指令序列（`指令1 → 指令2 → 指令3 → 指令4 → ...`）。
2. **状态机（State Machine）**：
   - **状态（State）**：此时此刻寄存器与内存里所有的 `0` 和 `1`。
   - **指令（Instruction）**：推动状态从 `S(t)` 精确转移到 `S(t+1)` 的原子操作。
   - **编程（Programming）**：设计这条状态变迁路径。

## 代码与汇编对照

[`foo.c`](./foo.c)：
```c
int foo() {
  return 42;
}

int main() {
  return foo();
}
```

典型 x86 汇编意象：
```assembly
foo:
  mov  eax, 42    ; 将 42 写入返回值寄存器 eax
  ret             ; 返回调用处

main:
  call foo        ; 跳转到 foo 执行
  ret             ; 将 eax 中的 42 作为退出码返回

; 常见寄存器操作
mov eax, ebx
add eax, ecx
```

## 经典硬核延伸课程推荐
- **台湾交通大学 · 曹效忠老师**：《嵌入式系统实验课》《操作系统设计与实现》
- **犹他大学 (University of Utah)**：《嵌入式系统设计与实现》

## 完整分镜台词
详见 [`shots.json`](./shots.json)。
