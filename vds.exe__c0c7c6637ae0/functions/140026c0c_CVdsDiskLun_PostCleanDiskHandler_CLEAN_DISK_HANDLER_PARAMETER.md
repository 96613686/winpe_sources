# CVdsDiskLun::PostCleanDiskHandler(_CLEAN_DISK_HANDLER_PARAMETER *)

- ea: `0x140026c0c`
- end: `0x140027263`
- name: `?PostCleanDiskHandler@CVdsDiskLun@@QEAAKPEAU_CLEAN_DISK_HANDLER_PARAMETER@@@Z`
- size: `1623`
- prototype: `unsigned int __fastcall(CVdsDiskLun *__hidden this, struct _CLEAN_DISK_HANDLER_PARAMETER *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x140049d10`

## callees

- `0x14000d0f0`
- `0x14000f930`
- `0x14000f9b0`
- `0x140026c0c`
- `0x14002e123`
- `0x140037a0c`
- `0x14003870c`
- `0x14003c668`
- `0x14003ca88`
- `0x14004f68c`
- `0x14004f790`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026ce6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026da8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026e65`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026eea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140027143`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400271e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026ce6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026da8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026e65`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140026eea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140027143`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400271e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140026f16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140027224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140026f16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140027224`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140026e12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140026e12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140026dca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140026dca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140026fa3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140026fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002718b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026fe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002718b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140026cf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140026cf6`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14002706c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14002706c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140027048`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140027048`
- `vdsutil!OpenDevice` at `0x140026f37`
- `vdsutil!OpenDevice` at `0x140026f37`
- `vdsutil!GetPartitionInformation` at `0x140026f72`
- `vdsutil!GetPartitionInformation` at `0x140026f72`
- `vdsutil!GarbageCollectDriveLetters` at `0x140026d57`
- `vdsutil!GarbageCollectDriveLetters` at `0x140026d57`
- `vdsutil!DeleteBcdObjects` at `0x140026d61`
- `vdsutil!DeleteBcdObjects` at `0x140026d61`
- `vdsutil!VdsHeapAlloc` at `0x140026fb2`
- `vdsutil!VdsHeapAlloc` at `0x140026fb2`
- `vdsutil!VdsTraceEx` at `0x140026cd8`
- `vdsutil!VdsTraceEx` at `0x140026d7d`
- `vdsutil!VdsTraceEx` at `0x140026e04`
- `vdsutil!VdsTraceEx` at `0x140026e54`
- `vdsutil!VdsTraceEx` at `0x140026ed9`
- `vdsutil!VdsTraceEx` at `0x140026f5e`
- `vdsutil!VdsTraceEx` at `0x1400271c8`
- `vdsutil!VdsTraceEx` at `0x140026cd8`
- `vdsutil!VdsTraceEx` at `0x140026d7d`
- `vdsutil!VdsTraceEx` at `0x140026e04`
- `vdsutil!VdsTraceEx` at `0x140026e54`
- `vdsutil!VdsTraceEx` at `0x140026ed9`
- `vdsutil!VdsTraceEx` at `0x140026f5e`
- `vdsutil!VdsTraceEx` at `0x1400271c8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140026c98`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140026c98`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140027230`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140027230`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVdsDiskLun::PostCleanDiskHandler(CVdsDiskLun *this, struct _CLEAN_DISK_HANDLER_PARAMETER *a2)
{
  void *v3; // rdi
  unsigned int v4; // r14d
  __int64 v5; // rsi
  int v6; // eax
  int v7; // r12d
  _DWORD *v8; // rbx
  int v9; // r12d
  int v10; // eax
  struct IUnknown *v11; // r14
  struct CVdsRawDiskLun *RawDisk; // rax
  signed int PartitionInformation; // eax
  const char *v14; // r8
  __int64 v15; // r9
  DWORD v16; // r14d
  HANDLE ProcessHeap; // rax
  __int64 v18; // rax
  DWORD v19; // ecx
  __int64 v20; // r13
  LARGE_INTEGER v21; // rbx
  __int64 v22; // rdx
  int v23; // edx
  __int64 v24; // rax
  int v25; // ecx
  signed int LastError; // eax
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v33; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[16]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-50h]
  unsigned int v39; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 *v40; // [rsp+1A0h] [rbp+A0h] BYREF
  struct CVdsRawDiskLun *v41; // [rsp+1A8h] [rbp+A8h]

  v29 = 0;
  memset(v35, 0, sizeof(v35));
  v28 = 0;
  v40 = 0;
  v39 = 0;
  hFile = (HANDLE)-1LL;
  v3 = 0;
  v32[0] = 0;
  memset_0(v36, 0, 0x90u);
  NumberOfBytesWritten = 0;
  v4 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v34, 0x5Eu, "CVdsDiskLun::PostCleanDiskHandler()");
  v5 = *((_QWORD *)a2 + 9);
  v6 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v5 + 64))(*(_QWORD *)(v5 + 64), &IID_IVdsAsync, &v29);
  v7 = v6;
  v8 = (_DWORD *)((char *)a2 + 84);
  if ( v6 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::PostCleanDiskHandler: pAsync QueryInterface failed: %lX", v6);
    *(_DWORD *)(v5 + 104) = v7;
    SetEvent(*(HANDLE *)(v5 + 96));
    goto LABEL_79;
  }
  if ( *v8 )
    g_dwThreadIdExclusiveLock = GetCurrentThreadId();
  v9 = (*(__int64 (__fastcall **)(__int64, int *, _OWORD *))(*(_QWORD *)v29 + 32LL))(v29, &v28, v35);
  if ( v9 < 0 || v28 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsDiskLun::PostCleanDiskHandler, 1, %lX, %lX", v9, v28);
    if ( v9 >= 0 )
      *(_DWORD *)(v5 + 104) = v28;
    else
      *(_DWORD *)(v5 + 104) = v9;
    goto LABEL_76;
  }
  if ( *((_DWORD *)a2 + 20) == 1 )
  {
    *(_DWORD *)(v5 + 108) = 100;
    *(_DWORD *)(v5 + 104) = 0;
LABEL_76:
    SetEvent(*(HANDLE *)(v5 + 96));
    goto LABEL_77;
  }
  if ( *v8 )
  {
    GarbageCollectDriveLetters();
    v10 = DeleteBcdObjects((char *)a2 + 24);
    if ( v10 < 0 )
      VdsTraceEx(94, 1, "CVdsDiskLun::PostCleanDiskHandler, 2, status=%lX", v10);
    if ( (unsigned int)CVdsService::ClaimRawDisk(*((wchar_t **)a2 + 8), (struct _GUID *)((char *)a2 + 8), 0, 0) )
    {
      *(_DWORD *)(v5 + 104) = -2147418113;
      SetEvent(*(HANDLE *)(v5 + 96));
      CVdsService::SendDiskNotification(9u, (struct _GUID *)((char *)a2 + 8));
LABEL_14:
      v4 = 0;
LABEL_77:
      if ( !v29 )
        goto LABEL_80;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_79:
      v29 = 0;
LABEL_80:
      if ( *v8 )
      {
        _InterlockedExchange((volatile __int32 *)&g_dwThreadIdExclusiveLock, 0);
        ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
      }
      goto LABEL_82;
    }
    EnterCriticalSection(&g_GlobalCriticalSection);
    v11 = (struct IUnknown *)*((_QWORD *)this + 26);
    if ( v11 )
      ((void (__fastcall *)(_QWORD))v11->lpVtbl->AddRef)(*((_QWORD *)this + 26));
    else
      VdsTraceEx(94, 1, "CVdsDiskLun::PostCleanDiskHandler, 3, m_pUnk == NULL");
    LeaveCriticalSection(&g_GlobalCriticalSection);
    if ( v11 )
    {
      v9 = CVdsService::ResetDiskWrapper((struct _GUID *)((char *)a2 + 8), v11, 0, 0);
      ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
      if ( v9 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::PostCleanDiskHandler, 4, %lX", v9);
        *(_DWORD *)(v5 + 104) = -2147212263;
        SetEvent(*(HANDLE *)(v5 + 96));
        v4 = -2147212263;
        goto LABEL_77;
      }
    }
  }
  v41 = 0;
  if ( *((_DWORD *)a2 + 22) == 1 )
  {
    v33 = *(struct _GUID *)((char *)a2 + 8);
    RawDisk = CVdsService::FindRawDisk(&v33, &v40, &v39);
    v41 = RawDisk;
    if ( !RawDisk )
    {
      v28 = -2147212283;
      VdsTraceEx(94, 0, "CVdsDiskLun::PostCleanDiskHandler, 5, %lX", v9);
      *(_DWORD *)(v5 + 104) = v28;
      SetEvent(*(HANDLE *)(v5 + 96));
      goto LABEL_14;
    }
    *((_DWORD *)RawDisk + 86) = 1;
  }
  if ( *v8 )
  {
    _InterlockedExchange((volatile __int32 *)&g_dwThreadIdExclusiveLock, 0);
    ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
  }
  if ( *((_DWORD *)a2 + 22) != 1 )
  {
LABEL_60:
    v28 = 0;
    goto LABEL_61;
  }
  PartitionInformation = OpenDevice(v40, 3221225472LL, &hFile);
  if ( PartitionInformation )
  {
    if ( PartitionInformation > 0 )
      PartitionInformation = (unsigned __int16)PartitionInformation | 0x80070000;
    v14 = "CVdsDiskLun::PostCleanDiskHandler, 6, %lX";
  }
  else
  {
    PartitionInformation = GetPartitionInformation(hFile, v36);
    if ( !PartitionInformation )
    {
      v16 = 0x100000;
      while ( !v3 )
      {
        if ( v16 < 0x200 )
        {
          PartitionInformation = GetLastError();
          if ( PartitionInformation > 0 )
            PartitionInformation = (unsigned __int16)PartitionInformation | 0x80070000;
          v14 = "CVdsDiskLun::PostCleanDiskHandler, 8, %lX";
          goto LABEL_32;
        }
        ProcessHeap = GetProcessHeap();
        v18 = VdsHeapAlloc(ProcessHeap, 8, v16);
        CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(v32, v18);
        v3 = (void *)v32[0];
        v19 = v16 >> 1;
        if ( v32[0] )
          v19 = v16;
        v16 = v19;
      }
      memset_0(v3, 0, v16);
      v20 = 0;
      v39 = 0;
      v21.QuadPart = 0;
      v22 = v37;
      while ( 1 )
      {
        if ( v16 > v22 - v20 )
          v16 = v22 - v20;
        if ( !WriteFile(hFile, v3, v16, &NumberOfBytesWritten, 0) )
          break;
        v21.QuadPart += NumberOfBytesWritten;
        if ( !SetFilePointerEx(hFile, v21, 0, 0) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v14 = "CVdsDiskLun::PostCleanDiskHandler, 10, %lX";
          goto LABEL_72;
        }
        v20 += v16;
        v24 = v37;
        v25 = (int)(float)((float)((float)(int)v20 / (float)(int)v37) * 100.0);
        if ( v25 != v39 )
        {
          v39 = (int)(float)((float)((float)(int)v20 / (float)(int)v37) * 100.0);
          *(_DWORD *)(v5 + 104) = -2147212279;
          *(_DWORD *)(v5 + 108) = v25;
          v24 = v37;
        }
        if ( v20 >= v24 )
        {
          CVdsAsyncObject::SetCancelTooLate((CVdsAsyncObject *)v5, v23);
        }
        else if ( (unsigned int)CVdsAsyncObject::IsCancelRequested((CVdsAsyncObject *)v5) )
        {
          v28 = 271386;
          v15 = (unsigned int)v9;
          v14 = "CVdsDiskLun::PostCleanDiskHandler, 11, %lX";
          goto LABEL_33;
        }
        v22 = v37;
        if ( v20 >= v37 )
        {
          CVdsService::SendDiskNotification(0xAu, (struct _GUID *)((char *)a2 + 8));
          goto LABEL_60;
        }
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = "CVdsDiskLun::PostCleanDiskHandler, 9, %lX";
LABEL_72:
      v15 = (unsigned int)LastError;
      v28 = LastError;
      goto LABEL_33;
    }
    if ( PartitionInformation > 0 )
      PartitionInformation = (unsigned __int16)PartitionInformation | 0x80070000;
    v14 = "CVdsDiskLun::PostCleanDiskHandler, 7, %lX";
  }
LABEL_32:
  v28 = PartitionInformation;
  v15 = (unsigned int)PartitionInformation;
LABEL_33:
  VdsTraceEx(94, 0, v14, v15);
LABEL_61:
  if ( *((_DWORD *)a2 + 22) == 1 )
    *((_DWORD *)v41 + 86) = 0;
  *(_DWORD *)(v5 + 104) = v28;
  *(_DWORD *)(v5 + 108) = 100;
  *(_DWORD *)(v5 + 104) = v28;
  SetEvent(*(HANDLE *)(v5 + 96));
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  v4 = 0;
LABEL_82:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(v32);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hFile);
  return v4;
}

```

