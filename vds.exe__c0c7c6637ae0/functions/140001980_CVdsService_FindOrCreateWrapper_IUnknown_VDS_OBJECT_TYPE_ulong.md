# CVdsService::FindOrCreateWrapper(IUnknown *,_VDS_OBJECT_TYPE,ulong * *)

- ea: `0x140001980`
- end: `0x14000239f`
- name: `?FindOrCreateWrapper@CVdsService@@QEAAPEAUIUnknown@@PEAU2@W4_VDS_OBJECT_TYPE@@PEAPEAK@Z`
- size: `2591`
- prototype: `struct IUnknown *__fastcall(CVdsService *__hidden this, struct IUnknown *, enum _VDS_OBJECT_TYPE, unsigned int **)`
- caller_count: `5`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400015f0`
- `0x1400016c0`
- `0x14000e920`
- `0x140015e10`
- `0x140038f90`

## callees

- `0x140001980`
- `0x1400032a0`
- `0x140008410`
- `0x140009610`
- `0x14001b958`
- `0x140035cfc`
- `0x1400383cc`
- `0x140038548`
- `0x1400392a0`
- `0x14003995c`
- `0x140039984`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140001c13`
- `msvcrt!_wcsicmp` at `0x140001c13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000224b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400022b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002353`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002361`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000224b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400022b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002353`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140002361`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001aca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400021e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001aca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400021e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140001f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140001f13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140001f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400022df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400022f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000232a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140001f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140001f13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140001f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400022df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400022f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000232a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000221e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000221e`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140001ae9`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x1400021f5`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140001ae9`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x1400021f5`
- `vdsutil!VdsTrace` at `0x140001b06`
- `vdsutil!VdsTrace` at `0x140001b2e`
- `vdsutil!VdsTrace` at `0x140001cae`
- `vdsutil!VdsTrace` at `0x140001b06`
- `vdsutil!VdsTrace` at `0x140001b2e`
- `vdsutil!VdsTrace` at `0x140001cae`
- `vdsutil!?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x140002214`
- `vdsutil!?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x140002214`
- `vdsutil!VdsTraceEx` at `0x140001e00`
- `vdsutil!VdsTraceEx` at `0x140001e8b`
- `vdsutil!VdsTraceEx` at `0x140002152`
- `vdsutil!VdsTraceEx` at `0x140002241`
- `vdsutil!VdsTraceEx` at `0x1400022a6`
- `vdsutil!VdsTraceEx` at `0x140001e00`
- `vdsutil!VdsTraceEx` at `0x140001e8b`
- `vdsutil!VdsTraceEx` at `0x140002152`
- `vdsutil!VdsTraceEx` at `0x140002241`
- `vdsutil!VdsTraceEx` at `0x1400022a6`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140001a68`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000219b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140001a68`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000219b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002256`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400022bb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000236c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140002256`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400022bb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000236c`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x140001c21`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x140001c21`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140001bc2`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140001bc2`

## string_xrefs

- `0x140001a58`: `CVdsService::FindOrCreateWrapper()`
- `0x140001aff`: `CVdsService::FindOrCreateWrapper, temp: object found: %p`
- `0x140001b27`: `CVdsService::FindOrCreateWrapper, temp: object not found.`
- `0x14000218b`: `CVdsService::AddObjectToMap()`
- `0x140001ca2`: `CVdsService::FindOrCreateWrapper, 4, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
struct IUnknown *__fastcall CVdsService::FindOrCreateWrapper(
        struct _RTL_CRITICAL_SECTION *this,
        struct IUnknown *a2,
        enum _VDS_OBJECT_TYPE a3,
        unsigned int **a4)
{
  enum _VDS_OBJECT_TYPE v4; // esi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  CRtlMap *p_LockCount; // r13
  void *Instance; // rdi
  int v10; // edi
  __int64 v11; // rax
  __int64 v12; // r8
  int LunObjectWrapper; // esi
  int v14; // eax
  __int64 v15; // r9
  const char *v16; // r8
  int v17; // edi
  wchar_t *LunFromId; // rax
  DWORD LastError; // eax
  CVdsService *v20; // rcx
  unsigned int *CookieInGlobalMap; // rax
  enum _VDS_OBJECT_TYPE v22; // r8d
  int v24; // [rsp+28h] [rbp-138h]
  int v25; // [rsp+30h] [rbp-130h]
  int v26; // [rsp+38h] [rbp-128h]
  int v27; // [rsp+40h] [rbp-120h]
  int v28; // [rsp+48h] [rbp-118h]
  int v29; // [rsp+50h] [rbp-110h]
  int v30; // [rsp+58h] [rbp-108h]
  int v31; // [rsp+60h] [rbp-100h]
  int v32; // [rsp+68h] [rbp-F8h]
  const wchar_t *v33; // [rsp+70h] [rbp-F0h]
  unsigned int Data1; // [rsp+78h] [rbp-E8h]
  int Data2; // [rsp+80h] [rbp-E0h]
  int Data3; // [rsp+88h] [rbp-D8h]
  int v37; // [rsp+90h] [rbp-D0h]
  int v38; // [rsp+98h] [rbp-C8h]
  int v39; // [rsp+A0h] [rbp-C0h]
  int v40; // [rsp+A8h] [rbp-B8h]
  int v41; // [rsp+B0h] [rbp-B0h]
  int v42; // [rsp+B8h] [rbp-A8h]
  int v43; // [rsp+C0h] [rbp-A0h]
  int v44; // [rsp+C8h] [rbp-98h]
  struct IUnknown *v45; // [rsp+D0h] [rbp-90h]
  void *v46; // [rsp+D8h] [rbp-88h]
  __int64 v48; // [rsp+E8h] [rbp-78h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-70h] BYREF
  const wchar_t *v50[2]; // [rsp+F8h] [rbp-68h] BYREF
  struct IUnknown *v51; // [rsp+108h] [rbp-58h]
  __int128 v52; // [rsp+110h] [rbp-50h] BYREF
  __int64 v53; // [rsp+120h] [rbp-40h]
  struct _RTL_CRITICAL_SECTION *v54; // [rsp+128h] [rbp-38h]
  _BYTE v55[16]; // [rsp+130h] [rbp-30h] BYREF
  struct _GUID v56[5]; // [rsp+140h] [rbp-20h] BYREF
  struct _GUID v57[8]; // [rsp+190h] [rbp+30h] BYREF
  struct _GUID v58; // [rsp+210h] [rbp+B0h] BYREF
  struct _GUID v59; // [rsp+220h] [rbp+C0h] BYREF
  void *v60; // [rsp+230h] [rbp+D0h]
  __int64 v61; // [rsp+238h] [rbp+D8h]
  struct _GUID v62; // [rsp+240h] [rbp+E0h] BYREF
  struct IUnknown *v63; // [rsp+250h] [rbp+F0h]
  __int64 v64; // [rsp+258h] [rbp+F8h]
  _QWORD v65[4]; // [rsp+260h] [rbp+100h] BYREF
  __int128 v66; // [rsp+280h] [rbp+120h] BYREF
  __int128 v67; // [rsp+290h] [rbp+130h]

  v4 = a3;
  v51 = a2;
  *(_QWORD *)&v59.Data1 = 0;
  v48 = 0;
  v49 = 0;
  v58 = 0;
  v52 = 0;
  v53 = 0;
  memset(v57, 0, sizeof(v57));
  memset(v56, 0, 72);
  v65[0] = 0;
  v65[1] = 0;
  v65[3] = 0;
  v66 = 0;
  v67 = 0;
  v65[2] = a2;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v55, 0x5Eu, "CVdsService::FindOrCreateWrapper()");
  memset(v57, 0, sizeof(v57));
  memset(v56, 0, 72);
  EnterCriticalSection(&g_GlobalCriticalSection);
  v7 = this + 3;
  v54 = this + 3;
  EnterCriticalSection(this + 3);
  p_LockCount = (CRtlMap *)&this[4].LockCount;
  if ( CRtlMap::Find((CRtlMap *)&this[4].LockCount, (struct CRtlEntry *)v65, (struct CRtlEntry *)&v66) )
  {
    VdsTrace(1, "CVdsService::FindOrCreateWrapper, temp: object found: %p", (const void *)v67);
    Instance = (void *)v67;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v67 + 8LL))(v67);
    goto LABEL_50;
  }
  VdsTrace(1, "CVdsService::FindOrCreateWrapper, temp: object not found.");
  if ( !dword_14009B420 )
  {
LABEL_39:
    Instance = VdsCreateInstance(a2, v4, (struct CVdsService *)this);
    if ( !Instance )
      goto LABEL_50;
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v50, 0x5Eu, "CVdsService::AddObjectToMap()");
    *(_QWORD *)&v62.Data1 = 0;
    *(_QWORD *)v62.Data4 = 0;
    v64 = 0;
    *(_QWORD *)&v59.Data1 = 0;
    *(_QWORD *)v59.Data4 = 0;
    v61 = 0;
    v63 = a2;
    v60 = Instance;
    v51 = (struct IUnknown *)v7;
    EnterCriticalSection(v7);
    if ( CRtlMap::Find(p_LockCount, (struct CRtlEntry *)&v62, 0) )
    {
      LastError = -2147212259;
    }
    else if ( CRtlMap::Insert(p_LockCount, (struct CRtlEntry *)&v62, (struct CRtlEntry *)&v59)
           || (LastError = GetLastError()) == 0 )
    {
      VdsTraceEx(94, 3, "ObjectMap: Wrapper added to map: %p, %p", a2, Instance);
      LeaveCriticalSection(v7);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v50);
      if ( v4 != VDS_OT_VOLUME )
        goto LABEL_50;
      CookieInGlobalMap = CVdsService::FindOrCreateCookieInGlobalMap(v20, a2);
      if ( CookieInGlobalMap )
      {
        *((_QWORD *)Instance + 19) = CookieInGlobalMap;
        goto LABEL_50;
      }
      CVdsService::RemoveObjectFromMap((CVdsService *)this, a2, v22);
      goto LABEL_49;
    }
    VdsTraceEx(94, 3, "ObjectMap: Wrapper could not be added to map: %p, %p, error=%ld", a2, Instance, LastError);
    LeaveCriticalSection(v7);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v50);
    (*(void (__fastcall **)(void *))(*(_QWORD *)Instance + 16LL))(Instance);
