# __security_check_cookie

- ea: `0x140008d20`
- end: `0x140008d3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400084d0`
- `0x140008b7c`
- `0x1400111bc`
- `0x140011730`
- `0x1400117e4`
- `0x140012c78`
- `0x1400131cc`
- `0x140013c40`
- `0x140013e70`
- `0x140014040`
- `0x140014420`
- `0x140015570`
- `0x1400161ec`
- `0x1400169e0`

## callees

- `0x140004ca0`
- `0x140008d20`

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
0x140008d20  cmp     rcx, cs:__security_cookie
0x140008d27  jnz     short ReportFailure
0x140008d29  rol     rcx, 10h
0x140008d2d  test    cx, 0FFFFh
0x140008d32  jnz     short RestoreRcx
0x140008d34  retn
0x140008d35  ror     rcx, 10h; StackCookie
0x140008d39  jmp     __report_gsfailure
```
