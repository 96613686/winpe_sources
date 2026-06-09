# RenameLiveIdIfRequired(void * const,CAutoRefPtr<CSingleIdentity>,_LUID &,EPPCRLRequestType,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CBytePtr &,SessionKeyTypes::Type)

- ea: `0x18006da60`
- end: `0x18006df41`
- name: `?RenameLiveIdIfRequired@@YAXQEAXV?$CAutoRefPtr@VCSingleIdentity@@@@AEAU_LUID@@W4EPPCRLRequestType@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCBytePtr@@W4Type@SessionKeyTypes@@@Z`
- size: `1249`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800563d0`

## callees

- `0x18000141c`
- `0x180009e98`
- `0x18000a354`
- `0x18000a36c`
- `0x18000c050`
- `0x18000d0e4`
- `0x18000ed04`
- `0x18000fc88`
- `0x18000fd04`
- `0x1800151c4`
- `0x180018f80`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180020970`
- `0x1800216f8`
- `0x180029d54`
- `0x18002a074`
- `0x180039d60`
- `0x18003b044`
- `0x18003c814`
- `0x18005538c`
- `0x18006da60`
- `0x180079554`
- `0x18009362c`
- `0x1800a1f78`
- `0x1800f0dd0`
- `0x1800f0ff8`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006dbf3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006dcb2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006dbf3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006dcb2`

## string_xrefs

- `0x18006db02`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\renamemembername.cpp`
- `0x18006dd44`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\renamemembername.cpp`
- `0x18006dd90`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\renamemembername.cpp`
- `0x18006dad8`: `RenameLiveIdIfRequired`
- `0x18006db29`: `RenameLiveIdIfRequired`
- `0x18006dbb1`: `RenameLiveIdIfRequired`
- `0x18006dc7a`: `RenameLiveIdIfRequired`
- `0x18006db9c`: `hr = pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_AUTHMEMBERNAME, renameAccountData.newEmailId)`
- `0x18006dc62`: `hr = SystemStoreLite::IsConnected(serviceExecutionContext.GetExternalExecutionContextLite(), &isCurrentIdentityConnected, &pConnectedLiveUserName)`
- `0x18006dc03`: `renameAccountData.newEmailId.CompareNoCase(renameAccountData.oldEmailId) != 0`
- `0x18006dd7e`: `hr = HandleCreateContext(renameAccountData.newEmailId, CREATECONTEXT_SET_APP_IDENTITY, &renameAccountData.hNewUser, c_renameAccountApplicationId)`
- `0x18006dd37`: `No rename required.`
- `0x18006de04`: `hr = PersistNewMemberNameCredentials(requestType, response, originalSessionKey, originalSessionKeyType, renameAccountData)`
- `0x18006ddc4`: `hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, renameAccountData.hNewUser, renameAccountData.pNewIdentity)`
- `0x18006de6a`: `hr = UpdateModernIdentityStore(&serviceExecutionContext, renameAccountData)`
- `0x18006de40`: `hr = RenameConnectedAccount(&serviceExecutionContext, renameAccountData)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall RenameLiveIdIfRequired(void *a1, _QWORD *a2, _DWORD *a3, int a4, __int64 a5, __int64 a6, int a7)
{
  bool v11; // bl
  int v12; // edi
  __int64 v13; // rax
  int v14; // eax
  int IsConnected; // eax
  int v16; // esi
  _QWORD *v17; // rax
  __int64 v18; // rbx
  bool v19; // bl
  int Context; // eax
  const char *v21; // rcx
  unsigned int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  char *v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v30[16]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v31[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v33; // [rsp+78h] [rbp-88h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  void *v35[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  int *v38[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v39[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v40[56]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v41[216]; // [rsp+128h] [rbp+28h] BYREF
  int v42; // [rsp+210h] [rbp+110h] BYREF
  _QWORD *v43; // [rsp+218h] [rbp+118h]

  v43 = a2;
  v11 = 0;
  v12 = 0;
  v42 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
  v34 = 0;
  *(_OWORD *)v35 = 0;
  v37 = 0;
  v36 = 0;
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v40);
  v28 = 0;
  v39[0] = "RenameLiveIdIfRequired";
  v39[1] = &v42;
  v39[2] = 0;
  v39[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
    "RenameLiveIdIfRequired",
    (const char *)0x1F1,
    0,
    (const unsigned __int16 *)v27);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v38, "RenameLiveIdIfRequired", &v42, 0x17u, &qword_18017E190);
  CAutoRefPtr<CSingleIdentity>::operator=(&v34);
  v35[0] = a1;
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 32LL))(*a2, &v29);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&v32, v13);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
  v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 **))(*(_QWORD *)*a2 + 64LL))(
          *a2,
          L"AuthMembername",
          &v33);
  v42 = v14;
  if ( v14 >= 0 )
  {
    if ( !*((_DWORD *)v33 - 4) )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
        0x206u,
        L"New name not set.");
      goto LABEL_41;
    }
    if ( !(unsigned int)_o__wcsicmp(v33, v32) )
    {
      v42 = 0;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
        "RenameLiveIdIfRequired",
        0x209u,
        0,
        "renameAccountData.newEmailId.CompareNoCase(renameAccountData.oldEmailId) != 0");
      goto LABEL_41;
    }
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v30,
      (struct _RTL_CRITICAL_SECTION *)((char *)g_pPPCRL + 2272),
      1);
    memset(v31, 0, 24);
    IsConnected = SystemStoreLite::IsConnected((struct IExecutionContextLite *)v41, &v28, v31);
    v42 = IsConnected;
    if ( IsConnected >= 0 )
    {
      v16 = v28;
      if ( v28 == 1 )
      {
        v17 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 32LL))(*a2, &v29);
        v12 = 1;
        v11 = (unsigned int)_o__wcsicmp(v31[0], *v17) != 0;
      }
      if ( (v12 & 1) != 0 )
      {
        v12 &= ~1u;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
      }
      if ( v11 )
        v16 = 0;
      v19 = 0;
      if ( !v16 && !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 48LL))(*a2) )
      {
        v18 = *a2;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v29,
          L"ps:password");
        v12 |= 2u;
        v28 = v12;
        if ( !(unsigned __int8)CSingleIdentity::HasPersistedCredential(v18, &v29) )
          v19 = 1;
      }
      if ( (v12 & 2) != 0 )
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
      if ( v19 )
      {
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
          0x21Eu,
          L"No rename required.");
      }
      else
      {
        Context = HandleCreateContext(v33, 0x800000, &v35[1], L"{d0d7679d-3fb6-470e-8b4b-857a57e92f82}");
        v42 = Context;
        if ( Context >= 0 )
        {
          Context = CIdentityStore::GetSingleIdentity((__int64)g_pPPCRL + 496, a3, (__int64)v35[1], (_QWORD *)&v34 + 1);
          v42 = Context;
          if ( Context >= 0 )
          {
            Context = PersistNewMemberNameCredentials(a4, a5, a6, a7, (__int64)&v32);
            v42 = Context;
            if ( Context >= 0 )
            {
              if ( v16 == 1
                && (*(_DWORD *)(*a2 + 736LL) = 0,
                    Context = RenameConnectedAccount(
                                (struct IServiceExecutionContext *)v40,
                                (struct RenameAccountData *)&v32),
                    v42 = Context,
                    Context < 0) )
              {
                v21 = "hr = RenameConnectedAccount(&serviceExecutionContext, renameAccountData)";
                v22 = 555;
              }
              else
              {
                Context = UpdateModernIdentityStore(
                            (struct IServiceExecutionContext *)v40,
                            (struct RenameAccountData *)&v32);
                v42 = Context;
                if ( Context >= 0 )
                {
                  if ( (unsigned int)dword_1801C2080 > 5
                    && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
                  {
                    v28 = v16;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                      v23,
                      (__int64)&word_18019B47E,
                      v24,
                      v25,
                      (__int64)&v28);
                  }
                  HandleRemovePersistedCredential(a1, L"ps:password", 2u);
                  goto LABEL_40;
                }
                v21 = "hr = UpdateModernIdentityStore(&serviceExecutionContext, renameAccountData)";
                v22 = 557;
              }
            }
            else
            {
              v21 = "hr = PersistNewMemberNameCredentials(requestType, response, originalSessionKey, originalSessionKeyTy"
                    "pe, renameAccountData)";
              v22 = 550;
            }
          }
          else
          {
            v21 = "hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, renameAccountData.hNewUser, renameAccoun"
                  "tData.pNewIdentity)";
            v22 = 548;
          }
        }
        else
        {
          v21 = "hr = HandleCreateContext(renameAccountData.newEmailId, CREATECONTEXT_SET_APP_IDENTITY, &renameAccountDat"
                "a.hNewUser, c_renameAccountApplicationId)";
          v22 = 546;
        }
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
          "RenameLiveIdIfRequired",
          v22,
          Context,
          v21);
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
        "RenameLiveIdIfRequired",
        0x213u,
        IsConnected,
        "hr = SystemStoreLite::IsConnected(serviceExecutionContext.GetExternalExecutionContextLite(), &isCurrentIdentityC"
        "onnected, &pConnectedLiveUserName)");
    }
LABEL_40:
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v31);
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v30);
    goto LABEL_41;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\renamemembername.cpp",
    "RenameLiveIdIfRequired",
    0x201u,
    v14,
    "hr = pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_AUTHMEMBERNAME, renameAccountData.newEmailId)");
LABEL_41:
  ErrorVerifier::CheckAgainstList((const char *)v38[3], *v38[2], (unsigned __int64)v38[1], v38[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v39);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v40);
  RenameAccountData::~RenameAccountData((RenameAccountData *)&v32);
  return CAutoRefPtr<CSingleIdentity>::Deinit(a2);
}

```

