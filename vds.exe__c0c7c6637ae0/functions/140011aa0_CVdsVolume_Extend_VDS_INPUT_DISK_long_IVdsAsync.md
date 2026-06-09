# CVdsVolume::Extend(_VDS_INPUT_DISK *,long,IVdsAsync * *)

- ea: `0x140011aa0`
- end: `0x1400122c8`
- name: `?Extend@CVdsVolume@@UEAAJPEAU_VDS_INPUT_DISK@@JPEAPEAUIVdsAsync@@@Z`
- size: `2088`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, struct _VDS_INPUT_DISK *, int, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x140003710`
- `0x140004360`
- `0x140009990`
- `0x14000d1c0`
- `0x140011a60`
- `0x140011aa0`
- `0x140012c48`
- `0x140012c70`
- `0x140013298`
- `0x140028f84`
- `0x14002e123`
- `0x140035bd4`
- `0x140040b54`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140011c8d`
- `msvcrt!_wcsnicmp` at `0x140011cb4`
- `msvcrt!_wcsnicmp` at `0x140011cd8`
- `msvcrt!_wcsnicmp` at `0x140011cfc`
- `msvcrt!_wcsnicmp` at `0x140011e6d`
- `msvcrt!_wcsnicmp` at `0x140011e8e`
- `msvcrt!_wcsnicmp` at `0x140011c8d`
- `msvcrt!_wcsnicmp` at `0x140011cb4`
- `msvcrt!_wcsnicmp` at `0x140011cd8`
- `msvcrt!_wcsnicmp` at `0x140011cfc`
- `msvcrt!_wcsnicmp` at `0x140011e6d`
- `msvcrt!_wcsnicmp` at `0x140011e8e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400120f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400120f1`
- `ntdll!NtQueryVolumeInformationFile` at `0x140011c27`
- `ntdll!NtQueryVolumeInformationFile` at `0x140011ebb`
- `ntdll!NtQueryVolumeInformationFile` at `0x140011c27`
- `ntdll!NtQueryVolumeInformationFile` at `0x140011ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011bb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011d66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011d66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400120ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400121f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011e07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400120ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400121f4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400121d5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400121d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011bdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011f90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011bdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011f90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012058`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140011dfd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140011dfd`
- `vdsutil!GetFileSystemRecognitionName` at `0x140011d1b`
- `vdsutil!GetFileSystemRecognitionName` at `0x140011d1b`
- `vdsutil!VdsHeapAlloc` at `0x14001216a`
- `vdsutil!VdsHeapAlloc` at `0x14001216a`
- `vdsutil!VdsHeapFree` at `0x140011d4c`
- `vdsutil!VdsHeapFree` at `0x140011d74`
- `vdsutil!VdsHeapFree` at `0x14001226e`
- `vdsutil!VdsHeapFree` at `0x140011d4c`
- `vdsutil!VdsHeapFree` at `0x140011d74`
- `vdsutil!VdsHeapFree` at `0x14001226e`
- `vdsutil!VdsTraceEx` at `0x140011b88`
- `vdsutil!VdsTraceEx` at `0x140011bd2`
- `vdsutil!VdsTraceEx` at `0x140011c41`
- `vdsutil!VdsTraceEx` at `0x140011dab`
- `vdsutil!VdsTraceEx` at `0x140011e1e`
- `vdsutil!VdsTraceEx` at `0x140011ed6`
- `vdsutil!VdsTraceEx` at `0x140011f53`
- `vdsutil!VdsTraceEx` at `0x140012116`
- `vdsutil!VdsTraceEx` at `0x14001220b`
- `vdsutil!VdsTraceEx` at `0x140011b88`
- `vdsutil!VdsTraceEx` at `0x140011bd2`
- `vdsutil!VdsTraceEx` at `0x140011c41`
- `vdsutil!VdsTraceEx` at `0x140011dab`
- `vdsutil!VdsTraceEx` at `0x140011e1e`
- `vdsutil!VdsTraceEx` at `0x140011ed6`
- `vdsutil!VdsTraceEx` at `0x140011f53`
- `vdsutil!VdsTraceEx` at `0x140012116`
- `vdsutil!VdsTraceEx` at `0x14001220b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140011af2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140011af2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001207e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400122bb`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001207e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400122bb`
- `vdsutil!VdsTraceW` at `0x140011d33`
- `vdsutil!VdsTraceW` at `0x140011d33`

