# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18001a630`
- end: `0x18001a69c`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `108`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001afa4`

## callees

- `0x180007b70`
- `0x180007b7c`
- `0x18001a630`

## string_xrefs

- `0x18001a660`: `onecoreuap\net\wcm\service\wcmpolicy\policyutil.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<1,0>(v9, v8, "onecoreuap\\net\\wcm\\service\\wcmpolicy\\policyutil.cpp");
  return v7;
}

```

## disassembly

```asm
0x18001a630  push    rbx
0x18001a632  sub     rsp, 60h
0x18001a636  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18001a63d  mov     r9, rcx
0x18001a640  test    ebx, ebx
0x18001a642  jle     short loc_18001A64D
0x18001a644  movzx   ebx, bx
0x18001a647  or      ebx, 80070000h
0x18001a64d  mov     ecx, ebx; this
0x18001a64f  mov     [rsp+68h+var_18], ebx
0x18001a653  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a658  mov     rcx, [rsp+68h+arg_28]
0x18001a660  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\wcmpolic"...
0x18001a667  mov     [rsp+68h+var_14], eax
0x18001a66b  lea     rax, [rsp+68h+var_18]
0x18001a670  mov     [rsp+68h+var_30], 0
0x18001a679  mov     [rsp+68h+var_38], rax
0x18001a67e  mov     [rsp+68h+var_40], rcx
0x18001a683  mov     rcx, r9
0x18001a686  mov     [rsp+68h+var_10], 0
0x18001a68e  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001a693  mov     eax, ebx
0x18001a695  add     rsp, 60h
0x18001a699  pop     rbx
0x18001a69a  retn
```
