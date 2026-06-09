# wil::details::ReportFailure_NtStatus<3>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x1800238f8`
- end: `0x18002395b`
- name: `??$ReportFailure_NtStatus@$02@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800286dc`

## callees

- `0x180004ec8`
- `0x1800258dc`

## string_xrefs

- `0x180023921`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NtStatus<3>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v9; // r9d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromStatus(v10, a7);
  wil::details::ReportFailure_Base<3,0>(
    a1,
    a2,
    (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
    v9);
}

```

## disassembly

```asm
0x1800238f8  mov     [rsp+arg_0], rbx
0x1800238fd  push    rdi
0x1800238fe  sub     rsp, 70h
0x180023902  mov     ebx, edx
0x180023904  mov     rdi, rcx
0x180023907  mov     edx, [rsp+78h+arg_30]
0x18002390e  lea     rcx, [rsp+78h+var_18]
0x180023913  call    ?FromStatus@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromStatus(long)
0x180023918  mov     [rsp+78h+var_40], 0
0x180023921  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180023928  mov     edx, ebx
0x18002392a  mov     rcx, rdi
0x18002392d  movsd   xmm0, qword ptr [rax]
0x180023931  mov     eax, [rax+8]
0x180023934  mov     [rsp+78h+var_20], eax
0x180023938  lea     rax, [rsp+78h+var_28]
0x18002393d  mov     [rsp+78h+var_48], rax
0x180023942  mov     rax, [rsp+78h+arg_28]
0x18002394a  mov     [rsp+78h+var_50], rax
0x18002394f  movsd   [rsp+78h+var_28], xmm0
0x180023955  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
