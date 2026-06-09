# SspirLogonUser2

- ea: `0x180002d20`
- end: `0x180002e07`
- name: `SspirLogonUser2`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800016d0`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirLogonUser2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        unsigned int *a9,
        int a10,
        __int64 a11,
        __int64 a12,
        _QWORD *a13,
        __int64 a14,
        __int64 a15,
        _QWORD *a16,
        _OWORD *a17)
{
  SspiSrvCallBegin(a2);
  return SspirLogonUser(a1, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15, a16, a17);
}

```

## disassembly

```asm
0x180002d20  mov     [rsp+arg_0], rbx
0x180002d25  mov     [rsp+arg_8], rsi
0x180002d2a  push    rdi
0x180002d2b  sub     rsp, 80h
0x180002d32  mov     rbx, rcx
0x180002d35  mov     rdi, r9
0x180002d38  mov     rcx, rdx
0x180002d3b  mov     rsi, r8
0x180002d3e  call    SspiSrvCallBegin
0x180002d43  mov     rax, [rsp+88h+arg_80]
0x180002d4b  mov     r8, rdi
0x180002d4e  mov     r9d, [rsp+88h+arg_20]
0x180002d56  mov     rdx, rsi
0x180002d59  mov     [rsp+88h+var_10], rax
0x180002d5e  mov     rcx, rbx
0x180002d61  mov     rax, [rsp+88h+arg_78]
0x180002d69  mov     [rsp+88h+var_18], rax
0x180002d6e  mov     rax, [rsp+88h+arg_70]
0x180002d76  mov     [rsp+88h+var_20], rax
0x180002d7b  mov     rax, [rsp+88h+arg_68]
0x180002d83  mov     [rsp+88h+var_28], rax
0x180002d88  mov     rax, [rsp+88h+arg_60]
0x180002d90  mov     [rsp+88h+var_30], rax
0x180002d95  mov     rax, [rsp+88h+arg_58]
0x180002d9d  mov     [rsp+88h+var_38], rax
0x180002da2  mov     rax, [rsp+88h+arg_50]
0x180002daa  mov     [rsp+88h+var_40], rax
0x180002daf  mov     eax, [rsp+88h+arg_48]
0x180002db6  mov     [rsp+88h+var_48], eax
0x180002dba  mov     rax, [rsp+88h+arg_40]
0x180002dc2  mov     [rsp+88h+var_50], rax
0x180002dc7  mov     rax, [rsp+88h+arg_38]
0x180002dcf  mov     [rsp+88h+var_58], rax
0x180002dd4  mov     rax, [rsp+88h+arg_30]
0x180002ddc  mov     [rsp+88h+var_60], rax
0x180002de1  mov     eax, [rsp+88h+arg_28]
0x180002de8  mov     [rsp+88h+var_68], eax
0x180002dec  call    SspirLogonUser
0x180002df1  lea     r11, [rsp+88h+var_8]
0x180002df9  mov     rbx, [r11+10h]
0x180002dfd  mov     rsi, [r11+18h]
0x180002e01  mov     rsp, r11
0x180002e04  pop     rdi
0x180002e05  retn
```
