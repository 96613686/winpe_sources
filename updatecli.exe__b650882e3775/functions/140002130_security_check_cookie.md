# __security_check_cookie

- ea: `0x140002130`
- end: `0x14000214e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x14000193c`
- `0x140002464`
- `0x1400031e8`
- `0x14000347c`
- `0x140003a18`
- `0x140003de8`
- `0x140004354`
- `0x1400046d0`
- `0x140005e9c`
- `0x140006380`
- `0x1400065f4`
- `0x140006db8`
- `0x140006eb8`
- `0x140007ea8`
- `0x140008038`
- `0x1400083c4`
- `0x14000867c`
- `0x1400088dc`
- `0x1400091e4`
- `0x1400093c0`
- `0x140009608`
- `0x14000969c`
- `0x14000983c`
- `0x140009dcc`
- `0x14000a6a8`

## callees

- `0x140002130`
- `0x1400027a0`

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
0x140002130  cmp     rcx, cs:__security_cookie
0x140002137  jnz     short loc_140002149
0x140002139  rol     rcx, 10h
0x14000213d  test    cx, 0FFFFh
0x140002142  jnz     short loc_140002145
0x140002144  retn
0x140002145  ror     rcx, 10h; StackCookie
0x140002149  jmp     __report_gsfailure
```
