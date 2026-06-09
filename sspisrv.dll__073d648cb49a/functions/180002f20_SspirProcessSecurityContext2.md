# SspirProcessSecurityContext2

- ea: `0x180002f20`
- end: `0x180003057`
- name: `SspirProcessSecurityContext2`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirProcessSecurityContext2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int128 *a6,
        __int128 *a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        _OWORD *a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22)
{
  SspiSrvCallBegin(a2);
  return SspirProcessSecurityContext(
           a1,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9,
           a10,
           a11,
           a12,
           a13,
           a14,
           a15,
           a16,
           a17,
           a18,
           a19,
           a20,
           a21,
           a22);
}

```

## disassembly

```asm
0x180002f20  mov     [rsp+arg_0], rbx
0x180002f25  mov     [rsp+arg_8], rsi
0x180002f2a  push    rdi
0x180002f2b  sub     rsp, 0B0h
0x180002f32  mov     rbx, rcx
0x180002f35  mov     rdi, r9
0x180002f38  mov     rcx, rdx
0x180002f3b  mov     rsi, r8
0x180002f3e  call    SspiSrvCallBegin
0x180002f43  mov     rax, [rsp+0B8h+arg_A8]
0x180002f4b  mov     r8, rdi
0x180002f4e  mov     [rsp+0B8h+var_18], rax
0x180002f56  mov     rdx, rsi
0x180002f59  mov     rax, [rsp+0B8h+arg_A0]
0x180002f61  mov     rcx, rbx
0x180002f64  mov     r9, [rsp+0B8h+arg_20]
0x180002f6c  mov     [rsp+0B8h+var_20], rax
0x180002f74  mov     rax, [rsp+0B8h+arg_98]
0x180002f7c  mov     [rsp+0B8h+var_28], rax
0x180002f84  mov     rax, [rsp+0B8h+arg_90]
0x180002f8c  mov     [rsp+0B8h+var_30], rax
0x180002f94  mov     rax, [rsp+0B8h+arg_88]
0x180002f9c  mov     [rsp+0B8h+var_38], rax
0x180002fa4  mov     rax, [rsp+0B8h+arg_80]
0x180002fac  mov     [rsp+0B8h+var_40], rax
0x180002fb1  mov     rax, [rsp+0B8h+arg_78]
0x180002fb9  mov     [rsp+0B8h+var_48], rax
0x180002fbe  mov     rax, [rsp+0B8h+arg_70]
0x180002fc6  mov     [rsp+0B8h+var_50], rax
0x180002fcb  mov     rax, [rsp+0B8h+arg_68]
0x180002fd3  mov     [rsp+0B8h+var_58], rax
0x180002fd8  mov     rax, [rsp+0B8h+arg_60]
0x180002fe0  mov     [rsp+0B8h+var_60], rax
0x180002fe5  mov     rax, [rsp+0B8h+arg_58]
0x180002fed  mov     [rsp+0B8h+var_68], rax
0x180002ff2  mov     rax, [rsp+0B8h+arg_50]
0x180002ffa  mov     [rsp+0B8h+var_70], rax
0x180002fff  mov     rax, [rsp+0B8h+arg_48]
0x180003007  mov     [rsp+0B8h+var_78], rax
0x18000300c  mov     eax, [rsp+0B8h+arg_40]
0x180003013  mov     [rsp+0B8h+var_80], eax
0x180003017  mov     eax, [rsp+0B8h+arg_38]
0x18000301e  mov     [rsp+0B8h+var_88], eax
0x180003022  mov     rax, [rsp+0B8h+arg_30]
0x18000302a  mov     [rsp+0B8h+var_90], rax
0x18000302f  mov     rax, [rsp+0B8h+arg_28]
0x180003037  mov     [rsp+0B8h+var_98], rax
0x18000303c  call    SspirProcessSecurityContext
0x180003041  lea     r11, [rsp+0B8h+var_8]
0x180003049  mov     rbx, [r11+10h]
0x18000304d  mov     rsi, [r11+18h]
0x180003051  mov     rsp, r11
0x180003054  pop     rdi
0x180003055  retn
```
