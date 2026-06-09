# CVdsService::UninstallDisks(_GUID *,ulong,uchar,uchar *,long *)

- ea: `0x140022400`
- end: `0x140022d06`
- name: `?UninstallDisks@CVdsService@@UEAAJPEAU_GUID@@KEPEAEPEAJ@Z`
- size: `2310`
- prototype: `int(CVdsService *__hidden this, struct _GUID *, unsigned int, unsigned __int8, unsigned __int8 *, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x140003710`
- `0x140004360`
- `0x1400069e8`
- `0x140013298`
- `0x140020590`
- `0x140022400`
- `0x14002afe8`
- `0x14002e123`
- `0x140038c64`
- `0x140039f84`
- `0x14003a2dc`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022c92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022c92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022cce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400224ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400224ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002256b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400225b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022af4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022c0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022c5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002256b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400225b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022af4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022c0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140022c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400228b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022bce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400228b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022bce`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002286c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14002286c`
- `vdsutil!OpenDevice` at `0x140022744`
- `vdsutil!OpenDevice` at `0x140022744`
- `vdsutil!LockDismountVolume` at `0x1400227be`
- `vdsutil!LockDismountVolume` at `0x1400227be`
- `vdsutil!VdsHeapAlloc` at `0x14002257b`
- `vdsutil!VdsHeapAlloc` at `0x1400225c3`
- `vdsutil!VdsHeapAlloc` at `0x14002257b`
- `vdsutil!VdsHeapAlloc` at `0x1400225c3`
- `vdsutil!VdsHeapFree` at `0x140022b02`
- `vdsutil!VdsHeapFree` at `0x140022bf4`
- `vdsutil!VdsHeapFree` at `0x140022c1d`
- `vdsutil!VdsHeapFree` at `0x140022c44`
- `vdsutil!VdsHeapFree` at `0x140022c6b`
- `vdsutil!VdsHeapFree` at `0x140022b02`
- `vdsutil!VdsHeapFree` at `0x140022bf4`
- `vdsutil!VdsHeapFree` at `0x140022c1d`
- `vdsutil!VdsHeapFree` at `0x140022c44`
- `vdsutil!VdsHeapFree` at `0x140022c6b`
- `vdsutil!VdsTraceW` at `0x14002247e`
- `vdsutil!VdsTraceW` at `0x140022537`
- `vdsutil!VdsTraceW` at `0x14002259c`
- `vdsutil!VdsTraceW` at `0x1400225e2`
- `vdsutil!VdsTraceW` at `0x1400226ee`
- `vdsutil!VdsTraceW` at `0x14002277e`
- `vdsutil!VdsTraceW` at `0x1400227f8`
- `vdsutil!VdsTraceW` at `0x1400228a3`
- `vdsutil!VdsTraceW` at `0x140022904`
- `vdsutil!VdsTraceW` at `0x140022a32`
- `vdsutil!VdsTraceW` at `0x140022aa8`
- `vdsutil!VdsTraceW` at `0x140022b77`
- `vdsutil!VdsTraceW` at `0x140022c84`
- `vdsutil!VdsTraceW` at `0x140022cc0`
- `vdsutil!VdsTraceW` at `0x14002247e`
- `vdsutil!VdsTraceW` at `0x140022537`
- `vdsutil!VdsTraceW` at `0x14002259c`
- `vdsutil!VdsTraceW` at `0x1400225e2`
- `vdsutil!VdsTraceW` at `0x1400226ee`
- `vdsutil!VdsTraceW` at `0x14002277e`
- `vdsutil!VdsTraceW` at `0x1400227f8`
- `vdsutil!VdsTraceW` at `0x1400228a3`
- `vdsutil!VdsTraceW` at `0x140022904`
- `vdsutil!VdsTraceW` at `0x140022a32`
- `vdsutil!VdsTraceW` at `0x140022aa8`
- `vdsutil!VdsTraceW` at `0x140022b77`
- `vdsutil!VdsTraceW` at `0x140022c84`
- `vdsutil!VdsTraceW` at `0x140022cc0`

## string_xrefs

