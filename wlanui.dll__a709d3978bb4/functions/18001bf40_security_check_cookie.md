# __security_check_cookie

- ea: `0x18001bf40`
- end: `0x18001bf5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000206c`
- `0x1800021bc`
- `0x1800030f4`
- `0x18000418c`
- `0x180004548`
- `0x180004698`
- `0x180004828`
- `0x1800049ec`
- `0x180005364`
- `0x1800054fc`
- `0x18000581c`
- `0x180005ec0`
- `0x1800064c0`
- `0x1800070e8`
- `0x180007df0`
- `0x180008670`
- `0x18000a7f8`
- `0x18000ad4c`
- `0x18000b514`
- `0x18000c824`
- `0x18000cfb8`
- `0x18000d464`
- `0x18000e918`
- `0x18000ec54`
- `0x18000ef50`
- `0x18000fc8c`
- `0x18000fe78`
- `0x180013120`
- `0x180014b70`
- `0x180016f48`
- `0x18001716c`
- `0x180017394`
- `0x180019710`
- `0x18001a09c`
- `0x18001a660`
- `0x18001a8c0`
- `0x18001ad64`
- `0x18001ae4c`
- `0x18001bd00`

## callees

- `0x1800019f0`
- `0x18001bf40`

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
0x18001bf40  cmp     rcx, cs:__security_cookie
0x18001bf47  jnz     short ReportFailure
0x18001bf49  rol     rcx, 10h
0x18001bf4d  test    cx, 0FFFFh
0x18001bf52  jnz     short RestoreRcx
0x18001bf54  retn
0x18001bf55  ror     rcx, 10h
0x18001bf59  jmp     __report_gsfailure
```
