# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000fa7c`
- end: `0x18000fade`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013bbc`

## callees

- `0x180003a4c`
- `0x180006c4c`
- `0x18000fa7c`

## string_xrefs

- `0x18000faac`: `onecoreuap\net\tethering\service\interfacemgr.cpp`

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
  wil::details::ReportFailure_Base<1,0>(v9, v8, "onecoreuap\\net\\tethering\\service\\interfacemgr.cpp");
  return v7;
}

```

## disassembly

```asm
0x18000fa7c  push    rbx
0x18000fa7e  sub     rsp, 60h
0x18000fa82  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000fa89  mov     r9, rcx
0x18000fa8c  test    ebx, ebx
0x18000fa8e  jle     short loc_18000FA99
0x18000fa90  movzx   ebx, bx
0x18000fa93  or      ebx, 80070000h
0x18000fa99  mov     ecx, ebx; this
0x18000fa9b  mov     [rsp+68h+var_18], ebx
0x18000fa9f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000faa4  mov     rcx, [rsp+68h+arg_28]
0x18000faac  lea     r8, aOnecoreuapNetT_0; "onecoreuap\\net\\tethering\\service\\in"...
0x18000fab3  mov     [rsp+68h+var_14], eax
0x18000fab7  lea     rax, [rsp+68h+var_18]
0x18000fabc  mov     [rsp+68h+var_38], rax
0x18000fac1  mov     [rsp+68h+var_40], rcx
0x18000fac6  mov     rcx, r9
0x18000fac9  mov     [rsp+68h+var_10], 0
0x18000fad1  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000fad6  mov     eax, ebx
0x18000fad8  add     rsp, 60h
0x18000fadc  pop     rbx
0x18000fadd  retn
```
