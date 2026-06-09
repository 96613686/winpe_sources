# __security_check_cookie

- ea: `0x18000ff10`
- end: `0x18000ff2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006090`
- `0x1800074f8`
- `0x18000844c`
- `0x18000a13c`
- `0x18000a948`
- `0x18000b17c`
- `0x18000efbc`
- `0x18000fe84`

## callees

- `0x1800018f0`
- `0x18000ff10`

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
0x18000ff10  cmp     rcx, cs:__security_cookie
0x18000ff17  jnz     short ReportFailure
0x18000ff19  rol     rcx, 10h
0x18000ff1d  test    cx, 0FFFFh
0x18000ff22  jnz     short RestoreRcx
0x18000ff24  retn
0x18000ff25  ror     rcx, 10h
0x18000ff29  jmp     __report_gsfailure
```
