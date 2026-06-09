# __security_check_cookie

- ea: `0x18000a640`
- end: `0x18000a65e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001034`
- `0x1800012e0`
- `0x180002a8c`
- `0x180004050`
- `0x180004258`
- `0x1800052cc`
- `0x180005cf4`
- `0x1800063fc`
- `0x18000741c`
- `0x18000774c`
- `0x180007854`
- `0x180007938`
- `0x180007b08`
- `0x180008930`
- `0x180008af0`
- `0x180008d98`
- `0x18000917c`
- `0x180009230`
- `0x180009ac8`
- `0x180009dfc`
- `0x180009f14`
- `0x18000a220`
- `0x18000a3e8`

## callees

- `0x180002490`
- `0x18000a640`

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
0x18000a640  cmp     rcx, cs:__security_cookie
0x18000a647  jnz     short ReportFailure
0x18000a649  rol     rcx, 10h
0x18000a64d  test    cx, 0FFFFh
0x18000a652  jnz     short RestoreRcx
0x18000a654  retn
0x18000a655  ror     rcx, 10h
0x18000a659  jmp     __report_gsfailure
```
