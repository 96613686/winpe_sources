# __security_check_cookie

- ea: `0x180018970`
- end: `0x18001898e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001190`
- `0x1800020e0`
- `0x1800027a0`
- `0x180004180`
- `0x180005540`
- `0x1800056d0`
- `0x1800086c0`
- `0x180009ab0`
- `0x180009bc4`
- `0x18000a6b0`
- `0x18000a9e0`
- `0x18000c180`
- `0x18000c770`
- `0x18000cf30`
- `0x18000d740`
- `0x18000de70`
- `0x18000df10`
- `0x18000e890`
- `0x18000ea20`
- `0x18000f210`
- `0x18000f460`
- `0x18000f8d4`
- `0x18001002c`
- `0x1800103f8`
- `0x1800104d8`
- `0x180011ef8`
- `0x180012058`
- `0x1800120b0`
- `0x180012130`
- `0x1800126cc`
- `0x180013744`
- `0x180013cd0`
- `0x180013f4c`
- `0x180013fb0`
- `0x1800140f0`
- `0x180014a84`
- `0x1800156c0`
- `0x180016050`
- `0x180016110`
- `0x180016424`
- `0x1800164e0`
- `0x180016818`
- `0x180016dd4`
- `0x1800171b8`
- `0x18001725c`
- `0x1800175cc`
- `0x1800177e0`
- `0x18001817c`
- `0x180018350`
- `0x180018460`

## callees

- `0x180010ff0`
- `0x180018970`

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
0x180018970  cmp     rcx, cs:__security_cookie
0x180018977  jnz     short ReportFailure
0x180018979  rol     rcx, 10h
0x18001897d  test    cx, 0FFFFh
0x180018982  jnz     short RestoreRcx
0x180018984  retn
0x180018985  ror     rcx, 10h
0x180018989  jmp     __report_gsfailure
```
