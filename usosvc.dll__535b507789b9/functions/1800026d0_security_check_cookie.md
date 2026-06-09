# __security_check_cookie

- ea: `0x1800026d0`
- end: `0x1800026ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `35`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180001e20`
- `0x180002b44`
- `0x180003744`
- `0x1800039d8`
- `0x180003f78`
- `0x180004348`
- `0x180004964`
- `0x180004ce0`
- `0x18000648c`
- `0x180006970`
- `0x180006b80`
- `0x1800081ec`
- `0x18000837c`
- `0x180008708`
- `0x1800089c0`
- `0x180009364`
- `0x180009540`
- `0x1800096cc`
- `0x1800097fc`
- `0x180009890`
- `0x180009a7c`
- `0x180009bf0`
- `0x180009e38`
- `0x18000a498`
- `0x18000ad78`
- `0x18000b35c`
- `0x18000b8f0`
- `0x18000c0b0`
- `0x18000c6c4`
- `0x18000cf7c`
- `0x18000e09c`

## callees

- `0x1800026d0`
- `0x180002d70`

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
0x1800026d0  cmp     rcx, cs:__security_cookie
0x1800026d7  jnz     short ReportFailure
0x1800026d9  rol     rcx, 10h
0x1800026dd  test    cx, 0FFFFh
0x1800026e2  jnz     short RestoreRcx
0x1800026e4  retn
0x1800026e5  ror     rcx, 10h; StackCookie
0x1800026e9  jmp     __report_gsfailure
```
