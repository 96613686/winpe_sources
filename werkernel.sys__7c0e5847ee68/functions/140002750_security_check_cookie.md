# __security_check_cookie

- ea: `0x140002750`
- end: `0x14000276e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400017e8`
- `0x1400018bc`
- `0x140001f88`
- `0x140002078`
- `0x1400023e8`
- `0x14000261c`
- `0x14000c6f0`
- `0x14000cc50`
- `0x14000ce68`
- `0x14000d2a8`
- `0x14000dc94`
- `0x14000dfd0`
- `0x14000e260`
- `0x14000e72c`
- `0x1400100f4`
- `0x140010a80`
- `0x140012080`
- `0x140012bfc`

## callees

- `0x1400010c0`
- `0x140002750`

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
0x140002750  cmp     rcx, cs:__security_cookie
0x140002757  jnz     short ReportFailure
0x140002759  rol     rcx, 10h
0x14000275d  test    cx, 0FFFFh
0x140002762  jnz     short RestoreRcx
0x140002764  retn
0x140002765  ror     rcx, 10h; StackCookie
0x140002769  jmp     __report_gsfailure
```
