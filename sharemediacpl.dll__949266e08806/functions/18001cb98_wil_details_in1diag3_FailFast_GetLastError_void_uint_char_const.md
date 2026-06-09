# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18001cb98`
- end: `0x18001cbac`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001998c`
- `0x180019cb8`
- `0x18001a05c`
- `0x18001be68`
- `0x18001c66c`

## callees

- `0x180018fd0`

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
0x18001cb98  sub     rsp, 38h
0x18001cb9c  mov     rax, [rsp+38h]
0x18001cba1  mov     [rsp+38h+var_10], rax
0x18001cba6  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
