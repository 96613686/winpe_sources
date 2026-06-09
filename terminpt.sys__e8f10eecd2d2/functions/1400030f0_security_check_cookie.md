# __security_check_cookie

- ea: `0x1400030f0`
- end: `0x14000310e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002fbc`
- `0x14000abb4`

## callees

- `0x140001010`
- `0x1400030f0`

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
0x1400030f0  cmp     rcx, cs:__security_cookie
0x1400030f7  jnz     short ReportFailure
0x1400030f9  rol     rcx, 10h
0x1400030fd  test    cx, 0FFFFh
0x140003102  jnz     short RestoreRcx
0x140003104  retn
0x140003105  ror     rcx, 10h; StackCookie
0x140003109  jmp     __report_gsfailure
```
