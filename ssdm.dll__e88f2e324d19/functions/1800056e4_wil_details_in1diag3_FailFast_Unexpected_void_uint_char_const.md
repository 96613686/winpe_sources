# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800056e4`
- end: `0x180005700`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `28`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800051cc`
- `0x180007594`
- `0x180008080`
- `0x180008d00`
- `0x18000c9a8`
- `0x18000cd88`
- `0x18000cfd8`
- `0x18000d4a8`
- `0x18000d508`

## callees

- `0x18000353c`

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
0x1800056e4  sub     rsp, 48h
0x1800056e8  mov     rax, [rsp+48h]
0x1800056ed  mov     [rsp+48h+var_18], 8000FFFFh
0x1800056f5  mov     [rsp+48h+var_20], rax
0x1800056fa  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
