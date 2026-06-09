# CVdsCallbackObject::Advise(CVdsService *,IVdsAdviseSink *,ulong *)

- ea: `0x14002bfb0`
- end: `0x14002c5c9`
- name: `?Advise@CVdsCallbackObject@@QEAAJPEAVCVdsService@@PEAUIVdsAdviseSink@@PEAK@Z`
- size: `1561`
- prototype: `__int64 __fastcall(CVdsCallbackObject *__hidden this, struct CVdsService *, struct IVdsAdviseSink *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140037980`

## callees

- `0x14002bfb0`
- `0x14002cbe8`
- `0x14002e123`
- `0x14004f9e8`
- `0x14004fbdc`
- `0x140056010`

## import_xrefs

- `msvcrt!rand` at `0x14002c4dc`
- `msvcrt!rand` at `0x14002c4dc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c3dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c3dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002c349`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002c412`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002c349`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002c412`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c176`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c1ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c1e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c176`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c1ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002c1e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c59b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c59b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c040`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002c249`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002c249`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002c258`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002c258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c42c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c42c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c2a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c2a5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14002c302`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14002c302`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c4bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c57b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c4bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c57b`
- `vdsutil!VdsInitializeCriticalSection` at `0x14002c0fe`
- `vdsutil!VdsInitializeCriticalSection` at `0x14002c11b`
- `vdsutil!VdsInitializeCriticalSection` at `0x14002c0fe`
- `vdsutil!VdsInitializeCriticalSection` at `0x14002c11b`
- `vdsutil!VdsTraceEx` at `0x14002c0d2`
- `vdsutil!VdsTraceEx` at `0x14002c14d`
- `vdsutil!VdsTraceEx` at `0x14002c337`
- `vdsutil!VdsTraceEx` at `0x14002c37a`
- `vdsutil!VdsTraceEx` at `0x14002c3a7`
- `vdsutil!VdsTraceEx` at `0x14002c3d3`
- `vdsutil!VdsTraceEx` at `0x14002c443`
- `vdsutil!VdsTraceEx` at `0x14002c470`
- `vdsutil!VdsTraceEx` at `0x14002c51a`
- `vdsutil!VdsTraceEx` at `0x14002c0d2`
- `vdsutil!VdsTraceEx` at `0x14002c14d`
- `vdsutil!VdsTraceEx` at `0x14002c337`
- `vdsutil!VdsTraceEx` at `0x14002c37a`
- `vdsutil!VdsTraceEx` at `0x14002c3a7`
- `vdsutil!VdsTraceEx` at `0x14002c3d3`
- `vdsutil!VdsTraceEx` at `0x14002c443`
- `vdsutil!VdsTraceEx` at `0x14002c470`
- `vdsutil!VdsTraceEx` at `0x14002c51a`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c026`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c2b6`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c026`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14002c2b6`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14002c2da`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14002c2da`
- `vdsutil!?Prev@CRtlListIter@@QEAAAEAV1@XZ` at `0x14002c2c9`
- `vdsutil!?Prev@CRtlListIter@@QEAAAEAV1@XZ` at `0x14002c2c9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002c001`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002c0f0`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002c001`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002c0f0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002c12b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002c166`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002c5a6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002c12b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002c166`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002c5a6`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14002c298`
- `vdsutil!?InsertTailPointer@CRtlList@@QEAAHPEAX@Z` at `0x14002c298`

## string_xrefs

