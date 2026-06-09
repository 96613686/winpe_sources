# __security_check_cookie

- ea: `0x140040a30`
- end: `0x140040a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001160`
- `0x1400030e0`
- `0x140005238`
- `0x140005308`
- `0x1400054c0`
- `0x1400072e8`
- `0x140007e70`
- `0x14000a4b4`
- `0x14000efa4`
- `0x1400116bc`
- `0x140012740`
- `0x140014b20`
- `0x140014d30`
- `0x140018990`
- `0x14001b37c`
- `0x14001b558`
- `0x14001d7bc`
- `0x14001e8b4`
- `0x14001ed70`
- `0x14001f460`
- `0x14001f4f4`
- `0x140020704`
- `0x140021fb4`
- `0x140023040`
- `0x1400230e8`
- `0x140023a88`
- `0x140023c70`
- `0x140023dfc`
- `0x1400259f4`
- `0x14002b340`
- `0x1400360a4`
- `0x140038b1c`
- `0x140039120`
- `0x14003be34`
- `0x1400400cc`
- `0x140040244`
- `0x1400408ec`
- `0x140054a30`
- `0x140055150`
- `0x140055880`
- `0x140055b70`
- `0x140055f40`
- `0x140056310`
- `0x140057470`
- `0x140057770`
- `0x140057ef0`
- `0x140058200`
- `0x140059890`
- `0x140059c10`
- `0x14005b300`

## callees

- `0x14001c140`
- `0x140040a30`

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
0x140040a30  cmp     rcx, cs:__security_cookie
0x140040a37  jnz     short ReportFailure
0x140040a39  rol     rcx, 10h
0x140040a3d  test    cx, 0FFFFh
0x140040a42  jnz     short RestoreRcx
0x140040a44  retn
0x140040a45  ror     rcx, 10h; StackCookie
0x140040a49  jmp     __report_gsfailure
```
