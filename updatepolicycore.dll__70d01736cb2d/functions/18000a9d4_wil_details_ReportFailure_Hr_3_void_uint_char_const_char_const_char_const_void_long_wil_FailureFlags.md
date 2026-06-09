# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x18000a9d4`
- end: `0x18000aa31`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab20`
- `0x180019ef4`

## callees

- `0x180009490`
- `0x18000a99c`

## string_xrefs

- `0x18000a9f6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x18000a9d4  sub     rsp, 78h
0x18000a9d8  mov     r10, rcx
0x18000a9db  mov     r9d, edx
0x18000a9de  mov     edx, 8000FFFFh
0x18000a9e3  lea     rcx, [rsp+78h+var_18]
0x18000a9e8  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000a9ed  mov     [rsp+78h+var_40], 0
0x18000a9f6  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000a9fd  mov     edx, r9d
0x18000aa00  mov     rcx, r10
0x18000aa03  movsd   xmm0, qword ptr [rax]
0x18000aa07  mov     eax, [rax+8]
0x18000aa0a  mov     [rsp+78h+var_20], eax
0x18000aa0e  lea     rax, [rsp+78h+var_28]
0x18000aa13  mov     [rsp+78h+var_48], rax
0x18000aa18  mov     rax, [rsp+78h+arg_28]
0x18000aa20  mov     [rsp+78h+var_50], rax
0x18000aa25  movsd   [rsp+78h+var_28], xmm0
0x18000aa2b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
