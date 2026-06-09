# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x14000c0dc`
- end: `0x14000c0f0`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009794`
- `0x14000aa44`
- `0x14000d028`

## callees

- `0x140001eec`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
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
0x14000c0dc  sub     rsp, 48h
0x14000c0e0  mov     rax, [rsp+48h]
0x14000c0e5  mov     [rsp+48h+var_20], rax
0x14000c0ea  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
