# __security_check_cookie

- ea: `0x1800298c0`
- end: `0x1800298de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002338`
- `0x1800027f8`
- `0x180004518`
- `0x180004d58`
- `0x180006a90`
- `0x180006ca0`
- `0x1800073a0`
- `0x180007bc0`
- `0x180007f0c`
- `0x180008184`
- `0x1800089b8`
- `0x180008c54`
- `0x18000988c`
- `0x180009c30`
- `0x18000aa8c`
- `0x18000ad80`
- `0x18000b984`
- `0x18000bdc4`
- `0x18000bef0`
- `0x18000c910`
- `0x18000cf00`
- `0x18000d63c`
- `0x18000e750`
- `0x18000e9d0`
- `0x18000f534`
- `0x18000fcf0`
- `0x1800101cc`
- `0x1800111dc`
- `0x180011630`
- `0x180011888`
- `0x180012d80`
- `0x180012e90`
- `0x180013128`
- `0x1800131a8`
- `0x18001483c`
- `0x180015730`
- `0x1800176dc`
- `0x18001d544`
- `0x18001e194`
- `0x18002114c`
- `0x180021d34`
- `0x180026958`
- `0x180026efc`
- `0x180026fa0`
- `0x18002744c`
- `0x18002778c`
- `0x180029794`

## callees

- `0x180001f20`
- `0x1800298c0`

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
0x1800298c0  cmp     rcx, cs:__security_cookie
0x1800298c7  jnz     short ReportFailure
0x1800298c9  rol     rcx, 10h
0x1800298cd  test    cx, 0FFFFh
0x1800298d2  jnz     short RestoreRcx
0x1800298d4  retn
0x1800298d5  ror     rcx, 10h
0x1800298d9  jmp     __report_gsfailure
```
