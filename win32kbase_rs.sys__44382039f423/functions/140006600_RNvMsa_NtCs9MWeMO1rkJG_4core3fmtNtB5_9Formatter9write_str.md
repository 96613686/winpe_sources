# _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter9write_str

- ea: `0x140006600`
- end: `0x140006615`
- name: `_RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter9write_str`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a750`
- `0x1400145e0`

## callees

- `0x140017a50`

## pseudocode

```c
__int64 __fastcall RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter9write_str(_QWORD *a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(a1[1] + 24LL))(*a1);
}

```

## disassembly

```asm
0x140006600  mov     r9, [rcx]
0x140006603  mov     rax, [rcx+8]
0x140006607  mov     rax, [rax+18h]
0x14000660b  mov     rcx, r9
0x14000660e  jmp     cs:__guard_dispatch_icall_fptr
```
