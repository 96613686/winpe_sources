# __security_check_cookie

- ea: `0x18000b550`
- end: `0x18000b56e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e50`
- `0x180003d30`
- `0x1800052f0`
- `0x180006210`
- `0x180007c40`
- `0x180007f00`
- `0x180008840`
- `0x1800090e0`
- `0x180009318`
- `0x18000988c`
- `0x18000cdd4`
- `0x18000d070`
- `0x18000d724`
- `0x18000d88c`
- `0x18000da54`
- `0x18000e0c4`
- `0x18000e3dc`
- `0x18000f274`
- `0x18000f5f8`
- `0x180010204`
- `0x180010c7c`
- `0x180012af0`
- `0x180013848`
- `0x1800147b0`
- `0x180014a84`
- `0x180014e90`
- `0x180015304`
- `0x180015bac`
- `0x180015f00`
- `0x1800168c4`
- `0x180016b38`
- `0x180016eec`
- `0x180017cd8`
- `0x1800182f0`
- `0x180019460`
- `0x18001a3e0`
- `0x18001b408`
- `0x18001b810`
- `0x18001be38`
- `0x18001bf74`
- `0x18001c1bc`
- `0x18001c550`

## callees

- `0x18000b550`
- `0x18000b950`

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
0x18000b550  cmp     rcx, cs:__security_cookie
0x18000b557  jnz     short ReportFailure
0x18000b559  rol     rcx, 10h
0x18000b55d  test    cx, 0FFFFh
0x18000b562  jnz     short RestoreRcx
0x18000b564  retn
0x18000b565  ror     rcx, 10h; StackCookie
0x18000b569  jmp     __report_gsfailure
```
