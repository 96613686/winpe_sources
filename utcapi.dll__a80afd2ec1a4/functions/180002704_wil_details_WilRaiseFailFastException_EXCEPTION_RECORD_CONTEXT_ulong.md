# wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180002704`
- end: `0x180002728`
- name: `?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `36`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002654`

## callees

- `0x180002704`
- `0x180004010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilRaiseFailFastException(
        struct _EXCEPTION_RECORD *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  if ( wil::details::g_pfnRaiseFailFastException )
    wil::details::g_pfnRaiseFailFastException(this, 0, (unsigned int)a3);
  __fastfail(7u);
}

```

## disassembly

```asm
0x180002704  sub     rsp, 28h
0x180002708  mov     rax, cs:?g_pfnRaiseFailFastException@details@wil@@3P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZEA; void (*wil::details::g_pfnRaiseFailFastException)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000270f  test    rax, rax
0x180002712  jz      short loc_18000271B
0x180002714  xor     edx, edx
0x180002716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000271b  mov     ecx, 7
0x180002720  int     29h; Win8: RtlFailFast(ecx)
0x180002722  add     rsp, 28h
0x180002726  retn
```
