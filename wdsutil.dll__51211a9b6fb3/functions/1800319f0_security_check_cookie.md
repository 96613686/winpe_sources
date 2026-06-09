# __security_check_cookie

- ea: `0x1800319f0`
- end: `0x180031a0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022f0`
- `0x18000243c`
- `0x180004eb0`
- `0x180006020`
- `0x180008c78`
- `0x180008d5c`
- `0x180008e84`
- `0x1800099cc`
- `0x18000bef8`
- `0x18000d240`
- `0x18000db90`
- `0x18000e450`
- `0x1800121a0`
- `0x18001486c`
- `0x180015e34`
- `0x180016248`
- `0x180016478`
- `0x180016698`
- `0x180017f68`
- `0x1800180a4`
- `0x18001871c`
- `0x180019370`
- `0x1800198f0`
- `0x18001a9f8`
- `0x18001c548`
- `0x18001e334`
- `0x18001eb64`
- `0x18001ef34`
- `0x18001f284`
- `0x18001f970`
- `0x180020868`
- `0x1800208ec`
- `0x180020b40`
- `0x180021398`
- `0x180021efc`
- `0x1800221b8`
- `0x1800246f4`
- `0x18002483c`
- `0x180024a60`
- `0x180024ea8`
- `0x180025564`
- `0x18002591c`
- `0x1800263f0`
- `0x180026640`
- `0x180027f74`
- `0x180029670`
- `0x18002990c`
- `0x180029f10`
- `0x18002a1dc`
- `0x18002a4d8`

## callees

- `0x180001fe0`
- `0x1800319f0`

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
0x1800319f0  cmp     rcx, cs:__security_cookie
0x1800319f7  jnz     short ReportFailure
0x1800319f9  rol     rcx, 10h
0x1800319fd  test    cx, 0FFFFh
0x180031a02  jnz     short RestoreRcx
0x180031a04  retn
0x180031a05  ror     rcx, 10h
0x180031a09  jmp     __report_gsfailure
```
