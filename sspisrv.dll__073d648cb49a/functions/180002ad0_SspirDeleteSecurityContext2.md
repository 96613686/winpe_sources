# SspirDeleteSecurityContext2

- ea: `0x180002ad0`
- end: `0x180002b12`
- name: `SspirDeleteSecurityContext2`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001470`
- `0x180002714`

## pseudocode

```c
__int64 __fastcall SspirDeleteSecurityContext2(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4)
{
  SspiSrvCallBegin(a2);
  return SspirDeleteSecurityContext(a1, a3, a4);
}

```

## disassembly

```asm
0x180002ad0  mov     [rsp+arg_0], rbx
0x180002ad5  mov     [rsp+arg_8], rsi
0x180002ada  push    rdi
0x180002adb  sub     rsp, 20h
0x180002adf  mov     rbx, rcx
0x180002ae2  mov     rdi, r9
0x180002ae5  mov     rcx, rdx
0x180002ae8  mov     rsi, r8
0x180002aeb  call    SspiSrvCallBegin
0x180002af0  mov     r9, [rsp+28h+arg_20]
0x180002af5  mov     r8, rdi
0x180002af8  mov     rdx, rsi
0x180002afb  mov     rcx, rbx
0x180002afe  mov     rbx, [rsp+28h+arg_0]
0x180002b03  mov     rsi, [rsp+28h+arg_8]
0x180002b08  add     rsp, 20h
0x180002b0c  pop     rdi
0x180002b0d  jmp     SspirDeleteSecurityContext
```
