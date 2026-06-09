# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001a518`
- end: `0x18001a62a`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a490`

## callees

- `0x180007b70`
- `0x180007b7c`
- `0x180008a90`
- `0x18000b2c0`
- `0x18001a518`
- `0x18001e010`

## string_xrefs

- `0x18001a5af`: `onecoreuap\net\wcm\service\wcmpolicy\policyutil.cpp`
- `0x18001a604`: `onecoreuap\net\wcm\service\wcmpolicy\policyutil.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(_BYTE *, __int64, __int64, _BYTE *); // rax
  __int64 v12; // rax
  int v14; // r9d
  _BYTE v15[16]; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v16[8]; // [rsp+60h] [rbp-28h] BYREF

  v16[0] = 0;
  v9 = -1;
  v10 = a2;
  do
    ++v9;
  while ( *(_WORD *)(a8 + 2 * v9) );
  v11 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, _BYTE *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v11
    || (v12 = v11(v15, a8 + 2 * v9, 2048 - v9, v16),
        LODWORD(a2) = *(_DWORD *)(v12 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v12,
        *(_DWORD *)(a1 + 8) = a2,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      v10,
      68,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\wcmpolicy\\policyutil.cpp",
      v14);
  }
  wil::details::ReportFailure_Base<1,0>(v10, 68, "onecoreuap\\net\\wcm\\service\\wcmpolicy\\policyutil.cpp");
  return a1;
}

```

## disassembly

```asm
0x18001a518  mov     [rsp+arg_0], rbx
0x18001a51d  mov     [rsp+arg_10], rbp
0x18001a522  push    rsi
0x18001a523  push    rdi
0x18001a524  push    r14
0x18001a526  sub     rsp, 70h
0x18001a52a  mov     rax, cs:__security_cookie
0x18001a531  xor     rax, rsp
0x18001a534  mov     [rsp+88h+var_20], rax
0x18001a539  mov     rbp, [rsp+88h+arg_30]
0x18001a541  xor     r14d, r14d
0x18001a544  mov     rdi, [rsp+88h+arg_38]
0x18001a54c  mov     rbx, rcx
0x18001a54f  mov     [rsp+88h+var_28], r14b
0x18001a554  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001a558  mov     rsi, rdx
0x18001a55b  inc     rcx
0x18001a55e  cmp     [rdi+rcx*2], r14w
0x18001a563  jnz     short loc_18001A55B
0x18001a565  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001a56c  mov     [rbx], r14
0x18001a56f  mov     dword ptr [rbx+8], 1
0x18001a576  test    rax, rax
0x18001a579  jz      short loc_18001A5F3
0x18001a57b  lea     rdx, [rdi+rcx*2]
0x18001a57f  mov     r8d, 800h
0x18001a585  sub     r8, rcx
0x18001a588  lea     r9, [rsp+88h+var_28]
0x18001a58d  lea     rcx, [rsp+88h+var_38]
0x18001a592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a597  movsd   xmm0, qword ptr [rax]
0x18001a59b  mov     edx, [rax+8]
0x18001a59e  movsd   qword ptr [rbx], xmm0
0x18001a5a2  mov     [rbx+8], edx
0x18001a5a5  cmp     [rbx], r14d
0x18001a5a8  jge     short loc_18001A5F3
0x18001a5aa  mov     [rsp+88h+var_50], rdi
0x18001a5af  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\wcmpolic"...
0x18001a5b6  mov     [rsp+88h+var_58], rbx
0x18001a5bb  mov     edx, 44h ; 'D'
0x18001a5c0  mov     rcx, rsi
0x18001a5c3  mov     [rsp+88h+var_60], rbp
0x18001a5c8  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001a5cd  mov     rax, rbx
0x18001a5d0  mov     rcx, [rsp+88h+var_20]
0x18001a5d5  xor     rcx, rsp; StackCookie
0x18001a5d8  call    __security_check_cookie
0x18001a5dd  lea     r11, [rsp+88h+var_18]
0x18001a5e2  mov     rbx, [r11+20h]
0x18001a5e6  mov     rbp, [r11+30h]
0x18001a5ea  mov     rsp, r11
0x18001a5ed  pop     r14
0x18001a5ef  pop     rdi
0x18001a5f0  pop     rsi
0x18001a5f1  retn
0x18001a5f3  mov     ecx, 8007023Eh; this
0x18001a5f8  mov     [rbx], ecx
0x18001a5fa  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a5ff  mov     [rsp+88h+var_50], rdi
0x18001a604  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\wcmpolic"...
0x18001a60b  mov     [rbx+4], eax
0x18001a60e  mov     rcx, rsi
0x18001a611  mov     [rsp+88h+var_58], rbx
0x18001a616  mov     edx, 44h ; 'D'
0x18001a61b  mov     [rbx+8], r14d
0x18001a61f  mov     [rsp+88h+var_60], rbp
0x18001a624  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
