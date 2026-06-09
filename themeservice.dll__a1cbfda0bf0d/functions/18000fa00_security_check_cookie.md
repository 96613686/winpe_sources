# __security_check_cookie

- ea: `0x18000fa00`
- end: `0x18000fa1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013b4`
- `0x180001478`
- `0x18000172c`
- `0x180001a24`
- `0x180001de4`
- `0x180002270`
- `0x180002660`
- `0x180002940`
- `0x180003558`
- `0x180003790`
- `0x180004be0`
- `0x180004d80`
- `0x18000546c`
- `0x180006770`
- `0x1800067e0`
- `0x180006e30`
- `0x18000838c`
- `0x180008480`
- `0x180008790`
- `0x180008924`
- `0x180008ca4`
- `0x180008fbc`
- `0x180009f7c`
- `0x18000a99c`
- `0x18000ba50`
- `0x18000bcd4`
- `0x18000c930`
- `0x18000ccd0`
- `0x18000de20`
- `0x18000eb30`
- `0x18000ecd4`
- `0x18000f190`
- `0x18000f3d8`
- `0x18000f940`

## callees

- `0x180007c50`
- `0x18000fa00`

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
0x18000fa00  cmp     rcx, cs:__security_cookie
0x18000fa07  jnz     short ReportFailure
0x18000fa09  rol     rcx, 10h
0x18000fa0d  test    cx, 0FFFFh
0x18000fa12  jnz     short RestoreRcx
0x18000fa14  retn
0x18000fa15  ror     rcx, 10h
0x18000fa19  jmp     __report_gsfailure
```
