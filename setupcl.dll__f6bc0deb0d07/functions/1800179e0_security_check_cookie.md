# __security_check_cookie

- ea: `0x1800179e0`
- end: `0x1800179fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `53`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000154c`
- `0x180001848`
- `0x180001ec4`
- `0x180002640`
- `0x180002a60`
- `0x180002b98`
- `0x180002cc8`
- `0x180004428`
- `0x180004844`
- `0x180004f5c`
- `0x1800059a4`
- `0x180005a20`
- `0x180005a90`
- `0x180005da0`
- `0x1800061b0`
- `0x1800065f8`
- `0x180007060`
- `0x180007c28`
- `0x180007cac`
- `0x180009374`
- `0x18000a564`
- `0x18000bc68`
- `0x18000c4b4`
- `0x18000c73c`
- `0x18000d620`
- `0x18000e4e4`
- `0x18000e66c`
- `0x18000e8d4`
- `0x18000eb38`
- `0x18000ec38`
- `0x18000f110`
- `0x18000f22c`
- `0x18000f6e4`
- `0x18000f7e4`
- `0x180010170`
- `0x180010544`
- `0x18001188c`
- `0x180011cb4`
- `0x18001204c`
- `0x180012114`
- `0x1800121d4`
- `0x1800126d8`
- `0x180013ee0`
- `0x180014c48`
- `0x1800156f8`
- `0x180016340`
- `0x180016740`
- `0x180016840`
- `0x1800168e0`
- `0x180016a5c`

## callees

- `0x1800011e0`
- `0x1800179e0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1800179e0  cmp     rcx, cs:__security_cookie
0x1800179e7  jnz     short loc_1800179F9
0x1800179e9  rol     rcx, 10h
0x1800179ed  test    cx, 0FFFFh
0x1800179f2  jnz     short loc_1800179F5
0x1800179f4  retn
0x1800179f5  ror     rcx, 10h
0x1800179f9  jmp     __report_gsfailure
```
