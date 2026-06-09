# IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)

- ea: `0x1800035cc`
- end: `0x180003986`
- name: `?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `954`
- prototype: ``
- caller_count: `11`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001261c`
- `0x180014004`
- `0x18003c9cc`
- `0x18003cfa8`
- `0x18003d0d0`
- `0x18003d848`
- `0x18003dd2c`
- `0x18003dfd4`
- `0x18003ea04`
- `0x18003f44c`
- `0x18003f5c0`

## callees

- `0x1800034c0`
- `0x1800035cc`
- `0x180003990`
- `0x1800039c8`
- `0x180003e00`
- `0x18000535c`
- `0x180009630`
- `0x180009e00`
- `0x18000a400`
- `0x180013434`
- `0x180016104`
- `0x180016758`
- `0x18001abbe`
- `0x1800535e4`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000372a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000372a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800038e9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800038e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800036bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800036bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003742`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003742`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000364e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000364e`

## string_xrefs

- `0x180003611`: `IdentityStorage::GetEnvironmentSpecificRegistryKey`
- `0x180003730`: `IdentityStorage::GetEnvironmentSpecificRegistryKey`
- `0x18000381a`: `ServiceEnvironment`
- `0x180003877`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x180003914`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x1800036fe`: `Reading current environment failed, using production as default`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void *IdentityStorage::GetEnvironmentSpecificRegistryKey(__int64 *a1, void *a2, __int64 a3, ...)
{
  __int64 v3; // rdi
  int v6; // r14d
  __int64 v7; // rsi
  _DWORD *v8; // r9
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rbx
  void *v11; // rbx
  int v12; // edi
  int v13; // r8d
  __int64 v15; // r13
  void *v16; // rdi
  int v17; // eax
  unsigned int v18; // esi
  char *v19; // rdx
  const unsigned __int16 *v20; // [rsp+28h] [rbp-49h]
  void *v21; // [rsp+60h] [rbp-11h] BYREF
  void *v22; // [rsp+68h] [rbp-9h]
  const char *v23; // [rsp+70h] [rbp-1h]
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+78h] [rbp+7h]
  _QWORD v25[9]; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v3 = a3;
  v6 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
  v23 = "IdentityStorage::GetEnvironmentSpecificRegistryKey";
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::GetEnvironmentSpecificRegistryKey",
    (const char *)0x21,
    0,
    v20);
  if ( IdentityStorage::_isInitialized )
    goto LABEL_15;
  v24 = &IdentityStorage::_criticalSection;
  EnterCriticalSection(&IdentityStorage::_criticalSection);
  if ( IdentityStorage::_isInitialized )
    goto LABEL_14;
  v22 = 0;
  v7 = *a1;
  v8 = IdentityStorage::_currentEnvironment;
  v9 = *((unsigned int *)IdentityStorage::_currentEnvironment - 4);
  v10 = ((char *)L"production" - (_BYTE *)IdentityStorage::_currentEnvironment) >> 1;
  if ( ((*((_DWORD *)IdentityStorage::_currentEnvironment - 3) - 10)
      | (1 - *((_DWORD *)IdentityStorage::_currentEnvironment - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&IdentityStorage::_currentEnvironment, 10);
    v8 = IdentityStorage::_currentEnvironment;
  }
  if ( v10 <= v9 )
  {
    if ( v8 )
    {
      v19 = (char *)v8 + 2 * v10;
      if ( v19 )
      {
        memmove_0(v8, v19, 0x14u);
        goto LABEL_19;
      }
    }
  }
  else if ( v8 )
  {
    *(_OWORD *)v8 = *(_OWORD *)L"production";
    v8[4] = *(_DWORD *)L"on";
    goto LABEL_19;
  }
  *(_DWORD *)_o__errno() = 22;
  invalid_parameter_noinfo();
LABEL_19:
  if ( *((int *)IdentityStorage::_currentEnvironment - 3) < 10 )
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)IdentityStorage::_currentEnvironment - 4) = 10;
  *((_WORD *)IdentityStorage::_currentEnvironment + 10) = 0;
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v25[2] = v15;
  v25[1] = 0;
  v16 = 0;
  v21 = 0;
  v11 = 0;
  v22 = 0;
  v25[0] = 0;
  while ( 1 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v15 + 56LL))(
            v15,
            -2147483646,
            L"Software\\Microsoft\\IdentityCRL",
            L"ServiceEnvironment");
    if ( !v17 )
    {
      if ( v16 )
      {
LABEL_8:
        v11 = v16;
        v22 = v16;
        v12 = 0;
        goto LABEL_9;
      }
      goto LABEL_34;
    }
    if ( v17 != 234 )
      break;
    if ( v6 >= 5 )
      goto LABEL_24;
LABEL_34:
    CMIDLPtr<unsigned short *>::Clear(&v21);
    v16 = malloc(0);
    CMIDLPtr<unsigned short *>::Clear(&v21);
    v21 = v16;
    if ( !v16 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
        (const char *)0x8007000ELL,
        2);
      goto LABEL_36;
    }
    if ( v6 >= 5 )
      goto LABEL_8;
    ++v6;
  }
  if ( v17 > 0 )
  {
LABEL_24:
    v18 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_25;
  }
  v18 = v17;
LABEL_25:
  v12 = -2147024894;
  if ( v18 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
      (const char *)v18,
      2);
    CMIDLPtr<unsigned short *>::Clear(&v21);
    v12 = v18;
    goto LABEL_9;
  }
LABEL_36:
  CMIDLPtr<unsigned short *>::Clear(&v21);
LABEL_9:
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v25);
  if ( v12 < 0 )
    TracePrintW(
      4u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      0x37u,
      L"Reading current environment failed, using production as default");
  IdentityStorage::_isInitialized = 1;
  if ( v11 )
    free(v11);
  v3 = a3;
LABEL_14:
  LeaveCriticalSection(&IdentityStorage::_criticalSection);
LABEL_15:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    a2,
    v3,
    IdentityStorage::_currentEnvironment);
  MsaTracingInternal::TraceFunctionExit(
    (MsaTracingInternal *)"IdentityStorage::GetEnvironmentSpecificRegistryKey",
    0,
    v13);
  return a2;
}

```

