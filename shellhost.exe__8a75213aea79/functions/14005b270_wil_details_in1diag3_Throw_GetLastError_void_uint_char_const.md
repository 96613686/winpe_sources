# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x14005b270`
- end: `0x14005b290`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006ab0`
- `0x140009bfc`
- `0x14005d884`

## callees

- `0x14004cc1c`

## string_xrefs

- `0x14005b279`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    7368,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x14005b270  sub     rsp, 38h
0x14005b274  mov     rax, [rsp+38h]
0x14005b279  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14005b280  mov     edx, 1CC8h; int
0x14005b285  mov     [rsp+38h+var_10], rax; char *
0x14005b28a  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