- `0x140022899`: `CVdsService::UninstallDisks, 8, hr=%lX, name=%s`
- `0x140022473`: `CVdsService::UninstallDisks`
- `0x140022cb7`: `CVdsService::UninstallDisks, 1, pDiskIdArray=%p, ulCount=%ld,pbReboot=%p, pResults=%p`
- `0x14002252e`: `CVdsService::UninstallDisks, 2, hr=%lX`
- `0x140022593`: `CVdsService::UninstallDisks, 3`
- `0x1400225db`: `CVdsService::UninstallDisks, 4`
- `0x1400226e2`: `CVdsService::UninstallDisks, 5, ObjectId=%s, hr=%lX`
- `0x140022772`: `CVdsService::UninstallDisks, 6, %lX, name=%s`
- `0x1400227ec`: `CVdsService::UninstallDisks, 7, %lX, name=%s`
- `0x1400228fb`: `CVdsService::UninstallDisks, 9, hr=%lX, name=%s`
- `0x140022a29`: `CVdsService::UninstallDisks, 10, hr=%lX, DiskId=%s`
- `0x140022a9f`: `CVdsService::UninstallDisks, 11, hr=%lX, name=%s`
- `0x140022b67`: `CVdsService::UninstallDisks, 12, hr=%lX, DiskId=%s`
- `0x140022c78`: `EXIT CVdsService::UninstallDisks, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::UninstallDisks(
        CVdsService *this,
        struct _GUID *a2,
        unsigned int a3,
        unsigned __int8 a4,
        unsigned __int8 *a5,
        int *a6)
{
  __int64 v6; // rsi
  unsigned __int8 *v9; // r12
  __int64 result; // rax
  signed int v11; // ebx
  int VolumeIdList; // eax
  unsigned int v13; // r14d
  unsigned int v14; // esi
  unsigned __int16 **v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // rbx
  HANDLE v20; // rax
  struct _GUID *v21; // rsi
  _QWORD *v22; // rbx
  unsigned __int16 **v23; // r13
  unsigned int v24; // eax
  unsigned __int8 v25; // di
  int VolumeNameById; // eax
  int v27; // eax
  __int64 v28; // r8
  const wchar_t *v29; // r9
  int v30; // eax
  const wchar_t *v31; // r9
  void **v32; // rdi
  unsigned __int16 **v33; // rbx
  unsigned int v34; // r13d
  BOOL v35; // r14d
  signed int LastError; // eax
  const wchar_t *v37; // r9
  int v38; // eax
  unsigned int v39; // esi
  const wchar_t *v40; // r9
  wchar_t *v41; // rax
  unsigned int v42; // r13d
  _DWORD *v43; // r12
  CVdsService *v44; // rcx
  int DiskNameById; // eax
  CVdsService *v46; // rcx
  unsigned int v47; // ebx
  int v48; // eax
  unsigned int v49; // ebx
  unsigned __int16 *v50; // r9
  wchar_t *v51; // rcx
  unsigned __int16 *v52; // rbx
  HANDLE v53; // rax
  int v54; // eax
  HANDLE *v55; // rbx
  unsigned int v56; // edi
  unsigned int i; // edx
  HANDLE v58; // rax
  unsigned __int16 **v59; // r15
  unsigned __int16 **v60; // rdi
  unsigned __int16 *v61; // rbx
  HANDLE v62; // rax
  HANDLE v63; // rax
  HANDLE v64; // rax
  LPVOID lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD nOutBufferSize[2]; // [rsp+28h] [rbp-D8h]
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  __int64 v69; // [rsp+40h] [rbp-C0h]
  __int64 v70; // [rsp+48h] [rbp-B8h]
  __int64 v71; // [rsp+50h] [rbp-B0h]
  __int64 v72; // [rsp+58h] [rbp-A8h]
  __int64 v73; // [rsp+60h] [rbp-A0h]
  __int64 v74; // [rsp+68h] [rbp-98h]
  unsigned __int8 v76[3]; // [rsp+71h] [rbp-8Fh] BYREF
  BOOL v77; // [rsp+74h] [rbp-8Ch]
  int v78; // [rsp+78h] [rbp-88h]
  __int128 v79; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v80; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v81; // [rsp+98h] [rbp-68h]
  unsigned int v82; // [rsp+9Ch] [rbp-64h]
  void **v83; // [rsp+A0h] [rbp-60h]
  __int64 v84; // [rsp+A8h] [rbp-58h] BYREF
  int v85; // [rsp+B0h] [rbp-50h]
  DWORD BytesReturned; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v87; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 **v88; // [rsp+C8h] [rbp-38h]
  unsigned int *p_Data1; // [rsp+D0h] [rbp-30h]
  _QWORD *v90; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v91; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 *v92; // [rsp+E8h] [rbp-18h]
  int *v93; // [rsp+F0h] [rbp-10h]
  char *v94; // [rsp+F8h] [rbp-8h]
  struct _GUID v95; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v96[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v97[68]; // [rsp+190h] [rbp+90h] BYREF

  v6 = a3;
  v82 = a3;
  v9 = a5;
  v92 = a5;
  v93 = a6;
  v87 = 0;
  v80 = 0;
  BytesReturned = 0;
  v76[0] = 0;
  v79 = 0;
  v91 = 0;
  VdsTraceW(2, L"CVdsService::UninstallDisks");
  v94 = (char *)this - 40;
  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 5) + 32LL))((char *)this - 40);
  if ( (int)result < 0 )
    return result;
  v84 = 0;
  v85 = 0;
  v11 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v84);
  if ( v11 < 0 )
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v84);
    return (unsigned int)v11;
  }
  EnterCriticalSection(&g_GlobalCriticalSection);
  if ( !a2 || !(_DWORD)v6 || !a5 || !a6 )
  {
    VdsTraceW(
      0,
      L"CVdsService::UninstallDisks, 1, pDiskIdArray=%p, ulCount=%ld,pbReboot=%p, pResults=%p",
      a2,
      (unsigned int)v6,
      a5,
      a6);
    LeaveCriticalSection(&g_GlobalCriticalSection);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v84);
    return 2147942487LL;
  }
  *a5 = 0;
  memset_0(a6, 0, 4 * v6);
  v79 = 0;
  VolumeIdList = CVdsService::GetVolumeIdList(a2, v6, (struct _VDS_UNINSTALL_INFORMATION *)&v79);
  v13 = VolumeIdList;
  v14 = 0;
  if ( VolumeIdList < 0 )
  {
    VdsTraceW(0, L"CVdsService::UninstallDisks, 2, hr=%lX", (unsigned int)VolumeIdList);
    *a5 = 0;
    goto LABEL_90;
  }
  v15 = 0;
  v88 = 0;
  v16 = 0;
  v83 = 0;
  if ( (_DWORD)v79 )
  {
    v17 = 8LL * (unsigned int)v79;
    ProcessHeap = GetProcessHeap();
    v16 = VdsHeapAlloc(ProcessHeap, 8, v17);
    v83 = (void **)v16;
    if ( !v16 )
    {
      v13 = -2147024882;
      VdsTraceW(0, L"CVdsService::UninstallDisks, 3");
      *a5 = 0;
      goto LABEL_92;
    }
    v19 = 8LL * (unsigned int)v79;
    v20 = GetProcessHeap();
    v15 = (unsigned __int16 **)VdsHeapAlloc(v20, 8, v19);
    v88 = v15;
    if ( !v15 )
    {
      v13 = -2147024882;
      VdsTraceW(0, L"CVdsService::UninstallDisks, 4");
      *a5 = 0;
      goto LABEL_81;
    }
  }
  v78 = 0;
  LOBYTE(v77) = 0;
  v21 = (struct _GUID *)*((_QWORD *)&v79 + 1);
  v22 = (_QWORD *)v16;
  v23 = v15;
  v24 = 0;
  v25 = a4;
  while ( 1 )
  {
    v81 = v24;
    v90 = v22;
    p_Data1 = &v21->Data1;
    if ( v24 >= (unsigned int)v79 )
      break;
    v95 = *v21;
    VolumeNameById = CVdsService::GetVolumeNameById(&v95, v23, &v91);
    v13 = VolumeNameById;
    if ( VolumeNameById == -2147211503 )
      goto LABEL_39;
    if ( VolumeNameById < 0 )
    {
      memset_0(v97, 0, 0x80u);
      LODWORD(v74) = v21->Data4[7];
      LODWORD(v73) = v21->Data4[6];
      LODWORD(v72) = v21->Data4[5];
      LODWORD(v71) = v21->Data4[4];
      LODWORD(v70) = v21->Data4[3];
      LODWORD(v69) = v21->Data4[2];
      LODWORD(lpOverlapped) = v21->Data4[1];
      LODWORD(lpBytesReturned) = v21->Data4[0];
      nOutBufferSize[0] = v21->Data3;
      LODWORD(lpOutBuffer) = v21->Data2;
      v21 = (struct _GUID *)p_Data1;
      StringCchPrintfW(
        v97,
        0x40u,
        L"%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x",
        *p_Data1,
        lpOutBuffer,
        *(_QWORD *)nOutBufferSize,
        lpBytesReturned,
        lpOverlapped,
        v69,
        v70,
        v71,
        v72,
        v73,
        v74);
      VdsTraceW(1, L"CVdsService::UninstallDisks, 5, ObjectId=%s, hr=%lX", v97, v13);
      if ( !a4 )
      {
        v14 = 0;
        goto LABEL_80;
      }
      VdsLogError(0x42000012u, 0, 0, v13, 0x200002Eu, v97, 0);
      v22 = v90;
LABEL_38:
      v25 = a4;
      goto LABEL_39;
    }
    v27 = OpenDevice(*v23, 3221225472LL, &v87);
    v13 = v27;
    if ( !v27 )
    {
      *v22 = v87;
      LOBYTE(v28) = 1;
      v30 = LockDismountVolume(v87, a4, v28);
      v13 = v30;
      if ( v30 )
      {
        if ( v30 > 0 )
          v13 = (unsigned __int16)v30 | 0x80070000;
        v31 = L"UNKNOWN";
        if ( *v23 )
          v31 = *v23;
        VdsTraceW(1, L"CVdsService::UninstallDisks, 7, %lX, name=%s", v13, v31);
        if ( !a4 )
        {
LABEL_27:
          v14 = 0;
          goto LABEL_28;
        }
      }
      goto LABEL_38;
    }
    if ( v27 > 0 )
      v13 = (unsigned __int16)v27 | 0x80070000;
    v29 = L"UNKNOWN";
    if ( *v23 )
      v29 = *v23;
    VdsTraceW(1, L"CVdsService::UninstallDisks, 6, %lX, name=%s", v13, v29);
    if ( !v25 )
      goto LABEL_27;
LABEL_39:
    v24 = v81 + 1;
    ++v21;
    ++v22;
    ++v23;
  }
  v32 = v83;
  v33 = v88;
  v14 = 0;
  v34 = 0;
  v35 = v77;
  if ( (_DWORD)v79 )
  {
    do
    {
      if ( v32 )
      {
        v15 = (unsigned __int16 **)*v32;
        if ( *v32 )
        {
          if ( !DeviceIoControl(v15, 0x56C00Cu, 0, 0, 0, 0, &BytesReturned, 0) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v37 = L"UNKNOWN";
            if ( *v33 )
              v37 = *v33;
            VdsTraceW(1, L"CVdsService::UninstallDisks, 8, hr=%lX, name=%s", (unsigned int)LastError, v37);
          }
          v15 = (unsigned __int16 **)*v32;
          if ( (char *)*v32 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            CloseHandle(v15);
            *v32 = 0;
          }
        }
      }
      if ( v33 && *v33 )
      {
        v76[0] = 0;
        v38 = CVdsService::UninstallVolume((CVdsService *)v15, *v33, v76);
        v39 = v38;
        if ( v38 < 0 )
        {
          v40 = L"UNKNOWN";
          if ( *v33 )
            v40 = *v33;
          VdsTraceW(0, L"CVdsService::UninstallDisks, 9, hr=%lX, name=%s", (unsigned int)v38, v40);
          v41 = L"UNKNOWN";
          if ( *v33 )
            v41 = *v33;
          VdsLogError(0x42000012u, 0, 0, v39, 0x200002Fu, v41, 0);
        }
        v14 = 0;
        if ( !v35 )
          v35 = v76[0] != 0;
      }
      ++v34;
      ++v32;
      ++v33;
    }
    while ( v34 < (unsigned int)v79 );
    v77 = v35;
    v9 = v92;
  }
  v42 = 0;
  if ( v82 )
  {
    v43 = v93;
    do
    {
      memset_0(v96, 0, sizeof(v96));
      LODWORD(v74) = a2->Data4[7];
      LODWORD(v73) = a2->Data4[6];
      LODWORD(v72) = a2->Data4[5];
      LODWORD(v71) = a2->Data4[4];
      LODWORD(v70) = a2->Data4[3];
      LODWORD(v69) = a2->Data4[2];
      LODWORD(lpOverlapped) = a2->Data4[1];
      LODWORD(lpBytesReturned) = a2->Data4[0];
      nOutBufferSize[0] = a2->Data3;
      LODWORD(lpOutBuffer) = a2->Data2;
      StringCchPrintfW(
        v96,
        0x40u,
        L"%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x",
        a2->Data1,
        lpOutBuffer,
        *(_QWORD *)nOutBufferSize,
        lpBytesReturned,
        lpOverlapped,
        v69,
        v70,
        v71,
        v72,
        v73,
        v74);
      DiskNameById = CVdsService::GetDiskNameById(v44, a2, &v80, &v91);
      v47 = DiskNameById;
      v14 = 0;
      if ( DiskNameById >= 0 )
      {
        v76[0] = 0;
        v48 = CVdsService::UninstallOneDisk(v46, v80, v76);
        v49 = v48;
        if ( v48 < 0 )
        {
          v50 = L"UNKNOWN";
          if ( v80 )
            v50 = v80;
          VdsTraceW(0, L"CVdsService::UninstallDisks, 11, hr=%lX, name=%s", (unsigned int)v48, v50);
          v51 = L"UNKNOWN";
          if ( v80 )
            v51 = v80;
          VdsLogError(0x42000013u, 0, 0, v49, 0x2000031u, v51, 0);
          *v43 = v49;
          v78 = 1;
        }
        v52 = v80;
        v53 = GetProcessHeap();
        VdsHeapFree(v53, 0, v52);
        v80 = 0;
        if ( !v35 )
        {
          v35 = 1;
          LOBYTE(v35) = v76[0] != 0;
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsService::UninstallDisks, 10, hr=%lX, DiskId=%s", (unsigned int)DiskNameById, v96);
        VdsLogError(0x42000013u, 0, 0, v47, 0x2000030u, v96, 0);
        *v43 = v47;
        v78 = 1;
      }
      ++v42;
      ++a2;
      ++v43;
    }
    while ( v42 < v82 );
    v77 = v35;
    v9 = v92;
  }
  v54 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v94 + 112LL))(v94);
  v13 = v54;
  if ( v54 < 0 )
  {
    VdsTraceW(1, L"CVdsService::UninstallDisks, 12, hr=%lX, DiskId=%s", (unsigned int)v54, v96);
    VdsLogError(0x42000014u, 0, 0, v13, 0x2000032u, 0);
    goto LABEL_80;
  }
LABEL_28:
  if ( !v13 && v78 )
    v13 = v78;
LABEL_80:
  *v9 = v77;
  v16 = (__int64)v83;
  if ( v83 )
  {
LABEL_81:
    v55 = (HANDLE *)v16;
    v56 = 0;
    for ( i = v79; v56 < i; ++v56 )
    {
      if ( (char *)*v55 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(*v55);
        *v55 = 0;
        i = v79;
      }
      ++v55;
    }
    v58 = GetProcessHeap();
    VdsHeapFree(v58, 0, v83);
  }
  v59 = v88;
  if ( v88 )
  {
    v60 = v88;
    if ( (_DWORD)v79 )
    {
      do
      {
        v61 = *v60;
        v62 = GetProcessHeap();
        VdsHeapFree(v62, 0, v61);
        *v60 = 0;
        ++v14;
        ++v60;
      }
      while ( v14 < (unsigned int)v79 );
    }
    v63 = GetProcessHeap();
    VdsHeapFree(v63, 0, v59);
  }
LABEL_90:
  if ( v13 == -2147024809 )
    v13 = -2147212216;
LABEL_92:
  v64 = GetProcessHeap();
  VdsHeapFree(v64, 0, *((_QWORD *)&v79 + 1));
  *((_QWORD *)&v79 + 1) = 0;
  VdsTraceW(2, L"EXIT CVdsService::UninstallDisks, hr=%lX", v13);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v84);
  return v13;
}

```

