# WinHvGetSparseGpaPagesAccessState

- ea: `0x140004e40`
- end: `0x140004eb9`
- name: `WinHvGetSparseGpaPagesAccessState`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvGetSparseGpaPagesAccessState(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        char *a4,
        char *a5,
        _QWORD *a6)
{
  _QWORD v7[3]; // [rsp+80h] [rbp-18h] BYREF

  v7[0] = a1;
  v7[1] = a2;
  return WinHvpSpecialListRepHypercall(202, a3, v7, 0x10u, 0, 0, a4, 8u, 0, 0, a5, 1u, 0, 0, a6);
}

```

## disassembly

```asm
0x140004e40  mov     r11, rsp
0x140004e43  sub     rsp, 98h
0x140004e4a  mov     rax, [rsp+98h+arg_28]
0x140004e52  mov     r10, r8
0x140004e55  mov     [r11-28h], rax
0x140004e59  lea     r8, [r11-18h]
0x140004e5d  mov     rax, [rsp+98h+arg_20]
0x140004e65  mov     [r11-18h], rcx
0x140004e69  xor     ecx, ecx
0x140004e6b  mov     [r11-30h], rcx
0x140004e6f  mov     [r11-38h], rcx
0x140004e73  mov     [rsp+98h+var_40], 1
0x140004e7b  mov     [r11-48h], rax
0x140004e7f  mov     [r11-50h], rcx
0x140004e83  mov     [r11-58h], rcx
0x140004e87  mov     [rsp+98h+var_60], 8
0x140004e8f  mov     [r11-68h], r9
0x140004e93  lea     r9d, [rcx+10h]
0x140004e97  mov     [r11-70h], rcx
0x140004e9b  mov     [r11-78h], rcx
0x140004e9f  mov     ecx, 0CAh
0x140004ea4  mov     [r11-10h], rdx
0x140004ea8  mov     rdx, r10
0x140004eab  call    WinHvpSpecialListRepHypercall
0x140004eb0  add     rsp, 98h
0x140004eb7  retn
```
