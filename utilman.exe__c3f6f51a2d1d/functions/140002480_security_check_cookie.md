# __security_check_cookie

- ea: `0x140002480`
- end: `0x14000249e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001304`
- `0x1400013dc`
- `0x1400014a4`
- `0x140001758`
- `0x140001a50`
- `0x140001c94`
- `0x1400034ac`
- `0x140003888`
- `0x140003cf8`
- `0x140003fb8`
- `0x140004dac`
- `0x140004f28`
- `0x1400051a4`
- `0x140005964`
- `0x140005d80`
- `0x140007484`
- `0x140007be4`
- `0x140008e00`
- `0x140009f00`
- `0x14000a144`
- `0x14000a448`
- `0x14000a748`
- `0x14000b380`
- `0x14000dd50`
- `0x14000dea0`
- `0x14000e550`
- `0x14000e624`
- `0x14000e81c`
- `0x14000f2d0`
- `0x14000f828`
- `0x14000fad8`
- `0x14000fce8`
- `0x14000fe7c`
- `0x1400100c8`
- `0x140010c88`
- `0x140011ff8`
- `0x1400121cc`
- `0x140012f54`
- `0x1400137c4`
- `0x140014310`
- `0x140014560`
- `0x140014ffc`
- `0x140015720`
- `0x140015fb8`
- `0x1400187fc`
- `0x140018d0c`
- `0x140018f28`
- `0x140019090`
- `0x1400191d0`

## callees

- `0x140002480`
- `0x140002750`

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
0x140002480  cmp     rcx, cs:__security_cookie
0x140002487  jnz     short loc_140002499
0x140002489  rol     rcx, 10h
0x14000248d  test    cx, 0FFFFh
0x140002492  jnz     short loc_140002495
0x140002494  retn
0x140002495  ror     rcx, 10h; StackCookie
0x140002499  jmp     __report_gsfailure
```
