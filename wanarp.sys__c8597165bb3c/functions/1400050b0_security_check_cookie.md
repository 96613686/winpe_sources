# __security_check_cookie

- ea: `0x1400050b0`
- end: `0x1400050ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400019c0`
- `0x140001dd0`
- `0x140002bb0`
- `0x140003c88`
- `0x140004b00`
- `0x140004f7c`
- `0x14000d8c4`
- `0x14000df30`
- `0x14000e530`
- `0x14000e89c`
- `0x14000ef18`
- `0x140010448`
- `0x1400112f0`
- `0x140011618`
- `0x1400140e4`
- `0x14001447c`
- `0x1400146ec`
- `0x140014964`
- `0x140014e84`
- `0x140015440`
- `0x140015b80`
- `0x1400171b4`
- `0x140017a4c`
- `0x140017ee0`
- `0x140018cb8`
- `0x140019864`
- `0x14001a078`
- `0x14001a91c`

## callees

- `0x140002e30`
- `0x1400050b0`

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
0x1400050b0  cmp     rcx, cs:__security_cookie
0x1400050b7  jnz     short ReportFailure
0x1400050b9  rol     rcx, 10h
0x1400050bd  test    cx, 0FFFFh
0x1400050c2  jnz     short RestoreRcx
0x1400050c4  retn
0x1400050c5  ror     rcx, 10h; StackCookie
0x1400050c9  jmp     __report_gsfailure
```
