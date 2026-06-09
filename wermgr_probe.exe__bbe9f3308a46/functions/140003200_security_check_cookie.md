# __security_check_cookie

- ea: `0x140003200`
- end: `0x14000321e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001098`
- `0x140001178`
- `0x140001270`
- `0x14000131c`
- `0x1400013f0`
- `0x1400014f4`
- `0x1400016cc`
- `0x1400019a4`
- `0x140001a68`
- `0x140001d1c`
- `0x140003cdc`
- `0x140003df4`
- `0x140004090`
- `0x140004d70`
- `0x140005464`
- `0x14000560c`
- `0x140005f98`
- `0x140007298`
- `0x140007684`
- `0x140007888`
- `0x140007cf0`
- `0x140008ce4`
- `0x14000915c`
- `0x14000964c`
- `0x140009da0`
- `0x14000a804`
- `0x14000b354`
- `0x14000b70c`
- `0x14000bd00`
- `0x14000be08`
- `0x14000c798`
- `0x14000e49c`
- `0x140010778`
- `0x140010b80`
- `0x140010fac`
- `0x140011a8c`
- `0x140012434`
- `0x140012d44`
- `0x14001410c`
- `0x140014a20`
- `0x140014b48`
- `0x140014e18`
- `0x1400170a4`
- `0x140017360`
- `0x14001817c`
- `0x140018258`
- `0x14001841c`
- `0x1400186bc`
- `0x14001a8bc`

## callees

- `0x140003200`
- `0x140003400`

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
0x140003200  cmp     rcx, cs:__security_cookie
0x140003207  jnz     short loc_140003219
0x140003209  rol     rcx, 10h
0x14000320d  test    cx, 0FFFFh
0x140003212  jnz     short loc_140003215
0x140003214  retn
0x140003215  ror     rcx, 10h; StackCookie
0x140003219  jmp     __report_gsfailure
```
