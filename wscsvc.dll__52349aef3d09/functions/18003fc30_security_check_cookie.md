# __security_check_cookie

- ea: `0x18003fc30`
- end: `0x18003fc4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `88`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010f4`
- `0x180001250`
- `0x180001300`
- `0x180001448`
- `0x18000148c`
- `0x18000156c`
- `0x1800016a8`
- `0x180001704`
- `0x1800017f8`
- `0x18000190c`
- `0x180002fc0`
- `0x180003a80`
- `0x180003d90`
- `0x180003e40`
- `0x180003f80`
- `0x180005650`
- `0x180005710`
- `0x1800062d0`
- `0x180006a70`
- `0x1800073b0`
- `0x180007690`
- `0x180007c50`
- `0x1800080c0`
- `0x180008b80`
- `0x180008cc0`
- `0x18000b59c`
- `0x180015a9c`
- `0x180015bf0`
- `0x180016120`
- `0x180016820`
- `0x180016d50`
- `0x180017c60`
- `0x180019850`
- `0x18001a7c0`
- `0x18001abb0`
- `0x18001b960`
- `0x18001cb1c`
- `0x18001d9e0`
- `0x18001f82c`
- `0x18001fb88`
- `0x180020ce4`
- `0x180020df0`
- `0x180021128`
- `0x18002400c`
- `0x180024630`
- `0x180025520`
- `0x180026b64`
- `0x1800280ac`
- `0x180029720`

## callees

- `0x18002a990`
- `0x18003fc30`

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
0x18003fc30  cmp     rcx, cs:__security_cookie
0x18003fc37  jnz     short ReportFailure
0x18003fc39  rol     rcx, 10h
0x18003fc3d  test    cx, 0FFFFh
0x18003fc42  jnz     short RestoreRcx
0x18003fc44  retn
0x18003fc45  ror     rcx, 10h
0x18003fc49  jmp     __report_gsfailure
```
