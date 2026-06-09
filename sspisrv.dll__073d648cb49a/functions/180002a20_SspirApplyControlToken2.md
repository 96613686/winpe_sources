# SspirApplyControlToken2

- ea: `0x180002a20`
- end: `0x180002a62`
- name: `SspirApplyControlToken2`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c10`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirApplyControlToken2(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4, __int64 a5)
{
  SspiSrvCallBegin(a2);
  return SspirApplyControlToken(a1, a3, a4, a5);
}

```

## disassembly

```asm
0x180002a20  mov     [rsp+arg_0], rbx
0x180002a25  mov     [rsp+arg_8], rsi
0x180002a2a  push    rdi
0x180002a2b  sub     rsp, 20h
0x180002a2f  mov     rbx, rcx
0x180002a32  mov     rdi, r9
0x180002a35  mov     rcx, rdx
0x180002a38  mov     rsi, r8
0x180002a3b  call    SspiSrvCallBegin
0x180002a40  mov     r9, [rsp+28h+arg_20]
0x180002a45  mov     r8, rdi
0x180002a48  mov     rdx, rsi
0x180002a4b  mov     rcx, rbx
0x180002a4e  mov     rbx, [rsp+28h+arg_0]
0x180002a53  mov     rsi, [rsp+28h+arg_8]
0x180002a58  add     rsp, 20h
0x180002a5c  pop     rdi
0x180002a5d  jmp     SspirApplyControlToken
```
