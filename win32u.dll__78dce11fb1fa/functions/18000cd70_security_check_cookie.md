# __security_check_cookie

- ea: `0x18000cd70`
- end: `0x18000cd8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800010b0`
- `0x18000cd70`

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
0x18000cd70  cmp     rcx, cs:__security_cookie
0x18000cd77  jnz     short loc_18000CD89
0x18000cd79  rol     rcx, 10h
0x18000cd7d  test    cx, 0FFFFh
0x18000cd82  jnz     short loc_18000CD85
0x18000cd84  retn
0x18000cd85  ror     rcx, 10h
0x18000cd89  jmp     __report_gsfailure
```
