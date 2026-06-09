# wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180001d50`
- end: `0x180001d96`
- name: `??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002590`

## callees

- `0x180001d44`
- `0x18000232c`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<1>()
{
  __int64 v0; // r8

  wil::details::HrToNtStatus((wil::details *)0x80070057LL);
  return wil::details::ReportFailure_Base<1,0>(v0);
}

```

## disassembly

```asm
0x180001d50  sub     rsp, 68h
0x180001d54  mov     r8, rcx
0x180001d57  mov     ecx, 80070057h; this
0x180001d5c  mov     [rsp+68h+var_18], ecx
0x180001d60  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180001d65  mov     [rsp+68h+var_14], eax
0x180001d69  mov     rcx, r8
0x180001d6c  lea     rax, [rsp+68h+var_18]
0x180001d71  mov     [rsp+68h+var_10], 0
0x180001d79  mov     [rsp+68h+var_38], rax
0x180001d7e  mov     rax, [rsp+68h+arg_28]
0x180001d86  mov     [rsp+68h+var_40], rax
0x180001d8b  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180001d90  add     rsp, 68h
0x180001d94  retn
```
