# __security_check_cookie

- ea: `0x140017000`
- end: `0x14001701e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001b70`
- `0x140003970`
- `0x140005aa0`
- `0x1400063d0`
- `0x1400066b0`
- `0x14000b1b4`
- `0x14000c928`
- `0x14000e408`
- `0x1400116d4`
- `0x140011dd8`
- `0x14001215c`
- `0x140012c74`
- `0x140012f34`
- `0x140013130`
- `0x1400142b4`
- `0x140014680`
- `0x140015d70`
- `0x14001617c`
- `0x140016ab0`
- `0x140016f4c`
- `0x140027008`
- `0x140027c20`
- `0x14002841c`
- `0x140029390`
- `0x140029634`
- `0x140029f18`
- `0x14002a740`
- `0x14002b890`
- `0x14002c0a0`
- `0x14002d128`
- `0x14002d65c`
- `0x14002e06c`
- `0x14002e6b0`
- `0x14002ed2c`
- `0x14002f0ec`
- `0x140030320`

## callees

- `0x140003440`
- `0x140017000`

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
0x140017000  cmp     rcx, cs:__security_cookie
0x140017007  jnz     short ReportFailure
0x140017009  rol     rcx, 10h
0x14001700d  test    cx, 0FFFFh
0x140017012  jnz     short RestoreRcx
0x140017014  retn
0x140017015  ror     rcx, 10h; StackCookie
0x140017019  jmp     __report_gsfailure
```
