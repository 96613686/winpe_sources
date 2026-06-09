# __security_check_cookie

- ea: `0x18000c860`
- end: `0x18000c87e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002b88`
- `0x18000440c`
- `0x1800048bc`
- `0x180004b8c`
- `0x180005714`
- `0x18000579c`
- `0x18000699c`
- `0x180006a60`
- `0x180007a48`
- `0x180007c60`
- `0x1800081f0`
- `0x180008bb0`
- `0x180008e60`
- `0x180009600`
- `0x180009b84`
- `0x180009f14`
- `0x18000a904`
- `0x18000b094`
- `0x18000b13c`
- `0x18000c03c`
- `0x18000c610`
- `0x18000c740`

## callees

- `0x1800023d0`
- `0x18000c860`

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
0x18000c860  cmp     rcx, cs:__security_cookie
0x18000c867  jnz     short ReportFailure
0x18000c869  rol     rcx, 10h
0x18000c86d  test    cx, 0FFFFh
0x18000c872  jnz     short RestoreRcx
0x18000c874  retn
0x18000c875  ror     rcx, 10h
0x18000c879  jmp     __report_gsfailure
```