- `0x14002c50f`: `CVdsCallbackObject::Advise, 1 error=%lX, pService=%p, pSink=%p, pulCookie=%p`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsCallbackObject::Advise(
        CVdsCallbackObject *this,
        struct CVdsService *a2,
        struct IVdsAdviseSink *a3,
        unsigned int *a4)
{
  struct CVdsService *v6; // rsi
  struct CVdsCallbackObject *v7; // r14
  char v8; // r13
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  signed int v11; // ebx
  unsigned int v12; // edx
  signed int LastError; // eax
  signed int v14; // eax
  signed int v15; // eax
  HANDLE ProcessHeap; // rax
  _OWORD *v17; // rax
  char *v18; // rbx
  void *EntryPointer; // rsi
  HANDLE Thread; // rax
  signed int v21; // eax
  DWORD v22; // eax
  signed int v23; // eax
  DWORD v24; // eax
  unsigned int v25; // ebx
  unsigned __int16 v26; // si
  const char *v27; // r8
  char *v28; // rcx
  __int128 v30; // [rsp+48h] [rbp-79h] BYREF
  __int128 v31; // [rsp+58h] [rbp-69h] BYREF
  char *v32; // [rsp+68h] [rbp-59h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-51h]
  __int128 v34; // [rsp+78h] [rbp-49h] BYREF
  HANDLE hObject[2]; // [rsp+88h] [rbp-39h]
  HANDLE hEvent[2]; // [rsp+98h] [rbp-29h]
  HANDLE v37[2]; // [rsp+A8h] [rbp-19h]
  __int128 v38; // [rsp+B8h] [rbp-9h]
  _BYTE v39[64]; // [rsp+D8h] [rbp+17h] BYREF
  int v40; // [rsp+128h] [rbp+67h]

  v6 = a2;
  v7 = CVdsService::m_pCallbackObject;
  v8 = 0;
  v31 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v39, 0x5Eu, "CVdsCallbackObject::Advise()");
  memset_0(&v34, 0, 0x58u);
  v32 = (char *)v7 + 120;
  CRtlList::End((char *)v7 + 120, &v30);
  v31 = v30;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)v7 + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 72));
  if ( !v6 || !a3 || !a4 )
  {
    v11 = -2147024809;
    VdsTraceEx(
      94,
      0,
      "CVdsCallbackObject::Advise, 1 error=%lX, pService=%p, pSink=%p, pulCookie=%p",
      -2147024809,
      v6,
      a3,
      a4);
    v10 = hObject[0];
    goto LABEL_66;
  }
  *a4 = 0;
  v9 = operator new(0x3A98u);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0x3840u);
    v10[3720] = -1;
    v10[3721] = -1;
    *((_QWORD *)v10 + 1874) = 0;
    *((_QWORD *)v10 + 1861) = 0;
    *((_QWORD *)v10 + 1862) = 0;
  }
  else
  {
    v10 = 0;
  }
  hObject[0] = v10;
  if ( !v10 )
  {
    v11 = -2147024882;
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 2 error=%lX", -2147024882);
LABEL_66:
    if ( v10 )
      CVdsMessageQueue::`scalar deleting destructor'((CVdsMessageQueue *)v10, v12);
    if ( (unsigned __int64)hObject[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[1]);
    if ( (unsigned __int64)hEvent[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hEvent[0]);
    if ( (unsigned __int64)v37[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v37[0]);
    if ( (unsigned __int64)hEvent[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hEvent[1]);
    if ( v8 == 1 )
      (*(void (__fastcall **)(struct CVdsService *))(*(_QWORD *)v6 + 16LL))(v6);
    goto LABEL_78;
  }
  v40 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)&v30, 0x5Eu, "CVdsMessageQueue::Initialize()");
  v11 = VdsInitializeCriticalSection(v10 + 3728);
  if ( v11 || (v10[3748] = 1, (v11 = VdsInitializeCriticalSection(v10 + 3738)) != 0) )
  {
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)&v30);
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 3 error=%lX", (unsigned int)v11);
    goto LABEL_59;
  }
  v10[3749] = 1;
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)&v30);
  hObject[1] = CreateEventW(0, 0, 0, 0);
  if ( !hObject[1] )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 4 error=%lX", (unsigned int)v11);
    goto LABEL_59;
  }
  hEvent[0] = CreateEventW(0, 0, 0, 0);
  if ( !hEvent[0] )
  {
    v14 = GetLastError();
    v11 = v14;
    if ( v14 > 0 )
      v11 = (unsigned __int16)v14 | 0x80070000;
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 5 error=%lX", (unsigned int)v11);
    goto LABEL_59;
  }
  v37[0] = CreateEventW(0, 0, 0, 0);
  if ( !v37[0] )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 6 error=%lX", (unsigned int)v11);
    goto LABEL_59;
  }
  *(_QWORD *)&v34 = a3;
  DWORD2(v34) = *((_DWORD *)v7 + 38);
  LODWORD(v37[1]) = -2147467259;
  *(_QWORD *)&v38 = v7;
  DWORD2(v38) = 0;
  (*(void (__fastcall **)(struct CVdsService *))(*(_QWORD *)v6 + 8LL))(v6);
  v8 = 1;
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 0, 0x58u);
  if ( v17 )
  {
    *v17 = v34;
    v17[1] = *(_OWORD *)hObject;
    v17[2] = *(_OWORD *)hEvent;
    v17[3] = *(_OWORD *)v37;
    v17[4] = v38;
    *((_QWORD *)v17 + 10) = v6;
    v18 = (char *)v7 + 120;
    CRtlList::InsertTailPointer((struct CVdsCallbackObject *)((char *)v7 + 120), v17);
  }
  else
  {
    SetLastError(0xEu);
    v18 = (char *)v7 + 120;
  }
  CRtlList::End(v18, &v30);
  v31 = v30;
  CRtlListIter::Prev((CRtlListIter *)&v31);
  v40 = 1;
  EntryPointer = CRtlListIter::GetEntryPointer((CRtlListIter *)&v31);
  Thread = CreateThread(0, 0, NotificationThread, EntryPointer, 0, 0);
  *((_QWORD *)EntryPointer + 5) = Thread;
  if ( !Thread )
  {
    v21 = GetLastError();
    v11 = v21;
    if ( v21 > 0 )
      v11 = (unsigned __int16)v21 | 0x80070000;
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 7 error=%lX", (unsigned int)v11);
    goto LABEL_58;
  }
  v22 = WaitForSingleObject(*((HANDLE *)EntryPointer + 6), 0xFFFFFFFF);
  if ( v22 )
  {
    if ( v22 == 128 )
    {
      LOWORD(v11) = 735;
      VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 9, state=%ld", 735);
    }
    else
    {
      LOWORD(v11) = 258;
      if ( v22 != 258 )
      {
        v11 = GetLastError();
        VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 8, error=%ld", v11);
        if ( v11 > 0 )
          goto LABEL_42;
LABEL_58:
        v6 = a2;
LABEL_59:
        if ( v11 >= 0 )
          goto LABEL_78;
        if ( v40 == 1 )
        {
          v30 = v31;
          VdsNotificationClientList::RemoveClient(v32, &v30);
        }
        goto LABEL_66;
      }
      VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 10, state=%ld", 258);
    }
LABEL_42:
    v11 = (unsigned __int16)v11;
LABEL_57:
    v11 |= 0x80070000;
    goto LABEL_58;
  }
  v11 = *((_DWORD *)EntryPointer + 14);
  if ( v11 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 11 error=%lX", v11);
    if ( !SetEvent(hEvent[0]) )
    {
      v23 = GetLastError();
      v11 = v23;
      if ( v23 > 0 )
        v11 = (unsigned __int16)v23 | 0x80070000;
      VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 12 error=%lX", (unsigned int)v11);
      goto LABEL_58;
    }
    v24 = WaitForSingleObject(*((HANDLE *)EntryPointer + 5), 0xFFFFFFFF);
    if ( !v24 )
      goto LABEL_58;
    if ( v24 == 128 )
    {
      v25 = 735;
      v27 = "CVdsCallbackObject::Advise, 14, state=%ld";
    }
    else
    {
      v25 = 258;
      if ( v24 != 258 )
      {
        v11 = GetLastError();
        VdsTraceEx(94, 0, "CVdsCallbackObject::Advise, 13, error=%ld", v11);
        if ( v11 <= 0 )
          goto LABEL_58;
        v26 = v11;
LABEL_56:
        v11 = v26;
        goto LABEL_57;
      }
      v27 = "CVdsCallbackObject::Advise, 15, state=%ld";
    }
    v26 = v25;
    VdsTraceEx(94, 0, v27, v25);
    goto LABEL_56;
  }
  v11 = 0;
  v28 = (char *)*((_QWORD *)EntryPointer + 6);
  if ( (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v28);
    *((_QWORD *)EntryPointer + 6) = 0;
  }
  *((_DWORD *)EntryPointer + 2) = *((_DWORD *)v7 + 38);
  *a4 = *((_DWORD *)v7 + 38);
  *((_DWORD *)v7 + 38) += rand();
  ((void (__fastcall *)(struct IVdsAdviseSink *))a3->lpVtbl->AddRef)(a3);
LABEL_78:
  LeaveCriticalSection(lpCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002bfb0  mov     rax, rsp
0x14002bfb3  mov     [rax+18h], rbx
0x14002bfb7  mov     [rax+10h], rdx
0x14002bfbb  mov     [rax+8], rcx
0x14002bfbf  push    rbp
0x14002bfc0  push    rsi
0x14002bfc1  push    rdi
0x14002bfc2  push    r12
0x14002bfc4  push    r13
0x14002bfc6  push    r14
0x14002bfc8  push    r15
0x14002bfca  lea     rbp, [rax-5Fh]
0x14002bfce  sub     rsp, 0E0h
0x14002bfd5  mov     r12, r9
0x14002bfd8  mov     r15, r8
0x14002bfdb  mov     rsi, rdx
0x14002bfde  mov     r14, cs:?m_pCallbackObject@CVdsService@@0PEAVCVdsCallbackObject@@EA; CVdsCallbackObject * CVdsService::m_pCallbackObject
0x14002bfe5  xor     ebx, ebx
0x14002bfe7  mov     r13b, bl
0x14002bfea  xorps   xmm0, xmm0
0x14002bfed  movups  [rbp+57h+var_C0], xmm0
0x14002bff1  lea     r8, aCvdscallbackob_2; "CVdsCallbackObject::Advise()"
0x14002bff8  lea     edi, [rbx+5Eh]
0x14002bffb  mov     edx, edi
0x14002bffd  lea     rcx, [rbp+57h+var_40]
0x14002c001  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002c007  nop
0x14002c008  xor     edx, edx; Val
0x14002c00a  lea     r8d, [rbx+58h]; Size
0x14002c00e  lea     rcx, [rbp+57h+var_A0]; void *
0x14002c012  call    memset_0
0x14002c017  lea     rax, [r14+78h]
0x14002c01b  mov     [rbp+57h+var_B0], rax
0x14002c01f  lea     rdx, [rbp+57h+var_D0]
0x14002c023  mov     rcx, rax
0x14002c026  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14002c02c  movaps  xmm0, [rbp+57h+var_D0]
0x14002c030  movdqa  [rbp+57h+var_C0], xmm0
0x14002c035  lea     rax, [r14+48h]
0x14002c039  mov     [rbp+57h+lpCriticalSection], rax
0x14002c03d  mov     rcx, rax; lpCriticalSection
0x14002c040  call    cs:__imp_EnterCriticalSection
0x14002c046  nop
0x14002c047  test    rsi, rsi
0x14002c04a  jz      loc_14002C4F8
0x14002c050  test    r15, r15
0x14002c053  jz      loc_14002C4F8
0x14002c059  test    r12, r12
0x14002c05c  jz      loc_14002C4F8
0x14002c062  mov     [r12], ebx
0x14002c066  mov     ecx, 3A98h; Size
0x14002c06b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002c070  mov     rdi, rax
0x14002c073  mov     [rbp+57h+arg_0], rax
0x14002c077  test    rax, rax
0x14002c07a  jz      short loc_14002C0B2
0x14002c07c  xor     edx, edx; Val
0x14002c07e  mov     r8d, 3840h; Size
0x14002c084  mov     rcx, rax; void *
0x14002c087  call    memset_0
0x14002c08c  or      eax, 0FFFFFFFFh
0x14002c08f  mov     [rdi+3A20h], eax
0x14002c095  mov     [rdi+3A24h], eax
0x14002c09b  mov     [rdi+3A90h], rbx
0x14002c0a2  mov     [rdi+3A28h], rbx
0x14002c0a9  mov     [rdi+3A30h], rbx
0x14002c0b0  jmp     short loc_14002C0B5
0x14002c0b2  mov     rdi, rbx
0x14002c0b5  mov     [rbp+57h+hObject], rdi
0x14002c0b9  test    rdi, rdi
0x14002c0bc  jnz     short loc_14002C0DD
0x14002c0be  mov     ebx, 8007000Eh
0x14002c0c3  mov     r9d, ebx
0x14002c0c6  lea     r8, aCvdscallbackob_26; "CVdsCallbackObject::Advise, 2 error=%lX"
0x14002c0cd  xor     edx, edx
0x14002c0cf  lea     ecx, [rdi+5Eh]
0x14002c0d2  call    cs:__imp_VdsTraceEx
0x14002c0d8  jmp     loc_14002C524
0x14002c0dd  mov     dword ptr [rbp+57h+arg_0], ebx
0x14002c0e0  lea     r8, aCvdsmessageque_0; "CVdsMessageQueue::Initialize()"
0x14002c0e7  mov     edx, 5Eh ; '^'
0x14002c0ec  lea     rcx, [rbp+57h+var_D0]
0x14002c0f0  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002c0f6  nop
0x14002c0f7  lea     rcx, [rdi+3A40h]
0x14002c0fe  call    cs:__imp_VdsInitializeCriticalSection
0x14002c104  mov     ebx, eax
0x14002c106  test    eax, eax
0x14002c108  jnz     short loc_14002C127
0x14002c10a  mov     dword ptr [rdi+3A90h], 1
0x14002c114  lea     rcx, [rdi+3A68h]
0x14002c11b  call    cs:__imp_VdsInitializeCriticalSection
0x14002c121  mov     ebx, eax
0x14002c123  test    eax, eax
0x14002c125  jz      short loc_14002C158
0x14002c127  lea     rcx, [rbp+57h+var_D0]
0x14002c12b  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002c131  test    ebx, ebx
0x14002c133  jle     short loc_14002C13E
0x14002c135  movzx   ebx, bx
0x14002c138  or      ebx, 80070000h
0x14002c13e  lea     r8, aCvdscallbackob_8; "CVdsCallbackObject::Advise, 3 error=%lX"
0x14002c145  mov     r9d, ebx
0x14002c148  xor     edx, edx
0x14002c14a  lea     ecx, [rdx+5Eh]
0x14002c14d  call    cs:__imp_VdsTraceEx
0x14002c153  jmp     loc_14002C483
0x14002c158  mov     dword ptr [rdi+3A94h], 1
0x14002c162  lea     rcx, [rbp+57h+var_D0]
0x14002c166  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002c16c  xor     r9d, r9d; lpName
0x14002c16f  xor     r8d, r8d; bInitialState
0x14002c172  xor     edx, edx; bManualReset
0x14002c174  xor     ecx, ecx; lpEventAttributes
0x14002c176  call    cs:__imp_CreateEventW
0x14002c17c  mov     [rbp+57h+hObject+8], rax
0x14002c180  test    rax, rax
0x14002c183  jnz     short loc_14002C1A3
0x14002c185  call    cs:__imp_GetLastError
0x14002c18b  mov     ebx, eax
0x14002c18d  test    eax, eax
0x14002c18f  jle     short loc_14002C19A
0x14002c191  movzx   ebx, ax
0x14002c194  or      ebx, 80070000h
0x14002c19a  lea     r8, aCvdscallbackob_35; "CVdsCallbackObject::Advise, 4 error=%lX"
0x14002c1a1  jmp     short loc_14002C145
0x14002c1a3  xor     r9d, r9d; lpName
0x14002c1a6  xor     r8d, r8d; bInitialState
0x14002c1a9  xor     edx, edx; bManualReset
0x14002c1ab  xor     ecx, ecx; lpEventAttributes
0x14002c1ad  call    cs:__imp_CreateEventW
0x14002c1b3  mov     [rbp+57h+hEvent], rax
0x14002c1b7  test    rax, rax
0x14002c1ba  jnz     short loc_14002C1DD
0x14002c1bc  call    cs:__imp_GetLastError
0x14002c1c2  mov     ebx, eax
0x14002c1c4  test    eax, eax
0x14002c1c6  jle     short loc_14002C1D1
0x14002c1c8  movzx   ebx, ax
0x14002c1cb  or      ebx, 80070000h
0x14002c1d1  lea     r8, aCvdscallbackob_14; "CVdsCallbackObject::Advise, 5 error=%lX"
0x14002c1d8  jmp     loc_14002C145
0x14002c1dd  xor     r9d, r9d; lpName
0x14002c1e0  xor     r8d, r8d; bInitialState
0x14002c1e3  xor     edx, edx; bManualReset
0x14002c1e5  xor     ecx, ecx; lpEventAttributes
0x14002c1e7  call    cs:__imp_CreateEventW
0x14002c1ed  mov     [rbp+57h+var_70], rax
0x14002c1f1  test    rax, rax
0x14002c1f4  jnz     short loc_14002C217
0x14002c1f6  call    cs:__imp_GetLastError
0x14002c1fc  mov     ebx, eax
0x14002c1fe  test    eax, eax
0x14002c200  jle     short loc_14002C20B
0x14002c202  movzx   ebx, ax
0x14002c205  or      ebx, 80070000h
0x14002c20b  lea     r8, aCvdscallbackob_10; "CVdsCallbackObject::Advise, 6 error=%lX"
0x14002c212  jmp     loc_14002C145
0x14002c217  mov     qword ptr [rbp+57h+var_A0], r15
0x14002c21b  mov     eax, [r14+98h]
0x14002c222  mov     dword ptr [rbp+57h+var_A0+8], eax
0x14002c225  mov     dword ptr [rbp+57h+var_70+8], 80004005h
0x14002c22c  mov     qword ptr [rbp+57h+var_60], r14
0x14002c230  mov     dword ptr [rbp+57h+var_60+8], 0
0x14002c237  mov     rax, [rsi]
0x14002c23a  mov     rcx, rsi
0x14002c23d  mov     rax, [rax+8]
0x14002c241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c246  mov     r13b, 1
0x14002c249  call    cs:__imp_GetProcessHeap
0x14002c24f  mov     rcx, rax; hHeap
0x14002c252  xor     edx, edx; dwFlags
0x14002c254  lea     r8d, [rdx+58h]; dwBytes
0x14002c258  call    cs:__imp_HeapAlloc
0x14002c25e  test    rax, rax
0x14002c261  jz      short loc_14002C2A0
0x14002c263  movaps  xmm0, [rbp+57h+var_A0]
0x14002c267  movups  xmmword ptr [rax], xmm0
0x14002c26a  movaps  xmm1, xmmword ptr [rbp+57h+hObject]
0x14002c26e  movups  xmmword ptr [rax+10h], xmm1
0x14002c272  movaps  xmm0, xmmword ptr [rbp+57h+hEvent]
0x14002c276  movups  xmmword ptr [rax+20h], xmm0
0x14002c27a  movaps  xmm1, xmmword ptr [rbp+57h+var_70]
0x14002c27e  movups  xmmword ptr [rax+30h], xmm1
0x14002c282  movaps  xmm0, [rbp+57h+var_60]
0x14002c286  movups  xmmword ptr [rax+40h], xmm0
0x14002c28a  mov     [rax+50h], rsi
0x14002c28e  mov     rdx, rax
0x14002c291  lea     rbx, [r14+78h]
0x14002c295  mov     rcx, rbx
0x14002c298  call    cs:__imp_?InsertTailPointer@CRtlList@@QEAAHPEAX@Z; CRtlList::InsertTailPointer(void *)
0x14002c29e  jmp     short loc_14002C2AF
0x14002c2a0  mov     ecx, 0Eh; dwErrCode
0x14002c2a5  call    cs:__imp_SetLastError
0x14002c2ab  lea     rbx, [r14+78h]
0x14002c2af  lea     rdx, [rbp+57h+var_D0]
0x14002c2b3  mov     rcx, rbx
0x14002c2b6  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14002c2bc  movaps  xmm0, [rbp+57h+var_D0]
0x14002c2c0  movdqa  [rbp+57h+var_C0], xmm0
0x14002c2c5  lea     rcx, [rbp+57h+var_C0]
0x14002c2c9  call    cs:__imp_?Prev@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Prev(void)
0x14002c2cf  mov     dword ptr [rbp+57h+arg_0], 1
0x14002c2d6  lea     rcx, [rbp+57h+var_C0]
0x14002c2da  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14002c2e0  mov     rsi, rax
0x14002c2e3  mov     [rsp+110h+lpThreadId], 0; lpThreadId
0x14002c2ec  mov     [rsp+110h+dwCreationFlags], 0; dwCreationFlags
0x14002c2f4  mov     r9, rax; lpParameter
0x14002c2f7  lea     r8, ?NotificationThread@@YAKPEAX@Z; lpStartAddress
0x14002c2fe  xor     edx, edx; dwStackSize
0x14002c300  xor     ecx, ecx; lpThreadAttributes
0x14002c302  call    cs:__imp_CreateThread
0x14002c308  mov     [rsi+28h], rax
0x14002c30c  test    rax, rax
0x14002c30f  jnz     short loc_14002C342
0x14002c311  call    cs:__imp_GetLastError
0x14002c317  mov     ebx, eax
0x14002c319  test    eax, eax
0x14002c31b  jle     short loc_14002C326
0x14002c31d  movzx   ebx, ax
0x14002c320  or      ebx, 80070000h
0x14002c326  lea     r8, aCvdscallbackob_12; "CVdsCallbackObject::Advise, 7 error=%lX"
0x14002c32d  mov     ecx, 5Eh ; '^'
0x14002c332  xor     edx, edx
0x14002c334  mov     r9d, ebx
0x14002c337  call    cs:__imp_VdsTraceEx
0x14002c33d  jmp     loc_14002C47F
0x14002c342  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002c345  mov     rcx, [rsi+30h]; hHandle
0x14002c349  call    cs:__imp_WaitForSingleObject
0x14002c34f  test    eax, eax
0x14002c351  jz      short loc_14002C3B5
0x14002c353  cmp     eax, 80h
0x14002c358  jz      short loc_14002C393
0x14002c35a  mov     ebx, 102h
0x14002c35f  cmp     eax, ebx
0x14002c361  jz      short loc_14002C38A
0x14002c363  call    cs:__imp_GetLastError
0x14002c369  mov     ebx, eax
0x14002c36b  mov     r9d, eax
0x14002c36e  lea     r8, aCvdscallbackob_21; "CVdsCallbackObject::Advise, 8, error=%l"...
0x14002c375  xor     edx, edx
0x14002c377  lea     ecx, [rdx+5Eh]
0x14002c37a  call    cs:__imp_VdsTraceEx
0x14002c380  test    ebx, ebx
0x14002c382  jle     loc_14002C47F
0x14002c388  jmp     short loc_14002C3AD
0x14002c38a  lea     r8, aCvdscallbackob_23; "CVdsCallbackObject::Advise, 10, state=%"...
0x14002c391  jmp     short loc_14002C39F
0x14002c393  mov     ebx, 2DFh
0x14002c398  lea     r8, aCvdscallbackob_13; "CVdsCallbackObject::Advise, 9, state=%l"...
0x14002c39f  mov     r9d, ebx
0x14002c3a2  xor     edx, edx
0x14002c3a4  lea     ecx, [rdx+5Eh]
0x14002c3a7  call    cs:__imp_VdsTraceEx
0x14002c3ad  movzx   ebx, bx
0x14002c3b0  jmp     loc_14002C479
0x14002c3b5  mov     ebx, [rsi+38h]
0x14002c3b8  test    ebx, ebx
0x14002c3ba  jns     loc_14002C4AD
0x14002c3c0  mov     r9d, ebx
0x14002c3c3  lea     r8, aCvdscallbackob_9; "CVdsCallbackObject::Advise, 11 error=%l"...
0x14002c3ca  xor     edx, edx
0x14002c3cc  lea     r14d, [rdx+5Eh]
0x14002c3d0  mov     ecx, r14d
0x14002c3d3  call    cs:__imp_VdsTraceEx
0x14002c3d9  mov     rcx, [rbp+57h+hEvent]; hEvent
0x14002c3dd  call    cs:__imp_SetEvent
0x14002c3e3  test    eax, eax
0x14002c3e5  jnz     short loc_14002C40B
0x14002c3e7  call    cs:__imp_GetLastError
0x14002c3ed  mov     ebx, eax
0x14002c3ef  test    eax, eax
0x14002c3f1  jle     short loc_14002C3FC
0x14002c3f3  movzx   ebx, ax
0x14002c3f6  or      ebx, 80070000h
0x14002c3fc  lea     r8, aCvdscallbackob_31; "CVdsCallbackObject::Advise, 12 error=%l"...
0x14002c403  mov     ecx, r14d
0x14002c406  jmp     loc_14002C332
0x14002c40b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002c40e  mov     rcx, [rsi+28h]; hHandle
0x14002c412  call    cs:__imp_WaitForSingleObject
0x14002c418  test    eax, eax
0x14002c41a  jz      short loc_14002C47F
0x14002c41c  cmp     eax, 80h
0x14002c421  jz      short loc_14002C45A
0x14002c423  mov     ebx, 102h
0x14002c428  cmp     eax, ebx
0x14002c42a  jz      short loc_14002C451
0x14002c42c  call    cs:__imp_GetLastError
0x14002c432  mov     ebx, eax
0x14002c434  mov     r9d, eax
0x14002c437  lea     r8, aCvdscallbackob_30; "CVdsCallbackObject::Advise, 13, error=%"...
0x14002c43e  xor     edx, edx
0x14002c440  mov     ecx, r14d
0x14002c443  call    cs:__imp_VdsTraceEx
0x14002c449  test    ebx, ebx
0x14002c44b  jle     short loc_14002C47F
0x14002c44d  mov     esi, ebx
  ... truncated ...
```
