# wil::details::in1diag4::FailFast_Unexpected(void *,uint,char const *,char const *)

- ea: `0x18000aaf0`
- end: `0x18000ab17`
- name: `?FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z`
- size: `39`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009b78`
- `0x180009f58`
- `0x18000d660`
- `0x18000d784`

## callees

- `0x1800088a0`

## string_xrefs

- `0x18000ab00`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag4::FailFast_Unexpected(
        wil::details::in1diag4 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (unsigned int)"wil::mutex_t<class wil::details::unique_storage<struct wil::details::resource_policy<void *,void (__cd"
                  "ecl*)(void *) noexcept,&void __cdecl wil::details::CloseHandle(void *),struct wistd::integral_constant"
                  "<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,struct wil::err_returncode_policy>::acquire");
}

```

## disassembly

```asm
0x18000aaf0  sub     rsp, 48h
0x18000aaf4  mov     rax, [rsp+48h]
0x18000aaf9  lea     r9, aWilMutexTClass; "wil::mutex_t<class wil::details::unique"...
0x18000ab00  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ab07  mov     [rsp+48h+var_20], rax
0x18000ab0c  mov     edx, 0E01h
0x18000ab11  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
