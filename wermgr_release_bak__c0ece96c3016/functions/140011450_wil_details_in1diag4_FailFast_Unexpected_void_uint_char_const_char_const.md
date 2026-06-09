# wil::details::in1diag4::FailFast_Unexpected(void *,uint,char const *,char const *)

- ea: `0x140011450`
- end: `0x140011477`
- name: `?FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z`
- size: `39`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140010778`
- `0x140010b80`
- `0x140013124`
- `0x140013248`

## callees

- `0x14000fa34`

## string_xrefs

- `0x140011465`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140011450  sub     rsp, 48h
0x140011454  mov     rax, [rsp+48h]
0x140011459  mov     [rsp+48h+var_20], rax
0x14001145e  lea     r9, aWilMutexTClass; "wil::mutex_t<class wil::details::unique"...
0x140011465  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001146c  mov     edx, 0E01h
0x140011471  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
