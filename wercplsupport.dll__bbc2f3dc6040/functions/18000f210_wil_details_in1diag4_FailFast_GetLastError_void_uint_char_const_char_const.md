# wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)

- ea: `0x18000f210`
- end: `0x18000f224`
- name: `?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009078`
- `0x180009618`
- `0x180009b78`
- `0x180009f58`
- `0x18000a410`
- `0x18000a7fc`
- `0x18000d660`
- `0x18000d784`
- `0x18000e098`

## callees

- `0x1800086c0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag4::_FailFast_GetLastError(
        wil::details::in1diag4 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5)
{
  int v5; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v5, retaddr);
}

```

## disassembly

```asm
0x18000f210  sub     rsp, 38h
0x18000f214  mov     rax, [rsp+38h]
0x18000f219  mov     [rsp+38h+var_10], rax
0x18000f21e  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
