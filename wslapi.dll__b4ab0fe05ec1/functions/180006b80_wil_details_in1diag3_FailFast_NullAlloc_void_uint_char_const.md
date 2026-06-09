# wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)

- ea: `0x180006b80`
- end: `0x180006b9c`
- name: `?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `28`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800066dc`
- `0x18000677c`
- `0x180006d64`
- `0x180006e08`
- `0x180006ea0`
- `0x1800077a4`
- `0x180007850`
- `0x180008a48`
- `0x1800090f0`
- `0x1800093ec`

## callees

- `0x180002dd8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = -2147024882;
  wil::details::ReportFailure_Hr<3>((__int64)this, (int)a2, a3, (__int64)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180006b80  sub     rsp, 48h
0x180006b84  mov     rax, [rsp+48h]
0x180006b89  mov     dword ptr [rsp+48h+var_18], 8007000Eh; wil::details *
0x180006b91  mov     [rsp+48h+var_20], rax; __int64
0x180006b96  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
