# WPP_SF__guid_

- ea: `0x14000db14`
- end: `0x14000db4a`
- name: `WPP_SF__guid_`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033f0`
- `0x140005bf0`

## callees

- `0x14000f150`

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
0x14000db14  sub     rsp, 48h
0x14000db18  mov     rax, cs:pfnWppTraceMessage
0x14000db1f  mov     [rsp+48h+var_18], 0
0x14000db28  mov     [rsp+48h+var_20], 10h
0x14000db31  mov     [rsp+48h+var_28], r9
0x14000db36  movzx   r9d, dx
0x14000db3a  mov     edx, 2Bh ; '+'
0x14000db3f  call    _guard_dispatch_icall
0x14000db44  add     rsp, 48h
0x14000db48  retn
```
