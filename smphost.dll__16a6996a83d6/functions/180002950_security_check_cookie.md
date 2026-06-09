# __security_check_cookie

- ea: `0x180002950`
- end: `0x18000296e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b0`
- `0x180001bc8`
- `0x180002044`
- `0x180002380`
- `0x1800024f0`
- `0x1800028b0`

## callees

- `0x180001a00`
- `0x180002950`

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
0x180002950  cmp     rcx, cs:__security_cookie
0x180002957  jnz     short ReportFailure
0x180002959  rol     rcx, 10h
0x18000295d  test    cx, 0FFFFh
0x180002962  jnz     short RestoreRcx
0x180002964  retn
0x180002965  ror     rcx, 10h
0x180002969  jmp     __report_gsfailure
```
