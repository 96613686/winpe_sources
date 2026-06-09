# __security_check_cookie

- ea: `0x18000aea0`
- end: `0x18000aebe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001120`
- `0x180002e64`
- `0x180003970`
- `0x1800059e0`
- `0x180007180`
- `0x180007430`
- `0x180007820`
- `0x180007de0`
- `0x180008bc0`
- `0x180008ea0`
- `0x1800095c8`
- `0x180009d6c`
- `0x18000ae10`

## callees

- `0x180002560`
- `0x18000aea0`

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
0x18000aea0  cmp     rcx, cs:__security_cookie
0x18000aea7  jnz     short ReportFailure
0x18000aea9  rol     rcx, 10h
0x18000aead  test    cx, 0FFFFh
0x18000aeb2  jnz     short RestoreRcx
0x18000aeb4  retn
0x18000aeb5  ror     rcx, 10h
0x18000aeb9  jmp     __report_gsfailure
```
