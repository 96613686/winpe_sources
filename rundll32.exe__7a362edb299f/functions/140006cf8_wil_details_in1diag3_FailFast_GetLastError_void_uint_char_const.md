# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x140006cf8`
- end: `0x140006d0c`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000388c`
- `0x140003b94`
- `0x140003ffc`
- `0x140004384`
- `0x140005d3c`
- `0x1400064cc`
- `0x140008480`
- `0x14000897c`
- `0x14000a168`

## callees

- `0x140002fac`

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
0x140006cf8  sub     rsp, 38h
0x140006cfc  mov     rax, [rsp+38h]
0x140006d01  mov     [rsp+38h+var_10], rax
0x140006d06  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
