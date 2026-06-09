# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x180005d08`
- end: `0x180005d28`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b34`
- `0x180003f2c`
- `0x180009638`
- `0x1800097c8`

## callees

- `0x180002aec`

## string_xrefs

- `0x180005d11`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    3111,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180005d08  sub     rsp, 48h
0x180005d0c  mov     rax, [rsp+48h]
0x180005d11  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005d18  mov     edx, 0C27h
0x180005d1d  mov     [rsp+48h+var_20], rax
0x180005d22  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long)
```