## string_xrefs

- `0x14001210a`: `CVdsVolume::Extend, 4: CreateEvent failed: %ld`
- `0x1400121ff`: `CVdsVolume::Extend, 5: CreateThread failed: %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CVdsVolume::Extend(
        struct IUnknown *this,
        struct _VDS_INPUT_DISK *a2,
        DWORD a3,
        struct IVdsAsync **a4)
{
  struct IUnknown *v5; // r13
  struct IVdsAsyncVtbl *EventW; // rsi
  __int64 v7; // rdx
  signed int LastError; // ebx
  CVdsVolume *v9; // rcx
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  HANDLE v12; // rcx
  char v13; // r12
  char v14; // di
  char v15; // r15
  char v16; // r14
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  char v21; // di
  NTSTATUS v22; // eax
  unsigned __int64 v23; // rdx
  __int64 v24; // r9
  DWORD v25; // ebx
  struct IVdsAsync *Instance; // rax
  CVdsServiceModule *v27; // rcx
  struct IVdsAsync *v28; // rdi
  signed int v29; // eax
  struct IUnknown *v31; // rdx
  HANDLE v32; // rax
  struct IVdsAsync **v33; // rax
  struct IVdsAsync **v34; // r14
  struct IUnknownVtbl *lpVtbl; // rcx
  HANDLE v36; // rax
  HANDLE v37; // rax
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v39; // [rsp+48h] [rbp-B8h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp-B0h] BYREF
  struct _VDS_INPUT_DISK *v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, struct IUnknown **); // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+78h] [rbp-88h]
  struct IVdsAsync **v46; // [rsp+80h] [rbp-80h]
  _BYTE v47[16]; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  struct _VDS_VOLUME_PROP v49; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v50; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v51; // [rsp+F0h] [rbp-10h]
  char FsInformation[8]; // [rsp+100h] [rbp+0h] BYREF
  int v53; // [rsp+108h] [rbp+8h]
  wchar_t String1[34]; // [rsp+10Ch] [rbp+Ch] BYREF

  v46 = a4;
  ThreadId = a3;
  v41 = a2;
  v5 = this;
  v39 = this;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v47, 0x5Eu, "CVdsVolume::Extend()");
  EventW = 0;
  v43 = 0;
  memset(&v49, 0, sizeof(v49));
  v50 = 0;
  v51 = 0;
  v42 = 0;
  *a4 = 0;
  v44 = 0;
  v45 = 0;
  LastError = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v44);
  if ( LastError < 0 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v44);
LABEL_74:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v43);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v47);
    return (unsigned int)LastError;
  }
  hObject = 0;
  LastError = CVdsVolume::OpenHandle((CVdsVolume *)v5, v7, &hObject, &v49);
  if ( LastError < 0 )
  {
    if ( LastError == -2147212270 )
      LastError = -2147211942;
    VdsTraceEx(94, 0, "CVdsVolume::Extend 1: hr=%lX", LastError);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v44);
    goto LABEL_74;
  }
  LastError = CVdsVolume::CheckFVEStatus(v9, v49.pwszName, 0);
  if ( v49.pwszName )
  {
    CoTaskMemFree(v49.pwszName);
    v49.pwszName = 0;
  }
  if ( LastError < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Extend 2: hr=%lX", LastError);
    CloseHandle(hObject);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v44);
    goto LABEL_74;
  }
  memset_0(FsInformation, 0, 0x50u);
  IoStatusBlock = 0;
  v10 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, FsInformation, 0x50u, FileFsAttributeInformation);
  v11 = v10;
  if ( v10 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Extend, 3: NtQueryVolumeInformationFile failed: %lX", v10);
    VdsLogError(0xC2000001, 0, 0, v11, 0x20A0011u, 0);
LABEL_13:
    LastError = v11 | 0x10000000;
LABEL_14:
    v12 = hObject;
LABEL_72:
    CloseHandle(v12);
    goto LABEL_73;
  }
  if ( v53 != 8 || (v13 = 1, _wcsnicmp(String1, L"NTFS", 4u)) )
    v13 = 0;
  if ( v53 != 6 || (v14 = 1, _wcsnicmp(String1, L"RAW", 3u)) )
    v14 = 0;
  if ( v53 != 10 || (v15 = 1, _wcsnicmp(String1, L"CSVFS", 5u)) )
    v15 = 0;
  if ( v53 != 8 || (v16 = 1, _wcsnicmp(String1, L"REFS", 4u)) )
    v16 = 0;
  if ( v14 )
  {
    if ( (int)GetFileSystemRecognitionName(hObject, &v42) >= 0 )
    {
      VdsTraceW(0, L"CVdsVolume::Extend, 3.0: Unknown file system, do not support Extend. File system name=%s", v42);
      v17 = v42;
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v17);
      v42 = 0;
      LastError = -2147210967;
      goto LABEL_14;
    }
    v19 = v42;
    v20 = GetProcessHeap();
    VdsHeapFree(v20, 0, v19);
    v42 = 0;
  }
  if ( !v13 )
  {
    if ( !v14 && !v15 )
    {
      if ( !v16 )
      {
        VdsTraceEx(
          94,
          1,
          "CVdsVolume::Extend, 3.1: File systems other than NTFS, RAW, REFS and CSVFS do not support Extend");
        LastError = -2147212274;
        goto LABEL_14;
      }
      goto LABEL_48;
    }
    if ( !v16 && !v15 )
    {
      v25 = ThreadId;
      goto LABEL_64;
    }
  }
  if ( !v15 )
    goto LABEL_48;
  if ( !DeviceIoControl(hObject, 0x902C0u, 0, 0, FsInformation, 0x50u, 0, 0) )
  {
    LastError = GetLastError();
    VdsTraceEx(
      94,
      0,
      "CVdsVolume::Extend, 3.15: DeviceIoControl(FSCTL_CSV_QUERY_DOWN_LEVEL_FILE_SYSTEM_CHARACTERISTICS) failed: %lX",
      LastError);
    VdsLogError(0xC2000001, 0, 0, LastError, 0x20A0017u, 0);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_14;
  }
  if ( v53 != 8 )
    goto LABEL_48;
  if ( !_wcsnicmp(String1, L"NTFS", 4u) )
    LOBYTE(EventW) = 1;
  if ( v53 != 8 || _wcsnicmp(String1, L"REFS", 4u) )
  {
LABEL_48:
    v21 = 0;
    goto LABEL_49;
  }
  v21 = 1;
LABEL_49:
  v22 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, &v50, 0x20u, FileFsFullSizeInformation);
  v11 = v22;
  if ( v22 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Extend, 3.2: NtQueryVolumeInformationFile failed: %lX", v22);
    VdsLogError(0xC2000001, 0, 0, v11, 0x20A001Du, 0);
    goto LABEL_13;
  }
  v23 = v50 * DWORD2(v51) * (unsigned __int64)HIDWORD(v51);
  v24 = 0;
  v25 = ThreadId;
  if ( (int)ThreadId > 0 )
  {
    do
    {
      v23 += v41[v24].ullSize;
      v24 = (unsigned int)(v24 + 1);
    }
    while ( (int)v24 < (int)ThreadId );
    v5 = v39;
  }
  if ( (v13 || (_BYTE)EventW) && v23 > 4294967294u * DWORD2(v51) * (unsigned __int64)HIDWORD(v51) )
  {
    VdsTraceEx(
      94,
      0,
      "CVdsVolume::Extend, 3.3: NTFS file system size cannot extend to more than 2^32 - 2 clusters",
      v24);
LABEL_58:
    LastError = -2147210968;
    goto LABEL_14;
  }
  EventW = 0;
  if ( (v16 || v21) && v23 > 0x7FFFFFFFFFFFFFFFLL )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Extend, 3.4: ReFS file system size cannot extend to more than 2^63 bytes", v24);
    goto LABEL_58;
  }
LABEL_64:
  CloseHandle(hObject);
  Instance = (struct IVdsAsync *)VdsCreateInstance(VDS_OT_ASYNC);
  v28 = Instance;
  if ( !Instance )
  {
    LastError = -2147024882;
    goto LABEL_73;
  }
  LODWORD(Instance[11].lpVtbl) = 2;
  CVdsServiceModule::StopAcceptingStop(v27);
  LastError = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, struct _VDS_INPUT_DISK *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **)))v5[16].lpVtbl->QueryInterface
               + 6))(
                v5[16].lpVtbl,
                v41,
                v25,
                &v43);
  if ( LastError < 0 )
  {
LABEL_70:
    ((void (__fastcall *)(struct IVdsAsync *))v28->lpVtbl->Release)(v28);
    if ( EventW )
    {
      v12 = EventW;
      goto LABEL_72;
    }
LABEL_73:
    CVdsServiceModule::ResumeAcceptingStop(v27);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v44);
    goto LABEL_74;
  }
  v39 = 0;
  v29 = (**v43)(v43, &IID_IUnknown, &v39);
  LastError = v29;
  if ( v29 < 0 )
  {
    VdsLogError(0xC2000009, 0, 0, v29, 0x20A001Eu, 0);
LABEL_69:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v39);
    goto LABEL_70;
  }
  v31 = v39;
  v39 = 0;
  CWrapperBase::SetObjectAndService((CWrapperBase *)&v28[8], v31, (struct CVdsService *)v5[15].lpVtbl);
  if ( v13 || v15 || v16 )
  {
    v41 = 0;
    ThreadId = 0;
    EventW = (struct IVdsAsyncVtbl *)CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      VdsTraceEx(94, 0, "CVdsVolume::Extend, 4: CreateEvent failed: %ld", LastError);
      VdsLogError(0xC2000001, 0, 0, LastError, 0x20A0012u, 0);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_83;
    }
    v32 = GetProcessHeap();
    v33 = (struct IVdsAsync **)VdsHeapAlloc(v32, 8, 16);
    v34 = v33;
    if ( !v33 )
    {
LABEL_83:
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>((void **)&v41);
      goto LABEL_69;
    }
    *v33 = v28;
    ((void (__fastcall *)(struct IVdsAsync *))v28->lpVtbl->AddRef)(v28);
    v28[12].lpVtbl = EventW;
    lpVtbl = v5[16].lpVtbl;
    v34[1] = (struct IVdsAsync *)lpVtbl;
    (*((void (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 1))(lpVtbl);
    v36 = CreateThread(0, 0, CVdsVolume::PostExtendVolumeHandler, v34, 0, &ThreadId);
    CVdsHandleImpl<0>::operator=(&v41, v36);
    if ( !v41 )
    {
      LastError = GetLastError();
      VdsTraceEx(94, 0, "CVdsVolume::Extend, 5: CreateThread failed: %ld", LastError);
      VdsLogError(0xC2000001, 0, 0, LastError, 0x20A0013u, 0);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ((void (__fastcall *)(struct IVdsAsync *))(*v34)->lpVtbl->Release)(*v34);
      ((void (__fastcall *)(struct IVdsAsync *))v34[1]->lpVtbl->Release)(v34[1]);
      v37 = GetProcessHeap();
      VdsHeapFree(v37, 0, v34);
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>((void **)&v41);
      goto LABEL_69;
    }
    CVdsHandleImpl<0>::~CVdsHandleImpl<0>((void **)&v41);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v39);
  *v46 = v28;
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v44);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v43);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v47);
  return 0;
}

```

