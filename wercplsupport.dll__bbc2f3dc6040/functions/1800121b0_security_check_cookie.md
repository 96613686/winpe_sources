# __security_check_cookie

- ea: `0x1800121b0`
- end: `0x1800121ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x180001178`
- `0x180001270`
- `0x180002344`
- `0x180002ad0`
- `0x180002c98`
- `0x180003ab0`
- `0x1800045cc`
- `0x180004970`
- `0x180004d28`
- `0x18000531c`
- `0x180005664`
- `0x18000576c`
- `0x180005e04`
- `0x180007c9c`
- `0x180008b5c`
- `0x180008df4`
- `0x180009b78`
- `0x180009f58`
- `0x18000a410`
- `0x18000b2ac`
- `0x18000c760`
- `0x18000c9e0`
- `0x18000d28c`
- `0x18000e098`
- `0x18000e520`
- `0x180011c1c`
- `0x1800120f4`

## callees

- `0x180001eb0`
- `0x1800121b0`

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
0x1800121b0  cmp     rcx, cs:__security_cookie
0x1800121b7  jnz     short ReportFailure
0x1800121b9  rol     rcx, 10h
0x1800121bd  test    cx, 0FFFFh
0x1800121c2  jnz     short RestoreRcx
0x1800121c4  retn
0x1800121c5  ror     rcx, 10h
0x1800121c9  jmp     __report_gsfailure
```
