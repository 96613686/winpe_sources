# __security_check_cookie

- ea: `0x18000e640`
- end: `0x18000e65e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `70`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001044`
- `0x18000116c`
- `0x1800012a4`
- `0x180001558`
- `0x1800015e8`
- `0x18000188c`
- `0x180001b84`
- `0x180001c7c`
- `0x180001e3c`
- `0x180001ee8`
- `0x180004b30`
- `0x180005100`
- `0x180005d48`
- `0x1800064d0`
- `0x1800067b8`
- `0x180006e18`
- `0x180007ca0`
- `0x180008160`
- `0x180008dd8`
- `0x1800098a0`
- `0x180009abc`
- `0x180009d40`
- `0x180009f74`
- `0x18000ab88`
- `0x18000c8c0`
- `0x18000d108`
- `0x18000de10`
- `0x1800100d4`
- `0x1800103a0`
- `0x180010ab0`
- `0x180010fa4`
- `0x180011264`
- `0x1800114e8`
- `0x180011730`
- `0x1800124cc`
- `0x180013424`
- `0x18001381c`
- `0x1800138dc`
- `0x180014c70`
- `0x180014e30`
- `0x180016084`
- `0x180017490`
- `0x180017ca0`
- `0x180018378`
- `0x18001960c`
- `0x1800197f0`
- `0x180019a7c`
- `0x180019b54`
- `0x18001a224`
- `0x18001a508`

## callees

- `0x18000e640`
- `0x18000ec00`

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
0x18000e640  cmp     rcx, cs:__security_cookie
0x18000e647  jnz     short ReportFailure
0x18000e649  rol     rcx, 10h
0x18000e64d  test    cx, 0FFFFh
0x18000e652  jnz     short RestoreRcx
0x18000e654  retn
0x18000e655  ror     rcx, 10h; StackCookie
0x18000e659  jmp     __report_gsfailure
```