## disassembly

```asm
0x140026c0c  mov     [rsp-8+arg_0], rcx
0x140026c11  push    rbp
0x140026c12  push    rbx
0x140026c13  push    rsi
0x140026c14  push    rdi
0x140026c15  push    r12
0x140026c17  push    r13
0x140026c19  push    r14
0x140026c1b  push    r15
0x140026c1d  lea     rbp, [rsp-48h]
0x140026c22  sub     rsp, 148h
0x140026c29  mov     r15, rdx
0x140026c2c  mov     [rsp+180h+var_148], 0
0x140026c35  xorps   xmm0, xmm0
0x140026c38  movups  [rbp+80h+var_100], xmm0
0x140026c3c  movups  [rbp+80h+var_F0], xmm0
0x140026c40  mov     [rsp+180h+var_150], 0
0x140026c48  mov     [rbp+80h+arg_10], 0
0x140026c53  mov     [rbp+80h+arg_8], 0
0x140026c5d  mov     [rsp+180h+hFile], 0FFFFFFFFFFFFFFFFh
0x140026c66  xor     edi, edi
0x140026c68  mov     [rsp+180h+var_130], rdi
0x140026c6d  xor     edx, edx; Val
0x140026c6f  mov     r8d, 90h; Size
0x140026c75  lea     rcx, [rbp+80h+var_E0]; void *
0x140026c79  call    memset_0
0x140026c7e  mov     [rsp+180h+NumberOfBytesWritten], edi
0x140026c82  xor     r14d, r14d
0x140026c85  lea     r8, aCvdsdisklunPos_9; "CVdsDiskLun::PostCleanDiskHandler()"
0x140026c8c  lea     r13d, [rdi+5Eh]
0x140026c90  mov     edx, r13d
0x140026c93  lea     rcx, [rsp+180h+var_110]
0x140026c98  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140026c9e  nop
0x140026c9f  mov     rsi, [r15+48h]
0x140026ca3  mov     rcx, [rsi+40h]
0x140026ca7  mov     rax, [rcx]
0x140026caa  lea     r8, [rsp+180h+var_148]
0x140026caf  lea     rdx, IID_IVdsAsync
0x140026cb6  mov     rax, [rax]
0x140026cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026cbe  mov     r12d, eax
0x140026cc1  lea     rbx, [r15+54h]
0x140026cc5  test    eax, eax
0x140026cc7  jns     short loc_140026CF1
0x140026cc9  mov     r9d, eax
0x140026ccc  lea     r8, aCvdsdisklunPos_12; "CVdsDiskLun::PostCleanDiskHandler: pAsy"...
0x140026cd3  xor     edx, edx
0x140026cd5  mov     ecx, r13d
0x140026cd8  call    cs:__imp_VdsTraceEx
0x140026cde  mov     [rsi+68h], r12d
0x140026ce2  mov     rcx, [rsi+60h]; hEvent
0x140026ce6  call    cs:__imp_SetEvent
0x140026cec  jmp     loc_140027200
0x140026cf1  cmp     dword ptr [rbx], 0
0x140026cf4  jz      short loc_140026D02
0x140026cf6  call    cs:__imp_GetCurrentThreadId
0x140026cfc  mov     cs:?g_dwThreadIdExclusiveLock@@3KC, eax; ulong volatile g_dwThreadIdExclusiveLock
0x140026d02  mov     rcx, [rsp+180h+var_148]
0x140026d07  mov     rax, [rcx]
0x140026d0a  lea     r8, [rbp+80h+var_100]
0x140026d0e  lea     rdx, [rsp+180h+var_150]
0x140026d13  mov     rax, [rax+20h]
0x140026d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026d1c  mov     r12d, eax
0x140026d1f  mov     eax, [rsp+180h+var_150]
0x140026d23  test    r12d, r12d
0x140026d26  js      loc_1400271B5
0x140026d2c  test    eax, eax
0x140026d2e  js      loc_1400271B5
0x140026d34  cmp     dword ptr [r15+50h], 1
0x140026d39  jnz     short loc_140026D4E
0x140026d3b  mov     dword ptr [rsi+6Ch], 64h ; 'd'
0x140026d42  mov     dword ptr [rsi+68h], 0
0x140026d49  jmp     loc_1400271E0
0x140026d4e  cmp     dword ptr [rbx], 0
0x140026d51  jz      loc_140026E7C
0x140026d57  call    cs:__imp_GarbageCollectDriveLetters
0x140026d5d  lea     rcx, [r15+18h]
0x140026d61  call    cs:__imp_DeleteBcdObjects
0x140026d67  test    eax, eax
0x140026d69  jns     short loc_140026D83
0x140026d6b  mov     r9d, eax
0x140026d6e  lea     r8, aCvdsdisklunPos_11; "CVdsDiskLun::PostCleanDiskHandler, 2, s"...
0x140026d75  mov     edx, 1
0x140026d7a  mov     ecx, r13d
0x140026d7d  call    cs:__imp_VdsTraceEx
0x140026d83  lea     r13, [r15+8]
0x140026d87  xor     r9d, r9d; int
0x140026d8a  xor     r8d, r8d; int
0x140026d8d  mov     rdx, r13; struct _GUID *
0x140026d90  mov     rcx, [r15+40h]; lpFileName
0x140026d94  call    ?ClaimRawDisk@CVdsService@@SAKPEAGAEAU_GUID@@HH@Z; CVdsService::ClaimRawDisk(ushort *,_GUID &,int,int)
0x140026d99  test    eax, eax
0x140026d9b  jz      short loc_140026DC3
0x140026d9d  mov     dword ptr [rsi+68h], 8000FFFFh
0x140026da4  mov     rcx, [rsi+60h]; hEvent
0x140026da8  call    cs:__imp_SetEvent
0x140026dae  mov     rdx, r13; struct _GUID *
0x140026db1  mov     ecx, 9; unsigned int
0x140026db6  call    ?SendDiskNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendDiskNotification(ulong,_GUID &)
0x140026dbb  xor     r14d, r14d
0x140026dbe  jmp     loc_1400271EA
0x140026dc3  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140026dca  call    cs:__imp_EnterCriticalSection
0x140026dd0  nop
0x140026dd1  mov     r14, [rbp+80h+arg_0]
0x140026dd8  mov     r14, [r14+0D0h]
0x140026ddf  test    r14, r14
0x140026de2  jz      short loc_140026DF5
0x140026de4  mov     rax, [r14]
0x140026de7  mov     rcx, r14
0x140026dea  mov     rax, [rax+8]
0x140026dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026df3  jmp     short loc_140026E0B
0x140026df5  lea     r8, aCvdsdisklunPos_4; "CVdsDiskLun::PostCleanDiskHandler, 3, m"...
0x140026dfc  mov     edx, 1
0x140026e01  lea     ecx, [rdx+5Dh]
0x140026e04  call    cs:__imp_VdsTraceEx
0x140026e0a  nop
0x140026e0b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140026e12  call    cs:__imp_LeaveCriticalSection
0x140026e18  test    r14, r14
0x140026e1b  jz      short loc_140026E76
0x140026e1d  xor     r9d, r9d; int
0x140026e20  xor     r8d, r8d; struct IVdsProvider *
0x140026e23  mov     rdx, r14; struct IUnknown *
0x140026e26  mov     rcx, r13; struct _GUID *
0x140026e29  call    ?ResetDiskWrapper@CVdsService@@SAJAEAU_GUID@@PEAUIUnknown@@PEAUIVdsProvider@@H@Z; CVdsService::ResetDiskWrapper(_GUID &,IUnknown *,IVdsProvider *,int)
0x140026e2e  mov     r12d, eax
0x140026e31  mov     rax, [r14]
0x140026e34  mov     rcx, r14
0x140026e37  mov     rax, [rax+10h]
0x140026e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e40  test    r12d, r12d
0x140026e43  jns     short loc_140026E76
0x140026e45  mov     r9d, r12d
0x140026e48  lea     r8, aCvdsdisklunPos_1; "CVdsDiskLun::PostCleanDiskHandler, 4, %"...
0x140026e4f  xor     edx, edx
0x140026e51  lea     ecx, [rdx+5Eh]
0x140026e54  call    cs:__imp_VdsTraceEx
0x140026e5a  mov     dword ptr [rsi+68h], 80042419h
0x140026e61  mov     rcx, [rsi+60h]; hEvent
0x140026e65  call    cs:__imp_SetEvent
0x140026e6b  mov     r14d, 80042419h
0x140026e71  jmp     loc_1400271EA
0x140026e76  mov     r13d, 5Eh ; '^'
0x140026e7c  mov     [rbp+80h+arg_18], 0
0x140026e87  mov     r14d, 1
0x140026e8d  cmp     [r15+58h], r14d
0x140026e91  jnz     short loc_140026EFC
0x140026e93  movups  xmm0, xmmword ptr [r15+8]
0x140026e98  movdqu  xmmword ptr [rsp+180h+var_120.Data1], xmm0
0x140026e9e  lea     r8, [rbp+80h+arg_8]; unsigned int *
0x140026ea5  lea     rdx, [rbp+80h+arg_10]; unsigned __int16 **
0x140026eac  lea     rcx, [rsp+180h+var_120]; struct _GUID
0x140026eb1  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@U_GUID@@AEAPEAGAEAK@Z; CVdsService::FindRawDisk(_GUID,ushort * &,ulong &)
0x140026eb6  mov     [rbp+80h+arg_18], rax
0x140026ebd  test    rax, rax
0x140026ec0  jnz     short loc_140026EF5
0x140026ec2  mov     [rsp+180h+var_150], 80042405h
0x140026eca  mov     r9d, r12d
0x140026ecd  lea     r8, aCvdsdisklunPos_8; "CVdsDiskLun::PostCleanDiskHandler, 5, %"...
0x140026ed4  xor     edx, edx
0x140026ed6  mov     ecx, r13d
0x140026ed9  call    cs:__imp_VdsTraceEx
0x140026edf  mov     eax, [rsp+180h+var_150]
0x140026ee3  mov     [rsi+68h], eax
0x140026ee6  mov     rcx, [rsi+60h]; hEvent
0x140026eea  call    cs:__imp_SetEvent
0x140026ef0  jmp     loc_140026DBB
0x140026ef5  mov     [rax+158h], r14d
0x140026efc  cmp     dword ptr [rbx], 0
0x140026eff  jz      short loc_140026F1C
0x140026f01  xor     eax, eax
0x140026f03  xchg    eax, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x140026f09  xor     r8d, r8d; lpPreviousCount
0x140026f0c  mov     edx, r14d; lReleaseCount
0x140026f0f  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hSemaphore
0x140026f16  call    cs:__imp_ReleaseSemaphore
0x140026f1c  cmp     [r15+58h], r14d
0x140026f20  jnz     loc_14002710A
0x140026f26  lea     r8, [rsp+180h+hFile]
0x140026f2b  mov     edx, 0C0000000h
0x140026f30  mov     rcx, [rbp+80h+arg_10]
0x140026f37  call    cs:__imp_OpenDevice
0x140026f3d  test    eax, eax
0x140026f3f  jz      short loc_140026F69
0x140026f41  jle     short loc_140026F4B
0x140026f43  movzx   eax, ax
0x140026f46  or      eax, 80070000h
0x140026f4b  lea     r8, aCvdsdisklunPos; "CVdsDiskLun::PostCleanDiskHandler, 6, %"...
0x140026f52  mov     [rsp+180h+var_150], eax
0x140026f56  mov     r9d, eax
0x140026f59  mov     ecx, r13d
0x140026f5c  xor     edx, edx
0x140026f5e  call    cs:__imp_VdsTraceEx
0x140026f64  jmp     loc_140027112
0x140026f69  lea     rdx, [rbp+80h+var_E0]
0x140026f6d  mov     rcx, [rsp+180h+hFile]
0x140026f72  call    cs:__imp_GetPartitionInformation
0x140026f78  test    eax, eax
0x140026f7a  jz      short loc_140026F8F
0x140026f7c  jle     short loc_140026F86
0x140026f7e  movzx   eax, ax
0x140026f81  or      eax, 80070000h
0x140026f86  lea     r8, aCvdsdisklunPos_5; "CVdsDiskLun::PostCleanDiskHandler, 7, %"...
0x140026f8d  jmp     short loc_140026F52
0x140026f8f  mov     r14d, 100000h
0x140026f95  test    rdi, rdi
0x140026f98  jnz     short loc_140026FFE
0x140026f9a  cmp     r14d, 200h
0x140026fa1  jb      short loc_140026FE0
0x140026fa3  call    cs:__imp_GetProcessHeap
0x140026fa9  mov     rcx, rax
0x140026fac  mov     r8d, r14d
0x140026faf  lea     edx, [rdi+8]
0x140026fb2  call    cs:__imp_VdsHeapAlloc
0x140026fb8  mov     rdx, rax
0x140026fbb  lea     rcx, [rsp+180h+var_130]
0x140026fc0  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x140026fc5  mov     rdi, [rsp+180h+var_130]
0x140026fca  test    rdi, rdi
0x140026fcd  setz    al
0x140026fd0  mov     ecx, r14d
0x140026fd3  shr     ecx, 1
0x140026fd5  test    al, al
0x140026fd7  cmovz   ecx, r14d
0x140026fdb  mov     r14d, ecx
0x140026fde  jmp     short loc_140026F95
0x140026fe0  call    cs:__imp_GetLastError
0x140026fe6  test    eax, eax
0x140026fe8  jle     short loc_140026FF2
0x140026fea  movzx   eax, ax
0x140026fed  or      eax, 80070000h
0x140026ff2  lea     r8, aCvdsdisklunPos_6; "CVdsDiskLun::PostCleanDiskHandler, 8, %"...
0x140026ff9  jmp     loc_140026F52
0x140026ffe  mov     r8d, r14d; Size
0x140027001  xor     edx, edx; Val
0x140027003  mov     rcx, rdi; void *
0x140027006  call    memset_0
0x14002700b  xor     r13d, r13d
0x14002700e  mov     [rbp+80h+arg_8], r13d
0x140027015  xor     ebx, ebx
0x140027017  mov     rdx, [rbp+80h+var_D0]
0x14002701b  mov     rcx, rdx
0x14002701e  sub     rcx, r13
0x140027021  mov     eax, r14d
0x140027024  cmp     rax, rcx
0x140027027  jle     short loc_14002702F
0x140027029  mov     r14d, edx
0x14002702c  sub     r14d, r13d
0x14002702f  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x140027038  lea     r9, [rsp+180h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002703d  mov     r8d, r14d; nNumberOfBytesToWrite
0x140027040  mov     rdx, rdi; lpBuffer
0x140027043  mov     rcx, [rsp+180h+hFile]; hFile
0x140027048  call    cs:__imp_WriteFile
0x14002704e  cmp     eax, 1
0x140027051  jnz     loc_14002718B
0x140027057  mov     eax, [rsp+180h+NumberOfBytesWritten]
0x14002705b  add     rbx, rax
0x14002705e  xor     r9d, r9d; dwMoveMethod
0x140027061  xor     r8d, r8d; lpNewFilePointer
0x140027064  mov     rdx, rbx; liDistanceToMove
0x140027067  mov     rcx, [rsp+180h+hFile]; hFile
0x14002706c  call    cs:__imp_SetFilePointerEx
0x140027072  cmp     eax, 1
0x140027075  jnz     loc_140027170
0x14002707b  mov     eax, r14d
0x14002707e  add     r13, rax
0x140027081  xorps   xmm1, xmm1
0x140027084  cvtsi2ss xmm1, r13
0x140027089  mov     rax, [rbp+80h+var_D0]
0x14002708d  xorps   xmm0, xmm0
0x140027090  cvtsi2ss xmm0, rax
0x140027095  divss   xmm1, xmm0
0x140027099  mulss   xmm1, cs:__real@42c80000
0x1400270a1  cvttss2si rcx, xmm1
0x1400270a6  cmp     ecx, [rbp+80h+arg_8]
0x1400270ac  jz      short loc_1400270C2
0x1400270ae  mov     [rbp+80h+arg_8], ecx
0x1400270b4  mov     dword ptr [rsi+68h], 80042409h
0x1400270bb  mov     [rsi+6Ch], ecx
0x1400270be  mov     rax, [rbp+80h+var_D0]
0x1400270c2  mov     rcx, rsi; this
0x1400270c5  cmp     r13, rax
0x1400270c8  jge     short loc_1400270EA
0x1400270ca  call    ?IsCancelRequested@CVdsAsyncObject@@QEAAHXZ; CVdsAsyncObject::IsCancelRequested(void)
0x1400270cf  test    eax, eax
0x1400270d1  jz      short loc_1400270EF
0x1400270d3  mov     [rsp+180h+var_150], 4241Ah
0x1400270db  mov     r9d, r12d
0x1400270de  lea     r8, aCvdsdisklunPos_0; "CVdsDiskLun::PostCleanDiskHandler, 11, "...
0x1400270e5  jmp     loc_1400271AB
0x1400270ea  call    ?SetCancelTooLate@CVdsAsyncObject@@QEAAXH@Z; CVdsAsyncObject::SetCancelTooLate(int)
0x1400270ef  mov     rdx, [rbp+80h+var_D0]
0x1400270f3  cmp     r13, rdx
0x1400270f6  jl      loc_14002701B
0x1400270fc  lea     rdx, [r15+8]; struct _GUID *
  ... truncated ...
```