LABEL_49:
    Instance = 0;
    goto LABEL_50;
  }
  if ( v4 == VDS_OT_DISK )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IVdsDisk,
           &v48) >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v48 + 24LL))(v48, v57);
      if ( v48 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        v48 = 0;
      }
      if ( v10 >= 0 && *(_QWORD *)v57[7].Data4 )
      {
        v11 = CRtlMap::Begin(CVdsService::m_mapLunIds, &v62);
        v52 = *(_OWORD *)v11;
        v53 = *(_QWORD *)(v11 + 16);
        while ( (_QWORD)v52 && *((_QWORD *)&v52 + 1) )
        {
          CRtlMapIter::GetKeyGuid((CRtlMapIter *)&v52, &v62);
          v50[0] = *(const wchar_t **)(v12 + 48);
          if ( !_wcsicmp(*(const wchar_t **)v57[7].Data4, v50[0]) )
          {
            LunObjectWrapper = CVdsService::GetLunObjectWrapper((CVdsService *)this, &v62, (struct IUnknown **)&v59);
            if ( LunObjectWrapper < 0 || (Instance = *(void **)&v59.Data1) == 0 )
            {
              VdsTraceEx(
                94,
                3,
                "No match in LUN-disk map for Disk {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} [%ws] (Unk: %p)",
                v57[0].Data1,
                v57[0].Data2,
                v57[0].Data3,
                v57[0].Data4[0],
                v57[0].Data4[1],
                v57[0].Data4[2],
                v57[0].Data4[3],
                v57[0].Data4[4],
                v57[0].Data4[5],
                v57[0].Data4[6],
                v57[0].Data4[7],
                v50[0],
                a2);
              p_LockCount = (CRtlMap *)&this[4].LockCount;
              goto LABEL_38;
            }
            ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
            CVdsDiskLun::SetObjectAndService((CVdsDiskLun *)Instance, a2, 0, *((struct CVdsService **)Instance + 27));
            if ( !(unsigned int)CVdsService::AddObjectToMap(this, a2, (struct IUnknown *)Instance) )
            {
              VdsTrace(1, "CVdsService::FindOrCreateWrapper, 4, hr=%lX", LunObjectWrapper);
              goto LABEL_49;
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)Instance + 8LL))(Instance);
            CRtlMapIter::GetKeyGuid((CRtlMapIter *)&v52, &v59);
            v46 = Instance;
            v45 = v51;
            v44 = v59.Data4[7];
            v43 = v59.Data4[6];
            v42 = v59.Data4[5];
            v41 = v59.Data4[4];
            v40 = v59.Data4[3];
            v39 = v59.Data4[2];
            v38 = v59.Data4[1];
            v37 = v59.Data4[0];
            Data3 = v59.Data3;
            Data2 = v59.Data2;
            Data1 = v59.Data1;
            v33 = v50[0];
            v32 = v57[0].Data4[7];
            v31 = v57[0].Data4[6];
            v30 = v57[0].Data4[5];
            v29 = v57[0].Data4[4];
            v28 = v57[0].Data4[3];
            v27 = v57[0].Data4[2];
            v26 = v57[0].Data4[1];
            v25 = v57[0].Data4[0];
            v24 = v57[0].Data3;
            v14 = v57[0].Data2;
            v15 = v57[0].Data1;
            v16 = "Disk {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} [%ws] is LUN Id {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%"
                  ".2x%.2x%.2x%.2x%.2x} from LUN-disk map; reusing wrapper (Unk:%p, Wrapper:%p)";
            goto LABEL_20;
          }
          CRtlMapIter::Next((CRtlMapIter *)&v52);
        }
      }
    }
    goto LABEL_39;
  }
  if ( v4 != VDS_OT_LUN
    || ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IVdsLun,
         &v49) < 0 )
  {
    goto LABEL_39;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v49 + 24LL))(v49, v56);
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( *(_QWORD *)v56[1].Data4 )
  {
    CoTaskMemFree(*(LPVOID *)v56[1].Data4);
    *(_QWORD *)v56[1].Data4 = 0;
  }
  if ( *(_QWORD *)&v56[2].Data1 )
  {
    CoTaskMemFree(*(LPVOID *)&v56[2].Data1);
    *(_QWORD *)&v56[2].Data1 = 0;
  }
  if ( *(_QWORD *)v56[2].Data4 )
  {
    CoTaskMemFree(*(LPVOID *)v56[2].Data4);
    *(_QWORD *)v56[2].Data4 = 0;
  }
  if ( v17 < 0 )
    goto LABEL_39;
  LunFromId = CVdsService::FindLunFromId(v56);
  v50[0] = LunFromId;
  if ( !LunFromId )
    goto LABEL_39;
  if ( (int)CVdsService::GetDiskId(LunFromId, &v58) < 0
    || (v62 = v58, (int)CVdsService::GetDiskObjectWrapper((CVdsService *)this, &v62, (struct IUnknown **)&v59) < 0) )
  {
    VdsTraceEx(
      94,
      3,
      "No match in LUN-disk map for LUN {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} [%ws]; (Unk: %p)",
      v56[0].Data1,
      v56[0].Data2,
      v56[0].Data3,
      v56[0].Data4[0],
      v56[0].Data4[1],
      v56[0].Data4[2],
      v56[0].Data4[3],
      v56[0].Data4[4],
      v56[0].Data4[5],
      v56[0].Data4[6],
      v56[0].Data4[7],
      v50[0],
      a2);
    v7 = this + 3;
LABEL_38:
    v4 = a3;
    goto LABEL_39;
  }
  Instance = *(void **)&v59.Data1;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v59.Data1 + 8LL))(*(_QWORD *)&v59.Data1);
  CVdsService::AddObjectToMap(this, a2, (struct IUnknown *)Instance);
  v46 = Instance;
  v45 = v51;
  v44 = v58.Data4[7];
  v43 = v58.Data4[6];
  v42 = v58.Data4[5];
  v41 = v58.Data4[4];
  v40 = v58.Data4[3];
  v39 = v58.Data4[2];
  v38 = v58.Data4[1];
  v37 = v58.Data4[0];
  Data3 = v58.Data3;
  Data2 = v58.Data2;
  Data1 = v58.Data1;
  v33 = v50[0];
  v32 = v56[0].Data4[7];
  v31 = v56[0].Data4[6];
  v30 = v56[0].Data4[5];
  v29 = v56[0].Data4[4];
  v28 = v56[0].Data4[3];
  v27 = v56[0].Data4[2];
  v26 = v56[0].Data4[1];
  v25 = v56[0].Data4[0];
  v24 = v56[0].Data3;
  v14 = v56[0].Data2;
  v15 = v56[0].Data1;
  v16 = "LUN {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} [%ws] is disk Id:{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2"
        "x%.2x%.2x} from LUN-disk map; re-using wrapper (Unk:%p Wrapper:%p)";
