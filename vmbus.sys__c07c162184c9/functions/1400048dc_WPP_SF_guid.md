# WPP_SF__guid_

- ea: `0x1400048dc`
- end: `0x140004912`
- name: `WPP_SF__guid_`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010834`
- `0x140011608`
- `0x140028138`
- `0x14002dc40`

## callees

- `0x140017190`

## pseudocode

```c
__int64 __fastcall WPP_SF__guid_(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4)
{
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           16,
           0);
}

```

## disassembly

```asm
0x1400048dc  sub     rsp, 48h
0x1400048e0  mov     rax, cs:pfnWppTraceMessage
0x1400048e7  mov     [rsp+48h+var_18], 0
0x1400048f0  mov     [rsp+48h+var_20], 10h
0x1400048f9  mov     [rsp+48h+var_28], r9
0x1400048fe  movzx   r9d, dx
0x140004902  mov     edx, 2Bh ; '+'
0x140004907  call    _guard_dispatch_icall
0x14000490c  add     rsp, 48h
0x140004910  retn
```
