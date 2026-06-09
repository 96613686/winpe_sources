# wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800026d0`
- end: `0x1800026f3`
- name: `?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002620`

## callees

- `0x1800026d0`
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
0x1800026d0  sub     rsp, 28h
0x1800026d4  mov     rax, cs:?g_pfnRaiseFailFastException@details@wil@@3P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZEA; void (*wil::details::g_pfnRaiseFailFastException)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800026db  test    rax, rax
0x1800026de  jz      short loc_1800026E7
0x1800026e0  xor     edx, edx
0x1800026e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e7  mov     ecx, 7
0x1800026ec  int     29h; Win8: RtlFailFast(ecx)
0x1800026ee  add     rsp, 28h
0x1800026f2  retn
```
