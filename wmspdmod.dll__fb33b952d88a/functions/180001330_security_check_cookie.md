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
- `0x18006f330`
- `0x18006f410`
- `0x18006f4f4`
- `0x1800792a4`
- `0x180079620`
- `0x180079820`
- `0x180079ca8`
- `0x18007a13c`
- `0x18007a584`
- `0x18007aa04`
- `0x18007ae74`
- `0x18007b314`
- `0x18007b79c`
- `0x18007bc48`
- `0x18007c0dc`
- `0x18007c540`
- `0x18007c6bc`
- `0x180082894`
- `0x1800832f0`
- `0x1800833e8`
- `0x180084138`
- `0x1800856e8`
- `0x180085fa4`
- `0x1800875b4`
- `0x180087980`
- `0x180088120`
- `0x1800888c8`
- `0x180088a04`
- `0x18008942c`
- `0x180089ed0`
- `0x18008eb74`
- `0x18008ff20`
- `0x1800902b8`
- `0x18009d73c`
- `0x18009d9a8`
- `0x18009de0c`
- `0x18009df18`
- `0x18009e7c8`

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
