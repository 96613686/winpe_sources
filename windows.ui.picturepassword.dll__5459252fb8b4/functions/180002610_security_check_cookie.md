# __security_check_cookie

- ea: `0x180002610`
- end: `0x18000262e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012cc`
- `0x18000133c`
- `0x1800013cc`
- `0x180001670`
- `0x180001968`
- `0x180001b98`
- `0x180001e70`
- `0x180001f44`
- `0x1800051fc`
- `0x180005490`
- `0x18000573c`
- `0x180005fe8`
- `0x180006154`
- `0x180006570`
- `0x18000695c`
- `0x180006f80`
- `0x180007204`
- `0x180007600`
- `0x180009400`
- `0x18000a49c`
- `0x18000a96c`
- `0x18000ad34`
- `0x18000be48`
- `0x18000bfb4`
- `0x18000e46c`
- `0x18000f4d0`
- `0x180011534`
- `0x180011b74`
- `0x1800123dc`
- `0x180012bd0`
- `0x1800135c8`
- `0x180013860`
- `0x180013980`
- `0x18001517c`
- `0x180015630`
- `0x180015d58`
- `0x180015f2c`
- `0x180016180`
- `0x180016314`
- `0x1800165c8`
- `0x1800168c4`
- `0x1800169ac`
- `0x180016c5c`
- `0x180016dfc`
- `0x18001720c`
- `0x1800185b4`
- `0x180018dac`
- `0x180018f10`
- `0x180019274`

## callees

- `0x180002610`
- `0x180002ba0`

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
0x180002610  cmp     rcx, cs:__security_cookie
0x180002617  jnz     short ReportFailure
0x180002619  rol     rcx, 10h
0x18000261d  test    cx, 0FFFFh
0x180002622  jnz     short RestoreRcx
0x180002624  retn
0x180002625  ror     rcx, 10h; StackCookie
0x180002629  jmp     __report_gsfailure
```
