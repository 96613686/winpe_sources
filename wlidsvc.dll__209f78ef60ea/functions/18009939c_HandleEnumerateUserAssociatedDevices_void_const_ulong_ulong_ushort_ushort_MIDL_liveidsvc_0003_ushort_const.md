# HandleEnumerateUserAssociatedDevices(void * const,ulong,ulong *,ushort * * *,ushort * * *,__MIDL_liveidsvc_0003 * *,ushort const *)

- ea: `0x18009939c`
- end: `0x180099a29`
- name: `?HandleEnumerateUserAssociatedDevices@@YAJQEAXKPEAKPEAPEAPEAG2PEAPEAU__MIDL_liveidsvc_0003@@PEBG@Z`
- size: `1677`
- prototype: `__int64 __fastcall(void *const, unsigned int, unsigned int *, unsigned __int16 ***, unsigned __int16 ***, struct __MIDL_liveidsvc_0003 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180099270`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x1800151c4`
- `0x180017af0`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x1800268d0`
- `0x18002df9c`
- `0x180030120`
- `0x18003b1e0`
- `0x18003c814`
- `0x180043344`
- `0x18009939c`
- `0x1800a3b60`
- `0x1800a4718`
- `0x1800a4778`
- `0x1800a716c`
- `0x1800ae308`
- `0x1800b9f5c`
- `0x1800cf25c`
- `0x1800ee29c`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800997e5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180099856`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800998d2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800997e5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180099856`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800998d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099999`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800999a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099999`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800999a7`

## string_xrefs

- `0x180099457`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800994b0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009969b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18009975f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099985`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180099494`: `hr = client.ImpersonateClient()`
- `0x180099743`: `hr = pEnumDevicesRequest->GetResponse(&dwCount, &pNamesTemp, &pFNamesTemp, &dwNamesSize, &dwFriendlyNamesSize )`
- `0x18009993a`: `hr = StringCchCopyW(rgDevices[i].wszString1, dwStrLen + 1, pNamesTemp[i])`
- `0x180099923`: `hr = StringCchCopyW(rgDevices[i].wszString2, dwStrLen + 1, pFNamesTemp[i])`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall HandleEnumerateUserAssociatedDevices(
        __int64 a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int16 ***a4,
        unsigned __int16 ***a5,
        struct __MIDL_liveidsvc_0003 **a6,
        const unsigned __int16 *a7)
{
  char *v9; // rsi
  struct CDeviceUserAssociation *v10; // rbx
  char *v11; // rdi
  int v12; // eax
  int LogonId; // eax
  int SingleIdentity; // eax
  CDeviceUserAssociation *v15; // rax
  __int64 v16; // rdi
  int v17; // eax
  int v18; // eax
  const char *v19; // rcx
  unsigned int v20; // r8d
  int Response; // eax
  unsigned int v22; // r12d
  struct __MIDL_liveidsvc_0003 *v23; // rax
  struct __MIDL_liveidsvc_0003 *v24; // r15
  unsigned int i; // r13d
  __int64 v26; // rax
  __int64 v27; // r14
  _WORD *v28; // r9
  char *v29; // rax
  int v30; // eax
  __int64 v31; // r10
  __int64 v32; // rax
  __int64 v33; // r14
  _WORD *v34; // r9
  char *v35; // rax
  int v36; // eax
  unsigned int v37; // edi
  char *v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v41; // [rsp+38h] [rbp-C8h] BYREF
  struct _LUID v42; // [rsp+40h] [rbp-C0h] BYREF
  char v43; // [rsp+48h] [rbp-B8h]
  unsigned int v44; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v46; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v48; // [rsp+68h] [rbp-98h]
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  __int64 v51; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v52; // [rsp+88h] [rbp-78h]
  struct __MIDL_liveidsvc_0003 **v53; // [rsp+90h] [rbp-70h]
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v55[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  __int64 v58; // [rsp+D0h] [rbp-30h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int16 v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  int v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  int v64; // [rsp+100h] [rbp+0h]
  __int128 v65; // [rsp+108h] [rbp+8h]
  __int128 v66; // [rsp+118h] [rbp+18h]
  __int64 v67; // [rsp+128h] [rbp+28h]
  void *Block; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v69[136]; // [rsp+138h] [rbp+38h] BYREF

  v52 = a3;
  v53 = a6;
  v9 = 0;
  v40 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  v42 = 0;
  v51 = 0;
  v10 = 0;
  v48 = 0;
  v49 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  v45 = 0;
  v46 = 0;
  v11 = 0;
  hMem = 0;
  v41 = 0;
  v44 = 0;
  v55[0] = "HandleEnumerateUserAssociatedDevices";
  v55[1] = &v40;
  v55[2] = 0;
  v55[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleEnumerateUserAssociatedDevices",
    (const char *)0x25A6,
    0,
    (const unsigned __int16 *)v39);
  if ( !v52 || !a6 )
  {
    v40 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      0x25A8u,
      -2147024809,
      "pdwCount && ((paNames && paFriendlyNames) || prgDevices)");
    goto LABEL_58;
  }
  *v52 = 0;
  *a6 = 0;
  v12 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v49, 0);
  v40 = v12;
  if ( v12 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      0x25B5u,
      v12,
      "hr = client.ImpersonateClient()");
    goto LABEL_62;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v49, &v42);
  v40 = LogonId;
  if ( LogonId < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      0x25B6u,
      LogonId,
      "hr = client.GetLogonId(logonId)");
    goto LABEL_62;
  }
  SingleIdentity = CIdentityStore::GetSingleIdentity((__int64)g_pPPCRL + 496, &v42, a1, &v51);
  v40 = SingleIdentity;
  if ( SingleIdentity < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      0x25BBu,
      SingleIdentity,
      "hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, hUser, pUserIdentity)");
    goto LABEL_62;
  }
  v15 = (CDeviceUserAssociation *)operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v15;
  v42 = (struct _LUID)v15;
  if ( v15 )
  {
    CDeviceUserAssociation::CDeviceUserAssociation(v15);
    *(_QWORD *)v10 = &CEnumDevicesRequest::`vftable'{for `CPPCRLBaseRequest'};
    *((_QWORD *)v10 + 8) = &CEnumDevicesRequest::`vftable'{for `IPPCRLRequest'};
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((_QWORD *)v10 + 37);
    *((_QWORD *)v10 + 38) = 0;
    *((_QWORD *)v10 + 39) = 0;
    *((_QWORD *)v10 + 40) = 0;
    *((_QWORD *)v10 + 41) = 0;
    *((_QWORD *)v10 + 42) = 0;
    *((_DWORD *)v10 + 86) = 10;
  }
  else
  {
    v10 = 0;
  }
  v48 = (unsigned __int64)v10;
  if ( !v10 )
  {
    v40 = -2147024882;
    goto LABEL_62;
  }
  Block = v69;
  ATL::CW2AEX<128>::Init(&Block, a7, 65001);
  ATL::CSimpleStringT<char,0>::SetString(&v50, (const char *)Block);
  if ( Block != v69 )
    free(Block);
  v16 = v51;
  v17 = CEnumDevicesRequest::Initialize(v10, v51, &v50, a2);
  v40 = v17;
  if ( v17 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      0x25C4u,
      v17,
      "hr = pEnumDevicesRequest->Initialize(pUserIdentity, strOwnerName, dwAssocType)");
    goto LABEL_62;
  }
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v42 = (struct _LUID)(v16 + 16);
  v43 = 0;
  v18 = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v42);
  v40 = v18;
  if ( v18 < 0 )
  {
    v19 = "hr = lock.Lock()";
    v20 = 9676;
LABEL_21:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      v20,
      v18,
      v19);
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v42);
    CTransport::~CTransport((CTransport *)&v56);
    goto LABEL_62;
  }
  v18 = (*(__int64 (__fastcall **)(struct CDeviceUserAssociation *))(*(_QWORD *)v10 + 352LL))(v10);
  v40 = v18;
  if ( v18 < 0 )
  {
    v19 = "hr = pEnumDevicesRequest->BuildRequest()";
    v20 = 9679;
    goto LABEL_21;
  }
  v18 = CTransport::SendDeviceRequest((CTransport *)&v56, v10);
  v40 = v18;
  if ( v18 < 0 )
  {
    v19 = "hr = transport.SendDeviceRequest(pEnumDevicesRequest)";
    v20 = 9682;
    goto LABEL_21;
  }
  Response = CEnumDevicesRequest::GetResponse(
               v10,
               &v44,
               (unsigned __int16 ***)&hMem,
               (unsigned __int16 ***)&v41,
               &v45,
               &v46);
  v40 = Response;
  if ( Response < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleEnumerateUserAssociatedDevices",
      0x25DAu,
      Response,
      "hr = pEnumDevicesRequest->GetResponse(&dwCount, &pNamesTemp, &pFNamesTemp, &dwNamesSize, &dwFriendlyNamesSize )");
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v42);
    CTransport::~CTransport((CTransport *)&v56);
