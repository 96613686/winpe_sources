# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180018d58`
- end: `0x180018d7d`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180018734`

## callees

- `0x18000b5fc`

## string_xrefs

- `0x180018d6b`: `onecoreuap\net\wcm\service\wcmpolicy\wcmconnectionmappingpolicykey.cpp`

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
    72,
    (unsigned int)"onecoreuap\\net\\wcm\\service\\wcmpolicy\\wcmconnectionmappingpolicykey.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180018d58  sub     rsp, 48h
0x180018d5c  mov     rax, [rsp+48h]
0x180018d61  mov     [rsp+48h+var_18], r9d
0x180018d66  mov     [rsp+48h+var_20], rax
0x180018d6b  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\service\\wcmpolic"...
0x180018d72  mov     edx, 48h ; 'H'
0x180018d77  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
