# __security_check_cookie

- ea: `0x180014270`
- end: `0x18001428e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e2c`
- `0x180001f7c`
- `0x180002e80`
- `0x180002fd8`
- `0x180003c90`
- `0x180004fd0`
- `0x180005410`
- `0x180005e28`
- `0x180006380`
- `0x1800064e0`
- `0x180007ca0`
- `0x180007ecc`
- `0x180008600`
- `0x180008b40`
- `0x180008d70`
- `0x1800091b0`
- `0x1800099ac`
- `0x18000a1b0`
- `0x18000a860`
- `0x18000cf50`
- `0x18000d2b0`
- `0x18000e2c4`
- `0x18000f500`
- `0x18000f68c`
- `0x18000f804`
- `0x18001008c`
- `0x180010440`
- `0x1800109ec`
- `0x1800111c8`
- `0x180011538`
- `0x18001167c`
- `0x180011800`
- `0x180011b0c`
- `0x1800124b4`
- `0x1800125c4`
- `0x1800127d8`
- `0x1800128e8`
- `0x180012af8`
- `0x180012cac`
- `0x180013070`

## callees

- `0x180001790`
- `0x180014270`

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
0x180014270  cmp     rcx, cs:__security_cookie
0x180014277  jnz     short ReportFailure
0x180014279  rol     rcx, 10h
0x18001427d  test    cx, 0FFFFh
0x180014282  jnz     short RestoreRcx
0x180014284  retn
0x180014285  ror     rcx, 10h
0x180014289  jmp     __report_gsfailure
```
