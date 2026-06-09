# __security_check_cookie

- ea: `0x18003a580`
- end: `0x18003a59e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `116`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b4`
- `0x180001970`
- `0x180002d10`
- `0x1800032f8`
- `0x18000367c`
- `0x180003ca4`
- `0x180005690`
- `0x180006324`
- `0x180006680`
- `0x1800091d0`
- `0x18000a294`
- `0x18000a750`
- `0x18000aac0`
- `0x18000ab94`
- `0x18000af40`
- `0x18000be1c`
- `0x18000c664`
- `0x18000cb40`
- `0x18000cfec`
- `0x18000d760`
- `0x18000e570`
- `0x18000eb30`
- `0x18000f0d8`
- `0x18000f2e0`
- `0x18000f7d0`
- `0x180010520`
- `0x1800111c0`
- `0x180011a94`
- `0x180012470`
- `0x180012840`
- `0x180012ae0`
- `0x180013080`
- `0x1800135d0`
- `0x180014900`
- `0x1800151d0`
- `0x180015b30`
- `0x180015e30`
- `0x180016250`
- `0x180019ef0`
- `0x18001ab50`
- `0x18001bc10`
- `0x18001cecc`
- `0x18001dbe0`
- `0x18001e4f0`
- `0x18001eda0`
- `0x18001fb9c`
- `0x180020030`
- `0x180020794`
- `0x180020c80`

## callees

- `0x18003a580`
- `0x18003ab10`

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
0x18003a580  cmp     rcx, cs:__security_cookie
0x18003a587  jnz     short ReportFailure
0x18003a589  rol     rcx, 10h
0x18003a58d  test    cx, 0FFFFh
0x18003a592  jnz     short RestoreRcx
0x18003a594  retn
0x18003a595  ror     rcx, 10h; StackCookie
0x18003a599  jmp     __report_gsfailure
```
