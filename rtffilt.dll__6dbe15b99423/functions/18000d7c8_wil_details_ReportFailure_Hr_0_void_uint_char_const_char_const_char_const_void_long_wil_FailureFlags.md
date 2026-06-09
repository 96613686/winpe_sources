# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x18000d7c8`
- end: `0x18000d81e`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dabc`

## callees

- `0x180002e90`
- `0x1800062f8`

## string_xrefs

- `0x18000d7e3`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v9, a7);
  wil::details::ReportFailure_Base<0,0>(
    v8,
    v7,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
    v7);
}

```

## disassembly

```asm
0x18000d7c8  sub     rsp, 78h
0x18000d7cc  mov     r10, rcx
0x18000d7cf  mov     r9d, edx
0x18000d7d2  mov     edx, [rsp+78h+arg_30]
0x18000d7d9  lea     rcx, [rsp+78h+var_18]
0x18000d7de  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18000d7e3  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000d7ea  mov     edx, r9d
0x18000d7ed  mov     rcx, r10
0x18000d7f0  movsd   xmm0, qword ptr [rax]
0x18000d7f4  mov     eax, [rax+8]
0x18000d7f7  mov     [rsp+78h+var_20], eax
0x18000d7fb  lea     rax, [rsp+78h+var_28]
0x18000d800  mov     [rsp+78h+var_48], rax
0x18000d805  mov     rax, [rsp+78h+arg_28]
0x18000d80d  mov     [rsp+78h+var_50], rax
0x18000d812  movsd   [rsp+78h+var_28], xmm0
0x18000d818  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
