# __security_check_cookie

- ea: `0x18001fbd0`
- end: `0x18001fbee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `70`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001750`
- `0x180002640`
- `0x180002890`
- `0x180002c20`
- `0x1800033c0`
- `0x180003b00`
- `0x180003db0`
- `0x180005b50`
- `0x180005e54`
- `0x1800061d8`
- `0x180006ea0`
- `0x18000743c`
- `0x180007cf4`
- `0x1800089ac`
- `0x180008c3c`
- `0x180008ddc`
- `0x180009110`
- `0x18000a3a0`
- `0x18000a9d0`
- `0x18000c630`
- `0x18000d860`
- `0x18000de44`
- `0x18000e140`
- `0x18000e57c`
- `0x18000e8e0`
- `0x18000eba8`
- `0x18000fff0`
- `0x1800100c4`
- `0x18001093c`
- `0x180010aac`
- `0x180010b90`
- `0x180010c2c`
- `0x180010ce8`
- `0x180010e00`
- `0x180011088`
- `0x18001124c`
- `0x180012368`
- `0x18001d364`
- `0x18001d6d8`
- `0x18001e3bc`
- `0x18001f3f0`
- `0x180023e54`
- `0x180025164`
- `0x180028030`
- `0x1800282dc`
- `0x180028438`
- `0x1800288a8`
- `0x18002a610`
- `0x18002a7a0`

## callees

- `0x18001fbd0`
- `0x18001fc00`

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
0x18001fbd0  cmp     rcx, cs:__security_cookie
0x18001fbd7  jnz     short ReportFailure
0x18001fbd9  rol     rcx, 10h
0x18001fbdd  test    cx, 0FFFFh
0x18001fbe2  jnz     short RestoreRcx
0x18001fbe4  retn
0x18001fbe5  ror     rcx, 10h; StackCookie
0x18001fbe9  jmp     __report_gsfailure
```
