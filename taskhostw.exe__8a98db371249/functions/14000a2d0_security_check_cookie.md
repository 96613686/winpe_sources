# __security_check_cookie

- ea: `0x14000a2d0`
- end: `0x14000a2ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001110`
- `0x1400012b0`
- `0x140001a70`
- `0x140001fb0`
- `0x1400022d0`
- `0x140002970`
- `0x140003c30`
- `0x140006550`
- `0x1400089a4`

## callees

- `0x140007c60`
- `0x14000a2d0`

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
0x14000a2d0  cmp     rcx, cs:__security_cookie
0x14000a2d7  jnz     short loc_14000A2E9
0x14000a2d9  rol     rcx, 10h
0x14000a2dd  test    cx, 0FFFFh
0x14000a2e2  jnz     short loc_14000A2E5
0x14000a2e4  retn
0x14000a2e5  ror     rcx, 10h
0x14000a2e9  jmp     __report_gsfailure
```
