# __security_check_cookie

- ea: `0x180001400`
- end: `0x18000141e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002110`
- `0x180002af0`
- `0x180002f08`
- `0x180006868`
- `0x180007938`
- `0x180007ac8`
- `0x180007d5c`
- `0x1800080bc`
- `0x180009070`
- `0x180009d2c`
- `0x18000ba40`

## callees

- `0x180001400`
- `0x180001430`

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
0x180001400  cmp     rcx, cs:__security_cookie
0x180001407  jnz     short ReportFailure
0x180001409  rol     rcx, 10h
0x18000140d  test    cx, 0FFFFh
0x180001412  jnz     short RestoreRcx
0x180001414  retn
0x180001415  ror     rcx, 10h; StackCookie
0x180001419  jmp     __report_gsfailure
```
