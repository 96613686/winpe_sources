# __security_check_cookie

- ea: `0x14000a9f0`
- end: `0x14000aa0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001150`
- `0x140001ce0`
- `0x140001e80`
- `0x140002ae0`
- `0x140002bc4`
- `0x140003acc`
- `0x140003f90`
- `0x1400048d4`
- `0x140004edc`
- `0x140005520`
- `0x140005a54`
- `0x1400068dc`
- `0x140006efc`
- `0x14000711c`
- `0x140007c24`
- `0x14000818c`
- `0x140009930`
- `0x140009eb4`

## callees

- `0x140001010`
- `0x14000a9f0`

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
0x14000a9f0  cmp     rcx, cs:__security_cookie
0x14000a9f7  jnz     short ReportFailure
0x14000a9f9  rol     rcx, 10h
0x14000a9fd  test    cx, 0FFFFh
0x14000aa02  jnz     short RestoreRcx
0x14000aa04  retn
0x14000aa05  ror     rcx, 10h; StackCookie
0x14000aa09  jmp     __report_gsfailure
```
