# CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget(_GUID,IVdsAsync * *)

- ea: `0x140013620`
- end: `0x140013f41`
- name: `?LogoutFromTarget@CVdsIscsiInitiatorAdapterInternal@@UEAAJU_GUID@@PEAPEAUIVdsAsync@@@Z`
- size: `2337`
- prototype: `__int64 __fastcall(CVdsIscsiInitiatorAdapterInternal *__hidden this, struct _GUID *__struct_ptr, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x14000dd3c`
- `0x14000f98c`
- `0x140011a60`
- `0x140012c48`
- `0x140012c70`
- `0x14001350c`
- `0x140013620`
- `0x14001f220`
- `0x14003d638`
- `0x14003e5f8`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400139b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400139cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400139b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400139cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400137f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013999`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013a0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013a28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013cfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400137f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013941`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013999`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013a0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013a28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013cfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140013e4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400137d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013e9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140013b5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140013b76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140013cf2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140013b5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140013b76`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140013cf2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140013e84`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140013e84`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400136c3`
- `vdsutil!??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x1400136c3`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140013a8e`
- `vdsutil!??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ` at `0x140013a8e`
- `vdsutil!VdsWmiConnectToNamespace` at `0x140013bdb`
- `vdsutil!VdsWmiConnectToNamespace` at `0x140013bdb`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x140013c76`
- `vdsutil!?Attach@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAUtagVARIANT@@@Z` at `0x140013c76`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x140013ca5`
- `vdsutil!?Next@CVdsWmiVariantObjectArrayEnum@@QEAAJPEAPEAUIWbemClassObject@@@Z` at `0x140013ca5`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14001397f`
- `vdsutil!?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ` at `0x14001397f`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140013e0a`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140013e0a`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140013e13`
- `vdsutil!?Signal@CVdsAsyncObjectBase@@QEAAXXZ` at `0x140013e13`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x140013c10`
- `vdsutil!VdsWmiFindInstanceOfClass` at `0x140013c10`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140013c32`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140013d3f`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140013c32`
- `vdsutil!VdsWmiGetUlonglongFromInstance` at `0x140013d3f`
- `vdsutil!VdsHeapAlloc` at `0x140013805`
- `vdsutil!VdsHeapAlloc` at `0x14001394f`
- `vdsutil!VdsHeapAlloc` at `0x140013d0b`
- `vdsutil!VdsHeapAlloc` at `0x140013805`
- `vdsutil!VdsHeapAlloc` at `0x14001394f`
- `vdsutil!VdsHeapAlloc` at `0x140013d0b`
- `vdsutil!VdsHeapFree` at `0x140013937`
- `vdsutil!VdsHeapFree` at `0x1400139a7`
- `vdsutil!VdsHeapFree` at `0x140013a1a`
- `vdsutil!VdsHeapFree` at `0x140013a36`
- `vdsutil!VdsHeapFree` at `0x140013e58`
- `vdsutil!VdsHeapFree` at `0x140013937`
- `vdsutil!VdsHeapFree` at `0x1400139a7`
- `vdsutil!VdsHeapFree` at `0x140013a1a`
- `vdsutil!VdsHeapFree` at `0x140013a36`
- `vdsutil!VdsHeapFree` at `0x140013e58`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140013757`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140013757`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140013a41`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140013a41`
- `vdsutil!VdsTraceW` at `0x140013782`
- `vdsutil!VdsTraceW` at `0x140013820`
- `vdsutil!VdsTraceW` at `0x14001386f`
- `vdsutil!VdsTraceW` at `0x1400138f1`
- `vdsutil!VdsTraceW` at `0x14001396b`
- `vdsutil!VdsTraceW` at `0x140013b20`
- `vdsutil!VdsTraceW` at `0x140013baf`
- `vdsutil!VdsTraceW` at `0x140013bf3`
- `vdsutil!VdsTraceW` at `0x140013eb3`
- `vdsutil!VdsTraceW` at `0x140013f0f`
- `vdsutil!VdsTraceW` at `0x140013f30`
- `vdsutil!VdsTraceW` at `0x140013782`
- `vdsutil!VdsTraceW` at `0x140013820`
- `vdsutil!VdsTraceW` at `0x14001386f`
- `vdsutil!VdsTraceW` at `0x1400138f1`
- `vdsutil!VdsTraceW` at `0x14001396b`
- `vdsutil!VdsTraceW` at `0x140013b20`
- `vdsutil!VdsTraceW` at `0x140013baf`
- `vdsutil!VdsTraceW` at `0x140013bf3`
- `vdsutil!VdsTraceW` at `0x140013eb3`
- `vdsutil!VdsTraceW` at `0x140013f0f`
- `vdsutil!VdsTraceW` at `0x140013f30`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a4c`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a57`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a62`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a6d`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a78`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a83`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a4c`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a57`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a62`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a6d`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a78`
- `OLEAUT32!__imp_SysFreeString` at `0x140013a83`
- `OLEAUT32!__imp_VariantInit` at `0x140013734`
- `OLEAUT32!__imp_VariantInit` at `0x14001373e`
- `OLEAUT32!__imp_VariantInit` at `0x140013734`
- `OLEAUT32!__imp_VariantInit` at `0x14001373e`
- `OLEAUT32!__imp_VariantClear` at `0x140013989`
- `OLEAUT32!__imp_VariantClear` at `0x140013993`
- `OLEAUT32!__imp_VariantClear` at `0x140013cc2`
- `OLEAUT32!__imp_VariantClear` at `0x140013989`
- `OLEAUT32!__imp_VariantClear` at `0x140013993`
- `OLEAUT32!__imp_VariantClear` at `0x140013cc2`

## string_xrefs

- `0x140013eaa`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: CreateThread failed: %X`
- `0x1400136db`: `MSiSCSI_InitiatorSessionInfo`
- `0x1400137b0`: `RemoveIScsiPersistentTargetW`
- `0x140013f27`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: Could not access necessary functions in iSCSI library.`
- `0x140013ba6`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: RemoveIScsiPersistentTargetW: %X`
- `0x140013c1c`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiFindInstanceOfClass MSiSCSI_InitiatorSessionInfo failed: %X`
- `0x140013dc2`: `CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: spAsync CreateInstance: Out of memory.`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget(
        CVdsIscsiInitiatorAdapterInternal *this,
        struct _GUID *a2,
        struct IVdsAsync **a3)
{
  CVdsIscsiInitiatorAdapterInternal *v5; // r15
  __int64 v6; // r12
  _QWORD *v7; // rsi
  __int64 LastError; // rdi
  FARPROC ProcAddress; // r14
  FARPROC v10; // r13
  FARPROC v11; // rax
  HANDLE ProcessHeap; // rax
  int v13; // eax
  __int64 v14; // rdi
  unsigned int v15; // eax
  HANDLE v16; // rax
  unsigned int v17; // ebx
  HANDLE v18; // rax
  const wchar_t *v19; // rdx
  HANDLE v20; // rax
  __int64 v21; // r14
  __int64 v22; // rbx
  HANDLE v23; // rax
  HANDLE v24; // rax
  int v26; // r14d
  int v27; // r12d
  unsigned int v28; // ebx
  CVdsIscsiInitiatorAdapterInternal *v29; // rsi
  __int64 v30; // rdi
  unsigned int v31; // eax
  int InstanceOfClass; // eax
  const wchar_t *v33; // rdx
  __int64 *v34; // rbx
  HANDLE v35; // rax
  __int64 v36; // rax
  _DWORD *v37; // rbx
  __int64 v38; // rcx
  HANDLE v39; // rax
  HANDLE Thread; // rax
  __int64 v41; // rcx
  __int64 v42; // [rsp+30h] [rbp-D0h]
  unsigned int v43; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v44; // [rsp+3Ch] [rbp-C4h] BYREF
  struct IWbemClassObject *v45; // [rsp+40h] [rbp-C0h] BYREF
  struct IWbemClassObject *v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v49; // [rsp+60h] [rbp-A0h] BYREF
  void *v50; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v51; // [rsp+70h] [rbp-90h] BYREF
  CVdsIscsiInitiatorAdapterInternal *v52; // [rsp+78h] [rbp-88h]
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  struct IVdsAsync **v54; // [rsp+88h] [rbp-78h]
  BSTR bstrString; // [rsp+90h] [rbp-70h] BYREF
  BSTR v56; // [rsp+98h] [rbp-68h] BYREF
  BSTR v57; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v58; // [rsp+A8h] [rbp-58h] BYREF
  BSTR v59; // [rsp+B0h] [rbp-50h] BYREF
  BSTR v60; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v62; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v63; // [rsp+E0h] [rbp-20h]
  VARIANTARG pvarg; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v65[32]; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID v66; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v67[16]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v68; // [rsp+140h] [rbp+40h] BYREF
  LPVOID pv[2]; // [rsp+150h] [rbp+50h]
  __int64 v70; // [rsp+160h] [rbp+60h]

  v54 = a3;
  v5 = this;
  v52 = this;
  v43 = 0;
  v44 = 0;
  v6 = 0;
  v42 = 0;
  v51 = 0;
  v7 = 0;
  v50 = 0;
  v49 = 0;
  v48 = 0;
  v68 = 0;
  *(_OWORD *)pv = 0;
  v70 = 0;
  v61 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v62, 0, sizeof(v62));
  CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v65);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v60, L"root\\wmi");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v59, L"MSiSCSI_InitiatorSessionInfo");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v58, L"UniqueAdapterId");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v57, L"SessionsList");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v56, L"TargetiSCSIName");
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"UniqueSessionId");
  VariantInit(&pvarg);
  VariantInit(&v62);
  v53 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v67, 0x5Eu, "CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget()");
  v68 = 0;
  *(_OWORD *)pv = 0;
  v70 = 0;
  if ( !a3 )
  {
    LODWORD(LastError) = -2147024809;
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: NULL input arguments");
    goto LABEL_28;
  }
  *a3 = 0;
  if ( !CVdsService::m_hIscsidscModule
    || (ProcAddress = GetProcAddress(CVdsService::m_hIscsidscModule, "ReportIScsiPersistentLoginsW"),
        v10 = GetProcAddress(CVdsService::m_hIscsidscModule, "RemoveIScsiPersistentTargetW"),
        v11 = GetProcAddress(CVdsService::m_hIscsidscModule, "LogoutIScsiTarget"),
        !ProcAddress)
    || !v10
    || !v11 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: Could not access necessary functions in iSCSI library.");
    LODWORD(LastError) = -2147212288;
    goto LABEL_28;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (_QWORD *)VdsHeapAlloc(ProcessHeap, 0, 24);
  v63 = v7;
  if ( !v7 )
  {
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: pLogoutParam Alloc: Out of memory.");
    LODWORD(LastError) = -2147024882;
    goto LABEL_28;
  }
  *(_OWORD *)v7 = 0;
  v7[2] = 0;
  v66 = *a2;
  LODWORD(LastError) = CVdsService::GetObjectFromProviders(&v66, VDS_OT_TARGET, &v49);
  if ( (_DWORD)LastError == -2147212283 )
  {
    LODWORD(LastError) = -2147024809;
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget, 1, hr=%lX", 2147942487LL);
    goto LABEL_28;
  }
  if ( (int)LastError < 0 || !v49 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: Could not retrieve target object from provider: %X",
      (unsigned int)LastError);
LABEL_91:
    if ( (int)LastError >= 0 )
      LODWORD(LastError) = -2147211511;
    goto LABEL_28;
  }
  LODWORD(LastError) = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v49->lpVtbl->QueryInterface)(
                         v49,
                         &IID_IVdsIscsiTarget,
                         &v48);
  if ( (int)LastError < 0 || !v48 )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: spTargetUnk->QueryInterface IID_IVdsIscsiTarget: %X",
      (unsigned int)LastError);
    goto LABEL_91;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v48 + 24LL))(v48, &v68);
  LODWORD(LastError) = v13;
  if ( v13 < 0 )
  {
    VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: spTarget->GetProperties: %X", (unsigned int)v13);
    goto LABEL_28;
  }
  if ( !pv[0] )
  {
    VdsTraceW(
      0,
      L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: Invalid target iSCSI name retrieved from provider.");
    LODWORD(LastError) = -2147211005;
    goto LABEL_28;
  }
  v14 = 0;
  do
  {
    v15 = ((__int64 (__fastcall *)(unsigned int *, __int64, unsigned int *))ProcAddress)(&v43, v14, &v44);
    if ( !v15 )
    {
      v26 = 0;
      v27 = 0;
      v28 = 0;
      if ( v43 )
      {
        v29 = v52;
        do
        {
          v30 = 2080LL * v28 + v14;
          if ( !lstrcmpiW((LPCWSTR)pv[0], (LPCWSTR)v30) && !lstrcmpiW(*((LPCWSTR *)v29 + 10), (LPCWSTR)(v30 + 450)) )
          {
            v27 = 1;
            v31 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64))v10)(
                    v30 + 450,
                    *(unsigned int *)(v30 + 964),
                    v30,
                    v30 + 968);
            if ( v31 )
            {
              VdsTraceW(
                0,
                L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: RemoveIScsiPersistentTargetW: %X",
                v31);
              v26 = 1;
            }
          }
          ++v28;
          v14 = v42;
        }
        while ( v28 < v43 );
        v7 = v63;
        v5 = v52;
      }
LABEL_49:
      InstanceOfClass = VdsWmiConnectToNamespace(v60, &v61, &v47);
      LODWORD(LastError) = InstanceOfClass;
      if ( InstanceOfClass >= 0 )
      {
        InstanceOfClass = VdsWmiFindInstanceOfClass(v47, v59, *((_QWORD *)v5 + 10), &v46);
        LODWORD(LastError) = InstanceOfClass;
        if ( InstanceOfClass >= 0 )
        {
          InstanceOfClass = VdsWmiGetUlonglongFromInstance(v46, v58, &v53);
          LODWORD(LastError) = InstanceOfClass;
          if ( InstanceOfClass >= 0 )
          {
            InstanceOfClass = VdsWmiGetVariantFromInstance(v46, v57, 0x200Du, &pvarg);
            LODWORD(LastError) = InstanceOfClass;
            if ( InstanceOfClass >= 0 )
            {
              InstanceOfClass = CVdsWmiVariantObjectArrayEnum::Attach((CVdsWmiVariantObjectArrayEnum *)v65, &pvarg);
              LODWORD(LastError) = InstanceOfClass;
              if ( InstanceOfClass >= 0 )
              {
                v34 = v7 + 2;
                while ( 1 )
                {
                  ATL::CComPtrBase<IVdsIscsiPortal>::Release(&v45);
                  InstanceOfClass = CVdsWmiVariantObjectArrayEnum::Next((CVdsWmiVariantObjectArrayEnum *)v65, &v45);
                  LODWORD(LastError) = InstanceOfClass;
                  if ( InstanceOfClass == 1 )
                    break;
                  if ( InstanceOfClass < 0 )
                  {
                    v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: vdsSessionsListEnum.Next failed: %X";
                    goto LABEL_51;
                  }
                  VariantClear(&v62);
                  InstanceOfClass = VdsWmiGetVariantFromInstance(v45, v56, 8u, &v62);
                  LODWORD(LastError) = InstanceOfClass;
                  if ( InstanceOfClass < 0 )
                  {
                    v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiGetVariantStringFromInstance Target"
                           "iSCSIName failed: %X";
                    goto LABEL_51;
                  }
                  if ( !lstrcmpiW((LPCWSTR)pv[0], v62.bstrVal) )
                  {
                    v35 = GetProcessHeap();
                    v36 = VdsHeapAlloc(v35, 0, 24);
                    *v34 = v36;
                    if ( !v36 )
                    {
                      VdsTraceW(
                        0,
                        L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: *ppCurrentSession Alloc: Out of memory.");
                      goto LABEL_26;
                    }
                    *(_OWORD *)v36 = 0;
                    *(_QWORD *)(v36 + 16) = 0;
                    *(_QWORD *)*v34 = v53;
                    InstanceOfClass = VdsWmiGetUlonglongFromInstance(v45, bstrString, *v34 + 8);
                    LODWORD(LastError) = InstanceOfClass;
                    if ( InstanceOfClass < 0 )
                    {
                      v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiGetUlonglongFromInstance UniqueSe"
                             "ssionId failed: %X";
                      goto LABEL_51;
                    }
                    v34 = (__int64 *)(*v34 + 16);
                    ++*((_DWORD *)v7 + 2);
                  }
                }
                if ( !*((_DWORD *)v7 + 2) && (!v27 || v26) )
                {
                  LODWORD(LastError) = -2147211510;
                  VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget, 2, hr=%lX", 2147755786LL);
                  goto LABEL_27;
                }
                ATL::CComObject<CVdsServiceAsyncObject>::CreateInstance(&v51);
                v37 = v51;
                if ( !v51 )
                {
                  v19 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: spAsync CreateInstance: Out of memory.";
                  goto LABEL_25;
                }
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v51 + 8LL))(v51);
                v37[20] = 61;
                *v7 = v37;
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v37 + 8LL))(v37);
                if ( *((_DWORD *)v7 + 2) )
                {
                  Thread = CreateThread(0, 0, CVdsIscsiInitiatorAdapterInternal::LogoutFromTargetThread, v7, 0, 0);
                  CVdsHandleImpl<0>::operator=(&v50, Thread);
                  if ( !v50 )
                  {
                    LastError = GetLastError();
                    VdsTraceW(
                      0,
                      L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: CreateThread failed: %X",
                      LastError);
                    if ( (int)LastError > 0 )
                      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
                    goto LABEL_27;
                  }
                  LODWORD(LastError) = 0;
                  v41 = *v7;
                  *v54 = (struct IVdsAsync *)*v7;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
                }
                else
                {
                  LODWORD(LastError) = 272384;
                  CVdsAsyncObjectBase::SetCompletionStatus((CVdsAsyncObjectBase *)*v7, 0, 0x64u);
                  CVdsAsyncObjectBase::Signal((CVdsAsyncObjectBase *)*v7);
                  v38 = *v7;
                  *v54 = (struct IVdsAsync *)*v7;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
                  if ( *v7 )
                  {
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
                    *v7 = 0;
                  }
                  v39 = GetProcessHeap();
                  VdsHeapFree(v39, 0, v7);
                  v7 = 0;
                }
                if ( v26 )
                  LODWORD(LastError) = 272385;
                goto LABEL_27;
              }
              v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: vdsSessionsListEnum.Attach failed: %X";
            }
            else
            {
              v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiGetVariantObjectArrayFromInstance Session"
                     "sList failed: %X";
            }
          }
          else
          {
            v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiGetUlonglongFromInstance UniqueAdapterId failed: %X";
          }
        }
        else
        {
          v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiFindInstanceOfClass MSiSCSI_InitiatorSessionInfo failed: %X";
        }
      }
      else
      {
        v33 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: VdsWmiConnectToNamespace failed: %X";
      }
LABEL_51:
      VdsTraceW(0, v33, (unsigned int)InstanceOfClass);
      goto LABEL_27;
    }
    if ( v15 != 122 )
    {
      VdsTraceW(0, L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: ReportIScsiPersistentLoginsW: %X", v15);
      v26 = 1;
      v27 = 0;
      goto LABEL_49;
    }
    v16 = GetProcessHeap();
    VdsHeapFree(v16, 0, v14);
    v17 = v44;
    v18 = GetProcessHeap();
    v14 = VdsHeapAlloc(v18, 0, v17);
    v42 = v14;
  }
  while ( v14 );
  v19 = L"CVdsIscsiInitiatorAdapterInternal::LogoutFromTarget: pPersistentLogins Alloc: Out of memory.";
LABEL_25:
  VdsTraceW(0, v19);
LABEL_26:
  LODWORD(LastError) = -2147024882;
LABEL_27:
  v6 = v42;
LABEL_28:
  CVdsWmiVariantObjectArrayEnum::Detach((CVdsWmiVariantObjectArrayEnum *)v65);
  VariantClear(&pvarg);
  VariantClear(&v62);
  v20 = GetProcessHeap();
  VdsHeapFree(v20, 0, v6);
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  if ( pv[1] )
  {
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
  }
  if ( (int)LastError < 0 && v7 )
  {
    if ( *v7 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
      *v7 = 0;
    }
    v21 = v7[2];
    if ( v21 )
    {
      do
      {
        v22 = *(_QWORD *)(v21 + 16);
        v23 = GetProcessHeap();
        VdsHeapFree(v23, 0, v21);
        v21 = v22;
      }
      while ( v22 );
    }
    v24 = GetProcessHeap();
    VdsHeapFree(v24, 0, v7);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v67);
  SysFreeString(bstrString);
  SysFreeString(v56);
  SysFreeString(v57);
  SysFreeString(v58);
  SysFreeString(v59);
  SysFreeString(v60);
  CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum((CVdsWmiVariantObjectArrayEnum *)v65);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v45);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v46);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v61);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v49);
  CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v50);
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v51);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140013620  mov     [rsp-8+arg_18], rbx
0x140013625  push    rbp
0x140013626  push    rsi
0x140013627  push    rdi
0x140013628  push    r12
0x14001362a  push    r13
0x14001362c  push    r14
0x14001362e  push    r15
0x140013630  lea     rbp, [rsp-70h]
0x140013635  sub     rsp, 170h
0x14001363c  mov     rax, cs:__security_cookie
0x140013643  xor     rax, rsp
0x140013646  mov     [rbp+0A0h+var_38], rax
0x14001364a  mov     rdi, r8
0x14001364d  mov     [rbp+0A0h+var_118], r8
0x140013651  mov     rbx, rdx
0x140013654  mov     r15, rcx
0x140013657  mov     [rsp+1A0h+var_128], rcx
0x14001365c  xor     r14d, r14d
0x14001365f  mov     [rsp+1A0h+var_168], r14d
0x140013664  mov     [rsp+1A0h+var_164], r14d
0x140013669  mov     r12d, r14d
0x14001366c  mov     [rsp+1A0h+var_170], r14
0x140013671  mov     [rsp+1A0h+var_130], r14
0x140013676  mov     esi, r14d
0x140013679  mov     [rsp+1A0h+var_138], r14
0x14001367e  mov     [rsp+1A0h+var_140], r14
0x140013683  mov     [rsp+1A0h+var_148], r14
0x140013688  xorps   xmm0, xmm0
0x14001368b  xor     eax, eax
0x14001368d  movups  [rbp+0A0h+var_60], xmm0
0x140013691  movups  xmmword ptr [rbp+0A0h+pv], xmm0
0x140013695  mov     [rbp+0A0h+var_40], rax
0x140013699  mov     [rbp+0A0h+var_E0], r14
0x14001369d  mov     [rsp+1A0h+var_150], r14
0x1400136a2  mov     [rsp+1A0h+var_158], r14
0x1400136a7  mov     [rsp+1A0h+var_160], r14
0x1400136ac  movups  xmmword ptr [rbp+0A0h+pvarg], xmm0
0x1400136b0  mov     qword ptr [rbp+0A0h+pvarg+10h], rax
0x1400136b4  xorps   xmm1, xmm1
0x1400136b7  movups  xmmword ptr [rbp+0A0h+var_D8], xmm1
0x1400136bb  mov     qword ptr [rbp+0A0h+var_D8+10h], rax
0x1400136bf  lea     rcx, [rbp+0A0h+var_A0]
0x1400136c3  call    cs:__imp_??0CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::CVdsWmiVariantObjectArrayEnum(void)
0x1400136c9  nop
0x1400136ca  lea     rdx, Source; "root\\wmi"
0x1400136d1  lea     rcx, [rbp+0A0h+var_E8]; this
0x1400136d5  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400136da  nop
0x1400136db  lea     rdx, aMsiscsiInitiat; "MSiSCSI_InitiatorSessionInfo"
0x1400136e2  lea     rcx, [rbp+0A0h+var_F0]; this
0x1400136e6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400136eb  nop
0x1400136ec  lea     rdx, aUniqueadapteri; "UniqueAdapterId"
0x1400136f3  lea     rcx, [rbp+0A0h+var_F8]; this
0x1400136f7  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400136fc  nop
0x1400136fd  lea     rdx, aSessionslist; "SessionsList"
0x140013704  lea     rcx, [rbp+0A0h+var_100]; this
0x140013708  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001370d  nop
0x14001370e  lea     rdx, aTargetiscsinam; "TargetiSCSIName"
0x140013715  lea     rcx, [rbp+0A0h+var_108]; this
0x140013719  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001371e  nop
0x14001371f  lea     rdx, aUniquesessioni; "UniqueSessionId"
0x140013726  lea     rcx, [rbp+0A0h+bstrString]; this
0x14001372a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001372f  nop
0x140013730  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x140013734  call    cs:__imp_VariantInit
0x14001373a  lea     rcx, [rbp+0A0h+var_D8]; pvarg
0x14001373e  call    cs:__imp_VariantInit
0x140013744  mov     [rbp+0A0h+var_120], r14
0x140013748  lea     r8, aCvdsiscsiiniti_49; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14001374f  lea     edx, [r14+5Eh]
0x140013753  lea     rcx, [rbp+0A0h+var_70]
0x140013757  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001375d  nop
0x14001375e  xorps   xmm0, xmm0
0x140013761  xor     eax, eax
0x140013763  movups  [rbp+0A0h+var_60], xmm0
0x140013767  movups  xmmword ptr [rbp+0A0h+pv], xmm0
0x14001376b  mov     [rbp+0A0h+var_40], rax
0x14001376f  test    rdi, rdi
0x140013772  jnz     short loc_14001378D
0x140013774  mov     edi, 80070057h
0x140013779  lea     rdx, aCvdsiscsiiniti_66; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x140013780  xor     ecx, ecx
0x140013782  call    cs:__imp_VdsTraceW
0x140013788  jmp     loc_14001397B
0x14001378d  mov     [rdi], r14
0x140013790  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x140013797  test    rcx, rcx
0x14001379a  jz      loc_140013F27
0x1400137a0  lea     rdx, aReportiscsiper; "ReportIScsiPersistentLoginsW"
0x1400137a7  call    cs:__imp_GetProcAddress
0x1400137ad  mov     r14, rax
0x1400137b0  lea     rdx, aRemoveiscsiper; "RemoveIScsiPersistentTargetW"
0x1400137b7  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x1400137be  call    cs:__imp_GetProcAddress
0x1400137c4  mov     r13, rax
0x1400137c7  lea     rdx, aLogoutiscsitar; "LogoutIScsiTarget"
0x1400137ce  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hModule
0x1400137d5  call    cs:__imp_GetProcAddress
0x1400137db  test    r14, r14
0x1400137de  jz      loc_140013F27
0x1400137e4  test    r13, r13
0x1400137e7  jz      loc_140013F27
0x1400137ed  test    rax, rax
0x1400137f0  jz      loc_140013F27
0x1400137f6  call    cs:__imp_GetProcessHeap
0x1400137fc  mov     rcx, rax
0x1400137ff  xor     edx, edx
0x140013801  lea     r8d, [rdx+18h]
0x140013805  call    cs:__imp_VdsHeapAlloc
0x14001380b  mov     rsi, rax
0x14001380e  mov     [rbp+0A0h+var_C0], rax
0x140013812  test    rax, rax
0x140013815  jnz     short loc_140013830
0x140013817  lea     rdx, aCvdsiscsiiniti_127; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14001381e  xor     ecx, ecx
0x140013820  call    cs:__imp_VdsTraceW
0x140013826  mov     edi, 8007000Eh
0x14001382b  jmp     loc_14001397B
0x140013830  xorps   xmm0, xmm0
0x140013833  xor     eax, eax
0x140013835  movups  xmmword ptr [rsi], xmm0
0x140013838  mov     [rsi+10h], rax
0x14001383c  movups  xmm0, xmmword ptr [rbx]
0x14001383f  movdqu  xmmword ptr [rbp+0A0h+var_80.Data1], xmm0
0x140013844  lea     r8, [rsp+1A0h+var_140]; struct IUnknown **
0x140013849  lea     edx, [rax+25h]; enum _VDS_OBJECT_TYPE
0x14001384c  lea     rcx, [rbp+0A0h+var_80]; struct _GUID
0x140013850  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x140013855  mov     edi, eax
0x140013857  cmp     eax, 80042405h
0x14001385c  jnz     short loc_14001387A
0x14001385e  mov     edi, 80070057h
0x140013863  mov     r8d, edi
0x140013866  lea     rdx, aCvdsiscsiiniti_107; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x14001386d  xor     ecx, ecx
0x14001386f  call    cs:__imp_VdsTraceW
0x140013875  jmp     loc_14001397B
0x14001387a  test    edi, edi
0x14001387c  js      loc_140013F03
0x140013882  mov     rcx, [rsp+1A0h+var_140]
0x140013887  test    rcx, rcx
0x14001388a  jz      loc_140013F03
0x140013890  mov     rax, [rcx]
0x140013893  lea     r8, [rsp+1A0h+var_148]
0x140013898  lea     rdx, IID_IVdsIscsiTarget
0x14001389f  mov     rax, [rax]
0x1400138a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138a7  mov     edi, eax
0x1400138a9  test    eax, eax
0x1400138ab  js      loc_140013EFA
0x1400138b1  mov     rcx, [rsp+1A0h+var_148]
0x1400138b6  test    rcx, rcx
0x1400138b9  jz      loc_140013EFA
0x1400138bf  mov     rax, [rcx]
0x1400138c2  lea     rdx, [rbp+0A0h+var_60]
0x1400138c6  mov     rax, [rax+18h]
0x1400138ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138cf  mov     edi, eax
0x1400138d1  test    eax, eax
0x1400138d3  jns     short loc_1400138E1
0x1400138d5  mov     r8d, eax
0x1400138d8  lea     rdx, aCvdsiscsiiniti_105; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x1400138df  jmp     short loc_14001386D
0x1400138e1  cmp     [rbp+0A0h+pv], 0
0x1400138e6  jnz     short loc_1400138FE
0x1400138e8  lea     rdx, aCvdsiscsiiniti_129; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x1400138ef  xor     ecx, ecx
0x1400138f1  call    cs:__imp_VdsTraceW
0x1400138f7  mov     edi, 80042903h
0x1400138fc  jmp     short loc_14001397B
0x1400138fe  mov     rdi, [rsp+1A0h+var_170]
0x140013903  lea     r8, [rsp+1A0h+var_164]
0x140013908  mov     rdx, rdi
0x14001390b  lea     rcx, [rsp+1A0h+var_168]
0x140013910  mov     rax, r14
0x140013913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013918  test    eax, eax
0x14001391a  jz      loc_140013B34
0x140013920  cmp     eax, 7Ah ; 'z'
0x140013923  jnz     loc_140013B14
0x140013929  call    cs:__imp_GetProcessHeap
0x14001392f  mov     rcx, rax
0x140013932  mov     r8, rdi
0x140013935  xor     edx, edx
0x140013937  call    cs:__imp_VdsHeapFree
0x14001393d  mov     ebx, [rsp+1A0h+var_164]
0x140013941  call    cs:__imp_GetProcessHeap
0x140013947  mov     r8d, ebx
0x14001394a  xor     edx, edx
0x14001394c  mov     rcx, rax
0x14001394f  call    cs:__imp_VdsHeapAlloc
0x140013955  mov     rdi, rax
0x140013958  mov     [rsp+1A0h+var_170], rax
0x14001395d  test    rax, rax
0x140013960  jnz     short loc_140013903
0x140013962  lea     rdx, aCvdsiscsiiniti_37; "CVdsIscsiInitiatorAdapterInternal::Logo"...
0x140013969  xor     ecx, ecx
0x14001396b  call    cs:__imp_VdsTraceW
0x140013971  mov     edi, 8007000Eh
0x140013976  mov     r12, [rsp+1A0h+var_170]
0x14001397b  lea     rcx, [rbp+0A0h+var_A0]
0x14001397f  call    cs:__imp_?Detach@CVdsWmiVariantObjectArrayEnum@@QEAAJXZ; CVdsWmiVariantObjectArrayEnum::Detach(void)
0x140013985  lea     rcx, [rbp+0A0h+pvarg]; pvarg
0x140013989  call    cs:__imp_VariantClear
0x14001398f  lea     rcx, [rbp+0A0h+var_D8]; pvarg
0x140013993  call    cs:__imp_VariantClear
0x140013999  call    cs:__imp_GetProcessHeap
0x14001399f  mov     rcx, rax
0x1400139a2  mov     r8, r12
0x1400139a5  xor     edx, edx
0x1400139a7  call    cs:__imp_VdsHeapFree
0x1400139ad  mov     rcx, [rbp+0A0h+pv]; pv
0x1400139b1  test    rcx, rcx
0x1400139b4  jz      short loc_1400139C4
0x1400139b6  call    cs:__imp_CoTaskMemFree
0x1400139bc  mov     [rbp+0A0h+pv], 0
0x1400139c4  mov     rcx, [rbp+0A0h+pv+8]; pv
0x1400139c8  test    rcx, rcx
0x1400139cb  jz      short loc_1400139DB
0x1400139cd  call    cs:__imp_CoTaskMemFree
0x1400139d3  mov     [rbp+0A0h+pv+8], 0
0x1400139db  test    edi, edi
0x1400139dd  jns     short loc_140013A3D
0x1400139df  test    rsi, rsi
0x1400139e2  jz      short loc_140013A3D
0x1400139e4  mov     rcx, [rsi]
0x1400139e7  test    rcx, rcx
0x1400139ea  jz      short loc_1400139FF
0x1400139ec  mov     rax, [rcx]
0x1400139ef  mov     rax, [rax+10h]
0x1400139f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400139f8  mov     qword ptr [rsi], 0
0x1400139ff  mov     r14, [rsi+10h]
0x140013a03  test    r14, r14
0x140013a06  jz      short loc_140013A28
0x140013a08  mov     rbx, [r14+10h]
0x140013a0c  call    cs:__imp_GetProcessHeap
0x140013a12  mov     rcx, rax
0x140013a15  mov     r8, r14
0x140013a18  xor     edx, edx
0x140013a1a  call    cs:__imp_VdsHeapFree
0x140013a20  mov     r14, rbx
0x140013a23  test    rbx, rbx
0x140013a26  jnz     short loc_140013A08
0x140013a28  call    cs:__imp_GetProcessHeap
0x140013a2e  mov     rcx, rax
0x140013a31  mov     r8, rsi
0x140013a34  xor     edx, edx
0x140013a36  call    cs:__imp_VdsHeapFree
0x140013a3c  nop
0x140013a3d  lea     rcx, [rbp+0A0h+var_70]
0x140013a41  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140013a47  nop
0x140013a48  mov     rcx, [rbp+0A0h+bstrString]; bstrString
0x140013a4c  call    cs:__imp_SysFreeString
0x140013a52  nop
0x140013a53  mov     rcx, [rbp+0A0h+var_108]; bstrString
0x140013a57  call    cs:__imp_SysFreeString
0x140013a5d  nop
0x140013a5e  mov     rcx, [rbp+0A0h+var_100]; bstrString
0x140013a62  call    cs:__imp_SysFreeString
0x140013a68  nop
0x140013a69  mov     rcx, [rbp+0A0h+var_F8]; bstrString
0x140013a6d  call    cs:__imp_SysFreeString
0x140013a73  nop
0x140013a74  mov     rcx, [rbp+0A0h+var_F0]; bstrString
0x140013a78  call    cs:__imp_SysFreeString
0x140013a7e  nop
0x140013a7f  mov     rcx, [rbp+0A0h+var_E8]; bstrString
0x140013a83  call    cs:__imp_SysFreeString
0x140013a89  nop
0x140013a8a  lea     rcx, [rbp+0A0h+var_A0]
0x140013a8e  call    cs:__imp_??1CVdsWmiVariantObjectArrayEnum@@QEAA@XZ; CVdsWmiVariantObjectArrayEnum::~CVdsWmiVariantObjectArrayEnum(void)
0x140013a94  nop
0x140013a95  lea     rcx, [rsp+1A0h+var_160]
0x140013a9a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013a9f  nop
0x140013aa0  lea     rcx, [rsp+1A0h+var_158]
0x140013aa5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013aaa  nop
0x140013aab  lea     rcx, [rsp+1A0h+var_150]
0x140013ab0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013ab5  nop
0x140013ab6  lea     rcx, [rbp+0A0h+var_E0]
0x140013aba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013abf  nop
0x140013ac0  lea     rcx, [rsp+1A0h+var_148]
0x140013ac5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013aca  nop
0x140013acb  lea     rcx, [rsp+1A0h+var_140]
0x140013ad0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013ad5  nop
0x140013ad6  lea     rcx, [rsp+1A0h+var_138]
  ... truncated ...
```
