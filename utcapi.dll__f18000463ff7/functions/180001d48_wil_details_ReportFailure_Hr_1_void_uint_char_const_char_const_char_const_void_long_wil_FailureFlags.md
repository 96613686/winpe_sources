# wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180001d48`
- end: `0x180001d8d`
- name: `??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002560`

## callees

- `0x180001d3c`
- `0x180002304`

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
0x180001d48  sub     rsp, 68h
0x180001d4c  mov     r8, rcx
0x180001d4f  mov     ecx, 80070057h; this
0x180001d54  mov     [rsp+68h+var_18], ecx
0x180001d58  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180001d5d  mov     [rsp+68h+var_14], eax
0x180001d61  mov     rcx, r8
0x180001d64  lea     rax, [rsp+68h+var_18]
0x180001d69  mov     [rsp+68h+var_10], 0
0x180001d71  mov     [rsp+68h+var_38], rax
0x180001d76  mov     rax, [rsp+68h+arg_28]
0x180001d7e  mov     [rsp+68h+var_40], rax
0x180001d83  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180001d88  add     rsp, 68h
0x180001d8c  retn
```
