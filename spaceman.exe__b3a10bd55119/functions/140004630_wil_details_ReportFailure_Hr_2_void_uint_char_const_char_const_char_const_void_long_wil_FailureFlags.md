# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140004630`
- end: `0x14000468c`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004540`
- `0x140006af0`
- `0x140006b58`
- `0x140007190`

## callees

- `0x140004444`
- `0x140006fcc`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x140004630  sub     rsp, 68h
0x140004634  mov     r10, rcx
0x140004637  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x14000463e  mov     [rsp+68h+var_18], ecx
0x140004642  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004647  mov     [rsp+68h+var_14], eax
0x14000464b  mov     rcx, r10
0x14000464e  mov     [rsp+68h+var_20], 0
0x140004656  lea     rax, [rsp+68h+var_18]
0x14000465b  mov     [rsp+68h+var_38], rax
0x140004660  mov     rax, [rsp+68h+arg_28]
0x140004668  mov     [rsp+68h+var_40], rax
0x14000466d  mov     rax, [rsp+68h+arg_20]
0x140004675  mov     [rsp+68h+var_48], rax
0x14000467a  mov     [rsp+68h+var_10], 0
0x140004682  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140004687  add     rsp, 68h
0x14000468b  retn
```
