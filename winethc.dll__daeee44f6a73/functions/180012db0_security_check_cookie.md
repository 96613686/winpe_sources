# __security_check_cookie

- ea: `0x180012db0`
- end: `0x180012dce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `35`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e5c`
- `0x180001fcc`
- `0x180002568`
- `0x180002818`
- `0x180003548`
- `0x180003b40`
- `0x180004fcc`
- `0x180005798`
- `0x1800076bc`
- `0x18000a5c0`
- `0x18000ab0c`
- `0x18000b204`
- `0x18000b374`
- `0x18000b518`
- `0x18000b6fc`
- `0x18000c82c`
- `0x18000cb58`
- `0x18000ce24`
- `0x18000e2a4`
- `0x18000e520`
- `0x18000e650`
- `0x18000e7d0`
- `0x18000eb64`
- `0x18000f0ec`
- `0x18000f5f8`
- `0x18000f710`
- `0x18000f830`
- `0x18001000c`
- `0x180010174`
- `0x180010250`
- `0x180010450`
- `0x18001070c`
- `0x180010ae4`
- `0x180010cb8`
- `0x1800111dc`

## callees

- `0x1800018c0`
- `0x180012db0`

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
0x180012db0  cmp     rcx, cs:__security_cookie
0x180012db7  jnz     short ReportFailure
0x180012db9  rol     rcx, 10h
0x180012dbd  test    cx, 0FFFFh
0x180012dc2  jnz     short RestoreRcx
0x180012dc4  retn
0x180012dc5  ror     rcx, 10h
0x180012dc9  jmp     __report_gsfailure
```
