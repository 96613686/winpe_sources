# __security_check_cookie

- ea: `0x180035e50`
- end: `0x180035e6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001024`
- `0x180002f80`
- `0x18000309c`
- `0x1800039e0`
- `0x180007340`
- `0x18000a220`
- `0x18000cc60`
- `0x18000ee00`
- `0x18000f244`
- `0x18000fe30`
- `0x180010094`
- `0x1800106f0`
- `0x180010c4c`
- `0x1800263c0`
- `0x180028980`
- `0x180028fb0`
- `0x1800297c0`
- `0x18002bfd0`
- `0x18002ced0`
- `0x1800314f0`
- `0x180033930`
- `0x180035010`
- `0x1800354b0`
- `0x180036fe0`
- `0x180037e00`
- `0x180039770`
- `0x18003aa30`
- `0x18003af50`
- `0x18003bad0`
- `0x18003c190`
- `0x18003c480`
- `0x18003ca60`
- `0x18003d050`
- `0x18003d420`
- `0x18003d700`
- `0x18003d950`
- `0x18003db70`
- `0x1800434f0`

## callees

- `0x180035e50`
- `0x180036720`

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
0x180035e50  cmp     rcx, cs:__security_cookie
0x180035e57  jnz     short ReportFailure
0x180035e59  rol     rcx, 10h
0x180035e5d  test    cx, 0FFFFh
0x180035e62  jnz     short RestoreRcx
0x180035e64  retn
0x180035e65  ror     rcx, 10h; StackCookie
0x180035e69  jmp     __report_gsfailure
```
