# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180008600`
- end: `0x180008620`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bd14`

## callees

- `0x180006fc0`

## string_xrefs

- `0x180008609`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180008600  sub     rsp, 48h
0x180008604  mov     rax, [rsp+48h]
0x180008609  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008610  mov     edx, 0E01h
0x180008615  mov     [rsp+48h+var_20], rax
0x18000861a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
