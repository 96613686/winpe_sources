# __security_check_cookie

- ea: `0x1800015b0`
- end: `0x1800015ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002c98`
- `0x180003c7c`
- `0x18000409c`
- `0x18000420c`
- `0x1800043c0`
- `0x18000459c`
- `0x180004fe0`
- `0x1800050c8`
- `0x180007214`
- `0x180007b54`
- `0x180007d28`
- `0x18000824c`
- `0x180009ba8`
- `0x18000b160`
- `0x18000b58c`
- `0x18000cb3c`

## callees

- `0x1800015b0`
- `0x180001620`

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
0x1800015b0  cmp     rcx, cs:__security_cookie
0x1800015b7  jnz     short ReportFailure
0x1800015b9  rol     rcx, 10h
0x1800015bd  test    cx, 0FFFFh
0x1800015c2  jnz     short RestoreRcx
0x1800015c4  retn
0x1800015c5  ror     rcx, 10h
0x1800015c9  jmp     __report_gsfailure
```
