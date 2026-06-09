# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180027d38`
- end: `0x180027dad`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180028558`

## callees

- `0x180003a58`
- `0x180006c4c`
- `0x180027d38`

## string_xrefs

- `0x180027d6a`: `onecoreuap\net\tethering\service\userutils.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // r10d
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, 0);
  v11[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v9,
    30,
    (unsigned int)"onecoreuap\\net\\tethering\\service\\userutils.cpp",
    0,
    v8,
    a6,
    (__int64)v11,
    v8);
  return v7;
}

```

## disassembly

```asm
0x180027d38  push    rbx
0x180027d3a  sub     rsp, 60h
0x180027d3e  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180027d45  xor     edx, edx; int
0x180027d47  mov     r10, rcx
0x180027d4a  test    ebx, ebx
0x180027d4c  jle     short loc_180027D57
0x180027d4e  movzx   ebx, bx
0x180027d51  or      ebx, 80070000h
0x180027d57  mov     ecx, ebx; this
0x180027d59  mov     [rsp+68h+var_18], ebx
0x180027d5d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027d62  mov     rcx, [rsp+68h+arg_28]
0x180027d6a  lea     r8, aOnecoreuapNetT_1; "onecoreuap\\net\\tethering\\service\\us"...
0x180027d71  mov     [rsp+68h+var_20], edx
0x180027d75  xor     r9d, r9d
0x180027d78  mov     [rsp+68h+var_30], rdx
0x180027d7d  mov     [rsp+68h+var_14], eax
0x180027d81  lea     rax, [rsp+68h+var_18]
0x180027d86  mov     [rsp+68h+var_38], rax
0x180027d8b  mov     [rsp+68h+var_40], rcx
0x180027d90  mov     rcx, r10
0x180027d93  mov     [rsp+68h+var_48], rdx
0x180027d98  mov     [rsp+68h+var_10], edx
0x180027d9c  lea     edx, [r9+1Eh]
0x180027da0  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180027da5  mov     eax, ebx
0x180027da7  add     rsp, 60h
0x180027dab  pop     rbx
0x180027dac  retn
```
