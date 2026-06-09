# __security_check_cookie

- ea: `0x180001770`
- end: `0x18000178e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002704`
- `0x1800029c0`
- `0x180003900`
- `0x180003f10`
- `0x180004638`
- `0x1800048e4`
- `0x18000558c`
- `0x18000595c`
- `0x180005e08`
- `0x1800068e0`
- `0x18000890c`
- `0x180008f0c`
- `0x180009018`
- `0x180009a0c`
- `0x18000ab28`
- `0x18000b824`
- `0x18000ba64`
- `0x18000caa8`
- `0x18000ccac`
- `0x18000cd50`
- `0x18000cde4`
- `0x18000d000`
- `0x18000d0dc`
- `0x18000d2f8`
- `0x18000d65c`

## callees

- `0x180001770`
- `0x180001dc0`

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
0x180001770  cmp     rcx, cs:__security_cookie
0x180001777  jnz     short ReportFailure
0x180001779  rol     rcx, 10h
0x18000177d  test    cx, 0FFFFh
0x180001782  jnz     short RestoreRcx
0x180001784  retn
0x180001785  ror     rcx, 10h; StackCookie
0x180001789  jmp     __report_gsfailure
```
