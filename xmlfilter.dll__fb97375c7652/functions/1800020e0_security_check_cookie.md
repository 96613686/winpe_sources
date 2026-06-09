# __security_check_cookie

- ea: `0x1800020e0`
- end: `0x1800020fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001100`
- `0x1800013b4`
- `0x180003894`
- `0x180003b40`
- `0x1800046d8`
- `0x180005198`
- `0x180005568`
- `0x180005a20`
- `0x180005f70`
- `0x180007e34`
- `0x1800081b0`
- `0x180008a10`
- `0x180009e5c`
- `0x180009f68`
- `0x18000a97c`
- `0x18000c80c`
- `0x18000cb28`
- `0x18000d928`
- `0x18000dbb0`
- `0x18000ddf0`
- `0x18000df18`
- `0x18000e1e8`
- `0x18000e98c`
- `0x18000f7e0`
- `0x180010410`
- `0x180010c24`
- `0x180010dcc`
- `0x180011294`
- `0x180011e40`
- `0x180012228`
- `0x180012378`
- `0x180012508`
- `0x1800126ec`
- `0x1800130bc`
- `0x18001325c`
- `0x1800134f8`
- `0x180014320`

## callees

- `0x1800020e0`
- `0x180002570`

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
0x1800020e0  cmp     rcx, cs:__security_cookie
0x1800020e7  jnz     short ReportFailure
0x1800020e9  rol     rcx, 10h
0x1800020ed  test    cx, 0FFFFh
0x1800020f2  jnz     short RestoreRcx
0x1800020f4  retn
0x1800020f5  ror     rcx, 10h; StackCookie
0x1800020f9  jmp     __report_gsfailure
```
