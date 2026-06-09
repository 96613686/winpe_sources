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

- `0x18000271c`
- `0x180003394`
- `0x180003698`
- `0x1800037e8`
- `0x180003978`
- `0x180003b5c`
- `0x18000430c`
- `0x1800043ec`
- `0x180004714`
- `0x180004d60`

## callees

- `0x180001510`
- `0x180001540`

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
