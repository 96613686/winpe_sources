# __security_check_cookie

- ea: `0x18001e420`
- end: `0x18001e43e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `70`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001710`
- `0x1800024f0`
- `0x180002700`
- `0x180002a60`
- `0x1800031d0`
- `0x1800038d0`
- `0x180003b70`
- `0x1800057e0`
- `0x180005ac0`
- `0x180005dec`
- `0x180006948`
- `0x180006e04`
- `0x180007620`
- `0x180007728`
- `0x1800084d8`
- `0x180008734`
- `0x180008a4c`
- `0x180009b80`
- `0x18000a270`
- `0x18000bbac`
- `0x18000ccc0`
- `0x18000d23c`
- `0x18000d500`
- `0x18000d904`
- `0x18000dbe0`
- `0x18000de6c`
- `0x18000f268`
- `0x18000f33c`
- `0x18000fb58`
- `0x18000fcc4`
- `0x18000fda8`
- `0x18000fe44`
- `0x18000ff00`
- `0x180010018`
- `0x180010280`
- `0x18001043c`
- `0x180011438`
- `0x18001bdc4`
- `0x18001c120`
- `0x18001cdcc`
- `0x18001dcc0`
- `0x1800224e8`
- `0x18002373c`
- `0x180026088`
- `0x180026300`
- `0x180026448`
- `0x180026840`
- `0x180028260`
- `0x1800283e0`

## callees

- `0x18001e420`
- `0x18001e450`

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
0x18001e420  cmp     rcx, cs:__security_cookie
0x18001e427  jnz     short ReportFailure
0x18001e429  rol     rcx, 10h
0x18001e42d  test    cx, 0FFFFh
0x18001e432  jnz     short RestoreRcx
0x18001e434  retn
0x18001e435  ror     rcx, 10h; StackCookie
0x18001e439  jmp     __report_gsfailure
```
