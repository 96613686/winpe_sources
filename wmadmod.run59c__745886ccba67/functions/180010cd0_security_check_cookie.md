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
- `0x18001c350`
- `0x18001c440`
- `0x18001cc70`
- `0x18001cf3c`
- `0x18001cfe8`
- `0x18001d060`
- `0x18002a928`
- `0x18002abf0`
- `0x18002ad70`
- `0x18002b2a0`
- `0x18002b800`
- `0x18002bd80`
- `0x18002c2f0`
- `0x18002c840`
- `0x18002cdb0`
- `0x18002d300`
- `0x18002d870`
- `0x18002ddb0`
- `0x18002e310`
- `0x18002e48c`
- `0x180038a54`
- `0x180038ddc`
- `0x180041728`
- `0x180041c64`
- `0x1800568d4`
- `0x180056d14`
- `0x18006aba8`
- `0x18006db94`
- `0x18007216c`
- `0x18007310c`
- `0x180073198`
- `0x1800732d0`
- `0x180073e68`
- `0x180074e90`
- `0x180076874`
- `0x180077ac0`
- `0x180077ba8`

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
