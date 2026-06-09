# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x18000883c`
- end: `0x180008898`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008740`
- `0x18000b674`
- `0x18000b6d4`
- `0x18000bdfc`

## callees

- `0x180008644`
- `0x18000ba88`

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
0x18000883c  sub     rsp, 68h
0x180008840  mov     r10, rcx
0x180008843  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x18000884a  mov     [rsp+68h+var_18], ecx
0x18000884e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008853  mov     [rsp+68h+var_14], eax
0x180008857  mov     rcx, r10
0x18000885a  mov     [rsp+68h+var_20], 0
0x180008862  lea     rax, [rsp+68h+var_18]
0x180008867  mov     [rsp+68h+var_38], rax
0x18000886c  mov     rax, [rsp+68h+arg_28]
0x180008874  mov     [rsp+68h+var_40], rax
0x180008879  mov     rax, [rsp+68h+arg_20]
0x180008881  mov     [rsp+68h+var_48], rax
0x180008886  mov     [rsp+68h+var_10], 0
0x18000888e  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180008893  add     rsp, 68h
0x180008897  retn
```
