# WinHvCheckSparseGpaPageVtlAccess

- ea: `0x140004cc0`
- end: `0x140004d50`
- name: `WinHvCheckSparseGpaPageVtlAccess`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvCheckSparseGpaPageVtlAccess(
        __int64 a1,
        char a2,
        char a3,
        unsigned __int64 a4,
        char *a5,
        char *a6,
        _QWORD *a7)
{
  __int128 v8; // [rsp+80h] [rbp-18h] BYREF

  v8 = 0;
  BYTE8(v8) = a2 & 0xF | 0x10;
  *(_QWORD *)&v8 = a1;
  BYTE9(v8) = a3;
  return WinHvpSpecialListRepHypercall(212, a4, &v8, 0x10u, 0, 0, a5, 8u, 0, 0, a6, 8u, 0, 0, a7);
}

```

## disassembly

```asm
0x140004cc0  mov     r11, rsp
0x140004cc3  sub     rsp, 98h
0x140004cca  mov     rax, [rsp+98h+arg_30]
0x140004cd2  and     dl, 0Fh
0x140004cd5  mov     [r11-28h], rax
0x140004cd9  mov     r10, r9
0x140004cdc  mov     rax, [rsp+98h+arg_28]
0x140004ce4  mov     r9d, 10h
0x140004cea  or      dl, r9b
0x140004ced  xorps   xmm0, xmm0
0x140004cf0  movups  xmmword ptr [r11-18h], xmm0
0x140004cf5  mov     [r11-10h], dl
0x140004cf9  xor     edx, edx
0x140004cfb  mov     [r11-30h], rdx
0x140004cff  mov     [r11-38h], rdx
0x140004d03  mov     [r11-18h], rcx
0x140004d07  lea     ecx, [rdx+8]
0x140004d0a  mov     [r11-0Fh], r8b
0x140004d0e  mov     [rsp+98h+var_40], ecx
0x140004d12  lea     r8, [r11-18h]
0x140004d16  mov     [r11-48h], rax
0x140004d1a  mov     rax, [rsp+98h+arg_20]
0x140004d22  mov     [r11-50h], rdx
0x140004d26  mov     [r11-58h], rdx
0x140004d2a  mov     [rsp+98h+var_60], ecx
0x140004d2e  mov     ecx, 0D4h
0x140004d33  mov     [r11-68h], rax
0x140004d37  mov     [r11-70h], rdx
0x140004d3b  mov     [r11-78h], rdx
0x140004d3f  mov     rdx, r10
0x140004d42  call    WinHvpSpecialListRepHypercall
0x140004d47  add     rsp, 98h
0x140004d4e  retn
```
