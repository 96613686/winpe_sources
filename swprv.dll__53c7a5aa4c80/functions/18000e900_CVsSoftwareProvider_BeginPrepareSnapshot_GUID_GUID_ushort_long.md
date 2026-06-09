# CVsSoftwareProvider::BeginPrepareSnapshot(_GUID,_GUID,ushort *,long)

- ea: `0x18000e900`
- end: `0x18000f8d9`
- name: `?BeginPrepareSnapshot@CVsSoftwareProvider@@UEAAJU_GUID@@0PEAGJ@Z`
- size: `4057`
- prototype: `__int64 __fastcall(CVsSoftwareProvider *this, struct _GUID *, struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001acc`
- `0x18000212c`
- `0x180002138`
- `0x1800034cc`
- `0x1800036c4`
- `0x180003718`
- `0x180003888`
- `0x1800049e0`
- `0x18000dd84`
- `0x18000e900`
- `0x1800108d4`
- `0x180010974`
- `0x180011178`
- `0x18001514c`
- `0x1800164a8`
- `0x180018544`
- `0x180018e2c`
- `0x180033a8c`
- `0x180033c78`
- `0x180034278`
- `0x180034324`
- `0x180034a4c`
- `0x18003649c`
- `0x1800367b8`
- `0x18003750c`
- `0x18003b348`
- `0x18003d78c`
- `0x1800419fc`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f450`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000f2ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000f43b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000f2ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000f43b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f3f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f3f6`

## string_xrefs

