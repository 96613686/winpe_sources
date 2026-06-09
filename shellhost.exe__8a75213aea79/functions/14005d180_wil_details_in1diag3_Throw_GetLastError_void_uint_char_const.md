# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x14005d180`
- end: `0x14005d1a0`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006ab0`
- `0x1400504f8`
- `0x1400505a0`

## callees

- `0x14004cc1c`

## string_xrefs

- `0x14005d189`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    956,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x14005d180  sub     rsp, 38h
0x14005d184  mov     rax, [rsp+38h]
0x14005d189  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14005d190  mov     edx, 3BCh; int
0x14005d195  mov     [rsp+38h+var_10], rax; char *
0x14005d19a  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
