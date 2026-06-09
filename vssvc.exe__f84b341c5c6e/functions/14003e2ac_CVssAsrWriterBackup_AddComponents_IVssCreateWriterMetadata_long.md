# CVssAsrWriterBackup::_AddComponents(IVssCreateWriterMetadata *,long *)

- ea: `0x14003e2ac`
- end: `0x14003ee94`
- name: `?_AddComponents@CVssAsrWriterBackup@@AEAAJPEAVIVssCreateWriterMetadata@@PEAJ@Z`
- size: `3048`
- prototype: `__int64 __fastcall(CVssAsrWriterBackup *__hidden this, struct IVssCreateWriterMetadata *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14005b9d0`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140019e30`
- `0x14003e2ac`
- `0x14003fc04`
- `0x140070fcc`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400d24ec`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e38a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e38a`
- `VssTrace!__imp_VssTraceMessage` at `0x14003e49c`
- `VssTrace!__imp_VssTraceMessage` at `0x14003e49c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003e3e7`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003e3e7`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003e3d5`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003e3d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003edfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ee14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ee2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ee40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003edfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ee14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ee2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003ee40`

## string_xrefs

- `0x14003e2ca`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003e543`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003e643`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003e794`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003e845`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003e98a`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003ea90`: `base\stor\vss\modules\writers\asrwriter.cxx`
- `0x14003e2d8`: `CVssAsrWriterBackup::_AddComponents`
- `0x14003e999`: `CVssAsrWriterBackup::_AddComponents`
- `0x14003ea9f`: `CVssAsrWriterBackup::_AddComponents`
- `0x14003e5ef`: `IVssCreateWriterMetadata::AddComponent`
- `0x14003e6ef`: `IVssAsrWriterBackup::GetVolumeComponents`
- `0x14003e7f6`: `IVssCreateWriterMetadata::AddComponent Volume component`
- `0x14003e8f1`: `IVssAsrWriterBackup::GetDiskComponents`
- `0x14003eb43`: `IVssAsrWriterBackup::GetBcdComponents`
- `0x14003ea3d`: `IVssCreateWriterMetadata::AddComponent Disk component`
- `0x14003ec71`: `IVssCreateWriterMetadata::AddComponent BCD component`
- `0x14003ed85`: `IVssCreateWriterMetadata::AddFilesToFileGroup BCD component`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssAsrWriterBackup::_AddComponents(
        CVssAsrWriterBackup *this,
        struct IVssCreateWriterMetadata *a2,
        int *a3)
{
  int v6; // eax
  const unsigned __int16 **v7; // rcx
  int v8; // ebx
  __int64 v9; // rax
  int v10; // ebx
  CVssDebugInfo *v11; // rax
  int v12; // ebx
  CVssDebugInfo *v13; // rax
  unsigned int i; // ebx
  __int64 v15; // r8
  __int64 v16; // rax
  bool v17; // cl
  int v18; // ebx
  CVssDebugInfo *v19; // rax
  unsigned int j; // esi
  __int64 v21; // rax
  int v22; // ebx
  CVssDebugInfo *v23; // rax
  int v24; // ebx
  CVssDebugInfo *v25; // rax
  __int64 v26; // rax
  int v27; // ebx
  CVssDebugInfo *v28; // rax
  __int64 v29; // rax
  int v30; // ebx
  CVssDebugInfo *v31; // rax
  unsigned int v32; // ebx
  unsigned __int16 k; // cx
  __int64 v35; // [rsp+28h] [rbp-2D0h]
  int v36; // [rsp+38h] [rbp-2C0h]
  __int64 v37; // [rsp+40h] [rbp-2B8h]
  int v38; // [rsp+48h] [rbp-2B0h]
  int v39; // [rsp+50h] [rbp-2A8h]
  const unsigned __int16 **v40; // [rsp+70h] [rbp-288h]
  const unsigned __int16 **v41; // [rsp+78h] [rbp-280h] BYREF
  const unsigned __int16 *v42; // [rsp+80h] [rbp-278h] BYREF
  const unsigned __int16 *v43; // [rsp+88h] [rbp-270h]
  const unsigned __int16 *v44; // [rsp+90h] [rbp-268h]
  __int64 v45; // [rsp+98h] [rbp-260h]
  int v46; // [rsp+A0h] [rbp-258h]
  _QWORD v47[15]; // [rsp+A8h] [rbp-250h] BYREF
  int v48; // [rsp+120h] [rbp-1D8h]
  unsigned __int64 v49; // [rsp+130h] [rbp-1C8h] BYREF
  int v50; // [rsp+138h] [rbp-1C0h]
  const unsigned __int16 *v51; // [rsp+140h] [rbp-1B8h]
  const unsigned __int16 *v52; // [rsp+148h] [rbp-1B0h]
  unsigned int v53; // [rsp+150h] [rbp-1A8h]
  unsigned int v54; // [rsp+154h] [rbp-1A4h]
  const unsigned __int16 *v55; // [rsp+158h] [rbp-1A0h]
  unsigned int v56; // [rsp+160h] [rbp-198h]
  DWORD TickCount; // [rsp+164h] [rbp-194h]
  int v58; // [rsp+168h] [rbp-190h]
  __int128 v59; // [rsp+170h] [rbp-188h]
  __int128 v60; // [rsp+180h] [rbp-178h]
  const unsigned __int16 **v61; // [rsp+190h] [rbp-168h]
  int pExceptionObject; // [rsp+1A0h] [rbp-158h] BYREF
  int v63; // [rsp+1A4h] [rbp-154h] BYREF
  int v64; // [rsp+1A8h] [rbp-150h] BYREF
  int v65; // [rsp+1ACh] [rbp-14Ch] BYREF
  int v66; // [rsp+1B0h] [rbp-148h] BYREF
  int v67; // [rsp+1B4h] [rbp-144h] BYREF
  int v68; // [rsp+1B8h] [rbp-140h] BYREF
  __int64 v69; // [rsp+1C0h] [rbp-138h] BYREF
  LPVOID pv[2]; // [rsp+1C8h] [rbp-130h] BYREF
  LPVOID v71[2]; // [rsp+1D8h] [rbp-120h]
  LPVOID v72[2]; // [rsp+1E8h] [rbp-110h]
  __int64 v73; // [rsp+1F8h] [rbp-100h]
  int v74; // [rsp+200h] [rbp-F8h] BYREF
  _com_error *v75; // [rsp+208h] [rbp-F0h] BYREF
  const std::exception *v76; // [rsp+210h] [rbp-E8h] BYREF
  _BYTE v77[224]; // [rsp+218h] [rbp-E0h] BYREF
  unsigned int v78; // [rsp+308h] [rbp+10h] BYREF
  unsigned int v79; // [rsp+310h] [rbp+18h] BYREF
  __int64 v80; // [rsp+318h] [rbp+20h] BYREF

  v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v43 = L"CVssAsrWriterBackup::_AddComponents";
  v44 = L"WRTASRWC";
  v45 = 0x4000000B2LL;
  v46 = 255;
  v48 = 0x1000000;
  memset_0(v47, 0, sizeof(v47));
  v50 = 0;
  v55 = L"CVssAsrWriterBackup::_AddComponents";
  v51 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
  v52 = L"WRTASRWC";
  v53 = 178;
  v54 = 4;
  TickCount = GetTickCount();
  v58 = 255;
  v49 = 0xFFFFFFFF00000000uLL;
  v61 = 0;
  v59 = 0;
  v60 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 )
  {
    v7 = v61;
  }
  else
  {
    v6 = VssSetTracingContextPerThread(&v49);
    v7 = v61;
    if ( v6 >= 0 )
      v7 = v41;
    v61 = v7;
  }
  if ( v7 )
    v56 = *((_DWORD *)v7 + 12) + 1;
  else
    v56 = 0;
  v8 = 160;
  if ( v58 != 255 )
    v8 = v58;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v49) )
    VssTraceMessage(v51, v52, v53, v56, v54, v55, L"ENTER", v8, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
  try
  {
    v80 = 0;
    v69 = 0;
    *(_OWORD *)pv = 0;
    *(_OWORD *)v71 = 0;
    *(_OWORD *)v72 = 0;
    v73 = 0;
    v78 = 0;
    v79 = 0;
    *a3 = 0;
    v9 = *(_QWORD *)a2;
    LOBYTE(v39) = 0;
    LOBYTE(v38) = 0;
    LOBYTE(v37) = 0;
    LOBYTE(v36) = 0;
    v10 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, const wchar_t *, const wchar_t *, _QWORD, _DWORD, int, _DWORD, int, int, _DWORD))(v9 + 16))(
            a2,
            2,
            L"ASR",
            L"ASR",
            L"ASR",
            0,
            0,
            v36,
            v37,
            v38,
            v39,
            0);
    v50 = v10;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 0x4000000CDLL;
    v46 = 255;
    v48 = 0x1000000;
    memset_0(v47, 0, sizeof(v47));
    v41 = &v42;
    if ( v10 < 0 )
    {
      if ( v10 == -2147418113 )
      {
        pExceptionObject = -2147418113;
        throw (long *)&pExceptionObject;
      }
      v11 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
      CVssFunctionTracer::TranslateError(&v49, v11, (unsigned int)v10, L"IVssCreateWriterMetadata::AddComponent");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64 *))(**((_QWORD **)this + 2) + 32LL))(
            *((_QWORD *)this + 2),
            &v78,
            &v80);
    v50 = v12;
    *a3 = v12;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 0x4000000D5LL;
    v46 = 255;
    v48 = 0x1000000;
    memset_0(v47, 0, sizeof(v47));
    v40 = &v42;
    if ( v12 < 0 )
    {
      if ( v12 == -2147418113 )
      {
        v63 = -2147418113;
        throw (long *)&v63;
      }
      v13 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
      CVssFunctionTracer::TranslateError(&v49, v13, (unsigned int)v12, L"IVssAsrWriterBackup::GetVolumeComponents");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
    for ( i = 0; i < v78; ++i )
    {
      v15 = 56LL * i;
      v16 = *(_QWORD *)a2;
      v17 = *(_DWORD *)(v15 + v80 + 32) != 0;
      LOBYTE(v39) = *(_DWORD *)(v15 + v80 + 36) != 0;
      LOBYTE(v38) = v17;
      LOBYTE(v37) = 0;
      LOBYTE(v36) = 0;
      v50 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD, int, _DWORD, int, int, _DWORD))(v16 + 16))(
              a2,
              2,
              L"Volumes",
              *(_QWORD *)(v15 + v80 + 8),
              *(_QWORD *)(v15 + v80 + 16),
              0,
              0,
              v36,
              v37,
              v38,
              v39,
              0);
      v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v43 = L"CVssAsrWriterBackup::_AddComponents";
      v44 = L"WRTASRWC";
      v45 = 0x4000000E5LL;
      v46 = 255;
      v48 = 0x1000000;
      memset_0(v47, 0, sizeof(v47));
      CVssFunctionTracer::CheckForErrorInternal(&v49, &v42, L"IVssCreateWriterMetadata::AddComponent Volume component");
    }
    v18 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64 *))(**((_QWORD **)this + 2) + 40LL))(
            *((_QWORD *)this + 2),
            &v79,
            &v69);
    v50 = v18;
    *a3 = v18;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 0x4000000EELL;
    v46 = 255;
    v48 = 0x1000000;
    memset_0(v47, 0, sizeof(v47));
    v40 = &v42;
    if ( v18 < 0 )
    {
      if ( v18 == -2147418113 )
      {
        v64 = -2147418113;
        throw (long *)&v64;
      }
      v19 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
      CVssFunctionTracer::TranslateError(&v49, v19, (unsigned int)v18, L"IVssAsrWriterBackup::GetDiskComponents");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
    for ( j = 0; j < v79; ++j )
    {
      v21 = *(_QWORD *)a2;
      LOBYTE(v39) = 1;
      LOBYTE(v38) = 1;
      LOBYTE(v37) = 0;
      LOBYTE(v36) = 0;
      v22 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, _QWORD, _QWORD, _QWORD, _DWORD, int, _DWORD, int, int, _DWORD))(v21 + 16))(
              a2,
              2,
              L"Disks",
              *(_QWORD *)(56LL * j + v69 + 8),
              *(_QWORD *)(56LL * j + v69 + 16),
              0,
              0,
              v36,
              v37,
              v38,
              v39,
              0);
      v50 = v22;
      v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
      v43 = L"CVssAsrWriterBackup::_AddComponents";
      v44 = L"WRTASRWC";
      v45 = 0x4000000FELL;
      v46 = 255;
      v48 = 0x1000000;
      memset_0(v47, 0, sizeof(v47));
      v40 = &v42;
      if ( v22 < 0 )
      {
        if ( v22 == -2147418113 )
        {
          v65 = -2147418113;
          throw (long *)&v65;
        }
        v23 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
        CVssFunctionTracer::TranslateError(
          &v49,
          v23,
          (unsigned int)v22,
          L"IVssCreateWriterMetadata::AddComponent Disk component");
      }
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), pv);
    v50 = v24;
    *a3 = v24;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 0x400000107LL;
    v46 = 255;
    v48 = 0x1000000;
    memset_0(v47, 0, sizeof(v47));
    v40 = &v42;
    if ( v24 < 0 )
    {
      if ( v24 == -2147418113 )
      {
        v66 = -2147418113;
        throw (long *)&v66;
      }
      v25 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
      CVssFunctionTracer::TranslateError(&v49, v25, (unsigned int)v24, L"IVssAsrWriterBackup::GetBcdComponents");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
    v26 = *(_QWORD *)a2;
    LOBYTE(v39) = 0;
    LOBYTE(v38) = LODWORD(v72[0]) != 0;
    LOBYTE(v37) = 0;
    LOBYTE(v36) = 0;
    v27 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, const wchar_t *, LPVOID, _QWORD, _DWORD, int, _DWORD, int, int, _DWORD))(v26 + 16))(
            a2,
            2,
            L"BCD",
            L"BCD",
            v71[0],
            0,
            0,
            v36,
            v37,
            v38,
            v39,
            0);
    v50 = v27;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 0x400000114LL;
    v46 = 255;
    v48 = 0x1000000;
    memset_0(v47, 0, sizeof(v47));
    v40 = &v42;
    if ( v27 < 0 )
    {
      if ( v27 == -2147418113 )
      {
        v67 = -2147418113;
        throw (long *)&v67;
      }
      v28 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
      CVssFunctionTracer::TranslateError(
        &v49,
        v28,
        (unsigned int)v27,
        L"IVssCreateWriterMetadata::AddComponent BCD component");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
    v29 = *(_QWORD *)a2;
    LOBYTE(v35) = 1;
    v30 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, const wchar_t *, const wchar_t *, LPVOID, const wchar_t *, _DWORD, _QWORD, _DWORD))(v29 + 40))(
            a2,
            L"BCD",
            L"BCD",
            v72[1],
            L"*.*",
            v35,
            0,
            v73);
    v50 = v30;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 0x40000011FLL;
    v46 = 255;
    v48 = 0x1000000;
    memset_0(v47, 0, sizeof(v47));
    v40 = &v42;
    if ( v30 < 0 )
    {
      if ( v30 == -2147418113 )
      {
        v68 = -2147418113;
        throw (long *)&v68;
      }
      v31 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v77, (const struct CVssDebugInfo *)&v42);
      CVssFunctionTracer::TranslateError(
        &v49,
        v31,
        (unsigned int)v30,
        L"IVssCreateWriterMetadata::AddFilesToFileGroup BCD component");
    }
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v42);
  }
  catch ( long v74 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v49,
      v74,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::_AddComponents",
      0x121u,
      v54);
  }
  catch ( _com_error *v75 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v49,
      v75,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::_AddComponents",
      0x121u,
      v54);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v49,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::_AddComponents",
      0x121u,
      v54);
  }
  catch ( const std::exception *v76 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v49,
      v76,
      L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx",
      L"WRTASRWC",
      L"CVssAsrWriterBackup::_AddComponents",
      0x121u,
      v54);
  }
  catch ( ... )
  {
    v50 = -2147418113;
    v42 = L"base\\stor\\vss\\modules\\writers\\asrwriter.cxx";
    v43 = L"CVssAsrWriterBackup::_AddComponents";
    v44 = L"WRTASRWC";
    v45 = 289;
    v46 = 255;
    v48 = 0x1000000;
    for ( k = 0; k < 0xFu; ++k )
      v47[k] = 0;
    CVssFunctionTracer::Trace(&v49, &v42, L"Exception caught!");
  }
  if ( v78 )
    AsrFreeComponentArray(&v78, &v80);
  if ( v79 )
    AsrFreeComponentArray(&v79, &v69);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v71[0]);
  v71[0] = 0;
  CoTaskMemFree(v72[1]);
  *(_OWORD *)pv = 0;
  *(_OWORD *)v71 = 0;
  *(_OWORD *)v72 = 0;
  v73 = 0;
  v32 = v50;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v49);
  return v32;
}

