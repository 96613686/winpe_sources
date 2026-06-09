# __security_check_cookie

- ea: `0x1400024e0`
- end: `0x1400024fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400018f8`
- `0x140001b84`
- `0x140001bf4`
- `0x140001cfc`
- `0x140002080`
- `0x1400023dc`
- `0x14000d330`
- `0x14000dff0`
- `0x14000f6e8`
- `0x14000f82c`
- `0x14000f944`
- `0x140012960`
- `0x140012ff0`
- `0x140013690`
- `0x140013ff0`
- `0x1400145d0`
- `0x1400147e0`
- `0x140015648`
- `0x140016340`
- `0x140016850`
- `0x1400168d0`
- `0x140016c00`
- `0x1400175d0`
- `0x140017950`
- `0x140018370`
- `0x14001a870`
- `0x14001b888`
- `0x14001bad0`
- `0x14001ca60`
- `0x14001d690`
- `0x14001e120`
- `0x14001ec00`
- `0x14001f3e8`
- `0x140020450`
- `0x140021084`
- `0x14002442c`
- `0x140024518`
- `0x140024610`
- `0x14002472c`
- `0x14002482c`

## callees

- `0x1400014a0`
- `0x1400024e0`

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
0x1400024e0  cmp     rcx, cs:__security_cookie
0x1400024e7  jnz     short ReportFailure
0x1400024e9  rol     rcx, 10h
0x1400024ed  test    cx, 0FFFFh
0x1400024f2  jnz     short RestoreRcx
0x1400024f4  retn
0x1400024f5  ror     rcx, 10h; StackCookie
0x1400024f9  jmp     __report_gsfailure
```