LABEL_20:
  VdsTraceEx(
    94,
    3,
    v16,
    v15,
    v14,
    v24,
    v25,
    v26,
    v27,
    v28,
    v29,
    v30,
    v31,
    v32,
    v33,
    Data1,
    Data2,
    Data3,
    v37,
    v38,
    v39,
    v40,
    v41,
    v42,
    v43,
    v44,
    v45,
    v46);
LABEL_50:
  if ( *(_QWORD *)v57[5].Data4 )
  {
    CoTaskMemFree(*(LPVOID *)v57[5].Data4);
    *(_QWORD *)v57[5].Data4 = 0;
  }
  if ( *(_QWORD *)&v57[6].Data1 )
  {
    CoTaskMemFree(*(LPVOID *)&v57[6].Data1);
    *(_QWORD *)&v57[6].Data1 = 0;
  }
  if ( *(_QWORD *)v57[6].Data4 )
  {
    CoTaskMemFree(*(LPVOID *)v57[6].Data4);
    *(_QWORD *)v57[6].Data4 = 0;
  }
  if ( *(_QWORD *)&v57[7].Data1 )
  {
    CoTaskMemFree(*(LPVOID *)&v57[7].Data1);
    *(_QWORD *)&v57[7].Data1 = 0;
  }
  if ( *(_QWORD *)v57[7].Data4 )
  {
    CoTaskMemFree(*(LPVOID *)v57[7].Data4);
    *(_QWORD *)v57[7].Data4 = 0;
  }
  LeaveCriticalSection(v7);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v55);
  return (struct IUnknown *)Instance;
}

