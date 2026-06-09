# __security_check_cookie

- ea: `0x18003c240`
- end: `0x18003c25e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `76`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001178`
- `0x1800011c4`
- `0x180004be0`
- `0x180009130`
- `0x180009eb4`
- `0x18000aa4c`
- `0x18000b228`
- `0x18000c138`
- `0x18000c3d4`
- `0x18000cfd8`
- `0x18000d140`
- `0x18000d360`
- `0x18000e0a4`
- `0x18000e4b4`
- `0x18000f994`
- `0x18000fca4`
- `0x1800103c4`
- `0x180011974`
- `0x180012760`
- `0x180012948`
- `0x1800138f0`
- `0x180014ecc`
- `0x180015a5c`
- `0x180016adc`
- `0x180017b24`
- `0x180019514`
- `0x1800199b0`
- `0x18001a59c`
- `0x18001c818`
- `0x180021220`
- `0x1800232ec`
- `0x180023dd0`
- `0x180024250`
- `0x180029abc`
- `0x18002c67c`
- `0x18002c80c`
- `0x18002c99c`
- `0x18002cf2c`
- `0x18002d504`
- `0x18002d61c`
- `0x18002d7f0`
- `0x18002de34`
- `0x18002e034`
- `0x18002e270`
- `0x18002e3bc`
- `0x18002e65c`
- `0x18002e7a0`
- `0x18002f2e0`
- `0x18002f440`

## callees

- `0x180001a30`
- `0x18003c240`

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
0x18003c240  cmp     rcx, cs:__security_cookie
0x18003c247  jnz     short ReportFailure
0x18003c249  rol     rcx, 10h
0x18003c24d  test    cx, 0FFFFh
0x18003c252  jnz     short RestoreRcx
0x18003c254  retn
0x18003c255  ror     rcx, 10h
0x18003c259  jmp     __report_gsfailure
```
