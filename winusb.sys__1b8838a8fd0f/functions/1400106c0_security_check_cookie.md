# __security_check_cookie

- ea: `0x1400106c0`
- end: `0x1400106de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001e04`
- `0x1400034cc`
- `0x140003a20`
- `0x140006dec`
- `0x140008aa4`
- `0x140008df0`
- `0x1400099d0`
- `0x14000a450`
- `0x14000af00`
- `0x14000b670`
- `0x14000ea0c`
- `0x14000eff0`
- `0x14001058c`
- `0x140018010`
- `0x14001ab90`
- `0x14001b870`
- `0x14001ba24`
- `0x14001cb74`
- `0x14001e03c`

## callees

- `0x140001010`
- `0x1400106c0`

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
0x1400106c0  cmp     rcx, cs:__security_cookie
0x1400106c7  jnz     short ReportFailure
0x1400106c9  rol     rcx, 10h
0x1400106cd  test    cx, 0FFFFh
0x1400106d2  jnz     short RestoreRcx
0x1400106d4  retn
0x1400106d5  ror     rcx, 10h; StackCookie
0x1400106d9  jmp     __report_gsfailure
```
