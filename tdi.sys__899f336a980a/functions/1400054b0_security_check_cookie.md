# __security_check_cookie

- ea: `0x1400054b0`
- end: `0x1400054ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002240`
- `0x140004ac0`
- `0x140004f38`
- `0x14000542c`
- `0x14000b560`
- `0x14000d138`

## callees

- `0x1400042c0`
- `0x1400054b0`

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
0x1400054b0  cmp     rcx, cs:__security_cookie
0x1400054b7  jnz     short ReportFailure
0x1400054b9  rol     rcx, 10h
0x1400054bd  test    cx, 0FFFFh
0x1400054c2  jnz     short RestoreRcx
0x1400054c4  retn
0x1400054c5  ror     rcx, 10h; StackCookie
0x1400054c9  jmp     __report_gsfailure
```
