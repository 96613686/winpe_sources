# __security_check_cookie

- ea: `0x18001b150`
- end: `0x18001b16e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `95`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010bc`
- `0x180001120`
- `0x1800011e4`
- `0x180001290`
- `0x180001384`
- `0x18000144c`
- `0x180001510`
- `0x18000173c`
- `0x180001838`
- `0x1800018fc`
- `0x180001978`
- `0x1800019f8`
- `0x180001ab0`
- `0x180001ba4`
- `0x180001c98`
- `0x180001d30`
- `0x180003868`
- `0x180003afc`
- `0x180004c10`
- `0x180004d7c`
- `0x180005014`
- `0x180005de4`
- `0x180006198`
- `0x18000763c`
- `0x180007904`
- `0x180008024`
- `0x180009738`
- `0x18000b840`
- `0x18000ba28`
- `0x18000bc30`
- `0x18000bf20`
- `0x18000c3c0`
- `0x18000c4e0`
- `0x18000c784`
- `0x18000ce30`
- `0x18000d07c`
- `0x18000dc80`
- `0x18000dedc`
- `0x18000e33c`
- `0x18000f354`
- `0x18000f530`
- `0x18000f928`
- `0x18001126c`
- `0x1800117d0`
- `0x1800123b8`
- `0x180012f38`
- `0x180013334`
- `0x18001369c`
- `0x1800139f4`

## callees

- `0x180002be0`
- `0x18001b150`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x18001b150  cmp     rcx, cs:__security_cookie
0x18001b157  jnz     short ReportFailure
0x18001b159  rol     rcx, 10h
0x18001b15d  test    cx, 0FFFFh
0x18001b162  jnz     short RestoreRcx
0x18001b164  retn
0x18001b165  ror     rcx, 10h
0x18001b169  jmp     __report_gsfailure
```