## disassembly

```asm
0x18006da60  mov     [rsp-8+arg_10], rbx
0x18006da65  mov     [rsp-8+arg_8], rdx
0x18006da6a  push    rbp
0x18006da6b  push    rsi
0x18006da6c  push    rdi
0x18006da6d  push    r12
0x18006da6f  push    r13
0x18006da71  push    r14
0x18006da73  push    r15
0x18006da75  lea     rbp, [rsp-0D0h]
0x18006da7d  sub     rsp, 1D0h
0x18006da84  mov     r13d, r9d
0x18006da87  mov     r12, r8
0x18006da8a  mov     r14, rdx
0x18006da8d  mov     r15, rcx
0x18006da90  xor     ebx, ebx
0x18006da92  mov     edi, ebx
0x18006da94  mov     [rsp+200h+var_1D0], ebx
0x18006da98  mov     [rbp+100h+arg_0], ebx
0x18006da9e  lea     rcx, [rsp+200h+var_190]
0x18006daa3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006daa8  lea     rcx, [rsp+200h+var_188]
0x18006daad  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006dab2  xorps   xmm0, xmm0
0x18006dab5  movdqa  [rbp+100h+var_180], xmm0
0x18006daba  xorps   xmm1, xmm1
0x18006dabd  movdqa  xmmword ptr [rbp+100h+var_170], xmm1
0x18006dac2  mov     [rbp+100h+var_158], rbx
0x18006dac6  mov     [rbp+100h+var_160], rbx
0x18006daca  lea     rcx, [rbp+100h+var_110]; this
0x18006dace  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x18006dad3  nop
0x18006dad4  mov     [rsp+200h+var_1D0], ebx
0x18006dad8  lea     rcx, aRenameliveidif; "RenameLiveIdIfRequired"
0x18006dadf  mov     [rbp+100h+var_130], rcx
0x18006dae3  lea     rax, [rbp+100h+arg_0]
0x18006daea  mov     [rbp+100h+var_128], rax
0x18006daee  mov     [rbp+100h+var_120], rbx
0x18006daf2  mov     [rbp+100h+var_118], rbx
0x18006daf6  xor     r9d, r9d; unsigned int
0x18006daf9  mov     r8d, 1F1h; char *
0x18006daff  mov     rdx, rcx; char *
0x18006db02  lea     rsi, aOnecoreuapDsEx_99; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006db09  mov     rcx, rsi; this
0x18006db0c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18006db11  nop
0x18006db12  lea     rax, qword_18017E190
0x18006db19  mov     [rsp+200h+var_1E0], rax; int *
0x18006db1e  lea     r9d, [rbx+17h]; unsigned __int64
0x18006db22  lea     r8, [rbp+100h+arg_0]; int *
0x18006db29  lea     rdx, aRenameliveidif; "RenameLiveIdIfRequired"
0x18006db30  lea     rcx, [rbp+100h+var_150]; this
0x18006db34  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18006db39  nop
0x18006db3a  mov     rdx, r14
0x18006db3d  lea     rcx, [rbp+100h+var_180]
0x18006db41  call    ??4?$CAutoRefPtr@VCSingleIdentity@@@@QEAAAEAV0@AEBV0@@Z; CAutoRefPtr<CSingleIdentity>::operator=(CAutoRefPtr<CSingleIdentity> const &)
0x18006db46  mov     [rbp+100h+var_170], r15
0x18006db4a  mov     rcx, [r14]
0x18006db4d  mov     rax, [rcx]
0x18006db50  lea     rdx, [rsp+200h+var_1C8]
0x18006db55  mov     rax, [rax+20h]
0x18006db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db5e  nop
0x18006db5f  mov     rdx, rax
0x18006db62  lea     rcx, [rsp+200h+var_190]
0x18006db67  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18006db6c  nop
0x18006db6d  lea     rcx, [rsp+200h+var_1C8]
0x18006db72  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006db77  mov     rcx, [r14]
0x18006db7a  mov     rax, [rcx]
0x18006db7d  lea     r8, [rsp+200h+var_188]
0x18006db82  lea     rdx, aAuthmembername; "AuthMembername"
0x18006db89  mov     rax, [rax+40h]
0x18006db8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db92  mov     [rbp+100h+arg_0], eax
0x18006db98  test    eax, eax
0x18006db9a  jns     short loc_18006DBC5
0x18006db9c  lea     r8, aHrPidentityGet_3; "hr = pIdentity->GetCredProperty(PPCRL_C"...
0x18006dba3  mov     [rsp+200h+var_1E0], r8; char *
0x18006dba8  mov     r9d, eax; int
0x18006dbab  mov     r8d, 201h; unsigned int
0x18006dbb1  lea     rdx, aRenameliveidif; "RenameLiveIdIfRequired"
0x18006dbb8  mov     rcx, rsi; char *
0x18006dbbb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006dbc0  jmp     loc_18006DEE7
0x18006dbc5  mov     rcx, [rsp+200h+var_188]
0x18006dbca  cmp     [rcx-10h], ebx
0x18006dbcd  jnz     short loc_18006DBEE
0x18006dbcf  lea     r9, aNewNameNotSet; "New name not set."
0x18006dbd6  mov     r8d, 206h; unsigned int
0x18006dbdc  mov     rdx, rsi; char *
0x18006dbdf  mov     ecx, 5; unsigned __int8
0x18006dbe4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006dbe9  jmp     loc_18006DEE7
0x18006dbee  mov     rdx, [rsp+200h+var_190]
0x18006dbf3  call    cs:__imp__o__wcsicmp
0x18006dbf9  test    eax, eax
0x18006dbfb  jnz     short loc_18006DC1A
0x18006dbfd  mov     [rbp+100h+arg_0], ebx
0x18006dc03  lea     rax, aRenameaccountd; "renameAccountData.newEmailId.CompareNoC"...
0x18006dc0a  mov     [rsp+200h+var_1E0], rax
0x18006dc0f  xor     r9d, r9d
0x18006dc12  mov     r8d, 209h
0x18006dc18  jmp     short loc_18006DBB1
0x18006dc1a  mov     rdx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18006dc21  add     rdx, 8E0h
0x18006dc28  mov     r8b, 1
0x18006dc2b  lea     rcx, [rsp+200h+var_1C0]
0x18006dc30  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18006dc35  nop
0x18006dc36  mov     [rsp+200h+var_1B0], rbx
0x18006dc3b  mov     [rsp+200h+var_1A0], rbx
0x18006dc40  mov     [rsp+200h+var_1A8], rbx
0x18006dc45  lea     r8, [rsp+200h+var_1B0]; unsigned __int16 **
0x18006dc4a  lea     rdx, [rsp+200h+var_1D0]; int *
0x18006dc4f  lea     rcx, [rbp+100h+var_D8]; struct IExecutionContextLite *
0x18006dc53  call    ?IsConnected@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEAHPEAPEAG@Z; SystemStoreLite::IsConnected(IExecutionContextLite *,int *,ushort * *)
0x18006dc58  mov     [rbp+100h+arg_0], eax
0x18006dc5e  test    eax, eax
0x18006dc60  jns     short loc_18006DC8B
0x18006dc62  lea     rcx, aHrSystemstorel_4; "hr = SystemStoreLite::IsConnected(servi"...
0x18006dc69  mov     [rsp+200h+var_1E0], rcx; char *
0x18006dc6e  mov     r8d, 213h; unsigned int
0x18006dc74  mov     rcx, rsi; char *
0x18006dc77  mov     r9d, eax; int
0x18006dc7a  lea     rdx, aRenameliveidif; "RenameLiveIdIfRequired"
0x18006dc81  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18006dc86  jmp     loc_18006DED1
0x18006dc8b  mov     esi, [rsp+200h+var_1D0]
0x18006dc8f  cmp     esi, 1
0x18006dc92  jnz     short loc_18006DCBF
0x18006dc94  mov     rcx, [r14]
0x18006dc97  mov     rax, [rcx]
0x18006dc9a  lea     rdx, [rsp+200h+var_1C8]
0x18006dc9f  mov     rax, [rax+20h]
0x18006dca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dca8  mov     edi, esi
0x18006dcaa  mov     rdx, [rax]
0x18006dcad  mov     rcx, [rsp+200h+var_1B0]
0x18006dcb2  call    cs:__imp__o__wcsicmp
0x18006dcb8  test    eax, eax
0x18006dcba  jz      short loc_18006DCBF
0x18006dcbc  mov     bl, dil
0x18006dcbf  test    dil, 1
0x18006dcc3  jz      short loc_18006DCD2
0x18006dcc5  and     edi, 0FFFFFFFEh
0x18006dcc8  lea     rcx, [rsp+200h+var_1C8]
0x18006dccd  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006dcd2  xor     eax, eax
0x18006dcd4  test    bl, bl
0x18006dcd6  cmovnz  esi, eax
0x18006dcd9  test    esi, esi
0x18006dcdb  jnz     short loc_18006DD21
0x18006dcdd  mov     rcx, [r14]
0x18006dce0  mov     rax, [rcx]
0x18006dce3  mov     rax, [rax+30h]
0x18006dce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dcec  test    al, al
0x18006dcee  jnz     short loc_18006DD21
0x18006dcf0  mov     rbx, [r14]
0x18006dcf3  lea     rdx, aPsPassword_0; "ps:password"
0x18006dcfa  lea     rcx, [rsp+200h+var_1C8]
0x18006dcff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18006dd04  nop
0x18006dd05  or      edi, 2
0x18006dd08  mov     [rsp+200h+var_1D0], edi
0x18006dd0c  lea     rdx, [rsp+200h+var_1C8]
0x18006dd11  mov     rcx, rbx
0x18006dd14  call    ?HasPersistedCredential@CSingleIdentity@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSingleIdentity::HasPersistedCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18006dd19  test    al, al
0x18006dd1b  jnz     short loc_18006DD21
0x18006dd1d  mov     bl, 1
0x18006dd1f  jmp     short loc_18006DD23
0x18006dd21  xor     bl, bl
0x18006dd23  test    dil, 2
0x18006dd27  jz      short loc_18006DD33
0x18006dd29  lea     rcx, [rsp+200h+var_1C8]
0x18006dd2e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006dd33  test    bl, bl
0x18006dd35  jz      short loc_18006DD5A
0x18006dd37  lea     r9, aNoRenameRequir; "No rename required."
0x18006dd3e  mov     r8d, 21Eh; unsigned int
0x18006dd44  lea     rdx, aOnecoreuapDsEx_99; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006dd4b  mov     ecx, 5; unsigned __int8
0x18006dd50  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18006dd55  jmp     loc_18006DED1
0x18006dd5a  lea     r9, aD0d7679d3fb647; "{d0d7679d-3fb6-470e-8b4b-857a57e92f82}"
0x18006dd61  lea     r8, [rbp+100h+var_170+8]; void **
0x18006dd65  mov     edx, 800000h; unsigned __int64
0x18006dd6a  mov     rcx, [rsp+200h+var_188]; unsigned __int16 *
0x18006dd6f  call    ?HandleCreateContext@@YAJPEBG_KPEAPEAX0@Z; HandleCreateContext(ushort const *,unsigned __int64,void * *,ushort const *)
0x18006dd74  mov     [rbp+100h+arg_0], eax
0x18006dd7a  test    eax, eax
0x18006dd7c  jns     short loc_18006DD9C
0x18006dd7e  lea     rcx, aHrHandlecreate_0; "hr = HandleCreateContext(renameAccountD"...
0x18006dd85  mov     r8d, 222h
0x18006dd8b  mov     [rsp+200h+var_1E0], rcx
0x18006dd90  lea     rcx, aOnecoreuapDsEx_99; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18006dd97  jmp     loc_18006DC77
0x18006dd9c  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18006dda3  add     rcx, 1F0h
0x18006ddaa  lea     r9, [rbp+100h+var_180+8]
0x18006ddae  mov     r8, [rbp+100h+var_170+8]
0x18006ddb2  mov     rdx, r12
0x18006ddb5  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x18006ddba  mov     [rbp+100h+arg_0], eax
0x18006ddc0  test    eax, eax
0x18006ddc2  jns     short loc_18006DDD3
0x18006ddc4  lea     rcx, aHrGPppcrlGetid_14; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x18006ddcb  mov     r8d, 224h
0x18006ddd1  jmp     short loc_18006DD8B
0x18006ddd3  lea     rax, [rsp+200h+var_190]
0x18006ddd8  mov     [rsp+200h+var_1E0], rax
0x18006dddd  mov     r9d, [rbp+100h+arg_30]
0x18006dde4  mov     r8, [rbp+100h+arg_28]
0x18006ddeb  mov     rdx, [rbp+100h+arg_20]
0x18006ddf2  mov     ecx, r13d
0x18006ddf5  call    ?PersistNewMemberNameCredentials@@YAJW4EPPCRLRequestType@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCBytePtr@@W4Type@SessionKeyTypes@@AEAURenameAccountData@@@Z; PersistNewMemberNameCredentials(EPPCRLRequestType,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,CBytePtr &,SessionKeyTypes::Type,RenameAccountData &)
0x18006ddfa  mov     [rbp+100h+arg_0], eax
0x18006de00  test    eax, eax
0x18006de02  jns     short loc_18006DE16
0x18006de04  lea     rcx, aHrPersistnewme; "hr = PersistNewMemberNameCredentials(re"...
0x18006de0b  mov     r8d, 226h
0x18006de11  jmp     loc_18006DD8B
0x18006de16  cmp     esi, 1
0x18006de19  jnz     short loc_18006DE52
0x18006de1b  mov     rax, [r14]
0x18006de1e  mov     dword ptr [rax+2E0h], 0
0x18006de28  lea     rdx, [rsp+200h+var_190]; struct RenameAccountData *
0x18006de2d  lea     rcx, [rbp+100h+var_110]; struct IServiceExecutionContext *
0x18006de31  call    ?RenameConnectedAccount@@YAJPEAVIServiceExecutionContext@@AEAURenameAccountData@@@Z; RenameConnectedAccount(IServiceExecutionContext *,RenameAccountData &)
0x18006de36  mov     [rbp+100h+arg_0], eax
0x18006de3c  test    eax, eax
0x18006de3e  jns     short loc_18006DE52
0x18006de40  lea     rcx, aHrRenameconnec; "hr = RenameConnectedAccount(&serviceExe"...
0x18006de47  mov     r8d, 22Bh
0x18006de4d  jmp     loc_18006DD8B
0x18006de52  lea     rdx, [rsp+200h+var_190]; struct RenameAccountData *
0x18006de57  lea     rcx, [rbp+100h+var_110]; struct IServiceExecutionContext *
0x18006de5b  call    ?UpdateModernIdentityStore@@YAJPEAVIServiceExecutionContext@@AEAURenameAccountData@@@Z; UpdateModernIdentityStore(IServiceExecutionContext *,RenameAccountData &)
0x18006de60  mov     [rbp+100h+arg_0], eax
0x18006de66  test    eax, eax
0x18006de68  jns     short loc_18006DE7C
0x18006de6a  lea     rcx, aHrUpdatemodern; "hr = UpdateModernIdentityStore(&service"...
0x18006de71  mov     r8d, 22Dh
0x18006de77  jmp     loc_18006DD8B
0x18006de7c  mov     eax, cs:dword_1801C2080
0x18006de82  cmp     eax, 5
0x18006de85  jbe     short loc_18006DEBB
0x18006de87  mov     rdx, 400000000000h
0x18006de91  lea     rcx, dword_1801C2080
0x18006de98  call    _tlgKeywordOn
0x18006de9d  test    al, al
0x18006de9f  jz      short loc_18006DEBB
0x18006dea1  mov     [rsp+200h+var_1D0], esi
0x18006dea5  lea     rax, [rsp+200h+var_1D0]
0x18006deaa  mov     [rsp+200h+var_1E0], rax
0x18006deaf  lea     rdx, word_18019B47E
0x18006deb6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006debb  mov     r8d, 2; unsigned __int64
0x18006dec1  lea     rdx, aPsPassword_0; "ps:password"
0x18006dec8  mov     rcx, r15; void *
0x18006decb  call    ?HandleRemovePersistedCredential@@YAJQEAXPEBG_K@Z; HandleRemovePersistedCredential(void * const,ushort const *,unsigned __int64)
0x18006ded0  nop
0x18006ded1  lea     rcx, [rsp+200h+var_1B0]
0x18006ded6  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18006dedb  nop
0x18006dedc  lea     rcx, [rsp+200h+var_1C0]
0x18006dee1  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18006dee6  nop
0x18006dee7  mov     r9, [rbp+100h+var_150]; int *
0x18006deeb  mov     r8, [rbp+100h+var_148]; unsigned __int64
0x18006deef  mov     rdx, [rbp+100h+var_140]
0x18006def3  mov     edx, [rdx]; int
0x18006def5  mov     rcx, [rbp+100h+var_138]; char *
0x18006def9  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18006defe  nop
0x18006deff  lea     rcx, [rbp+100h+var_130]
0x18006df03  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18006df08  nop
0x18006df09  lea     rcx, [rbp+100h+var_110]; this
0x18006df0d  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x18006df12  nop
0x18006df13  lea     rcx, [rsp+200h+var_190]; this
0x18006df18  call    ??1RenameAccountData@@QEAA@XZ; RenameAccountData::~RenameAccountData(void)
0x18006df1d  nop
0x18006df1e  mov     rcx, r14
0x18006df21  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x18006df26  mov     rbx, [rsp+200h+arg_10]
0x18006df2e  add     rsp, 1D0h
0x18006df35  pop     r15
0x18006df37  pop     r14
0x18006df39  pop     r13
0x18006df3b  pop     r12
0x18006df3d  pop     rdi
0x18006df3e  pop     rsi
0x18006df3f  pop     rbp
0x18006df40  retn
  ... truncated ...
```
