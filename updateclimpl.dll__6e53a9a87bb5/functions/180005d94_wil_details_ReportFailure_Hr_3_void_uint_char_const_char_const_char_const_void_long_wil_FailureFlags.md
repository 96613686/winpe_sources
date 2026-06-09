# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180005d94`
- end: `0x180005df1`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ee0`
- `0x18000b6b4`

## callees

- `0x1800049e0`
- `0x180005d5c`

## string_xrefs

- `0x180005db6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  int v7; // r10d
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, 2147549183LL);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x180005d94  sub     rsp, 78h
0x180005d98  mov     r10, rcx
0x180005d9b  mov     r9d, edx
0x180005d9e  mov     edx, 8000FFFFh
0x180005da3  lea     rcx, [rsp+78h+var_18]
0x180005da8  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180005dad  mov     [rsp+78h+var_40], 0
0x180005db6  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180005dbd  mov     edx, r9d
0x180005dc0  mov     rcx, r10
0x180005dc3  movsd   xmm0, qword ptr [rax]
0x180005dc7  mov     eax, [rax+8]
0x180005dca  mov     [rsp+78h+var_20], eax
0x180005dce  lea     rax, [rsp+78h+var_28]
0x180005dd3  mov     [rsp+78h+var_48], rax
0x180005dd8  mov     rax, [rsp+78h+arg_28]
0x180005de0  mov     [rsp+78h+var_50], rax
0x180005de5  movsd   [rsp+78h+var_28], xmm0
0x180005deb  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
