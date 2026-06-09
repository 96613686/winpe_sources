# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1800071e4`
- end: `0x1800071f8`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047bc`
- `0x180005144`
- `0x180007594`
- `0x180007a20`
- `0x180007dd8`
- `0x180008080`
- `0x18000845c`
- `0x180008d00`
- `0x18000986c`
- `0x18000c700`
- `0x18000d934`
- `0x18000e070`
- `0x18000e468`

## callees

- `0x1800032d8`

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
0x1800071e4  sub     rsp, 38h
0x1800071e8  mov     rax, [rsp+38h]
0x1800071ed  mov     [rsp+38h+var_10], rax
0x1800071f2  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
