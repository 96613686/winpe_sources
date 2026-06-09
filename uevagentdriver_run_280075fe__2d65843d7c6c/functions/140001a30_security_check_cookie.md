# __security_check_cookie

- ea: `0x140001a30`
- end: `0x140001a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001090`
- `0x1400011b0`
- `0x140001298`
- `0x140001500`
- `0x140001544`
- `0x1400018fc`
- `0x14000b03c`

## callees

- `0x140001010`
- `0x140001a30`

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
0x140001a30  cmp     rcx, cs:__security_cookie
0x140001a37  jnz     short ReportFailure
0x140001a39  rol     rcx, 10h
0x140001a3d  test    cx, 0FFFFh
0x140001a42  jnz     short RestoreRcx
0x140001a44  retn
0x140001a45  ror     rcx, 10h; StackCookie
0x140001a49  jmp     __report_gsfailure
```
