# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180010a48`
- end: `0x180010a5c`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f7c`
- `0x18000a204`
- `0x18000a5fc`
- `0x18000e64c`
- `0x18000e7dc`
- `0x180010120`
- `0x180010d18`

## callees

- `0x1800091c0`

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
0x180010a48  sub     rsp, 38h
0x180010a4c  mov     rax, [rsp+38h]
0x180010a51  mov     [rsp+38h+var_10], rax
0x180010a56  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
