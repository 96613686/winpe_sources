# __security_check_cookie

- ea: `0x1800015f0`
- end: `0x18000160e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `100`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003220`
- `0x180003440`
- `0x1800039f0`
- `0x180004510`
- `0x1800047c0`
- `0x18000569c`
- `0x180005df0`
- `0x1800067e0`
- `0x180006f20`
- `0x180006fbc`
- `0x180007590`
- `0x180008184`
- `0x180008264`
- `0x180008cc0`
- `0x180009340`
- `0x18000a060`
- `0x18000b780`
- `0x18000bddc`
- `0x18000c2a0`
- `0x18000c9f8`
- `0x18000dbb0`
- `0x18000dfe0`
- `0x18000f390`
- `0x18000f5d0`
- `0x180010060`
- `0x180012080`
- `0x180012e38`
- `0x180013310`
- `0x180013918`
- `0x180013b8c`
- `0x180013d60`
- `0x180014054`
- `0x18001493c`
- `0x180014bd8`
- `0x18001721c`
- `0x180017a20`
- `0x18001a994`
- `0x18001ab44`
- `0x18001b090`
- `0x18001b184`
- `0x18001b278`
- `0x18001b36c`
- `0x18001b460`
- `0x18001b554`
- `0x18001b648`
- `0x18001b73c`
- `0x18001b830`
- `0x18001b924`
- `0x18001c244`
- `0x18001c74c`

## callees

- `0x1800015f0`
- `0x180001b80`

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
0x1800015f0  cmp     rcx, cs:__security_cookie
0x1800015f7  jnz     short ReportFailure
0x1800015f9  rol     rcx, 10h
0x1800015fd  test    cx, 0FFFFh
0x180001602  jnz     short RestoreRcx
0x180001604  retn
0x180001605  ror     rcx, 10h; StackCookie
0x180001609  jmp     __report_gsfailure
```
