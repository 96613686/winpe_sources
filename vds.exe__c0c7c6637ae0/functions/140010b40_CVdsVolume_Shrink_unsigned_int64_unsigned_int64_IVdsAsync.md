# CVdsVolume::Shrink(unsigned __int64,unsigned __int64,IVdsAsync * *)

- ea: `0x140010b40`
- end: `0x1400113e5`
- name: `?Shrink@CVdsVolume@@UEAAJ_K0PEAPEAUIVdsAsync@@@Z`
- size: `2213`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned __int64, unsigned __int64, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `18`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x140009990`
- `0x14000f930`
- `0x14000f98c`
- `0x14000f9b0`
- `0x140010b04`
- `0x140010b40`
- `0x140011a60`
- `0x140012c70`
- `0x140012c9c`
- `0x140013298`
- `0x14002e123`
- `0x140040b54`
- `0x140040d6c`
- `0x140042b30`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140010f58`
- `msvcrt!_wcsnicmp` at `0x140010f79`
- `msvcrt!_wcsnicmp` at `0x140010fa6`
- `msvcrt!_wcsnicmp` at `0x14001123f`
- `msvcrt!_wcsnicmp` at `0x140011260`
- `msvcrt!_wcsnicmp` at `0x140010f58`
- `msvcrt!_wcsnicmp` at `0x140010f79`
- `msvcrt!_wcsnicmp` at `0x140010fa6`
- `msvcrt!_wcsnicmp` at `0x14001123f`
- `msvcrt!_wcsnicmp` at `0x140011260`
- `ntdll!NtQueryVolumeInformationFile` at `0x140010eb1`
- `ntdll!NtQueryVolumeInformationFile` at `0x140010eb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010e2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010e2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011054`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010fe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011054`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400112e4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400112ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400112ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011076`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011003`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011076`
- `vdsutil!GetFileSystemRecognitionName` at `0x140010fbe`
- `vdsutil!GetFileSystemRecognitionName` at `0x140010fbe`
- `vdsutil!VdsHeapAlloc` at `0x1400111c6`
- `vdsutil!VdsHeapAlloc` at `0x1400111c6`
- `vdsutil!VdsHeapFree` at `0x140010ff3`
- `vdsutil!VdsHeapFree` at `0x140011062`
- `vdsutil!VdsHeapFree` at `0x140010ff3`
- `vdsutil!VdsHeapFree` at `0x140011062`
- `vdsutil!VdsTraceEx` at `0x140010e4a`
- `vdsutil!VdsTraceEx` at `0x140010ed0`
- `vdsutil!VdsTraceEx` at `0x14001109c`
- `vdsutil!VdsTraceEx` at `0x140010e4a`
- `vdsutil!VdsTraceEx` at `0x140010ed0`
- `vdsutil!VdsTraceEx` at `0x14001109c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140010bdf`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140010bdf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010c12`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010c54`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010c9b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010d02`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010d8a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010de6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010e6c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010f14`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001101a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400110b3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001111f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140011187`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400111f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001131b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001137e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010c12`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010c54`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010c9b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010d02`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010d8a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010de6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010e6c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140010f14`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001101a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400110b3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001111f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140011187`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400111f3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001131b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001137e`
- `vdsutil!VdsTraceW` at `0x140010ceb`
- `vdsutil!VdsTraceW` at `0x140010d73`
- `vdsutil!VdsTraceW` at `0x140010dcf`
- `vdsutil!VdsTraceW` at `0x140010fda`
- `vdsutil!VdsTraceW` at `0x140011108`
- `vdsutil!VdsTraceW` at `0x140011170`
- `vdsutil!VdsTraceW` at `0x1400112f8`
- `vdsutil!VdsTraceW` at `0x140010ceb`
- `vdsutil!VdsTraceW` at `0x140010d73`
- `vdsutil!VdsTraceW` at `0x140010dcf`
- `vdsutil!VdsTraceW` at `0x140010fda`
- `vdsutil!VdsTraceW` at `0x140011108`
- `vdsutil!VdsTraceW` at `0x140011170`
- `vdsutil!VdsTraceW` at `0x1400112f8`

## string_xrefs

- `0x140010d67`: `CVdsVolume::Shrink, 2, path=%s, hr=%lX`
- `0x140010dc6`: `CVdsVolume::Shrink, 3, path=%s, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CVdsVolume::Shrink(
        CVdsVolume *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        struct IVdsAsync **a4)
{
  char v7; // di
  __int64 v8; // rdx
  struct IVdsAsync **LastError; // rbx
  char *v10; // r14
  CVdsVolume *v11; // rcx
  LPWSTR pwszName; // r8
  NTSTATUS v13; // eax
  unsigned int v14; // ebx
  bool v15; // si
  HANDLE ProcessHeap; // rax
  struct IVdsAsync **v17; // rbx
  HANDLE v18; // rax
  int v19; // eax
  int v20; // eax
  HANDLE v21; // rax
  __int64 v22; // rax
  _DWORD *v23; // rbx
  int v24; // eax
  struct IVdsAsync *v25; // rdi
  HANDLE v26; // rax
  LPVOID lpParameter; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  void *v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h]
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v34[16]; // [rsp+60h] [rbp-A0h] BYREF
  struct IVdsAsync **v35; // [rsp+70h] [rbp-90h] BYREF
  struct IVdsAsync *v36; // [rsp+78h] [rbp-88h] BYREF
  DWORD ThreadId; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  struct IVdsAsync **v39; // [rsp+90h] [rbp-70h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  _VDS_VOLUME_PROP v41; // [rsp+A8h] [rbp-58h] BYREF
  char FsInformation[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v43; // [rsp+E8h] [rbp-18h]
  wchar_t String1[34]; // [rsp+ECh] [rbp-14h] BYREF

  LastError = a4;
  v39 = a4;
  v7 = 0;
  hObject = 0;
  memset(&v41, 0, sizeof(v41));
  memset_0(FsInformation, 0, 0x50u);
  IoStatusBlock = 0;
  v38 = 0;
  v36 = 0;
  lpParameter = 0;
  v30 = 0;
  ThreadId = 0;
  v29 = 0;
  v35 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v34, 0x5Eu, "CVdsVolume::Shrink()");
  *LastError = 0;
  v31 = 0;
  v32 = 0;
  LODWORD(LastError) = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v31);
  if ( (int)LastError < 0 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  if ( !a2 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    LODWORD(LastError) = -2147211917;
    goto LABEL_54;
  }
  if ( a2 < a3 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    LODWORD(LastError) = -2147024809;
    goto LABEL_54;
  }
  v10 = (char *)this - 16;
  if ( !*((_QWORD *)this + 14) )
  {
    LODWORD(LastError) = -2147211946;
    VdsTraceW(0, L"CVdsVolume::Shrink,  1, hr=%lX", 2147755350LL);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  LODWORD(LastError) = CVdsVolume::OpenHandle((CVdsVolume *)((char *)this - 16), v8, &hObject, &v41);
  if ( (int)LastError < 0 )
  {
    pwszName = L"UNKNOWN";
    if ( (_DWORD)LastError == -2147212270 )
    {
      if ( v41.pwszName )
        pwszName = v41.pwszName;
      VdsTraceW(3, L"CVdsVolume::Shrink, 2, path=%s, hr=%lX", pwszName);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
      CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
      LODWORD(LastError) = -2147211942;
    }
    else
    {
      if ( v41.pwszName )
        pwszName = v41.pwszName;
      VdsTraceW(0, L"CVdsVolume::Shrink, 3, path=%s, hr=%lX", pwszName, (unsigned int)LastError);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
      CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    }
    goto LABEL_54;
  }
  LODWORD(LastError) = CVdsVolume::CheckFVEStatus(v11, v41.pwszName, 1);
  if ( v41.pwszName )
  {
    CoTaskMemFree(v41.pwszName);
    v41.pwszName = 0;
  }
  if ( (int)LastError < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Shrink, 4, hr=%lX", (_DWORD)LastError);
    CloseHandle(hObject);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  v13 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, FsInformation, 0x50u, FileFsAttributeInformation);
  v14 = v13;
  if ( v13 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Shrink 5, status=%lX", v13);
    VdsLogError(0xC2000001, 0, 0, v14, 0x20A001Bu, 0);
    CloseHandle(hObject);
    LODWORD(LastError) = v14 | 0x10000000;
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  v15 = v43 == 8 && !_wcsnicmp(String1, L"NTFS", 4u) || v43 == 10 && !_wcsnicmp(String1, L"CSVFS", 5u);
  if ( v43 == 6 && !_wcsnicmp(String1, L"RAW", 3u) )
  {
    if ( (int)GetFileSystemRecognitionName(hObject, &v35) >= 0 )
    {
      VdsTraceW(0, L"CVdsVolume::Shrink, 5.1: Unknown file system, do not support shrink. File system name=%s", v35);
      LastError = v35;
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, LastError);
      v35 = 0;
      CloseHandle(hObject);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
      ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
      CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
      LODWORD(LastError) = -2147210966;
      goto LABEL_54;
    }
    v7 = 1;
    v17 = v35;
    v18 = GetProcessHeap();
    VdsHeapFree(v18, 0, v17);
    v35 = 0;
  }
  CloseHandle(hObject);
  if ( !v15 && !v7 )
  {
    LODWORD(LastError) = -2147212002;
    VdsTraceEx(94, 0, "CVdsVolume::Shrink 6, hr=%lX", -2147212002);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  v19 = CVolumeLock::Lock((CVolumeLock *)&v38, (unsigned __int16 *)(*((_QWORD *)this + 17) + 2LL));
  LODWORD(LastError) = v19;
  if ( v19 < 0 )
  {
    VdsTraceW(0, L"CVdsVolume::Shrink 7, hr=%lX", (unsigned int)v19);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  v20 = CVdsVolume::CreateAsynchObj(3, 0, 0, &v36);
  LODWORD(LastError) = v20;
  if ( v20 < 0 )
  {
    VdsTraceW(0, L"CVdsVolume::Shrink 8, hr=%lX", (unsigned int)v20);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    goto LABEL_54;
  }
  v21 = GetProcessHeap();
  v22 = VdsHeapAlloc(v21, 8, 48);
  CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&lpParameter, v22);
  v23 = lpParameter;
  if ( !lpParameter )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    LODWORD(LastError) = -2147024882;
    goto LABEL_54;
  }
  *((_DWORD *)lpParameter + 8) = 0;
  v24 = v43;
  if ( v43 == 8 )
  {
    if ( !_wcsnicmp(String1, L"NTFS", 4u) )
    {
LABEL_48:
      v23[8] = 1;
      goto LABEL_49;
    }
    v24 = v43;
  }
  if ( v24 == 10 && !_wcsnicmp(String1, L"CSVFS", 5u) )
    goto LABEL_48;
LABEL_49:
  *(_QWORD *)v23 = a2;
  *((_QWORD *)v23 + 1) = a3;
  *((_QWORD *)v23 + 2) = v10;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this - 16);
  ATL::CComPtrBase<CVdsEnumObject>::Attach(&v29, (__int64)this - 16);
  v25 = v36;
  *((_QWORD *)v23 + 3) = v36;
  *((_QWORD *)v23 + 5) = *((_QWORD *)this + 17);
  HIDWORD(v25[14].lpVtbl) = 0;
  v26 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CVdsVolume::ShrinkRoutine, v23, 0, &ThreadId);
  CVdsHandleImpl<0>::operator=(&v30, v26);
  if ( v30 )
  {
    v29 = 0;
    lpParameter = 0;
    v36 = 0;
    *v39 = v25;
    ((void (__fastcall *)(struct IVdsAsync *))v25->lpVtbl->AddRef)(v25);
    v38 = 0;
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
    LODWORD(LastError) = 0;
  }
  else
  {
    LastError = (struct IVdsAsync **)GetLastError();
    VdsTraceW(0, L"CVdsVolume::Shrink 9, error=%ld", LastError);
    if ( (int)LastError > 0 )
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
    ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v29);
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v30);
    CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpParameter);
  }
