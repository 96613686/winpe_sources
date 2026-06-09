# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180003428`
- end: `0x18000347d`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004390`
- `0x180007774`
- `0x1800077a0`

## callees

- `0x1800031b0`
- `0x180004448`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  int v9; // r11d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v10, a7, a3, a3);
  wil::details::ReportFailure_Base<3,0>(v9, v8, v7, v7);
}

```

## disassembly

```asm
0x180003428  sub     rsp, 78h
0x18000342c  mov     r11, rcx
0x18000342f  mov     r10d, edx
0x180003432  mov     edx, [rsp+78h+arg_30]
0x180003439  lea     rcx, [rsp+78h+var_18]
0x18000343e  mov     r9, r8
0x180003441  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180003446  mov     r8, r9
0x180003449  mov     edx, r10d
0x18000344c  mov     rcx, r11
0x18000344f  movsd   xmm0, qword ptr [rax]
0x180003453  mov     eax, [rax+8]
0x180003456  mov     [rsp+78h+var_20], eax
0x18000345a  lea     rax, [rsp+78h+var_28]
0x18000345f  mov     [rsp+78h+var_48], rax
0x180003464  mov     rax, [rsp+78h+arg_28]
0x18000346c  mov     [rsp+78h+var_50], rax
0x180003471  movsd   [rsp+78h+var_28], xmm0
0x180003477  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
