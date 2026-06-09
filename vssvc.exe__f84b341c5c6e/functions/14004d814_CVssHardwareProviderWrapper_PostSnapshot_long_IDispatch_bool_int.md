# CVssHardwareProviderWrapper::PostSnapshot(long,IDispatch *,bool *,int)

- ea: `0x14004d814`
- end: `0x14004ee36`
- name: `?PostSnapshot@CVssHardwareProviderWrapper@@QEAAJJPEAUIDispatch@@PEA_NH@Z`
- size: `5666`
- prototype: `__int64 __fastcall(CVssHardwareProviderWrapper *__hidden this, int, struct IDispatch *, bool *, int)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400bcf70`

## callees

- `0x140006020`
- `0x140006270`
- `0x1400088fc`
- `0x140008a10`
- `0x14000a834`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x140019760`
- `0x140019990`
- `0x140032fcc`
- `0x1400330fc`
- `0x14003c160`
- `0x14003fc04`
- `0x14003fcac`
- `0x14004030c`
- `0x140042acc`
- `0x140044ce8`
- `0x140046a64`
- `0x14004d404`
- `0x14004d814`
- `0x1400518bc`
- `0x1400525e4`
- `0x140055ba4`
- `0x140056164`
- `0x140073d84`
- `0x14009197c`
- `0x1400921dc`
- `0x1400a9608`
- `0x1400afba0`
- `0x1400b1e18`
- `0x1400b5bd8`
- `0x1400b6804`
- `0x1400b95ec`
- `0x1400bc0f8`
- `0x1400be544`
- `0x1400bfe84`
- `0x1400da314`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14004e1b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14004e1b1`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e532`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e54f`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e532`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004deaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004deaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x14004e06f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x14004e06f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e13d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004e13d`

## string_xrefs