- `0x18000f397`: `GetComputerNameEx(%d, NULL, [%lu]) [%ld]`
- `0x18000f4e2`: `GetComputerNameEx(%d, %p, %lu)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVsSoftwareProvider::BeginPrepareSnapshot(
        CVsSoftwareProvider *this,
        struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  bool v9; // dl
  unsigned int v10; // ecx
  bool v11; // al
  int v12; // esi
  __int64 v13; // rax
  unsigned int v14; // ebx
  int ContextInternal; // eax
  BOOL ComputerName; // esi
  signed int LastError; // eax
  unsigned int v18; // ebx
  DWORD v19; // edi
  __int64 v20; // rbx
  WCHAR *v21; // rax
  unsigned __int16 *v22; // rdi
  DWORD v23; // esi
  signed int v24; // eax
  unsigned int v25; // ebx
  int v26; // eax
  CVssQueuedSnapshot *v27; // rdi
  char v28; // bl
  int v29; // eax
  CVssQueuedSnapshot *v30; // rbx
  unsigned int v31; // ebx
  bool v33[8]; // [rsp+20h] [rbp-288h]
  int v34; // [rsp+20h] [rbp-288h]
  unsigned __int16 *v35; // [rsp+28h] [rbp-280h]
  unsigned __int16 *v36; // [rsp+28h] [rbp-280h]
  unsigned __int16 *v37; // [rsp+30h] [rbp-278h]
  unsigned __int16 *v38; // [rsp+30h] [rbp-278h]
  unsigned __int16 *v39; // [rsp+38h] [rbp-270h]
  unsigned __int16 *v40; // [rsp+38h] [rbp-270h]
  unsigned __int16 *v41; // [rsp+40h] [rbp-268h]
  unsigned __int16 *v42; // [rsp+48h] [rbp-260h]
  unsigned __int16 *v43; // [rsp+50h] [rbp-258h]
  __int64 v44; // [rsp+68h] [rbp-240h]
  DWORD nSize; // [rsp+D0h] [rbp-1D8h] BYREF
  const unsigned __int16 *v46; // [rsp+D8h] [rbp-1D0h] BYREF
  const unsigned __int16 *v47; // [rsp+E0h] [rbp-1C8h]
  const unsigned __int16 *v48; // [rsp+E8h] [rbp-1C0h]
  int v49; // [rsp+F0h] [rbp-1B8h]
  int v50; // [rsp+F4h] [rbp-1B4h]
  int v51; // [rsp+F8h] [rbp-1B0h]
  _BYTE v52[120]; // [rsp+100h] [rbp-1A8h] BYREF
  int v53; // [rsp+178h] [rbp-130h]
  struct _GUID v54; // [rsp+180h] [rbp-128h] BYREF
  LPVOID v55; // [rsp+190h] [rbp-118h] BYREF
  int pExceptionObject; // [rsp+198h] [rbp-110h] BYREF
  struct _GUID v57; // [rsp+1A0h] [rbp-108h] BYREF
  __int128 v58; // [rsp+1B0h] [rbp-F8h] BYREF
  LPVOID v59; // [rsp+1C0h] [rbp-E8h] BYREF
  unsigned int v60; // [rsp+1C8h] [rbp-E0h]
  unsigned int v61; // [rsp+1E4h] [rbp-C4h]
  int v62; // [rsp+230h] [rbp-78h] BYREF
  struct _GUID v63; // [rsp+240h] [rbp-68h] BYREF
  _com_error *v64; // [rsp+250h] [rbp-58h] BYREF
  const std::exception *v65; // [rsp+258h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v66[9]; // [rsp+260h] [rbp-48h] BYREF

  v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
  v48 = L"SPRPROVC";
  v49 = 285;
  v50 = 2;
  v51 = 255;
  v53 = 0x1000000;
  memset_0(v52, 0, sizeof(v52));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v59, (__int64)&v46, 0);
  try
  {
    v11 = IsInGroup(v10, v9);
    v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v50 = 2;
    v51 = 255;
    v53 = 0x1000000;
    v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
    v48 = L"SPRPROVC";
    if ( !v11 )
    {
      v49 = 291;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(
        &v59,
        &v46,
        2147942405LL,
        L"The client process is not running under an administrator account");
    }
    v49 = 294;
    memset_0(v52, 0, sizeof(v52));
    v12 = a3->Data4[6];
    CVssFunctionTracer::Trace(
      &v59,
      &v46,
      L"Parameters: \n"
       "  SnapshotId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
       "  SnapshotSetId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
       "  VolumeName = %s",
      a3->Data1,
      a3->Data2,
      a3->Data3,
      a3->Data4[0],
      a3->Data4[1],
      a3->Data4[2],
      a3->Data4[3],
      a3->Data4[4],
      a3->Data4[5],
      v12,
      a3->Data4[7],
      a2->Data1,
      a2->Data2,
      a2->Data3,
      a2->Data4[0],
      a2->Data4[1],
      a2->Data4[2],
      a2->Data4[3],
      a2->Data4[4],
      a2->Data4[5],
      a2->Data4[6],
      a2->Data4[7],
      a4);
    if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 304;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147942487LL, L"SnapshotSetId == GUID_NULL");
    }
    if ( !a4 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 306;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147942487LL, L"pwszVolumeName is NULL");
    }
    if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 308;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147942487LL, L"Snapshot ID is NULL");
    }
    v13 = *((_QWORD *)this + 11) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v13 )
      v13 = *((_QWORD *)this + 12) - *(_QWORD *)GUID_NULL.Data4;
    if ( !v13 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 311;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147942414LL, L"The Provider instance ID could not be generated");
    }
    v14 = a5;
    if ( (a5 & 0x20000) != 0 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 318;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Trace(&v59, &v46, L"Removing DIFFERENTIAL attribute from internal snapshot context\n");
      v14 = a5 & 0xFFFDFFFF;
    }
    if ( (v14 & 2) != 0 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 324;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Trace(
        &v59,
        &v46,
        L"Removing VSS_VOLSNAP_ATTR_NO_AUTORECOVERY attribute from internal snapshot context\n");
      v14 &= ~2u;
    }
    if ( (v14 & 0x2000000) != 0 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 330;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Trace(
        &v59,
        &v46,
        L"Removing VSS_VOLSNAP_ATTR_TXF_RECOVERY attribute from internal snapshot context\n");
      v14 &= ~0x2000000u;
    }
    if ( ((v14 ^ (unsigned int)CVsSoftwareProvider::GetContextInternal(this)) & 0xFF3FFFFF) != 0 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 337;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147754779LL, L"Can't change arbitrary context in BeginPrepareSnapshot");
    }
    CVssAutomaticLock2::CVssAutomaticLock2(
      (CVssAutomaticLock2 *)v66,
      (struct CVssCriticalSection *)CVsSoftwareProvider::m_cs);
    v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
    v48 = L"SPRPROVC";
    v49 = 341;
    v50 = 2;
    v51 = 255;
    v53 = 0x1000000;
    memset_0(v52, 0, sizeof(v52));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v59, (const struct CVssDebugInfo *)&v46, 405);
    v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
    v48 = L"SPRPROVC";
    v49 = 342;
    v50 = 2;
    v51 = 255;
    v53 = 0x1000000;
    memset_0(v52, 0, sizeof(v52));
    CVssFunctionTracer::AddContext((__int64)&v59, (const struct CVssDebugInfo *)&v46);
    v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
    v48 = L"SPRPROVC";
    v49 = 343;
    v50 = 2;
    v51 = 255;
    v53 = 0x1000000;
    memset_0(v52, 0, sizeof(v52));
    CVssFunctionTracer::AddContext((__int64)&v59, (const struct CVssDebugInfo *)&v46);
    v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
    v48 = L"SPRPROVC";
    v49 = 344;
    v50 = 2;
    v51 = 255;
    v53 = 0x1000000;
    memset_0(v52, 0, sizeof(v52));
    LODWORD(v44) = v12;
    LODWORD(v43) = a3->Data4[3];
    LODWORD(v42) = a3->Data4[2];
    LODWORD(v41) = a3->Data4[1];
    LODWORD(v39) = a3->Data4[0];
    LODWORD(v37) = a3->Data3;
    LODWORD(v35) = a3->Data2;
    *(_DWORD *)v33 = a3->Data1;
    CVssFunctionTracer::AddContextEx(
      &v59,
      &v46,
      5014,
      L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      *(_QWORD *)v33,
      v35,
      v37,
      v39,
      v41);
    v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
    v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
    v48 = L"SPRPROVC";
    v49 = 346;
    v50 = 2;
    v51 = 255;
    v53 = 0x1000000;
    memset_0(v52, 0, sizeof(v52));
    CVssFunctionTracer::AddOperation((struct CVssFunctionTracer *)&v59, (const struct CVssDebugInfo *)&v46, 5013, v14);
    ContextInternal = CVsSoftwareProvider::GetContextInternal(this);
    if ( (CVsSoftwareProvider::GetVolumeInformationFlags((_DWORD)a4, ContextInternal, 0, 1, 31) & 1) == 0 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 354;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147754766LL, L"Volume not supported");
    }
    CVsSoftwareProvider::FreezeContext(this);
    if ( v14 != (unsigned int)CVsSoftwareProvider::GetContextInternal(this) )
      CVsSoftwareProvider::SetContextInternal(this, v14);
    v58 = (__int128)*a2;
    v57 = *(struct _GUID *)((char *)this + 88);
    CVsSoftwareProvider::RemoveSnapshotsFromGlobalList(&v57, &v58, 3);
    nSize = 0;
    ComputerName = GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize);
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError != 234 )
    {
      v19 = nSize;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 393;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      LODWORD(v40) = ComputerName;
      LODWORD(v38) = v19;
      LODWORD(v36) = 3;
      CVssFunctionTracer::TranslateInternalProviderError(
        &v59,
        &v46,
        v18,
        2147754758LL,
        L"GetComputerNameEx(%d, NULL, [%lu]) [%ld]",
        v36,
        v38,
        v40);
    }
    *((_QWORD *)&v58 + 1) = 0;
    *(_QWORD *)&v58 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
    v20 = nSize;
    CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&v58);
    v21 = (WCHAR *)CoTaskMemAlloc(2 * v20 + 2);
    v22 = v21;
    *((_QWORD *)&v58 + 1) = v21;
    if ( !v21 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v21, &nSize) )
    {
      v23 = nSize;
      v24 = GetLastError();
      v25 = v24;
      if ( v24 > 0 )
        v25 = (unsigned __int16)v24 | 0x80070000;
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 406;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      LODWORD(v40) = v23;
      LODWORD(v36) = 3;
      CVssFunctionTracer::TranslateInternalProviderError(
        &v59,
        &v46,
        v25,
        2147754758LL,
        L"GetComputerNameEx(%d, %p, %lu)",
        v36,
        v22,
        v40);
    }
    v55 = 0;
    v26 = CVsSoftwareProvider::GetContextInternal(this);
    v57 = (struct _GUID)xmmword_180053F90;
    v54 = *a2;
    v63 = *a3;
    VSS_OBJECT_PROP_Ptr::InitializeAsSnapshot(
      (VSS_OBJECT_PROP_Ptr *)&v55,
      (struct CVssFunctionTracer *)&v59,
      &v63,
      &v54,
      v34,
      0,
      a4,
      v22,
      v22,
      v42,
      v43,
      &v57,
      v26 | 0x20000,
      v44,
      VSS_SS_PREPARING);
    v27 = (CVssQueuedSnapshot *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)&v54.Data1 = v27;
    if ( v27 )
    {
      v28 = *((_BYTE *)this + 109);
      v29 = CVsSoftwareProvider::GetContextInternal(this);
      v63 = *(struct _GUID *)((char *)this + 88);
      v30 = CVssQueuedSnapshot::CVssQueuedSnapshot(v27, (struct VSS_OBJECT_PROP_Ptr *)&v55, &v63, v29, v28);
    }
    else
    {
      v30 = 0;
    }
    *(_QWORD *)&v54.Data1 = v30;
    if ( !v30 )
    {
      v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
      v47 = L"CVsSoftwareProvider::BeginPrepareSnapshot";
      v48 = L"SPRPROVC";
      v49 = 440;
      v50 = 2;
      v51 = 255;
      v53 = 0x1000000;
      memset_0(v52, 0, sizeof(v52));
      CVssFunctionTracer::Throw(&v59, &v46, 2147942414LL, L"Memory allocation error");
    }
    (*(void (__fastcall **)(CVssQueuedSnapshot *))(*(_QWORD *)v30 + 8LL))(v30);
    v55 = 0;
    CVssQueuedSnapshot::AttachToGlobalList(v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v54);
    VSS_OBJECT_PROP_Ptr::~VSS_OBJECT_PROP_Ptr(&v55);
    CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v58);
    CVssAutomaticLock2::~CVssAutomaticLock2(v66);
  }
  catch ( long v62 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v59,
      v62,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::BeginPrepareSnapshot",
      0x1C4u,
      v61);
  }
  catch ( _com_error *v64 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v59,
      v64,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::BeginPrepareSnapshot",
      0x1C4u,
      v61);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v59,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::BeginPrepareSnapshot",
      0x1C4u,
      v61);
  }
  catch ( const std::exception *v65 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v59,
      v65,
      L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx",
      L"SPRPROVC",
      L"CVsSoftwareProvider::BeginPrepareSnapshot",
      0x1C4u,
      v61);
  }
  v11 = IsInGroup(v10, v9);
  v46 = L"base\\stor\\vss\\modules\\softprv\\src\\provider.cxx";
  v50 = 2;
}

```

