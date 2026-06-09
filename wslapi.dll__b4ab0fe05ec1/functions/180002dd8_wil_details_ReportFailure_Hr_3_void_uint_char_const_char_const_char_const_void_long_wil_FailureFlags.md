# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180002dd8`
- end: `0x180002e24`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `76`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003960`
- `0x180006b80`
- `0x1800089f8`
- `0x180008a24`

## callees

- `0x180002bec`
- `0x180004374`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // [rsp+20h] [rbp-48h]
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v11[0] = (_DWORD)a7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v11[2] = 0;
  wil::details::ReportFailure_Base<3,0>(v9, v7, v8, v9, v10, a6, (__int64)v11, 0);
}

```

## disassembly

```asm
0x180002dd8  sub     rsp, 68h
0x180002ddc  mov     r9, rcx
0x180002ddf  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180002de6  mov     [rsp+68h+var_18], ecx
0x180002dea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002def  mov     [rsp+68h+var_14], eax
0x180002df3  mov     rcx, r9
0x180002df6  lea     rax, [rsp+68h+var_18]
0x180002dfb  mov     [rsp+68h+var_30], 0
0x180002e04  mov     [rsp+68h+var_38], rax
0x180002e09  mov     rax, [rsp+68h+arg_28]
0x180002e11  mov     [rsp+68h+var_40], rax
0x180002e16  mov     [rsp+68h+var_10], 0
0x180002e1e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
