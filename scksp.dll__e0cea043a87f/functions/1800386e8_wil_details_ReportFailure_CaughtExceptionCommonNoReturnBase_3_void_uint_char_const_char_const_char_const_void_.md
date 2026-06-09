# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x1800386e8`
- end: `0x1800387d6`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800386b8`

## callees

- `0x18000be28`
- `0x18000e924`
- `0x1800386e8`
- `0x18003d010`

## string_xrefs

- `0x18003876d`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`
- `0x1800387a1`: `ds\security\scard\common\devhlpr\lib\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  int v10; // r9d
  int v11; // r9d
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  LOBYTE(v13) = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a8 + 2 * v8) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v12,
                                                           a8 + 2 * v8,
                                                           2048 - v8,
                                                           &v13)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        104,
        (unsigned int)"ds\\security\\scard\\common\\devhlpr\\lib\\errorcontract.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    104,
    (unsigned int)"ds\\security\\scard\\common\\devhlpr\\lib\\errorcontract.h",
    v11);
}

```

## disassembly

```asm
0x1800386e8  mov     rax, rsp
0x1800386eb  mov     [rax+8], rbx
0x1800386ef  mov     [rax+10h], rsi
0x1800386f3  mov     [rax+18h], r8d
0x1800386f7  push    rdi
0x1800386f8  sub     rsp, 70h
0x1800386fc  mov     rbx, [rsp+78h+arg_38]
0x180038704  xor     esi, esi
0x180038706  mov     [rax+18h], sil
0x18003870a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003870e  mov     rdi, rdx
0x180038711  inc     rcx
0x180038714  cmp     [rbx+rcx*2], si
0x180038718  jnz     short loc_180038711
0x18003871a  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180038721  test    rax, rax
0x180038724  jz      short loc_18003878F
0x180038726  lea     rdx, [rbx+rcx*2]
0x18003872a  mov     r8d, 800h
0x180038730  sub     r8, rcx
0x180038733  lea     r9, [rsp+78h+arg_10]
0x18003873b  lea     rcx, [rsp+78h+var_18]
0x180038740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038745  movsd   xmm0, qword ptr [rax]
0x180038749  mov     eax, [rax+8]
0x18003874c  mov     [rsp+78h+var_20], eax
0x180038750  movd    eax, xmm0
0x180038754  movsd   [rsp+78h+var_28], xmm0
0x18003875a  test    eax, eax
0x18003875c  jns     short loc_18003878F
0x18003875e  lea     rax, [rsp+78h+var_28]
0x180038763  mov     [rsp+78h+var_40], rbx
0x180038768  mov     [rsp+78h+var_48], rax
0x18003876d  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\devhlpr\\l"...
0x180038774  mov     rax, [rsp+78h+arg_30]
0x18003877c  mov     edx, 68h ; 'h'
0x180038781  mov     rcx, rdi
0x180038784  mov     [rsp+78h+var_50], rax
0x180038789  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18003878f  mov     ecx, 8007023Eh; this
0x180038794  mov     dword ptr [rsp+78h+var_28], ecx
0x180038798  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003879d  mov     dword ptr [rsp+78h+var_28+4], eax
0x1800387a1  lea     r8, aDsSecurityScar; "ds\\security\\scard\\common\\devhlpr\\l"...
0x1800387a8  lea     rax, [rsp+78h+var_28]
0x1800387ad  mov     [rsp+78h+var_40], rbx
0x1800387b2  mov     [rsp+78h+var_48], rax
0x1800387b7  mov     edx, 68h ; 'h'
0x1800387bc  mov     rax, [rsp+78h+arg_30]
0x1800387c4  mov     rcx, rdi
0x1800387c7  mov     [rsp+78h+var_50], rax
0x1800387cc  mov     [rsp+78h+var_20], esi
0x1800387d0  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
