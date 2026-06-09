# __security_check_cookie

- ea: `0x1800138f0`
- end: `0x18001390e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023c0`
- `0x1800025f8`
- `0x180002684`
- `0x180002724`
- `0x1800027f8`
- `0x180002e1c`
- `0x180003128`
- `0x1800032cc`
- `0x180003a74`
- `0x180003c40`
- `0x180004c10`
- `0x180004fb4`
- `0x180005b70`
- `0x180006208`
- `0x1800063a0`
- `0x180006468`
- `0x180006514`
- `0x180006660`
- `0x180006918`
- `0x180006b7c`
- `0x18000725c`
- `0x180007310`
- `0x18000755c`
- `0x1800079d4`
- `0x180007eb0`
- `0x1800080b0`
- `0x180008a7c`
- `0x180008c10`
- `0x180009688`
- `0x18000a914`
- `0x18000b5fc`
- `0x18000bc38`
- `0x18000bf38`
- `0x18000c050`
- `0x18000d030`
- `0x18000d738`
- `0x18000d870`
- `0x18000dbb4`
- `0x18000e928`
- `0x18000ef7c`
- `0x18000f6d0`
- `0x18000f954`
- `0x18000ff10`
- `0x180010550`
- `0x180010750`
- `0x1800113d0`
- `0x1800117c8`
- `0x180012618`
- `0x1800129f8`
- `0x180012ef8`

## callees

- `0x180001250`
- `0x1800138f0`

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
0x1800138f0  cmp     rcx, cs:__security_cookie
0x1800138f7  jnz     short loc_180013909
0x1800138f9  rol     rcx, 10h
0x1800138fd  test    cx, 0FFFFh
0x180013902  jnz     short loc_180013905
0x180013904  retn
0x180013905  ror     rcx, 10h
0x180013909  jmp     __report_gsfailure
```
