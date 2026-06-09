# __security_check_cookie

- ea: `0x18001be10`
- end: `0x18001be2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cfc`
- `0x180002570`
- `0x180002a30`
- `0x18000f270`
- `0x18000f860`
- `0x180012c10`
- `0x180016890`
- `0x180018b48`
- `0x1800196cc`
- `0x18001b044`
- `0x18001d0a0`
- `0x18001d194`
- `0x18001dd78`
- `0x18001defc`
- `0x18001e198`
- `0x18001e9a4`
- `0x18001ed58`
- `0x18001f340`
- `0x180020508`
- `0x180020b60`
- `0x180021ec0`
- `0x180022910`
- `0x180022b18`
- `0x180022d44`
- `0x180023b74`
- `0x180023f30`
- `0x1800249b0`
- `0x180029018`
- `0x18002e998`
- `0x18002eb98`
- `0x18002ed6c`

## callees

- `0x18001be10`
- `0x18001be40`

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
0x18001be10  cmp     rcx, cs:__security_cookie
0x18001be17  jnz     short ReportFailure
0x18001be19  rol     rcx, 10h
0x18001be1d  test    cx, 0FFFFh
0x18001be22  jnz     short RestoreRcx
0x18001be24  retn
0x18001be25  ror     rcx, 10h; StackCookie
0x18001be29  jmp     __report_gsfailure
```
