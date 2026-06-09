# __security_check_cookie

- ea: `0x180011000`
- end: `0x18001101e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `53`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800017e0`
- `0x180001940`
- `0x1800019c8`
- `0x180001c1c`
- `0x180001e28`
- `0x1800020a4`
- `0x1800022d4`
- `0x180002488`
- `0x18000297c`
- `0x180002b50`
- `0x180002c90`
- `0x180002f24`
- `0x18000331c`
- `0x180003428`
- `0x180003798`
- `0x180003d00`
- `0x180003f90`
- `0x180004ac0`
- `0x180004f90`
- `0x1800053b0`
- `0x180005660`
- `0x180006700`
- `0x180006850`
- `0x180006a80`
- `0x1800077b0`
- `0x180008718`
- `0x180008cb4`
- `0x1800090c8`
- `0x1800098bc`
- `0x18000a1bc`
- `0x18000a65c`
- `0x18000add0`
- `0x18000afcc`
- `0x18000b100`
- `0x18000b5b0`
- `0x18000b97c`
- `0x18000c078`
- `0x18000c158`
- `0x18000c430`
- `0x18000c6d8`
- `0x18000c894`
- `0x18000cd40`
- `0x18000e8a8`
- `0x18000ebec`
- `0x18000f22c`
- `0x18000f440`
- `0x18000f8bc`
- `0x18000fa10`
- `0x18000fc9c`
- `0x18000feb0`

## callees

- `0x18000e070`
- `0x180011000`

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
0x180011000  cmp     rcx, cs:__security_cookie
0x180011007  jnz     short ReportFailure
0x180011009  rol     rcx, 10h
0x18001100d  test    cx, 0FFFFh
0x180011012  jnz     short RestoreRcx
0x180011014  retn
0x180011015  ror     rcx, 10h
0x180011019  jmp     __report_gsfailure
```
