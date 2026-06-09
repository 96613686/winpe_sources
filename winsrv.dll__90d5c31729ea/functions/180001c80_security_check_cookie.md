# __security_check_cookie

- ea: `0x180001c80`
- end: `0x180001c9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001230`
- `0x180001c80`

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
0x180001c80  cmp     rcx, cs:__security_cookie
0x180001c87  jnz     short loc_180001C99
0x180001c89  rol     rcx, 10h
0x180001c8d  test    cx, 0FFFFh
0x180001c92  jnz     short loc_180001C95
0x180001c94  retn
0x180001c95  ror     rcx, 10h
0x180001c99  jmp     __report_gsfailure
```
