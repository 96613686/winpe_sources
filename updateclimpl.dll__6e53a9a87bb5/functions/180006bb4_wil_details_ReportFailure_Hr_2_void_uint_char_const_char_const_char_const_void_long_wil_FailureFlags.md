# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180006bb4`
- end: `0x180006c0f`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f18`
- `0x180004f80`
- `0x180005a50`
- `0x180006fe0`
- `0x18000cf08`

## callees

- `0x180004d50`
- `0x180006ca0`

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
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x180006bb4  sub     rsp, 68h
0x180006bb8  mov     r10, rcx
0x180006bbb  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180006bc2  mov     [rsp+68h+var_18], ecx
0x180006bc6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006bcb  mov     [rsp+68h+var_14], eax
0x180006bcf  mov     rcx, r10
0x180006bd2  xor     eax, eax
0x180006bd4  mov     [rsp+68h+var_20], eax
0x180006bd8  mov     [rsp+68h+var_30], rax
0x180006bdd  mov     [rsp+68h+var_10], eax
0x180006be1  lea     rax, [rsp+68h+var_18]
0x180006be6  mov     [rsp+68h+var_38], rax
0x180006beb  mov     rax, [rsp+68h+arg_28]
0x180006bf3  mov     [rsp+68h+var_40], rax
0x180006bf8  mov     rax, [rsp+68h+arg_20]
0x180006c00  mov     [rsp+68h+var_48], rax
0x180006c05  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180006c0a  add     rsp, 68h
0x180006c0e  retn
```
