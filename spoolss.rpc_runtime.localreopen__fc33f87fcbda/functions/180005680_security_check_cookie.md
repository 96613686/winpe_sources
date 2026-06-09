# __security_check_cookie

- ea: `0x180005680`
- end: `0x18000569e`
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
- `0x180002908`
- `0x1800039ac`
- `0x18000445c`
- `0x180006d64`
- `0x180007014`
- `0x1800078cc`
- `0x180007a40`
- `0x180007cb4`
- `0x180008c64`
- `0x180008f94`
- `0x18000a1a4`
- `0x18000bba4`
- `0x18000c860`
- `0x18000ca6c`
- `0x1800103b8`
- `0x180010a84`
- `0x180013528`
- `0x18001374c`
- `0x1800138d0`
- `0x180014414`
- `0x1800145b0`
- `0x180014b7c`
- `0x1800154bc`
- `0x180015c64`
- `0x18001643c`
- `0x1800168f0`

## callees

- `0x180005680`
- `0x180005c30`

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
0x180005680  cmp     rcx, cs:__security_cookie
0x180005687  jnz     short ReportFailure
0x180005689  rol     rcx, 10h
0x18000568d  test    cx, 0FFFFh
0x180005692  jnz     short RestoreRcx
0x180005694  retn
0x180005695  ror     rcx, 10h; StackCookie
0x180005699  jmp     __report_gsfailure
```
