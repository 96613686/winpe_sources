# SspirCallRpc2

- ea: `0x180002a70`
- end: `0x180002ac7`
- name: `SspirCallRpc2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800012b0`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirCallRpc2(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const void *a4,
        _DWORD *a5,
        __int16 **a6,
        __int64 a7)
{
  SspiSrvCallBegin(a2);
  return SspirCallRpc(a1, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180002a70  mov     [rsp+arg_0], rbx
0x180002a75  mov     [rsp+arg_8], rsi
0x180002a7a  push    rdi
0x180002a7b  sub     rsp, 30h
0x180002a7f  mov     rbx, rcx
0x180002a82  mov     rdi, r9
0x180002a85  mov     rcx, rdx
0x180002a88  mov     esi, r8d
0x180002a8b  call    SspiSrvCallBegin
0x180002a90  mov     rax, [rsp+38h+arg_30]
0x180002a95  mov     r8, rdi
0x180002a98  mov     r9, [rsp+38h+arg_20]
0x180002a9d  mov     edx, esi
0x180002a9f  mov     [rsp+38h+var_10], rax
0x180002aa4  mov     rcx, rbx
0x180002aa7  mov     rax, [rsp+38h+arg_28]
0x180002aac  mov     [rsp+38h+var_18], rax
0x180002ab1  call    SspirCallRpc
0x180002ab6  mov     rbx, [rsp+38h+arg_0]
0x180002abb  mov     rsi, [rsp+38h+arg_8]
0x180002ac0  add     rsp, 30h
0x180002ac4  pop     rdi
0x180002ac5  retn
```
