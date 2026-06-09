# __security_check_cookie

- ea: `0x1800028e0`
- end: `0x1800028fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001160`
- `0x1800012b8`
- `0x1800013d8`
- `0x180001500`
- `0x18000159c`
- `0x1800016cc`
- `0x1800017a8`
- `0x18000196c`
- `0x180001b6c`
- `0x180001cbc`
- `0x180001d80`
- `0x180001e30`
- `0x180001f64`
- `0x180001ff8`
- `0x1800020b0`
- `0x1800037b4`
- `0x180003c4c`
- `0x1800045a8`
- `0x180004760`
- `0x180004890`
- `0x180004df0`
- `0x18000674c`
- `0x180006848`
- `0x180006c24`
- `0x180006e2c`
- `0x180007898`
- `0x1800083c8`
- `0x18000918c`
- `0x1800097e0`
- `0x180009a84`
- `0x18000a248`
- `0x18000a4dc`
- `0x18000a964`
- `0x18000ae50`
- `0x18000c6a8`
- `0x18000ce50`
- `0x18000de7c`
- `0x18000f24c`
- `0x18000f410`
- `0x18000fbe4`
- `0x180011430`
- `0x180011930`
- `0x18001202c`
- `0x18001247c`
- `0x180012530`
- `0x180012c18`
- `0x180013454`
- `0x1800136ac`
- `0x180013b0c`

## callees

- `0x1800028e0`
- `0x1800031e0`

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
0x1800028e0  cmp     rcx, cs:__security_cookie
0x1800028e7  jnz     short ReportFailure
0x1800028e9  rol     rcx, 10h
0x1800028ed  test    cx, 0FFFFh
0x1800028f2  jnz     short RestoreRcx
0x1800028f4  retn
0x1800028f5  ror     rcx, 10h; StackCookie
0x1800028f9  jmp     __report_gsfailure
```
