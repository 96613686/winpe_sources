# UpdateUserAssociatedDeviceProperties

- ea: `0x180034930`
- end: `0x180034e48`
- name: `UpdateUserAssociatedDeviceProperties`
- size: `1304`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003298`
- `0x1800039e4`
- `0x180008b70`
- `0x18000b0bc`
- `0x18000ba8c`
- `0x18000c354`
- `0x18000c538`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x18002126c`
- `0x180022740`
- `0x180026130`
- `0x18002932c`
- `0x180029788`
- `0x180034930`
- `0x18004ffa4`
- `0x180053890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034db4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034dc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034de1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034db4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034dc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034de1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034a60`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034ad9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034b97`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034a60`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034ad9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180034b97`

## string_xrefs

- `0x1800349b3`: `IDCRL::UpdateUserAssociatedDeviceProperties`
- `0x180034e0f`: `IDCRL::UpdateUserAssociatedDeviceProperties`
- `0x180034b44`: `hr = StringCchCopyW((WCHAR*)pProps[i].wszString1, wcslen(paPropertyNames[i]) + 1, paPropertyNames[i])`
- `0x180034bf7`: `hr = StringCchCopyW((WCHAR*)pProps[i].wszString2, wcslen(paPropertyValues[i]) + 1, paPropertyValues[i])`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall UpdateUserAssociatedDeviceProperties(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // r13
  __int64 v7; // r8
  __int64 v8; // rbx
  struct __MIDL_liveidsvc_0003 *v9; // rax
  struct __MIDL_liveidsvc_0003 *v10; // rsi
  unsigned int i; // r14d
  __int64 v12; // r12
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  const unsigned __int16 *v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // r11
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  const unsigned __int16 *v21; // r8
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rcx
  _QWORD *v25; // r14
  _QWORD *v26; // rbx
  void *v27; // rbx
  _QWORD *HostingAppId; // rax
  const unsigned __int16 **v29; // rax
  unsigned int v30; // r14d
  __int64 v31; // r15
  void *v32; // rcx
  void *v33; // rcx
  unsigned int v34; // ebx
  __int64 v36; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+58h] [rbp-B0h] BYREF
  char *v38[4]; // [rsp+60h] [rbp-A8h] BYREF
  struct __MIDL_liveidsvc_0003 *v39; // [rsp+80h] [rbp-88h]
  __int64 v40; // [rsp+88h] [rbp-80h] BYREF
  char v41; // [rsp+90h] [rbp-78h]
  _QWORD v42[13]; // [rsp+A0h] [rbp-68h] BYREF
  int IdentityFromExternalHandle_Internal; // [rsp+110h] [rbp+8h] BYREF
  unsigned int v44; // [rsp+118h] [rbp+10h]
  unsigned int v45; // [rsp+120h] [rbp+18h]
  __int64 v46; // [rsp+128h] [rbp+20h]

  v46 = a4;
  v45 = a3;
  v44 = a2;
  v5 = a3;
  v37 = 0;
  IdentityFromExternalHandle_Internal = 0;
  if ( a1 && a3 - 1 <= 0xFE && a4 && (v39 = 0, a5) )
  {
    CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
      v38,
      (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x1761u,
      (char *)&IdentityFromExternalHandle_Internal,
      "IDCRL::UpdateUserAssociatedDeviceProperties",
      L"hUserIdentity=0x%p, dwAssocType=0x%x, dwCount=%d",
      a1,
      a2,
      a3);
    IdentityFromExternalHandle_Internal = VerifyInitialized();
    if ( IdentityFromExternalHandle_Internal >= 0 )
    {
      LOBYTE(v7) = 1;
      IdentityFromExternalHandle_Internal = CClientIdentityStore::GetIdentityFromExternalHandle_Internal(
                                              g_pPPCRL + 8,
                                              a1,
                                              v7,
                                              &v37);
      if ( IdentityFromExternalHandle_Internal >= 0 )
      {
        v8 = v37;
        if ( v37 )
        {
          v9 = (struct __MIDL_liveidsvc_0003 *)malloc(16 * v5);
          v10 = v9;
          v39 = v9;
          if ( v9 )
          {
            memset_0(v9, 0, 16 * v5);
            for ( i = 0; i < (unsigned int)v5; ++i )
            {
              v36 = i;
              v12 = 8LL * i;
              v13 = -1;
              do
                ++v13;
              while ( *(_WORD *)(*(_QWORD *)(v12 + v46) + 2 * v13) );
              v14 = (unsigned __int16 *)malloc(2LL * (unsigned int)(v13 + 1));
              v36 *= 16;
              *(_QWORD *)((char *)v10 + v36) = v14;
              if ( !v14 )
              {
LABEL_18:
                IdentityFromExternalHandle_Internal = -2147024882;
                CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
                goto LABEL_38;
              }
              v15 = *(const unsigned __int16 **)(v12 + v46);
              v16 = -1;
              do
                ++v16;
              while ( v15[v16] );
              v17 = StringCchCopyW(v14, v16 + 1, v15);
              IdentityFromExternalHandle_Internal = v17;
              if ( v17 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
                  "IDCRL::UpdateUserAssociatedDeviceProperties",
                  0x177Cu,
                  v17,
                  "hr = StringCchCopyW((WCHAR*)pProps[i].wszString1, wcslen(paPropertyNames[i]) + 1, paPropertyNames[i])");
                CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
                goto LABEL_38;
              }
              v19 = v18;
              do
                ++v19;
              while ( *(_WORD *)(*(_QWORD *)(v12 + a5) + 2 * v19) );
              v20 = (unsigned __int16 *)malloc(2LL * (unsigned int)(v19 + 1));
              *(_QWORD *)((char *)v10 + v36 + 8) = v20;
              if ( !v20 )
                goto LABEL_18;
              v21 = *(const unsigned __int16 **)(v12 + a5);
              v22 = -1;
              do
                ++v22;
              while ( v21[v22] );
              v23 = StringCchCopyW(v20, v22 + 1, v21);
              IdentityFromExternalHandle_Internal = v23;
              if ( v23 < 0 )
              {
                Telemetry::IfFailExit(
                  "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
                  "IDCRL::UpdateUserAssociatedDeviceProperties",
                  0x1780u,
                  v23,
                  "hr = StringCchCopyW((WCHAR*)pProps[i].wszString2, wcslen(paPropertyValues[i]) + 1, paPropertyValues[i])");
                CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
                goto LABEL_38;
              }
            }
            if ( v8 )
            {
              v40 = v8 + 16;
              v41 = 0;
              IdentityFromExternalHandle_Internal = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(&v40);
              if ( IdentityFromExternalHandle_Internal >= 0 )
              {
                v25 = (_QWORD *)(v8 + 64);
                v26 = *(_QWORD **)(v8 + 64);
                if ( !v26 )
                {
                  v26 = operator new(0x28u);
                  v26[1] = 0;
                  *((_DWORD *)v26 + 6) = 1;
                  *v26 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
                  v26[2] = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
                  v26[4] = 0;
                  CAutoRefPtr<SmartWLIDHandle>::Deinit(v25);
                  *v25 = v26;
                }
                v27 = (void *)v26[1];
                HostingAppId = (_QWORD *)CClientPassportClientLibrary::GetHostingAppId(v24, v42);
                v29 = (const unsigned __int16 **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                                                   &v36,
                                                   *HostingAppId);
                IdentityFromExternalHandle_Internal = WLIDCUpdateUserAssociatedDeviceProperties(*v29, v27, v44, v5, v10);
                ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
                ATL::CStringData::Release((ATL::CStringData *)(v42[0] - 24LL));
                CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v40);
                CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
              }
              else
              {
                CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v40);
                CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
              }
            }
            else
            {
              IdentityFromExternalHandle_Internal = -2147418113;
              CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
            }
LABEL_38:
            v30 = 0;
            if ( (_DWORD)v5 )
            {
              v31 = 0;
              do
              {
                v32 = (void *)*((_QWORD *)v10 + 2 * v31);
                if ( v32 )
                {
                  free(v32);
                  *((_QWORD *)v10 + 2 * v31) = 0;
                }
                v33 = (void *)*((_QWORD *)v10 + 2 * v31 + 1);
                if ( v33 )
                {
                  free(v33);
                  *((_QWORD *)v10 + 2 * v31 + 1) = 0;
                }
                ++v30;
                ++v31;
              }
              while ( v30 < (unsigned int)v5 );
            }
            free(v10);
          }
          else
          {
            IdentityFromExternalHandle_Internal = -2147024882;
            CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
          }
        }
        else
        {
          IdentityFromExternalHandle_Internal = -2147188704;
          CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
        }
      }
      else
      {
        CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
      }
    }
    else
    {
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
    }
  }
  else
  {
    IdentityFromExternalHandle_Internal = -2147024809;
    Telemetry::IfFailExit(
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      "IDCRL::UpdateUserAssociatedDeviceProperties",
      0x175Bu,
      -2147024809,
      "hUserIdentity && dwCount > 0 && dwCount < MAX_DEVICE_PROPERTIES && paPropertyNames && paPropertyValues");
  }
  v34 = IdentityFromExternalHandle_Internal;
  CAutoRefPtr<CAuthContext>::Deinit(&v37);
  return v34;
}

```

