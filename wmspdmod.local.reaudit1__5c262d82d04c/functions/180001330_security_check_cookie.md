# __security_check_cookie

- ea: `0x180001330`
- end: `0x18000134e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `119`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023f8`
- `0x18004c3e8`
- `0x18006106c`
- `0x1800687e0`
- `0x180068c60`
- `0x1800691b0`
- `0x180069328`
- `0x18006c1e0`
- `0x18006c300`
- `0x18006c550`
- `0x18006c670`
- `0x18006d464`
- `0x18006f2d0`
- `0x18006f3b0`
- `0x18006f494`
- `0x180079244`
- `0x1800795c0`
- `0x1800797c0`
- `0x180079c48`
- `0x18007a0dc`
- `0x18007a524`
- `0x18007a9a4`
- `0x18007ae14`
- `0x18007b2b4`
- `0x18007b73c`
- `0x18007bbe8`
- `0x18007c07c`
- `0x18007c4e0`
- `0x18007c65c`
- `0x180082834`
- `0x180083290`
- `0x180083388`
- `0x1800840d8`
- `0x180085688`
- `0x180085f44`
- `0x180087554`
- `0x180087920`
- `0x1800880c0`
- `0x180088868`
- `0x1800889a4`
- `0x1800893cc`
- `0x180089e70`
- `0x18008eb14`
- `0x18008fec0`
- `0x180090258`
- `0x18009d6dc`
- `0x18009d948`
- `0x18009ddac`
- `0x18009deb8`
- `0x18009e768`

## callees

- `0x180001330`
- `0x1800016c0`

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
0x180001330  cmp     rcx, cs:__security_cookie
0x180001337  jnz     short loc_180001349
0x180001339  rol     rcx, 10h
0x18000133d  test    cx, 0FFFFh
0x180001342  jnz     short loc_180001345
0x180001344  retn
0x180001345  ror     rcx, 10h; StackCookie
0x180001349  jmp     __report_gsfailure
```
