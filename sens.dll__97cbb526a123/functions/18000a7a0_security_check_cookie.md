# __security_check_cookie

- ea: `0x18000a7a0`
- end: `0x18000a7be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001850`
- `0x180001d70`
- `0x180002060`
- `0x180002c10`
- `0x180003bd0`
- `0x1800041fc`
- `0x180004e70`
- `0x180004f10`
- `0x1800050b0`
- `0x1800051d0`
- `0x180005650`
- `0x180006740`
- `0x180006958`
- `0x180006dfc`
- `0x18000748c`
- `0x180007698`
- `0x180007dd0`
- `0x1800097c4`
- `0x1800098f4`
- `0x180009cc4`
- `0x18000a6f4`

## callees

- `0x180008850`
- `0x18000a7a0`

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
0x18000a7a0  cmp     rcx, cs:__security_cookie
0x18000a7a7  jnz     short ReportFailure
0x18000a7a9  rol     rcx, 10h
0x18000a7ad  test    cx, 0FFFFh
0x18000a7b2  jnz     short RestoreRcx
0x18000a7b4  retn
0x18000a7b5  ror     rcx, 10h
0x18000a7b9  jmp     __report_gsfailure
```
