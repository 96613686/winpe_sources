# __security_check_cookie

- ea: `0x180015680`
- end: `0x18001569e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800020c0`
- `0x1800043c0`
- `0x180006524`
- `0x180007100`
- `0x180008c30`
- `0x18000e110`
- `0x18000f4cc`
- `0x1800101d4`
- `0x180010fc0`
- `0x180011300`
- `0x18001175c`
- `0x180012ee8`
- `0x180014d28`
- `0x180015564`

## callees

- `0x18000c190`
- `0x180015680`

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
0x180015680  cmp     rcx, cs:__security_cookie
0x180015687  jnz     short ReportFailure
0x180015689  rol     rcx, 10h
0x18001568d  test    cx, 0FFFFh
0x180015692  jnz     short RestoreRcx
0x180015694  retn
0x180015695  ror     rcx, 10h
0x180015699  jmp     __report_gsfailure
```
