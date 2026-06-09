# __security_check_cookie

- ea: `0x18001e9f0`
- end: `0x18001ea0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028cc`
- `0x180002a04`
- `0x18000304c`
- `0x180003838`
- `0x1800039fc`
- `0x180003d38`
- `0x1800047b0`
- `0x180004a08`
- `0x180004b10`
- `0x180004c9c`
- `0x180004f1c`
- `0x180005578`
- `0x180005914`
- `0x180007044`
- `0x18000d9e8`
- `0x180011874`
- `0x1800125f4`
- `0x180014640`
- `0x180019400`
- `0x18001a564`
- `0x18001a740`
- `0x18001af4c`
- `0x18001b0a4`
- `0x18001b2f8`
- `0x18001b594`
- `0x18001b7dc`
- `0x18001b934`
- `0x18001bc04`
- `0x18001be70`
- `0x18001c15c`
- `0x18001c290`

## callees

- `0x1800022b0`
- `0x18001e9f0`

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
0x18001e9f0  cmp     rcx, cs:__security_cookie
0x18001e9f7  jnz     short ReportFailure
0x18001e9f9  rol     rcx, 10h
0x18001e9fd  test    cx, 0FFFFh
0x18001ea02  jnz     short RestoreRcx
0x18001ea04  retn
0x18001ea05  ror     rcx, 10h
0x18001ea09  jmp     __report_gsfailure
```
