# __security_check_cookie

- ea: `0x140001340`
- end: `0x14000135e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001f9c`
- `0x140004d0c`
- `0x1400050fc`
- `0x140005680`
- `0x1400068f4`
- `0x140007644`

## callees

- `0x140001340`
- `0x140001370`

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
0x140001340  cmp     rcx, cs:__security_cookie
0x140001347  jnz     short loc_140001359
0x140001349  rol     rcx, 10h
0x14000134d  test    cx, 0FFFFh
0x140001352  jnz     short loc_140001355
0x140001354  retn
0x140001355  ror     rcx, 10h; StackCookie
0x140001359  jmp     __report_gsfailure
```
