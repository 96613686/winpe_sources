# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180006814`
- end: `0x18000686c`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z`
- size: `88`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006708`
- `0x18000949c`
- `0x180009508`
- `0x18000a414`

## callees

- `0x180006618`
- `0x180009b0c`

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
0x180006814  sub     rsp, 68h
0x180006818  mov     r11, rcx
0x18000681b  mov     r10d, edx
0x18000681e  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180006825  mov     [rsp+68h+var_18], ecx
0x180006829  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000682e  and     [rsp+68h+var_10], 0
0x180006833  mov     edx, r10d
0x180006836  mov     [rsp+68h+var_14], eax
0x18000683a  mov     rcx, r11
0x18000683d  lea     rax, [rsp+68h+var_18]
0x180006842  mov     [rsp+68h+var_38], rax
0x180006847  mov     rax, [rsp+68h+arg_28]
0x18000684f  mov     [rsp+68h+var_40], rax
0x180006854  mov     rax, [rsp+68h+arg_20]
0x18000685c  mov     [rsp+68h+var_48], rax
0x180006861  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
0x180006866  add     rsp, 68h
0x18000686a  retn
```
