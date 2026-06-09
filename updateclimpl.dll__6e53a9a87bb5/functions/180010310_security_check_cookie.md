# __security_check_cookie

- ea: `0x180010310`
- end: `0x18001032e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000109c`
- `0x180001350`
- `0x18000140c`
- `0x180001704`
- `0x180001a7c`
- `0x180002214`
- `0x180002304`
- `0x1800026f8`
- `0x1800027e8`
- `0x1800029dc`
- `0x180002acc`
- `0x180002ecc`
- `0x180003020`
- `0x180003bd0`
- `0x1800040e0`
- `0x180004158`
- `0x180004558`
- `0x1800046b8`
- `0x180004724`
- `0x180004b54`
- `0x180005560`
- `0x180005f10`
- `0x180006084`
- `0x180006a30`
- `0x180007274`
- `0x18000739c`
- `0x180007654`
- `0x180007a74`
- `0x180007dec`
- `0x18000820c`
- `0x180008390`
- `0x180008408`
- `0x1800084bc`
- `0x18000884c`
- `0x18000892c`
- `0x180008e40`
- `0x180009224`
- `0x18000960c`
- `0x180009c54`
- `0x18000a6c0`
- `0x18000a760`
- `0x18000a7f0`
- `0x18000abf0`
- `0x18000acf4`
- `0x18000af3c`
- `0x18000b828`
- `0x18000b88c`
- `0x18000bc80`
- `0x18000bdfc`
- `0x18000be54`

## callees

- `0x180010310`
- `0x180010af0`

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
0x180010310  cmp     rcx, cs:__security_cookie
0x180010317  jnz     short ReportFailure
0x180010319  rol     rcx, 10h
0x18001031d  test    cx, 0FFFFh
0x180010322  jnz     short RestoreRcx
0x180010324  retn
0x180010325  ror     rcx, 10h
0x180010329  jmp     __report_gsfailure
```
