# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180008d18`
- end: `0x180008d2c`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003608`
- `0x1800036d4`
- `0x180003e4c`
- `0x1800041f0`
- `0x180004830`
- `0x180004a60`
- `0x1800078bc`
- `0x1800079d0`
- `0x180008434`

## callees

- `0x180002ce4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x180008d18  sub     rsp, 38h
0x180008d1c  mov     rax, [rsp+38h]
0x180008d21  mov     [rsp+38h+var_10], rax
0x180008d26  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
