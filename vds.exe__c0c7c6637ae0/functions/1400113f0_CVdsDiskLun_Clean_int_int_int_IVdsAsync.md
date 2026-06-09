# CVdsDiskLun::Clean(int,int,int,IVdsAsync * *)

- ea: `0x1400113f0`
- end: `0x140011a56`
- name: `?Clean@CVdsDiskLun@@UEAAJHHHPEAPEAUIVdsAsync@@@Z`
- size: `1638`
- prototype: `__int64 __fastcall(CVdsDiskLun *this, unsigned int, unsigned int, unsigned int, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400025b0`
- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x14000d1c0`
- `0x14000e270`
- `0x14000f930`
- `0x14000f98c`
- `0x140010b04`
- `0x1400113f0`
- `0x140011a60`
- `0x140012c48`
- `0x140012c70`
- `0x140028f84`
- `0x14002e123`
- `0x140035bd4`
- `0x140038618`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011882`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140011882`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400116da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400116da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140011995`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140011995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001185c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400118d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011927`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001185c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400118d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140011927`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400114f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400118a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400114f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400118a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400115f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400116a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400116a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400117fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400117fa`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140011974`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400119bf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140011974`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1400119bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011888`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011888`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400117da`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400117da`
- `vdsutil!VdsHeapAlloc` at `0x1400116b3`
- `vdsutil!VdsHeapAlloc` at `0x1400116b3`
- `vdsutil!VdsTraceEx` at `0x140011519`
- `vdsutil!VdsTraceEx` at `0x140011557`
- `vdsutil!VdsTraceEx` at `0x140011593`
- `vdsutil!VdsTraceEx` at `0x140011637`
- `vdsutil!VdsTraceEx` at `0x140011681`
- `vdsutil!VdsTraceEx` at `0x14001171b`
- `vdsutil!VdsTraceEx` at `0x14001181e`
- `vdsutil!VdsTraceEx` at `0x1400118c3`
- `vdsutil!VdsTraceEx` at `0x140011918`
- `vdsutil!VdsTraceEx` at `0x14001195c`
- `vdsutil!VdsTraceEx` at `0x140011519`
- `vdsutil!VdsTraceEx` at `0x140011557`
- `vdsutil!VdsTraceEx` at `0x140011593`
- `vdsutil!VdsTraceEx` at `0x140011637`
- `vdsutil!VdsTraceEx` at `0x140011681`
- `vdsutil!VdsTraceEx` at `0x14001171b`
- `vdsutil!VdsTraceEx` at `0x14001181e`
- `vdsutil!VdsTraceEx` at `0x1400118c3`
- `vdsutil!VdsTraceEx` at `0x140011918`
- `vdsutil!VdsTraceEx` at `0x14001195c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140011446`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140011446`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140011a2e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140011a2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsDiskLun::Clean(
        CVdsDiskLun *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        struct IVdsAsync **a5)
{
  int v6; // edi
  char *v7; // rbx
  int v8; // eax
  int v9; // r15d
  struct IVdsAsync *Instance; // rax
  struct IVdsAsync *v11; // r14
  const char *v12; // r8
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  _DWORD *v15; // rsi
  HANDLE EventW; // rax
  void *v17; // r12
  signed int LastError; // eax
  __int64 v19; // rax
  BOOL v20; // ecx
  bool v21; // zf
  int v22; // ecx
  HANDLE v23; // rax
  HANDLE v24; // rbx
  signed int v25; // eax
  int v26; // r15d
  CVdsServiceModule *v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  CVdsServiceModule *v31; // rcx
  struct IUnknown *v32; // rdx
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h]
  unsigned int v36; // [rsp+40h] [rbp-C0h]
  struct IUnknown *v37; // [rsp+48h] [rbp-B8h] BYREF
  void *v38; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, struct IUnknown **); // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hThread; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  DWORD ThreadId; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v44; // [rsp+7Ch] [rbp-84h]
  unsigned int v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  struct IVdsAsync **v47; // [rsp+90h] [rbp-70h]
  _BYTE v48[24]; // [rsp+98h] [rbp-68h] BYREF
  __int128 Buf1; // [rsp+B0h] [rbp-50h] BYREF
  int v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+F4h] [rbp-Ch]
  int v53; // [rsp+F8h] [rbp-8h]
  __int64 v54; // [rsp+FCh] [rbp-4h]
  int v55; // [rsp+104h] [rbp+4h]
  LPVOID pv; // [rsp+108h] [rbp+8h]
  LPVOID v57; // [rsp+110h] [rbp+10h]
  LPVOID v58; // [rsp+118h] [rbp+18h]
  LPVOID v59; // [rsp+120h] [rbp+20h]
  wchar_t *String1; // [rsp+128h] [rbp+28h]

  v36 = a4;
  v44 = a3;
  v45 = a2;
  v47 = a5;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v48, 0x5Eu, "CVdsDiskLun::Clean()");
  v46 = 0;
  v42 = 0;
  hThread = 0;
  v38 = 0;
  v40 = 0;
  v37 = 0;
  v39 = 0;
  memset_0(&Buf1, 0, 0x80u);
  ThreadId = 0;
  v34 = 0;
  v35 = 0;
  v6 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v34);
  if ( v6 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v7 = (char *)this - 32;
    v8 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 32));
    v6 = v8;
    if ( v8 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 1, hr=%lX", v8);
      if ( v6 == -2147212283 )
        v6 = -2147212277;
      goto LABEL_6;
    }
    if ( !a5 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 2");
      v6 = -2147024809;
LABEL_6:
      LeaveCriticalSection(&g_GlobalCriticalSection);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v34);
