# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180005a1c`
- end: `0x180005a35`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003128`
- `0x180003b40`
- `0x180003c70`
- `0x180003d20`
- `0x180003dd0`
- `0x180003e70`
- `0x180003f20`
- `0x180003fd0`
- `0x180004080`
- `0x1800043f8`
- `0x18000448c`

## callees

- `0x180007764`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180005a1c  sub     rsp, 48h
0x180005a20  mov     rax, [rsp+48h]
0x180005a25  mov     [rsp+48h+var_18], r9d
0x180005a2a  mov     [rsp+48h+var_20], rax
0x180005a2f  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
