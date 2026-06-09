# __security_check_cookie

- ea: `0x18002cfa0`
- end: `0x18002cfbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ca0`
- `0x180003458`
- `0x18000370c`
- `0x1800044a8`
- `0x180005568`
- `0x180006a90`
- `0x180006d20`
- `0x180007b50`
- `0x180007e10`
- `0x18000a370`
- `0x18000a770`
- `0x18000d9e4`
- `0x1800118c0`
- `0x1800135b4`
- `0x1800141a4`
- `0x180014fa0`
- `0x18001507c`
- `0x180016d24`
- `0x180017624`
- `0x18001832c`
- `0x180019240`
- `0x1800196d0`
- `0x18001c6e8`
- `0x18001f058`
- `0x18001f190`
- `0x18002097c`
- `0x180021628`
- `0x180024190`
- `0x180027774`
- `0x180027854`
- `0x180028c40`
- `0x18002986c`
- `0x18002a7d4`
- `0x18002a964`
- `0x18002afb0`
- `0x18002b1e0`
- `0x18002bfa4`
- `0x18002ce70`

## callees

- `0x180001570`
- `0x18002cfa0`

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
0x18002cfa0  cmp     rcx, cs:__security_cookie
0x18002cfa7  jnz     short ReportFailure
0x18002cfa9  rol     rcx, 10h
0x18002cfad  test    cx, 0FFFFh
0x18002cfb2  jnz     short RestoreRcx
0x18002cfb4  retn
0x18002cfb5  ror     rcx, 10h
0x18002cfb9  jmp     __report_gsfailure
```
