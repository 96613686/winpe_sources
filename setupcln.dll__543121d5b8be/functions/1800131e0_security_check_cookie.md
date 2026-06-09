# __security_check_cookie

- ea: `0x1800131e0`
- end: `0x1800131fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001178`
- `0x1800012ac`
- `0x180001418`
- `0x180001524`
- `0x180002f7c`
- `0x180003b54`
- `0x1800040c0`
- `0x180004c70`
- `0x180005c30`
- `0x1800071a8`
- `0x1800074e4`
- `0x18000a0f0`
- `0x18000aa40`
- `0x18000bb18`
- `0x18000c2b0`
- `0x18000c3b0`
- `0x18000c580`
- `0x18000ce94`
- `0x18000d130`
- `0x18000de78`
- `0x18000dfe0`
- `0x18000e1a8`
- `0x18000e894`
- `0x18000eca4`
- `0x18000ffbc`
- `0x1800101a4`
- `0x180010840`
- `0x1800117e0`
- `0x18001200c`
- `0x180012820`
- `0x180012a08`
- `0x180012d54`

## callees

- `0x180002da0`
- `0x1800131e0`

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
0x1800131e0  cmp     rcx, cs:__security_cookie
0x1800131e7  jnz     short ReportFailure
0x1800131e9  rol     rcx, 10h
0x1800131ed  test    cx, 0FFFFh
0x1800131f2  jnz     short RestoreRcx
0x1800131f4  retn
0x1800131f5  ror     rcx, 10h
0x1800131f9  jmp     __report_gsfailure
```