LABEL_28:
    v11 = (char *)hMem;
    v9 = (char *)v41;
    goto LABEL_58;
  }
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v42);
  CTransport::~CTransport((CTransport *)&v56);
  if ( v40 < 0 )
    goto LABEL_28;
  v22 = v44;
  if ( !v44 || !v45 || !v46 )
    goto LABEL_28;
  v9 = (char *)v41;
  v11 = (char *)hMem;
  if ( !v41 )
  {
LABEL_58:
    if ( v11 )
      LocalFree(v11);
    goto LABEL_60;
  }
  if ( hMem )
  {
    v23 = (struct __MIDL_liveidsvc_0003 *)malloc(16LL * v44);
    v24 = v23;
    if ( v23 )
    {
      memset_0(v23, 0, 16LL * v22);
      for ( i = 0; i < v22; ++i )
      {
        v41 = (HLOCAL)i;
        v42 = (struct _LUID)(8LL * i);
        v26 = *(_QWORD *)&v11[*(_QWORD *)&v42];
        if ( v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)(v26 + 2 * v27) );
        }
        else
        {
          LODWORD(v27) = 0;
        }
        v48 = (unsigned int)(v27 + 1);
        v28 = malloc(2 * v48);
        v29 = (char *)(16LL * (_QWORD)v41);
        v41 = v29;
        *(_QWORD *)((char *)v24 + (_QWORD)v29) = v28;
        if ( !v28 )
          goto LABEL_36;
        v28[(unsigned int)v27] = 0;
        v30 = StringCchCopyW(
                *(unsigned __int16 **)((char *)v24 + (_QWORD)v29),
                v48,
                *(const unsigned __int16 **)&v11[*(_QWORD *)&v42]);
        v40 = v30;
        if ( v30 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "HandleEnumerateUserAssociatedDevices",
            0x25FDu,
            v30,
            "hr = StringCchCopyW(rgDevices[i].wszString1, dwStrLen + 1, pNamesTemp[i])");
          goto LABEL_58;
        }
        v32 = *(_QWORD *)&v9[v31];
        if ( v32 )
        {
          v33 = -1;
          do
            ++v33;
          while ( *(_WORD *)(v32 + 2 * v33) );
        }
        else
        {
          LODWORD(v33) = 0;
        }
        v48 = (unsigned int)(v33 + 1);
        v34 = malloc(2 * v48);
        v35 = (char *)v41;
        *(_QWORD *)((char *)v24 + (_QWORD)v41 + 8) = v34;
        if ( !v34 )
          goto LABEL_36;
        v34[(unsigned int)v33] = 0;
        v36 = StringCchCopyW(
                *(unsigned __int16 **)((char *)v24 + (_QWORD)v35 + 8),
                v48,
                *(const unsigned __int16 **)&v9[*(_QWORD *)&v42]);
        v40 = v36;
        if ( v36 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "HandleEnumerateUserAssociatedDevices",
            0x2603u,
            v36,
            "hr = StringCchCopyW(rgDevices[i].wszString2, dwStrLen + 1, pFNamesTemp[i])");
          goto LABEL_58;
        }
      }
      *v52 = v22;
      *v53 = v24;
    }
    else
    {
LABEL_36:
      v40 = -2147024882;
    }
    goto LABEL_58;
  }
