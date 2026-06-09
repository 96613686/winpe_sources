# CVssProviderManager::GetProviderInterfaceInternal(CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>> &,_GUID,long,_GUID,_VSS_PROVIDER_TYPE,ATL::CComPtr<IVssSnapshotProvider> &)

- ea: `0x14001818c`
- end: `0x140018daa`
- name: `?GetProviderInterfaceInternal@CVssProviderManager@@CAHAEAV?$CVssSimpleMap@U_GUID@@V?$CComPtr@UIVssSnapshotProvider@@@ATL@@@@U_GUID@@J1W4_VSS_PROVIDER_TYPE@@AEAV?$CComPtr@UIVssSnapshotProvider@@@ATL@@@Z`
- size: `3102`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140005c38`
- `0x140016db0`
- `0x14009e168`

## callees

- `0x140006020`
- `0x140007250`
- `0x1400088fc`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14001818c`
- `0x140019760`
- `0x140019990`
- `0x14001b9c0`
- `0x14001d69c`
- `0x1400281a0`
- `0x14003c160`
- `0x140042acc`
- `0x140046a64`
- `0x140049ec4`
- `0x140055ba4`
- `0x140056084`
- `0x1400562c8`
- `0x140063078`
- `0x1400921dc`
- `0x140099a60`
- `0x1400cbe80`
- `0x1400da308`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14001899b`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1400189c3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140018b72`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140018b93`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14001899b`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1400189c3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140018b72`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140018b93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018236`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018236`
- `VssTrace!__imp_VssTraceMessage` at `0x140018320`
- `VssTrace!__imp_VssTraceMessage` at `0x140018320`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140018289`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140018289`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001827b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001827b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 CVssProviderManager::GetProviderInterfaceInternal(__int64 a1, struct _GUID *a2, int a3, ...)
{
  unsigned __int8 *v3; // r14
  unsigned int v6; // r15d
  int v7; // eax
  __int64 v8; // rcx
  int v9; // ebx
  struct _GUID *v10; // rdi
  int v11; // ebx
  unsigned int v12; // esi
  struct IUnknown **v13; // r14
  int i; // edx
  _QWORD *v16; // rcx
  __int64 v17; // rax
  int j; // eax
  _QWORD *v19; // rdx
  __int64 v20; // rcx
  struct IUnknown *v21; // rbx
  int v22; // eax
  unsigned int k; // ebx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // ebx
  struct IVssSnapshotProvider *v28; // rax
  int m; // edx
  void *v30; // rbx
  _QWORD *v31; // rcx
  __int64 v32; // rax
  __int64 *v33; // rdi
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r9
  struct _GUID *v38; // r8
  __int64 *v39; // rcx
  __int64 *v40; // rax
  int v41; // eax
  __int64 *v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  struct _GUID *v46; // r8
  __int64 *v47; // rcx
  __int64 *v48; // rax
  __int64 v49; // [rsp+28h] [rbp-E0h]
  __int64 v50; // [rsp+28h] [rbp-E0h]
  __int64 v51; // [rsp+28h] [rbp-E0h]
  __int64 v52; // [rsp+28h] [rbp-E0h]
  __int64 v53; // [rsp+30h] [rbp-D8h]
  __int64 v54; // [rsp+30h] [rbp-D8h]
  __int64 v55; // [rsp+38h] [rbp-D0h]
  __int64 v56; // [rsp+38h] [rbp-D0h]
  __int64 v57; // [rsp+40h] [rbp-C8h]
  __int64 v58; // [rsp+40h] [rbp-C8h]
  __int64 v59; // [rsp+48h] [rbp-C0h]
  __int64 v60; // [rsp+48h] [rbp-C0h]
  __int64 v61; // [rsp+50h] [rbp-B8h]
  __int64 v62; // [rsp+58h] [rbp-B0h]
  __int64 v63; // [rsp+60h] [rbp-A8h]
  __int64 v64; // [rsp+68h] [rbp-A0h]
  __int64 v65; // [rsp+70h] [rbp-98h]
  __int64 v66; // [rsp+78h] [rbp-90h]
  struct _GUID v67; // [rsp+88h] [rbp-80h] BYREF
  const unsigned __int16 *v68; // [rsp+98h] [rbp-70h] BYREF
  const wchar_t *v69; // [rsp+A0h] [rbp-68h]
  const unsigned __int16 *v70; // [rsp+A8h] [rbp-60h]
  int v71; // [rsp+B0h] [rbp-58h]
  int v72; // [rsp+B4h] [rbp-54h]
  int v73; // [rsp+B8h] [rbp-50h]
  _BYTE v74[120]; // [rsp+C0h] [rbp-48h] BYREF
  int v75; // [rsp+138h] [rbp+30h]
  struct _GUID v76; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 v77; // [rsp+158h] [rbp+50h] BYREF
  int v78; // [rsp+160h] [rbp+58h]
  const unsigned __int16 *v79; // [rsp+168h] [rbp+60h]
  const unsigned __int16 *v80; // [rsp+170h] [rbp+68h]
  unsigned int v81; // [rsp+178h] [rbp+70h]
  int v82; // [rsp+17Ch] [rbp+74h]
  const wchar_t *v83; // [rsp+180h] [rbp+78h]
  unsigned int v84; // [rsp+188h] [rbp+80h]
  DWORD TickCount; // [rsp+18Ch] [rbp+84h]
  int v86; // [rsp+190h] [rbp+88h]
  __int128 v87; // [rsp+198h] [rbp+90h]
  __int128 v88; // [rsp+1A8h] [rbp+A0h]
  __int64 v89; // [rsp+1B8h] [rbp+B0h]
  __int64 v90; // [rsp+210h] [rbp+108h] BYREF
  int v91; // [rsp+218h] [rbp+110h]
  void *Buf1; // [rsp+220h] [rbp+118h] BYREF
  va_list Buf1a; // [rsp+220h] [rbp+118h]
  __int64 v94; // [rsp+228h] [rbp+120h]
  struct IUnknown **v95; // [rsp+230h] [rbp+128h]
  va_list va1; // [rsp+238h] [rbp+130h] BYREF

  va_start(va1, a3);
  va_start(Buf1a, a3);
  Buf1 = va_arg(va1, void *);
  v94 = va_arg(va1, _QWORD);
  v95 = va_arg(va1, struct IUnknown **);
  v91 = a3;
  v3 = (unsigned __int8 *)Buf1;
  v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
  v70 = L"CORPRVMC";
  v71 = 482;
  v6 = 1;
  v72 = 1;
  v73 = 255;
  v75 = 0x1000000;
  memset_0(v74, 0, sizeof(v74));
  v78 = 0;
  v83 = L"CVssProviderManager::GetProviderInterfaceInternal";
  v79 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v80 = L"CORPRVMC";
  v81 = 482;
  v82 = 1;
  TickCount = GetTickCount();
  v86 = 255;
  v77 = 0xFFFFFFFF00000000uLL;
  v89 = 0;
  v87 = 0;
  v88 = 0;
  v90 = 0;
  if ( (int)VssGetTracingContextPerThread(&v90) < 0 )
  {
    v8 = v89;
  }
  else
  {
    v7 = VssSetTracingContextPerThread(&v77);
    v8 = v89;
    if ( v7 >= 0 )
      v8 = v90;
    v89 = v8;
  }
  if ( v8 )
    v84 = *(_DWORD *)(v8 + 48) + 1;
  else
    v84 = 0;
  v9 = 160;
  if ( v86 != 255 )
    v9 = v86;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v77) )
    VssTraceMessage(v79, v80, v81, v84, v82, v83, L"ENTER", v9, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v68);
  v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
  v70 = L"CORPRVMC";
  v71 = 484;
  v72 = 1;
  v73 = 255;
  v75 = 0x1000000;
  memset_0(v74, 0, sizeof(v74));
  CVssFunctionTracer::AddOperation((__int64)&v77, (__int64)&v68, 0x1B4u);
  v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
  v70 = L"CORPRVMC";
  v71 = 485;
  v72 = 1;
  v73 = 255;
  v75 = 0x1000000;
  memset_0(v74, 0, sizeof(v74));
  LODWORD(v59) = a2->Data4[1];
  LODWORD(v57) = a2->Data4[0];
  LODWORD(v55) = a2->Data3;
  LODWORD(v53) = a2->Data2;
  LODWORD(v49) = a2->Data1;
  CVssFunctionTracer::AddContextEx(
    (__int64)&v77,
    (__int64)&v68,
    0x1391u,
    L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
    v49,
    v53,
    v55,
    v57,
    v59,
    a2->Data4[2],
    a2->Data4[3],
    a2->Data4[4],
    a2->Data4[5],
    a2->Data4[6],
    a2->Data4[7]);
  v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
  v70 = L"CORPRVMC";
  v71 = 486;
  v72 = 1;
  v73 = 255;
  v75 = 0x1000000;
  memset_0(v74, 0, sizeof(v74));
  LODWORD(v66) = v3[15];
  LODWORD(v65) = v3[14];
  LODWORD(v64) = v3[13];
  LODWORD(v63) = v3[12];
  LODWORD(v62) = v3[11];
  LODWORD(v61) = v3[10];
  LODWORD(v60) = v3[9];
  LODWORD(v58) = v3[8];
  LODWORD(v56) = *((unsigned __int16 *)v3 + 3);
  LODWORD(v54) = *((unsigned __int16 *)v3 + 2);
  v10 = (struct _GUID *)Buf1;
  LODWORD(v50) = *(_DWORD *)Buf1;
  CVssFunctionTracer::AddContextEx(
    (__int64)&v77,
    (__int64)&v68,
    0x1397u,
    L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
    v50,
    v54,
    v56,
    v58,
    v60,
    v61,
    v62,
    v63,
    v64,
    v65,
    v66);
  v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
  v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
  v70 = L"CORPRVMC";
  v71 = 487;
  v72 = 1;
  v73 = 255;
  v75 = 0x1000000;
  memset_0(v74, 0, sizeof(v74));
  v11 = v91;
  LODWORD(v51) = v91;
  CVssFunctionTracer::AddContextEx((__int64)&v77, (__int64)&v68, 0x1395u, L"%d", v51);
  v12 = v11 & 0xFD3FFFFF;
  if ( v11 == -1 )
    v12 = -1;
  v13 = v95;
  ATL::CComPtr<IVssSnapshotSetDescription>::operator=(v95, 0);
  if ( v12 != -1 && (v12 & 4) != 0 && memcmp_0(a2, qword_1400FBAE0, 0x10u) )
  {
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v77);
    return 0;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a1 + 16) )
      goto LABEL_39;
    v16 = (_QWORD *)(*(_QWORD *)a1 + 16LL * i);
    v17 = *v16 - *(_QWORD *)&a2->Data1;
    if ( *v16 == *(_QWORD *)&a2->Data1 )
      v17 = v16[1] - *(_QWORD *)a2->Data4;
    if ( !v17 )
      break;
  }
  if ( i != -1 )
  {
    v67 = *a2;
    for ( j = 0; j < *(_DWORD *)(a1 + 16); ++j )
    {
      v19 = (_QWORD *)(*(_QWORD *)a1 + 16LL * j);
      v20 = *v19 - *(_QWORD *)&v67.Data1;
      if ( *v19 == *(_QWORD *)&v67.Data1 )
        v20 = v19[1] - *(_QWORD *)v67.Data4;
      if ( !v20 )
      {
        if ( j != -1 )
        {
          ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(
            (__int64 *)Buf1a,
            (__int64 *)(*(_QWORD *)(a1 + 8) + 8LL * j));
          goto LABEL_35;
        }
        break;
      }
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>((void **)Buf1a);
LABEL_35:
    v21 = (struct IUnknown *)Buf1;
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)Buf1a);
    if ( !v21 )
      goto LABEL_49;
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v90);
    v22 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *, __int64 *))v21->lpVtbl[1].QueryInterface)(
            v21,
            qword_1400FB148,
            &v90);
    v78 = v22;
    if ( (int)(v22 + 0x80000000) < 0 || v22 == -2147467262 )
    {
      ATL::CComPtr<IVssSnapshotSetDescription>::operator=(v13, v21);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v90);
      goto LABEL_93;
    }
    v67 = *a2;
    CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::Remove(a1, &v67);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v90);
  }
LABEL_39:
  ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>((void **)Buf1a);
  if ( !memcmp_0(v10, &GUID_NULL, 0x10u) )
  {
    CVssProviderManager::LoadInternalProvidersArray();
    for ( k = 0; (signed int)k < *((_DWORD *)CVssProviderManager::m_pProvidersArray + 4); ++k )
    {
      v24 = ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::operator[](
              (char *)CVssProviderManager::m_pProvidersArray + 8,
              k);
      v25 = *(_QWORD *)v24;
      v26 = *(_QWORD *)(*(_QWORD *)v24 + 8LL) - *(_QWORD *)&a2->Data1;
      if ( !v26 )
        v26 = *(_QWORD *)(v25 + 16) - *(_QWORD *)a2->Data4;
      if ( !v26 )
      {
        *v10 = *(struct _GUID *)(v25 + 64);
        v27 = *(_DWORD *)(v25 + 32);
        goto LABEL_51;
      }
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)Buf1a);
LABEL_49:
    v6 = 0;
    goto LABEL_93;
  }
  v27 = v94;
LABEL_51:
  switch ( v27 )
  {
    case 1:
    case 2:
      v76 = *v10;
      v67 = *a2;
      v28 = CVssSoftwareProviderWrapper::CreateInstance(&v67, &v76);
      break;
    case 3:
      v76 = *v10;
      v67 = *a2;
      v28 = CVssHardwareProviderWrapper::CreateInstance(&v67, &v76);
      break;
    case 4:
      v67 = *v10;
      v76 = *a2;
      v28 = CVssFileShareProviderWrapper::CreateInstance(&v76, &v67);
      break;
    default:
      v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
      v70 = L"CORPRVMC";
      v71 = 586;
      v72 = 1;
      v73 = 255;
      v75 = 0x1000000;
      memset_0(v74, 0, sizeof(v74));
      LODWORD(v52) = v27;
      CVssFunctionTracer::TranslateGenericError(&v77, &v68, 2147549183LL, L"Unexpected provider type %d", v52);
  }
  ATL::CComPtrBase<IXMLDOMNode>::Attach((void **)Buf1a, v28);
  for ( m = 0; ; ++m )
  {
    v30 = Buf1;
    if ( m >= dword_14014FB10 )
      break;
    v31 = (_QWORD *)(CVssProviderManager::m_mapProviderItfOnLoadCache + 16LL * m);
    v32 = *v31 - *(_QWORD *)&a2->Data1;
    if ( *v31 == *(_QWORD *)&a2->Data1 )
      v32 = v31[1] - *(_QWORD *)a2->Data4;
    if ( !v32 )
    {
      if ( m != -1 )
        goto LABEL_76;
      break;
    }
  }
  v78 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)Buf1 + 272LL))(Buf1, 0);
  if ( v78 < 0 )
  {
    v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
    v70 = L"CORPRVMC";
    v71 = 597;
    v72 = 1;
    v73 = 255;
    v75 = 0x1000000;
    memset_0(v74, 0, sizeof(v74));
    v76 = *a2;
    CVssFunctionTracer::TranslateProviderError(&v77, &v68, &v76, L"IVssProviderNotifications::OnLoad");
  }
  v33 = ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>((__int64 *)&v67, (__int64 *)Buf1a);
  v34 = _o_realloc(CVssProviderManager::m_mapProviderItfOnLoadCache, 16LL * (dword_14014FB10 + 1));
  if ( !v34
    || (CVssProviderManager::m_mapProviderItfOnLoadCache = v34,
        v35 = _o_realloc(qword_14014FB08, 8LL * (dword_14014FB10 + 1)),
        (v36 = v35) == 0) )
  {
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v33);
    v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
    v70 = L"CORPRVMC";
    v71 = 601;
    v72 = 1;
    v73 = 255;
    v75 = 0x1000000;
    memset_0(v74, 0, sizeof(v74));
    CVssFunctionTracer::Throw(&v77, &v68, 2147942414LL, L"Memory allocation error.");
  }
  qword_14014FB08 = v35;
  v37 = dword_14014FB10++;
  v38 = (struct _GUID *)(CVssProviderManager::m_mapProviderItfOnLoadCache + 16 * v37);
  if ( v38 )
  {
    *v38 = *a2;
    v36 = qword_14014FB08;
  }
  v39 = (__int64 *)(v36 + 8 * v37);
  if ( v39 )
    ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(v39, v33);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v33);
LABEL_76:
  if ( v12 )
  {
    v41 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v30 + 32LL))(v30, v12);
    v78 = v41;
    if ( v41 == -2147212517 )
    {
      v42 = ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v67);
      v43 = _o_realloc(*(_QWORD *)a1, 16LL * (*(_DWORD *)(a1 + 16) + 1));
      if ( !v43 || (*(_QWORD *)a1 = v43, (v44 = _o_realloc(*(_QWORD *)(a1 + 8), 8LL * (*(_DWORD *)(a1 + 16) + 1))) == 0) )
      {
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v42);
        v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
        v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
        v70 = L"CORPRVMC";
        v71 = 627;
        v72 = 1;
        v73 = 255;
        v75 = 0x1000000;
        memset_0(v74, 0, sizeof(v74));
        CVssFunctionTracer::Throw(&v77, &v68, 2147942414LL, L"Memory allocation error.");
      }
      *(_QWORD *)(a1 + 8) = v44;
      v45 = *(int *)(a1 + 16);
      *(_DWORD *)(a1 + 16) = v45 + 1;
      v46 = (struct _GUID *)(*(_QWORD *)a1 + 16 * v45);
      if ( v46 )
        *v46 = *a2;
      v47 = (__int64 *)(*(_QWORD *)(a1 + 8) + 8 * v45);
      if ( v47 )
        ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(v47, v42);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v42);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)Buf1a);
      v6 = 0;
      goto LABEL_93;
    }
    if ( v41 < 0 )
    {
      v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
      v70 = L"CORPRVMC";
      v71 = 633;
      v72 = 1;
      v73 = 255;
      v75 = 0x1000000;
      memset_0(v74, 0, sizeof(v74));
      v76 = *a2;
      CVssFunctionTracer::TranslateProviderError(&v77, &v68, &v76, L"IVssSnapshotProvider::SetContext");
    }
    v48 = ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(&v90, (__int64 *)Buf1a);
    v76 = *a2;
    if ( !(unsigned int)CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::Add(a1, &v76, v48) )
    {
      v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
      v70 = L"CORPRVMC";
      v71 = 637;
      v72 = 1;
      v73 = 255;
      v75 = 0x1000000;
      memset_0(v74, 0, sizeof(v74));
      CVssFunctionTracer::Throw(&v77, &v68, 2147942414LL, L"Memory allocation error.");
    }
  }
  else
  {
    v40 = ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(&v90, (__int64 *)Buf1a);
    v76 = *a2;
    if ( !(unsigned int)CVssSimpleMap<_GUID,ATL::CComPtr<IVssSnapshotProvider>>::Add(a1, &v76, v40) )
    {
      v68 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
      v69 = L"CVssProviderManager::GetProviderInterfaceInternal";
      v70 = L"CORPRVMC";
      v71 = 615;
      v72 = 1;
      v73 = 255;
      v75 = 0x1000000;
      memset_0(v74, 0, sizeof(v74));
      CVssFunctionTracer::Throw(&v77, &v68, 2147942414LL, L"Memory allocation error.");
    }
  }
  ATL::CComPtr<IVssSnapshotProvider>::operator=(v13, (struct IUnknown **)Buf1a);
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)Buf1a);
LABEL_93:
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v77);
  return v6;
}

```

