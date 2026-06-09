# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800088b4`
- end: `0x1800088d4`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000794c`
- `0x180007d44`
- `0x18000c490`
- `0x18000c620`

## callees

- `0x180006874`

## string_xrefs

- `0x1800088bd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800088b4  sub     rsp, 48h
0x1800088b8  mov     rax, [rsp+48h]
0x1800088bd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800088c4  mov     edx, 0C27h
0x1800088c9  mov     [rsp+48h+var_20], rax
0x1800088ce  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long)
```
