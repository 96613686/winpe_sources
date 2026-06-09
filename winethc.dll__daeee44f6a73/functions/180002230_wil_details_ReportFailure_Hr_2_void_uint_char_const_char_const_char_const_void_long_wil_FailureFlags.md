# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180002230`
- end: `0x18000228d`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002138`
- `0x180005a64`
- `0x180005ad4`
- `0x180008b20`
- `0x18000d7e0`

## callees

- `0x180002044`
- `0x180007fbc`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        __int64 a2,
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
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x180002230  sub     rsp, 68h
0x180002234  mov     r10, rcx
0x180002237  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x18000223e  mov     [rsp+68h+var_18], ecx
0x180002242  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002247  mov     [rsp+68h+var_14], eax
0x18000224b  mov     rcx, r10
0x18000224e  mov     [rsp+68h+var_20], 0
0x180002256  lea     rax, [rsp+68h+var_18]
0x18000225b  mov     [rsp+68h+var_38], rax
0x180002260  mov     rax, [rsp+68h+arg_28]
0x180002268  mov     [rsp+68h+var_40], rax
0x18000226d  mov     rax, [rsp+68h+arg_20]
0x180002275  mov     [rsp+68h+var_48], rax
0x18000227a  mov     [rsp+68h+var_10], 0
0x180002282  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180002287  add     rsp, 68h
0x18000228b  retn
```
