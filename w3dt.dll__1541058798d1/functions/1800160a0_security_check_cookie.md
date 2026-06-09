# __security_check_cookie

- ea: `0x1800160a0`
- end: `0x1800160be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001060`
- `0x180001770`
- `0x18000fad0`
- `0x1800108c0`
- `0x1800115b8`
- `0x180011d44`
- `0x180012b5c`
- `0x180013ed8`
- `0x180014d64`
- `0x180015b2c`
- `0x180015bec`
- `0x180015ffc`

## callees

- `0x180013d10`
- `0x1800160a0`

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
0x1800160a0  cmp     rcx, cs:__security_cookie
0x1800160a7  jnz     short ReportFailure
0x1800160a9  rol     rcx, 10h
0x1800160ad  test    cx, 0FFFFh
0x1800160b2  jnz     short RestoreRcx
0x1800160b4  retn
0x1800160b5  ror     rcx, 10h
0x1800160b9  jmp     __report_gsfailure
```
