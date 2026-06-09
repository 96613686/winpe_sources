# __security_check_cookie

- ea: `0x140021b00`
- end: `0x140021b1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `69`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000116c`
- `0x140001ce0`
- `0x140003b50`
- `0x140004d40`
- `0x1400076b4`
- `0x140008db0`
- `0x140009a38`
- `0x140009b58`
- `0x14000a6a0`
- `0x14000adf0`
- `0x14000b470`
- `0x14000b8e8`
- `0x14000bbd0`
- `0x14000be14`
- `0x14000c928`
- `0x14000cafc`
- `0x14000d144`
- `0x14000d7e4`
- `0x14000e924`
- `0x14000fc50`
- `0x140010704`
- `0x140010910`
- `0x140010f08`
- `0x14001145c`
- `0x1400115c0`
- `0x140011f60`
- `0x14001291c`
- `0x140013658`
- `0x1400151ec`
- `0x14001663c`
- `0x1400178bc`
- `0x140017fbc`
- `0x14001853c`
- `0x14001989c`
- `0x140019c4c`
- `0x14001a0e0`
- `0x14001a2dc`
- `0x14001a814`
- `0x14001b75c`
- `0x14001c6b0`
- `0x14001e0c0`
- `0x14001e458`
- `0x14002164c`
- `0x140024504`
- `0x140024f10`
- `0x140025014`
- `0x1400255a0`
- `0x140025890`
- `0x140025c50`
- `0x1400260f8`

## callees

- `0x140021b00`
- `0x1400220b0`

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
0x140021b00  cmp     rcx, cs:__security_cookie
0x140021b07  jnz     short loc_140021B19
0x140021b09  rol     rcx, 10h
0x140021b0d  test    cx, 0FFFFh
0x140021b12  jnz     short loc_140021B15
0x140021b14  retn
0x140021b15  ror     rcx, 10h; StackCookie
0x140021b19  jmp     __report_gsfailure
```
