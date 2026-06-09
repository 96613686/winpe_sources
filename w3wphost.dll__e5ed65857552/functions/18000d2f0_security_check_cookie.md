# __security_check_cookie

- ea: `0x18000d2f0`
- end: `0x18000d30e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`
- `0x180003914`
- `0x180004100`
- `0x180004ee4`
- `0x18000561c`
- `0x1800062bc`
- `0x1800076cc`
- `0x180007b48`
- `0x180008514`
- `0x1800086a0`
- `0x180008818`
- `0x1800090e4`
- `0x180009a78`
- `0x18000a2a4`
- `0x18000b8e8`
- `0x18000c88c`
- `0x18000cc48`
- `0x18000d238`

## callees

- `0x180002820`
- `0x18000d2f0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x18000d2f0  cmp     rcx, cs:__security_cookie
0x18000d2f7  jnz     short ReportFailure
0x18000d2f9  rol     rcx, 10h
0x18000d2fd  test    cx, 0FFFFh
0x18000d302  jnz     short RestoreRcx
0x18000d304  retn
0x18000d305  ror     rcx, 10h
0x18000d309  jmp     __report_gsfailure
```
