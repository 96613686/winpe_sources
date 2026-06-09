# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x140006e3c`
- end: `0x140006e59`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `29`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003928`
- `0x140003bd0`
- `0x140003f74`
- `0x14000536c`
- `0x14000697c`

## callees

- `0x140002ec0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  char *retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>(this, a2, a3, a4, v4, retaddr);
}

```

## disassembly

```asm
0x140006e3c  sub     rsp, 48h
0x140006e40  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x140006e49  mov     rax, [rsp+48h]
0x140006e4e  mov     [rsp+48h+var_20], rax
0x140006e53  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
