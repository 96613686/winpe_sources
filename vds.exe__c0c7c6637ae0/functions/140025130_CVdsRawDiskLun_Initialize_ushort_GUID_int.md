# CVdsRawDiskLun::Initialize(ushort *,_GUID &,int)

- ea: `0x140025130`
- end: `0x140025a65`
- name: `?Initialize@CVdsRawDiskLun@@QEAAKPEAGAEAU_GUID@@H@Z`
- size: `2357`
- prototype: `unsigned int(CVdsRawDiskLun *__hidden this, unsigned __int16 *, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140037a0c`

## callees

- `0x1400069e8`
- `0x140006e60`
- `0x140013298`
- `0x140025130`
- `0x14002e123`
- `0x140052e80`

## import_xrefs

- `msvcrt!_ltow` at `0x14002551c`
- `msvcrt!_ltow` at `0x14002551c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002525f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14002525f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002535d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025380`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400253a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400253c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002567a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400256f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400257cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002582a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002584c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025925`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002535d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025380`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400253a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400253c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025624`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002567a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400256f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400257cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002582a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002584c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025901`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140025925`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400258f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400258f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400258b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400258b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025a0c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002589e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140025a25`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002589e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140025a25`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x140025714`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x140025714`
- `vdsutil!OpenDevice` at `0x1400252bc`
- `vdsutil!OpenDevice` at `0x1400252bc`
- `vdsutil!GetDeviceAndMediaType` at `0x140025423`
- `vdsutil!GetDeviceAndMediaType` at `0x140025423`
- `vdsutil!GetDeviceNumber` at `0x140025316`
- `vdsutil!GetDeviceNumber` at `0x140025316`
- `vdsutil!GetDeviceManufacturerInfo` at `0x1400253f0`
- `vdsutil!GetDeviceManufacturerInfo` at `0x1400253f0`
- `vdsutil!GetMediaGeometryEx` at `0x140025447`
- `vdsutil!GetMediaGeometryEx` at `0x140025447`
- `vdsutil!GetStorageAccessAlignmentProperty` at `0x140025477`
- `vdsutil!GetStorageAccessAlignmentProperty` at `0x140025477`
- `vdsutil!IsDiskClustered` at `0x1400254dc`
- `vdsutil!IsDiskClustered` at `0x1400254dc`
- `vdsutil!IsDiskReadOnly` at `0x14002557f`
- `vdsutil!IsDiskReadOnly` at `0x14002557f`
- `vdsutil!IsDiskCurrentStateReadOnly` at `0x1400255bd`
- `vdsutil!IsDiskCurrentStateReadOnly` at `0x1400255bd`
- `vdsutil!CreateDeviceInfoSet` at `0x1400255fe`
- `vdsutil!CreateDeviceInfoSet` at `0x1400255fe`
- `vdsutil!GetDeviceId` at `0x140025647`
- `vdsutil!GetDeviceId` at `0x140025647`
- `vdsutil!GetDeviceRegistryPropertyByInfo` at `0x1400256a8`
- `vdsutil!GetDeviceRegistryPropertyByInfo` at `0x1400256a8`
- `vdsutil!VdsAllocateEmptyString` at `0x1400256c7`
- `vdsutil!VdsAllocateEmptyString` at `0x140025730`
- `vdsutil!VdsAllocateEmptyString` at `0x14002576f`
- `vdsutil!VdsAllocateEmptyString` at `0x1400256c7`
- `vdsutil!VdsAllocateEmptyString` at `0x140025730`
- `vdsutil!VdsAllocateEmptyString` at `0x14002576f`
- `vdsutil!GetDeviceRegistryPropertyByInst` at `0x140025753`
- `vdsutil!GetDeviceRegistryPropertyByInst` at `0x140025753`
- `vdsutil!GetDeviceLocationEx` at `0x14002587d`
- `vdsutil!GetDeviceLocationEx` at `0x14002587d`
- `vdsutil!VdsDoesDiskHaveArcPath` at `0x140025987`
- `vdsutil!VdsDoesDiskHaveArcPath` at `0x140025987`
- `vdsutil!GetBootFromDiskNumber` at `0x1400259be`
- `vdsutil!GetBootFromDiskNumber` at `0x1400259be`
- `vdsutil!VdsHeapAlloc` at `0x1400257de`
- `vdsutil!VdsHeapAlloc` at `0x140025938`
- `vdsutil!VdsHeapAlloc` at `0x1400257de`
- `vdsutil!VdsHeapAlloc` at `0x140025938`
- `vdsutil!VdsHeapFree` at `0x14002536b`
- `vdsutil!VdsHeapFree` at `0x14002538e`
- `vdsutil!VdsHeapFree` at `0x1400253af`
- `vdsutil!VdsHeapFree` at `0x1400253d0`
- `vdsutil!VdsHeapFree` at `0x140025632`
- `vdsutil!VdsHeapFree` at `0x140025688`
- `vdsutil!VdsHeapFree` at `0x140025700`
- `vdsutil!VdsHeapFree` at `0x1400257a7`
- `vdsutil!VdsHeapFree` at `0x140025838`
- `vdsutil!VdsHeapFree` at `0x14002585a`
- `vdsutil!VdsHeapFree` at `0x14002590f`
- `vdsutil!VdsHeapFree` at `0x14002536b`
- `vdsutil!VdsHeapFree` at `0x14002538e`
- `vdsutil!VdsHeapFree` at `0x1400253af`
- `vdsutil!VdsHeapFree` at `0x1400253d0`
- `vdsutil!VdsHeapFree` at `0x140025632`
- `vdsutil!VdsHeapFree` at `0x140025688`
- `vdsutil!VdsHeapFree` at `0x140025700`
- `vdsutil!VdsHeapFree` at `0x1400257a7`
- `vdsutil!VdsHeapFree` at `0x140025838`
- `vdsutil!VdsHeapFree` at `0x14002585a`
- `vdsutil!VdsHeapFree` at `0x14002590f`
- `vdsutil!VdsTraceEx` at `0x1400254f7`
- `vdsutil!VdsTraceEx` at `0x14002559c`
- `vdsutil!VdsTraceEx` at `0x1400255d5`
- `vdsutil!VdsTraceEx` at `0x1400259a3`
- `vdsutil!VdsTraceEx` at `0x1400259f7`
- `vdsutil!VdsTraceEx` at `0x1400254f7`
- `vdsutil!VdsTraceEx` at `0x14002559c`
- `vdsutil!VdsTraceEx` at `0x1400255d5`
- `vdsutil!VdsTraceEx` at `0x1400259a3`
- `vdsutil!VdsTraceEx` at `0x1400259f7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002517a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002517a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140025a33`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140025a33`
- `vdsutil!VdsTraceW` at `0x1400251fb`
- `vdsutil!VdsTraceW` at `0x140025296`
- `vdsutil!VdsTraceW` at `0x1400252d4`
- `vdsutil!VdsTraceW` at `0x14002532c`
- `vdsutil!VdsTraceW` at `0x14002534d`
- `vdsutil!VdsTraceW` at `0x140025409`
- `vdsutil!VdsTraceW` at `0x140025439`
- `vdsutil!VdsTraceW` at `0x14002545d`
- `vdsutil!VdsTraceW` at `0x140025494`
- `vdsutil!VdsTraceW` at `0x140025614`
- `vdsutil!VdsTraceW` at `0x14002565d`
- `vdsutil!VdsTraceW` at `0x1400256c1`
- `vdsutil!VdsTraceW` at `0x1400256e2`
- `vdsutil!VdsTraceW` at `0x14002572a`
- `vdsutil!VdsTraceW` at `0x140025769`
- `vdsutil!VdsTraceW` at `0x14002578c`
- `vdsutil!VdsTraceW` at `0x1400257f9`
- `vdsutil!VdsTraceW` at `0x140025893`
- `vdsutil!VdsTraceW` at `0x140025957`
- `vdsutil!VdsTraceW` at `0x1400251fb`
- `vdsutil!VdsTraceW` at `0x140025296`
- `vdsutil!VdsTraceW` at `0x1400252d4`
- `vdsutil!VdsTraceW` at `0x14002532c`
- `vdsutil!VdsTraceW` at `0x14002534d`
- `vdsutil!VdsTraceW` at `0x140025409`
- `vdsutil!VdsTraceW` at `0x140025439`
- `vdsutil!VdsTraceW` at `0x14002545d`
- `vdsutil!VdsTraceW` at `0x140025494`
- `vdsutil!VdsTraceW` at `0x140025614`
- `vdsutil!VdsTraceW` at `0x14002565d`
- `vdsutil!VdsTraceW` at `0x1400256c1`
- `vdsutil!VdsTraceW` at `0x1400256e2`
- `vdsutil!VdsTraceW` at `0x14002572a`
- `vdsutil!VdsTraceW` at `0x140025769`
- `vdsutil!VdsTraceW` at `0x14002578c`
- `vdsutil!VdsTraceW` at `0x1400257f9`
- `vdsutil!VdsTraceW` at `0x140025893`
- `vdsutil!VdsTraceW` at `0x140025957`

