# SspirAcquireCredentialsHandle2

- ea: `0x180002950`
- end: `0x180002a17`
- name: `SspirAcquireCredentialsHandle2`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001540`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirAcquireCredentialsHandle2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int a11,
        _OWORD *a12,
        __int64 a13)
{
  SspiSrvCallBegin(a2);
  return SspirAcquireCredentialsHandle(a1, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13);
}

```

## disassembly

```asm
0x180002950  mov     [rsp+arg_0], rbx
0x180002955  mov     [rsp+arg_8], rsi
0x18000295a  push    rdi
0x18000295b  sub     rsp, 70h
0x18000295f  mov     rbx, rcx
0x180002962  mov     rdi, r9
0x180002965  mov     rcx, rdx
0x180002968  mov     rsi, r8
0x18000296b  call    SspiSrvCallBegin
0x180002970  mov     rax, [rsp+78h+arg_70]
0x180002978  mov     r8, rdi
0x18000297b  mov     r9, [rsp+78h+arg_20]
0x180002983  mov     rdx, rsi
0x180002986  mov     [rsp+78h+var_10], rax
0x18000298b  mov     rcx, rbx
0x18000298e  mov     rax, [rsp+78h+arg_68]
0x180002996  mov     [rsp+78h+var_18], rax
0x18000299b  mov     rax, [rsp+78h+arg_60]
0x1800029a3  mov     [rsp+78h+var_20], rax
0x1800029a8  mov     rax, [rsp+78h+arg_58]
0x1800029b0  mov     [rsp+78h+var_28], rax
0x1800029b5  mov     eax, [rsp+78h+arg_50]
0x1800029bc  mov     [rsp+78h+var_30], eax
0x1800029c0  mov     rax, [rsp+78h+arg_48]
0x1800029c8  mov     [rsp+78h+var_38], rax
0x1800029cd  mov     rax, [rsp+78h+arg_40]
0x1800029d5  mov     [rsp+78h+var_40], rax
0x1800029da  mov     rax, [rsp+78h+arg_38]
0x1800029e2  mov     [rsp+78h+var_48], rax
0x1800029e7  mov     rax, [rsp+78h+arg_30]
0x1800029ef  mov     [rsp+78h+var_50], rax
0x1800029f4  mov     eax, [rsp+78h+arg_28]
0x1800029fb  mov     [rsp+78h+var_58], eax
0x1800029ff  call    SspirAcquireCredentialsHandle
0x180002a04  lea     r11, [rsp+78h+var_8]
0x180002a09  mov     rbx, [r11+10h]
0x180002a0d  mov     rsi, [r11+18h]
0x180002a11  mov     rsp, r11
0x180002a14  pop     rdi
0x180002a15  retn
```
