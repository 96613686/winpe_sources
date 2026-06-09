# __security_check_cookie

- ea: `0x140001490`
- end: `0x1400014ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002424`
- `0x140002a54`
- `0x140002bfc`
- `0x1400030b8`
- `0x140003a88`
- `0x140003c44`
- `0x140003f2c`
- `0x140004258`
- `0x1400043a8`
- `0x140004698`
- `0x140004954`
- `0x1400051e0`
- `0x14000550c`
- `0x140005834`
- `0x140005c80`
- `0x1400065cc`

## callees

- `0x140001490`
- `0x1400014c0`

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
0x140001490  cmp     rcx, cs:__security_cookie
0x140001497  jnz     short loc_1400014A9
0x140001499  rol     rcx, 10h
0x14000149d  test    cx, 0FFFFh
0x1400014a2  jnz     short loc_1400014A5
0x1400014a4  retn
0x1400014a5  ror     rcx, 10h; StackCookie
0x1400014a9  jmp     __report_gsfailure
```
