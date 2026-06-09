# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180006fdc`
- end: `0x180007130`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `340`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180008a70`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x180004614`
- `0x180004668`
- `0x1800056d0`
- `0x180006fdc`
- `0x1800265e0`
- `0x180029010`

## string_xrefs

- `0x18000709e`: `pcshell\base\whesvc\dll\whesvc.cpp`
- `0x180007101`: `pcshell\base\whesvc\dll\whesvc.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  __int64 v9; // rcx
  unsigned __int64 *v10; // rax
  __m128i v11; // xmm0
  int v12; // r14d
  int v14; // r9d
  _BYTE v15[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v19[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v19, 0, sizeof(v19));
  v15[0] = 0;
  v9 = -1;
  do
    ++v9;
  while ( v19[v9] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v10 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v18, &v19[v9], 2048 - v9, v15),
        v11 = (__m128i)*v10,
        LODWORD(v10) = *((_DWORD *)v10 + 2),
        v12 = _mm_cvtsi128_si32(v11),
        v16 = v11.m128i_i64[0],
        v17 = (int)v10,
        v12 >= 0) )
  {
    LODWORD(v16) = -2147024322;
    HIDWORD(v16) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v8);
    v17 = 0;
    wil::details::ReportFailure_Base<3,0>(a1, a2, (unsigned int)"pcshell\\base\\whesvc\\dll\\whesvc.cpp", v14);
  }
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"pcshell\\base\\whesvc\\dll\\whesvc.cpp",
    0,
    0,
    a6,
    (__int64)&v16,
    (__int64)v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006fdc  mov     [rsp-8+arg_10], rbx
0x180006fe1  push    rbp
0x180006fe2  push    rsi
0x180006fe3  push    rdi
0x180006fe4  push    r14
0x180006fe6  push    r15
0x180006fe8  lea     rbp, [rsp-0F90h]
0x180006ff0  mov     eax, 1090h
0x180006ff5  call    _alloca_probe
0x180006ffa  sub     rsp, rax
0x180006ffd  mov     rax, cs:__security_cookie
0x180007004  xor     rax, rsp
0x180007007  mov     [rbp+0FB0h+var_30], rax
0x18000700e  mov     rsi, [rbp+0FB0h+arg_28]
0x180007015  mov     edi, edx
0x180007017  mov     rbx, rcx
0x18000701a  xor     edx, edx; Val
0x18000701c  lea     rcx, [rbp+0FB0h+var_1030]; void *
0x180007020  mov     r8d, 1000h; Size
0x180007026  call    memset_0
0x18000702b  xor     r15d, r15d
0x18000702e  lea     rax, [rbp+0FB0h+var_1030]
0x180007032  mov     [rsp+10B0h+var_1060], r15b
0x180007037  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000703b  inc     rcx
0x18000703e  cmp     [rax+rcx*2], r15w
0x180007043  jnz     short loc_18000703B
0x180007045  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000704c  test    rax, rax
0x18000704f  jz      loc_1800070EF
0x180007055  mov     r8d, 800h
0x18000705b  lea     rdx, [rbp+0FB0h+var_1030]
0x18000705f  sub     r8, rcx
0x180007062  lea     rdx, [rdx+rcx*2]
0x180007066  lea     rcx, [rsp+10B0h+var_1048]
0x18000706b  lea     r9, [rsp+10B0h+var_1060]
0x180007070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007075  movsd   xmm0, qword ptr [rax]
0x180007079  mov     eax, [rax+8]
0x18000707c  movd    r14d, xmm0
0x180007081  movsd   [rsp+10B0h+var_1058], xmm0
0x180007087  mov     [rsp+10B0h+var_1050], eax
0x18000708b  test    r14d, r14d
0x18000708e  jns     short loc_1800070EF
0x180007090  mov     [rsp+10B0h+var_1068], r15d
0x180007095  lea     rax, [rbp+0FB0h+var_1030]
0x180007099  mov     [rsp+10B0h+var_1078], rax
0x18000709e  lea     r8, aPcshellBaseWhe_4; "pcshell\\base\\whesvc\\dll\\whesvc.cpp"
0x1800070a5  lea     rax, [rsp+10B0h+var_1058]
0x1800070aa  xor     r9d, r9d
0x1800070ad  mov     [rsp+10B0h+var_1080], rax
0x1800070b2  mov     edx, edi
0x1800070b4  mov     [rsp+10B0h+var_1088], rsi
0x1800070b9  mov     rcx, rbx
0x1800070bc  mov     [rsp+10B0h+var_1090], r15
0x1800070c1  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800070c6  mov     eax, r14d
0x1800070c9  mov     rcx, [rbp+0FB0h+var_30]
0x1800070d0  xor     rcx, rsp; StackCookie
0x1800070d3  call    __security_check_cookie
0x1800070d8  mov     rbx, [rsp+10B0h+arg_10]
0x1800070e0  add     rsp, 1090h
0x1800070e7  pop     r15
0x1800070e9  pop     r14
0x1800070eb  pop     rdi
0x1800070ec  pop     rsi
0x1800070ed  pop     rbp
0x1800070ee  retn
0x1800070ef  mov     ecx, 8007023Eh; this
0x1800070f4  mov     dword ptr [rsp+10B0h+var_1058], ecx
0x1800070f8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800070fd  mov     dword ptr [rsp+10B0h+var_1058+4], eax
0x180007101  lea     r8, aPcshellBaseWhe_4; "pcshell\\base\\whesvc\\dll\\whesvc.cpp"
0x180007108  lea     rax, [rbp+0FB0h+var_1030]
0x18000710c  mov     [rsp+10B0h+var_1050], r15d
0x180007111  mov     [rsp+10B0h+var_1078], rax
0x180007116  mov     edx, edi
0x180007118  lea     rax, [rsp+10B0h+var_1058]
0x18000711d  mov     rcx, rbx
0x180007120  mov     [rsp+10B0h+var_1080], rax
0x180007125  mov     [rsp+10B0h+var_1088], rsi
0x18000712a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
