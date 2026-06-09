# __security_check_cookie

- ea: `0x18001bcf0`
- end: `0x18001bd0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001240`
- `0x180001a80`
- `0x180001ee0`
- `0x1800021f0`
- `0x180002908`
- `0x180002e00`
- `0x1800033b0`
- `0x180003920`
- `0x1800045b0`
- `0x180004824`
- `0x180004940`
- `0x180004bc0`
- `0x180004d10`
- `0x180004ef4`
- `0x180005280`
- `0x180005560`
- `0x180005920`
- `0x1800063a0`
- `0x180006670`
- `0x180006a50`
- `0x180006b64`
- `0x1800072cc`
- `0x1800073d8`
- `0x180007944`
- `0x180007a84`
- `0x180008360`
- `0x1800093ac`
- `0x180009a00`
- `0x180009c7c`
- `0x180009dd8`
- `0x18000a0d4`
- `0x18000a270`
- `0x18000a35c`
- `0x18000a448`
- `0x18000a620`
- `0x18000afbc`
- `0x18000b2e0`
- `0x18000b9fc`
- `0x18000bc78`
- `0x18000bf68`
- `0x18000c788`
- `0x18000c8d0`
- `0x18000cba4`
- `0x18000cdd8`
- `0x18000cec8`
- `0x18000d1a0`
- `0x18000d324`
- `0x18000df30`
- `0x18000e9a0`
- `0x18000ec98`

## callees

- `0x180008d70`
- `0x18001bcf0`

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
0x18001bcf0  cmp     rcx, cs:__security_cookie
0x18001bcf7  jnz     short ReportFailure
0x18001bcf9  rol     rcx, 10h
0x18001bcfd  test    cx, 0FFFFh
0x18001bd02  jnz     short RestoreRcx
0x18001bd04  retn
0x18001bd05  ror     rcx, 10h
0x18001bd09  jmp     __report_gsfailure
```