## string_xrefs

- `0x1400251f0`: `CVdsRawDiskLun::Initialize(), 0, path=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsRawDiskLun::Initialize(CVdsRawDiskLun *this, unsigned __int16 *a2, struct _GUID *a3)
{
  unsigned int v6; // r14d
  const wchar_t *v7; // r8
  __int64 v8; // rax
  HRESULT Guid; // eax
  unsigned int v10; // ebx
  char *v11; // rsi
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int DeviceNumber; // eax
  __int64 v15; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  __int64 v21; // rbx
  HANDLE v22; // rax
  unsigned int DeviceManufacturerInfo; // eax
  unsigned int DeviceAndMediaType; // eax
  unsigned int MediaGeometry; // eax
  unsigned int StorageAccessAlignmentProperty; // eax
  unsigned int v27; // eax
  unsigned int v28; // ebx
  unsigned __int16 *v29; // rax
  int v30; // eax
  int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rbx
  HANDLE v34; // rax
  unsigned int DeviceId; // eax
  __int64 v36; // rbx
  HANDLE v37; // rax
  unsigned int DeviceRegistryPropertyByInfo; // eax
  __int64 EmptyString; // rax
  __int64 *v40; // rdi
  __int64 v41; // rbx
  HANDLE v42; // rax
  CONFIGRET Parent; // eax
  __int64 v44; // rax
  unsigned int DeviceRegistryPropertyByInst; // eax
  __int64 v46; // rax
  __int64 v47; // rbx
  HANDLE v48; // rax
  __int64 v49; // rbx
  HANDLE v50; // rax
  unsigned __int16 *v51; // rax
  unsigned __int16 *v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rbx
  HANDLE v55; // rax
  __int64 v56; // rbx
  HANDLE v57; // rax
  unsigned int DeviceLocation; // eax
  const unsigned __int16 *v59; // r8
  int v60; // edi
  __int64 v61; // rbx
  HANDLE v62; // rax
  unsigned __int64 v63; // rax
  unsigned __int64 v64; // rdi
  __int64 v65; // rbx
  HANDLE v66; // rax
  unsigned __int16 *v67; // rax
  int HaveArcPath; // eax
  int BootFromDiskNumber; // eax
  __int64 v70; // r9
  char v72; // [rsp+40h] [rbp-C0h] BYREF
  char v73; // [rsp+41h] [rbp-BFh] BYREF
  char v74; // [rsp+42h] [rbp-BEh] BYREF
  char v75; // [rsp+43h] [rbp-BDh] BYREF
  char v76; // [rsp+44h] [rbp-BCh] BYREF
  char v77; // [rsp+45h] [rbp-BBh] BYREF
  _BYTE v78[2]; // [rsp+46h] [rbp-BAh] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  int Value; // [rsp+50h] [rbp-B0h]
  DEVNODE pdnDevInst; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v84[16]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v85[2]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v86[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v87; // [rsp+A8h] [rbp-58h]
  _OWORD v88[2]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR String[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v90; // [rsp+E8h] [rbp-18h]
  _BYTE v91[28]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t Buffer[64]; // [rsp+120h] [rbp+20h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v84, 0x5Eu, "CVdsRawDiskLun::Initialize()");
  v82 = 0;
  hObject = 0;
  pdnDevInst = 0;
  v6 = 999999;
  Value = 999999;
  v83 = 999999;
  v76 = 0;
  v73 = 0;
  v74 = 0;
  v72 = 0;
  v78[0] = 0;
  v77 = 0;
  v75 = 0;
  memset(v86, 0, sizeof(v86));
  v87 = 0;
  memset(v85, 0, 12);
  v7 = a2;
  if ( !a2 )
    v7 = L"UNKNOWN";
  VdsTraceW(2, L"CVdsRawDiskLun::Initialize(), 0, path=%s", v7);
  memset(v86, 0, sizeof(v86));
  v87 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  LODWORD(v85[0]) = 0;
  *(_QWORD *)((char *)v85 + 4) = 999999;
  *(_OWORD *)String = 0;
  v90 = 0;
  memset(v91, 0, sizeof(v91));
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v8 || (Guid = CoCreateGuid(a3), v10 = Guid, Guid >= 0) )
  {
    v11 = (char *)this + 120;
    *(struct _GUID *)((char *)this + 120) = *a3;
    v12 = OpenDevice(a2, 0x80000000LL, &hObject);
    v13 = v12;
    if ( v12 )
    {
      VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 2, error=%ld", v12);
      if ( v13 != 2 )
        VdsLogError(0xC2000008, 0, 0, v13, 0x20D0002u, a2, 0);
    }
    else
    {
      DeviceNumber = GetDeviceNumber(hObject, v85);
      if ( DeviceNumber )
      {
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 3, error=%ld", DeviceNumber);
      }
      else
      {
        v6 = HIDWORD(v85[0]);
        Value = HIDWORD(v85[0]);
      }
      VdsTraceW(2, L"CVdsRawDiskLun::Initialize(), 3b, Disk Number=%ld", v6);
      v15 = *((_QWORD *)this + 35);
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v15);
      *((_QWORD *)this + 35) = 0;
      v17 = *((_QWORD *)this + 36);
      v18 = GetProcessHeap();
      VdsHeapFree(v18, 0, v17);
      *((_QWORD *)this + 36) = 0;
      v19 = *((_QWORD *)this + 37);
      v20 = GetProcessHeap();
      VdsHeapFree(v20, 0, v19);
      *((_QWORD *)this + 37) = 0;
      v21 = *((_QWORD *)this + 38);
      v22 = GetProcessHeap();
      VdsHeapFree(v22, 0, v21);
      *((_QWORD *)this + 38) = 0;
      DeviceManufacturerInfo = GetDeviceManufacturerInfo(
                                 hObject,
                                 (char *)this + 280,
                                 (char *)this + 288,
                                 (char *)this + 296,
                                 (char *)this + 304);
      if ( DeviceManufacturerInfo )
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 3c, error=%ld", DeviceManufacturerInfo);
      v11 = (char *)this + 120;
      DeviceAndMediaType = GetDeviceAndMediaType(a2, hObject, (char *)this + 152, (char *)this + 156);
      if ( DeviceAndMediaType )
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 4, error=%ld", DeviceAndMediaType);
      MediaGeometry = GetMediaGeometryEx(hObject, (char *)this + 120);
      if ( MediaGeometry )
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 5, error=%ld", MediaGeometry);
      memset(v88, 0, 28);
      StorageAccessAlignmentProperty = GetStorageAccessAlignmentProperty(hObject, v88);
      if ( StorageAccessAlignmentProperty )
      {
        *((_QWORD *)this + 39) = 0;
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 5b, error=%ld", StorageAccessAlignmentProperty);
      }
      else
      {
        *((_QWORD *)this + 39) = *(_QWORD *)&v88[1];
      }
      if ( *((_DWORD *)this + 38) == 7 )
      {
        v27 = IsDiskClustered(hObject, &v72, v78, &v77, &v73);
        v28 = v27;
        if ( v27 )
        {
          VdsTraceEx(94, 0, "CVdsRawDiskLun::Initialize, 6a, error=%ld", v27);
          memset_0(Buffer, 0, sizeof(Buffer));
          v29 = _ltow(Value, Buffer, 10);
          VdsLogError(0xC2000015, 0, 0, v28, 0x20D0005u, v29, 0);
        }
        if ( v72 )
          *((_DWORD *)this + 45) |= 0x20u;
        *((_DWORD *)this + 37) = 1;
        *((_DWORD *)this + 34) = v73 != 0 ? 1 : 4;
      }
      v30 = IsDiskReadOnly(hObject, &v74);
      if ( v30 )
      {
        VdsTraceEx(95, 0, "CVdsRawDiskLun::Initialize, 6b, error=%ld", v30);
      }
      else if ( v74 )
      {
        *((_DWORD *)this + 45) |= 0x40u;
      }
      v31 = IsDiskCurrentStateReadOnly(hObject, &v75);
      if ( v31 )
      {
        VdsTraceEx(95, 0, "CVdsRawDiskLun::Initialize, 7, error=%ld", v31);
      }
      else if ( v75 )
      {
        *((_DWORD *)this + 45) |= 0x8000u;
      }
      v6 = Value;
    }
    v32 = CreateDeviceInfoSet(a2, &v82, v86);
    if ( v32 )
      VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 8, error=%ld", v32);
    v33 = *((_QWORD *)this + 34);
    v34 = GetProcessHeap();
    VdsHeapFree(v34, 0, v33);
    *((_QWORD *)this + 34) = 0;
    DeviceId = GetDeviceId(v82, v86, (char *)this + 272);
    if ( DeviceId )
      VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 8b, error=%ld", DeviceId);
    *((_OWORD *)this + 16) = *(_OWORD *)((char *)v86 + 4);
    v36 = *((_QWORD *)this + 28);
    v37 = GetProcessHeap();
    VdsHeapFree(v37, 0, v36);
    *((_QWORD *)this + 28) = 0;
    DeviceRegistryPropertyByInfo = GetDeviceRegistryPropertyByInfo(v82, v86, 12, (char *)this + 224, 0);
    if ( DeviceRegistryPropertyByInfo )
    {
      VdsTraceW(1, L"CVdsRawDiskLun::Initialize(), 9, error=%ld", DeviceRegistryPropertyByInfo);
      EmptyString = VdsAllocateEmptyString();
      *((_QWORD *)this + 28) = EmptyString;
      if ( !EmptyString )
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 9b, error=%ld", 8);
    }
    v40 = (__int64 *)((char *)this + 232);
    v41 = *((_QWORD *)this + 29);
    v42 = GetProcessHeap();
    VdsHeapFree(v42, 0, v41);
    *((_QWORD *)this + 29) = 0;
    Parent = CM_Get_Parent(&pdnDevInst, DWORD1(v86[1]), 0);
    if ( Parent )
    {
      VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 10, error=%ld", Parent);
      v44 = VdsAllocateEmptyString();
      *v40 = v44;
      if ( !v44 )
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 11, error=%ld", 8);
    }
    else
    {
      DeviceRegistryPropertyByInst = GetDeviceRegistryPropertyByInst(pdnDevInst, 0, (char *)this + 232, 0);
      if ( DeviceRegistryPropertyByInst )
      {
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 12, error=%ld", DeviceRegistryPropertyByInst);
        v46 = VdsAllocateEmptyString();
        *v40 = v46;
        if ( !v46 )
          VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 12b, error=%ld", 8);
      }
    }
    v47 = *((_QWORD *)this + 30);
    v48 = GetProcessHeap();
    VdsHeapFree(v48, 0, v47);
    *((_QWORD *)this + 30) = 0;
    v49 = -1;
    do
      ++v49;
    while ( a2[v49] );
    v50 = GetProcessHeap();
    v51 = (unsigned __int16 *)VdsHeapAlloc(v50, 8, 2 * v49 + 2);
    v52 = v51;
    if ( v51 )
    {
      v53 = -1;
      do
        ++v53;
      while ( a2[v53] );
      StringCchCopyW(v51, v53 + 1, a2);
    }
    else
    {
      VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 13, error=%ld", 8);
    }
    *((_QWORD *)this + 30) = v52;
    v54 = *((_QWORD *)this + 26);
    v55 = GetProcessHeap();
    VdsHeapFree(v55, 0, v54);
    *((_QWORD *)this + 26) = 0;
    v56 = *((_QWORD *)this + 31);
    v57 = GetProcessHeap();
    VdsHeapFree(v57, 0, v56);
    *((_QWORD *)this + 31) = 0;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      DeviceLocation = GetDeviceLocationEx(hObject, pdnDevInst, v11);
      if ( DeviceLocation )
        VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 13.5, error=%ld", DeviceLocation);
    }
    DevObjDestroyDeviceInfoList(v82);
    v82 = 0;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    v59 = L"\\\\?\\PhysicalDrive%d";
    if ( *((_DWORD *)this + 38) != 7 )
      v59 = L"\\\\?\\CdRom%d";
    StringCchPrintfW(String, 0x1Eu, v59, v6);
    v60 = lstrlenW(String);
    v61 = *((_QWORD *)this + 27);
    v62 = GetProcessHeap();
    VdsHeapFree(v62, 0, v61);
    *((_QWORD *)this + 27) = 0;
    v63 = (unsigned int)(v60 + 1);
    v64 = v63;
    v65 = 2 * v63;
    v66 = GetProcessHeap();
    v67 = (unsigned __int16 *)VdsHeapAlloc(v66, 8, v65);
    *((_QWORD *)this + 27) = v67;
    if ( v67 )
      StringCchCopyW(v67, v64, String);
    else
      VdsTraceW(1, L"CVdsRawDiskLun::Initialize(), 14, error=%ld", 8);
    *((_DWORD *)this + 80) = v6;
    if ( *((_DWORD *)this + 38) == 7 )
    {
      HaveArcPath = VdsDoesDiskHaveArcPath(v6, &v76);
      if ( HaveArcPath )
        VdsTraceEx(94, 1, "CVdsRawDiskLun::Initialize, 15, error=%ld", HaveArcPath);
      if ( v76 )
        *((_DWORD *)this + 45) |= 0x1000u;
      BootFromDiskNumber = GetBootFromDiskNumber(&v83);
      if ( BootFromDiskNumber >= 0 )
      {
        v70 = *((unsigned int *)this + 80);
        if ( (_DWORD)v70 == v83 )
        {
          *((_DWORD *)this + 45) |= 0x4000u;
          VdsTraceEx(94, 0, "CVdsRawDiskLun::Initialize, BOOT FROM DISK:%lu", v70);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsRawDiskLun::Initialize, 25.25, hr=%lX", (unsigned int)BootFromDiskNumber);
      }
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    if ( v82 )
      DevObjDestroyDeviceInfoList(v82);
    v10 = 0;
  }
  else
  {
    VdsLogError(0xC2000001, 0, 0, Guid, 0x20D0001u, 0);
    VdsTraceW(0, L"CVdsRawDiskLun::Initialize(), 1, hr=%lX", v10);
    v10 = (unsigned __int16)v10;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v84);
  return v10;
}

```

