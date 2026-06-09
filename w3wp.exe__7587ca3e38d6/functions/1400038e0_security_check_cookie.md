# __security_check_cookie

- ea: `0x1400038e0`
- end: `0x1400038fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001ee8`
- `0x140001ff8`
- `0x140002090`
- `0x14000215c`
- `0x1400027b0`
- `0x14000377c`
- `0x140003840`

## callees

- `0x140001360`
- `0x1400038e0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1400038e0  cmp     rcx, cs:__security_cookie
0x1400038e7  jnz     short loc_1400038F9
0x1400038e9  rol     rcx, 10h
0x1400038ed  test    cx, 0FFFFh
0x1400038f2  jnz     short loc_1400038F5
0x1400038f4  retn
0x1400038f5  ror     rcx, 10h
0x1400038f9  jmp     __report_gsfailure
```