- `0x14004e284`: `IVssSnapshotSetDescription::SaveAsXML`
- `0x14004e3db`: `Error querying for IVssWriterCallback interface.  hr = 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVssHardwareProviderWrapper::PostSnapshot(
        CVssHardwareProviderWrapper *this,
        unsigned int a2,
        struct IDispatch *a3,
        bool *a4,
        int a5)
{
  CVssHardwareProviderWrapper *v5; // r12
  __int64 v6; // rdx
  __int64 v7; // rdx
  CVssHardwareProviderWrapper *v8; // rcx
  void *v9; // rax
  int v10; // eax
  char *v11; // rax
  struct _VDS_LUN_INFORMATION *v12; // rbx
  CVssHardwareProviderWrapper *v13; // rcx
  CVssHardwareProviderWrapper *v14; // rcx
  unsigned int i; // edx
  CVssDebugInfo *v16; // rax
  DWORD v17; // ebx
  bool *v18; // r8
  CVssHardwareProviderWrapper *v19; // rcx
  struct IVssSnapshotSetDescription *v20; // rax
  VSS_SNAPSHOT_SET_LIST *v21; // rax
  VSS_SNAPSHOT_SET_LIST *v22; // rbx
  CVssHardwareProviderWrapper *v23; // rcx
  const wchar_t *v24; // rbx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  DWORD v28; // ebx
  DWORD v29; // ebx
  struct _VDS_LUN_INFORMATION **v31; // [rsp+20h] [rbp-328h]
  struct _VDS_LUN_INFORMATION **v32; // [rsp+20h] [rbp-328h]
  struct _VDS_LUN_INFORMATION **v33; // [rsp+20h] [rbp-328h]
  struct _VDS_LUN_INFORMATION **v34; // [rsp+20h] [rbp-328h]
  struct _GUID *v35; // [rsp+28h] [rbp-320h]
  struct _GUID *v36; // [rsp+28h] [rbp-320h]
  __int64 v37; // [rsp+30h] [rbp-318h]
  __int64 v38; // [rsp+38h] [rbp-310h]
  __int64 v39; // [rsp+40h] [rbp-308h]
  __int64 v40; // [rsp+48h] [rbp-300h]
  __int64 v41; // [rsp+50h] [rbp-2F8h]
  __int64 v42; // [rsp+58h] [rbp-2F0h]
  __int64 v43; // [rsp+60h] [rbp-2E8h]
  __int64 v44; // [rsp+68h] [rbp-2E0h]
  __int64 v45; // [rsp+70h] [rbp-2D8h]
  DWORD v46; // [rsp+80h] [rbp-2C8h]
  const unsigned __int16 *v47; // [rsp+88h] [rbp-2C0h] BYREF
  const unsigned __int16 *v48; // [rsp+90h] [rbp-2B8h]
  const unsigned __int16 *v49; // [rsp+98h] [rbp-2B0h]
  int v50; // [rsp+A0h] [rbp-2A8h]
  int v51; // [rsp+A4h] [rbp-2A4h]
  int v52; // [rsp+A8h] [rbp-2A0h]
  _BYTE v53[120]; // [rsp+B0h] [rbp-298h] BYREF
  int v54; // [rsp+128h] [rbp-220h]
  LPVOID pv; // [rsp+130h] [rbp-218h]
  int v56; // [rsp+138h] [rbp-210h]
  int v57; // [rsp+13Ch] [rbp-20Ch]
  int Val[4]; // [rsp+140h] [rbp-208h] BYREF
  unsigned int v59; // [rsp+150h] [rbp-1F8h]
  void *Src; // [rsp+158h] [rbp-1F0h]
  struct IVssSnapshotDescription *v61; // [rsp+160h] [rbp-1E8h] BYREF
  unsigned __int16 **v62; // [rsp+168h] [rbp-1E0h] BYREF
  struct _VDS_LUN_INFORMATION *v63; // [rsp+170h] [rbp-1D8h] BYREF
  size_t Size; // [rsp+178h] [rbp-1D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+180h] [rbp-1C8h] BYREF
  unsigned int v66; // [rsp+190h] [rbp-1B8h] BYREF
  DWORD dwMessageId; // [rsp+198h] [rbp-1B0h]
  void *v68; // [rsp+1A0h] [rbp-1A8h]
  _QWORD *v69; // [rsp+1A8h] [rbp-1A0h] BYREF
  struct _LUN_MAPPING_STRUCTURE *v70; // [rsp+1B0h] [rbp-198h] BYREF
  _DWORD *v71; // [rsp+1B8h] [rbp-190h]
  LPVOID v72; // [rsp+1C0h] [rbp-188h] BYREF
  DWORD v73; // [rsp+1C8h] [rbp-180h]
  unsigned int v74; // [rsp+1E4h] [rbp-164h]
  int v75; // [rsp+230h] [rbp-118h]
  __int64 v76; // [rsp+238h] [rbp-110h] BYREF
  int v77; // [rsp+240h] [rbp-108h] BYREF
  CVssDiag *v78; // [rsp+248h] [rbp-100h]
  _com_error *v79; // [rsp+250h] [rbp-F8h] BYREF
  const std::exception *v80; // [rsp+258h] [rbp-F0h] BYREF
  char v81[232]; // [rsp+260h] [rbp-E8h] BYREF
  char *v83; // [rsp+350h] [rbp+8h]
  int v84; // [rsp+350h] [rbp+8h]
  char *v85; // [rsp+350h] [rbp+8h]
  int v86; // [rsp+350h] [rbp+8h]
  unsigned int v88; // [rsp+358h] [rbp+10h]
  unsigned int j; // [rsp+358h] [rbp+10h]
  bool *v91; // [rsp+368h] [rbp+20h] BYREF

  v91 = a4;
  v5 = this;
  v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
  v49 = L"CORHWPWC";
  v50 = 785;
  v51 = 1;
  v52 = 255;
  v54 = 0x1000000;
  memset_0(v53, 0, sizeof(v53));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v72, (__int64)&v47, 0);
  v78 = (CVssHardwareProviderWrapper *)((char *)v5 + 440);
  v71 = (_DWORD *)((char *)v5 + 120);
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = *(_OWORD *)((char *)v5 + 120);
  CVssDiag::RecordGenericEvent(
    (CVssHardwareProviderWrapper *)((char *)v5 + 440),
    0x408u,
    1,
    0,
    0,
    (struct _GUID *)SystemTimeAsFileTime);
  Src = 0;
  v63 = 0;
  pv = 0;
  v68 = 0;
  v70 = 0;
  v62 = 0;
  LODWORD(v91) = 0;
  v59 = 0;
  v46 = 0;
  v56 = 0;
  v75 = (a2 & 0x400000) == 0;
  v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
  v49 = L"CORHWPWC";
  v50 = 819;
  v51 = 1;
  v52 = 255;
  v54 = 0x1000000;
  memset_0(v53, 0, sizeof(v53));
  try
  {
    CVssFunctionTracer::AddOperation((__int64)&v72, (__int64)&v47, 0xE5u);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 820;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    CVssFunctionTracer::AddContext((__int64)&v72, (__int64)&v47, 5012, (__int64)L"Provider");
    v69 = 0;
    *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = *(_OWORD *)((char *)v5 + 404);
    CVssProviderManager::GetProviderStructure((struct _GUID *)SystemTimeAsFileTime, (struct VSS_OBJECT_PROP_Ptr *)&v69);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 826;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    CVssFunctionTracer::AddContext((__int64)&v72, (__int64)&v47, 5016, v69[3]);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 827;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    CVssFunctionTracer::AddContext((__int64)&v72, (__int64)&v47, 5017, v69[5]);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 828;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    LODWORD(v35) = *((unsigned __int16 *)v5 + 204);
    LODWORD(v31) = *((_DWORD *)v5 + 101);
    CVssFunctionTracer::AddContextEx(
      (__int64)&v72,
      (__int64)&v47,
      0x1391u,
      L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      v31,
      v35,
      *((unsigned __int16 *)v5 + 205),
      *((unsigned __int8 *)v5 + 412),
      *((unsigned __int8 *)v5 + 413),
      *((unsigned __int8 *)v5 + 414),
      *((unsigned __int8 *)v5 + 415),
      *((unsigned __int8 *)v5 + 416),
      *((unsigned __int8 *)v5 + 417),
      *((unsigned __int8 *)v5 + 418),
      *((unsigned __int8 *)v5 + 419));
    v66 = 0;
    v73 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v5 + 14) + 88LL))(
            *((_QWORD *)v5 + 14),
            &v66);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 836;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    CVssFunctionTracer::CheckForErrorInternal(&v72, &v47, L"IVssSnapshotSetDescription::GetSnapshotCount");
    for ( i = 0; ; i = v57 + 1 )
    {
      v57 = i;
      if ( i >= v66 )
        break;
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v61);
      v73 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IVssSnapshotDescription **))(**((_QWORD **)v5 + 14)
                                                                                          + 112LL))(
              *((_QWORD *)v5 + 14),
              v6,
              &v61);
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 845;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      CVssFunctionTracer::CheckForErrorInternal(&v72, &v47, L"IVssSnapshotSetDescription::GetSnapshotDescription");
      v7 = a2;
      LODWORD(v7) = a2 | 0x10000;
      v73 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, __int64))(*(_QWORD *)v61 + 72LL))(v61, v7);
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 849;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      CVssFunctionTracer::CheckForErrorInternal(&v72, &v47, L"IVssSnapshotDescription::SetAttributes");
      CVssHardwareProviderWrapper::GetLunInformation(v8, v61, 0, &v62, &v63, (unsigned int *)&v91);
      Size = 96LL * (unsigned int)v91;
      v9 = CoTaskMemAlloc(Size);
      Src = v9;
      if ( !v9 )
      {
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 864;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        CVssFunctionTracer::Throw(&v72, &v47, 2147942414LL, L"can't allocate destination luns");
      }
      v59 = (unsigned int)v91;
      memset_0(v9, 0, Size);
      if ( CVssFunctionTracer::IsHwDiagEnabled((CVssFunctionTracer *)&v72) )
        v10 = (*(__int64 (__fastcall **)(CVssHardwareProviderWrapper *, _QWORD, unsigned __int16 **, struct _VDS_LUN_INFORMATION *, void *))(*(_QWORD *)v5 + 336LL))(
                v5,
                (unsigned int)v91,
                v62,
                v63,
                Src);
      else
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 **, struct _VDS_LUN_INFORMATION *, void *))(**((_QWORD **)v5 + 46) + 48LL))(
                *((_QWORD *)v5 + 46),
                (unsigned int)v91,
                v62,
                v63,
                Src);
      v73 = v10;
      if ( v10 < 0 )
      {
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 898;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        *(_OWORD *)Val = *(_OWORD *)((char *)v5 + 404);
        CVssFunctionTracer::TranslateProviderError(&v72, &v47, Val, L"IVssHardwareSnapshotProvider::GetTargetLuns");
      }
      v56 = 1;
      dwMessageId = v46 + (_DWORD)v91;
      v11 = (char *)CoTaskMemRealloc(pv, 96LL * (v46 + (unsigned int)v91));
      pv = v11;
      if ( !v11 )
      {
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 912;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        CVssFunctionTracer::Throw(&v72, &v47, 2147942414LL, L"can't re-allocate total luns");
      }
      v68 = v11;
      v12 = (struct _VDS_LUN_INFORMATION *)&v11[96 * v46];
      memcpy_0(v12, Src, Size);
      v46 = dwMessageId;
      CoTaskMemFree(Src);
      Src = 0;
      v59 = 0;
      CVssHardwareProviderWrapper::SaveLunInformation(v13, v61, 1, v12, (unsigned int)v91);
      CVssHardwareProviderWrapper::FreeLunInfo(v63, v62, 0, (unsigned int)v91);
      v63 = 0;
      v62 = 0;
      LODWORD(v91) = 0;
      GetSystemTimeAsFileTime(SystemTimeAsFileTime);
      (*(void (__fastcall **)(struct IVssSnapshotDescription *, _QWORD))(*(_QWORD *)v61 + 56LL))(
        v61,
        *(_QWORD *)SystemTimeAsFileTime);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v61);
    }
    v57 = a2 & 0x20;
    if ( (a2 & 0x20) == 0 )
      goto LABEL_19;
    Size = 0;
    v73 = (*(__int64 (__fastcall **)(_QWORD, size_t *))(**((_QWORD **)v5 + 14) + 24LL))(*((_QWORD *)v5 + 14), &Size);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 952;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    CVssFunctionTracer::CheckForError(&v72, &v47, L"IVssSnapshotSetDescription::SaveAsXML");
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v76);
    dwMessageId = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
                    a3,
                    &GUID_6a36e2b7_7cf8_48b7_8d9f_d4f96fa413a8,
                    &v76);
    v73 = dwMessageId;
    if ( (dwMessageId & 0x80000000) != 0 )
    {
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 961;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      v16 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v47, (CVssDebugInfo *)v81, dwMessageId);
      CVssFunctionTracer::LogError((__int64)&v72, 0x2002u, (__int64)v16, 1u);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v47);
      v17 = v73;
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 964;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      LODWORD(v32) = v17;
      CVssFunctionTracer::Throw(
        &v72,
        &v47,
        2147754754LL,
        L"Error querying for IVssWriterCallback interface.  hr = 0x%08lx",
        v32);
    }
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)Val, &stru_140100AE8);
    if ( !*(_QWORD *)Val )
    {
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 975;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      CVssFunctionTracer::Throw(&v72, &v47, 2147942414LL, L"Can't allocate string");
    }
    v73 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, size_t))(*(_QWORD *)v76 + 32LL))(
            v76,
            *(_QWORD *)Val,
            0,
            0,
            Size);
    v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
    v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
    v49 = L"CORHWPWC";
    v50 = 979;
    v51 = 1;
    v52 = 255;
    v54 = 0x1000000;
    memset_0(v53, 0, sizeof(v53));
    CVssFunctionTracer::CheckForError(&v72, &v47, L"IVssCoordCallback::SetContent");
    SysFreeString(*(BSTR *)Val);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v76);
    SysFreeString((BSTR)Size);
    if ( a5 )
    {
LABEL_19:
      CVssHardwareProviderWrapper::BuildLunMappingStructure(v14, *((struct IVssSnapshotSetDescription **)v5 + 14), &v70);
      CVssHardwareProviderWrapper::LocateAndExposeVolumes(v5, v70, v18, a2, v75);
      CVssHardwareProviderWrapper::WriteDeviceNames(v19, *((struct IVssSnapshotSetDescription **)v5 + 14), v70, 0);
      v20 = (struct IVssSnapshotSetDescription *)ATL::CComPtrBase<IGlobalInterfaceTable>::operator->((__int64)v5 + 112);
      v73 = CVssHardwareProviderWrapper::RemoveUnexposedSnaphots(v5, v20, 1);
      if ( v73 == -2147212512 )
      {
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 995;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        LODWORD(v45) = *((unsigned __int8 *)v5 + 135);
        LODWORD(v44) = *((unsigned __int8 *)v5 + 134);
        LODWORD(v43) = *((unsigned __int8 *)v5 + 133);
        LODWORD(v42) = *((unsigned __int8 *)v5 + 132);
        LODWORD(v41) = *((unsigned __int8 *)v5 + 131);
        LODWORD(v40) = *((unsigned __int8 *)v5 + 130);
        LODWORD(v39) = *((unsigned __int8 *)v5 + 129);
        LODWORD(v38) = *((unsigned __int8 *)v5 + 128);
        LODWORD(v37) = *((unsigned __int16 *)v5 + 63);
        LODWORD(v36) = *((unsigned __int16 *)v5 + 62);
        LODWORD(v33) = *v71;
        CVssFunctionTracer::Throw(
          &v72,
          &v47,
          2147754784LL,
          L"No snapshots were successfully imported for snapshot set {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
          v33,
          v36,
          v37,
          v38,
          v39,
          v40,
          v41,
          v42,
          v43,
          v44,
          v45);
      }
      v21 = (VSS_SNAPSHOT_SET_LIST *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v21 )
        v22 = VSS_SNAPSHOT_SET_LIST::VSS_SNAPSHOT_SET_LIST(v21);
      else
        v22 = 0;
      if ( !v22 )
      {
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 1004;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        CVssFunctionTracer::Throw(&v72, &v47, 2147942414LL, L"Couldn't allocate snapshot set list element");
      }
      CVssAuto<CVssSafeCriticalSection,CVssAutoGenericObj_Storage<CVssSafeCriticalSection,CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalUnlock(CVssSafeCriticalSection &),CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalLock(CVssSafeCriticalSection &)>>::CVssAuto<CVssSafeCriticalSection,CVssAutoGenericObj_Storage<CVssSafeCriticalSection,CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalUnlock(CVssSafeCriticalSection &),CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalLock(CVssSafeCriticalSection &)>>(
        Val,
        (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 8));
      *(_QWORD *)v22 = *((_QWORD *)v5 + 22);
      ATL::CComPtr<IVssSnapshotProvider>::operator=((struct IUnknown **)v22 + 3, (struct IUnknown **)v5 + 14);
      ATL::CComPtr<IVssSnapshotSetDescription>::operator=((struct IUnknown **)v5 + 14, 0);
      *(_OWORD *)((char *)v22 + 8) = *(_OWORD *)v71;
      *((_QWORD *)v5 + 22) = v22;
      if ( (a2 & 8) != 0 )
        *((_BYTE *)v5 + 209) = 1;
      CVssAuto<CVssSafeCriticalSection,CVssAutoGenericObj_Storage<CVssSafeCriticalSection,CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalUnlock(CVssSafeCriticalSection &),CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalLock(CVssSafeCriticalSection &)>>::~CVssAuto<CVssSafeCriticalSection,CVssAutoGenericObj_Storage<CVssSafeCriticalSection,CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalUnlock(CVssSafeCriticalSection &),CVssSafeCriticalSection & (*)(CVssSafeCriticalSection &),&CVssSafeCriticalSection & CriticalLock(CVssSafeCriticalSection &)>>(Val);
      if ( !v57 )
        CVssHardwareProviderWrapper::TrySaveData(v5);
    }
    VSS_OBJECT_PROP_Ptr::~VSS_OBJECT_PROP_Ptr((LPVOID *)&v69);
  }
  catch ( long v77 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v72,
      v77,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::PostSnapshot",
      0x401u,
      v74);
    pv = v68;
    v5 = this;
  }
  catch ( _com_error *v79 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v72,
      v79,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::PostSnapshot",
      0x401u,
      v74);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v72,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::PostSnapshot",
      0x401u,
      v74);
    pv = v68;
    v5 = this;
  }
  catch ( const std::exception *v80 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v72,
      v80,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::PostSnapshot",
      0x401u,
      v74);
  }
  CVssHardwareProviderWrapper::DeleteLunMappingStructure(v23, v70);
  v24 = L"TRUE";
  if ( !v56 )
    v24 = L"FALSE";
  v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
  v49 = L"CORHWPWC";
  v50 = 1031;
  v51 = 1;
  v52 = 255;
  v54 = 0x1000000;
  memset_0(v53, 0, sizeof(v53));
  LODWORD(v36) = v46;
  CVssFunctionTracer::Trace(
    &v72,
    &v47,
    L"PostSnapshots is prior to cleanup code: ft.hr=0x%08lx bGetTargetLunsSucceeded=%s cTotalLuns=%u",
    v73,
    v24,
    v36);
  v25 = v73;
  if ( v73 == 271115 )
  {
    if ( !v56 )
      goto LABEL_59;
    v88 = 0;
    if ( !v46 )
      goto LABEL_59;
    do
    {
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 1042;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      CVssFunctionTracer::Trace(&v72, &v47, L"Calling OnLunEmpty on LUN no %u after a post-export cancel", v88);
      v83 = (char *)pv + 96 * v88;
      if ( CVssFunctionTracer::IsHwDiagEnabled((CVssFunctionTracer *)&v72) )
        v26 = (*(__int64 (__fastcall **)(CVssHardwareProviderWrapper *, _QWORD, char *))(*(_QWORD *)v5 + 352LL))(
                v5,
                0,
                v83);
      else
        v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)v5 + 46) + 64LL))(
                *((_QWORD *)v5 + 46),
                0,
                v83);
      v84 = v26;
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 1052;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      LODWORD(v34) = v84;
      CVssFunctionTracer::Trace(&v72, &v47, L"OnLunEmpty for LUN no %u returned hr=0x%08lx", v88++, v34);
    }
    while ( v88 < v46 );
    v25 = v73;
  }
  if ( v25 < 0 )
  {
    if ( v56 )
    {
      for ( j = 0; j < v46; ++j )
      {
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 1070;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        CVssFunctionTracer::Trace(&v72, &v47, L"Calling OnLunEmpty on LUN no %u after a post-export failure", j);
        v85 = (char *)pv + 96 * j;
        if ( CVssFunctionTracer::IsHwDiagEnabled((CVssFunctionTracer *)&v72) )
          v27 = (*(__int64 (__fastcall **)(CVssHardwareProviderWrapper *, _QWORD, char *))(*(_QWORD *)v5 + 352LL))(
                  v5,
                  0,
                  v85);
        else
          v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)v5 + 46) + 64LL))(
                  *((_QWORD *)v5 + 46),
                  0,
                  v85);
        v86 = v27;
        v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
        v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
        v49 = L"CORHWPWC";
        v50 = 1080;
        v51 = 1;
        v52 = 255;
        v54 = 0x1000000;
        memset_0(v53, 0, sizeof(v53));
        LODWORD(v34) = v86;
        CVssFunctionTracer::Trace(&v72, &v47, L"OnLunEmpty for LUN no %u returned hr=0x%08lx", j, v34);
      }
    }
    else
    {
      *(_OWORD *)Val = *(_OWORD *)v71;
      (*(void (__fastcall **)(CVssHardwareProviderWrapper *, int *))(*(_QWORD *)v5 + 152LL))(v5, Val);
    }
    CVssHardwareProviderWrapper::FreeLunInfo(v63, v62, 0, (unsigned int)v91);
    CVssHardwareProviderWrapper::FreeLunInfo((struct _VDS_LUN_INFORMATION *)Src, 0, 0, v59);
    v28 = v73;
    if ( v73 != -2147212538
      && v73 != -2147212512
      && v73 != -2147212296
      && v73 != -2147212295
      && v73 != -2147212294
      && v73 != -2147212293
      && v73 != -2147212292
      && v73 != -2147024882 )
    {
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
      v48 = L"CVssHardwareProviderWrapper::PostSnapshot";
      v49 = L"CORHWPWC";
      v50 = 1111;
      v51 = 1;
      v52 = 255;
      v54 = 0x1000000;
      memset_0(v53, 0, sizeof(v53));
      CVssFunctionTracer::Trace(&v72, &v47, L"Converting 0x%08lx to VSS_E_NO_SNAPSHOTS_IMPORTED", v28);
      v73 = -2147212512;
    }
  }
LABEL_59:
  CVssHardwareProviderWrapper::FreeLunInfo((struct _VDS_LUN_INFORMATION *)pv, 0, 0, v46);
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = *(_OWORD *)v71;
  CVssDiag::RecordGenericEvent(v78, 0x408u, 0, 0, 0, (struct _GUID *)SystemTimeAsFileTime);
  v29 = v73;
  CVssFunctionTracer::~CVssFunctionTracer(&v72);
  return v29;
}

```