## disassembly

```asm
0x180034930  mov     r11, rsp
0x180034933  mov     [r11+20h], r9
0x180034937  mov     [r11+18h], r8d
0x18003493b  mov     [rsp+arg_8], edx
0x18003493f  push    rbx
0x180034940  push    rsi
0x180034941  push    rdi
0x180034942  push    r12
0x180034944  push    r13
0x180034946  push    r14
0x180034948  push    r15
0x18003494a  sub     rsp, 0D0h
0x180034951  mov     r13d, r8d
0x180034954  mov     rbx, rcx
0x180034957  xor     edi, edi
0x180034959  mov     [rsp+108h+var_B0], rdi
0x18003495e  mov     [r11+8], edi
0x180034962  test    rcx, rcx
0x180034965  jz      loc_180034DEF
0x18003496b  lea     eax, [r13-1]
0x18003496f  cmp     eax, 0FEh
0x180034974  ja      loc_180034DEF
0x18003497a  test    r9, r9
0x18003497d  jz      loc_180034DEF
0x180034983  mov     [rsp+108h+var_88], rdi
0x18003498b  cmp     [rsp+108h+arg_20], rdi
0x180034993  jz      loc_180034DEF
0x180034999  mov     [rsp+108h+var_C8], r13d
0x18003499e  mov     [rsp+108h+var_D0], edx
0x1800349a2  mov     [rsp+108h+var_D8], rcx
0x1800349a7  lea     rax, aHuseridentity0_1; "hUserIdentity=0x%p, dwAssocType=0x%x, d"...
0x1800349ae  mov     [rsp+108h+var_E0], rax
0x1800349b3  lea     r15, aIdcrlUpdateuse; "IDCRL::UpdateUserAssociatedDeviceProper"...
0x1800349ba  mov     [rsp+108h+var_E8], r15
0x1800349bf  lea     r9, [r11+8]
0x1800349c3  mov     r8d, 1761h
0x1800349c9  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x1800349d0  lea     rcx, [rsp+108h+var_A8]
0x1800349d5  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x1800349da  nop
0x1800349db  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x1800349e0  mov     [rsp+108h+arg_0], eax
0x1800349e7  test    eax, eax
0x1800349e9  jns     short loc_1800349FB
0x1800349eb  lea     rcx, [rsp+108h+var_A8]
0x1800349f0  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800349f5  nop
0x1800349f6  jmp     loc_180034E22
0x1800349fb  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x180034a02  add     rcx, 20h ; ' '
0x180034a06  lea     r9, [rsp+108h+var_B0]
0x180034a0b  mov     r8b, 1
0x180034a0e  mov     rdx, rbx
0x180034a11  call    ?GetIdentityFromExternalHandle_Internal@CClientIdentityStore@@QEAAJPEAU_tagPIH@IDCRL@@_NAEAV?$CAutoRefPtr@VCClientSingleIdentity@@@@@Z; CClientIdentityStore::GetIdentityFromExternalHandle_Internal(IDCRL::_tagPIH *,bool,CAutoRefPtr<CClientSingleIdentity> &)
0x180034a16  mov     [rsp+108h+arg_0], eax
0x180034a1d  test    eax, eax
0x180034a1f  jns     short loc_180034A31
0x180034a21  lea     rcx, [rsp+108h+var_A8]
0x180034a26  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034a2b  nop
0x180034a2c  jmp     loc_180034E22
0x180034a31  mov     rbx, [rsp+108h+var_B0]
0x180034a36  test    rbx, rbx
0x180034a39  jnz     short loc_180034A56
0x180034a3b  mov     [rsp+108h+arg_0], 80048020h
0x180034a46  lea     rcx, [rsp+108h+var_A8]
0x180034a4b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034a50  nop
0x180034a51  jmp     loc_180034E22
0x180034a56  mov     r14, r13
0x180034a59  shl     r14, 4
0x180034a5d  mov     rcx, r14; Size
0x180034a60  call    cs:__imp_malloc
0x180034a66  mov     rsi, rax
0x180034a69  mov     [rsp+108h+var_88], rax
0x180034a71  test    rax, rax
0x180034a74  jnz     short loc_180034A91
0x180034a76  mov     [rsp+108h+arg_0], 8007000Eh
0x180034a81  lea     rcx, [rsp+108h+var_A8]
0x180034a86  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034a8b  nop
0x180034a8c  jmp     loc_180034E22
0x180034a91  mov     r8, r14; Size
0x180034a94  xor     edx, edx; Val
0x180034a96  mov     rcx, rsi; void *
0x180034a99  call    memset_0
0x180034a9e  mov     r14d, edi
0x180034aa1  cmp     r14d, r13d
0x180034aa4  jnb     loc_180034C34
0x180034aaa  mov     ecx, r14d
0x180034aad  mov     [rsp+108h+var_B8], rcx
0x180034ab2  lea     r12, ds:0[rcx*8]
0x180034aba  mov     rcx, [rsp+108h+arg_18]
0x180034ac2  mov     rcx, [r12+rcx]
0x180034ac6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034aca  inc     rax
0x180034acd  cmp     [rcx+rax*2], di
0x180034ad1  jnz     short loc_180034ACA
0x180034ad3  lea     ecx, [rax+1]
0x180034ad6  add     rcx, rcx; Size
0x180034ad9  call    cs:__imp_malloc
0x180034adf  mov     rcx, rax; unsigned __int16 *
0x180034ae2  mov     rax, [rsp+108h+var_B8]
0x180034ae7  shl     rax, 4
0x180034aeb  mov     [rsp+108h+var_B8], rax
0x180034af0  mov     [rax+rsi], rcx
0x180034af4  test    rcx, rcx
0x180034af7  jnz     short loc_180034B14
0x180034af9  mov     [rsp+108h+arg_0], 8007000Eh
0x180034b04  lea     rcx, [rsp+108h+var_A8]
0x180034b09  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034b0e  nop
0x180034b0f  jmp     loc_180034D9A
0x180034b14  mov     rax, [rsp+108h+arg_18]
0x180034b1c  mov     r8, [r12+rax]; unsigned __int16 *
0x180034b20  or      r11, 0FFFFFFFFFFFFFFFFh
0x180034b24  mov     rdx, r11
0x180034b27  inc     rdx
0x180034b2a  cmp     [r8+rdx*2], di
0x180034b2f  jnz     short loc_180034B27
0x180034b31  inc     rdx; unsigned __int64
0x180034b34  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034b39  mov     [rsp+108h+arg_0], eax
0x180034b40  test    eax, eax
0x180034b42  jns     short loc_180034B79
0x180034b44  lea     rcx, aHrStringcchcop_1; "hr = StringCchCopyW((WCHAR*)pProps[i].w"...
0x180034b4b  mov     [rsp+108h+var_E8], rcx; char *
0x180034b50  mov     r9d, eax; int
0x180034b53  mov     r8d, 177Ch; unsigned int
0x180034b59  mov     rdx, r15; char *
0x180034b5c  lea     rcx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180034b63  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180034b68  nop
0x180034b69  lea     rcx, [rsp+108h+var_A8]
0x180034b6e  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034b73  nop
0x180034b74  jmp     loc_180034D9A
0x180034b79  mov     rax, [rsp+108h+arg_20]
0x180034b81  mov     rcx, [r12+rax]
0x180034b85  mov     rax, r11
0x180034b88  inc     rax
0x180034b8b  cmp     [rcx+rax*2], di
0x180034b8f  jnz     short loc_180034B88
0x180034b91  lea     ecx, [rax+1]
0x180034b94  add     rcx, rcx; Size
0x180034b97  call    cs:__imp_malloc
0x180034b9d  mov     rcx, [rsp+108h+var_B8]
0x180034ba2  mov     [rcx+rsi+8], rax
0x180034ba7  test    rax, rax
0x180034baa  jnz     short loc_180034BC7
0x180034bac  mov     [rsp+108h+arg_0], 8007000Eh
0x180034bb7  lea     rcx, [rsp+108h+var_A8]
0x180034bbc  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034bc1  nop
0x180034bc2  jmp     loc_180034D9A
0x180034bc7  mov     r8, [rsp+108h+arg_20]
0x180034bcf  mov     r8, [r12+r8]; unsigned __int16 *
0x180034bd3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180034bd7  inc     rdx
0x180034bda  cmp     [r8+rdx*2], di
0x180034bdf  jnz     short loc_180034BD7
0x180034be1  inc     rdx; unsigned __int64
0x180034be4  mov     rcx, rax; unsigned __int16 *
0x180034be7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034bec  mov     [rsp+108h+arg_0], eax
0x180034bf3  test    eax, eax
0x180034bf5  jns     short loc_180034C2C
0x180034bf7  lea     rcx, aHrStringcchcop_0; "hr = StringCchCopyW((WCHAR*)pProps[i].w"...
0x180034bfe  mov     [rsp+108h+var_E8], rcx; char *
0x180034c03  mov     r9d, eax; int
0x180034c06  mov     r8d, 1780h; unsigned int
0x180034c0c  mov     rdx, r15; char *
0x180034c0f  lea     rcx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180034c16  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180034c1b  nop
0x180034c1c  lea     rcx, [rsp+108h+var_A8]
0x180034c21  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034c26  nop
0x180034c27  jmp     loc_180034D9A
0x180034c2c  inc     r14d
0x180034c2f  jmp     loc_180034AA1
0x180034c34  test    rbx, rbx
0x180034c37  jnz     short loc_180034C54
0x180034c39  mov     [rsp+108h+arg_0], 8000FFFFh
0x180034c44  lea     rcx, [rsp+108h+var_A8]
0x180034c49  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034c4e  nop
0x180034c4f  jmp     loc_180034D9A
0x180034c54  lea     rax, [rbx+10h]
0x180034c58  mov     [rsp+108h+var_80], rax
0x180034c60  mov     [rsp+108h+var_78], dil
0x180034c68  lea     rcx, [rsp+108h+var_80]
0x180034c70  call    ?TryLock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(void)
0x180034c75  mov     [rsp+108h+arg_0], eax
0x180034c7c  test    eax, eax
0x180034c7e  jns     short loc_180034C9E
0x180034c80  lea     rcx, [rsp+108h+var_80]
0x180034c88  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180034c8d  nop
0x180034c8e  lea     rcx, [rsp+108h+var_A8]
0x180034c93  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034c98  nop
0x180034c99  jmp     loc_180034D9A
0x180034c9e  lea     r14, [rbx+40h]
0x180034ca2  mov     rbx, [r14]
0x180034ca5  test    rbx, rbx
0x180034ca8  jnz     short loc_180034CE6
0x180034caa  lea     ecx, [rbx+28h]; Size
0x180034cad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034cb2  mov     rbx, rax
0x180034cb5  xor     eax, eax
0x180034cb7  mov     [rbx+8], rax
0x180034cbb  mov     dword ptr [rbx+18h], 1
0x180034cc2  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x180034cc9  mov     [rbx], rax
0x180034ccc  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x180034cd3  mov     [rbx+10h], rax
0x180034cd7  mov     [rbx+20h], rdi
0x180034cdb  mov     rcx, r14
0x180034cde  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x180034ce3  mov     [r14], rbx
0x180034ce6  mov     rbx, [rbx+8]
0x180034cea  lea     rdx, [rsp+108h+var_68]
0x180034cf2  call    ?GetHostingAppId@CClientPassportClientLibrary@@QEBA?AV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@XZ; CClientPassportClientLibrary::GetHostingAppId(void)
0x180034cf7  nop
0x180034cf8  mov     rdx, [rax]
0x180034cfb  lea     rcx, [rsp+108h+var_B8]
0x180034d00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x180034d05  mov     [rsp+108h+var_E8], rsi; struct __MIDL_liveidsvc_0003 *
0x180034d0a  mov     r9d, r13d; unsigned int
0x180034d0d  mov     r8d, [rsp+108h+arg_8]; unsigned int
0x180034d15  mov     rdx, rbx; void *
0x180034d18  mov     rcx, [rax]; unsigned __int16 *
0x180034d1b  call    ?WLIDCUpdateUserAssociatedDeviceProperties@@YAJPEBGQEAXKKPEAU__MIDL_liveidsvc_0003@@@Z; WLIDCUpdateUserAssociatedDeviceProperties(ushort const *,void * const,ulong,ulong,__MIDL_liveidsvc_0003 *)
0x180034d20  mov     [rsp+108h+arg_0], eax
0x180034d27  mov     rcx, [rsp+108h+var_B8]
0x180034d2c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034d30  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034d35  nop
0x180034d36  mov     rcx, [rsp+108h+var_68]
0x180034d3e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034d42  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034d47  nop
0x180034d48  lea     rcx, [rsp+108h+var_80]
0x180034d50  cmp     [rsp+108h+arg_0], edi
0x180034d57  jge     short loc_180034D6C
0x180034d59  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180034d5e  nop
0x180034d5f  lea     rcx, [rsp+108h+var_A8]
0x180034d64  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034d69  nop
0x180034d6a  jmp     short loc_180034D9A
0x180034d6c  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180034d71  nop
0x180034d72  lea     rcx, [rsp+108h+var_A8]
0x180034d77  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034d7c  nop
0x180034d7d  jmp     short loc_180034D9A
0x180034d7f  mov     rsi, [rsp+108h+var_88]
0x180034d87  xor     edi, edi
0x180034d89  test    rsi, rsi
0x180034d8c  jz      loc_180034E22
0x180034d92  mov     r13d, [rsp+108h+arg_10]
0x180034d9a  mov     r14d, edi
0x180034d9d  test    r13d, r13d
0x180034da0  jz      short loc_180034DDE
0x180034da2  mov     r15, rdi
0x180034da5  mov     rbx, r15
0x180034da8  add     rbx, rbx
0x180034dab  mov     rcx, [rsi+rbx*8]; Block
0x180034daf  test    rcx, rcx
0x180034db2  jz      short loc_180034DBE
0x180034db4  call    cs:__imp_free
0x180034dba  mov     [rsi+rbx*8], rdi
0x180034dbe  mov     rcx, [rsi+rbx*8+8]; Block
0x180034dc3  test    rcx, rcx
0x180034dc6  jz      short loc_180034DD3
0x180034dc8  call    cs:__imp_free
0x180034dce  mov     [rsi+rbx*8+8], rdi
0x180034dd3  inc     r14d
0x180034dd6  inc     r15
0x180034dd9  cmp     r14d, r13d
0x180034ddc  jb      short loc_180034DA5
0x180034dde  mov     rcx, rsi; Block
0x180034de1  call    cs:__imp_free
0x180034de7  jmp     short loc_180034E22
0x180034de9  jmp     short loc_180034D7F
0x180034deb  jmp     short loc_180034D7F
0x180034ded  jmp     short loc_180034D7F
0x180034def  mov     r9d, 80070057h; int
0x180034df5  mov     [rsp+108h+arg_0], r9d
0x180034dfd  lea     rax, aHuseridentityD; "hUserIdentity && dwCount > 0 && dwCount"...
0x180034e04  mov     [rsp+108h+var_E8], rax; char *
0x180034e09  mov     r8d, 175Bh; unsigned int
0x180034e0f  lea     rdx, aIdcrlUpdateuse; "IDCRL::UpdateUserAssociatedDeviceProper"...
0x180034e16  lea     rcx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180034e1d  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180034e22  mov     ebx, [rsp+108h+arg_0]
0x180034e29  lea     rcx, [rsp+108h+var_B0]
0x180034e2e  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
  ... truncated ...
```
