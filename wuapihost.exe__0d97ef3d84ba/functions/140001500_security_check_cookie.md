# __security_check_cookie

- ea: `0x140001500`
- end: `0x14000151e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012b0`
- `0x140001340`
- `0x1400026cc`
- `0x140003624`
- `0x140003b64`
- `0x140004b20`
- `0x14000572c`

## callees

- `0x140001500`
- `0x140001800`

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
0x140001500  cmp     rcx, cs:__security_cookie
0x140001507  jnz     short loc_140001519
0x140001509  rol     rcx, 10h
0x14000150d  test    cx, 0FFFFh
0x140001512  jnz     short loc_140001515
0x140001514  retn
0x140001515  ror     rcx, 10h
0x140001519  jmp     __report_gsfailure
```
