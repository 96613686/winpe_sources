# __security_check_cookie

- ea: `0x18006ef80`
- end: `0x18006ef9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `87`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002048`
- `0x180002144`
- `0x1800021a8`
- `0x180002338`
- `0x180003a30`
- `0x180003b4c`
- `0x18000582c`
- `0x180006c10`
- `0x180016498`
- `0x180016a0c`
- `0x180016b38`
- `0x180023bd8`
- `0x180023ea8`
- `0x180024adc`
- `0x180024c44`
- `0x180024dac`
- `0x1800251d4`
- `0x180025430`
- `0x1800258ac`
- `0x180025dc0`
- `0x180025e5c`
- `0x18002622c`
- `0x1800268e4`
- `0x180026d98`
- `0x180026f44`
- `0x18002e3ac`
- `0x18002e4c8`
- `0x18002e6ec`
- `0x18002ee88`
- `0x180030434`
- `0x180031744`
- `0x1800324b8`
- `0x180032b84`
- `0x180033ad0`
- `0x180035284`
- `0x1800353a8`
- `0x180037b34`
- `0x180037cf8`
- `0x18003882c`
- `0x180038c64`
- `0x18003c0d8`
- `0x18003cc14`
- `0x18003d2a0`
- `0x180040740`
- `0x180041664`
- `0x180041830`
- `0x1800419a8`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`

## callees

- `0x180003330`
- `0x18006ef80`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == _security_cookie )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_180003330(StackCookie);
}

```

## disassembly

```asm
0x18006ef80  cmp     rcx, cs:__security_cookie
0x18006ef87  jnz     short loc_18006EF99
0x18006ef89  rol     rcx, 10h
0x18006ef8d  test    cx, 0FFFFh
0x18006ef92  jnz     short loc_18006EF95
0x18006ef94  retn
0x18006ef95  ror     rcx, 10h
0x18006ef99  jmp     sub_180003330
```
