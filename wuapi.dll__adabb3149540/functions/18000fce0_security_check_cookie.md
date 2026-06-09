# __security_check_cookie

- ea: `0x18000fce0`
- end: `0x18000fcfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000109c`
- `0x180001158`
- `0x18000140c`
- `0x1800014c8`
- `0x1800017c0`
- `0x180001ca8`
- `0x180001e08`
- `0x180001e74`
- `0x180002380`
- `0x180002d90`
- `0x180003800`
- `0x180003974`
- `0x180004310`
- `0x180004a38`
- `0x180004b60`
- `0x180004dfc`
- `0x18000521c`
- `0x1800055e4`
- `0x18000576c`
- `0x1800059b8`
- `0x180005c60`
- `0x180006518`
- `0x180006b3c`
- `0x180006bd4`
- `0x180006d98`
- `0x180006f90`
- `0x180007308`
- `0x180007b64`
- `0x1800082b4`
- `0x180008a44`
- `0x180009064`
- `0x180009564`
- `0x180009974`
- `0x180009f70`
- `0x180009ff0`
- `0x18000a2b0`
- `0x18000a4a4`
- `0x18000a66c`
- `0x18000ae48`
- `0x18000b21c`
- `0x18000d684`
- `0x18000d7fc`
- `0x18000d9cc`
- `0x18000dc1c`
- `0x18000ddcc`
- `0x18000e2ac`
- `0x18000e33c`
- `0x18000e3ec`
- `0x18000e6f8`
- `0x18000e8b8`

## callees

- `0x18000fce0`
- `0x180010530`

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
0x18000fce0  cmp     rcx, cs:__security_cookie
0x18000fce7  jnz     short ReportFailure
0x18000fce9  rol     rcx, 10h
0x18000fced  test    cx, 0FFFFh
0x18000fcf2  jnz     short RestoreRcx
0x18000fcf4  retn
0x18000fcf5  ror     rcx, 10h
0x18000fcf9  jmp     __report_gsfailure
```