## disassembly

```asm
0x18000e900  mov     r11, rsp
0x18000e903  push    rbx
0x18000e904  push    rsi
0x18000e905  push    rdi
0x18000e906  push    r12
0x18000e908  push    r13
0x18000e90a  push    r14
0x18000e90c  push    r15
0x18000e90e  sub     rsp, 270h
0x18000e915  mov     r15, r9
0x18000e918  mov     r13, r8
0x18000e91b  mov     r12, rdx
0x18000e91e  mov     r14, rcx
0x18000e921  lea     rsi, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000e928  mov     [r11-1D0h], rsi
0x18000e92f  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000e936  mov     [r11-1C8h], rax
0x18000e93d  lea     rax, aSprprovc; "SPRPROVC"
0x18000e944  mov     [r11-1C0h], rax
0x18000e94b  mov     [rsp+2A8h+var_1B8], 11Dh
0x18000e956  mov     edi, 2
0x18000e95b  mov     [rsp+2A8h+var_1B4], edi
0x18000e962  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000e96d  mov     [rsp+2A8h+var_130], 1000000h
0x18000e978  xor     edx, edx; Val
0x18000e97a  lea     r8d, [rdi+76h]; Size
0x18000e97e  lea     rcx, [r11-1A8h]; void *
0x18000e985  call    memset_0
0x18000e98a  xor     r8d, r8d
0x18000e98d  lea     rdx, [rsp+2A8h+var_1D0]
0x18000e995  lea     rcx, [rsp+2A8h+var_E8]
0x18000e99d  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000e9a2  nop
0x18000e9a3  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x18000e9a8  mov     [rsp+2A8h+var_1D0], rsi
0x18000e9b0  mov     [rsp+2A8h+var_1B4], edi
0x18000e9b7  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000e9c2  mov     [rsp+2A8h+var_130], 1000000h
0x18000e9cd  xor     edx, edx; Val
0x18000e9cf  lea     r8d, [rdi+76h]; Size
0x18000e9d3  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000e9db  test    al, al
0x18000e9dd  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000e9e4  mov     [rsp+2A8h+var_1C8], rax
0x18000e9ec  lea     rax, aSprprovc; "SPRPROVC"
0x18000e9f3  mov     [rsp+2A8h+var_1C0], rax
0x18000e9fb  jnz     short loc_18000EA2F
0x18000e9fd  mov     [rsp+2A8h+var_1B8], 123h
0x18000ea08  call    memset_0
0x18000ea0d  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x18000ea14  mov     r8d, 80070005h
0x18000ea1a  lea     rdx, [rsp+2A8h+var_1D0]
0x18000ea22  lea     rcx, [rsp+2A8h+var_E8]
0x18000ea2a  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000ea2f  mov     [rsp+2A8h+var_1B8], 126h
0x18000ea3a  call    memset_0
0x18000ea3f  movzx   eax, byte ptr [r12+0Fh]
0x18000ea45  movzx   ecx, byte ptr [r12+0Eh]
0x18000ea4b  movzx   edx, byte ptr [r12+0Dh]
0x18000ea51  movzx   r8d, byte ptr [r12+0Ch]
0x18000ea57  movzx   r9d, byte ptr [r12+0Bh]
0x18000ea5d  movzx   r10d, byte ptr [r12+0Ah]
0x18000ea63  movzx   r11d, byte ptr [r12+9]
0x18000ea69  movzx   ebx, byte ptr [r12+8]
0x18000ea6f  movzx   edi, word ptr [r12+6]
0x18000ea75  movzx   esi, word ptr [r12+4]
0x18000ea7b  mov     [rsp+2A8h+var_1E0], r15
0x18000ea83  mov     [rsp+2A8h+var_1E8], eax
0x18000ea8a  mov     [rsp+2A8h+var_1F0], ecx
0x18000ea91  mov     [rsp+2A8h+var_1F8], edx
0x18000ea98  mov     [rsp+2A8h+var_200], r8d
0x18000eaa0  mov     [rsp+2A8h+var_208], r9d
0x18000eaa8  mov     [rsp+2A8h+var_210], r10d
0x18000eab0  mov     [rsp+2A8h+var_218], r11d
0x18000eab8  mov     [rsp+2A8h+var_220], ebx
0x18000eabf  mov     [rsp+2A8h+var_228], edi
0x18000eac6  mov     [rsp+2A8h+var_230], esi
0x18000eaca  mov     eax, [r12]
0x18000eace  mov     [rsp+2A8h+var_238], eax
0x18000ead2  movzx   edi, byte ptr [r13+0Fh]
0x18000ead7  mov     dword ptr [rsp+2A8h+var_240], edi
0x18000eadb  movzx   esi, byte ptr [r13+0Eh]
0x18000eae0  mov     [rsp+2A8h+var_248], esi
0x18000eae4  movzx   eax, byte ptr [r13+0Dh]
0x18000eae9  mov     dword ptr [rsp+2A8h+var_250], eax
0x18000eaed  movzx   eax, byte ptr [r13+0Ch]
0x18000eaf2  mov     dword ptr [rsp+2A8h+var_258], eax
0x18000eaf6  movzx   eax, byte ptr [r13+0Bh]
0x18000eafb  mov     dword ptr [rsp+2A8h+var_260], eax
0x18000eaff  movzx   eax, byte ptr [r13+0Ah]
0x18000eb04  mov     dword ptr [rsp+2A8h+var_268], eax
0x18000eb08  movzx   eax, byte ptr [r13+9]
0x18000eb0d  mov     dword ptr [rsp+2A8h+var_270], eax
0x18000eb11  movzx   eax, byte ptr [r13+8]
0x18000eb16  mov     dword ptr [rsp+2A8h+var_278], eax
0x18000eb1a  movzx   eax, word ptr [r13+6]
0x18000eb1f  mov     dword ptr [rsp+2A8h+var_280], eax
0x18000eb23  movzx   eax, word ptr [r13+4]
0x18000eb28  mov     dword ptr [rsp+2A8h+var_288], eax
0x18000eb2c  mov     r9d, [r13+0]
0x18000eb30  lea     r8, aParametersSnap_1; "Parameters: \n  SnapshotId = {%.8x-%.4x"...
0x18000eb37  lea     rdx, [rsp+2A8h+var_1D0]
0x18000eb3f  lea     rcx, [rsp+2A8h+var_E8]
0x18000eb47  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000eb4c  mov     r8d, 10h; Size
0x18000eb52  lea     rdx, GUID_NULL; Buf2
0x18000eb59  mov     rcx, r12; Buf1
0x18000eb5c  call    memcmp_0
0x18000eb61  test    eax, eax
0x18000eb63  jz      loc_18000F81B
0x18000eb69  test    r15, r15
0x18000eb6c  jnz     loc_18000EC00
0x18000eb72  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000eb79  mov     [rsp+2A8h+var_1D0], rax
0x18000eb81  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000eb88  mov     [rsp+2A8h+var_1C8], rax
0x18000eb90  lea     rax, aSprprovc; "SPRPROVC"
0x18000eb97  mov     [rsp+2A8h+var_1C0], rax
0x18000eb9f  mov     [rsp+2A8h+var_1B8], 132h
0x18000ebaa  mov     [rsp+2A8h+var_1B4], 2
0x18000ebb5  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000ebc0  mov     [rsp+2A8h+var_130], 1000000h
0x18000ebcb  xor     edx, edx; Val
0x18000ebcd  lea     r8d, [r15+78h]; Size
0x18000ebd1  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000ebd9  call    memset_0
0x18000ebde  lea     r9, aPwszvolumename; "pwszVolumeName is NULL"
0x18000ebe5  mov     r8d, 80070057h
0x18000ebeb  lea     rdx, [rsp+2A8h+var_1D0]
0x18000ebf3  lea     rcx, [rsp+2A8h+var_E8]
0x18000ebfb  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000ec00  mov     r8d, 10h; Size
0x18000ec06  lea     rdx, GUID_NULL; Buf2
0x18000ec0d  mov     rcx, r13; Buf1
0x18000ec10  call    memcmp_0
0x18000ec15  test    eax, eax
0x18000ec17  jz      loc_18000F78D
0x18000ec1d  mov     rax, [r14+58h]
0x18000ec21  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18000ec28  jnz     short loc_18000EC35
0x18000ec2a  mov     rax, [r14+60h]
0x18000ec2e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18000ec35  test    rax, rax
0x18000ec38  jz      loc_18000F6FF
0x18000ec3e  mov     ebx, [rsp+2A8h+arg_20]
0x18000ec45  bt      ebx, 11h
0x18000ec49  jnb     loc_18000ECDB
0x18000ec4f  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000ec56  mov     [rsp+2A8h+var_1D0], rax
0x18000ec5e  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000ec65  mov     [rsp+2A8h+var_1C8], rax
0x18000ec6d  lea     rax, aSprprovc; "SPRPROVC"
0x18000ec74  mov     [rsp+2A8h+var_1C0], rax
0x18000ec7c  mov     [rsp+2A8h+var_1B8], 13Eh
0x18000ec87  mov     [rsp+2A8h+var_1B4], 2
0x18000ec92  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000ec9d  mov     [rsp+2A8h+var_130], 1000000h
0x18000eca8  xor     edx, edx; Val
0x18000ecaa  lea     r8d, [rdx+78h]; Size
0x18000ecae  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000ecb6  call    memset_0
0x18000ecbb  lea     r8, aRemovingDiffer; "Removing DIFFERENTIAL attribute from in"...
0x18000ecc2  lea     rdx, [rsp+2A8h+var_1D0]
0x18000ecca  lea     rcx, [rsp+2A8h+var_E8]
0x18000ecd2  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000ecd7  btr     ebx, 11h
0x18000ecdb  test    bl, 2
0x18000ecde  jz      loc_18000ED6F
0x18000ece4  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000eceb  mov     [rsp+2A8h+var_1D0], rax
0x18000ecf3  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000ecfa  mov     [rsp+2A8h+var_1C8], rax
0x18000ed02  lea     rax, aSprprovc; "SPRPROVC"
0x18000ed09  mov     [rsp+2A8h+var_1C0], rax
0x18000ed11  mov     [rsp+2A8h+var_1B8], 144h
0x18000ed1c  mov     [rsp+2A8h+var_1B4], 2
0x18000ed27  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000ed32  mov     [rsp+2A8h+var_130], 1000000h
0x18000ed3d  xor     edx, edx; Val
0x18000ed3f  lea     r8d, [rdx+78h]; Size
0x18000ed43  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000ed4b  call    memset_0
0x18000ed50  lea     r8, aRemovingVssVol_0; "Removing VSS_VOLSNAP_ATTR_NO_AUTORECOVE"...
0x18000ed57  lea     rdx, [rsp+2A8h+var_1D0]
0x18000ed5f  lea     rcx, [rsp+2A8h+var_E8]
0x18000ed67  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000ed6c  and     ebx, 0FFFFFFFDh
0x18000ed6f  bt      ebx, 19h
0x18000ed73  jnb     loc_18000EE05
0x18000ed79  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000ed80  mov     [rsp+2A8h+var_1D0], rax
0x18000ed88  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000ed8f  mov     [rsp+2A8h+var_1C8], rax
0x18000ed97  lea     rax, aSprprovc; "SPRPROVC"
0x18000ed9e  mov     [rsp+2A8h+var_1C0], rax
0x18000eda6  mov     [rsp+2A8h+var_1B8], 14Ah
0x18000edb1  mov     [rsp+2A8h+var_1B4], 2
0x18000edbc  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000edc7  mov     [rsp+2A8h+var_130], 1000000h
0x18000edd2  xor     edx, edx; Val
0x18000edd4  lea     r8d, [rdx+78h]; Size
0x18000edd8  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000ede0  call    memset_0
0x18000ede5  lea     r8, aRemovingVssVol; "Removing VSS_VOLSNAP_ATTR_TXF_RECOVERY "...
0x18000edec  lea     rdx, [rsp+2A8h+var_1D0]
0x18000edf4  lea     rcx, [rsp+2A8h+var_E8]
0x18000edfc  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000ee01  btr     ebx, 19h
0x18000ee05  mov     rcx, r14; this
0x18000ee08  call    ?GetContextInternal@CVsSoftwareProvider@@AEBAJXZ; CVsSoftwareProvider::GetContextInternal(void)
0x18000ee0d  xor     eax, ebx
0x18000ee0f  test    eax, 0FF3FFFFFh
0x18000ee14  jz      loc_18000EEA8
0x18000ee1a  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000ee21  mov     [rsp+2A8h+var_1D0], rax
0x18000ee29  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000ee30  mov     [rsp+2A8h+var_1C8], rax
0x18000ee38  lea     rax, aSprprovc; "SPRPROVC"
0x18000ee3f  mov     [rsp+2A8h+var_1C0], rax
0x18000ee47  mov     [rsp+2A8h+var_1B8], 151h
0x18000ee52  mov     [rsp+2A8h+var_1B4], 2
0x18000ee5d  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000ee68  mov     [rsp+2A8h+var_130], 1000000h
0x18000ee73  xor     edx, edx; Val
0x18000ee75  lea     r8d, [rdx+78h]; Size
0x18000ee79  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000ee81  call    memset_0
0x18000ee86  lea     r9, aCanTChangeArbi; "Can't change arbitrary context in Begin"...
0x18000ee8d  mov     r8d, 8004231Bh
0x18000ee93  lea     rdx, [rsp+2A8h+var_1D0]
0x18000ee9b  lea     rcx, [rsp+2A8h+var_E8]
0x18000eea3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18000eea8  lea     rdx, ?m_cs@CVsSoftwareProvider@@0VCVssCriticalSection@@A; struct CVssCriticalSection *
0x18000eeaf  lea     rcx, [rsp+2A8h+var_48]; this
0x18000eeb7  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x18000eebc  nop
0x18000eebd  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000eec4  mov     [rsp+2A8h+var_1D0], rax
0x18000eecc  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000eed3  mov     [rsp+2A8h+var_1C8], rax
0x18000eedb  lea     rax, aSprprovc; "SPRPROVC"
0x18000eee2  mov     [rsp+2A8h+var_1C0], rax
0x18000eeea  mov     [rsp+2A8h+var_1B8], 155h
0x18000eef5  mov     [rsp+2A8h+var_1B4], 2
0x18000ef00  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000ef0b  mov     [rsp+2A8h+var_130], 1000000h
0x18000ef16  xor     edx, edx; Val
0x18000ef18  lea     r8d, [rdx+78h]; Size
0x18000ef1c  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000ef24  call    memset_0
0x18000ef29  mov     r8d, 195h
0x18000ef2f  lea     rdx, [rsp+2A8h+var_1D0]
0x18000ef37  lea     rcx, [rsp+2A8h+var_E8]
0x18000ef3f  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x18000ef44  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000ef4b  mov     [rsp+2A8h+var_1D0], rax
0x18000ef53  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000ef5a  mov     [rsp+2A8h+var_1C8], rax
0x18000ef62  lea     rax, aSprprovc; "SPRPROVC"
0x18000ef69  mov     [rsp+2A8h+var_1C0], rax
0x18000ef71  mov     [rsp+2A8h+var_1B8], 156h
0x18000ef7c  mov     [rsp+2A8h+var_1B4], 2
0x18000ef87  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000ef92  mov     [rsp+2A8h+var_130], 1000000h
0x18000ef9d  xor     edx, edx; Val
0x18000ef9f  lea     r8d, [rdx+78h]; Size
0x18000efa3  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000efab  call    memset_0
0x18000efb0  lea     r9, aSystemProvider; "System Provider"
0x18000efb7  mov     r8d, 1394h
0x18000efbd  lea     rdx, [rsp+2A8h+var_1D0]
0x18000efc5  lea     rcx, [rsp+2A8h+var_E8]
0x18000efcd  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x18000efd2  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000efd9  mov     [rsp+2A8h+var_1D0], rax
0x18000efe1  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000efe8  mov     [rsp+2A8h+var_1C8], rax
0x18000eff0  lea     rax, aSprprovc; "SPRPROVC"
0x18000eff7  mov     [rsp+2A8h+var_1C0], rax
0x18000efff  mov     [rsp+2A8h+var_1B8], 157h
0x18000f00a  mov     [rsp+2A8h+var_1B4], 2
0x18000f015  mov     [rsp+2A8h+var_1B0], 0FFh
0x18000f020  mov     [rsp+2A8h+var_130], 1000000h
0x18000f02b  xor     edx, edx; Val
0x18000f02d  lea     r8d, [rdx+78h]; Size
0x18000f031  lea     rcx, [rsp+2A8h+var_1A8]; void *
0x18000f039  call    memset_0
0x18000f03e  mov     r9, r15
0x18000f041  mov     r8d, 1392h
0x18000f047  lea     rdx, [rsp+2A8h+var_1D0]
0x18000f04f  lea     rcx, [rsp+2A8h+var_E8]
0x18000f057  call    ?AddContext@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IPEBG@Z; CVssFunctionTracer::AddContext(CVssDebugInfo,uint,ushort const *)
0x18000f05c  lea     rax, aBaseStorVssMod_9; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000f063  mov     [rsp+2A8h+var_1D0], rax
0x18000f06b  lea     rax, aCvssoftwarepro_7; "CVsSoftwareProvider::BeginPrepareSnapsh"...
0x18000f072  mov     [rsp+2A8h+var_1C8], rax
0x18000f07a  lea     rax, aSprprovc; "SPRPROVC"
0x18000f081  mov     [rsp+2A8h+var_1C0], rax
0x18000f089  mov     [rsp+2A8h+var_1B8], 158h
0x18000f094  mov     [rsp+2A8h+var_1B4], 2
  ... truncated ...
```
