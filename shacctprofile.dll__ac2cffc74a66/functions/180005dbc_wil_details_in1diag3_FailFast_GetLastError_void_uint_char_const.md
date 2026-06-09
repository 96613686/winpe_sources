# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180005dbc`
- end: `0x180005dd0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a80`
- `0x180003bd0`
- `0x180003f74`
- `0x1800053dc`
- `0x1800059f4`

## callees

- `0x18000322c`

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
0x180005dbc  sub     rsp, 38h
0x180005dc0  mov     rax, [rsp+38h]
0x180005dc5  mov     [rsp+38h+var_10], rax
0x180005dca  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
