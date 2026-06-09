# __security_check_cookie

- ea: `0x18000e9a0`
- end: `0x18000e9be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019b0`
- `0x180001bd0`
- `0x1800023d8`
- `0x180002704`
- `0x180002808`
- `0x18000289c`
- `0x180002a64`
- `0x180002c28`
- `0x180002f48`
- `0x180003078`
- `0x1800031d0`
- `0x180003718`
- `0x180004878`
- `0x180004dbc`
- `0x180004fe4`
- `0x180005458`
- `0x180005880`
- `0x180005960`
- `0x180005f04`
- `0x180006148`
- `0x1800062c4`
- `0x1800067a4`
- `0x1800073e8`
- `0x180007744`
- `0x180007a44`
- `0x180008230`
- `0x180008858`
- `0x18000921c`
- `0x1800097f8`
- `0x180009ae4`
- `0x180009d10`
- `0x180009f6c`
- `0x18000a124`
- `0x18000a57c`
- `0x18000b964`
- `0x18000bc64`
- `0x18000d860`
- `0x18000dfc0`
- `0x18000e874`

## callees

- `0x1800017a0`
- `0x18000e9a0`

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
0x18000e9a0  cmp     rcx, cs:__security_cookie
0x18000e9a7  jnz     short ReportFailure
0x18000e9a9  rol     rcx, 10h
0x18000e9ad  test    cx, 0FFFFh
0x18000e9b2  jnz     short RestoreRcx
0x18000e9b4  retn
0x18000e9b5  ror     rcx, 10h
0x18000e9b9  jmp     __report_gsfailure
```
