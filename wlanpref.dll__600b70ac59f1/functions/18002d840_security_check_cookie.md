# __security_check_cookie

- ea: `0x18002d840`
- end: `0x18002d85e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `66`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002154`
- `0x18000227c`
- `0x18000434c`
- `0x180004d64`
- `0x180004fc8`
- `0x18000530c`
- `0x180007b3c`
- `0x180007f4c`
- `0x180008484`
- `0x180009274`
- `0x18000a8e8`
- `0x18000ab4c`
- `0x18000acc0`
- `0x18000af10`
- `0x18000b9cc`
- `0x18000bfbc`
- `0x18000c234`
- `0x18000ca14`
- `0x18000d6b0`
- `0x18000e660`
- `0x18000e700`
- `0x18000eb50`
- `0x18000eea0`
- `0x18000f130`
- `0x18000f448`
- `0x18000f630`
- `0x18000f770`
- `0x18000fdf0`
- `0x180010300`
- `0x180010bf0`
- `0x1800114c0`
- `0x18001181c`
- `0x180012840`
- `0x1800132ec`
- `0x180013738`
- `0x1800139a0`
- `0x180014230`
- `0x1800149e8`
- `0x180014ae0`
- `0x180014be8`
- `0x180014f54`
- `0x180015ac4`
- `0x180020214`
- `0x180020344`
- `0x180020ab0`
- `0x180021078`
- `0x180022080`
- `0x180022524`
- `0x180022b40`
- `0x180022c74`

## callees

- `0x180001a60`
- `0x18002d840`

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
0x18002d840  cmp     rcx, cs:__security_cookie
0x18002d847  jnz     short ReportFailure
0x18002d849  rol     rcx, 10h
0x18002d84d  test    cx, 0FFFFh
0x18002d852  jnz     short RestoreRcx
0x18002d854  retn
0x18002d855  ror     rcx, 10h
0x18002d859  jmp     __report_gsfailure
```
