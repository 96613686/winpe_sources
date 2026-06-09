# SspirGetUserName2

- ea: `0x180002c40`
- end: `0x180002c8c`
- name: `SspirGetUserName2`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001400`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirGetUserName2(__int64 a1, __int64 a2, __int128 *a3, unsigned int a4, __int64 a5, _DWORD *a6)
{
  SspiSrvCallBegin(a2);
  return SspirGetUserName(a1, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180002c40  mov     [rsp+arg_0], rbx
0x180002c45  mov     [rsp+arg_8], rsi
0x180002c4a  push    rdi
0x180002c4b  sub     rsp, 30h
0x180002c4f  mov     rbx, rcx
0x180002c52  mov     edi, r9d
0x180002c55  mov     rcx, rdx
0x180002c58  mov     rsi, r8
0x180002c5b  call    SspiSrvCallBegin
0x180002c60  mov     rax, [rsp+38h+arg_28]
0x180002c65  mov     r8d, edi
0x180002c68  mov     r9, [rsp+38h+arg_20]
0x180002c6d  mov     rdx, rsi
0x180002c70  mov     rcx, rbx
0x180002c73  mov     [rsp+38h+arg_20], rax
0x180002c78  mov     rbx, [rsp+38h+arg_0]
0x180002c7d  mov     rsi, [rsp+38h+arg_8]
0x180002c82  add     rsp, 30h
0x180002c86  pop     rdi
0x180002c87  jmp     SspirGetUserName
```
