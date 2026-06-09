# __security_check_cookie

- ea: `0x18003c560`
- end: `0x18003c57e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003540`
- `0x180003950`
- `0x180003c18`
- `0x1800041c8`
- `0x180004288`
- `0x1800052a0`
- `0x180005b30`
- `0x18000f5a0`
- `0x180018f80`
- `0x180019210`
- `0x180019940`
- `0x18001dfa0`
- `0x18001e220`
- `0x18001e840`
- `0x18001ecb0`
- `0x18001f2a0`
- `0x18001f8cc`
- `0x18001fa70`
- `0x180020b70`
- `0x180021988`
- `0x18002214c`
- `0x180022984`
- `0x180023134`
- `0x1800236b4`
- `0x180037d40`
- `0x180038d30`
- `0x1800396c4`
- `0x18003b0e8`
- `0x18003b94c`
- `0x18003bd80`
- `0x18003c490`

## callees

- `0x180001e20`
- `0x18003c560`

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
0x18003c560  cmp     rcx, cs:__security_cookie
0x18003c567  jnz     short ReportFailure
0x18003c569  rol     rcx, 10h
0x18003c56d  test    cx, 0FFFFh
0x18003c572  jnz     short RestoreRcx
0x18003c574  retn
0x18003c575  ror     rcx, 10h
0x18003c579  jmp     __report_gsfailure
```