LABEL_61:
      CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v40);
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v38);
      CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&hThread);
      goto LABEL_62;
    }
    *a5 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 24) + 24LL))(
           *((_QWORD *)this + 24),
           &Buf1);
    if ( v6 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 3, %lX", (unsigned int)v6);
      goto LABEL_6;
    }
    if ( !String1 || (v9 = 1, !CVdsService::FindRawDisk(String1)) )
      v9 = 0;
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v57 )
    {
      CoTaskMemFree(v57);
      v57 = 0;
    }
    if ( v58 )
    {
      CoTaskMemFree(v58);
      v58 = 0;
    }
    if ( v59 )
    {
      CoTaskMemFree(v59);
      v59 = 0;
    }
    v39 = String1;
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v6 = -2147212223;
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 4");
      goto LABEL_6;
    }
    if ( v50 == 4 )
    {
      v6 = -2147211254;
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 4.1, %lX", 2147756042LL);
      goto LABEL_6;
    }
    Instance = (struct IVdsAsync *)VdsCreateInstance(VDS_OT_ASYNC);
    v11 = Instance;
    if ( !Instance )
    {
      v12 = "CVdsDiskLun::Clean, 5";
LABEL_28:
      v6 = -2147024882;
      VdsTraceEx(94, 0, v12);
      goto LABEL_6;
    }
    ATL::CComPtrBase<CVdsEnumObject>::Attach(&v42, (__int64)Instance);
    ProcessHeap = GetProcessHeap();
    v14 = VdsHeapAlloc(ProcessHeap, 8, 96);
    v15 = (_DWORD *)v14;
    if ( !v14 )
    {
      v12 = "CVdsDiskLun::Clean, 6";
      goto LABEL_28;
    }
    v46 = v14;
    EventW = CreateEventW(0, 1, 0, 0);
    CVdsHandleImpl<0>::operator=(&v38, EventW);
    v17 = v38;
    if ( !v38 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 7, %lX", v6);
      goto LABEL_6;
    }
    *(_OWORD *)(v15 + 2) = Buf1;
    *((_BYTE *)v15 + 24) = 1;
    v15[7] = v52;
    if ( v52 == 1 )
    {
      v15[8] = v53;
    }
    else if ( v52 == 2 )
    {
      v15[8] = v53;
      *(_QWORD *)(v15 + 9) = v54;
      v15[11] = v55;
    }
    *(_QWORD *)v15 = v7;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this - 32);
    *((_QWORD *)v15 + 8) = String1;
    String1 = 0;
    v19 = v42;
    *((_QWORD *)v15 + 9) = v42;
    v15[23] = 0;
    v20 = v51 != 12;
    v15[20] = v20;
    if ( v9 || (v21 = !v20, v22 = 1, !v21) )
      v22 = 0;
    v15[21] = v22;
    v15[22] = v36;
    v38 = 0;
    *(_QWORD *)(v19 + 96) = v17;
    v23 = CreateThread(0, 0, CVdsDiskLun::PostCleanDiskHandlerEntry, v15, 4u, &ThreadId);
    CVdsHandleImpl<0>::operator=(&hThread, v23);
    v24 = hThread;
    if ( !hThread )
    {
      v25 = GetLastError();
      v6 = v25;
      if ( v25 > 0 )
        v6 = (unsigned __int16)v25 | 0x80070000;
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 8, %lX", v6);
      if ( *(_QWORD *)v15 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 16LL))(*(_QWORD *)v15);
        *(_QWORD *)v15 = 0;
      }
      goto LABEL_6;
    }
    v26 = 0;
    v46 = 0;
    v39 = 0;
    v42 = 0;
    LeaveCriticalSection(&g_GlobalCriticalSection);
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v34);
    CVdsServiceModule::StopAcceptingStop(v27);
    if ( v15[21] )
    {
      WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF);
      g_dwThreadIdExclusiveLock = GetCurrentThreadId();
      v26 = 1;
    }
    EnterCriticalSection(&g_GlobalCriticalSection);
    v28 = *((_QWORD *)this + 26);
    if ( v28 )
    {
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **)))(*(_QWORD *)v28 + 96LL))(
              v28,
              v45,
              v44,
              v36,
              &v40);
      v6 = v29;
      if ( v29 >= 0 )
      {
        LeaveCriticalSection(&g_GlobalCriticalSection);
        v30 = (**v40)(v40, &IID_IUnknown, &v37);
        if ( v30 >= 0 )
        {
          v32 = v37;
          v37 = 0;
          CWrapperBase::SetObjectAndService((CWrapperBase *)&v11[8], v32, *((struct CVdsService **)this + 23));
          ResumeThread(v24);
          *v47 = v11;
          ((void (__fastcall *)(struct IVdsAsync *))v11->lpVtbl->AddRef)(v11);
          v6 = 0;
          goto LABEL_61;
        }
        VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 12, %lX", v30);
        v6 = -2147211946;
LABEL_57:
        v15[23] = 1;
        ResumeThread(v24);
        if ( v26 )
        {
          _InterlockedExchange((volatile __int32 *)&g_dwThreadIdExclusiveLock, 0);
          ReleaseSemaphore(g_hExclusiveOperationSem, 1, 0);
        }
        CVdsServiceModule::ResumeAcceptingStop(v31);
        goto LABEL_61;
      }
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 10, %lX", v29);
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::Clean, 9, %lX", v6);
      v6 = -2147212277;
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
    goto LABEL_57;
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v34);
  CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v39);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v40);
  CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&v38);
  CVdsHandleImpl<0>::~CVdsHandleImpl<0>(&hThread);
