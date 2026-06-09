# __security_check_cookie

- ea: `0x180003be0`
- end: `0x180003bfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f58`
- `0x180002148`
- `0x1800022c0`
- `0x1800030b8`
- `0x1800034c0`
- `0x1800036b0`
- `0x180003b30`

## callees

- `0x1800017b0`
- `0x180003be0`

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
0x180003be0  cmp     rcx, cs:__security_cookie
0x180003be7  jnz     short ReportFailure
0x180003be9  rol     rcx, 10h
0x180003bed  test    cx, 0FFFFh
0x180003bf2  jnz     short RestoreRcx
0x180003bf4  retn
0x180003bf5  ror     rcx, 10h
0x180003bf9  jmp     __report_gsfailure
```
