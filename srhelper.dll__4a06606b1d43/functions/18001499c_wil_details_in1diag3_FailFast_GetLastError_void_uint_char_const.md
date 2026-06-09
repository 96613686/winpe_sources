# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x18001499c`
- end: `0x1800149b0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180010144`
- `0x180010210`
- `0x18001078c`
- `0x180010b30`
- `0x180010f00`
- `0x180011130`
- `0x18001383c`
- `0x180013950`
- `0x1800141ac`

## callees

- `0x18000f820`

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
0x18001499c  sub     rsp, 38h
0x1800149a0  mov     rax, [rsp+38h]
0x1800149a5  mov     [rsp+38h+var_10], rax
0x1800149aa  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