## disassembly

```asm
0x140025130  mov     [rsp-8+arg_18], rbx
0x140025135  push    rbp
0x140025136  push    rsi
0x140025137  push    rdi
0x140025138  push    r12
0x14002513a  push    r13
0x14002513c  push    r14
0x14002513e  push    r15
0x140025140  lea     rbp, [rsp-0B0h]
0x140025148  sub     rsp, 1B0h
0x14002514f  mov     rax, cs:__security_cookie
0x140025156  xor     rax, rsp
0x140025159  mov     [rbp+0E0h+var_40], rax
0x140025160  mov     rdi, r8
0x140025163  mov     r12, rdx
0x140025166  mov     r13, rcx
0x140025169  lea     r8, aCvdsrawdisklun_97; "CVdsRawDiskLun::Initialize()"
0x140025170  mov     edx, 5Eh ; '^'
0x140025175  lea     rcx, [rsp+1E0h+var_178]
0x14002517a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140025180  nop
0x140025181  xor     r15d, r15d
0x140025184  mov     [rsp+1E0h+var_188], r15
0x140025189  mov     [rsp+1E0h+hObject], r15
0x14002518e  mov     [rsp+1E0h+pdnDevInst], r15d
0x140025193  mov     r14d, 0F423Fh
0x140025199  mov     [rsp+1E0h+Value], r14d
0x14002519e  mov     [rsp+1E0h+var_180], r14d
0x1400251a3  mov     [rsp+1E0h+var_19C], r15b
0x1400251a8  mov     [rsp+1E0h+var_19F], r15b
0x1400251ad  mov     [rsp+1E0h+var_19E], r15b
0x1400251b2  mov     [rsp+1E0h+var_1A0], r15b
0x1400251b7  mov     [rsp+1E0h+var_19A], r15b
0x1400251bc  mov     [rsp+1E0h+var_19B], r15b
0x1400251c1  mov     [rsp+1E0h+var_19D], r15b
0x1400251c6  xorps   xmm0, xmm0
0x1400251c9  movups  [rbp+0E0h+var_158], xmm0
0x1400251cd  movups  xmmword ptr [rbp+0E0h+dnDevInst], xmm0
0x1400251d1  movups  [rbp+0E0h+var_138], xmm0
0x1400251d5  xor     eax, eax
0x1400251d7  mov     [rsp+1E0h+var_168], rax
0x1400251dc  mov     [rbp+0E0h+var_160], eax
0x1400251df  lea     rax, aUnknown_0; "UNKNOWN"
0x1400251e6  mov     r8, r12
0x1400251e9  test    r12, r12
0x1400251ec  cmovz   r8, rax
0x1400251f0  lea     rdx, aCvdsrawdisklun_9; "CVdsRawDiskLun::Initialize(), 0, path=%"...
0x1400251f7  lea     ecx, [r15+2]
0x1400251fb  call    cs:__imp_VdsTraceW
0x140025201  xorps   xmm0, xmm0
0x140025204  movups  [rbp+0E0h+var_158], xmm0
0x140025208  movups  xmmword ptr [rbp+0E0h+dnDevInst], xmm0
0x14002520c  movups  [rbp+0E0h+var_138], xmm0
0x140025210  xor     edx, edx; Val
0x140025212  mov     r8d, 80h; Size
0x140025218  lea     rcx, [rbp+0E0h+Buffer]; void *
0x14002521c  call    memset_0
0x140025221  xor     eax, eax
0x140025223  mov     [rsp+1E0h+var_168], rax
0x140025228  mov     [rsp+1E0h+var_168+4], r14
0x14002522d  xorps   xmm0, xmm0
0x140025230  movups  xmmword ptr [rbp+0E0h+String], xmm0
0x140025234  movups  [rbp+0E0h+var_F8], xmm0
0x140025238  movups  xmmword ptr [rbp+0E0h+var_E8], xmm0
0x14002523c  movups  xmmword ptr [rbp+0E0h+var_E8+0Ch], xmm0
0x140025240  mov     rax, [rdi]
0x140025243  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14002524a  jnz     short loc_140025257
0x14002524c  mov     rax, [rdi+8]
0x140025250  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140025257  test    rax, rax
0x14002525a  jnz     short loc_1400252A4
0x14002525c  mov     rcx, rdi; pguid
0x14002525f  call    cs:__imp_CoCreateGuid
0x140025265  mov     ebx, eax
0x140025267  test    eax, eax
0x140025269  jns     short loc_1400252A4
0x14002526b  mov     [rsp+1E0h+var_1B8], r15; unsigned __int16 *
0x140025270  mov     [rsp+1E0h+var_1C0], 20D0001h; unsigned int
0x140025278  mov     r9d, eax; unsigned int
0x14002527b  xor     r8d, r8d; void *
0x14002527e  xor     edx, edx; unsigned int
0x140025280  mov     ecx, 0C2000001h; unsigned int
0x140025285  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14002528a  mov     r8d, ebx
0x14002528d  lea     rdx, aCvdsrawdisklun_93; "CVdsRawDiskLun::Initialize(), 1, hr=%lX"
0x140025294  xor     ecx, ecx
0x140025296  call    cs:__imp_VdsTraceW
0x14002529c  movzx   ebx, bx
0x14002529f  jmp     loc_140025A2E
0x1400252a4  lea     rsi, [r13+78h]
0x1400252a8  movups  xmm0, xmmword ptr [rdi]
0x1400252ab  movdqu  xmmword ptr [rsi], xmm0
0x1400252af  lea     r8, [rsp+1E0h+hObject]
0x1400252b4  mov     edx, 80000000h
0x1400252b9  mov     rcx, r12
0x1400252bc  call    cs:__imp_OpenDevice
0x1400252c2  mov     ebx, eax
0x1400252c4  test    eax, eax
0x1400252c6  jz      short loc_14002530C
0x1400252c8  mov     r8d, eax
0x1400252cb  lea     rdx, aCvdsrawdisklun_73; "CVdsRawDiskLun::Initialize(), 2, error="...
0x1400252d2  xor     ecx, ecx
0x1400252d4  call    cs:__imp_VdsTraceW
0x1400252da  cmp     ebx, 2
0x1400252dd  jz      loc_1400255F2
0x1400252e3  mov     [rsp+1E0h+var_1B0], r15
0x1400252e8  mov     [rsp+1E0h+var_1B8], r12; unsigned __int16 *
0x1400252ed  mov     [rsp+1E0h+var_1C0], 20D0002h; unsigned int
0x1400252f5  mov     r9d, ebx; unsigned int
0x1400252f8  xor     r8d, r8d; void *
0x1400252fb  xor     edx, edx; unsigned int
0x1400252fd  mov     ecx, 0C2000008h; unsigned int
0x140025302  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140025307  jmp     loc_1400255F2
0x14002530c  lea     rdx, [rsp+1E0h+var_168]
0x140025311  mov     rcx, [rsp+1E0h+hObject]
0x140025316  call    cs:__imp_GetDeviceNumber
0x14002531c  test    eax, eax
0x14002531e  jz      short loc_140025334
0x140025320  mov     r8d, eax
0x140025323  lea     rdx, aCvdsrawdisklun_2; "CVdsRawDiskLun::Initialize(), 3, error="...
0x14002532a  xor     ecx, ecx
0x14002532c  call    cs:__imp_VdsTraceW
0x140025332  jmp     short loc_14002533E
0x140025334  mov     r14d, dword ptr [rsp+1E0h+var_168+4]
0x140025339  mov     [rsp+1E0h+Value], r14d
0x14002533e  mov     r8d, r14d
0x140025341  lea     rdx, aCvdsrawdisklun_12; "CVdsRawDiskLun::Initialize(), 3b, Disk "...
0x140025348  mov     ecx, 2
0x14002534d  call    cs:__imp_VdsTraceW
0x140025353  lea     r15, [r13+118h]
0x14002535a  mov     rbx, [r15]
0x14002535d  call    cs:__imp_GetProcessHeap
0x140025363  mov     r8, rbx
0x140025366  xor     edx, edx
0x140025368  mov     rcx, rax
0x14002536b  call    cs:__imp_VdsHeapFree
0x140025371  xor     edi, edi
0x140025373  mov     [r15], rdi
0x140025376  lea     r14, [r13+120h]
0x14002537d  mov     rbx, [r14]
0x140025380  call    cs:__imp_GetProcessHeap
0x140025386  mov     r8, rbx
0x140025389  xor     edx, edx
0x14002538b  mov     rcx, rax
0x14002538e  call    cs:__imp_VdsHeapFree
0x140025394  mov     [r14], rdi
0x140025397  lea     rsi, [r13+128h]
0x14002539e  mov     rbx, [rsi]
0x1400253a1  call    cs:__imp_GetProcessHeap
0x1400253a7  mov     r8, rbx
0x1400253aa  xor     edx, edx
0x1400253ac  mov     rcx, rax
0x1400253af  call    cs:__imp_VdsHeapFree
0x1400253b5  mov     [rsi], rdi
0x1400253b8  lea     rdi, [r13+130h]
0x1400253bf  mov     rbx, [rdi]
0x1400253c2  call    cs:__imp_GetProcessHeap
0x1400253c8  mov     r8, rbx
0x1400253cb  xor     edx, edx
0x1400253cd  mov     rcx, rax
0x1400253d0  call    cs:__imp_VdsHeapFree
0x1400253d6  mov     qword ptr [rdi], 0
0x1400253dd  mov     qword ptr [rsp+1E0h+var_1C0], rdi
0x1400253e2  mov     r9, rsi
0x1400253e5  mov     r8, r14
0x1400253e8  mov     rdx, r15
0x1400253eb  mov     rcx, [rsp+1E0h+hObject]
0x1400253f0  call    cs:__imp_GetDeviceManufacturerInfo
0x1400253f6  xor     r15d, r15d
0x1400253f9  test    eax, eax
0x1400253fb  jz      short loc_14002540F
0x1400253fd  mov     r8d, eax
0x140025400  lea     rdx, aCvdsrawdisklun_54; "CVdsRawDiskLun::Initialize(), 3c, error"...
0x140025407  xor     ecx, ecx
0x140025409  call    cs:__imp_VdsTraceW
0x14002540f  lea     rsi, [r13+78h]
0x140025413  lea     r9, [rsi+24h]
0x140025417  lea     r8, [rsi+20h]
0x14002541b  mov     rdx, [rsp+1E0h+hObject]
0x140025420  mov     rcx, r12
0x140025423  call    cs:__imp_GetDeviceAndMediaType
0x140025429  test    eax, eax
0x14002542b  jz      short loc_14002543F
0x14002542d  mov     r8d, eax
0x140025430  lea     rdx, aCvdsrawdisklun_56; "CVdsRawDiskLun::Initialize(), 4, error="...
0x140025437  xor     ecx, ecx
0x140025439  call    cs:__imp_VdsTraceW
0x14002543f  mov     rdx, rsi
0x140025442  mov     rcx, [rsp+1E0h+hObject]
0x140025447  call    cs:__imp_GetMediaGeometryEx
0x14002544d  test    eax, eax
0x14002544f  jz      short loc_140025463
0x140025451  mov     r8d, eax
0x140025454  lea     rdx, aCvdsrawdisklun_75; "CVdsRawDiskLun::Initialize(), 5, error="...
0x14002545b  xor     ecx, ecx
0x14002545d  call    cs:__imp_VdsTraceW
0x140025463  xorps   xmm0, xmm0
0x140025466  movups  [rbp+0E0h+var_128], xmm0
0x14002546a  movups  [rbp+0E0h+var_128+0Ch], xmm0
0x14002546e  lea     rdx, [rbp+0E0h+var_128]
0x140025472  mov     rcx, [rsp+1E0h+hObject]
0x140025477  call    cs:__imp_GetStorageAccessAlignmentProperty
0x14002547d  test    eax, eax
0x14002547f  jz      short loc_14002549C
0x140025481  mov     [r13+138h], r15
0x140025488  mov     r8d, eax
0x14002548b  lea     rdx, aCvdsrawdisklun_19; "CVdsRawDiskLun::Initialize(), 5b, error"...
0x140025492  xor     ecx, ecx
0x140025494  call    cs:__imp_VdsTraceW
0x14002549a  jmp     short loc_1400254B0
0x14002549c  mov     eax, [rbp+0E0h+var_118]
0x14002549f  mov     [r13+138h], eax
0x1400254a6  mov     eax, [rbp+0E0h+var_114]
0x1400254a9  mov     [r13+13Ch], eax
0x1400254b0  cmp     dword ptr [r13+98h], 7
0x1400254b8  jnz     loc_140025575
0x1400254be  lea     rax, [rsp+1E0h+var_19F]
0x1400254c3  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x1400254c8  lea     r9, [rsp+1E0h+var_19B]
0x1400254cd  lea     r8, [rsp+1E0h+var_19A]
0x1400254d2  lea     rdx, [rsp+1E0h+var_1A0]
0x1400254d7  mov     rcx, [rsp+1E0h+hObject]
0x1400254dc  call    cs:__imp_IsDiskClustered
0x1400254e2  mov     ebx, eax
0x1400254e4  test    eax, eax
0x1400254e6  jz      short loc_140025546
0x1400254e8  mov     r9d, eax
0x1400254eb  lea     r8, aCvdsrawdisklun_49; "CVdsRawDiskLun::Initialize, 6a, error=%"...
0x1400254f2  xor     edx, edx
0x1400254f4  lea     ecx, [rdx+5Eh]
0x1400254f7  call    cs:__imp_VdsTraceEx
0x1400254fd  xor     edx, edx; Val
0x1400254ff  mov     r8d, 80h; Size
0x140025505  lea     rcx, [rbp+0E0h+Buffer]; void *
0x140025509  call    memset_0
0x14002550e  mov     r8d, 0Ah; Radix
0x140025514  lea     rdx, [rbp+0E0h+Buffer]; Buffer
0x140025518  mov     ecx, [rsp+1E0h+Value]; Value
0x14002551c  call    cs:__imp__ltow
0x140025522  mov     [rsp+1E0h+var_1B0], r15
0x140025527  mov     [rsp+1E0h+var_1B8], rax; unsigned __int16 *
0x14002552c  mov     [rsp+1E0h+var_1C0], 20D0005h; unsigned int
0x140025534  mov     r9d, ebx; unsigned int
0x140025537  xor     r8d, r8d; void *
0x14002553a  xor     edx, edx; unsigned int
0x14002553c  mov     ecx, 0C2000015h; unsigned int
0x140025541  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140025546  cmp     [rsp+1E0h+var_1A0], r15b
0x14002554b  jz      short loc_140025555
0x14002554d  or      dword ptr [r13+0B4h], 20h
0x140025555  mov     dword ptr [r13+94h], 1
0x140025560  mov     al, [rsp+1E0h+var_19F]
0x140025564  neg     al
0x140025566  sbb     ecx, ecx
0x140025568  and     ecx, 0FFFFFFFDh
0x14002556b  add     ecx, 4
0x14002556e  mov     [r13+88h], ecx
0x140025575  lea     rdx, [rsp+1E0h+var_19E]
0x14002557a  mov     rcx, [rsp+1E0h+hObject]
0x14002557f  call    cs:__imp_IsDiskReadOnly
0x140025585  mov     ebx, 5Fh ; '_'
0x14002558a  test    eax, eax
0x14002558c  jz      short loc_1400255A4
0x14002558e  mov     r9d, eax
0x140025591  lea     r8, aCvdsrawdisklun_27; "CVdsRawDiskLun::Initialize, 6b, error=%"...
0x140025598  xor     edx, edx
0x14002559a  mov     ecx, ebx
0x14002559c  call    cs:__imp_VdsTraceEx
0x1400255a2  jmp     short loc_1400255B3
0x1400255a4  cmp     [rsp+1E0h+var_19E], r15b
0x1400255a9  jz      short loc_1400255B3
0x1400255ab  or      dword ptr [r13+0B4h], 40h
0x1400255b3  lea     rdx, [rsp+1E0h+var_19D]
0x1400255b8  mov     rcx, [rsp+1E0h+hObject]
0x1400255bd  call    cs:__imp_IsDiskCurrentStateReadOnly
0x1400255c3  test    eax, eax
0x1400255c5  jz      short loc_1400255DD
0x1400255c7  mov     r9d, eax
0x1400255ca  lea     r8, aCvdsrawdisklun_60; "CVdsRawDiskLun::Initialize, 7, error=%l"...
0x1400255d1  xor     edx, edx
0x1400255d3  mov     ecx, ebx
0x1400255d5  call    cs:__imp_VdsTraceEx
0x1400255db  jmp     short loc_1400255ED
0x1400255dd  cmp     [rsp+1E0h+var_19D], r15b
0x1400255e2  jz      short loc_1400255ED
0x1400255e4  bts     dword ptr [r13+0B4h], 0Fh
0x1400255ed  mov     r14d, [rsp+1E0h+Value]
0x1400255f2  lea     r8, [rbp+0E0h+var_158]
0x1400255f6  lea     rdx, [rsp+1E0h+var_188]
0x1400255fb  mov     rcx, r12
0x1400255fe  call    cs:__imp_CreateDeviceInfoSet
0x140025604  test    eax, eax
0x140025606  jz      short loc_14002561A
0x140025608  mov     r8d, eax
0x14002560b  lea     rdx, aCvdsrawdisklun_96; "CVdsRawDiskLun::Initialize(), 8, error="...
0x140025612  xor     ecx, ecx
0x140025614  call    cs:__imp_VdsTraceW
0x14002561a  lea     rdi, [r13+110h]
  ... truncated ...
```