## disassembly

```asm
0x1800035cc  mov     rax, rsp
0x1800035cf  mov     [rax+8], rbx
0x1800035d3  mov     [rax+18h], r8
0x1800035d7  mov     [rax+10h], rdx
0x1800035db  push    rbp
0x1800035dc  push    rsi
0x1800035dd  push    rdi
0x1800035de  push    r12
0x1800035e0  push    r13
0x1800035e2  push    r14
0x1800035e4  push    r15
0x1800035e6  lea     rbp, [rax-5Fh]
0x1800035ea  sub     rsp, 90h
0x1800035f1  mov     rdi, r8
0x1800035f4  mov     r15, rdx
0x1800035f7  mov     rbx, rcx
0x1800035fa  xor     r14d, r14d
0x1800035fd  mov     [rbp+57h+var_70], r14d
0x180003601  mov     rcx, rdx; void *
0x180003604  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180003609  lea     r12d, [r14+1]
0x18000360d  mov     [rbp+57h+var_70], r12d
0x180003611  lea     rsi, aIdentitystorag_5; "IdentityStorage::GetEnvironmentSpecific"...
0x180003618  mov     [rbp+57h+var_58], rsi
0x18000361c  xor     r9d, r9d; unsigned int
0x18000361f  lea     r8d, [r14+21h]; char *
0x180003623  mov     rdx, rsi; char *
0x180003626  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000362d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180003632  nop
0x180003633  cmp     cs:?_isInitialized@IdentityStorage@@0_NA, r14b; bool IdentityStorage::_isInitialized
0x18000363a  jnz     loc_180003748
0x180003640  lea     rax, ?_criticalSection@IdentityStorage@@0VCCritSecLite@@A; CCritSecLite IdentityStorage::_criticalSection
0x180003647  mov     [rbp+57h+var_50], rax
0x18000364b  mov     rcx, rax; lpCriticalSection
0x18000364e  call    cs:__imp_EnterCriticalSection
0x180003654  nop
0x180003655  cmp     cs:?_isInitialized@IdentityStorage@@0_NA, r14b; bool IdentityStorage::_isInitialized
0x18000365c  jnz     loc_18000373B
0x180003662  mov     [rbp+57h+var_60], r14
0x180003666  mov     rsi, [rbx]
0x180003669  mov     r9, cs:?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x180003670  mov     edi, [r9-10h]
0x180003674  lea     rbx, aProduction; "production"
0x18000367b  sub     rbx, r9
0x18000367e  sar     rbx, 1
0x180003681  mov     ecx, r12d
0x180003684  sub     ecx, [r9-8]
0x180003688  mov     eax, [r9-0Ch]
0x18000368c  lea     r12d, [r14+0Ah]
0x180003690  sub     eax, r12d
0x180003693  or      ecx, eax
0x180003695  jge     short loc_1800036AD
0x180003697  mov     edx, r12d
0x18000369a  lea     rcx, ?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x1800036a1  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800036a6  mov     r9, cs:?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x1800036ad  cmp     rbx, rdi
0x1800036b0  jbe     loc_18000389E
0x1800036b6  test    r9, r9
0x1800036b9  jnz     loc_180003792
0x1800036bf  call    cs:__imp__o__errno
0x1800036c5  mov     dword ptr [rax], 16h
0x1800036cb  call    _invalid_parameter_noinfo
0x1800036d0  jmp     loc_1800037A7
0x1800036d5  cmp     eax, 0EAh
0x1800036da  jz      loc_180003783
0x1800036e0  mov     rbx, rdi
0x1800036e3  mov     [rbp+57h+var_60], rbx
0x1800036e7  mov     r12d, [rbp+57h+arg_18]
0x1800036eb  xor     edi, edi
0x1800036ed  lea     rcx, [rbp+57h+var_48]
0x1800036f1  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x1800036f6  test    edi, edi
0x1800036f8  jns     loc_180003935
0x1800036fe  lea     r9, aReadingCurrent; "Reading current environment failed, usi"...
0x180003705  mov     r8d, 37h ; '7'; unsigned int
0x18000370b  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180003712  lea     ecx, [r8-33h]; unsigned __int8
0x180003716  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000371b  mov     cs:?_isInitialized@IdentityStorage@@0_NA, 1; bool IdentityStorage::_isInitialized
0x180003722  test    rbx, rbx
0x180003725  jz      short loc_180003730
0x180003727  mov     rcx, rbx; Block
0x18000372a  call    cs:__imp_free
0x180003730  lea     rsi, aIdentitystorag_5; "IdentityStorage::GetEnvironmentSpecific"...
0x180003737  mov     rdi, [rbp+57h+arg_10]
0x18000373b  lea     rcx, ?_criticalSection@IdentityStorage@@0VCCritSecLite@@A; lpCriticalSection
0x180003742  call    cs:__imp_LeaveCriticalSection
0x180003748  mov     r8, cs:?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x18000374f  mov     rdx, rdi
0x180003752  mov     rcx, r15
0x180003755  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000375a  nop
0x18000375b  xor     edx, edx; char *
0x18000375d  mov     rcx, rsi; this
0x180003760  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x180003765  mov     rax, r15
0x180003768  mov     rbx, [rsp+0C0h+arg_0]
0x180003770  add     rsp, 90h
0x180003777  pop     r15
0x180003779  pop     r14
0x18000377b  pop     r13
0x18000377d  pop     r12
0x18000377f  pop     rdi
0x180003780  pop     rsi
0x180003781  pop     rbp
0x180003782  retn
0x180003783  cmp     r14d, 5
0x180003787  jge     loc_1800036E0
0x18000378d  inc     r14d
0x180003790  jmp     short loc_1800037FB
0x180003792  movups  xmm0, xmmword ptr cs:aProduction; "production"
0x180003799  movups  xmmword ptr [r9], xmm0
0x18000379d  mov     eax, dword ptr cs:aProduction+10h; "on"
0x1800037a3  mov     [r9+10h], eax
0x1800037a7  mov     rax, cs:?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x1800037ae  cmp     [rax-0Ch], r12d
0x1800037b2  jl      loc_18000397B
0x1800037b8  mov     [rax-10h], r12d
0x1800037bc  mov     rax, cs:?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x1800037c3  mov     [rax+14h], r14w
0x1800037c8  mov     rax, [rsi]
0x1800037cb  mov     rcx, rsi
0x1800037ce  mov     rax, [rax+8]
0x1800037d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d7  mov     r13, rax
0x1800037da  mov     [rbp+57h+var_38], rax
0x1800037de  mov     [rbp+57h+var_40], r14
0x1800037e2  mov     rdi, r14
0x1800037e5  mov     [rbp+57h+var_68], r14
0x1800037e9  mov     rbx, r14
0x1800037ec  mov     [rbp+57h+var_60], rbx
0x1800037f0  mov     r12d, r14d
0x1800037f3  mov     [rbp+57h+var_48], r14
0x1800037f7  mov     [rbp+57h+arg_18], r14d
0x1800037fb  mov     rax, [r13+0]
0x1800037ff  lea     rcx, [rbp+57h+arg_18]
0x180003803  mov     [rsp+38h], rcx
0x180003808  mov     [rsp+0C0h+var_90], rdi
0x18000380d  mov     [rsp+0C0h+var_98], rbx
0x180003812  mov     [rsp+0C0h+var_A0], 2; int
0x18000381a  lea     r9, aServiceenviron; "ServiceEnvironment"
0x180003821  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\IdentityCRL"
0x180003828  mov     rdx, 0FFFFFFFF80000002h
0x18000382f  mov     rcx, r13
0x180003832  mov     rax, [rax+38h]
0x180003836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383b  test    eax, eax
0x18000383d  jz      loc_1800038C7
0x180003843  cmp     eax, 0EAh
0x180003848  jz      loc_1800038D2
0x18000384e  test    eax, eax
0x180003850  jle     short loc_18000389A
0x180003852  movzx   esi, ax
0x180003855  or      esi, 80070000h
0x18000385b  test    esi, esi
0x18000385d  jns     loc_1800036D5
0x180003863  mov     edi, 80070002h
0x180003868  cmp     esi, edi
0x18000386a  jz      loc_180003926
0x180003870  mov     rcx, [rbp+5Fh]; this
0x180003874  mov     r9d, esi; char *
0x180003877  lea     r8, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000387e  mov     edx, 60h ; '`'; void *
0x180003883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003888  nop
0x180003889  lea     rcx, [rbp+57h+var_68]
0x18000388d  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180003892  nop
0x180003893  mov     edi, esi
0x180003895  jmp     loc_1800036ED
0x18000389a  mov     esi, eax
0x18000389c  jmp     short loc_18000385B
0x18000389e  test    r9, r9
0x1800038a1  jz      loc_1800036BF
0x1800038a7  lea     rdx, [r9+rbx*2]; Src
0x1800038ab  test    rdx, rdx
0x1800038ae  jz      loc_1800036BF
0x1800038b4  mov     r8d, 14h; Size
0x1800038ba  mov     rcx, r9; void *
0x1800038bd  call    memmove_0
0x1800038c2  jmp     loc_1800037A7
0x1800038c7  test    rdi, rdi
0x1800038ca  jnz     loc_1800036E0
0x1800038d0  jmp     short loc_1800038DC
0x1800038d2  cmp     r14d, 5
0x1800038d6  jge     loc_180003852
0x1800038dc  lea     rcx, [rbp+57h+var_68]
0x1800038e0  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800038e5  movsxd  rcx, [rbp+57h+arg_18]; Size
0x1800038e9  call    cs:__imp_malloc
0x1800038ef  mov     rdi, rax
0x1800038f2  lea     rcx, [rbp+57h+var_68]
0x1800038f6  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800038fb  mov     [rbp+57h+var_68], rdi
0x1800038ff  test    rdi, rdi
0x180003902  jnz     loc_180003783
0x180003908  mov     rcx, [rbp+5Fh]; this
0x18000390c  mov     edi, 8007000Eh
0x180003911  mov     r9d, edi; char *
0x180003914  lea     r8, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000391b  mov     edx, 5Ah ; 'Z'; void *
0x180003920  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003925  nop
0x180003926  lea     rcx, [rbp+57h+var_68]
0x18000392a  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18000392f  nop
0x180003930  jmp     loc_1800036ED
0x180003935  test    r12d, r12d
0x180003938  jz      loc_18000371B
0x18000393e  mov     rdx, rbx
0x180003941  lea     rcx, ?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x180003948  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18000394d  mov     rax, cs:?_currentEnvironment@IdentityStorage@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> IdentityStorage::_currentEnvironment
0x180003954  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180003959  lea     r9, aCurrentEnviron; "Current environment is %s"
0x180003960  mov     r8d, 32h ; '2'; unsigned int
0x180003966  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000396d  lea     ecx, [r8-2Dh]; unsigned __int8
0x180003971  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180003976  jmp     loc_18000371B
0x18000397b  mov     ecx, 80070057h; int
0x180003980  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
