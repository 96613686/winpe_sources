# __security_check_cookie

- ea: `0x18000d700`
- end: `0x18000d71e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002dc0`
- `0x180003070`
- `0x180003b34`
- `0x180003f2c`
- `0x180004340`
- `0x180004460`
- `0x18000474c`
- `0x1800049e0`
- `0x180004e8c`
- `0x180005064`
- `0x180005558`
- `0x1800059f8`
- `0x1800062d4`
- `0x180006660`
- `0x180006f80`
- `0x1800077f4`
- `0x180008698`
- `0x1800088e4`
- `0x1800091fc`
- `0x18000b008`
- `0x18000bb68`
- `0x18000d5c8`

## callees

- `0x180001b20`
- `0x18000d700`

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
0x18000d700  cmp     rcx, cs:__security_cookie
0x18000d707  jnz     short ReportFailure
0x18000d709  rol     rcx, 10h
0x18000d70d  test    cx, 0FFFFh
0x18000d712  jnz     short RestoreRcx
0x18000d714  retn
0x18000d715  ror     rcx, 10h
0x18000d719  jmp     __report_gsfailure
```
