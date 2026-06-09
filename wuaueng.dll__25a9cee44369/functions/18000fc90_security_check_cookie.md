# __security_check_cookie

- ea: `0x18000fc90`
- end: `0x18000fcae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000109c`
- `0x180001158`
- `0x180001214`
- `0x1800014c8`
- `0x1800017c0`
- `0x180001ca8`
- `0x180001e08`
- `0x180001e74`
- `0x180002380`
- `0x180002d90`
- `0x1800038f0`
- `0x180003a20`
- `0x180003b94`
- `0x180004a38`
- `0x180004b60`
- `0x180004dfc`
- `0x18000521c`
- `0x180005524`
- `0x180005d80`
- `0x1800062d0`
- `0x180006400`
- `0x180006a98`
- `0x180006e34`
- `0x180006f70`
- `0x1800077f8`
- `0x180008148`
- `0x180008388`
- `0x180008614`
- `0x180008714`
- `0x180008848`
- `0x180008a10`
- `0x180008c38`
- `0x180008dfc`
- `0x180009254`
- `0x180009a60`
- `0x18000a00c`
- `0x18000a070`
- `0x18000a360`
- `0x18000adf4`
- `0x18000b1c8`
- `0x18000d6f8`
- `0x18000d870`
- `0x18000da40`
- `0x18000dc90`
- `0x18000de40`
- `0x18000e320`
- `0x18000e3b0`
- `0x18000e460`
- `0x18000e6a4`
- `0x18000e864`

## callees

- `0x18000fc90`
- `0x1800104e0`

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
0x18000fc90  cmp     rcx, cs:__security_cookie
0x18000fc97  jnz     short ReportFailure
0x18000fc99  rol     rcx, 10h
0x18000fc9d  test    cx, 0FFFFh
0x18000fca2  jnz     short RestoreRcx
0x18000fca4  retn
0x18000fca5  ror     rcx, 10h
0x18000fca9  jmp     __report_gsfailure
```
