# __security_check_cookie

- ea: `0x140005050`
- end: `0x14000506e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001190`
- `0x140001328`
- `0x1400039f0`
- `0x140003b00`
- `0x140004028`
- `0x140004f1c`
- `0x14000e6dc`
- `0x14000e888`
- `0x14000eba0`
- `0x14000f19c`
- `0x14000f3b0`
- `0x14000f56c`
- `0x14000f6fc`
- `0x14000f950`
- `0x14000fbf8`
- `0x14000fd48`
- `0x140010014`
- `0x140010ad8`
- `0x140010d7c`
- `0x1400114f8`
- `0x140011920`
- `0x140011d94`
- `0x14001218c`
- `0x140012fa0`
- `0x140013ba0`
- `0x140013e00`
- `0x140014a44`
- `0x140015288`
- `0x1400156d0`
- `0x140015900`
- `0x140015a70`
- `0x140015da0`
- `0x140016010`
- `0x1400163e0`
- `0x140016760`

## callees

- `0x140003f30`
- `0x140005050`

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
0x140005050  cmp     rcx, cs:__security_cookie
0x140005057  jnz     short ReportFailure
0x140005059  rol     rcx, 10h
0x14000505d  test    cx, 0FFFFh
0x140005062  jnz     short RestoreRcx
0x140005064  retn
0x140005065  ror     rcx, 10h; StackCookie
0x140005069  jmp     __report_gsfailure
```
