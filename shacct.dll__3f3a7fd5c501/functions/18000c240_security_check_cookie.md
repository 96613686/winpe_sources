# __security_check_cookie

- ea: `0x18000c240`
- end: `0x18000c25e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001940`
- `0x180003e20`
- `0x180004c90`
- `0x180005060`
- `0x180005300`
- `0x180005f40`
- `0x180007970`
- `0x180007cb0`
- `0x1800087e0`
- `0x18000a4e0`
- `0x18000aa70`
- `0x18000ad20`
- `0x18000b410`
- `0x18000b9e0`
- `0x18000e220`
- `0x18000e6ec`
- `0x18000e81c`
- `0x18000e8b4`
- `0x18000ed10`
- `0x180011734`
- `0x180013770`
- `0x180013cb0`
- `0x1800149b0`
- `0x180014d90`
- `0x180015440`
- `0x180015660`
- `0x180015d30`
- `0x180016330`
- `0x1800164c8`
- `0x1800169c4`
- `0x180016aa8`
- `0x180016c74`

## callees

- `0x18000c240`
- `0x18000c7d0`

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
0x18000c240  cmp     rcx, cs:__security_cookie
0x18000c247  jnz     short ReportFailure
0x18000c249  rol     rcx, 10h
0x18000c24d  test    cx, 0FFFFh
0x18000c252  jnz     short RestoreRcx
0x18000c254  retn
0x18000c255  ror     rcx, 10h; StackCookie
0x18000c259  jmp     __report_gsfailure
```
