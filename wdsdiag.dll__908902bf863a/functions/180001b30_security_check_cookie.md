# __security_check_cookie

- ea: `0x180001b30`
- end: `0x180001b4f`
- name: `__security_check_cookie`
- size: `31`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001338`
- `0x1800021a8`

## callees

- `0x180001b30`
- `0x180001e10`

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
0x180001b30  cmp     rcx, cs:__security_cookie
0x180001b37  jnz     short loc_180001B4A
0x180001b39  rol     rcx, 10h
0x180001b3d  test    cx, 0FFFFh
0x180001b42  jnz     short loc_180001B46
0x180001b44  nop
0x180001b45  retn
0x180001b46  ror     rcx, 10h
0x180001b4a  jmp     __report_gsfailure
```
