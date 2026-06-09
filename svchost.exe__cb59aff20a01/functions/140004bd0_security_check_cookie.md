# __security_check_cookie

- ea: `0x140004bd0`
- end: `0x140004bee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001250`
- `0x140001480`
- `0x1400018d0`
- `0x140002350`
- `0x1400027b0`
- `0x140002b90`
- `0x140002e00`
- `0x140003180`
- `0x1400039f0`
- `0x140004390`
- `0x140006080`
- `0x1400067dc`
- `0x1400068a4`
- `0x140006fbc`
- `0x140008124`
- `0x140008610`

## callees

- `0x140004bd0`
- `0x140005130`

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
0x140004bd0  cmp     rcx, cs:__security_cookie
0x140004bd7  jnz     short loc_140004BE9
0x140004bd9  rol     rcx, 10h
0x140004bdd  test    cx, 0FFFFh
0x140004be2  jnz     short loc_140004BE5
0x140004be4  retn
0x140004be5  ror     rcx, 10h; StackCookie
0x140004be9  jmp     __report_gsfailure
```
