# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x18001cab4`
- end: `0x18001cadc`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eab0`

## callees

- `0x18001b868`

## string_xrefs

- `0x18001cabd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = -2147024882;
  wil::details::ReportFailure_Hr<0>(
    (int)this,
    4088,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (int)a4,
    v4,
    retaddr,
    v5);
}

```

## disassembly

```asm
0x18001cab4  sub     rsp, 48h
0x18001cab8  mov     rax, [rsp+48h]
0x18001cabd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001cac4  mov     dword ptr [rsp+48h+var_18], 8007000Eh; wil::details *
0x18001cacc  mov     edx, 0FF8h; int
0x18001cad1  mov     [rsp+48h+var_20], rax; __int64
0x18001cad6  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
