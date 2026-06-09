# __security_check_cookie

- ea: `0x180005320`
- end: `0x18000533e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010e0`
- `0x180001394`
- `0x18000168c`
- `0x18000277c`
- `0x1800036ec`
- `0x180004154`
- `0x1800069d0`
- `0x180006c6c`
- `0x180007568`
- `0x1800076d0`
- `0x180007898`
- `0x1800085b4`
- `0x1800088cc`
- `0x180009a18`
- `0x18000b290`
- `0x18000bec0`
- `0x18000c098`
- `0x18000f2ec`
- `0x18000f9a0`
- `0x180011df8`
- `0x180011fec`
- `0x18001215c`
- `0x180012cd0`
- `0x180012e5c`
- `0x1800133ec`
- `0x180013c58`
- `0x180014360`
- `0x180014a84`
- `0x180014ee8`

## callees

- `0x180005320`
- `0x1800058d0`

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
0x180005320  cmp     rcx, cs:__security_cookie
0x180005327  jnz     short ReportFailure
0x180005329  rol     rcx, 10h
0x18000532d  test    cx, 0FFFFh
0x180005332  jnz     short RestoreRcx
0x180005334  retn
0x180005335  ror     rcx, 10h; StackCookie
0x180005339  jmp     __report_gsfailure
```
