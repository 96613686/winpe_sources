# __security_check_cookie

- ea: `0x18000c990`
- end: `0x18000c9ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013b4`
- `0x180001478`
- `0x18000172c`
- `0x1800020d0`
- `0x180003720`
- `0x180004e0c`
- `0x1800061f4`
- `0x180006a84`
- `0x180007470`
- `0x180007a00`
- `0x1800088cc`
- `0x180008af0`
- `0x180009704`
- `0x18000a430`
- `0x18000a834`
- `0x18000ae28`
- `0x18000b6fc`
- `0x18000e6e0`
- `0x18000eb40`
- `0x18000ef60`
- `0x18000f1a0`
- `0x1800100b0`
- `0x180011610`
- `0x180012f30`
- `0x180013870`
- `0x180013f64`
- `0x180014e04`
- `0x180015180`
- `0x1800153b8`
- `0x1800159c8`
- `0x18001623c`
- `0x180016c10`
- `0x180017474`
- `0x180017874`
- `0x18001795c`
- `0x180019a60`
- `0x180019c10`
- `0x180019de0`
- `0x18001a790`

## callees

- `0x18000c990`
- `0x18000c9c0`

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
0x18000c990  cmp     rcx, cs:__security_cookie
0x18000c997  jnz     short ReportFailure
0x18000c999  rol     rcx, 10h
0x18000c99d  test    cx, 0FFFFh
0x18000c9a2  jnz     short RestoreRcx
0x18000c9a4  retn
0x18000c9a5  ror     rcx, 10h; StackCookie
0x18000c9a9  jmp     __report_gsfailure
```
