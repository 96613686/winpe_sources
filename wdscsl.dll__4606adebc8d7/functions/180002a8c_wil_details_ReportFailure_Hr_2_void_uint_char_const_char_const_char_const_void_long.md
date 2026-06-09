# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180002a8c`
- end: `0x180002ae4`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z`
- size: `88`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002980`
- `0x18000659c`
- `0x180006608`
- `0x18000796c`

## callees

- `0x180002890`
- `0x180006bdc`

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
  int v7; // r8d
  int v8; // r9d
  int v9; // r10d
  int v10; // r11d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[2] = 0;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  return wil::details::ReportFailure_Base<2,0>(v10, v9, v7, v8, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x180002a8c  sub     rsp, 68h
0x180002a90  mov     r11, rcx
0x180002a93  mov     r10d, edx
0x180002a96  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180002a9d  mov     [rsp+68h+var_18], ecx
0x180002aa1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002aa6  and     [rsp+68h+var_10], 0
0x180002aab  mov     edx, r10d
0x180002aae  mov     [rsp+68h+var_14], eax
0x180002ab2  mov     rcx, r11
0x180002ab5  lea     rax, [rsp+68h+var_18]
0x180002aba  mov     [rsp+68h+var_38], rax
0x180002abf  mov     rax, [rsp+68h+arg_28]
0x180002ac7  mov     [rsp+68h+var_40], rax
0x180002acc  mov     rax, [rsp+68h+arg_20]
0x180002ad4  mov     [rsp+68h+var_48], rax
0x180002ad9  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
0x180002ade  add     rsp, 68h
0x180002ae2  retn
```
