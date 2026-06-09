# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800077a0`
- end: `0x1800077c8`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012b0`

## callees

- `0x180003428`

## string_xrefs

- `0x1800077b6`: `onecore\vm\dv\vmbus\pipes\dll\server.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    81,
    (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\server.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800077a0  sub     rsp, 48h
0x1800077a4  mov     rax, [rsp+48h]
0x1800077a9  mov     [rsp+48h+var_18], 8000FFFFh
0x1800077b1  mov     [rsp+48h+var_20], rax
0x1800077b6  lea     r8, aOnecoreVmDvVmb_0; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\ser"...
0x1800077bd  mov     edx, 51h ; 'Q'
0x1800077c2  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
