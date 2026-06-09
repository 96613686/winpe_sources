# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x1800089f8`
- end: `0x180008a1d`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008944`

## callees

- `0x180002dd8`

## string_xrefs

- `0x180008a0b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    5324,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (__int64)a4,
    v5,
    retaddr,
    v6);
}

```

## disassembly

```asm
0x1800089f8  sub     rsp, 48h
0x1800089fc  mov     rax, [rsp+48h]
0x180008a01  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180008a06  mov     [rsp+48h+var_20], rax; __int64
0x180008a0b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008a12  mov     edx, 14CCh; int
0x180008a17  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
