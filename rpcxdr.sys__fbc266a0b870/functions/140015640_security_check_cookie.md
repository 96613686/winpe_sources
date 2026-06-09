# __security_check_cookie

- ea: `0x140015640`
- end: `0x14001565e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400038c8`
- `0x1400064cc`
- `0x140008988`
- `0x140008fb8`
- `0x1400090f4`
- `0x140009540`
- `0x14000aac4`
- `0x14000bf88`
- `0x14000c470`
- `0x14000cb78`
- `0x14000df80`
- `0x140011c84`
- `0x140013fd4`
- `0x14001550c`
- `0x140021a78`
- `0x140022624`

## callees

- `0x140001010`
- `0x140015640`

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
0x140015640  cmp     rcx, cs:__security_cookie
0x140015647  jnz     short ReportFailure
0x140015649  rol     rcx, 10h
0x14001564d  test    cx, 0FFFFh
0x140015652  jnz     short RestoreRcx
0x140015654  retn
0x140015655  ror     rcx, 10h; StackCookie
0x140015659  jmp     __report_gsfailure
```
