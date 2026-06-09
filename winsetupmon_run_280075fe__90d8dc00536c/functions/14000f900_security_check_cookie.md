# __security_check_cookie

- ea: `0x14000f900`
- end: `0x14000f91e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001404`
- `0x140002f00`
- `0x140003218`
- `0x140003944`
- `0x140003f48`
- `0x14000816c`
- `0x14000d9c4`
- `0x14000dd90`
- `0x14000df1c`
- `0x14000e778`
- `0x14000eb68`
- `0x14000f34c`
- `0x14000f80c`
- `0x14001e5cc`
- `0x14001e808`
- `0x14001f130`
- `0x14001f288`
- `0x14001f6c0`
- `0x14001fab0`
- `0x140020eb8`
- `0x140021a2c`
- `0x140021b30`
- `0x140022078`

## callees

- `0x140001200`
- `0x14000f900`

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
0x14000f900  cmp     rcx, cs:__security_cookie
0x14000f907  jnz     short ReportFailure
0x14000f909  rol     rcx, 10h
0x14000f90d  test    cx, 0FFFFh
0x14000f912  jnz     short RestoreRcx
0x14000f914  retn
0x14000f915  ror     rcx, 10h; StackCookie
0x14000f919  jmp     __report_gsfailure
```