```

## disassembly

```asm
0x14003e2ac  mov     r11, rsp
0x14003e2af  push    rbx
0x14003e2b0  push    rsi
0x14003e2b1  push    rdi
0x14003e2b2  push    r12
0x14003e2b4  push    r13
0x14003e2b6  push    r14
0x14003e2b8  push    r15
0x14003e2ba  sub     rsp, 2C0h
0x14003e2c1  mov     r15, r8
0x14003e2c4  mov     r14, rdx
0x14003e2c7  mov     r13, rcx
0x14003e2ca  lea     rax, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x14003e2d1  mov     [r11-278h], rax
0x14003e2d8  lea     rsi, aCvssasrwriterb_11; "CVssAsrWriterBackup::_AddComponents"
0x14003e2df  mov     [r11-270h], rsi
0x14003e2e6  lea     rax, aWrtasrwc; "WRTASRWC"
0x14003e2ed  mov     [r11-268h], rax
0x14003e2f4  mov     [rsp+2F8h+var_260], 0B2h
0x14003e2ff  mov     [rsp+2F8h+var_25C], 4
0x14003e30a  mov     r12d, 0FFh
0x14003e310  mov     [r11-258h], r12d
0x14003e317  xor     edi, edi
0x14003e319  mov     [rsp+2F8h+var_1D8], 1000000h
0x14003e324  xor     edx, edx; Val
0x14003e326  lea     r8d, [rdi+78h]; Size
0x14003e32a  lea     rcx, [r11-250h]; void *
0x14003e331  call    memset_0
0x14003e336  mov     rax, [rsp+2F8h+var_278]
0x14003e33e  mov     rcx, [rsp+2F8h+var_268]
0x14003e346  mov     edx, [rsp+2F8h+var_260]
0x14003e34d  mov     r8d, [rsp+2F8h+var_25C]
0x14003e355  mov     ebx, [rsp+2F8h+var_258]
0x14003e35c  mov     [rsp+2F8h+var_1C0], edi
0x14003e363  mov     [rsp+2F8h+var_1A0], rsi
0x14003e36b  mov     [rsp+2F8h+var_1B8], rax
0x14003e373  mov     [rsp+2F8h+var_1B0], rcx
0x14003e37b  mov     [rsp+2F8h+var_1A8], edx
0x14003e382  mov     [rsp+2F8h+var_1A4], r8d
0x14003e38a  call    cs:__imp_GetTickCount
0x14003e390  mov     [rsp+2F8h+var_194], eax
0x14003e397  mov     [rsp+2F8h+var_1C4], 0FFFFFFFFh
0x14003e3a2  mov     [rsp+2F8h+var_190], ebx
0x14003e3a9  mov     [rsp+2F8h+var_1C8], edi
0x14003e3b0  mov     [rsp+2F8h+var_168], rdi
0x14003e3b8  xorps   xmm0, xmm0
0x14003e3bb  movups  [rsp+2F8h+var_188], xmm0
0x14003e3c3  movups  [rsp+2F8h+var_178], xmm0
0x14003e3cb  mov     [rsp+2F8h+var_280], rdi
0x14003e3d0  lea     rcx, [rsp+2F8h+var_280]
0x14003e3d5  call    cs:__imp_VssGetTracingContextPerThread
0x14003e3db  test    eax, eax
0x14003e3dd  js      short loc_14003E407
0x14003e3df  lea     rcx, [rsp+2F8h+var_1C8]
0x14003e3e7  call    cs:__imp_VssSetTracingContextPerThread
0x14003e3ed  mov     rcx, [rsp+2F8h+var_168]
0x14003e3f5  test    eax, eax
0x14003e3f7  cmovns  rcx, [rsp+2F8h+var_280]
0x14003e3fd  mov     [rsp+2F8h+var_168], rcx
0x14003e405  jmp     short loc_14003E40F
0x14003e407  mov     rcx, [rsp+2F8h+var_168]
0x14003e40f  test    rcx, rcx
0x14003e412  jz      short loc_14003E422
0x14003e414  mov     eax, [rcx+30h]
0x14003e417  inc     eax
0x14003e419  mov     [rsp+2F8h+var_198], eax
0x14003e420  jmp     short loc_14003E429
0x14003e422  mov     [rsp+2F8h+var_198], edi
0x14003e429  mov     ebx, 0A0h
0x14003e42e  cmp     [rsp+2F8h+var_190], r12d
0x14003e436  cmovnz  ebx, [rsp+2F8h+var_190]
0x14003e43e  lea     rcx, [rsp+2F8h+var_1C8]; this
0x14003e446  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003e44b  test    eax, eax
0x14003e44d  jz      short loc_14003E4A2
0x14003e44f  mov     [rsp+2F8h+var_2B8], rdi
0x14003e454  mov     [rsp+2F8h+var_2C0], ebx
0x14003e458  lea     rax, aEnter; "ENTER"
0x14003e45f  mov     [rsp+2F8h+var_2C8], rax
0x14003e464  mov     rax, [rsp+2F8h+var_1A0]
0x14003e46c  mov     [rsp+2F8h+var_2D0], rax
0x14003e471  mov     eax, [rsp+2F8h+var_1A4]
0x14003e478  mov     dword ptr [rsp+2F8h+var_2D8], eax
0x14003e47c  mov     r9d, [rsp+2F8h+var_198]
0x14003e484  mov     r8d, [rsp+2F8h+var_1A8]
0x14003e48c  mov     rdx, [rsp+2F8h+var_1B0]
0x14003e494  mov     rcx, [rsp+2F8h+var_1B8]
0x14003e49c  call    cs:__imp_VssTraceMessage
0x14003e4a2  lea     rcx, [rsp+2F8h+var_278]; this
0x14003e4aa  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003e4af  nop
0x14003e4b0  mov     [rsp+2F8h+arg_18], rdi
0x14003e4b8  mov     [rsp+2F8h+var_138], rdi
0x14003e4c0  xorps   xmm0, xmm0
0x14003e4c3  xor     eax, eax
0x14003e4c5  movups  xmmword ptr [rsp+2F8h+pv], xmm0
0x14003e4cd  movups  xmmword ptr [rsp+2F8h+var_120], xmm0
0x14003e4d5  movups  xmmword ptr [rsp+2F8h+var_110], xmm0
0x14003e4dd  mov     [rsp+2F8h+var_100], rax
0x14003e4e5  mov     [rsp+2F8h+arg_8], edi
0x14003e4ec  mov     [rsp+2F8h+arg_10], edi
0x14003e4f3  mov     [r15], edi
0x14003e4f6  mov     rax, [r14]
0x14003e4f9  mov     [rsp+2F8h+var_2A0], edi
0x14003e4fd  mov     byte ptr [rsp+2F8h+var_2A8], dil
0x14003e502  mov     byte ptr [rsp+2F8h+var_2B0], dil
0x14003e507  mov     byte ptr [rsp+2F8h+var_2B8], dil
0x14003e50c  mov     byte ptr [rsp+2F8h+var_2C0], dil
0x14003e511  mov     dword ptr [rsp+2F8h+var_2C8], edi
0x14003e515  mov     [rsp+2F8h+var_2D0], rdi
0x14003e51a  lea     r8, aAsr; "ASR"
0x14003e521  mov     [rsp+2F8h+var_2D8], r8
0x14003e526  mov     r9, r8
0x14003e529  mov     edx, 2
0x14003e52e  mov     rcx, r14
0x14003e531  mov     rax, [rax+10h]
0x14003e535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e53a  mov     ebx, eax
0x14003e53c  mov     [rsp+2F8h+var_1C0], eax
0x14003e543  lea     rax, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x14003e54a  mov     [rsp+2F8h+var_278], rax
0x14003e552  mov     [rsp+2F8h+var_270], rsi
0x14003e55a  lea     rax, aWrtasrwc; "WRTASRWC"
0x14003e561  mov     [rsp+2F8h+var_268], rax
0x14003e569  mov     [rsp+2F8h+var_260], 0CDh
0x14003e574  mov     [rsp+2F8h+var_25C], 4
0x14003e57f  mov     [rsp+2F8h+var_258], r12d
0x14003e587  mov     [rsp+2F8h+var_1D8], 1000000h
0x14003e592  xor     edx, edx; Val
0x14003e594  lea     r8d, [rdx+78h]; Size
0x14003e598  lea     rcx, [rsp+2F8h+var_250]; void *
0x14003e5a0  call    memset_0
0x14003e5a5  lea     rax, [rsp+2F8h+var_278]
0x14003e5ad  mov     [rsp+2F8h+var_280], rax
0x14003e5b2  test    ebx, ebx
0x14003e5b4  jns     short loc_14003E60A
0x14003e5b6  mov     eax, 8000FFFFh
0x14003e5bb  cmp     ebx, eax
0x14003e5bd  jnz     short loc_14003E5DA
0x14003e5bf  mov     [rsp+2F8h+pExceptionObject], eax
0x14003e5c6  lea     rdx, _TI1J; pThrowInfo
0x14003e5cd  lea     rcx, [rsp+2F8h+pExceptionObject]; pExceptionObject
0x14003e5d5  call    _CxxThrowException_0
0x14003e5da  lea     rdx, [rsp+2F8h+var_278]; struct CVssDebugInfo *
0x14003e5e2  lea     rcx, [rsp+2F8h+var_E0]; this
0x14003e5ea  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003e5ef  lea     r9, aIvsscreatewrit_3; "IVssCreateWriterMetadata::AddComponent"
0x14003e5f6  mov     r8d, ebx
0x14003e5f9  mov     rdx, rax
0x14003e5fc  lea     rcx, [rsp+2F8h+var_1C8]
0x14003e604  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003e60a  lea     rcx, [rsp+2F8h+var_278]; this
0x14003e612  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003e617  mov     rcx, [r13+10h]
0x14003e61b  mov     rax, [rcx]
0x14003e61e  lea     r8, [rsp+2F8h+arg_18]
0x14003e626  lea     rdx, [rsp+2F8h+arg_8]
0x14003e62e  mov     rax, [rax+20h]
0x14003e632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e637  mov     ebx, eax
0x14003e639  mov     [rsp+2F8h+var_1C0], eax
0x14003e640  mov     [r15], eax
0x14003e643  lea     rax, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x14003e64a  mov     [rsp+2F8h+var_278], rax
0x14003e652  mov     [rsp+2F8h+var_270], rsi
0x14003e65a  lea     rax, aWrtasrwc; "WRTASRWC"
0x14003e661  mov     [rsp+2F8h+var_268], rax
0x14003e669  mov     [rsp+2F8h+var_260], 0D5h
0x14003e674  mov     [rsp+2F8h+var_25C], 4
0x14003e67f  mov     [rsp+2F8h+var_258], r12d
0x14003e687  mov     [rsp+2F8h+var_1D8], 1000000h
0x14003e692  xor     edx, edx; Val
0x14003e694  lea     r8d, [rdx+78h]; Size
0x14003e698  lea     rcx, [rsp+2F8h+var_250]; void *
0x14003e6a0  call    memset_0
0x14003e6a5  lea     rax, [rsp+2F8h+var_278]
0x14003e6ad  mov     [rsp+2F8h+var_288], rax
0x14003e6b2  test    ebx, ebx
0x14003e6b4  jns     short loc_14003E70A
0x14003e6b6  mov     eax, 8000FFFFh
0x14003e6bb  cmp     ebx, eax
0x14003e6bd  jnz     short loc_14003E6DA
0x14003e6bf  mov     [rsp+2F8h+var_154], eax
0x14003e6c6  lea     rdx, _TI1J; pThrowInfo
0x14003e6cd  lea     rcx, [rsp+2F8h+var_154]; pExceptionObject
0x14003e6d5  call    _CxxThrowException_0
0x14003e6da  lea     rdx, [rsp+2F8h+var_278]; struct CVssDebugInfo *
0x14003e6e2  lea     rcx, [rsp+2F8h+var_E0]; this
0x14003e6ea  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003e6ef  lea     r9, aIvssasrwriterb_1; "IVssAsrWriterBackup::GetVolumeComponent"...
0x14003e6f6  mov     r8d, ebx
0x14003e6f9  mov     rdx, rax
0x14003e6fc  lea     rcx, [rsp+2F8h+var_1C8]
0x14003e704  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003e70a  lea     rcx, [rsp+2F8h+var_278]; this
0x14003e712  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003e717  mov     ebx, edi
0x14003e719  cmp     ebx, [rsp+2F8h+arg_8]
0x14003e720  jnb     loc_14003E819
0x14003e726  mov     eax, ebx
0x14003e728  imul    r8, rax, 38h ; '8'
0x14003e72c  mov     r9, [rsp+2F8h+arg_18]
0x14003e734  mov     rax, [r14]
0x14003e737  cmp     [r8+r9+24h], edi
0x14003e73c  setnz   dl
0x14003e73f  cmp     [r8+r9+20h], edi
0x14003e744  setnz   cl
0x14003e747  mov     [rsp+2F8h+var_2A0], edi
0x14003e74b  mov     byte ptr [rsp+2F8h+var_2A8], dl
0x14003e74f  mov     byte ptr [rsp+2F8h+var_2B0], cl
0x14003e753  mov     byte ptr [rsp+2F8h+var_2B8], dil
0x14003e758  mov     byte ptr [rsp+2F8h+var_2C0], dil
0x14003e75d  mov     dword ptr [rsp+2F8h+var_2C8], edi
0x14003e761  mov     [rsp+2F8h+var_2D0], rdi
0x14003e766  mov     rcx, [r8+r9+10h]
0x14003e76b  mov     [rsp+2F8h+var_2D8], rcx
0x14003e770  mov     r9, [r8+r9+8]
0x14003e775  lea     r8, aVolumes; "Volumes"
0x14003e77c  mov     edx, 2
0x14003e781  mov     rcx, r14
0x14003e784  mov     rax, [rax+10h]
0x14003e788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e78d  mov     [rsp+2F8h+var_1C0], eax
0x14003e794  lea     rax, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x14003e79b  mov     [rsp+2F8h+var_278], rax
0x14003e7a3  mov     [rsp+2F8h+var_270], rsi
0x14003e7ab  lea     rax, aWrtasrwc; "WRTASRWC"
0x14003e7b2  mov     [rsp+2F8h+var_268], rax
0x14003e7ba  mov     [rsp+2F8h+var_260], 0E5h
0x14003e7c5  mov     [rsp+2F8h+var_25C], 4
0x14003e7d0  mov     [rsp+2F8h+var_258], r12d
0x14003e7d8  mov     [rsp+2F8h+var_1D8], 1000000h
0x14003e7e3  xor     edx, edx; Val
0x14003e7e5  lea     r8d, [rdx+78h]; Size
0x14003e7e9  lea     rcx, [rsp+2F8h+var_250]; void *
0x14003e7f1  call    memset_0
0x14003e7f6  lea     r8, aIvsscreatewrit; "IVssCreateWriterMetadata::AddComponent "...
0x14003e7fd  lea     rdx, [rsp+2F8h+var_278]
0x14003e805  lea     rcx, [rsp+2F8h+var_1C8]
0x14003e80d  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14003e812  inc     ebx
0x14003e814  jmp     loc_14003E719
0x14003e819  mov     rcx, [r13+10h]
0x14003e81d  mov     rax, [rcx]
0x14003e820  lea     r8, [rsp+2F8h+var_138]
0x14003e828  lea     rdx, [rsp+2F8h+arg_10]
0x14003e830  mov     rax, [rax+28h]
0x14003e834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e839  mov     ebx, eax
0x14003e83b  mov     [rsp+2F8h+var_1C0], eax
0x14003e842  mov     [r15], eax
0x14003e845  lea     rax, aBaseStorVssMod_7; "base\\stor\\vss\\modules\\writers\\asrw"...
0x14003e84c  mov     [rsp+2F8h+var_278], rax
0x14003e854  mov     [rsp+2F8h+var_270], rsi
0x14003e85c  lea     rax, aWrtasrwc; "WRTASRWC"
0x14003e863  mov     [rsp+2F8h+var_268], rax
0x14003e86b  mov     [rsp+2F8h+var_260], 0EEh
0x14003e876  mov     [rsp+2F8h+var_25C], 4
0x14003e881  mov     [rsp+2F8h+var_258], r12d
0x14003e889  mov     [rsp+2F8h+var_1D8], 1000000h
0x14003e894  xor     edx, edx; Val
0x14003e896  lea     r8d, [rdx+78h]; Size
0x14003e89a  lea     rcx, [rsp+2F8h+var_250]; void *
0x14003e8a2  call    memset_0
0x14003e8a7  lea     rax, [rsp+2F8h+var_278]
0x14003e8af  mov     [rsp+2F8h+var_288], rax
0x14003e8b4  test    ebx, ebx
0x14003e8b6  jns     short loc_14003E90C
0x14003e8b8  mov     eax, 8000FFFFh
0x14003e8bd  cmp     ebx, eax
0x14003e8bf  jnz     short loc_14003E8DC
0x14003e8c1  mov     [rsp+2F8h+var_150], eax
0x14003e8c8  lea     rdx, _TI1J; pThrowInfo
0x14003e8cf  lea     rcx, [rsp+2F8h+var_150]; pExceptionObject
0x14003e8d7  call    _CxxThrowException_0
0x14003e8dc  lea     rdx, [rsp+2F8h+var_278]; struct CVssDebugInfo *
0x14003e8e4  lea     rcx, [rsp+2F8h+var_E0]; this
0x14003e8ec  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x14003e8f1  lea     r9, aIvssasrwriterb; "IVssAsrWriterBackup::GetDiskComponents"
0x14003e8f8  mov     r8d, ebx
0x14003e8fb  mov     rdx, rax
0x14003e8fe  lea     rcx, [rsp+2F8h+var_1C8]
0x14003e906  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14003e90c  lea     rcx, [rsp+2F8h+var_278]; this
0x14003e914  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14003e919  mov     esi, edi
0x14003e91b  cmp     esi, [rsp+2F8h+arg_10]
0x14003e922  jnb     loc_14003EA6C
0x14003e928  mov     eax, esi
0x14003e92a  imul    rdx, rax, 38h ; '8'
0x14003e92e  mov     r9, [rsp+2F8h+var_138]
0x14003e936  mov     rax, [r14]
0x14003e939  mov     [rsp+2F8h+var_2A0], edi
0x14003e93d  mov     byte ptr [rsp+2F8h+var_2A8], 1
0x14003e942  mov     byte ptr [rsp+2F8h+var_2B0], 1
0x14003e947  mov     byte ptr [rsp+2F8h+var_2B8], dil
0x14003e94c  mov     byte ptr [rsp+2F8h+var_2C0], dil
0x14003e951  mov     dword ptr [rsp+2F8h+var_2C8], edi
0x14003e955  mov     [rsp+2F8h+var_2D0], rdi
0x14003e95a  mov     rcx, [rdx+r9+10h]
  ... truncated ...
```
