# __security_check_cookie

- ea: `0x180012880`
- end: `0x18001289e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001180`
- `0x180001338`
- `0x1800014a0`
- `0x180002ef0`
- `0x180006260`
- `0x1800076b0`
- `0x180009820`
- `0x18000d32c`
- `0x18000d850`
- `0x18000e180`
- `0x18000e8f0`
- `0x18000e9fc`
- `0x18000ef40`
- `0x18000f030`
- `0x18000ff20`
- `0x1800109f8`
- `0x180013164`
- `0x180013f98`
- `0x180014088`
- `0x180014554`
- `0x1800146bc`
- `0x180014850`
- `0x180014cd4`
- `0x180014fec`
- `0x180016754`
- `0x18001704c`
- `0x180018298`
- `0x180018d38`
- `0x1800195dc`
- `0x18001bf40`
- `0x18001c8e0`
- `0x18001d5e8`
- `0x18001e360`
- `0x18001e4b0`
- `0x1800206d0`
- `0x180024000`
- `0x180024328`
- `0x1800245d0`
- `0x18002494c`
- `0x180024b10`
- `0x180024d4c`
- `0x180026020`
- `0x180026ad0`
- `0x180027678`
- `0x180027e2c`
- `0x180028190`
- `0x180028ff0`
- `0x1800298f4`
- `0x180029c98`

## callees

- `0x180012880`
- `0x180012cc0`

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
0x180012880  cmp     rcx, cs:__security_cookie
0x180012887  jnz     short ReportFailure
0x180012889  rol     rcx, 10h
0x18001288d  test    cx, 0FFFFh
0x180012892  jnz     short RestoreRcx
0x180012894  retn
0x180012895  ror     rcx, 10h; StackCookie
0x180012899  jmp     __report_gsfailure
```