## disassembly

```asm
0x14004d814  mov     rax, rsp
0x14004d817  mov     [rax+20h], r9
0x14004d81b  mov     [rax+18h], r8
0x14004d81f  mov     [rax+10h], edx
0x14004d822  mov     [rax+8], rcx
0x14004d826  push    rbx
0x14004d827  push    rsi
0x14004d828  push    rdi
0x14004d829  push    r12
0x14004d82b  push    r13
0x14004d82d  push    r14
0x14004d82f  push    r15
0x14004d831  sub     rsp, 310h
0x14004d838  mov     r12, rcx
0x14004d83b  lea     r13, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14004d842  mov     [rax-2C0h], r13
0x14004d849  lea     rbx, aCvsshardwarepr_99; "CVssHardwareProviderWrapper::PostSnapsh"...
0x14004d850  mov     [rax-2B8h], rbx
0x14004d857  lea     rdi, aCorhwpwc; "CORHWPWC"
0x14004d85e  mov     [rax-2B0h], rdi
0x14004d865  mov     dword ptr [rax-2A8h], 311h
0x14004d86f  mov     r15d, 1
0x14004d875  mov     [rax-2A4h], r15d
0x14004d87c  mov     esi, 0FFh
0x14004d881  mov     [rax-2A0h], esi
0x14004d887  xor     r14d, r14d
0x14004d88a  mov     dword ptr [rax-220h], 1000000h
0x14004d894  xor     edx, edx; Val
0x14004d896  lea     r8d, [r15+77h]; Size
0x14004d89a  lea     rcx, [rax-298h]; void *
0x14004d8a1  call    memset_0
0x14004d8a6  xor     r8d, r8d
0x14004d8a9  lea     rdx, [rsp+348h+var_2C0]
0x14004d8b1  lea     rcx, [rsp+348h+var_188]
0x14004d8b9  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14004d8be  nop
0x14004d8bf  lea     rcx, [r12+1B8h]; this
0x14004d8c7  mov     [rsp+348h+var_100], rcx
0x14004d8cf  lea     rax, [r12+78h]
0x14004d8d4  mov     [rsp+348h+var_190], rax
0x14004d8dc  movups  xmm0, xmmword ptr [rax]
0x14004d8df  movdqu  xmmword ptr [rsp+348h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x14004d8e8  lea     rax, [rsp+348h+SystemTimeAsFileTime]
0x14004d8f0  mov     [rsp+348h+var_320], rax; struct _GUID *
0x14004d8f5  mov     dword ptr [rsp+348h+var_328], r14d; int
0x14004d8fa  xor     r9d, r9d; unsigned int
0x14004d8fd  mov     r8d, r15d; unsigned int
0x14004d900  mov     edx, 408h; unsigned int
0x14004d905  call    ?RecordGenericEvent@CVssDiag@@QEAAXKKKJU_GUID@@@Z; CVssDiag::RecordGenericEvent(ulong,ulong,ulong,long,_GUID)
0x14004d90a  mov     [rsp+348h+Src], r14
0x14004d912  mov     [rsp+348h+var_1D8], r14
0x14004d91a  mov     eax, r14d
0x14004d91d  mov     [rsp+348h+pv], rax
0x14004d925  mov     [rsp+348h+var_1A8], rax
0x14004d92d  mov     [rsp+348h+var_198], r14
0x14004d935  mov     [rsp+348h+var_1E0], r14
0x14004d93d  mov     dword ptr [rsp+348h+arg_18], r14d
0x14004d945  mov     [rsp+348h+var_1F8], r14d
0x14004d94d  mov     [rsp+348h+var_2C8], r14d
0x14004d955  mov     [rsp+348h+var_210], r14d
0x14004d95d  mov     eax, [rsp+348h+arg_8]
0x14004d964  and     eax, 400000h
0x14004d969  mov     ecx, r14d
0x14004d96c  test    eax, eax
0x14004d96e  setz    cl
0x14004d971  mov     [rsp+348h+var_118], ecx
0x14004d978  mov     [rsp+348h+var_2C0], r13
0x14004d980  mov     [rsp+348h+var_2B8], rbx
0x14004d988  mov     [rsp+348h+var_2B0], rdi
0x14004d990  mov     [rsp+348h+var_2A8], 333h
0x14004d99b  mov     [rsp+348h+var_2A4], r15d
0x14004d9a3  mov     [rsp+348h+var_2A0], esi
0x14004d9aa  mov     [rsp+348h+var_220], 1000000h
0x14004d9b5  xor     edx, edx; Val
0x14004d9b7  lea     r8d, [r15+77h]; Size
0x14004d9bb  lea     rcx, [rsp+348h+var_298]; void *
0x14004d9c3  call    memset_0
0x14004d9c8  lea     r8d, [rsi-1Ah]
0x14004d9cc  lea     rdx, [rsp+348h+var_2C0]
0x14004d9d4  lea     rcx, [rsp+348h+var_188]
0x14004d9dc  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x14004d9e1  mov     [rsp+348h+var_2C0], r13
0x14004d9e9  mov     [rsp+348h+var_2B8], rbx
0x14004d9f1  mov     [rsp+348h+var_2B0], rdi
0x14004d9f9  mov     [rsp+348h+var_2A8], 334h
0x14004da04  mov     [rsp+348h+var_2A4], r15d
0x14004da0c  mov     [rsp+348h+var_2A0], esi
0x14004da13  mov     [rsp+348h+var_220], 1000000h
0x14004da1e  xor     edx, edx; Val
0x14004da20  lea     r8d, [r15+77h]; Size
0x14004da24  lea     rcx, [rsp+348h+var_298]; void *
0x14004da2c  call    memset_0
0x14004da31  lea     r9, aProvider; "Provider"
0x14004da38  mov     r8d, 1394h
0x14004da3e  lea     rdx, [rsp+348h+var_2C0]
0x14004da46  lea     rcx, [rsp+348h+var_188]
0x14004da4e  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x14004da53  mov     [rsp+348h+var_1A0], r14
0x14004da5b  movups  xmm0, xmmword ptr [r12+194h]
0x14004da64  movdqu  xmmword ptr [rsp+348h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x14004da6d  lea     rdx, [rsp+348h+var_1A0]; struct VSS_OBJECT_PROP_Ptr *
0x14004da75  lea     rcx, [rsp+348h+SystemTimeAsFileTime]; struct _GUID
0x14004da7d  call    ?GetProviderStructure@CVssProviderManager@@SAHU_GUID@@AEAVVSS_OBJECT_PROP_Ptr@@@Z; CVssProviderManager::GetProviderStructure(_GUID,VSS_OBJECT_PROP_Ptr &)
0x14004da82  mov     [rsp+348h+var_2C0], r13
0x14004da8a  mov     [rsp+348h+var_2B8], rbx
0x14004da92  mov     [rsp+348h+var_2B0], rdi
0x14004da9a  mov     [rsp+348h+var_2A8], 33Ah
0x14004daa5  mov     [rsp+348h+var_2A4], r15d
0x14004daad  mov     [rsp+348h+var_2A0], esi
0x14004dab4  mov     [rsp+348h+var_220], 1000000h
0x14004dabf  xor     edx, edx; Val
0x14004dac1  lea     r8d, [r15+77h]; Size
0x14004dac5  lea     rcx, [rsp+348h+var_298]; void *
0x14004dacd  call    memset_0
0x14004dad2  mov     r9, [rsp+348h+var_1A0]
0x14004dada  mov     r9, [r9+18h]
0x14004dade  mov     r8d, 1398h
0x14004dae4  lea     rdx, [rsp+348h+var_2C0]
0x14004daec  lea     rcx, [rsp+348h+var_188]
0x14004daf4  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x14004daf9  mov     [rsp+348h+var_2C0], r13
0x14004db01  mov     [rsp+348h+var_2B8], rbx
0x14004db09  mov     [rsp+348h+var_2B0], rdi
0x14004db11  mov     [rsp+348h+var_2A8], 33Bh
0x14004db1c  mov     [rsp+348h+var_2A4], r15d
0x14004db24  mov     [rsp+348h+var_2A0], esi
0x14004db2b  mov     [rsp+348h+var_220], 1000000h
0x14004db36  xor     edx, edx; Val
0x14004db38  lea     r8d, [r15+77h]; Size
0x14004db3c  lea     rcx, [rsp+348h+var_298]; void *
0x14004db44  call    memset_0
0x14004db49  mov     rax, [rsp+348h+var_1A0]
0x14004db51  mov     r9, [rax+28h]
0x14004db55  mov     r8d, 1399h
0x14004db5b  lea     rdx, [rsp+348h+var_2C0]
0x14004db63  lea     rcx, [rsp+348h+var_188]
0x14004db6b  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x14004db70  mov     [rsp+348h+var_2C0], r13
0x14004db78  mov     [rsp+348h+var_2B8], rbx
0x14004db80  mov     [rsp+348h+var_2B0], rdi
0x14004db88  mov     [rsp+348h+var_2A8], 33Ch
0x14004db93  mov     [rsp+348h+var_2A4], r15d
0x14004db9b  mov     [rsp+348h+var_2A0], esi
0x14004dba2  mov     [rsp+348h+var_220], 1000000h
0x14004dbad  xor     edx, edx; Val
0x14004dbaf  lea     r8d, [r15+77h]; Size
0x14004dbb3  lea     rcx, [rsp+348h+var_298]; void *
0x14004dbbb  call    memset_0
0x14004dbc0  movzx   eax, byte ptr [r12+1A3h]
0x14004dbc9  movzx   ecx, byte ptr [r12+1A2h]
0x14004dbd2  movzx   edx, byte ptr [r12+1A1h]
0x14004dbdb  movzx   r8d, byte ptr [r12+1A0h]
0x14004dbe4  movzx   r9d, byte ptr [r12+19Fh]
0x14004dbed  movzx   r10d, byte ptr [r12+19Eh]
0x14004dbf6  movzx   r11d, byte ptr [r12+19Dh]
0x14004dbff  movzx   ebx, byte ptr [r12+19Ch]
0x14004dc08  movzx   edi, word ptr [r12+19Ah]
0x14004dc11  movzx   esi, word ptr [r12+198h]
0x14004dc1a  mov     [rsp+348h+var_2D8], eax
0x14004dc1e  mov     dword ptr [rsp+348h+var_2E0], ecx
0x14004dc22  mov     dword ptr [rsp+348h+var_2E8], edx
0x14004dc26  mov     dword ptr [rsp+348h+var_2F0], r8d
0x14004dc2b  mov     dword ptr [rsp+348h+var_2F8], r9d
0x14004dc30  mov     dword ptr [rsp+348h+var_300], r10d
0x14004dc35  mov     dword ptr [rsp+348h+var_308], r11d
0x14004dc3a  mov     dword ptr [rsp+348h+var_310], ebx
0x14004dc3e  mov     dword ptr [rsp+348h+var_318], edi
0x14004dc42  mov     dword ptr [rsp+348h+var_320], esi
0x14004dc46  mov     eax, [r12+194h]
0x14004dc4e  mov     dword ptr [rsp+348h+var_328], eax
0x14004dc52  lea     r9, a8x4x4x2x2x2x2x; "{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%."...
0x14004dc59  mov     r8d, 1391h
0x14004dc5f  lea     rdx, [rsp+348h+var_2C0]
0x14004dc67  lea     rcx, [rsp+348h+var_188]
0x14004dc6f  call    ?AddContextEx@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBGZZ; CVssFunctionTracer::AddContextEx(CVssDebugInfo,uint,ushort const *,...)
0x14004dc74  mov     [rsp+348h+var_1B8], r14d
0x14004dc7c  mov     rcx, [r12+70h]
0x14004dc81  mov     rax, [rcx]
0x14004dc84  lea     rdx, [rsp+348h+var_1B8]
0x14004dc8c  mov     rax, [rax+58h]
0x14004dc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dc95  mov     [rsp+348h+var_180], eax
0x14004dc9c  mov     [rsp+348h+var_2C0], r13
0x14004dca4  lea     rdi, aCvsshardwarepr_99; "CVssHardwareProviderWrapper::PostSnapsh"...
0x14004dcab  mov     [rsp+348h+var_2B8], rdi
0x14004dcb3  lea     rsi, aCorhwpwc; "CORHWPWC"
0x14004dcba  mov     [rsp+348h+var_2B0], rsi
0x14004dcc2  mov     [rsp+348h+var_2A8], 344h
0x14004dccd  mov     [rsp+348h+var_2A4], r15d
0x14004dcd5  mov     ebx, 0FFh
0x14004dcda  mov     [rsp+348h+var_2A0], ebx
0x14004dce1  mov     [rsp+348h+var_220], 1000000h
0x14004dcec  xor     edx, edx; Val
0x14004dcee  lea     r8d, [r15+77h]; Size
0x14004dcf2  lea     rcx, [rsp+348h+var_298]; void *
0x14004dcfa  call    memset_0
0x14004dcff  lea     r8, aIvsssnapshotse_8; "IVssSnapshotSetDescription::GetSnapshot"...
0x14004dd06  lea     rdx, [rsp+348h+var_2C0]
0x14004dd0e  lea     rcx, [rsp+348h+var_188]
0x14004dd16  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14004dd1b  mov     edx, r14d
0x14004dd1e  mov     [rsp+348h+var_20C], edx
0x14004dd25  cmp     edx, [rsp+348h+var_1B8]
0x14004dd2c  jnb     loc_14004E1F5
0x14004dd32  lea     rcx, [rsp+348h+var_1E8]
0x14004dd3a  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14004dd3f  nop
0x14004dd40  mov     rcx, [r12+70h]
0x14004dd45  mov     rax, [rcx]
0x14004dd48  lea     r8, [rsp+348h+var_1E8]
0x14004dd50  mov     rax, [rax+70h]
0x14004dd54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004dd59  mov     [rsp+348h+var_180], eax
0x14004dd60  mov     [rsp+348h+var_2C0], r13
0x14004dd68  mov     [rsp+348h+var_2B8], rdi
0x14004dd70  mov     [rsp+348h+var_2B0], rsi
0x14004dd78  mov     [rsp+348h+var_2A8], 34Dh
0x14004dd83  mov     [rsp+348h+var_2A4], r15d
0x14004dd8b  mov     [rsp+348h+var_2A0], ebx
0x14004dd92  mov     [rsp+348h+var_220], 1000000h
0x14004dd9d  xor     edx, edx; Val
0x14004dd9f  lea     r8d, [rdx+78h]; Size
0x14004dda3  lea     rcx, [rsp+348h+var_298]; void *
0x14004ddab  call    memset_0
0x14004ddb0  lea     r8, aIvsssnapshotse; "IVssSnapshotSetDescription::GetSnapshot"...
0x14004ddb7  lea     rdx, [rsp+348h+var_2C0]
0x14004ddbf  lea     rcx, [rsp+348h+var_188]
0x14004ddc7  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14004ddcc  mov     rcx, [rsp+348h+var_1E8]
0x14004ddd4  mov     rax, [rcx]
0x14004ddd7  mov     edx, [rsp+348h+arg_8]
0x14004ddde  bts     edx, 10h
0x14004dde2  mov     rax, [rax+48h]
0x14004dde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ddeb  mov     [rsp+348h+var_180], eax
0x14004ddf2  mov     [rsp+348h+var_2C0], r13
0x14004ddfa  mov     [rsp+348h+var_2B8], rdi
0x14004de02  mov     [rsp+348h+var_2B0], rsi
0x14004de0a  mov     [rsp+348h+var_2A8], 351h
0x14004de15  mov     [rsp+348h+var_2A4], r15d
0x14004de1d  mov     [rsp+348h+var_2A0], ebx
0x14004de24  mov     [rsp+348h+var_220], 1000000h
0x14004de2f  xor     edx, edx; Val
0x14004de31  lea     r8d, [rdx+78h]; Size
0x14004de35  lea     rcx, [rsp+348h+var_298]; void *
0x14004de3d  call    memset_0
0x14004de42  lea     r8, aIvsssnapshotde_0; "IVssSnapshotDescription::SetAttributes"
0x14004de49  lea     rdx, [rsp+348h+var_2C0]
0x14004de51  lea     rcx, [rsp+348h+var_188]
0x14004de59  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14004de5e  lea     rax, [rsp+348h+arg_18]
0x14004de66  mov     [rsp+348h+var_320], rax; unsigned int *
0x14004de6b  lea     rax, [rsp+348h+var_1D8]
0x14004de73  mov     [rsp+348h+var_328], rax; struct _VDS_LUN_INFORMATION **
0x14004de78  lea     r9, [rsp+348h+var_1E0]; unsigned __int16 ***
0x14004de80  xor     r8d, r8d; bool
0x14004de83  mov     rdx, [rsp+348h+var_1E8]; struct IVssSnapshotDescription *
0x14004de8b  call    ?GetLunInformation@CVssHardwareProviderWrapper@@AEAAXPEAVIVssSnapshotDescription@@_NPEAPEAPEAGPEAPEAU_VDS_LUN_INFORMATION@@PEAI@Z; CVssHardwareProviderWrapper::GetLunInformation(IVssSnapshotDescription *,bool,ushort * * *,_VDS_LUN_INFORMATION * *,uint *)
0x14004de90  mov     eax, dword ptr [rsp+348h+arg_18]
0x14004de97  lea     rax, [rax+rax*2]
0x14004de9b  shl     rax, 5
0x14004de9f  mov     [rsp+348h+Size], rax
0x14004dea7  mov     rcx, rax; cb
0x14004deaa  call    cs:__imp_CoTaskMemAlloc
0x14004deb0  mov     [rsp+348h+Src], rax
0x14004deb8  test    rax, rax
0x14004debb  jnz     short loc_14004DF2F
0x14004debd  mov     [rsp+348h+var_2C0], r13
0x14004dec5  mov     [rsp+348h+var_2B8], rdi
0x14004decd  mov     [rsp+348h+var_2B0], rsi
0x14004ded5  mov     [rsp+348h+var_2A8], 360h
0x14004dee0  mov     [rsp+348h+var_2A4], r15d
0x14004dee8  mov     [rsp+348h+var_2A0], ebx
0x14004deef  mov     [rsp+348h+var_220], 1000000h
0x14004defa  xor     edx, edx; Val
0x14004defc  lea     r8d, [rax+78h]; Size
0x14004df00  lea     rcx, [rsp+348h+var_298]; void *
0x14004df08  call    memset_0
0x14004df0d  lea     r9, aCanTAllocateDe_0; "can't allocate destination luns"
0x14004df14  mov     r8d, 8007000Eh
0x14004df1a  lea     rdx, [rsp+348h+var_2C0]
0x14004df22  lea     rcx, [rsp+348h+var_188]
0x14004df2a  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14004df2f  mov     ecx, dword ptr [rsp+348h+arg_18]
0x14004df36  mov     [rsp+348h+var_1F8], ecx
0x14004df3d  mov     r8, [rsp+348h+Size]; Size
0x14004df45  xor     edx, edx; Val
0x14004df47  mov     rcx, rax; void *
0x14004df4a  call    memset_0
0x14004df4f  lea     rcx, [rsp+348h+var_188]; this
0x14004df57  call    ?IsHwDiagEnabled@CVssFunctionTracer@@QEAA_NXZ; CVssFunctionTracer::IsHwDiagEnabled(void)
0x14004df5c  mov     rdx, [rsp+348h+Src]
0x14004df64  mov     r9, [rsp+348h+var_1D8]
0x14004df6c  mov     r8, [rsp+348h+var_1E0]
0x14004df74  mov     [rsp+348h+var_328], rdx
0x14004df79  mov     edx, dword ptr [rsp+348h+arg_18]
0x14004df80  test    al, al
0x14004df82  jz      short loc_14004DF99
0x14004df84  mov     rax, [r12]
0x14004df88  mov     rcx, r12
  ... truncated ...
```
