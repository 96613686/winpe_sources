# __security_check_cookie

- ea: `0x18001d3a0`
- end: `0x18001d3be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800017a8`
- `0x180001d30`
- `0x180002ea4`
- `0x180003b94`
- `0x180004390`
- `0x180004900`
- `0x1800052a0`
- `0x18000574c`
- `0x1800062c8`
- `0x1800066b4`
- `0x180006ed0`
- `0x180007120`
- `0x1800078f4`
- `0x180007a20`
- `0x180007bc4`
- `0x180008050`
- `0x180008840`
- `0x18000b410`
- `0x18000b760`
- `0x18000ba0c`
- `0x18000ca8c`
- `0x18000dcdc`
- `0x180012604`
- `0x18001273c`
- `0x1800128d0`
- `0x180012e9c`
- `0x1800136e4`
- `0x180013c68`
- `0x180013ffc`
- `0x1800152e0`
- `0x180015560`
- `0x180015a00`
- `0x180015ff0`
- `0x180016950`
- `0x1800174ec`
- `0x180019190`
- `0x180019f88`
- `0x18001ae4c`
- `0x18001af0c`
- `0x18001c814`
- `0x18001d298`

## callees

- `0x18000efb0`
- `0x18001d3a0`

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
0x18001d3a0  cmp     rcx, cs:__security_cookie
0x18001d3a7  jnz     short ReportFailure
0x18001d3a9  rol     rcx, 10h
0x18001d3ad  test    cx, 0FFFFh
0x18001d3b2  jnz     short RestoreRcx
0x18001d3b4  retn
0x18001d3b5  ror     rcx, 10h
0x18001d3b9  jmp     __report_gsfailure
```