LABEL_60:
  if ( v9 )
    LocalFree(v9);
LABEL_62:
  v37 = v40;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v55);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v49);
  if ( v10 )
    (**(void (__fastcall ***)(struct CDeviceUserAssociation *, __int64))v10)(v10, 1);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  return v37;
}

```

## disassembly

```asm
0x18009939c  mov     [rsp-8+arg_18], rbx
0x1800993a1  push    rbp
0x1800993a2  push    rsi
0x1800993a3  push    rdi
0x1800993a4  push    r12
0x1800993a6  push    r13
0x1800993a8  push    r14
0x1800993aa  push    r15
0x1800993ac  lea     rbp, [rsp-0D0h]
0x1800993b4  sub     rsp, 1D0h
0x1800993bb  mov     rax, cs:__security_cookie
0x1800993c2  xor     rax, rsp
0x1800993c5  mov     [rbp+100h+var_40], rax
0x1800993cc  mov     [rbp+100h+var_178], r8
0x1800993d0  mov     r12d, edx
0x1800993d3  mov     r14, rcx
0x1800993d6  mov     r13, [rbp+100h+arg_28]
0x1800993dd  mov     [rbp+100h+var_170], r13
0x1800993e1  mov     r15, [rbp+100h+arg_30]
0x1800993e8  xor     esi, esi
0x1800993ea  mov     [rsp+200h+var_1D0], esi
0x1800993ee  lea     rcx, [rbp+100h+var_168]
0x1800993f2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800993f7  nop
0x1800993f8  mov     qword ptr [rsp+200h+var_1C0.LowPart], rsi
0x1800993fd  mov     [rbp+100h+var_180], rsi
0x180099401  mov     ebx, esi
0x180099403  mov     [rsp+200h+var_198], rbx
0x180099408  mov     [rsp+200h+var_190], rsi
0x18009940d  lea     rcx, [rsp+200h+var_188]
0x180099412  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180099417  nop
0x180099418  mov     [rsp+200h+var_1AC], esi
0x18009941c  mov     [rsp+200h+var_1A8], esi
0x180099420  mov     edi, esi
0x180099422  mov     [rsp+200h+hMem], rsi
0x180099427  mov     [rsp+200h+var_1C8], rsi
0x18009942c  xor     ecx, ecx
0x18009942e  mov     [rsp+200h+var_1B0], ecx
0x180099432  lea     rdx, aHandleenumerat; "HandleEnumerateUserAssociatedDevices"
0x180099439  mov     [rbp+100h+var_160], rdx
0x18009943d  lea     rax, [rsp+200h+var_1D0]
0x180099442  mov     [rbp+100h+var_158], rax
0x180099446  mov     [rbp+100h+var_150], rcx
0x18009944a  mov     [rbp+100h+var_148], rcx
0x18009944e  xor     r9d, r9d; unsigned int
0x180099451  mov     r8d, 25A6h; char *
0x180099457  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18009945e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180099463  nop
0x180099464  mov     rax, [rbp+100h+var_178]
0x180099468  test    rax, rax
0x18009946b  jz      loc_180099961
0x180099471  test    r13, r13
0x180099474  jz      loc_180099961
0x18009947a  mov     [rax], esi
0x18009947c  mov     [r13+0], rsi
0x180099480  xor     edx, edx; struct ATL::CAccessToken *
0x180099482  lea     rcx, [rsp+200h+var_190]; this
0x180099487  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18009948c  mov     [rsp+200h+var_1D0], eax
0x180099490  test    eax, eax
0x180099492  jns     short loc_1800994C1
0x180099494  lea     rdx, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x18009949b  mov     [rsp+200h+var_1E0], rdx; char *
0x1800994a0  mov     r8d, 25B5h; unsigned int
0x1800994a6  mov     r9d, eax; int
0x1800994a9  lea     rdx, aHandleenumerat; "HandleEnumerateUserAssociatedDevices"
0x1800994b0  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800994b7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800994bc  jmp     loc_1800999AD
0x1800994c1  lea     rdx, [rsp+200h+var_1C0]; struct _LUID *
0x1800994c6  lea     rcx, [rsp+200h+var_190]; this
0x1800994cb  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x1800994d0  mov     [rsp+200h+var_1D0], eax
0x1800994d4  test    eax, eax
0x1800994d6  jns     short loc_1800994EC
0x1800994d8  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x1800994df  mov     [rsp+200h+var_1E0], rcx
0x1800994e4  mov     r8d, 25B6h
0x1800994ea  jmp     short loc_1800994A6
0x1800994ec  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800994f3  add     rcx, 1F0h
0x1800994fa  lea     r9, [rbp+100h+var_180]
0x1800994fe  mov     r8, r14
0x180099501  lea     rdx, [rsp+200h+var_1C0]
0x180099506  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x18009950b  mov     [rsp+200h+var_1D0], eax
0x18009950f  test    eax, eax
0x180099511  jns     short loc_18009952A
0x180099513  lea     rcx, aHrGPppcrlGetid_2; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x18009951a  mov     [rsp+200h+var_1E0], rcx
0x18009951f  mov     r8d, 25BBh
0x180099525  jmp     loc_1800994A6
0x18009952a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180099531  mov     ecx, 160h; unsigned __int64
0x180099536  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009953b  mov     rbx, rax
0x18009953e  mov     qword ptr [rsp+200h+var_1C0.LowPart], rax
0x180099543  test    rax, rax
0x180099546  jz      short loc_1800995A0
0x180099548  mov     rcx, rax; this
0x18009954b  call    ??0CDeviceUserAssociation@@QEAA@XZ; CDeviceUserAssociation::CDeviceUserAssociation(void)
0x180099550  lea     rax, ??_7CEnumDevicesRequest@@6BCPPCRLBaseRequest@@@; const CEnumDevicesRequest::`vftable'{for `CPPCRLBaseRequest'}
0x180099557  mov     [rbx], rax
0x18009955a  lea     rax, ??_7CEnumDevicesRequest@@6BIPPCRLRequest@@@; const CEnumDevicesRequest::`vftable'{for `IPPCRLRequest'}
0x180099561  mov     [rbx+40h], rax
0x180099565  lea     rcx, [rbx+128h]
0x18009956c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180099571  mov     [rbx+130h], rsi
0x180099578  mov     [rbx+138h], rsi
0x18009957f  mov     [rbx+140h], rsi
0x180099586  mov     [rbx+148h], rsi
0x18009958d  mov     [rbx+150h], rsi
0x180099594  mov     dword ptr [rbx+158h], 0Ah
0x18009959e  jmp     short loc_1800995A3
0x1800995a0  mov     rbx, rsi
0x1800995a3  mov     [rsp+200h+var_198], rbx
0x1800995a8  test    rbx, rbx
0x1800995ab  jnz     short loc_1800995BA
0x1800995ad  mov     [rsp+200h+var_1D0], 8007000Eh
0x1800995b5  jmp     loc_1800999AD
0x1800995ba  lea     rax, [rbp+100h+var_C8]
0x1800995be  mov     [rbp+100h+Block], rax
0x1800995c2  mov     r8d, 0FDE9h
0x1800995c8  mov     rdx, r15
0x1800995cb  lea     rcx, [rbp+100h+Block]
0x1800995cf  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x1800995d4  nop
0x1800995d5  mov     rdx, [rbp+100h+Block]
0x1800995d9  lea     rcx, [rsp+200h+var_188]
0x1800995de  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x1800995e3  nop
0x1800995e4  mov     rcx, [rbp+100h+Block]; Block
0x1800995e8  lea     rax, [rbp+100h+var_C8]
0x1800995ec  cmp     rcx, rax
0x1800995ef  jz      short loc_1800995F6
0x1800995f1  call    free
0x1800995f6  mov     r9d, r12d
0x1800995f9  lea     r8, [rsp+200h+var_188]
0x1800995fe  mov     rdi, [rbp+100h+var_180]
0x180099602  mov     rdx, rdi
0x180099605  mov     rcx, rbx
0x180099608  call    ?Initialize@CEnumDevicesRequest@@QEAAJPEAVCSingleIdentity@@AEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@K@Z; CEnumDevicesRequest::Initialize(CSingleIdentity *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ulong)
0x18009960d  mov     [rsp+200h+var_1D0], eax
0x180099611  test    eax, eax
0x180099613  jns     short loc_18009962C
0x180099615  lea     rcx, aHrPenumdevices; "hr = pEnumDevicesRequest->Initialize(pU"...
0x18009961c  mov     [rsp+200h+var_1E0], rcx
0x180099621  mov     r8d, 25C4h
0x180099627  jmp     loc_1800994A6
0x18009962c  mov     [rbp+100h+var_140], si
0x180099630  mov     [rbp+100h+var_138], rsi
0x180099634  mov     [rbp+100h+var_130], rsi
0x180099638  mov     [rbp+100h+var_128], rsi
0x18009963c  mov     [rbp+100h+var_120], si
0x180099640  mov     [rbp+100h+var_118], rsi
0x180099644  mov     [rbp+100h+var_110], esi
0x180099647  mov     [rbp+100h+var_108], rsi
0x18009964b  mov     [rbp+100h+var_100], esi
0x18009964e  xorps   xmm0, xmm0
0x180099651  xor     eax, eax
0x180099653  movups  [rbp+100h+var_F8], xmm0
0x180099657  movups  [rbp+100h+var_E8], xmm0
0x18009965b  mov     [rbp+100h+var_D8], rax
0x18009965f  add     rdi, 10h
0x180099663  mov     qword ptr [rsp+200h+var_1C0.LowPart], rdi
0x180099668  mov     [rsp+200h+var_1B8], sil
0x18009966d  lea     rcx, [rsp+200h+var_1C0]
0x180099672  call    ?Lock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(void)
0x180099677  mov     [rsp+200h+var_1D0], eax
0x18009967b  test    eax, eax
0x18009967d  jns     short loc_1800996C1
0x18009967f  lea     rcx, aHrLockLock; "hr = lock.Lock()"
0x180099686  mov     r8d, 25CCh; unsigned int
0x18009968c  mov     [rsp+200h+var_1E0], rcx; char *
0x180099691  mov     r9d, eax; int
0x180099694  lea     rdx, aHandleenumerat; "HandleEnumerateUserAssociatedDevices"
0x18009969b  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800996a2  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800996a7  nop
0x1800996a8  lea     rcx, [rsp+200h+var_1C0]
0x1800996ad  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x1800996b2  nop
0x1800996b3  lea     rcx, [rbp+100h+var_140]; this
0x1800996b7  call    ??1CTransport@@QEAA@XZ; CTransport::~CTransport(void)
0x1800996bc  jmp     loc_1800999AD
0x1800996c1  mov     rax, [rbx]
0x1800996c4  mov     rcx, rbx
0x1800996c7  mov     rax, [rax+160h]
0x1800996ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996d3  mov     [rsp+200h+var_1D0], eax
0x1800996d7  test    eax, eax
0x1800996d9  jns     short loc_1800996EA
0x1800996db  lea     rcx, aHrPenumdevices_0; "hr = pEnumDevicesRequest->BuildRequest("...
0x1800996e2  mov     r8d, 25CFh
0x1800996e8  jmp     short loc_18009968C
0x1800996ea  mov     rdx, rbx; struct CDeviceUserAssociation *
0x1800996ed  lea     rcx, [rbp+100h+var_140]; this
0x1800996f1  call    ?SendDeviceRequest@CTransport@@QEAAJPEAVCDeviceUserAssociation@@@Z; CTransport::SendDeviceRequest(CDeviceUserAssociation *)
0x1800996f6  mov     [rsp+200h+var_1D0], eax
0x1800996fa  test    eax, eax
0x1800996fc  jns     short loc_180099710
0x1800996fe  lea     rcx, aHrTransportSen_7; "hr = transport.SendDeviceRequest(pEnumD"...
0x180099705  mov     r8d, 25D2h
0x18009970b  jmp     loc_18009968C
0x180099710  lea     rax, [rsp+200h+var_1A8]
0x180099715  mov     [rsp+200h+var_1D8], rax; unsigned int *
0x18009971a  lea     rax, [rsp+200h+var_1AC]
0x18009971f  mov     [rsp+200h+var_1E0], rax; unsigned int *
0x180099724  lea     r9, [rsp+200h+var_1C8]; unsigned __int16 ***
0x180099729  lea     r8, [rsp+200h+hMem]; unsigned __int16 ***
0x18009972e  lea     rdx, [rsp+200h+var_1B0]; unsigned int *
0x180099733  mov     rcx, rbx; this
0x180099736  call    ?GetResponse@CEnumDevicesRequest@@QEAAJPEAKPEAPEAPEAG100@Z; CEnumDevicesRequest::GetResponse(ulong *,ushort * * *,ushort * * *,ulong *,ulong *)
0x18009973b  mov     [rsp+200h+var_1D0], eax
0x18009973f  test    eax, eax
0x180099741  jns     short loc_18009978F
0x180099743  lea     rcx, aHrPenumdevices_1; "hr = pEnumDevicesRequest->GetResponse(&"...
0x18009974a  mov     [rsp+200h+var_1E0], rcx; char *
0x18009974f  mov     r9d, eax; int
0x180099752  mov     r8d, 25DAh; unsigned int
0x180099758  lea     rdx, aHandleenumerat; "HandleEnumerateUserAssociatedDevices"
0x18009975f  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180099766  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18009976b  nop
0x18009976c  lea     rcx, [rsp+200h+var_1C0]
0x180099771  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180099776  nop
0x180099777  lea     rcx, [rbp+100h+var_140]; this
0x18009977b  call    ??1CTransport@@QEAA@XZ; CTransport::~CTransport(void)
0x180099780  mov     rdi, [rsp+200h+hMem]
0x180099785  mov     rsi, [rsp+200h+var_1C8]
0x18009978a  jmp     loc_180099991
0x18009978f  lea     rcx, [rsp+200h+var_1C0]
0x180099794  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180099799  nop
0x18009979a  lea     rcx, [rbp+100h+var_140]; this
0x18009979e  call    ??1CTransport@@QEAA@XZ; CTransport::~CTransport(void)
0x1800997a3  cmp     [rsp+200h+var_1D0], esi
0x1800997a7  jl      short loc_180099780
0x1800997a9  mov     r12d, [rsp+200h+var_1B0]
0x1800997ae  test    r12d, r12d
0x1800997b1  jz      short loc_180099780
0x1800997b3  cmp     [rsp+200h+var_1AC], esi
0x1800997b7  jbe     short loc_180099780
0x1800997b9  cmp     [rsp+200h+var_1A8], esi
0x1800997bd  jbe     short loc_180099780
0x1800997bf  mov     rsi, [rsp+200h+var_1C8]
0x1800997c4  mov     rdi, [rsp+200h+hMem]
0x1800997c9  test    rsi, rsi
0x1800997cc  jz      loc_180099991
0x1800997d2  test    rdi, rdi
0x1800997d5  jz      loc_18009999F
0x1800997db  mov     r14d, r12d
0x1800997de  shl     r14, 4
0x1800997e2  mov     rcx, r14; Size
0x1800997e5  call    cs:__imp_malloc
0x1800997eb  mov     r15, rax
0x1800997ee  test    rax, rax
0x1800997f1  jnz     short loc_180099800
0x1800997f3  mov     [rsp+200h+var_1D0], 8007000Eh
0x1800997fb  jmp     loc_180099991
0x180099800  mov     r8, r14; Size
0x180099803  xor     edx, edx; Val
0x180099805  mov     rcx, r15; void *
0x180099808  call    memset_0
0x18009980d  xor     r8d, r8d
0x180099810  mov     r13d, r8d
0x180099813  cmp     r13d, r12d
0x180099816  jnb     loc_180099951
0x18009981c  mov     eax, r13d
0x18009981f  mov     [rsp+200h+var_1C8], rax
0x180099824  shl     rax, 3
0x180099828  mov     qword ptr [rsp+200h+var_1C0.LowPart], rax
0x18009982d  mov     rax, [rax+rdi]
0x180099831  test    rax, rax
0x180099834  jz      short loc_180099846
0x180099836  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009983a  inc     r14
0x18009983d  cmp     [rax+r14*2], r8w
0x180099842  jnz     short loc_18009983A
0x180099844  jmp     short loc_180099849
0x180099846  mov     r14d, r8d
0x180099849  lea     eax, [r14+1]
0x18009984d  mov     [rsp+200h+var_198], rax
0x180099852  lea     rcx, [rax+rax]; Size
0x180099856  call    cs:__imp_malloc
0x18009985c  mov     r9, rax
0x18009985f  mov     rax, [rsp+200h+var_1C8]
0x180099864  shl     rax, 4
0x180099868  mov     [rsp+200h+var_1C8], rax
0x18009986d  mov     [rax+r15], r9
0x180099871  test    r9, r9
0x180099874  jz      loc_1800997F3
0x18009987a  mov     r8d, r14d
0x18009987d  xor     ecx, ecx
0x18009987f  mov     [r9+r8*2], cx
0x180099884  mov     r10, qword ptr [rsp+200h+var_1C0.LowPart]
0x180099889  mov     r8, [r10+rdi]; unsigned __int16 *
  ... truncated ...
```
