# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180009d78`
- end: `0x180009d9d`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006a10`
- `0x180009e30`

## callees

- `0x180007394`

## string_xrefs

- `0x180009d8b`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    55,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180009d78  sub     rsp, 48h
0x180009d7c  mov     rax, [rsp+48h]
0x180009d81  mov     [rsp+48h+var_18], r9d
0x180009d86  mov     [rsp+48h+var_20], rax
0x180009d8b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180009d92  mov     edx, 37h ; '7'
0x180009d97  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
