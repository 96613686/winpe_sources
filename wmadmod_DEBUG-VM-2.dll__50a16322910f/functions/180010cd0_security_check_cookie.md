# __security_check_cookie

- ea: `0x180010cd0`
- end: `0x180010cee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `90`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f170`
- `0x1800106ec`
- `0x180019d00`
- `0x180019e78`
- `0x18001a030`
- `0x18001a270`
- `0x18001ae0c`
- `0x18001af70`
- `0x18001b070`
- `0x18001b260`
- `0x18001b360`
- `0x18001b660`
- `0x18001b9d0`
- `0x18001c390`
- `0x18001c480`
- `0x18001ccb0`
- `0x18001cf7c`
- `0x18001d028`
- `0x18001d0a0`
- `0x18002a968`
- `0x18002ac30`
- `0x18002adb0`
- `0x18002b2e0`
- `0x18002b840`
- `0x18002bdc0`
- `0x18002c330`
- `0x18002c880`
- `0x18002cdf0`
- `0x18002d340`
- `0x18002d8b0`
- `0x18002ddf0`
- `0x18002e350`
- `0x18002e4cc`
- `0x180038a94`
- `0x180038e1c`
- `0x180041768`
- `0x180041ca4`
- `0x180056914`
- `0x180056d54`
- `0x18006abe8`
- `0x18006dbd4`
- `0x1800721ac`
- `0x18007314c`
- `0x1800731d8`
- `0x180073310`
- `0x180073ea8`
- `0x180074ed0`
- `0x1800768b4`
- `0x180077b00`
- `0x180077be8`

## callees

- `0x180010cd0`
- `0x180011060`

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
0x180010cd0  cmp     rcx, cs:__security_cookie
0x180010cd7  jnz     short loc_180010CE9
0x180010cd9  rol     rcx, 10h
0x180010cdd  test    cx, 0FFFFh
0x180010ce2  jnz     short loc_180010CE5
0x180010ce4  retn
0x180010ce5  ror     rcx, 10h; StackCookie
0x180010ce9  jmp     __report_gsfailure
```
