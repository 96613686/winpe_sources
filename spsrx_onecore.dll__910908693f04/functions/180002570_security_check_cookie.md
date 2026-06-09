# __security_check_cookie

- ea: `0x180002570`
- end: `0x18000258e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003064`
- `0x180003ab0`
- `0x1800043c0`
- `0x1800044e0`
- `0x1800045a0`
- `0x180004ac0`
- `0x180005e28`
- `0x180006598`
- `0x180007120`
- `0x1800073c8`
- `0x1800074dc`
- `0x18000764c`
- `0x1800078ec`
- `0x180007ff0`
- `0x18000830c`
- `0x18000858c`
- `0x18000c0e0`

## callees

- `0x180002570`
- `0x1800025d0`

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
0x180002570  cmp     rcx, cs:__security_cookie
0x180002577  jnz     short ReportFailure
0x180002579  rol     rcx, 10h
0x18000257d  test    cx, 0FFFFh
0x180002582  jnz     short RestoreRcx
0x180002584  retn
0x180002585  ror     rcx, 10h; StackCookie
0x180002589  jmp     __report_gsfailure
```