## disassembly

```asm
0x140022400  push    rbp
0x140022402  push    rbx
0x140022403  push    rsi
0x140022404  push    rdi
0x140022405  push    r12
0x140022407  push    r13
0x140022409  push    r14
0x14002240b  push    r15
0x14002240d  lea     rbp, [rsp-128h]
0x140022415  sub     rsp, 228h
0x14002241c  mov     rax, cs:__security_cookie
0x140022423  xor     rax, rsp
0x140022426  mov     [rbp+160h+var_48], rax
0x14002242d  mov     [rsp+260h+var_1F0], r9b
0x140022432  mov     esi, r8d
0x140022435  mov     [rbp+160h+var_1C4], esi
0x140022438  mov     r15, rdx
0x14002243b  mov     rbx, rcx
0x14002243e  mov     r12, [rbp+160h+arg_20]
0x140022445  mov     [rbp+160h+var_178], r12
0x140022449  mov     rdi, [rbp+160h+arg_28]
0x140022450  mov     [rbp+160h+var_170], rdi
0x140022454  xor     r14d, r14d
0x140022457  mov     [rbp+160h+var_1A0], r14
0x14002245b  mov     [rbp+160h+var_1D0], r14
0x14002245f  mov     [rbp+160h+BytesReturned], r14d
0x140022463  mov     [rsp+260h+var_1EF], r14b
0x140022468  xorps   xmm0, xmm0
0x14002246b  movups  [rbp+160h+var_1E0], xmm0
0x14002246f  mov     [rbp+160h+var_180], r14
0x140022473  lea     rdx, aCvdsserviceUni_36; "CVdsService::UninstallDisks"
0x14002247a  lea     ecx, [r14+2]
0x14002247e  call    cs:__imp_VdsTraceW
0x140022484  lea     rcx, [rbx-28h]
0x140022488  mov     [rbp+160h+var_168], rcx
0x14002248c  mov     rax, [rcx]
0x14002248f  mov     rax, [rax+20h]
0x140022493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022498  test    eax, eax
0x14002249a  js      loc_140022CE3
0x1400224a0  mov     [rbp+160h+var_1B8], r14
0x1400224a4  mov     [rbp+160h+var_1B0], r14d
0x1400224a8  lea     rcx, [rbp+160h+var_1B8]; this
0x1400224ac  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x1400224b1  mov     ebx, eax
0x1400224b3  test    eax, eax
0x1400224b5  jns     short loc_1400224C7
0x1400224b7  lea     rcx, [rbp+160h+var_1B8]; this
0x1400224bb  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400224c0  mov     eax, ebx
0x1400224c2  jmp     loc_140022CE3
0x1400224c7  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400224ce  call    cs:__imp_EnterCriticalSection
0x1400224d4  nop
0x1400224d5  test    r15, r15
0x1400224d8  jz      loc_140022CA7
0x1400224de  test    esi, esi
0x1400224e0  jz      loc_140022CA7
0x1400224e6  test    r12, r12
0x1400224e9  jz      loc_140022CA7
0x1400224ef  test    rdi, rdi
0x1400224f2  jz      loc_140022CA7
0x1400224f8  mov     [r12], r14b
0x1400224fc  mov     r8, rsi
0x1400224ff  shl     r8, 2; Size
0x140022503  xor     edx, edx; Val
0x140022505  mov     rcx, rdi; void *
0x140022508  call    memset_0
0x14002250d  xorps   xmm0, xmm0
0x140022510  movups  [rbp+160h+var_1E0], xmm0
0x140022514  lea     r8, [rbp+160h+var_1E0]; struct _VDS_UNINSTALL_INFORMATION *
0x140022518  mov     edx, esi; unsigned int
0x14002251a  mov     rcx, r15; struct _GUID *
0x14002251d  call    ?GetVolumeIdList@CVdsService@@SAJPEAU_GUID@@KPEAU_VDS_UNINSTALL_INFORMATION@@@Z; CVdsService::GetVolumeIdList(_GUID *,ulong,_VDS_UNINSTALL_INFORMATION *)
0x140022522  mov     r14d, eax
0x140022525  xor     esi, esi
0x140022527  test    eax, eax
0x140022529  jns     short loc_140022546
0x14002252b  mov     r8d, eax
0x14002252e  lea     rdx, aCvdsserviceUni_15; "CVdsService::UninstallDisks, 2, hr=%lX"
0x140022535  xor     ecx, ecx
0x140022537  call    cs:__imp_VdsTraceW
0x14002253d  mov     [r12], sil
0x140022541  jmp     loc_140022C4C
0x140022546  mov     rcx, rsi
0x140022549  mov     [rbp+160h+var_198], rcx
0x14002254d  mov     rdi, rsi
0x140022550  mov     [rbp+160h+var_1C0], rsi
0x140022554  mov     r13d, 1
0x14002255a  mov     eax, dword ptr [rbp+160h+var_1E0]
0x14002255d  test    eax, eax
0x14002255f  jz      loc_1400225F1
0x140022565  mov     ebx, eax
0x140022567  shl     rbx, 3
0x14002256b  call    cs:__imp_GetProcessHeap
0x140022571  mov     rcx, rax
0x140022574  mov     r8, rbx
0x140022577  lea     edx, [r13+7]
0x14002257b  call    cs:__imp_VdsHeapAlloc
0x140022581  mov     rdi, rax
0x140022584  mov     [rbp+160h+var_1C0], rax
0x140022588  test    rax, rax
0x14002258b  jnz     short loc_1400225AB
0x14002258d  mov     r14d, 8007000Eh
0x140022593  lea     rdx, aCvdsserviceUni_42; "CVdsService::UninstallDisks, 3"
0x14002259a  xor     ecx, ecx
0x14002259c  call    cs:__imp_VdsTraceW
0x1400225a2  mov     [r12], sil
0x1400225a6  jmp     loc_140022C5C
0x1400225ab  mov     ebx, dword ptr [rbp+160h+var_1E0]
0x1400225ae  shl     rbx, 3
0x1400225b2  call    cs:__imp_GetProcessHeap
0x1400225b8  mov     rcx, rax
0x1400225bb  mov     r8, rbx
0x1400225be  mov     edx, 8
0x1400225c3  call    cs:__imp_VdsHeapAlloc
0x1400225c9  mov     rcx, rax
0x1400225cc  mov     [rbp+160h+var_198], rax
0x1400225d0  test    rax, rax
0x1400225d3  jnz     short loc_1400225F1
0x1400225d5  mov     r14d, 8007000Eh
0x1400225db  lea     rdx, aCvdsserviceUni_7; "CVdsService::UninstallDisks, 4"
0x1400225e2  call    cs:__imp_VdsTraceW
0x1400225e8  mov     [r12], sil
0x1400225ec  jmp     loc_140022BB5
0x1400225f1  mov     [rsp+260h+var_1E8], esi
0x1400225f5  mov     byte ptr [rsp+260h+var_1EC], sil
0x1400225fa  mov     rsi, qword ptr [rbp+160h+var_1E0+8]
0x1400225fe  mov     rbx, rdi
0x140022601  mov     r13, rcx
0x140022604  xor     eax, eax
0x140022606  mov     dil, [rsp+260h+var_1F0]
0x14002260b  mov     [rbp+160h+var_1C8], eax
0x14002260e  mov     [rbp+160h+var_188], rbx
0x140022612  mov     [rbp+160h+var_190], rsi
0x140022616  cmp     eax, dword ptr [rbp+160h+var_1E0]
0x140022619  jnb     loc_14002281E
0x14002261f  movups  xmm0, xmmword ptr [rsi]
0x140022622  movdqu  xmmword ptr [rbp+160h+var_160.Data1], xmm0
0x140022627  lea     r8, [rbp+160h+var_180]; unsigned __int64 *
0x14002262b  mov     rdx, r13; unsigned __int16 **
0x14002262e  lea     rcx, [rbp+160h+var_160]; struct _GUID
0x140022632  call    ?GetVolumeNameById@CVdsService@@SAJU_GUID@@PEAPEAGAEA_K@Z; CVdsService::GetVolumeNameById(_GUID,ushort * *,unsigned __int64 &)
0x140022637  mov     r14d, eax
0x14002263a  cmp     eax, 80042711h
0x14002263f  jz      loc_140022808
0x140022645  test    eax, eax
0x140022647  jns     loc_140022737
0x14002264d  xor     edx, edx; Val
0x14002264f  mov     r8d, 80h; Size
0x140022655  lea     rcx, [rbp+160h+var_D0]; void *
0x14002265c  call    memset_0
0x140022661  movzx   eax, byte ptr [rsi+0Fh]
0x140022665  movzx   ecx, byte ptr [rsi+0Eh]
0x140022669  movzx   edx, byte ptr [rsi+0Dh]
0x14002266d  movzx   r8d, byte ptr [rsi+0Ch]
0x140022672  movzx   r9d, byte ptr [rsi+0Bh]
0x140022677  movzx   r10d, byte ptr [rsi+0Ah]
0x14002267c  movzx   r11d, byte ptr [rsi+9]
0x140022681  movzx   ebx, byte ptr [rsi+8]
0x140022685  movzx   edi, word ptr [rsi+6]
0x140022689  movzx   esi, word ptr [rsi+4]
0x14002268d  mov     dword ptr [rsp+260h+var_1F8], eax
0x140022691  mov     dword ptr [rsp+260h+var_200], ecx
0x140022695  mov     dword ptr [rsp+260h+var_208], edx
0x140022699  mov     dword ptr [rsp+260h+var_210], r8d
0x14002269e  mov     dword ptr [rsp+260h+var_218], r9d
0x1400226a3  mov     dword ptr [rsp+260h+var_220], r10d
0x1400226a8  mov     dword ptr [rsp+260h+lpOverlapped], r11d
0x1400226ad  mov     dword ptr [rsp+260h+lpBytesReturned], ebx
0x1400226b1  mov     [rsp+260h+nOutBufferSize], edi
0x1400226b5  mov     dword ptr [rsp+260h+lpOutBuffer], esi
0x1400226b9  mov     rsi, [rbp+160h+var_190]
0x1400226bd  mov     r9d, [rsi]
0x1400226c0  lea     r8, a8x4x4x2x2x2x2x; "%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2"...
0x1400226c7  mov     edx, 40h ; '@'; unsigned __int64
0x1400226cc  lea     rcx, [rbp+160h+var_D0]; unsigned __int16 *
0x1400226d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400226d8  mov     r9d, r14d
0x1400226db  lea     r8, [rbp+160h+var_D0]
0x1400226e2  lea     rdx, aCvdsserviceUni_14; "CVdsService::UninstallDisks, 5, ObjectI"...
0x1400226e9  mov     ecx, 1
0x1400226ee  call    cs:__imp_VdsTraceW
0x1400226f4  cmp     [rsp+260h+var_1F0], 0
0x1400226f9  jz      loc_140022B9E
0x1400226ff  mov     [rsp+260h+lpBytesReturned], 0
0x140022708  lea     rax, [rbp+160h+var_D0]
0x14002270f  mov     qword ptr [rsp+260h+nOutBufferSize], rax; unsigned __int16 *
0x140022714  mov     dword ptr [rsp+260h+lpOutBuffer], 200002Eh; unsigned int
0x14002271c  mov     r9d, r14d; unsigned int
0x14002271f  xor     r8d, r8d; void *
0x140022722  xor     edx, edx; unsigned int
0x140022724  mov     ecx, 42000012h; unsigned int
0x140022729  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14002272e  mov     rbx, [rbp+160h+var_188]
0x140022732  jmp     loc_140022803
0x140022737  lea     r8, [rbp+160h+var_1A0]
0x14002273b  mov     edx, 0C0000000h
0x140022740  mov     rcx, [r13+0]
0x140022744  call    cs:__imp_OpenDevice
0x14002274a  mov     r14d, eax
0x14002274d  test    eax, eax
0x14002274f  jz      short loc_1400227A9
0x140022751  jle     short loc_14002275E
0x140022753  movzx   r14d, ax
0x140022757  or      r14d, 80070000h
0x14002275e  lea     r9, aUnknown_0; "UNKNOWN"
0x140022765  cmp     qword ptr [r13+0], 0
0x14002276a  cmovnz  r9, [r13+0]
0x14002276f  mov     r8d, r14d
0x140022772  lea     rdx, aCvdsserviceUni_33; "CVdsService::UninstallDisks, 6, %lX, na"...
0x140022779  mov     ecx, 1
0x14002277e  call    cs:__imp_VdsTraceW
0x140022784  test    dil, dil
0x140022787  jnz     short loc_140022808
0x140022789  xor     esi, esi
0x14002278b  mov     r13d, 1
0x140022791  test    r14d, r14d
0x140022794  jnz     loc_140022BA4
0x14002279a  mov     eax, [rsp+260h+var_1E8]
0x14002279e  test    eax, eax
0x1400227a0  cmovnz  r14d, eax
0x1400227a4  jmp     loc_140022BA4
0x1400227a9  mov     rax, [rbp+160h+var_1A0]
0x1400227ad  mov     [rbx], rax
0x1400227b0  movzx   edi, [rsp+260h+var_1F0]
0x1400227b5  mov     edx, edi
0x1400227b7  mov     r8b, 1
0x1400227ba  mov     rcx, [rbp+160h+var_1A0]
0x1400227be  call    cs:__imp_LockDismountVolume
0x1400227c4  mov     r14d, eax
0x1400227c7  test    eax, eax
0x1400227c9  jz      short loc_140022803
0x1400227cb  jle     short loc_1400227D8
0x1400227cd  movzx   r14d, ax
0x1400227d1  or      r14d, 80070000h
0x1400227d8  lea     r9, aUnknown_0; "UNKNOWN"
0x1400227df  cmp     qword ptr [r13+0], 0
0x1400227e4  cmovnz  r9, [r13+0]
0x1400227e9  mov     r8d, r14d
0x1400227ec  lea     rdx, aCvdsserviceUni_13; "CVdsService::UninstallDisks, 7, %lX, na"...
0x1400227f3  mov     ecx, 1
0x1400227f8  call    cs:__imp_VdsTraceW
0x1400227fe  test    dil, dil
0x140022801  jz      short loc_140022789
0x140022803  mov     dil, [rsp+260h+var_1F0]
0x140022808  mov     eax, [rbp+160h+var_1C8]
0x14002280b  inc     eax
0x14002280d  add     rsi, 10h
0x140022811  add     rbx, 8
0x140022815  add     r13, 8
0x140022819  jmp     loc_14002260B
0x14002281e  mov     rdi, [rbp+160h+var_1C0]
0x140022822  mov     rbx, [rbp+160h+var_198]
0x140022826  xor     esi, esi
0x140022828  mov     r13d, esi
0x14002282b  mov     r14d, [rsp+260h+var_1EC]
0x140022830  cmp     dword ptr [rbp+160h+var_1E0], esi
0x140022833  jbe     loc_140022973
0x140022839  lea     r12d, [rsi+1]
0x14002283d  test    rdi, rdi
0x140022840  jz      short loc_1400228BF
0x140022842  mov     rcx, [rdi]; hDevice
0x140022845  test    rcx, rcx
0x140022848  jz      short loc_1400228BF
0x14002284a  mov     [rsp+260h+lpOverlapped], rsi; lpOverlapped
0x14002284f  lea     rax, [rbp+160h+BytesReturned]
0x140022853  mov     [rsp+260h+lpBytesReturned], rax; lpBytesReturned
0x140022858  mov     [rsp+260h+nOutBufferSize], esi; nOutBufferSize
0x14002285c  mov     [rsp+260h+lpOutBuffer], rsi; lpOutBuffer
0x140022861  xor     r9d, r9d; nInBufferSize
0x140022864  xor     r8d, r8d; lpInBuffer
0x140022867  mov     edx, 56C00Ch; dwIoControlCode
0x14002286c  call    cs:__imp_DeviceIoControl
0x140022872  test    eax, eax
0x140022874  jnz     short loc_1400228A9
0x140022876  call    cs:__imp_GetLastError
0x14002287c  test    eax, eax
0x14002287e  jle     short loc_140022888
0x140022880  movzx   eax, ax
0x140022883  or      eax, 80070000h
0x140022888  lea     r9, aUnknown_0; "UNKNOWN"
0x14002288f  cmp     [rbx], rsi
0x140022892  cmovnz  r9, [rbx]
0x140022896  mov     r8d, eax
0x140022899  lea     rdx, aCvdsserviceUni_27; "CVdsService::UninstallDisks, 8, hr=%lX,"...
0x1400228a0  mov     ecx, r12d
0x1400228a3  call    cs:__imp_VdsTraceW
0x1400228a9  mov     rcx, [rdi]; hObject
0x1400228ac  lea     rax, [rcx-1]
0x1400228b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400228b4  ja      short loc_1400228BF
0x1400228b6  call    cs:__imp_CloseHandle
0x1400228bc  mov     [rdi], rsi
0x1400228bf  test    rbx, rbx
0x1400228c2  jz      loc_140022955
0x1400228c8  cmp     [rbx], rsi
0x1400228cb  jz      loc_140022955
0x1400228d1  mov     [rsp+260h+var_1EF], sil
0x1400228d6  lea     r8, [rsp+260h+var_1EF]; unsigned __int8 *
  ... truncated ...
```
