# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000b390`
- end: `0x18000b4af`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b2f8`

## callees

- `0x180007b7c`
- `0x180008a90`
- `0x18000b26c`
- `0x18000b2c0`
- `0x18000b390`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rcx
  __int64 (__fastcall *v12)(_BYTE *, __int64, __int64, _BYTE *); // rax
  __int64 v13; // rax
  int v14; // r8d
  int v16; // r9d
  _BYTE v17[16]; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v18[8]; // [rsp+60h] [rbp-38h] BYREF

  v18[0] = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a8 + 2 * v9) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, _BYTE *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v17, a8 + 2 * v9, 2048 - v9, v18),
        v14 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v14,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      a3,
      (unsigned int)"OneCore\\Internal\\Net\\inc\\NetworkingTriageScenario.h",
      v16);
  }
  wil::details::ReportFailure_Base<2,0>(
    a2,
    a3,
    (unsigned int)"OneCore\\Internal\\Net\\inc\\NetworkingTriageScenario.h",
    0,
    0,
    a7,
    a1,
    a8);
  return a1;
}

```

## disassembly

```asm
0x18000b390  mov     [rsp+arg_0], rbx
0x18000b395  push    rbp
0x18000b396  push    rsi
0x18000b397  push    rdi
0x18000b398  push    r14
0x18000b39a  push    r15
0x18000b39c  sub     rsp, 70h
0x18000b3a0  mov     rax, cs:__security_cookie
0x18000b3a7  xor     rax, rsp
0x18000b3aa  mov     [rsp+98h+var_30], rax
0x18000b3af  mov     r14, [rsp+98h+arg_30]
0x18000b3b7  xor     r15d, r15d
0x18000b3ba  mov     rdi, [rsp+98h+arg_38]
0x18000b3c2  mov     rbx, rcx
0x18000b3c5  mov     [rsp+98h+var_38], r15b
0x18000b3ca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b3ce  mov     ebp, r8d
0x18000b3d1  mov     rsi, rdx
0x18000b3d4  inc     rcx
0x18000b3d7  cmp     [rdi+rcx*2], r15w
0x18000b3dc  jnz     short loc_18000B3D4
0x18000b3de  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000b3e5  mov     [rbx], r15
0x18000b3e8  mov     dword ptr [rbx+8], 1
0x18000b3ef  test    rax, rax
0x18000b3f2  jz      loc_18000B47B
0x18000b3f8  lea     rdx, [rdi+rcx*2]
0x18000b3fc  mov     r8d, 800h
0x18000b402  sub     r8, rcx
0x18000b405  lea     r9, [rsp+98h+var_38]
0x18000b40a  lea     rcx, [rsp+98h+var_48]
0x18000b40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b414  movsd   xmm0, qword ptr [rax]
0x18000b418  mov     r8d, [rax+8]
0x18000b41c  movsd   qword ptr [rbx], xmm0
0x18000b420  mov     [rbx+8], r8d
0x18000b424  cmp     [rbx], r15d
0x18000b427  jge     short loc_18000B47B
0x18000b429  mov     [rsp+98h+var_50], r15d
0x18000b42e  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Net\\inc\\Networking"...
0x18000b435  mov     [rsp+98h+var_60], rdi
0x18000b43a  xor     r9d, r9d
0x18000b43d  mov     [rsp+98h+var_68], rbx
0x18000b442  mov     edx, ebp
0x18000b444  mov     [rsp+98h+var_70], r14
0x18000b449  mov     rcx, rsi
0x18000b44c  mov     [rsp+98h+var_78], r15
0x18000b451  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b456  mov     rax, rbx
0x18000b459  mov     rcx, [rsp+98h+var_30]
0x18000b45e  xor     rcx, rsp; StackCookie
0x18000b461  call    __security_check_cookie
0x18000b466  mov     rbx, [rsp+98h+arg_0]
0x18000b46e  add     rsp, 70h
0x18000b472  pop     r15
0x18000b474  pop     r14
0x18000b476  pop     rdi
0x18000b477  pop     rsi
0x18000b478  pop     rbp
0x18000b479  retn
0x18000b47b  mov     ecx, 8007023Eh; this
0x18000b480  mov     [rbx], ecx
0x18000b482  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b487  mov     [rsp+98h+var_60], rdi
0x18000b48c  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Net\\inc\\Networking"...
0x18000b493  mov     [rbx+4], eax
0x18000b496  mov     rcx, rsi
0x18000b499  mov     [rsp+98h+var_68], rbx
0x18000b49e  mov     edx, ebp
0x18000b4a0  mov     [rbx+8], r15d
0x18000b4a4  mov     [rsp+98h+var_70], r14
0x18000b4a9  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
