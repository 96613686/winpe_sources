# __security_check_cookie

- ea: `0x180010250`
- end: `0x18001026e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `70`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011a0`
- `0x180001aa0`
- `0x180001c30`
- `0x1800023e0`
- `0x180002c48`
- `0x180002d10`
- `0x1800032e0`
- `0x1800034a0`
- `0x180003750`
- `0x180003af0`
- `0x180003dbc`
- `0x1800040a0`
- `0x18000419c`
- `0x1800042f4`
- `0x180004cc0`
- `0x180004e70`
- `0x180005010`
- `0x180005adc`
- `0x180007690`
- `0x180007c00`
- `0x180008600`
- `0x1800087c0`
- `0x180008930`
- `0x180008ef4`
- `0x180009354`
- `0x180009770`
- `0x180009870`
- `0x180009980`
- `0x180009a9c`
- `0x180009cf0`
- `0x18000a400`
- `0x18000a550`
- `0x18000a820`
- `0x18000a900`
- `0x18000a9e0`
- `0x18000ac70`
- `0x18000ada0`
- `0x18000ae90`
- `0x18000afb0`
- `0x18000b2f8`
- `0x18000b50c`
- `0x18000b95c`
- `0x18000c00c`
- `0x18000c128`
- `0x18000c2f8`
- `0x18000c3ec`
- `0x18000c798`
- `0x18000c8b8`
- `0x18000cc80`
- `0x18000ce3c`

## callees

- `0x180006640`
- `0x180010250`

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
0x180010250  cmp     rcx, cs:__security_cookie
0x180010257  jnz     short ReportFailure
0x180010259  rol     rcx, 10h
0x18001025d  test    cx, 0FFFFh
0x180010262  jnz     short RestoreRcx
0x180010264  retn
0x180010265  ror     rcx, 10h
0x180010269  jmp     __report_gsfailure
```
