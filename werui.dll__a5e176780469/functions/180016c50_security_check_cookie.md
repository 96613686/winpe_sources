# __security_check_cookie

- ea: `0x180016c50`
- end: `0x180016c6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x18000116c`
- `0x180001300`
- `0x180001350`
- `0x1800013e0`
- `0x1800014c0`
- `0x1800015b8`
- `0x180001694`
- `0x180001740`
- `0x1800017a4`
- `0x18000181c`
- `0x180003650`
- `0x180003b20`
- `0x180004160`
- `0x1800045cc`
- `0x1800046fc`
- `0x180004d34`
- `0x180004ff0`
- `0x1800059b0`
- `0x180005fec`
- `0x180006340`
- `0x180006ee0`
- `0x180007490`
- `0x180008dfc`
- `0x18000b0e4`
- `0x18000b334`
- `0x18000bb20`
- `0x18000cbc8`
- `0x18000e18c`
- `0x18000e440`
- `0x18000e6a4`
- `0x18000ea8c`
- `0x18000ec8c`
- `0x18000f170`
- `0x18000f764`
- `0x18000f834`
- `0x18000fc94`
- `0x180010938`
- `0x180010df0`
- `0x1800113fc`
- `0x180011af0`
- `0x180011fa8`
- `0x180012084`
- `0x180012610`
- `0x18001275c`
- `0x180012d68`
- `0x180013814`
- `0x180013948`
- `0x180014e78`
- `0x180015114`

## callees

- `0x180002270`
- `0x180016c50`

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
0x180016c50  cmp     rcx, cs:__security_cookie
0x180016c57  jnz     short ReportFailure
0x180016c59  rol     rcx, 10h
0x180016c5d  test    cx, 0FFFFh
0x180016c62  jnz     short RestoreRcx
0x180016c64  retn
0x180016c65  ror     rcx, 10h
0x180016c69  jmp     __report_gsfailure
```
