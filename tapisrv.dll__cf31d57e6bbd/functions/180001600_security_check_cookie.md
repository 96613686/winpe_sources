# __security_check_cookie

- ea: `0x180001600`
- end: `0x18000161e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028cc`
- `0x180002b1c`
- `0x1800030a4`
- `0x180004fcc`
- `0x180005378`
- `0x180006610`
- `0x18000b990`
- `0x18000c8a0`
- `0x18000f390`
- `0x180014710`
- `0x180014da0`
- `0x180016d20`
- `0x180017be0`
- `0x18001af14`
- `0x18001c490`
- `0x18001cb10`
- `0x18001dd40`
- `0x18001eafc`
- `0x18001fb28`
- `0x180025e40`
- `0x180026730`
- `0x180026d60`
- `0x1800281f0`
- `0x180028b00`
- `0x18002a8c0`
- `0x18002b064`
- `0x18002c448`
- `0x18002c8fc`
- `0x18002d27c`
- `0x18002d6d0`
- `0x18002efa8`
- `0x180030218`
- `0x180030f40`
- `0x18003120c`
- `0x180031650`
- `0x1800319fc`
- `0x180031eec`
- `0x180032080`
- `0x1800330a8`
- `0x180033f18`
- `0x1800359d4`
- `0x180035c70`
- `0x1800366c4`
- `0x18003682c`
- `0x180036b7c`
- `0x180037148`
- `0x180037264`
- `0x180037344`
- `0x1800380e4`
- `0x1800384f4`

## callees

- `0x180001600`
- `0x180001630`

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
0x180001600  cmp     rcx, cs:__security_cookie
0x180001607  jnz     short ReportFailure
0x180001609  rol     rcx, 10h
0x18000160d  test    cx, 0FFFFh
0x180001612  jnz     short RestoreRcx
0x180001614  retn
0x180001615  ror     rcx, 10h; StackCookie
0x180001619  jmp     __report_gsfailure
```
