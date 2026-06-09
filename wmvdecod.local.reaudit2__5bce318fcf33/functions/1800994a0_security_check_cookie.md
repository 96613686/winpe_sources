# __security_check_cookie

- ea: `0x1800994a0`
- end: `0x1800994be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `381`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800013a8`
- `0x1800014bc`
- `0x1800017b0`
- `0x1800018a8`
- `0x180001a80`
- `0x180006ec0`
- `0x180006f70`
- `0x180007070`
- `0x180007170`
- `0x180007250`
- `0x180007470`
- `0x180007530`
- `0x180007650`
- `0x180007770`
- `0x180007830`
- `0x180007dc0`
- `0x180008000`
- `0x180008200`
- `0x1800084b8`
- `0x180008824`
- `0x180008b54`
- `0x18000cfa8`
- `0x180012850`
- `0x180013160`
- `0x18001d148`
- `0x180020250`
- `0x180020460`
- `0x180020670`
- `0x180020a10`
- `0x180020d70`
- `0x1800210d0`
- `0x180021600`
- `0x180021cc8`
- `0x180022244`
- `0x180022804`
- `0x18002301c`
- `0x1800234fc`
- `0x1800238a8`
- `0x1800242f0`
- `0x1800261b4`
- `0x1800270b8`
- `0x18002720c`
- `0x180028b84`
- `0x18002b76c`
- `0x180031d20`
- `0x180031f28`
- `0x180032780`
- `0x180032800`
- `0x180033e04`
- `0x180045ef8`

## callees

- `0x1800994a0`
- `0x180099a30`

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
0x1800994a0  cmp     rcx, cs:__security_cookie
0x1800994a7  jnz     short loc_1800994B9
0x1800994a9  rol     rcx, 10h
0x1800994ad  test    cx, 0FFFFh
0x1800994b2  jnz     short loc_1800994B5
0x1800994b4  retn
0x1800994b5  ror     rcx, 10h; StackCookie
0x1800994b9  jmp     __report_gsfailure
```
