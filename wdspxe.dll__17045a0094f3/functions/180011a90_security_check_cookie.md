# __security_check_cookie

- ea: `0x180011a90`
- end: `0x180011aae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002a70`
- `0x180002f00`
- `0x180003384`
- `0x180004030`
- `0x180004660`
- `0x180005aa4`
- `0x180006430`
- `0x180006770`
- `0x180008250`
- `0x180008570`
- `0x1800086b0`
- `0x180009680`
- `0x180009930`
- `0x18000a204`
- `0x18000a5fc`
- `0x18000aa10`
- `0x18000b8f0`
- `0x18000bc7c`
- `0x18000bdc0`
- `0x18000cef0`
- `0x18000d3c4`
- `0x18000dcdc`
- `0x18000e08c`
- `0x18000e314`
- `0x18000f224`
- `0x180010120`
- `0x180010d98`
- `0x1800119e8`

## callees

- `0x180001b60`
- `0x180011a90`

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
0x180011a90  cmp     rcx, cs:__security_cookie
0x180011a97  jnz     short ReportFailure
0x180011a99  rol     rcx, 10h
0x180011a9d  test    cx, 0FFFFh
0x180011aa2  jnz     short RestoreRcx
0x180011aa4  retn
0x180011aa5  ror     rcx, 10h
0x180011aa9  jmp     __report_gsfailure
```
