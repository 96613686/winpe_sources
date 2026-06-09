# __security_check_cookie

- ea: `0x1800024e0`
- end: `0x1800024fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`
- `0x180001980`
- `0x180001b84`
- `0x180001cd8`
- `0x180001d30`
- `0x180003484`
- `0x1800035d4`
- `0x180003880`
- `0x180003a90`
- `0x180004254`
- `0x1800045f4`
- `0x1800048b0`
- `0x180004bd4`
- `0x180004ea8`
- `0x1800055f0`
- `0x18000565c`
- `0x180005800`
- `0x180005940`
- `0x180005b68`
- `0x180005db8`
- `0x180006390`
- `0x180006558`
- `0x180006718`
- `0x180006a10`
- `0x180006f60`
- `0x1800071f0`
- `0x1800073d0`
- `0x1800076d0`
- `0x180007844`

## callees

- `0x1800024e0`
- `0x180002af0`

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
0x1800024e0  cmp     rcx, cs:__security_cookie
0x1800024e7  jnz     short ReportFailure
0x1800024e9  rol     rcx, 10h
0x1800024ed  test    cx, 0FFFFh
0x1800024f2  jnz     short RestoreRcx
0x1800024f4  retn
0x1800024f5  ror     rcx, 10h; StackCookie
0x1800024f9  jmp     __report_gsfailure
```
