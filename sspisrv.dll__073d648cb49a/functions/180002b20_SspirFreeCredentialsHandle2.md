# SspirFreeCredentialsHandle2

- ea: `0x180002b20`
- end: `0x180002b62`
- name: `SspirFreeCredentialsHandle2`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ac0`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirFreeCredentialsHandle2(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4)
{
  SspiSrvCallBegin(a2);
  return SspirFreeCredentialsHandle(a1, a3, a4);
}

```

## disassembly

```asm
0x180002b20  mov     [rsp+arg_0], rbx
0x180002b25  mov     [rsp+arg_8], rsi
0x180002b2a  push    rdi
0x180002b2b  sub     rsp, 20h
0x180002b2f  mov     rbx, rcx
0x180002b32  mov     rdi, r9
0x180002b35  mov     rcx, rdx
0x180002b38  mov     rsi, r8
0x180002b3b  call    SspiSrvCallBegin
0x180002b40  mov     r9, [rsp+28h+arg_20]
0x180002b45  mov     r8, rdi
0x180002b48  mov     rdx, rsi
0x180002b4b  mov     rcx, rbx
0x180002b4e  mov     rbx, [rsp+28h+arg_0]
0x180002b53  mov     rsi, [rsp+28h+arg_8]
0x180002b58  add     rsp, 20h
0x180002b5c  pop     rdi
0x180002b5d  jmp     SspirFreeCredentialsHandle
```