## disassembly

```asm
0x140011aa0  push    rbp
0x140011aa2  push    rbx
0x140011aa3  push    rsi
0x140011aa4  push    rdi
0x140011aa5  push    r12
0x140011aa7  push    r13
0x140011aa9  push    r14
0x140011aab  push    r15
0x140011aad  lea     rbp, [rsp-68h]
0x140011ab2  sub     rsp, 168h
0x140011ab9  mov     rax, cs:__security_cookie
0x140011ac0  xor     rax, rsp
0x140011ac3  mov     [rbp+0A0h+var_50], rax
0x140011ac7  mov     rbx, r9
0x140011aca  mov     [rbp+0A0h+var_120], rbx
0x140011ace  mov     [rsp+1A0h+ThreadId], r8d
0x140011ad3  mov     [rsp+1A0h+var_148], rdx
0x140011ad8  mov     r13, rcx
0x140011adb  mov     [rsp+1A0h+var_158], rcx
0x140011ae0  lea     r8, aCvdsvolumeExte; "CVdsVolume::Extend()"
0x140011ae7  mov     edi, 5Eh ; '^'
0x140011aec  mov     edx, edi
0x140011aee  lea     rcx, [rbp+0A0h+var_118]
0x140011af2  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140011af8  nop
0x140011af9  xor     esi, esi
0x140011afb  mov     [rsp+1A0h+var_138], rsi
0x140011b00  mov     [rbp+0A0h+var_F8.id.Data1], esi
0x140011b03  xorps   xmm0, xmm0
0x140011b06  xor     eax, eax
0x140011b08  movups  xmmword ptr [rbp+0A0h+var_F8.id.Data2], xmm0
0x140011b0c  movups  xmmword ptr [rbp+0A0h+var_F8.status], xmm0
0x140011b10  movups  xmmword ptr [rbp+0A0h+var_F8.ullSize+4], xmm0
0x140011b14  mov     dword ptr [rbp+0A0h+var_F8.pwszName+4], eax
0x140011b17  movups  [rbp+0A0h+var_C0], xmm0
0x140011b1b  movups  [rbp+0A0h+var_B0], xmm0
0x140011b1f  mov     [rsp+1A0h+var_140], rsi
0x140011b24  mov     [rbx], rsi
0x140011b27  mov     [rsp+1A0h+var_130], rsi
0x140011b2c  mov     [rsp+1A0h+var_128], esi
0x140011b30  lea     rcx, [rsp+1A0h+var_130]; this
0x140011b35  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140011b3a  mov     ebx, eax
0x140011b3c  test    eax, eax
0x140011b3e  jns     short loc_140011B50
0x140011b40  lea     rcx, [rsp+1A0h+var_130]; this
0x140011b45  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140011b4a  nop
0x140011b4b  jmp     loc_14001206F
0x140011b50  mov     [rsp+1A0h+hObject], rsi
0x140011b55  lea     r9, [rbp+0A0h+var_F8]; struct _VDS_VOLUME_PROP *
0x140011b59  lea     r8, [rsp+1A0h+hObject]; void **
0x140011b5e  mov     rcx, r13; this
0x140011b61  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x140011b66  mov     ebx, eax
0x140011b68  test    eax, eax
0x140011b6a  jns     short loc_140011B9F
0x140011b6c  mov     eax, 8004255Ah
0x140011b71  cmp     ebx, 80042412h
0x140011b77  cmovz   ebx, eax
0x140011b7a  mov     r9d, ebx
0x140011b7d  lea     r8, aCvdsvolumeExte_2; "CVdsVolume::Extend 1: hr=%lX"
0x140011b84  xor     edx, edx
0x140011b86  mov     ecx, edi
0x140011b88  call    cs:__imp_VdsTraceEx
0x140011b8e  nop
0x140011b8f  lea     rcx, [rsp+1A0h+var_130]; this
0x140011b94  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140011b99  nop
0x140011b9a  jmp     loc_14001206F
0x140011b9f  xor     r8d, r8d; int
0x140011ba2  mov     rdx, [rbp+0A0h+var_F8.pwszName]; unsigned __int16 *
0x140011ba6  call    ?CheckFVEStatus@CVdsVolume@@AEAAJQEAGH@Z; CVdsVolume::CheckFVEStatus(ushort * const,int)
0x140011bab  mov     ebx, eax
0x140011bad  mov     rcx, [rbp+0A0h+var_F8.pwszName]; pv
0x140011bb1  test    rcx, rcx
0x140011bb4  jz      short loc_140011BC0
0x140011bb6  call    cs:__imp_CoTaskMemFree
0x140011bbc  mov     [rbp+0A0h+var_F8.pwszName], rsi
0x140011bc0  test    ebx, ebx
0x140011bc2  jns     short loc_140011BF4
0x140011bc4  mov     r9d, ebx
0x140011bc7  lea     r8, aCvdsvolumeExte_7; "CVdsVolume::Extend 2: hr=%lX"
0x140011bce  xor     edx, edx
0x140011bd0  mov     ecx, edi
0x140011bd2  call    cs:__imp_VdsTraceEx
0x140011bd8  mov     rcx, [rsp+1A0h+hObject]; hObject
0x140011bdd  call    cs:__imp_CloseHandle
0x140011be3  nop
0x140011be4  lea     rcx, [rsp+1A0h+var_130]; this
0x140011be9  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140011bee  nop
0x140011bef  jmp     loc_14001206F
0x140011bf4  mov     ebx, 50h ; 'P'
0x140011bf9  mov     r8d, ebx; Size
0x140011bfc  xor     edx, edx; Val
0x140011bfe  lea     rcx, [rbp+0A0h+FsInformation]; void *
0x140011c02  call    memset_0
0x140011c07  xorps   xmm0, xmm0
0x140011c0a  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x140011c0e  lea     r14d, [rbx-4Bh]
0x140011c12  mov     [rsp+1A0h+FsInformationClass], r14d; FsInformationClass
0x140011c17  mov     r9d, ebx; Length
0x140011c1a  lea     r8, [rbp+0A0h+FsInformation]; FsInformation
0x140011c1e  lea     rdx, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x140011c22  mov     rcx, [rsp+1A0h+hObject]; FileHandle
0x140011c27  call    cs:__imp_NtQueryVolumeInformationFile
0x140011c2d  mov     ebx, eax
0x140011c2f  test    eax, eax
0x140011c31  jz      short loc_140011C74
0x140011c33  mov     r9d, eax
0x140011c36  lea     r8, aCvdsvolumeExte_3; "CVdsVolume::Extend, 3: NtQueryVolumeInf"...
0x140011c3d  xor     edx, edx
0x140011c3f  mov     ecx, edi
0x140011c41  call    cs:__imp_VdsTraceEx
0x140011c47  mov     qword ptr [rsp+1A0h+nOutBufferSize], rsi; unsigned __int16 *
0x140011c4c  mov     [rsp+1A0h+FsInformationClass], 20A0011h; unsigned int
0x140011c54  mov     r9d, ebx; unsigned int
0x140011c57  xor     r8d, r8d; void *
0x140011c5a  xor     edx, edx; unsigned int
0x140011c5c  mov     ecx, 0C2000001h; unsigned int
0x140011c61  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140011c66  bts     ebx, 1Ch
0x140011c6a  mov     rcx, [rsp+1A0h+hObject]
0x140011c6f  jmp     loc_140012058
0x140011c74  mov     ebx, 4
0x140011c79  cmp     [rbp+0A0h+var_98], 8
0x140011c7d  jnz     short loc_140011C9A
0x140011c7f  mov     r8d, ebx; MaxCount
0x140011c82  lea     rdx, aNtfs; "NTFS"
0x140011c89  lea     rcx, [rbp+0A0h+String1]; String1
0x140011c8d  call    cs:__imp__wcsnicmp
0x140011c93  test    eax, eax
0x140011c95  mov     r12b, 1
0x140011c98  jz      short loc_140011C9D
0x140011c9a  mov     r12b, sil
0x140011c9d  cmp     [rbp+0A0h+var_98], 6
0x140011ca1  jnz     short loc_140011CC1
0x140011ca3  mov     r8d, 3; MaxCount
0x140011ca9  lea     rdx, aRaw; "RAW"
0x140011cb0  lea     rcx, [rbp+0A0h+String1]; String1
0x140011cb4  call    cs:__imp__wcsnicmp
0x140011cba  test    eax, eax
0x140011cbc  mov     dil, 1
0x140011cbf  jz      short loc_140011CC4
0x140011cc1  mov     dil, sil
0x140011cc4  cmp     [rbp+0A0h+var_98], 0Ah
0x140011cc8  jnz     short loc_140011CE5
0x140011cca  mov     r8, r14; MaxCount
0x140011ccd  lea     rdx, aCsvfs; "CSVFS"
0x140011cd4  lea     rcx, [rbp+0A0h+String1]; String1
0x140011cd8  call    cs:__imp__wcsnicmp
0x140011cde  test    eax, eax
0x140011ce0  mov     r15b, 1
0x140011ce3  jz      short loc_140011CE8
0x140011ce5  mov     r15b, sil
0x140011ce8  cmp     [rbp+0A0h+var_98], 8
0x140011cec  jnz     short loc_140011D09
0x140011cee  mov     r8, rbx; MaxCount
0x140011cf1  lea     rdx, aRefs; "REFS"
0x140011cf8  lea     rcx, [rbp+0A0h+String1]; String1
0x140011cfc  call    cs:__imp__wcsnicmp
0x140011d02  test    eax, eax
0x140011d04  mov     r14b, 1
0x140011d07  jz      short loc_140011D0C
0x140011d09  mov     r14b, sil
0x140011d0c  test    dil, dil
0x140011d0f  jz      short loc_140011D84
0x140011d11  lea     rdx, [rsp+1A0h+var_140]
0x140011d16  mov     rcx, [rsp+1A0h+hObject]
0x140011d1b  call    cs:__imp_GetFileSystemRecognitionName
0x140011d21  test    eax, eax
0x140011d23  js      short loc_140011D61
0x140011d25  mov     r8, [rsp+1A0h+var_140]
0x140011d2a  lea     rdx, aCvdsvolumeExte_1; "CVdsVolume::Extend, 3.0: Unknown file s"...
0x140011d31  xor     ecx, ecx
0x140011d33  call    cs:__imp_VdsTraceW
0x140011d39  mov     rbx, [rsp+1A0h+var_140]
0x140011d3e  call    cs:__imp_GetProcessHeap
0x140011d44  mov     r8, rbx
0x140011d47  xor     edx, edx
0x140011d49  mov     rcx, rax
0x140011d4c  call    cs:__imp_VdsHeapFree
0x140011d52  mov     [rsp+1A0h+var_140], rsi
0x140011d57  mov     ebx, 80042929h
0x140011d5c  jmp     loc_140011C6A
0x140011d61  mov     rbx, [rsp+1A0h+var_140]
0x140011d66  call    cs:__imp_GetProcessHeap
0x140011d6c  mov     r8, rbx
0x140011d6f  xor     edx, edx
0x140011d71  mov     rcx, rax
0x140011d74  call    cs:__imp_VdsHeapFree
0x140011d7a  mov     [rsp+1A0h+var_140], rsi
0x140011d7f  mov     ebx, 4
0x140011d84  test    r12b, r12b
0x140011d87  jnz     short loc_140011DC9
0x140011d89  test    dil, dil
0x140011d8c  jnz     short loc_140011DBB
0x140011d8e  test    r15b, r15b
0x140011d91  jnz     short loc_140011DBB
0x140011d93  test    r14b, r14b
0x140011d96  jnz     loc_140011E9D
0x140011d9c  lea     r8, aCvdsvolumeExte_9; "CVdsVolume::Extend, 3.1: File systems o"...
0x140011da3  mov     edx, 1
0x140011da8  lea     ecx, [rdx+5Dh]
0x140011dab  call    cs:__imp_VdsTraceEx
0x140011db1  mov     ebx, 8004240Eh
0x140011db6  jmp     loc_140011C6A
0x140011dbb  test    r14b, r14b
0x140011dbe  jnz     short loc_140011DC9
0x140011dc0  test    r15b, r15b
0x140011dc3  jz      loc_140011F87
0x140011dc9  test    r15b, r15b
0x140011dcc  jz      loc_140011E9D
0x140011dd2  mov     [rsp+1A0h+lpOverlapped], rsi; lpOverlapped
0x140011dd7  mov     [rsp+1A0h+lpBytesReturned], rsi; lpBytesReturned
0x140011ddc  mov     [rsp+1A0h+nOutBufferSize], 50h ; 'P'; nOutBufferSize
0x140011de4  lea     rax, [rbp+0A0h+FsInformation]
0x140011de8  mov     qword ptr [rsp+1A0h+FsInformationClass], rax; lpOutBuffer
0x140011ded  xor     r9d, r9d; nInBufferSize
0x140011df0  xor     r8d, r8d; lpInBuffer
0x140011df3  mov     edx, 902C0h; dwIoControlCode
0x140011df8  mov     rcx, [rsp+1A0h+hObject]; hDevice
0x140011dfd  call    cs:__imp_DeviceIoControl
0x140011e03  test    eax, eax
0x140011e05  jnz     short loc_140011E59
0x140011e07  call    cs:__imp_GetLastError
0x140011e0d  mov     ebx, eax
0x140011e0f  mov     r9d, eax
0x140011e12  lea     r8, aCvdsvolumeExte_5; "CVdsVolume::Extend, 3.15: DeviceIoContr"...
0x140011e19  xor     edx, edx
0x140011e1b  lea     ecx, [rdx+5Eh]
0x140011e1e  call    cs:__imp_VdsTraceEx
0x140011e24  mov     qword ptr [rsp+1A0h+nOutBufferSize], rsi; unsigned __int16 *
0x140011e29  mov     [rsp+1A0h+FsInformationClass], 20A0017h; unsigned int
0x140011e31  mov     r9d, ebx; unsigned int
0x140011e34  xor     r8d, r8d; void *
0x140011e37  xor     edx, edx; unsigned int
0x140011e39  mov     ecx, 0C2000001h; unsigned int
0x140011e3e  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140011e43  test    ebx, ebx
0x140011e45  jle     loc_140011C6A
0x140011e4b  movzx   ebx, bx
0x140011e4e  or      ebx, 80070000h
0x140011e54  jmp     loc_140011C6A
0x140011e59  cmp     [rbp+0A0h+var_98], 8
0x140011e5d  jnz     short loc_140011E9D
0x140011e5f  mov     r8, rbx; MaxCount
0x140011e62  lea     rdx, aNtfs; "NTFS"
0x140011e69  lea     rcx, [rbp+0A0h+String1]; String1
0x140011e6d  call    cs:__imp__wcsnicmp
0x140011e73  test    eax, eax
0x140011e75  jnz     short loc_140011E7A
0x140011e77  mov     sil, 1
0x140011e7a  cmp     [rbp+0A0h+var_98], 8
0x140011e7e  jnz     short loc_140011E9D
0x140011e80  mov     r8, rbx; MaxCount
0x140011e83  lea     rdx, aRefs; "REFS"
0x140011e8a  lea     rcx, [rbp+0A0h+String1]; String1
0x140011e8e  call    cs:__imp__wcsnicmp
0x140011e94  test    eax, eax
0x140011e96  jnz     short loc_140011E9D
0x140011e98  mov     dil, 1
0x140011e9b  jmp     short loc_140011EA0
0x140011e9d  xor     dil, dil
0x140011ea0  mov     [rsp+1A0h+FsInformationClass], 7; FsInformationClass
0x140011ea8  mov     r9d, 20h ; ' '; Length
0x140011eae  lea     r8, [rbp+0A0h+var_C0]; FsInformation
0x140011eb2  lea     rdx, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x140011eb6  mov     rcx, [rsp+1A0h+hObject]; FileHandle
0x140011ebb  call    cs:__imp_NtQueryVolumeInformationFile
0x140011ec1  mov     ebx, eax
0x140011ec3  test    eax, eax
0x140011ec5  jz      short loc_140011EF2
0x140011ec7  mov     r9d, eax
0x140011eca  lea     r8, aCvdsvolumeExte_10; "CVdsVolume::Extend, 3.2: NtQueryVolumeI"...
0x140011ed1  xor     edx, edx
0x140011ed3  lea     ecx, [rdx+5Eh]
0x140011ed6  call    cs:__imp_VdsTraceEx
0x140011edc  mov     qword ptr [rsp+1A0h+nOutBufferSize], 0
0x140011ee5  mov     [rsp+1A0h+FsInformationClass], 20A001Dh
0x140011eed  jmp     loc_140011C54
0x140011ef2  mov     r8d, dword ptr [rbp+0A0h+var_B0+0Ch]
0x140011ef6  mov     eax, dword ptr [rbp+0A0h+var_B0+8]
0x140011ef9  imul    r8, rax
0x140011efd  mov     rdx, r8
0x140011f00  imul    rdx, qword ptr [rbp+0A0h+var_C0]
0x140011f05  xor     r9d, r9d
0x140011f08  mov     ebx, [rsp+1A0h+ThreadId]
0x140011f0c  test    ebx, ebx
0x140011f0e  jle     short loc_140011F2F
0x140011f10  mov     r13, [rsp+1A0h+var_148]
0x140011f15  lea     rcx, [r9+r9*2]
0x140011f19  shl     rcx, 4
0x140011f1d  add     rdx, [rcx+r13+10h]
0x140011f22  inc     r9d
0x140011f25  cmp     r9d, ebx
0x140011f28  jl      short loc_140011F15
0x140011f2a  mov     r13, [rsp+1A0h+var_158]
0x140011f2f  test    r12b, r12b
  ... truncated ...
```
