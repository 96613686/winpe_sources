# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180025644`
- end: `0x180025732`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: `void __fastcall __noreturn(__int64, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025614`

## callees

- `0x180002ca4`
- `0x1800045f8`
- `0x180025644`
- `0x180037010`

## string_xrefs

- `0x1800256c9`: `onecore\ds\security\scard\vscr\transports\simulator\cards\tpmvsc\dll\misc.h`
- `0x1800256fd`: `onecore\ds\security\scard\vscr\transports\simulator\cards\tpmvsc\dll\misc.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
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
        140,
        (unsigned int)"onecore\\ds\\security\\scard\\vscr\\transports\\simulator\\cards\\tpmvsc\\dll\\misc.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    140,
    (unsigned int)"onecore\\ds\\security\\scard\\vscr\\transports\\simulator\\cards\\tpmvsc\\dll\\misc.h",
    v11);
}

```

## disassembly

```asm
0x180025644  mov     rax, rsp
0x180025647  mov     [rax+8], rbx
0x18002564b  mov     [rax+10h], rsi
0x18002564f  mov     [rax+18h], r8d
0x180025653  push    rdi
0x180025654  sub     rsp, 70h
0x180025658  mov     rbx, [rsp+78h+arg_38]
0x180025660  xor     esi, esi
0x180025662  mov     [rax+18h], sil
0x180025666  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002566a  mov     rdi, rdx
0x18002566d  inc     rcx
0x180025670  cmp     [rbx+rcx*2], si
0x180025674  jnz     short loc_18002566D
0x180025676  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18002567d  test    rax, rax
0x180025680  jz      short loc_1800256EB
0x180025682  lea     rdx, [rbx+rcx*2]
0x180025686  mov     r8d, 800h
0x18002568c  sub     r8, rcx
0x18002568f  lea     r9, [rsp+78h+arg_10]
0x180025697  lea     rcx, [rsp+78h+var_18]
0x18002569c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256a1  movsd   xmm0, qword ptr [rax]
0x1800256a5  mov     eax, [rax+8]
0x1800256a8  mov     [rsp+78h+var_20], eax
0x1800256ac  movd    eax, xmm0
0x1800256b0  movsd   [rsp+78h+var_28], xmm0
0x1800256b6  test    eax, eax
0x1800256b8  jns     short loc_1800256EB
0x1800256ba  lea     rax, [rsp+78h+var_28]
0x1800256bf  mov     [rsp+78h+var_40], rbx
0x1800256c4  mov     [rsp+78h+var_48], rax
0x1800256c9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\scard\\vscr\\tra"...
0x1800256d0  mov     rax, [rsp+78h+arg_30]
0x1800256d8  mov     edx, 8Ch
0x1800256dd  mov     rcx, rdi
0x1800256e0  mov     [rsp+78h+var_50], rax
0x1800256e5  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800256eb  mov     ecx, 8007023Eh; this
0x1800256f0  mov     dword ptr [rsp+78h+var_28], ecx
0x1800256f4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800256f9  mov     dword ptr [rsp+78h+var_28+4], eax
0x1800256fd  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\scard\\vscr\\tra"...
0x180025704  lea     rax, [rsp+78h+var_28]
0x180025709  mov     [rsp+78h+var_40], rbx
0x18002570e  mov     [rsp+78h+var_48], rax
0x180025713  mov     edx, 8Ch
0x180025718  mov     rax, [rsp+78h+arg_30]
0x180025720  mov     rcx, rdi
0x180025723  mov     [rsp+78h+var_50], rax
0x180025728  mov     [rsp+78h+var_20], esi
0x18002572c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
