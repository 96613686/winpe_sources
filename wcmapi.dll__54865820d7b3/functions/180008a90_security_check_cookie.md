# __security_check_cookie

- ea: `0x180008a90`
- end: `0x180008aae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `156`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001118`
- `0x180001288`
- `0x1800013e0`
- `0x180001518`
- `0x180001630`
- `0x180001754`
- `0x180001858`
- `0x1800019a0`
- `0x180001ac8`
- `0x180001bc4`
- `0x180001cb8`
- `0x180001f6c`
- `0x180002390`
- `0x180002550`
- `0x180002750`
- `0x180002bd0`
- `0x180002e00`
- `0x1800031e0`
- `0x180003c30`
- `0x180003f90`
- `0x180004530`
- `0x180004860`
- `0x180004d40`
- `0x1800050d0`
- `0x180005230`
- `0x180005340`
- `0x180005410`
- `0x1800057b4`
- `0x180005a74`
- `0x180005b34`
- `0x180005f40`
- `0x1800060e8`
- `0x1800061b0`
- `0x180006604`
- `0x180006750`
- `0x180006b4c`
- `0x180006f30`
- `0x18000761c`
- `0x180007754`
- `0x180008010`
- `0x1800085c8`
- `0x180009b44`
- `0x180009e10`
- `0x180009f48`
- `0x18000a040`
- `0x18000a61c`
- `0x18000a8b0`
- `0x18000b070`
- `0x18000b2f8`

## callees

- `0x180008a90`
- `0x180009070`

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
0x180008a90  cmp     rcx, cs:__security_cookie
0x180008a97  jnz     short ReportFailure
0x180008a99  rol     rcx, 10h
0x180008a9d  test    cx, 0FFFFh
0x180008aa2  jnz     short RestoreRcx
0x180008aa4  retn
0x180008aa5  ror     rcx, 10h; StackCookie
0x180008aa9  jmp     __report_gsfailure
```
