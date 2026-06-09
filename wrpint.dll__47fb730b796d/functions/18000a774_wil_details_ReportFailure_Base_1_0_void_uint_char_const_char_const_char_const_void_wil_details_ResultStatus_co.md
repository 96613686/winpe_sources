# wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a774`
- end: `0x18000a779`
- name: `??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `5`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a87c`
- `0x18000a924`
- `0x18000b058`
- `0x180013814`

## callees

- `0x18000ac9c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall wil::details::ReportFailure_Base<1,0>(int a1, int a2, int a3, int a4, int a5, __int64 a6, int a7)
{
  return wil::details::ReportFailure_Return<1>(a1, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x18000a774  jmp     ??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