LABEL_54:
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>((__int64 *)&v36);
  CVolumeLock::~CVolumeLock((CVolumeLock *)&v38);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140010b40  mov     [rsp-8+arg_8], rbx
0x140010b45  push    rbp
0x140010b46  push    rsi
0x140010b47  push    rdi
0x140010b48  push    r12
0x140010b4a  push    r13
0x140010b4c  push    r14
0x140010b4e  push    r15
0x140010b50  lea     rbp, [rsp-40h]
0x140010b55  sub     rsp, 140h
0x140010b5c  mov     rax, cs:__security_cookie
0x140010b63  xor     rax, rsp
0x140010b66  mov     [rbp+70h+var_40], rax
0x140010b6a  mov     rbx, r9
0x140010b6d  mov     [rbp+70h+var_E0], rbx
0x140010b71  mov     r12, r8
0x140010b74  mov     r15, rdx
0x140010b77  mov     r13, rcx
0x140010b7a  xor     edi, edi
0x140010b7c  mov     [rsp+170h+hObject], rdi
0x140010b81  mov     [rbp+70h+var_C8.id.Data1], edi
0x140010b84  xorps   xmm0, xmm0
0x140010b87  xor     eax, eax
0x140010b89  movups  xmmword ptr [rbp+70h+var_C8.id.Data2], xmm0
0x140010b8d  movups  xmmword ptr [rbp+70h+var_C8.status], xmm0
0x140010b91  movups  xmmword ptr [rbp+70h+var_C8.ullSize+4], xmm0
0x140010b95  mov     dword ptr [rbp+70h+var_C8.pwszName+4], eax
0x140010b98  lea     esi, [rdi+50h]
0x140010b9b  mov     r8d, esi; Size
0x140010b9e  xor     edx, edx; Val
0x140010ba0  lea     rcx, [rbp+70h+FsInformation]; void *
0x140010ba4  call    memset_0
0x140010ba9  xorps   xmm0, xmm0
0x140010bac  movups  xmmword ptr [rbp+70h+IoStatusBlock], xmm0
0x140010bb0  mov     [rbp+70h+var_E8], rdi
0x140010bb4  mov     [rsp+170h+var_F8], rdi
0x140010bb9  mov     [rsp+170h+lpParameter], rdi
0x140010bbe  mov     [rsp+170h+var_130], rdi
0x140010bc3  mov     [rbp+70h+ThreadId], edi
0x140010bc6  mov     [rsp+170h+var_138], rdi
0x140010bcb  mov     [rsp+170h+var_100], rdi
0x140010bd0  lea     r8, aCvdsvolumeShri_10; "CVdsVolume::Shrink()"
0x140010bd7  lea     edx, [rdi+5Eh]
0x140010bda  lea     rcx, [rsp+170h+var_110]
0x140010bdf  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140010be5  nop
0x140010be6  mov     [rbx], rdi
0x140010be9  mov     [rsp+170h+var_128], rdi
0x140010bee  mov     [rsp+170h+var_120], edi
0x140010bf2  lea     rcx, [rsp+170h+var_128]; this
0x140010bf7  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140010bfc  mov     ebx, eax
0x140010bfe  test    eax, eax
0x140010c00  jns     short loc_140010C3F
0x140010c02  lea     rcx, [rsp+170h+var_128]; this
0x140010c07  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010c0c  nop
0x140010c0d  lea     rcx, [rsp+170h+var_110]
0x140010c12  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010c18  nop
0x140010c19  lea     rcx, [rsp+170h+var_138]
0x140010c1e  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010c23  nop
0x140010c24  lea     rcx, [rsp+170h+var_130]
0x140010c29  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010c2e  nop
0x140010c2f  lea     rcx, [rsp+170h+lpParameter]
0x140010c34  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010c39  nop
0x140010c3a  jmp     loc_1400113A8
0x140010c3f  test    r15, r15
0x140010c42  jnz     short loc_140010C86
0x140010c44  lea     rcx, [rsp+170h+var_128]; this
0x140010c49  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010c4e  nop
0x140010c4f  lea     rcx, [rsp+170h+var_110]
0x140010c54  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010c5a  nop
0x140010c5b  lea     rcx, [rsp+170h+var_138]
0x140010c60  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010c65  nop
0x140010c66  lea     rcx, [rsp+170h+var_130]
0x140010c6b  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010c70  nop
0x140010c71  lea     rcx, [rsp+170h+lpParameter]
0x140010c76  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010c7b  nop
0x140010c7c  mov     ebx, 80042573h
0x140010c81  jmp     loc_1400113A8
0x140010c86  cmp     r15, r12
0x140010c89  jnb     short loc_140010CCD
0x140010c8b  lea     rcx, [rsp+170h+var_128]; this
0x140010c90  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010c95  nop
0x140010c96  lea     rcx, [rsp+170h+var_110]
0x140010c9b  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010ca1  nop
0x140010ca2  lea     rcx, [rsp+170h+var_138]
0x140010ca7  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010cac  nop
0x140010cad  lea     rcx, [rsp+170h+var_130]
0x140010cb2  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010cb7  nop
0x140010cb8  lea     rcx, [rsp+170h+lpParameter]
0x140010cbd  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010cc2  nop
0x140010cc3  mov     ebx, 80070057h
0x140010cc8  jmp     loc_1400113A8
0x140010ccd  lea     r14, [r13-10h]
0x140010cd1  cmp     [r14+80h], rdi
0x140010cd8  jnz     short loc_140010D2F
0x140010cda  mov     ebx, 80042556h
0x140010cdf  mov     r8d, ebx
0x140010ce2  lea     rdx, aCvdsvolumeShri_4; "CVdsVolume::Shrink,  1, hr=%lX"
0x140010ce9  xor     ecx, ecx
0x140010ceb  call    cs:__imp_VdsTraceW
0x140010cf1  nop
0x140010cf2  lea     rcx, [rsp+170h+var_128]; this
0x140010cf7  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010cfc  nop
0x140010cfd  lea     rcx, [rsp+170h+var_110]
0x140010d02  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010d08  nop
0x140010d09  lea     rcx, [rsp+170h+var_138]
0x140010d0e  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010d13  nop
0x140010d14  lea     rcx, [rsp+170h+var_130]
0x140010d19  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010d1e  nop
0x140010d1f  lea     rcx, [rsp+170h+lpParameter]
0x140010d24  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010d29  nop
0x140010d2a  jmp     loc_1400113A8
0x140010d2f  lea     r9, [rbp+70h+var_C8]; struct _VDS_VOLUME_PROP *
0x140010d33  lea     r8, [rsp+170h+hObject]; void **
0x140010d38  mov     rcx, r14; this
0x140010d3b  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x140010d40  mov     ebx, eax
0x140010d42  test    eax, eax
0x140010d44  jns     loc_140010E13
0x140010d4a  mov     r9d, 80042412h
0x140010d50  lea     r8, aUnknown_0; "UNKNOWN"
0x140010d57  mov     rax, [rbp+70h+var_C8.pwszName]
0x140010d5b  cmp     ebx, r9d
0x140010d5e  jnz     short loc_140010DBC
0x140010d60  test    rax, rax
0x140010d63  cmovnz  r8, rax
0x140010d67  lea     rdx, aCvdsvolumeShri_16; "CVdsVolume::Shrink, 2, path=%s, hr=%lX"
0x140010d6e  mov     ecx, 3
0x140010d73  call    cs:__imp_VdsTraceW
0x140010d79  nop
0x140010d7a  lea     rcx, [rsp+170h+var_128]; this
0x140010d7f  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010d84  nop
0x140010d85  lea     rcx, [rsp+170h+var_110]
0x140010d8a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010d90  nop
0x140010d91  lea     rcx, [rsp+170h+var_138]
0x140010d96  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010d9b  nop
0x140010d9c  lea     rcx, [rsp+170h+var_130]
0x140010da1  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010da6  nop
0x140010da7  lea     rcx, [rsp+170h+lpParameter]
0x140010dac  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010db1  nop
0x140010db2  mov     ebx, 8004255Ah
0x140010db7  jmp     loc_1400113A8
0x140010dbc  test    rax, rax
0x140010dbf  cmovnz  r8, rax
0x140010dc3  mov     r9d, ebx
0x140010dc6  lea     rdx, aCvdsvolumeShri_17; "CVdsVolume::Shrink, 3, path=%s, hr=%lX"
0x140010dcd  xor     ecx, ecx
0x140010dcf  call    cs:__imp_VdsTraceW
0x140010dd5  nop
0x140010dd6  lea     rcx, [rsp+170h+var_128]; this
0x140010ddb  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010de0  nop
0x140010de1  lea     rcx, [rsp+170h+var_110]
0x140010de6  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010dec  nop
0x140010ded  lea     rcx, [rsp+170h+var_138]
0x140010df2  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010df7  nop
0x140010df8  lea     rcx, [rsp+170h+var_130]
0x140010dfd  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010e02  nop
0x140010e03  lea     rcx, [rsp+170h+lpParameter]
0x140010e08  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010e0d  nop
0x140010e0e  jmp     loc_1400113A8
0x140010e13  mov     r8d, 1; int
0x140010e19  mov     rdx, [rbp+70h+var_C8.pwszName]; unsigned __int16 *
0x140010e1d  call    ?CheckFVEStatus@CVdsVolume@@AEAAJQEAGH@Z; CVdsVolume::CheckFVEStatus(ushort * const,int)
0x140010e22  mov     ebx, eax
0x140010e24  mov     rcx, [rbp+70h+var_C8.pwszName]; pv
0x140010e28  test    rcx, rcx
0x140010e2b  jz      short loc_140010E37
0x140010e2d  call    cs:__imp_CoTaskMemFree
0x140010e33  mov     [rbp+70h+var_C8.pwszName], rdi
0x140010e37  test    ebx, ebx
0x140010e39  jns     short loc_140010E99
0x140010e3b  mov     r9d, ebx
0x140010e3e  lea     r8, aCvdsvolumeShri_19; "CVdsVolume::Shrink, 4, hr=%lX"
0x140010e45  xor     edx, edx
0x140010e47  lea     ecx, [rdx+5Eh]
0x140010e4a  call    cs:__imp_VdsTraceEx
0x140010e50  mov     rcx, [rsp+170h+hObject]; hObject
0x140010e55  call    cs:__imp_CloseHandle
0x140010e5b  nop
0x140010e5c  lea     rcx, [rsp+170h+var_128]; this
0x140010e61  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010e66  nop
0x140010e67  lea     rcx, [rsp+170h+var_110]
0x140010e6c  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010e72  nop
0x140010e73  lea     rcx, [rsp+170h+var_138]
0x140010e78  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010e7d  nop
0x140010e7e  lea     rcx, [rsp+170h+var_130]
0x140010e83  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010e88  nop
0x140010e89  lea     rcx, [rsp+170h+lpParameter]
0x140010e8e  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010e93  nop
0x140010e94  jmp     loc_1400113A8
0x140010e99  mov     [rsp+170h+FsInformationClass], 5; FsInformationClass
0x140010ea1  mov     r9d, esi; Length
0x140010ea4  lea     r8, [rbp+70h+FsInformation]; FsInformation
0x140010ea8  lea     rdx, [rbp+70h+IoStatusBlock]; IoStatusBlock
0x140010eac  mov     rcx, [rsp+170h+hObject]; FileHandle
0x140010eb1  call    cs:__imp_NtQueryVolumeInformationFile
0x140010eb7  mov     ebx, eax
0x140010eb9  test    eax, eax
0x140010ebb  jz      loc_140010F41
0x140010ec1  mov     r9d, eax
0x140010ec4  lea     r8, aCvdsvolumeShri_14; "CVdsVolume::Shrink 5, status=%lX"
0x140010ecb  xor     edx, edx
0x140010ecd  lea     ecx, [rdx+5Eh]
0x140010ed0  call    cs:__imp_VdsTraceEx
0x140010ed6  mov     [rsp+170h+lpThreadId], rdi; unsigned __int16 *
0x140010edb  mov     [rsp+170h+FsInformationClass], 20A001Bh; unsigned int
0x140010ee3  mov     r9d, ebx; unsigned int
0x140010ee6  xor     r8d, r8d; void *
0x140010ee9  xor     edx, edx; unsigned int
0x140010eeb  mov     ecx, 0C2000001h; unsigned int
0x140010ef0  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140010ef5  mov     rcx, [rsp+170h+hObject]; hObject
0x140010efa  call    cs:__imp_CloseHandle
0x140010f00  bts     ebx, 1Ch
0x140010f04  lea     rcx, [rsp+170h+var_128]; this
0x140010f09  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140010f0e  nop
0x140010f0f  lea     rcx, [rsp+170h+var_110]
0x140010f14  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140010f1a  nop
0x140010f1b  lea     rcx, [rsp+170h+var_138]
0x140010f20  call    ??1?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(void)
0x140010f25  nop
0x140010f26  lea     rcx, [rsp+170h+var_130]
0x140010f2b  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x140010f30  nop
0x140010f31  lea     rcx, [rsp+170h+lpParameter]
0x140010f36  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140010f3b  nop
0x140010f3c  jmp     loc_1400113A8
0x140010f41  cmp     [rbp+70h+var_88], 8
0x140010f45  jnz     short loc_140010F62
0x140010f47  mov     r8d, 4; MaxCount
0x140010f4d  lea     rdx, aNtfs; "NTFS"
0x140010f54  lea     rcx, [rbp+70h+String1]; String1
0x140010f58  call    cs:__imp__wcsnicmp
0x140010f5e  test    eax, eax
0x140010f60  jz      short loc_140010F83
0x140010f62  cmp     [rbp+70h+var_88], 0Ah
0x140010f66  jnz     short loc_140010F88
0x140010f68  mov     r8d, 5; MaxCount
0x140010f6e  lea     rdx, aCsvfs; "CSVFS"
0x140010f75  lea     rcx, [rbp+70h+String1]; String1
0x140010f79  call    cs:__imp__wcsnicmp
0x140010f7f  test    eax, eax
0x140010f81  jnz     short loc_140010F88
0x140010f83  mov     sil, 1
0x140010f86  jmp     short loc_140010F8B
0x140010f88  mov     sil, dil
0x140010f8b  cmp     [rbp+70h+var_88], 6
0x140010f8f  jnz     loc_140011071
0x140010f95  mov     r8d, 3; MaxCount
0x140010f9b  lea     rdx, aRaw; "RAW"
0x140010fa2  lea     rcx, [rbp+70h+String1]; String1
0x140010fa6  call    cs:__imp__wcsnicmp
0x140010fac  test    eax, eax
0x140010fae  jnz     loc_140011071
0x140010fb4  lea     rdx, [rsp+170h+var_100]
0x140010fb9  mov     rcx, [rsp+170h+hObject]
0x140010fbe  call    cs:__imp_GetFileSystemRecognitionName
0x140010fc4  test    eax, eax
0x140010fc6  js      loc_14001104C
0x140010fcc  mov     r8, [rsp+170h+var_100]
0x140010fd1  lea     rdx, aCvdsvolumeShri_23; "CVdsVolume::Shrink, 5.1: Unknown file s"...
  ... truncated ...
```