```

## disassembly

```asm
0x140001980  mov     [rsp-8+arg_18], rbx
0x140001985  push    rbp
0x140001986  push    rsi
0x140001987  push    rdi
0x140001988  push    r12
0x14000198a  push    r13
0x14000198c  push    r14
0x14000198e  push    r15
0x140001990  lea     rbp, [rsp-150h]
0x140001998  sub     rsp, 2B0h
0x14000199f  mov     rax, cs:__security_cookie
0x1400019a6  xor     rax, rsp
0x1400019a9  mov     [rbp+180h+var_38], rax
0x1400019b0  mov     esi, r8d
0x1400019b3  mov     [rbp+180h+var_200], r8d
0x1400019b7  mov     r12, rdx
0x1400019ba  mov     [rbp+180h+var_1D8], rdx
0x1400019be  mov     r15, rcx
0x1400019c1  xor     r14d, r14d
0x1400019c4  mov     qword ptr [rbp+180h+var_C0.Data1], r14
0x1400019cb  mov     [rbp+180h+var_1F8], r14
0x1400019cf  mov     [rbp+180h+var_1F0], r14
0x1400019d3  xorps   xmm0, xmm0
0x1400019d6  movups  xmmword ptr [rbp+180h+var_D0.Data1], xmm0
0x1400019dd  xorps   xmm1, xmm1
0x1400019e0  xor     eax, eax
0x1400019e2  movups  [rbp+180h+var_1D0], xmm1
0x1400019e6  mov     [rbp+180h+var_1C0], rax
0x1400019ea  mov     dword ptr [rbp+180h+var_150], r14d
0x1400019ee  movups  [rbp+180h+var_150+4], xmm0
0x1400019f2  movups  [rbp+180h+var_13C], xmm0
0x1400019f6  movups  [rbp+180h+var_12C], xmm0
0x1400019fa  movups  [rbp+180h+var_11C], xmm0
0x1400019fe  movups  [rbp+180h+var_10C], xmm0
0x140001a02  movups  xmmword ptr [rbp+180h+var_FC], xmm0
0x140001a09  movups  xmmword ptr [rbp+180h+var_EC], xmm0
0x140001a10  movups  xmmword ptr [rbp+180h+var_EC+0Ch], xmm0
0x140001a17  mov     [rbp+180h+var_1A0.Data1], r14d
0x140001a1b  movups  xmmword ptr [rbp+180h+var_1A0.Data2], xmm0
0x140001a1f  movups  xmmword ptr [rbp+180h+pv], xmm0
0x140001a23  movups  xmmword ptr [rbp+180h+var_17C], xmm0
0x140001a27  movups  [rbp+180h+var_16C], xmm0
0x140001a2b  mov     [rbp+180h+var_15C], eax
0x140001a2e  mov     [rbp+180h+var_80], r14
0x140001a35  mov     [rbp+180h+var_78], r14
0x140001a3c  mov     [rbp+180h+var_68], r14
0x140001a43  movups  [rbp+180h+var_60], xmm0
0x140001a4a  movups  [rbp+180h+var_50], xmm0
0x140001a51  mov     [rbp+180h+var_70], rdx
0x140001a58  lea     r8, aCvdsserviceFin_8; "CVdsService::FindOrCreateWrapper()"
0x140001a5f  mov     edx, 5Eh ; '^'
0x140001a64  lea     rcx, [rbp+180h+var_1B0]
0x140001a68  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140001a6e  nop
0x140001a6f  xorps   xmm0, xmm0
0x140001a72  movups  [rbp+180h+var_150], xmm0
0x140001a76  movups  xmmword ptr [rbp+40h], xmm0
0x140001a7a  movups  [rbp+180h+var_13C+0Ch], xmm0
0x140001a7e  movups  [rbp+180h+var_12C+0Ch], xmm0
0x140001a82  movups  [rbp+180h+var_11C+0Ch], xmm0
0x140001a86  movups  [rbp+180h+var_10C+0Ch], xmm0
0x140001a8d  movups  xmmword ptr [rbp+180h+var_FC+0Ch], xmm0
0x140001a94  movups  xmmword ptr [rbp+180h+var_EC+0Ch], xmm0
0x140001a9b  xor     eax, eax
0x140001a9d  movups  xmmword ptr [rbp+180h+var_1A0.Data1], xmm0
0x140001aa1  movups  xmmword ptr [rbp-10h], xmm0
0x140001aa5  movups  xmmword ptr [rbp+180h+pv+0Ch], xmm0
0x140001aa9  movups  xmmword ptr [rbp+180h+var_17C+0Ch], xmm0
0x140001aad  mov     qword ptr [rbp+180h+var_16C+0Ch], rax
0x140001ab1  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140001ab8  call    cs:__imp_EnterCriticalSection
0x140001abe  nop
0x140001abf  lea     rbx, [r15+78h]
0x140001ac3  mov     [rbp+180h+var_1B8], rbx
0x140001ac7  mov     rcx, rbx; lpCriticalSection
0x140001aca  call    cs:__imp_EnterCriticalSection
0x140001ad0  nop
0x140001ad1  lea     r13, [r15+0A8h]
0x140001ad8  lea     r8, [rbp+180h+var_60]
0x140001adf  lea     rdx, [rbp+180h+var_80]
0x140001ae6  mov     rcx, r13
0x140001ae9  call    cs:__imp_?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z; CRtlMap::Find(CRtlEntry &,CRtlEntry *)
0x140001aef  mov     ecx, 1
0x140001af4  test    eax, eax
0x140001af6  jz      short loc_140001B27
0x140001af8  mov     r8, qword ptr [rbp+180h+var_50]
0x140001aff  lea     rdx, aCvdsserviceFin_2; "CVdsService::FindOrCreateWrapper, temp:"...
0x140001b06  call    cs:__imp_VdsTrace
0x140001b0c  mov     rdi, qword ptr [rbp+180h+var_50]
0x140001b13  mov     rax, [rdi]
0x140001b16  mov     rcx, rdi
0x140001b19  mov     rax, [rax+8]
0x140001b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b22  jmp     loc_1400022D3
0x140001b27  lea     rdx, aCvdsserviceFin_3; "CVdsService::FindOrCreateWrapper, temp:"...
0x140001b2e  call    cs:__imp_VdsTrace
0x140001b34  cmp     cs:dword_14009B420, 0
0x140001b3b  jz      loc_140002162
0x140001b41  cmp     esi, 0Dh
0x140001b44  jnz     loc_140001E9D
0x140001b4a  mov     rax, [r12]
0x140001b4e  lea     r8, [rbp+180h+var_1F8]
0x140001b52  lea     rdx, IID_IVdsDisk
0x140001b59  mov     rcx, r12
0x140001b5c  mov     rax, [rax]
0x140001b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b64  test    eax, eax
0x140001b66  js      loc_140002162
0x140001b6c  mov     rcx, [rbp+180h+var_1F8]
0x140001b70  mov     rax, [rcx]
0x140001b73  lea     rdx, [rbp+180h+var_150]
0x140001b77  mov     rax, [rax+18h]
0x140001b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b80  mov     edi, eax
0x140001b82  mov     rdx, [rbp+180h+var_1F8]
0x140001b86  test    rdx, rdx
0x140001b89  jz      short loc_140001B9E
0x140001b8b  mov     rcx, [rdx]
0x140001b8e  mov     rax, [rcx+10h]
0x140001b92  mov     rcx, rdx
0x140001b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b9a  mov     [rbp+180h+var_1F8], r14
0x140001b9e  test    edi, edi
0x140001ba0  js      loc_140002162
0x140001ba6  cmp     [rbp+180h+String1], 0
0x140001bae  jz      loc_140002162
0x140001bb4  lea     rdx, [rbp+180h+var_A0]
0x140001bbb  lea     rcx, ?m_mapLunIds@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapLunIds
0x140001bc2  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x140001bc8  movups  xmm0, xmmword ptr [rax]
0x140001bcb  movups  [rbp+180h+var_1D0], xmm0
0x140001bcf  movsd   xmm1, qword ptr [rax+10h]
0x140001bd4  movsd   [rbp+180h+var_1C0], xmm1
0x140001bd9  cmp     qword ptr [rbp+180h+var_1D0], 0
0x140001bde  jz      loc_140002162
0x140001be4  mov     r8, qword ptr [rbp+180h+var_1D0+8]
0x140001be8  test    r8, r8
0x140001beb  jz      loc_140002162
0x140001bf1  lea     rdx, [rbp+180h+var_A0]; retstr
0x140001bf8  lea     rcx, [rbp+180h+var_1D0]; this
0x140001bfc  call    ?GetKeyGuid@CRtlMapIter@@QEBA?AU_GUID@@XZ; CRtlMapIter::GetKeyGuid(void)
0x140001c01  mov     rax, [r8+30h]
0x140001c05  mov     [rbp+180h+var_1E8], rax
0x140001c09  mov     rdx, rax; String2
0x140001c0c  mov     rcx, [rbp+180h+String1]; String1
0x140001c13  call    cs:__imp__wcsicmp
0x140001c19  test    eax, eax
0x140001c1b  jz      short loc_140001C29
0x140001c1d  lea     rcx, [rbp+180h+var_1D0]
0x140001c21  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x140001c27  jmp     short loc_140001BD9
0x140001c29  movaps  xmm0, xmmword ptr [rbp+180h+var_A0.Data1]
0x140001c30  movdqa  xmmword ptr [rbp+180h+var_A0.Data1], xmm0
0x140001c38  lea     r8, [rbp+180h+var_C0]; struct IUnknown **
0x140001c3f  lea     rdx, [rbp+180h+var_A0]; struct _GUID
0x140001c46  mov     rcx, r15; this
0x140001c49  call    ?GetLunObjectWrapper@CVdsService@@QEAAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetLunObjectWrapper(_GUID,IUnknown * *)
0x140001c4e  mov     esi, eax
0x140001c50  test    eax, eax
0x140001c52  js      loc_140001E0E
0x140001c58  mov     rdi, qword ptr [rbp+180h+var_C0.Data1]
0x140001c5f  test    rdi, rdi
0x140001c62  jz      loc_140001E0E
0x140001c68  mov     rdx, [r12]
0x140001c6c  mov     rcx, r12
0x140001c6f  mov     rax, [rdx+8]
0x140001c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c78  mov     r9, [rdi+0D8h]; struct CVdsService *
0x140001c7f  xor     r8d, r8d; struct IUnknown *
0x140001c82  mov     rdx, r12; struct IUnknown *
0x140001c85  mov     rcx, rdi; this
0x140001c88  call    ?SetObjectAndService@CVdsDiskLun@@QEAAJPEAUIUnknown@@0PEAVCVdsService@@@Z; CVdsDiskLun::SetObjectAndService(IUnknown *,IUnknown *,CVdsService *)
0x140001c8d  mov     r8, rdi; struct IUnknown *
0x140001c90  mov     rdx, r12; struct IUnknown *
0x140001c93  mov     rcx, r15; this
0x140001c96  call    ?AddObjectToMap@CVdsService@@QEAAHPEAUIUnknown@@0@Z; CVdsService::AddObjectToMap(IUnknown *,IUnknown *)
0x140001c9b  test    eax, eax
0x140001c9d  jnz     short loc_140001CB9
0x140001c9f  mov     r8d, esi
0x140001ca2  lea     rdx, aCvdsserviceFin_15; "CVdsService::FindOrCreateWrapper, 4, hr"...
0x140001ca9  mov     ecx, 1
0x140001cae  call    cs:__imp_VdsTrace
0x140001cb4  jmp     loc_1400022D0
0x140001cb9  mov     rax, [rdi]
0x140001cbc  mov     rcx, rdi
0x140001cbf  mov     rax, [rax+8]
0x140001cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001cc8  lea     rdx, [rbp+180h+var_C0]; retstr
0x140001ccf  lea     rcx, [rbp+180h+var_1D0]; this
0x140001cd3  call    ?GetKeyGuid@CRtlMapIter@@QEBA?AU_GUID@@XZ; CRtlMapIter::GetKeyGuid(void)
0x140001cd8  movzx   ecx, [rbp+180h+var_C0.Data4+7]
0x140001cdf  movzx   eax, [rbp+180h+var_C0.Data4+6]
0x140001ce6  movzx   edx, [rbp+180h+var_C0.Data4+5]
0x140001ced  movzx   r8d, [rbp+180h+var_C0.Data4+4]
0x140001cf5  movzx   r9d, [rbp+180h+var_C0.Data4+3]
0x140001cfd  movzx   r10d, [rbp+180h+var_C0.Data4+2]
0x140001d05  movzx   r11d, [rbp+180h+var_C0.Data4+1]
0x140001d0d  movzx   esi, [rbp+180h+var_C0.Data4]
0x140001d14  movzx   r14d, [rbp+180h+var_C0.Data3]
0x140001d1c  movzx   r15d, [rbp+180h+var_C0.Data2]
0x140001d24  movzx   r13d, byte ptr [rbp+180h+var_150+0Eh]
0x140001d29  mov     [rsp+2E0h+var_208], rdi
0x140001d31  mov     r12, [rbp+180h+var_1D8]
0x140001d35  mov     [rsp+2E0h+var_210], r12
0x140001d3d  mov     [rsp+2E0h+var_218], ecx
0x140001d44  mov     [rsp+2E0h+var_220], eax
0x140001d4b  mov     [rsp+2E0h+var_228], edx
0x140001d52  mov     [rsp+2E0h+var_230], r8d
0x140001d5a  mov     [rsp+2E0h+var_238], r9d
0x140001d62  mov     [rsp+2E0h+var_240], r10d
0x140001d6a  mov     [rsp+2E0h+var_248], r11d
0x140001d72  mov     [rsp+2E0h+var_250], esi
0x140001d79  mov     [rsp+2E0h+var_258], r14d
0x140001d81  mov     [rsp+2E0h+var_260], r15d
0x140001d89  mov     eax, [rbp+180h+var_C0.Data1]
0x140001d8f  mov     dword ptr [rsp+2E0h+var_268], eax
0x140001d93  mov     rax, [rbp+180h+var_1E8]
0x140001d97  mov     [rsp+2E0h+var_270], rax
0x140001d9c  movzx   r12d, byte ptr [rbp+180h+var_150+0Fh]
0x140001da1  mov     [rsp+2E0h+var_278], r12d
0x140001da6  mov     [rsp+2E0h+var_280], r13d
0x140001dab  movzx   eax, byte ptr [rbp+180h+var_150+0Dh]
0x140001daf  mov     [rsp+2E0h+var_288], eax
0x140001db3  movzx   eax, byte ptr [rbp+180h+var_150+0Ch]
0x140001db7  mov     [rsp+2E0h+var_290], eax
0x140001dbb  movzx   eax, byte ptr [rbp+180h+var_150+0Bh]
0x140001dbf  mov     [rsp+2E0h+var_298], eax
0x140001dc3  movzx   eax, byte ptr [rbp+180h+var_150+0Ah]
0x140001dc7  mov     [rsp+2E0h+var_2A0], eax
0x140001dcb  movzx   eax, byte ptr [rbp+180h+var_150+9]
0x140001dcf  mov     [rsp+2E0h+var_2A8], eax
0x140001dd3  movzx   eax, byte ptr [rbp+180h+var_150+8]
0x140001dd7  mov     [rsp+2E0h+var_2B0], eax
0x140001ddb  movzx   eax, word ptr [rbp+180h+var_150+6]
0x140001ddf  mov     [rsp+2E0h+var_2B8], eax
0x140001de3  movzx   eax, word ptr [rbp+180h+var_150+4]
0x140001de7  mov     r9d, dword ptr [rbp+180h+var_150]
0x140001deb  lea     r8, aDisk8x4x4x2x2x; "Disk {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%"...
0x140001df2  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x140001df6  mov     edx, 3
0x140001dfb  mov     ecx, 5Eh ; '^'
0x140001e00  call    cs:__imp_VdsTraceEx
0x140001e06  xor     r14d, r14d
0x140001e09  jmp     loc_1400022D3
0x140001e0e  movzx   eax, byte ptr [rbp+180h+var_150+0Fh]
0x140001e12  movzx   ecx, byte ptr [rbp+180h+var_150+0Eh]
0x140001e16  movzx   edx, byte ptr [rbp+180h+var_150+0Dh]
0x140001e1a  movzx   r8d, byte ptr [rbp+180h+var_150+0Ch]
0x140001e1f  movzx   r9d, byte ptr [rbp+180h+var_150+0Bh]
0x140001e24  movzx   r10d, byte ptr [rbp+180h+var_150+0Ah]
0x140001e29  movzx   r11d, byte ptr [rbp+180h+var_150+9]
0x140001e2e  movzx   edi, byte ptr [rbp+180h+var_150+8]
0x140001e32  movzx   esi, word ptr [rbp+180h+var_150+6]
0x140001e36  movzx   r14d, word ptr [rbp+180h+var_150+4]
0x140001e3b  mov     [rsp+2E0h+var_268], r12
0x140001e40  mov     r13, [rbp+180h+var_1E8]
0x140001e44  mov     [rsp+2E0h+var_270], r13
0x140001e49  mov     [rsp+2E0h+var_278], eax
0x140001e4d  mov     [rsp+2E0h+var_280], ecx
0x140001e51  mov     [rsp+2E0h+var_288], edx
0x140001e55  mov     [rsp+2E0h+var_290], r8d
0x140001e5a  mov     [rsp+2E0h+var_298], r9d
0x140001e5f  mov     [rsp+2E0h+var_2A0], r10d
0x140001e64  mov     [rsp+2E0h+var_2A8], r11d
0x140001e69  mov     [rsp+2E0h+var_2B0], edi
0x140001e6d  mov     [rsp+2E0h+var_2B8], esi
0x140001e71  mov     dword ptr [rsp+2E0h+var_2C0], r14d
0x140001e76  mov     r9d, dword ptr [rbp+180h+var_150]
0x140001e7a  lea     r8, aNoMatchInLunDi; "No match in LUN-disk map for Disk {%.8x"...
0x140001e81  mov     edx, 3
0x140001e86  mov     ecx, 5Eh ; '^'
0x140001e8b  call    cs:__imp_VdsTraceEx
0x140001e91  lea     r13, [r15+0A8h]
0x140001e98  jmp     loc_14000215C
0x140001e9d  cmp     esi, 21h ; '!'
0x140001ea0  jnz     loc_140002162
0x140001ea6  mov     rax, [r12]
0x140001eaa  lea     r8, [rbp+180h+var_1F0]
0x140001eae  lea     rdx, IID_IVdsLun
0x140001eb5  mov     rcx, r12
0x140001eb8  mov     rax, [rax]
0x140001ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ec0  test    eax, eax
0x140001ec2  js      loc_140002162
0x140001ec8  mov     rcx, [rbp+180h+var_1F0]
0x140001ecc  mov     rax, [rcx]
0x140001ecf  lea     rdx, [rbp+180h+var_1A0]
0x140001ed3  mov     rax, [rax+18h]
0x140001ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001edc  mov     edi, eax
0x140001ede  mov     rcx, [rbp+180h+var_1F0]
0x140001ee2  test    rcx, rcx
0x140001ee5  jz      short loc_140001EF7
0x140001ee7  mov     rdx, [rcx]
0x140001eea  mov     rax, [rdx+10h]
0x140001eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ef3  mov     [rbp+180h+var_1F0], r14
0x140001ef7  mov     rcx, [rbp+180h+pv+4]; pv
0x140001efb  test    rcx, rcx
0x140001efe  jz      short loc_140001F0A
  ... truncated ...
```