## disassembly

```asm
0x14001818c  mov     rax, rsp
0x14001818f  mov     [rax+8], rbx
0x140018193  mov     [rax+20h], r9
0x140018197  mov     [rax+18h], r8d
0x14001819b  push    rbp
0x14001819c  push    rsi
0x14001819d  push    rdi
0x14001819e  push    r12
0x1400181a0  push    r13
0x1400181a2  push    r14
0x1400181a4  push    r15
0x1400181a6  lea     rbp, [rax-0F8h]
0x1400181ad  sub     rsp, 1C0h
0x1400181b4  mov     r14, r9
0x1400181b7  mov     r12, rdx
0x1400181ba  mov     r13, rcx
0x1400181bd  lea     rax, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x1400181c4  mov     [rbp+0F0h+var_160], rax
0x1400181c8  lea     rax, aCvssproviderma_14; "CVssProviderManager::GetProviderInterfa"...
0x1400181cf  mov     [rbp+0F0h+var_158], rax
0x1400181d3  lea     rax, aCorprvmc; "CORPRVMC"
0x1400181da  mov     [rbp+0F0h+var_150], rax
0x1400181de  mov     [rbp+0F0h+var_148], 1E2h
0x1400181e5  mov     r15d, 1
0x1400181eb  mov     [rbp+0F0h+var_144], r15d
0x1400181ef  mov     esi, 0FFh
0x1400181f4  mov     [rbp+0F0h+var_140], esi
0x1400181f7  xor     edi, edi
0x1400181f9  mov     [rbp+0F0h+var_C0], 1000000h
0x140018200  xor     edx, edx; Val
0x140018202  lea     r8d, [r15+77h]; Size
0x140018206  lea     rcx, [rbp+0F0h+var_138]; void *
0x14001820a  call    memset_0
0x14001820f  mov     [rbp+0F0h+var_98], edi
0x140018212  mov     rax, [rbp+0F0h+var_158]
0x140018216  mov     [rbp+0F0h+var_78], rax
0x14001821a  mov     rax, [rbp+0F0h+var_160]
0x14001821e  mov     [rbp+0F0h+var_90], rax
0x140018222  mov     rax, [rbp+0F0h+var_150]
0x140018226  mov     [rbp+0F0h+var_88], rax
0x14001822a  mov     eax, [rbp+0F0h+var_148]
0x14001822d  mov     [rbp+0F0h+var_80], eax
0x140018230  mov     eax, [rbp+0F0h+var_144]
0x140018233  mov     [rbp+0F0h+var_7C], eax
0x140018236  call    cs:__imp_GetTickCount
0x14001823c  mov     [rbp+0F0h+var_6C], eax
0x140018242  mov     [rbp+0F0h+var_9C], 0FFFFFFFFh
0x140018249  mov     eax, [rbp+0F0h+var_140]
0x14001824c  mov     [rbp+0F0h+var_68], eax
0x140018252  mov     [rbp+0F0h+var_A0], edi
0x140018255  mov     [rbp+0F0h+var_40], rdi
0x14001825c  xorps   xmm0, xmm0
0x14001825f  movups  [rbp+0F0h+var_60], xmm0
0x140018266  movups  [rbp+0F0h+var_50], xmm0
0x14001826d  mov     [rbp+0F0h+arg_8], rdi
0x140018274  lea     rcx, [rbp+0F0h+arg_8]
0x14001827b  call    cs:__imp_VssGetTracingContextPerThread
0x140018281  test    eax, eax
0x140018283  js      short loc_1400182A9
0x140018285  lea     rcx, [rbp+0F0h+var_A0]
0x140018289  call    cs:__imp_VssSetTracingContextPerThread
0x14001828f  mov     rcx, [rbp+0F0h+var_40]
0x140018296  test    eax, eax
0x140018298  cmovns  rcx, [rbp+0F0h+arg_8]
0x1400182a0  mov     [rbp+0F0h+var_40], rcx
0x1400182a7  jmp     short loc_1400182B0
0x1400182a9  mov     rcx, [rbp+0F0h+var_40]
0x1400182b0  test    rcx, rcx
0x1400182b3  jz      short loc_1400182C3
0x1400182b5  mov     eax, [rcx+30h]
0x1400182b8  add     eax, r15d
0x1400182bb  mov     [rbp+0F0h+var_70], eax
0x1400182c1  jmp     short loc_1400182C9
0x1400182c3  mov     [rbp+0F0h+var_70], edi
0x1400182c9  mov     ebx, 0A0h
0x1400182ce  cmp     [rbp+0F0h+var_68], esi
0x1400182d4  cmovnz  ebx, [rbp+0F0h+var_68]
0x1400182db  lea     rcx, [rbp+0F0h+var_A0]; this
0x1400182df  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x1400182e4  test    eax, eax
0x1400182e6  jz      short loc_140018326
0x1400182e8  mov     [rsp+1F0h+var_1B0], rdi
0x1400182ed  mov     dword ptr [rsp+1F0h+var_1B8], ebx
0x1400182f1  lea     rax, aEnter; "ENTER"
0x1400182f8  mov     [rsp+1F0h+var_1C0], rax
0x1400182fd  mov     rax, [rbp+0F0h+var_78]
0x140018301  mov     [rsp+1F0h+var_1C8], rax
0x140018306  mov     eax, [rbp+0F0h+var_7C]
0x140018309  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x14001830d  mov     r9d, [rbp+0F0h+var_70]
0x140018314  mov     r8d, [rbp+0F0h+var_80]
0x140018318  mov     rdx, [rbp+0F0h+var_88]
0x14001831c  mov     rcx, [rbp+0F0h+var_90]
0x140018320  call    cs:__imp_VssTraceMessage
0x140018326  lea     rcx, [rbp+0F0h+var_160]; this
0x14001832a  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14001832f  nop
0x140018330  lea     rbx, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140018337  mov     [rbp+0F0h+var_160], rbx
0x14001833b  lea     rax, aCvssproviderma_14; "CVssProviderManager::GetProviderInterfa"...
0x140018342  mov     [rbp+0F0h+var_158], rax
0x140018346  lea     rax, aCorprvmc; "CORPRVMC"
0x14001834d  mov     [rbp+0F0h+var_150], rax
0x140018351  mov     [rbp+0F0h+var_148], 1E4h
0x140018358  mov     [rbp+0F0h+var_144], r15d
0x14001835c  mov     [rbp+0F0h+var_140], esi
0x14001835f  mov     [rbp+0F0h+var_C0], 1000000h
0x140018366  xor     edx, edx; Val
0x140018368  lea     r8d, [rdx+78h]; Size
0x14001836c  lea     rcx, [rbp+0F0h+var_138]; void *
0x140018370  call    memset_0
0x140018375  mov     r8d, 1B4h
0x14001837b  lea     rdx, [rbp+0F0h+var_160]
0x14001837f  lea     rcx, [rbp+0F0h+var_A0]
0x140018383  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x140018388  mov     [rbp+0F0h+var_160], rbx
0x14001838c  lea     rax, aCvssproviderma_14; "CVssProviderManager::GetProviderInterfa"...
0x140018393  mov     [rbp+0F0h+var_158], rax
0x140018397  lea     rax, aCorprvmc; "CORPRVMC"
0x14001839e  mov     [rbp+0F0h+var_150], rax
0x1400183a2  mov     [rbp+0F0h+var_148], 1E5h
0x1400183a9  mov     [rbp+0F0h+var_144], r15d
0x1400183ad  mov     [rbp+0F0h+var_140], esi
0x1400183b0  mov     [rbp+0F0h+var_C0], 1000000h
0x1400183b7  xor     edx, edx; Val
0x1400183b9  lea     r8d, [rdx+78h]; Size
0x1400183bd  lea     rcx, [rbp+0F0h+var_138]; void *
0x1400183c1  call    memset_0
0x1400183c6  movzx   eax, byte ptr [r12+0Fh]
0x1400183cc  movzx   ecx, byte ptr [r12+0Eh]
0x1400183d2  movzx   edx, byte ptr [r12+0Dh]
0x1400183d8  movzx   r8d, byte ptr [r12+0Ch]
0x1400183de  movzx   r9d, byte ptr [r12+0Bh]
0x1400183e4  movzx   r10d, byte ptr [r12+0Ah]
0x1400183ea  movzx   r11d, byte ptr [r12+9]
0x1400183f0  movzx   ebx, byte ptr [r12+8]
0x1400183f6  movzx   edi, word ptr [r12+6]
0x1400183fc  movzx   esi, word ptr [r12+4]
0x140018402  mov     [rsp+70h], eax
0x140018406  mov     dword ptr [rsp+1F0h+var_188], ecx
0x14001840a  mov     dword ptr [rsp+1F0h+var_190], edx
0x14001840e  mov     dword ptr [rsp+1F0h+var_198], r8d
0x140018413  mov     dword ptr [rsp+1F0h+var_1A0], r9d
0x140018418  mov     dword ptr [rsp+1F0h+var_1A8], r10d
0x14001841d  mov     dword ptr [rsp+1F0h+var_1B0], r11d
0x140018422  mov     dword ptr [rsp+1F0h+var_1B8], ebx
0x140018426  mov     dword ptr [rsp+1F0h+var_1C0], edi
0x14001842a  mov     dword ptr [rsp+1F0h+var_1C8], esi
0x14001842e  mov     eax, [r12]
0x140018432  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x140018436  lea     r9, a8x4x4x2x2x2x2x; "{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%."...
0x14001843d  mov     r8d, 1391h
0x140018443  lea     rdx, [rbp+0F0h+var_160]
0x140018447  lea     rcx, [rbp+0F0h+var_A0]
0x14001844b  call    ?AddContextEx@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddContextEx(CVssDebugInfo,uint,ushort const *,...)
0x140018450  lea     rax, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140018457  mov     [rbp+0F0h+var_160], rax
0x14001845b  lea     rax, aCvssproviderma_14; "CVssProviderManager::GetProviderInterfa"...
0x140018462  mov     [rbp+0F0h+var_158], rax
0x140018466  lea     rax, aCorprvmc; "CORPRVMC"
0x14001846d  mov     [rbp+0F0h+var_150], rax
0x140018471  mov     [rbp+0F0h+var_148], 1E6h
0x140018478  mov     [rbp+0F0h+var_144], r15d
0x14001847c  mov     [rbp+0F0h+var_140], 0FFh
0x140018483  mov     [rbp+0F0h+var_C0], 1000000h
0x14001848a  xor     edx, edx; Val
0x14001848c  lea     r8d, [rdx+78h]; Size
0x140018490  lea     rcx, [rbp+0F0h+var_138]; void *
0x140018494  call    memset_0
0x140018499  movzx   eax, byte ptr [r14+0Fh]
0x14001849e  movzx   ecx, byte ptr [r14+0Eh]
0x1400184a3  movzx   edx, byte ptr [r14+0Dh]
0x1400184a8  movzx   r8d, byte ptr [r14+0Ch]
0x1400184ad  movzx   r10d, byte ptr [r14+0Bh]
0x1400184b2  movzx   r11d, byte ptr [r14+0Ah]
0x1400184b7  movzx   ebx, byte ptr [r14+9]
0x1400184bc  movzx   edi, byte ptr [r14+8]
0x1400184c1  movzx   esi, word ptr [r14+6]
0x1400184c6  movzx   r14d, word ptr [r14+4]
0x1400184cb  mov     [rsp+70h], eax
0x1400184cf  mov     dword ptr [rsp+1F0h+var_188], ecx
0x1400184d3  mov     dword ptr [rsp+1F0h+var_190], edx
0x1400184d7  mov     dword ptr [rsp+1F0h+var_198], r8d
0x1400184dc  mov     dword ptr [rsp+1F0h+var_1A0], r10d
0x1400184e1  mov     dword ptr [rsp+1F0h+var_1A8], r11d
0x1400184e6  mov     dword ptr [rsp+1F0h+var_1B0], ebx
0x1400184ea  mov     dword ptr [rsp+1F0h+var_1B8], edi
0x1400184ee  mov     dword ptr [rsp+1F0h+var_1C0], esi
0x1400184f2  mov     dword ptr [rsp+1F0h+var_1C8], r14d
0x1400184f7  mov     rdi, [rbp+0F0h+Buf1]
0x1400184fe  mov     eax, [rdi]
0x140018500  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x140018504  lea     r9, a8x4x4x2x2x2x2x; "{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%."...
0x14001850b  mov     r8d, 1397h
0x140018511  lea     rdx, [rbp+0F0h+var_160]
0x140018515  lea     rcx, [rbp+0F0h+var_A0]
0x140018519  call    ?AddContextEx@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddContextEx(CVssDebugInfo,uint,ushort const *,...)
0x14001851e  lea     rax, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140018525  mov     [rbp+0F0h+var_160], rax
0x140018529  lea     rax, aCvssproviderma_14; "CVssProviderManager::GetProviderInterfa"...
0x140018530  mov     [rbp+0F0h+var_158], rax
0x140018534  lea     rax, aCorprvmc; "CORPRVMC"
0x14001853b  mov     [rbp+0F0h+var_150], rax
0x14001853f  mov     [rbp+0F0h+var_148], 1E7h
0x140018546  mov     [rbp+0F0h+var_144], r15d
0x14001854a  mov     [rbp+0F0h+var_140], 0FFh
0x140018551  mov     [rbp+0F0h+var_C0], 1000000h
0x140018558  xor     edx, edx; Val
0x14001855a  lea     r8d, [rdx+78h]; Size
0x14001855e  lea     rcx, [rbp+0F0h+var_138]; void *
0x140018562  call    memset_0
0x140018567  mov     ebx, [rbp+0F0h+arg_10]
0x14001856d  mov     dword ptr [rsp+1F0h+var_1D0], ebx
0x140018571  lea     r9, aD; "%d"
0x140018578  mov     r8d, 1395h
0x14001857e  lea     rdx, [rbp+0F0h+var_160]
0x140018582  lea     rcx, [rbp+0F0h+var_A0]
0x140018586  call    ?AddContextEx@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddContextEx(CVssDebugInfo,uint,ushort const *,...)
0x14001858b  mov     esi, ebx
0x14001858d  and     esi, 0FD3FFFFFh
0x140018593  cmp     ebx, 0FFFFFFFFh
0x140018596  cmovz   esi, ebx
0x140018599  xor     edx, edx
0x14001859b  mov     r14, [rbp+0F0h+arg_28]
0x1400185a2  mov     rcx, r14
0x1400185a5  call    ??4?$CComPtr@VIVssSnapshotSetDescription@@@ATL@@QEAAPEAVIVssSnapshotSetDescription@@PEAV2@@Z; ATL::CComPtr<IVssSnapshotSetDescription>::operator=(IVssSnapshotSetDescription *)
0x1400185aa  cmp     esi, 0FFFFFFFFh
0x1400185ad  jz      short loc_1400185DE
0x1400185af  test    sil, 4
0x1400185b3  jz      short loc_1400185DE
0x1400185b5  mov     r8d, 10h; Size
0x1400185bb  lea     rdx, qword_1400FBAE0; Buf2
0x1400185c2  mov     rcx, r12; Buf1
0x1400185c5  call    memcmp_0
0x1400185ca  test    eax, eax
0x1400185cc  jz      short loc_1400185DE
0x1400185ce  lea     rcx, [rbp+0F0h+var_A0]; this
0x1400185d2  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400185d7  xor     eax, eax
0x1400185d9  jmp     loc_140018D8F
0x1400185de  xor     edx, edx
0x1400185e0  cmp     edx, [r13+10h]
0x1400185e4  jge     loc_140018703
0x1400185ea  movsxd  rcx, edx
0x1400185ed  shl     rcx, 4
0x1400185f1  add     rcx, [r13+0]
0x1400185f5  mov     rax, [rcx]
0x1400185f8  sub     rax, [r12]
0x1400185fc  jnz     short loc_140018607
0x1400185fe  mov     rax, [rcx+8]
0x140018602  sub     rax, [r12+8]
0x140018607  test    rax, rax
0x14001860a  jz      short loc_140018611
0x14001860c  add     edx, r15d
0x14001860f  jmp     short loc_1400185E0
0x140018611  cmp     edx, 0FFFFFFFFh
0x140018614  jz      loc_140018703
0x14001861a  movaps  xmm0, xmmword ptr [r12]
0x14001861f  movdqa  xmmword ptr [rbp+0F0h+var_170.Data1], xmm0
0x140018624  xor     eax, eax
0x140018626  cmp     eax, [r13+10h]
0x14001862a  jge     short loc_140018670
0x14001862c  movsxd  rdx, eax
0x14001862f  shl     rdx, 4
0x140018633  add     rdx, [r13+0]
0x140018637  mov     rcx, [rdx]
0x14001863a  sub     rcx, qword ptr [rbp+0F0h+var_170.Data1]
0x14001863e  jnz     short loc_140018648
0x140018640  mov     rcx, [rdx+8]
0x140018644  sub     rcx, qword ptr [rbp+0F0h+var_170.Data4]
0x140018648  test    rcx, rcx
0x14001864b  jz      short loc_140018652
0x14001864d  add     eax, r15d
0x140018650  jmp     short loc_140018626
0x140018652  cmp     eax, 0FFFFFFFFh
0x140018655  jz      short loc_140018670
0x140018657  movsxd  rcx, eax
0x14001865a  mov     rax, [r13+8]
0x14001865e  lea     rdx, [rax+rcx*8]
0x140018662  lea     rcx, [rbp+0F0h+Buf1]
0x140018669  call    ??0?$CComPtr@UIVssSnapshotProvider@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(ATL::CComPtr<IVssSnapshotProvider> const &)
0x14001866e  jmp     short loc_14001867C
0x140018670  lea     rcx, [rbp+0F0h+Buf1]
0x140018677  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001867c  mov     rbx, [rbp+0F0h+Buf1]
0x140018683  lea     rcx, [rbp+0F0h+Buf1]
0x14001868a  call    ??1?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(void)
0x14001868f  test    rbx, rbx
0x140018692  jz      loc_14001879D
0x140018698  lea     rcx, [rbp+0F0h+arg_8]
0x14001869f  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x1400186a4  nop
0x1400186a5  mov     rax, [rbx]
0x1400186a8  lea     r8, [rbp+0F0h+arg_8]
0x1400186af  lea     rdx, qword_1400FB148
0x1400186b6  mov     rcx, rbx
0x1400186b9  mov     rax, [rax+18h]
0x1400186bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400186c2  mov     [rbp+0F0h+var_98], eax
0x1400186c5  mov     edx, 80000000h
  ... truncated ...
```
