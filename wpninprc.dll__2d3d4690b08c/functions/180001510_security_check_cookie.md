# __security_check_cookie

- ea: `0x180001510`
- end: `0x18000152e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002554`
- `0x180002810`
- `0x180003560`
- `0x180003c30`
- `0x180003ecc`
- `0x180004144`
- `0x1800044e8`
- `0x1800055c0`
- `0x180005b7c`
- `0x180006598`

## callees

- `0x180001510`
- `0x180001af0`

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
0x180001510  cmp     rcx, cs:__security_cookie
0x180001517  jnz     short ReportFailure
0x180001519  rol     rcx, 10h
0x18000151d  test    cx, 0FFFFh
0x180001522  jnz     short RestoreRcx
0x180001524  retn
0x180001525  ror     rcx, 10h; StackCookie
0x180001529  jmp     __report_gsfailure
```
