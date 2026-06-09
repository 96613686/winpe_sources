# __security_check_cookie

- ea: `0x14001aa60`
- end: `0x14001aa7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `117`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x1400015b4`
- `0x1400016fc`
- `0x1400017b8`
- `0x140001bb4`
- `0x140001e90`
- `0x140001efc`
- `0x1400025a0`
- `0x140002d48`
- `0x14000302c`
- `0x140003860`
- `0x140003f00`
- `0x140004074`
- `0x140004a10`
- `0x140004eb8`
- `0x140005738`
- `0x140005b58`
- `0x140005e60`
- `0x140005f84`
- `0x14000631c`
- `0x1400066b0`
- `0x140007060`
- `0x14000713c`
- `0x1400074c8`
- `0x140007eb0`
- `0x140007fe0`
- `0x1400080bc`
- `0x140008c78`
- `0x140008f20`
- `0x140008fd4`
- `0x14000951c`
- `0x14000997c`
- `0x140009c30`
- `0x140009d20`
- `0x14000a14c`
- `0x14000a23c`
- `0x14000a63c`
- `0x14000aac4`
- `0x14000ae14`
- `0x14000ae78`
- `0x14000b344`
- `0x14000b530`
- `0x14000b6f8`
- `0x14000bb94`
- `0x14000bf4c`
- `0x14000c52c`
- `0x14000c5b0`
- `0x14000d1e8`
- `0x14000d2ac`

## callees

- `0x14001aa60`
- `0x14001b070`

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
0x14001aa60  cmp     rcx, cs:__security_cookie
0x14001aa67  jnz     short loc_14001AA79
0x14001aa69  rol     rcx, 10h
0x14001aa6d  test    cx, 0FFFFh
0x14001aa72  jnz     short loc_14001AA75
0x14001aa74  retn
0x14001aa75  ror     rcx, 10h
0x14001aa79  jmp     __report_gsfailure
```
