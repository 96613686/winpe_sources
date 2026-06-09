# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180005e98`
- end: `0x180005ebb`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005188`
- `0x18000555c`
- `0x1800084e8`
- `0x180008600`
- `0x1800229b8`
- `0x18002638c`

## callees

- `0x180003ccc`

## string_xrefs

- `0x180005eae`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180005e98  sub     rsp, 48h
0x180005e9c  mov     rax, [rsp+48h]
0x180005ea1  mov     [rsp+48h+var_18], 8000FFFFh
0x180005ea9  mov     [rsp+48h+var_20], rax
0x180005eae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005eb5  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