LABEL_62:
  ATL::CComPtrBase<CVdsEnumObject>::~CComPtrBase<CVdsEnumObject>(&v42);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(&v46);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v48);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400113f0  push    rbp
0x1400113f2  push    rbx
0x1400113f3  push    rsi
0x1400113f4  push    rdi
0x1400113f5  push    r12
0x1400113f7  push    r13
0x1400113f9  push    r14
0x1400113fb  push    r15
0x1400113fd  lea     rbp, [rsp-48h]
0x140011402  sub     rsp, 148h
0x140011409  mov     rax, cs:__security_cookie
0x140011410  xor     rax, rsp
0x140011413  mov     [rbp+80h+var_48], rax
0x140011417  mov     [rsp+180h+var_140], r9d
0x14001141c  mov     [rsp+180h+var_104], r8d
0x140011421  mov     [rbp+80h+var_100], edx
0x140011424  mov     r13, rcx
0x140011427  mov     rsi, [rbp+80h+arg_20]
0x14001142e  mov     [rbp+80h+var_F0], rsi
0x140011432  lea     r8, aCvdsdisklunCle_12; "CVdsDiskLun::Clean()"
0x140011439  mov     r15d, 5Eh ; '^'
0x14001143f  mov     edx, r15d
0x140011442  lea     rcx, [rbp+80h+var_E8]
0x140011446  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001144c  nop
0x14001144d  xor     r12d, r12d
0x140011450  mov     [rbp+80h+var_F8], r12
0x140011454  mov     [rsp+180h+var_110], r12
0x140011459  mov     [rsp+180h+hThread], r12
0x14001145e  mov     [rsp+180h+var_130], r12
0x140011463  mov     [rsp+180h+var_120], r12
0x140011468  mov     [rsp+180h+var_138], r12
0x14001146d  mov     [rsp+180h+var_128], r12
0x140011472  xor     edx, edx; Val
0x140011474  lea     r8d, [r15+22h]; Size
0x140011478  lea     rcx, [rbp+80h+Buf1]; void *
0x14001147c  call    memset_0
0x140011481  mov     [rsp+180h+ThreadId], r12d
0x140011486  mov     [rsp+180h+var_150], r12
0x14001148b  mov     [rsp+180h+var_148], r12d
0x140011490  lea     rcx, [rsp+180h+var_150]; this
0x140011495  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x14001149a  mov     edi, eax
0x14001149c  test    eax, eax
0x14001149e  jns     short loc_1400114E7
0x1400114a0  lea     rcx, [rsp+180h+var_150]; this
0x1400114a5  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400114aa  nop
0x1400114ab  lea     rcx, [rsp+180h+var_128]
0x1400114b0  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x1400114b5  nop
0x1400114b6  lea     rcx, [rsp+180h+var_138]
0x1400114bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400114c0  nop
0x1400114c1  lea     rcx, [rsp+180h+var_120]
0x1400114c6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400114cb  nop
0x1400114cc  lea     rcx, [rsp+180h+var_130]
0x1400114d1  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x1400114d6  nop
0x1400114d7  lea     rcx, [rsp+180h+hThread]
0x1400114dc  call    ??1?$CVdsHandleImpl@$0A@@@QEAA@XZ; CVdsHandleImpl<0>::~CVdsHandleImpl<0>(void)
0x1400114e1  nop
0x1400114e2  jmp     loc_140011A15
0x1400114e7  lea     r14, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x1400114ee  mov     rcx, r14; lpCriticalSection
0x1400114f1  call    cs:__imp_EnterCriticalSection
0x1400114f7  nop
0x1400114f8  lea     rbx, [r13-20h]
0x1400114fc  mov     rcx, rbx; this
0x1400114ff  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140011504  mov     edi, eax
0x140011506  test    eax, eax
0x140011508  jns     short loc_140011546
0x14001150a  mov     r9d, eax
0x14001150d  lea     r8, aCvdsdisklunCle; "CVdsDiskLun::Clean, 1, hr=%lX"
0x140011514  xor     edx, edx
0x140011516  mov     ecx, r15d
0x140011519  call    cs:__imp_VdsTraceEx
0x14001151f  mov     eax, 8004240Bh
0x140011524  cmp     edi, 80042405h
0x14001152a  cmovz   edi, eax
0x14001152d  mov     rcx, r14; lpCriticalSection
0x140011530  call    cs:__imp_LeaveCriticalSection
0x140011536  nop
0x140011537  lea     rcx, [rsp+180h+var_150]; this
0x14001153c  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140011541  jmp     loc_1400119DE
0x140011546  test    rsi, rsi
0x140011549  jnz     short loc_140011564
0x14001154b  lea     r8, aCvdsdisklunCle_6; "CVdsDiskLun::Clean, 2"
0x140011552  xor     edx, edx
0x140011554  mov     ecx, r15d
0x140011557  call    cs:__imp_VdsTraceEx
0x14001155d  mov     edi, 80070057h
0x140011562  jmp     short loc_14001152D
0x140011564  mov     [rsi], r12
0x140011567  mov     rcx, [r13+0C0h]
0x14001156e  mov     rax, [rcx]
0x140011571  lea     rdx, [rbp+80h+Buf1]
0x140011575  mov     rax, [rax+18h]
0x140011579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001157e  mov     edi, eax
0x140011580  test    eax, eax
0x140011582  jns     short loc_14001159B
0x140011584  lea     r8, aCvdsdisklunCle_16; "CVdsDiskLun::Clean, 3, %lX"
0x14001158b  mov     ecx, r15d
0x14001158e  xor     edx, edx
0x140011590  mov     r9d, edi
0x140011593  call    cs:__imp_VdsTraceEx
0x140011599  jmp     short loc_14001152D
0x14001159b  mov     rcx, [rbp+80h+String1]; String1
0x14001159f  test    rcx, rcx
0x1400115a2  jz      short loc_1400115B4
0x1400115a4  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@PEAG@Z; CVdsService::FindRawDisk(ushort *)
0x1400115a9  test    rax, rax
0x1400115ac  mov     r15d, 1
0x1400115b2  jnz     short loc_1400115B7
0x1400115b4  mov     r15d, r12d
0x1400115b7  mov     rcx, [rbp+80h+pv]; pv
0x1400115bb  test    rcx, rcx
0x1400115be  jz      short loc_1400115CA
0x1400115c0  call    cs:__imp_CoTaskMemFree
0x1400115c6  mov     [rbp+80h+pv], r12
0x1400115ca  mov     rcx, [rbp+80h+var_70]; pv
0x1400115ce  test    rcx, rcx
0x1400115d1  jz      short loc_1400115DD
0x1400115d3  call    cs:__imp_CoTaskMemFree
0x1400115d9  mov     [rbp+80h+var_70], r12
0x1400115dd  mov     rcx, [rbp+80h+var_68]; pv
0x1400115e1  test    rcx, rcx
0x1400115e4  jz      short loc_1400115F0
0x1400115e6  call    cs:__imp_CoTaskMemFree
0x1400115ec  mov     [rbp+80h+var_68], r12
0x1400115f0  mov     rcx, [rbp+80h+var_60]; pv
0x1400115f4  test    rcx, rcx
0x1400115f7  jz      short loc_140011603
0x1400115f9  call    cs:__imp_CoTaskMemFree
0x1400115ff  mov     [rbp+80h+var_60], r12
0x140011603  mov     rax, [rbp+80h+String1]
0x140011607  mov     [rsp+180h+var_128], rax
0x14001160c  mov     r8d, 10h; Size
0x140011612  lea     rdx, GUID_NULL; Buf2
0x140011619  lea     rcx, [rbp+80h+Buf1]; Buf1
0x14001161d  call    memcmp_0
0x140011622  test    eax, eax
0x140011624  jnz     short loc_140011642
0x140011626  mov     edi, 80042441h
0x14001162b  lea     r8, aCvdsdisklunCle_1; "CVdsDiskLun::Clean, 4"
0x140011632  xor     edx, edx
0x140011634  lea     ecx, [rax+5Eh]
0x140011637  call    cs:__imp_VdsTraceEx
0x14001163d  jmp     loc_14001152D
0x140011642  cmp     [rbp+80h+var_C0], 4
0x140011646  jnz     short loc_14001165E
0x140011648  mov     edi, 8004280Ah
0x14001164d  lea     r8, aCvdsdisklunCle_8; "CVdsDiskLun::Clean, 4.1, %lX"
0x140011654  mov     ecx, 5Eh ; '^'
0x140011659  jmp     loc_14001158E
0x14001165e  mov     ecx, 64h ; 'd'; enum _VDS_OBJECT_TYPE
0x140011663  call    ?VdsCreateInstance@@YAPEAXW4_VDS_OBJECT_TYPE@@@Z; VdsCreateInstance(_VDS_OBJECT_TYPE)
0x140011668  mov     r14, rax
0x14001166b  test    rax, rax
0x14001166e  jnz     short loc_140011694
0x140011670  lea     r8, aCvdsdisklunCle_7; "CVdsDiskLun::Clean, 5"
0x140011677  mov     edi, 8007000Eh
0x14001167c  xor     edx, edx
0x14001167e  lea     ecx, [rdx+5Eh]
0x140011681  call    cs:__imp_VdsTraceEx
0x140011687  nop
0x140011688  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x14001168f  jmp     loc_140011530
0x140011694  mov     rdx, r14
0x140011697  lea     rcx, [rsp+180h+var_110]
0x14001169c  call    ?Attach@?$CComPtrBase@VCVdsEnumObject@@@ATL@@QEAAXPEAVCVdsEnumObject@@@Z; ATL::CComPtrBase<CVdsEnumObject>::Attach(CVdsEnumObject *)
0x1400116a1  call    cs:__imp_GetProcessHeap
0x1400116a7  mov     rcx, rax
0x1400116aa  mov     edx, 8
0x1400116af  lea     r8d, [rdx+58h]
0x1400116b3  call    cs:__imp_VdsHeapAlloc
0x1400116b9  mov     rsi, rax
0x1400116bc  test    rax, rax
0x1400116bf  jnz     short loc_1400116CA
0x1400116c1  lea     r8, aCvdsdisklunCle_15; "CVdsDiskLun::Clean, 6"
0x1400116c8  jmp     short loc_140011677
0x1400116ca  mov     [rbp+80h+var_F8], rsi
0x1400116ce  xor     r9d, r9d; lpName
0x1400116d1  xor     r8d, r8d; bInitialState
0x1400116d4  lea     edx, [r9+1]; bManualReset
0x1400116d8  xor     ecx, ecx; lpEventAttributes
0x1400116da  call    cs:__imp_CreateEventW
0x1400116e0  mov     rdx, rax
0x1400116e3  lea     rcx, [rsp+180h+var_130]
0x1400116e8  call    ??4?$CVdsHandleImpl@$0A@@@QEAAPEAXPEAX@Z; CVdsHandleImpl<0>::operator=(void *)
0x1400116ed  mov     r12, [rsp+180h+var_130]
0x1400116f2  test    r12, r12
0x1400116f5  jnz     short loc_140011726
0x1400116f7  call    cs:__imp_GetLastError
0x1400116fd  mov     edi, eax
0x1400116ff  test    eax, eax
0x140011701  jle     short loc_14001170C
0x140011703  movzx   edi, ax
0x140011706  or      edi, 80070000h
0x14001170c  mov     r9d, edi
0x14001170f  lea     r8, aCvdsdisklunCle_11; "CVdsDiskLun::Clean, 7, %lX"
0x140011716  xor     edx, edx
0x140011718  lea     ecx, [rdx+5Eh]
0x14001171b  call    cs:__imp_VdsTraceEx
0x140011721  jmp     loc_140011688
0x140011726  movaps  xmm0, [rbp+80h+Buf1]
0x14001172a  movdqu  xmmword ptr [rsi+8], xmm0
0x14001172f  mov     byte ptr [rsi+18h], 1
0x140011733  mov     eax, [rbp+80h+var_8C]
0x140011736  mov     [rsi+1Ch], eax
0x140011739  cmp     [rbp+80h+var_8C], 1
0x14001173d  jnz     short loc_140011747
0x14001173f  mov     eax, [rbp+80h+var_88]
0x140011742  mov     [rsi+20h], eax
0x140011745  jmp     short loc_140011763
0x140011747  cmp     [rbp+80h+var_8C], 2
0x14001174b  jnz     short loc_140011763
0x14001174d  mov     eax, [rbp+80h+var_88]
0x140011750  mov     [rsi+20h], eax
0x140011753  movsd   xmm0, [rbp+80h+var_84]
0x140011758  movsd   qword ptr [rsi+24h], xmm0
0x14001175d  mov     eax, [rbp+80h+var_7C]
0x140011760  mov     [rsi+2Ch], eax
0x140011763  mov     [rsi], rbx
0x140011766  mov     rax, [rbx]
0x140011769  mov     rcx, rbx
0x14001176c  mov     rax, [rax+8]
0x140011770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011775  mov     rax, [rbp+80h+String1]
0x140011779  mov     [rsi+40h], rax
0x14001177d  xor     edx, edx; dwStackSize
0x14001177f  mov     [rbp+80h+String1], rdx
0x140011783  mov     rax, [rsp+180h+var_110]
0x140011788  mov     [rsi+48h], rax
0x14001178c  mov     [rsi+5Ch], edx
0x14001178f  mov     ecx, edx
0x140011791  cmp     [rbp+80h+var_B0], 0Ch
0x140011795  setnz   cl
0x140011798  mov     [rsi+50h], ecx
0x14001179b  test    r15d, r15d
0x14001179e  jnz     short loc_1400117A7
0x1400117a0  test    ecx, ecx
0x1400117a2  lea     ecx, [rdx+1]
0x1400117a5  jz      short loc_1400117A9
0x1400117a7  mov     ecx, edx
0x1400117a9  mov     [rsi+54h], ecx
0x1400117ac  mov     ecx, [rsp+180h+var_140]
0x1400117b0  mov     [rsi+58h], ecx
0x1400117b3  mov     [rsp+180h+var_130], rdx
0x1400117b8  mov     [rax+60h], r12
0x1400117bc  lea     rax, [rsp+180h+ThreadId]
0x1400117c1  mov     [rsp+180h+lpThreadId], rax; lpThreadId
0x1400117c6  mov     [rsp+180h+dwCreationFlags], 4; dwCreationFlags
0x1400117ce  mov     r9, rsi; lpParameter
0x1400117d1  lea     r8, ?PostCleanDiskHandlerEntry@CVdsDiskLun@@SAKPEAX@Z; lpStartAddress
0x1400117d8  xor     ecx, ecx; lpThreadAttributes
0x1400117da  call    cs:__imp_CreateThread
0x1400117e0  mov     rdx, rax
0x1400117e3  lea     rcx, [rsp+180h+hThread]
0x1400117e8  call    ??4?$CVdsHandleImpl@$0A@@@QEAAPEAXPEAX@Z; CVdsHandleImpl<0>::operator=(void *)
0x1400117ed  mov     rbx, [rsp+180h+hThread]
0x1400117f2  xor     r12d, r12d
0x1400117f5  test    rbx, rbx
0x1400117f8  jnz     short loc_140011844
0x1400117fa  call    cs:__imp_GetLastError
0x140011800  mov     edi, eax
0x140011802  test    eax, eax
0x140011804  jle     short loc_14001180F
0x140011806  movzx   edi, ax
0x140011809  or      edi, 80070000h
0x14001180f  mov     r9d, edi
0x140011812  lea     r8, aCvdsdisklunCle_14; "CVdsDiskLun::Clean, 8, %lX"
0x140011819  xor     edx, edx
0x14001181b  lea     ecx, [rdx+5Eh]
0x14001181e  call    cs:__imp_VdsTraceEx
0x140011824  mov     rcx, [rsi]
0x140011827  test    rcx, rcx
0x14001182a  jz      loc_140011688
0x140011830  mov     rax, [rcx]
0x140011833  mov     rax, [rax+10h]
0x140011837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001183c  mov     [rsi], r12
0x14001183f  jmp     loc_140011688
0x140011844  mov     r15d, r12d
0x140011847  mov     [rbp+80h+var_F8], r12
0x14001184b  mov     [rsp+180h+var_128], r12
0x140011850  mov     [rsp+180h+var_110], r12
0x140011855  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001185c  call    cs:__imp_LeaveCriticalSection
0x140011862  nop
0x140011863  lea     rcx, [rsp+180h+var_150]; this
0x140011868  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14001186d  call    ?StopAcceptingStop@CVdsServiceModule@@QEAAXXZ; CVdsServiceModule::StopAcceptingStop(void)
0x140011872  cmp     [rsi+54h], r12d
0x140011876  jz      short loc_14001189A
0x140011878  or      edx, 0FFFFFFFFh; dwMilliseconds
  ... truncated ...
```
