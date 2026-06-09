# __security_check_cookie

- ea: `0x18000d9b0`
- end: `0x18000d9ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `70`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001044`
- `0x18000116c`
- `0x1800012a4`
- `0x180001558`
- `0x1800015e8`
- `0x18000188c`
- `0x180001b84`
- `0x180001c7c`
- `0x180001e24`
- `0x180001ed0`
- `0x180004570`
- `0x180004ae0`
- `0x1800055ec`
- `0x180005ce0`
- `0x1800061d4`
- `0x180006904`
- `0x180006fe0`
- `0x180007470`
- `0x1800085b0`
- `0x180008fe0`
- `0x1800091f8`
- `0x180009478`
- `0x18000965c`
- `0x18000a200`
- `0x18000bdd8`
- `0x18000c554`
- `0x18000d198`
- `0x18000f314`
- `0x18000f5d0`
- `0x18000fca0`
- `0x18001014c`
- `0x1800103f8`
- `0x1800106d8`
- `0x180010870`
- `0x18001158c`
- `0x180012440`
- `0x180012820`
- `0x180012c90`
- `0x180013bc0`
- `0x180013d50`
- `0x180014df4`
- `0x180015cb0`
- `0x180016408`
- `0x180016af8`
- `0x180017cf8`
- `0x180017ee0`
- `0x180018154`
- `0x1800181bc`
- `0x180018870`
- `0x180018b50`

## callees

- `0x18000d9b0`
- `0x18000df70`

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
0x18000d9b0  cmp     rcx, cs:__security_cookie
0x18000d9b7  jnz     short ReportFailure
0x18000d9b9  rol     rcx, 10h
0x18000d9bd  test    cx, 0FFFFh
0x18000d9c2  jnz     short RestoreRcx
0x18000d9c4  retn
0x18000d9c5  ror     rcx, 10h; StackCookie
0x18000d9c9  jmp     __report_gsfailure
```
