# __security_check_cookie

- ea: `0x18000ae80`
- end: `0x18000ae9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a6c`
- `0x180001d10`
- `0x180002518`
- `0x180002a00`
- `0x180003280`
- `0x180003510`
- `0x180003820`
- `0x180003aac`
- `0x180003e10`
- `0x180004000`
- `0x180004300`
- `0x1800044a0`
- `0x180004c30`
- `0x180004f10`
- `0x180005370`
- `0x180005830`
- `0x180005ea0`
- `0x180006168`
- `0x180006380`
- `0x180006590`
- `0x180006794`
- `0x180006a20`
- `0x180006b6c`
- `0x1800070f0`
- `0x180007450`
- `0x18000863c`
- `0x180008968`
- `0x180008be4`
- `0x180008e70`
- `0x180009330`
- `0x180009550`
- `0x180009720`
- `0x180009b34`
- `0x180009ee4`
- `0x18000a414`
- `0x18000adc0`

## callees

- `0x180001520`
- `0x18000ae80`

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
0x18000ae80  cmp     rcx, cs:__security_cookie
0x18000ae87  jnz     short ReportFailure
0x18000ae89  rol     rcx, 10h
0x18000ae8d  test    cx, 0FFFFh
0x18000ae92  jnz     short RestoreRcx
0x18000ae94  retn
0x18000ae95  ror     rcx, 10h
0x18000ae99  jmp     __report_gsfailure
```
