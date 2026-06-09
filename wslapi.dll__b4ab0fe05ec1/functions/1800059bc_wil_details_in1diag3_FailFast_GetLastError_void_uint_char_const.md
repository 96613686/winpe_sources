# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800059bc`
- end: `0x1800059d0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037f4`
- `0x180004dd8`
- `0x1800066dc`
- `0x18000677c`
- `0x180006d64`
- `0x180006e08`
- `0x180006ea0`
- `0x1800077a4`
- `0x180007850`
- `0x1800089a0`

## callees

- `0x180002c24`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1800059bc  sub     rsp, 38h
0x1800059c0  mov     rax, [rsp+38h]
0x1800059c5  mov     [rsp+38h+var_10], rax
0x1800059ca  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
