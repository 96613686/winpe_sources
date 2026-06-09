# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1400041a0`
- end: `0x1400041bd`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `29`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bd0`
- `0x14000536c`

## callees

- `0x140003094`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1400041a0  sub     rsp, 58h
0x1400041a4  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400041ad  mov     rax, [rsp+58h]
0x1400041b2  mov     [rsp+58h+var_30], rax
0x1400041b7  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
