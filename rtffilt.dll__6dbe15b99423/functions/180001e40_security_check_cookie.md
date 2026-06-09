# __security_check_cookie

- ea: `0x180001e40`
- end: `0x180001e5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180003648`
- `0x1800038f4`
- `0x180004b78`
- `0x180004f48`
- `0x180005340`
- `0x18000555c`
- `0x1800057f0`
- `0x180005ae4`
- `0x180006b04`
- `0x180006f24`
- `0x180008314`
- `0x180008420`
- `0x180008e2c`
- `0x18000920c`
- `0x180009490`
- `0x180009894`
- `0x180009e20`
- `0x18000a120`
- `0x18000b7e8`
- `0x18000ba74`
- `0x18000ca70`
- `0x18000cb98`
- `0x18000cff4`
- `0x18000d24c`
- `0x18000e034`
- `0x18000e748`
- `0x18001066c`
- `0x1800108a4`
- `0x180011384`
- `0x180011420`
- `0x18001153c`
- `0x180014948`
- `0x1800156e4`
- `0x180015820`
- `0x180015a68`
- `0x180015e20`
- `0x18001620c`
- `0x1800169b8`
- `0x180017524`
- `0x18001779c`
- `0x1800189d8`
- `0x180018c9c`
- `0x180019770`

## callees

- `0x180001e40`
- `0x180001e70`

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
0x180001e40  cmp     rcx, cs:__security_cookie
0x180001e47  jnz     short ReportFailure
0x180001e49  rol     rcx, 10h
0x180001e4d  test    cx, 0FFFFh
0x180001e52  jnz     short RestoreRcx
0x180001e54  retn
0x180001e55  ror     rcx, 10h; StackCookie
0x180001e59  jmp     __report_gsfailure
```
