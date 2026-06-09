# __security_check_cookie

- ea: `0x140001390`
- end: `0x1400013ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002b10`
- `0x140003470`
- `0x140003aa4`
- `0x1400066c4`
- `0x140009130`
- `0x140009ec8`
- `0x14000a68c`
- `0x14000a828`
- `0x14000aae0`
- `0x14000b2c4`
- `0x14000b6b8`
- `0x14000b9a0`
- `0x14000bbf0`
- `0x14000c860`
- `0x14000ca78`
- `0x14000caf0`
- `0x14000ccb8`
- `0x14000e294`

## callees

- `0x140001390`
- `0x1400013c0`

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
0x140001390  cmp     rcx, cs:__security_cookie
0x140001397  jnz     short loc_1400013A9
0x140001399  rol     rcx, 10h
0x14000139d  test    cx, 0FFFFh
0x1400013a2  jnz     short loc_1400013A5
0x1400013a4  retn
0x1400013a5  ror     rcx, 10h; StackCookie
0x1400013a9  jmp     __report_gsfailure
```
