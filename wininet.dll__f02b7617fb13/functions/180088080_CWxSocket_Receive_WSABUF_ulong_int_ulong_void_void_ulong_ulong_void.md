# CWxSocket::Receive(_WSABUF *,ulong,int,ulong *,void (*)(void *,ulong,ulong),void *)

- ea: `0x180088080`
- end: `0x18008866d`
- name: `?Receive@CWxSocket@@QEAAJPEAU_WSABUF@@KHPEAKP6AXPEAXKK@Z2@Z`
- size: `1517`
- prototype: `int(CWxSocket *__hidden this, struct _WSABUF *, unsigned int, int, unsigned int *, void (*)(void *, unsigned int, unsigned int), void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18013e680`

## callees

- `0x180009cf0`
- `0x180087bc4`
- `0x180087f30`
- `0x180087fac`
- `0x180088080`
- `0x180088674`
- `0x18008a970`
- `0x1800e2fe8`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800881ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800881ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800881bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800881bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088578`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008859a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088578`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008859a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180088357`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180088357`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180088505`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180088505`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008820a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008820a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088117`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180088117`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008846d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008846d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180088332`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180088332`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800882c6`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800882c6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008860b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008860b`
- `ntdll!RtlGetLastNtStatus` at `0x18008847f`
- `ntdll!RtlGetLastNtStatus` at `0x18008847f`
- `WS2_32!WSARecv` at `0x1800882f7`
- `WS2_32!WSARecv` at `0x1800882f7`
- `WS2_32!__imp_WSAGetLastError` at `0x180088301`
- `WS2_32!__imp_WSAGetLastError` at `0x180088301`

## pseudocode

```c
__int64 __fastcall CWxSocket::Receive(
        CWxSocket *this,
        struct _WSABUF *a2,
        __int64 a3,
        int a4,
        unsigned int *a5,
        void (*a6)(void *, unsigned int, unsigned int),
        void *a7)
{
  char *v9; // rax
  char *v10; // rbx
  CWxSocket *v11; // rdi
  int v12; // edi
  bool v13; // zf
  RTL_SRWLOCK *v14; // rdi
  __int64 v15; // r8
  unsigned int Error; // r15d
  unsigned int v17; // edx
  DWORD v18; // ebp
  int v19; // eax
  signed int v20; // edi
  __int64 v22; // rdi
  DWORD v23; // ecx
  LARGE_INTEGER v24; // rcx
  __int64 v25; // r9
  LONGLONG *v26; // rax
  LONGLONG v27; // rdx
  LONGLONG **v28; // r8
  unsigned int NewSlot; // [rsp+40h] [rbp-A8h]
  char *v30; // [rsp+48h] [rbp-A0h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-90h] BYREF
  DWORD Flags; // [rsp+60h] [rbp-88h] BYREF
  int v33; // [rsp+68h] [rbp-80h] BYREF
  DWORD NumberOfBytesRecvd; // [rsp+70h] [rbp-78h] BYREF
  char v35[16]; // [rsp+78h] [rbp-70h] BYREF
  LARGE_INTEGER *p_PerformanceCount; // [rsp+88h] [rbp-60h]
  __int64 v37; // [rsp+90h] [rbp-58h]
  int *v38; // [rsp+98h] [rbp-50h]
  __int64 v39; // [rsp+A0h] [rbp-48h]

  v33 = a4;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !a5 )
    return (unsigned int)-2147024809;
  if ( !a6 )
    return (unsigned int)-2147024809;
  PerformanceCount.HighPart = 0;
  v9 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x60u);
  v10 = v9;
  if ( !v9 )
  {
    PerformanceCount.HighPart = 671;
    return (unsigned int)-2147024882;
  }
  *(_QWORD *)v9 = 1;
  *(_QWORD *)(v9 + 44) = 0;
  *((_DWORD *)v9 + 13) = 0;
  *((_DWORD *)v9 + 10) = 0;
  *((_QWORD *)v9 + 7) = 0;
  *((_QWORD *)v9 + 8) = 0;
  *((_QWORD *)v9 + 9) = 0;
  *((_QWORD *)v9 + 10) = 0;
  *((_QWORD *)v9 + 11) = 0;
  *(_OWORD *)(v9 + 8) = 0;
  *(_OWORD *)(v9 + 24) = 0;
  if ( this )
    _InterlockedIncrement((volatile signed __int32 *)this);
  v11 = (CWxSocket *)*((_QWORD *)v9 + 9);
  if ( v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 )
  {
    CWxSocket::~CWxSocket(v11);
    operator delete(v11, 0x270u);
  }
  *((_QWORD *)v10 + 9) = this;
  *((_QWORD *)v10 + 6) = CWxSocket::StaticReceiveCompletion;
  *((_QWORD *)v10 + 8) = a7;
  *((_DWORD *)v10 + 10) = 3;
  *((_QWORD *)v10 + 7) = a6;
  v12 = 0;
  if ( this != (CWxSocket *)-32LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v12 = 1;
  }
  v13 = (*((_DWORD *)this + 61))++ == -1;
  if ( !v13
    && !*((_DWORD *)this + 63)
    && *((_DWORD *)this + 62)
    && (unsigned int)(*((_DWORD *)this + 60) - 1) <= 0xFFFFFFFD )
  {
    *((_DWORD *)this + 63) = 1;
    _InterlockedIncrement((volatile signed __int32 *)this);
    v23 = *((_DWORD *)this + 60);
    PerformanceCount.QuadPart = (LONGLONG)g_pTimerWheel;
    v30 = (char *)g_pTimerWheel + 32;
    NumberOfBytesRecvd = v23;
    Flags = 0;
    while ( 1 )
    {
      NewSlot = CWxTimerWheel::GetNewSlot(v23);
      AcquireSRWLockExclusive((PSRWLOCK)&v30[24 * (NewSlot & 0x3FF)]);
      v24 = PerformanceCount;
      v25 = 24LL * (NewSlot & 0x3FF);
      if ( NewSlot > *(_DWORD *)(PerformanceCount.QuadPart + 12) )
      {
        v26 = (LONGLONG *)((char *)this + 256);
        *((_QWORD *)this + 35) = this;
        v27 = v24.QuadPart + v25 + 16;
        *((_DWORD *)this + 72) = NewSlot;
        *((_DWORD *)this + 73) = 1;
        *((_QWORD *)this + 34) = CWxSocketTimer::Callback;
        v28 = *(LONGLONG ***)(v27 + 8);
        if ( *v28 != (LONGLONG *)v27 )
          __fastfail(3u);
        *v26 = v27;
        *((_QWORD *)this + 33) = v28;
        *v28 = v26;
        *(_QWORD *)(v27 + 8) = v26;
        Flags = 1;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v24.QuadPart + 8)) == 1 )
          break;
      }
      ReleaseSRWLockExclusive((PSRWLOCK)&v30[v25]);
      if ( Flags )
        goto LABEL_17;
      v23 = NumberOfBytesRecvd;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)&v30[v25]);
    CWxTimerWheel::ScheduleTimer((CWxTimerWheel *)PerformanceCount.QuadPart);
  }
LABEL_17:
  if ( v12 && this != (CWxSocket *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v14 = (RTL_SRWLOCK *)((char *)this + 8);
  NumberOfBytesRecvd = 0;
  Flags = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 1);
  if ( !v33 )
    Flags = 32;
  _InterlockedIncrement((volatile signed __int32 *)this + 74);
  if ( *((_QWORD *)this + 2) == -1 )
  {
    Error = 1359;
    if ( *((_DWORD *)this + 75) )
      Error = *((_DWORD *)this + 75);
    goto LABEL_50;
  }
  _InterlockedIncrement((volatile signed __int32 *)v10);
  Error = 997;
  v13 = *((_DWORD *)this + 77) == 0;
  PerformanceCount.QuadPart = 0;
  if ( !v13 )
    Error = 0;
  if ( *((_QWORD *)this + 72) )
  {
    QueryPerformanceCounter(&PerformanceCount);
    *((LARGE_INTEGER *)this + 74) = PerformanceCount;
  }
  if ( (Microsoft_Windows_WinINetEnableBits & 0x800000) != 0 )
  {
    v33 = *((_DWORD *)this + 4);
    PerformanceCount.QuadPart = (LONGLONG)this;
    p_PerformanceCount = &PerformanceCount;
    v37 = 8;
    v38 = &v33;
    v39 = 4;
    McGenEventWrite_EventWriteTransfer(WININET_Context, WININET_SOCKET_RECEIVE_DELAY_STOP, v15, 3, v35);
  }
  StartThreadpoolIo(*((PTP_IO *)this + 3));
  if ( WSARecv(*((_QWORD *)this + 2), a2, 1u, &NumberOfBytesRecvd, &Flags, (LPWSAOVERLAPPED)(v10 + 8), 0) == -1 )
  {
    Error = WSAGetLastError();
    if ( !Error )
      Error = WX_WIN32_FROM_HR(2147549183LL);
    if ( qword_180269EA8 && Error )
    {
      if ( Error == 997 )
        goto LABEL_36;
      if ( Error != 12150 && Error != 12028 && Error != 122 )
      {
        v22 = 16LL * (unsigned __int8)_InterlockedIncrement(&dword_180269EA4);
        GetSystemTimeAsFileTime((LPFILETIME)(v22 + qword_180269EA8));
        *(_DWORD *)(v22 + qword_180269EA8 + 8) = Error;
        *(_DWORD *)(v22 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
        v14 = (RTL_SRWLOCK *)((char *)this + 8);
      }
    }
  }
  if ( Error != 997 )
    CancelThreadpoolIo(*((PTP_IO *)this + 3));
LABEL_36:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
    CWxIoContext::`scalar deleting destructor'((CWxIoContext *)v10, v17);
  if ( !Error )
  {
    v18 = NumberOfBytesRecvd;
    goto LABEL_40;
  }
LABEL_50:
  v18 = 0;
LABEL_40:
  ReleaseSRWLockShared(v14);
  if ( Error == 997 )
  {
    return (unsigned int)-2147023899;
  }
  else
  {
    v19 = (*((__int64 (__fastcall **)(_QWORD, char *, _QWORD))v10 + 6))(Error, v10, v18);
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 >= 0 )
      *a5 = v18;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
    {
      CWxIoContext::~CWxIoContext((CWxIoContext *)v10);
      operator delete(v10, 0x60u);
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180088080  push    rbp
0x180088082  push    rdi
0x180088083  push    r12
0x180088085  push    r14
0x180088087  sub     rsp, 0C8h
0x18008808e  mov     rax, cs:__security_cookie
0x180088095  xor     rax, rsp
0x180088098  mov     [rsp+0E8h+var_40], rax
0x1800880a0  mov     r14, [rsp+0E8h+arg_20]
0x1800880a8  xor     edi, edi
0x1800880aa  mov     [rsp+0E8h+var_80], r9d
0x1800880af  mov     r12, rdx
0x1800880b2  mov     [rsp+0E8h+var_A4], edi
0x1800880b6  mov     rbp, rcx
0x1800880b9  test    r14, r14
0x1800880bc  jz      short loc_1800880C1
0x1800880be  mov     [r14], edi
0x1800880c1  mov     [rsp+0E8h+arg_10], rbx
0x1800880c9  mov     [rsp+0E8h+var_28], rsi
0x1800880d1  mov     [rsp+0E8h+var_30], r13
0x1800880d9  mov     [rsp+0E8h+var_38], r15
0x1800880e1  test    r12, r12
0x1800880e4  jz      loc_1800885D0
0x1800880ea  test    r14, r14
0x1800880ed  jz      loc_1800885E2
0x1800880f3  mov     r15, [rsp+0E8h+arg_28]
0x1800880fb  test    r15, r15
0x1800880fe  jz      loc_1800885F4
0x180088104  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18008810b  xor     edx, edx; dwFlags
0x18008810d  mov     r8d, 60h ; '`'; dwBytes
0x180088113  mov     dword ptr [rsp+0E8h+PerformanceCount+4], edi
0x180088117  call    cs:__imp_HeapAlloc
0x18008811d  mov     rbx, rax
0x180088120  test    rax, rax
0x180088123  jz      loc_180088653
0x180088129  mov     qword ptr [rax], 1
0x180088130  xorps   xmm0, xmm0
0x180088133  xor     eax, eax
0x180088135  mov     r13d, 1
0x18008813b  mov     [rbx+2Ch], rax
0x18008813f  mov     [rbx+34h], eax
0x180088142  mov     [rbx+28h], edi
0x180088145  mov     [rbx+38h], rdi
0x180088149  mov     [rbx+40h], rdi
0x18008814d  mov     [rbx+48h], rdi
0x180088151  mov     [rbx+50h], rdi
0x180088155  mov     [rbx+58h], rdi
0x180088159  movups  xmmword ptr [rbx+8], xmm0
0x18008815d  movups  xmmword ptr [rbx+18h], xmm0
0x180088161  test    rbp, rbp
0x180088164  jz      short loc_18008816A
0x180088166  lock inc dword ptr [rbp+0]
0x18008816a  mov     rdi, [rbx+48h]
0x18008816e  mov     esi, 0FFFFFFFFh
0x180088173  test    rdi, rdi
0x180088176  jz      short loc_180088187
0x180088178  mov     eax, esi
0x18008817a  lock xadd [rdi], eax
0x18008817e  cmp     eax, r13d
0x180088181  jz      loc_1800885B6
0x180088187  mov     [rbx+48h], rbp
0x18008818b  lea     rax, ?StaticReceiveCompletion@CWxSocket@@CAKKPEAVCWxIoContext@@K@Z; CWxSocket::StaticReceiveCompletion(ulong,CWxIoContext *,ulong)
0x180088192  mov     [rbx+30h], rax
0x180088196  mov     rax, [rsp+0E8h+arg_30]
0x18008819e  mov     [rbx+40h], rax
0x1800881a2  mov     dword ptr [rbx+28h], 3
0x1800881a9  mov     [rbx+38h], r15
0x1800881ad  lea     r15, [rbp+20h]
0x1800881b1  xor     edi, edi
0x1800881b3  test    r15, r15
0x1800881b6  jz      short loc_1800881C4
0x1800881b8  mov     rcx, r15; lpCriticalSection
0x1800881bb  call    cs:__imp_EnterCriticalSection
0x1800881c1  mov     edi, r13d
0x1800881c4  add     [rbp+0F4h], r13d
0x1800881cb  jz      short loc_1800881E3
0x1800881cd  cmp     dword ptr [rbp+0FCh], 0
0x1800881d4  jnz     short loc_1800881E3
0x1800881d6  cmp     dword ptr [rbp+0F8h], 0
0x1800881dd  jnz     loc_18008849B
0x1800881e3  test    edi, edi
0x1800881e5  jz      short loc_1800881F5
0x1800881e7  test    r15, r15
0x1800881ea  jz      short loc_1800881F5
0x1800881ec  mov     rcx, r15; lpCriticalSection
0x1800881ef  call    cs:__imp_LeaveCriticalSection
0x1800881f5  xor     eax, eax
0x1800881f7  lea     rdi, [rbp+8]
0x1800881fb  mov     [rsp+0E8h+NumberOfBytesRecvd], eax
0x1800881ff  mov     rcx, rdi; SRWLock
0x180088202  mov     [rsp+0E8h+Flags], eax
0x180088206  mov     [rsp+0E8h+var_A8], eax
0x18008820a  call    cs:__imp_AcquireSRWLockShared
0x180088210  cmp     [rsp+0E8h+var_80], 0
0x180088215  jnz     short loc_18008821F
0x180088217  mov     [rsp+0E8h+Flags], 20h ; ' '
0x18008821f  lock inc dword ptr [rbp+128h]
0x180088226  cmp     qword ptr [rbp+10h], 0FFFFFFFFFFFFFFFFh
0x18008822b  jz      loc_1800883F6
0x180088231  lock inc dword ptr [rbx]
0x180088234  xor     ecx, ecx
0x180088236  mov     r15d, 3E5h
0x18008823c  cmp     [rbp+134h], ecx
0x180088242  mov     [rsp+58h], rcx
0x180088247  cmovnz  r15d, ecx
0x18008824b  cmp     [rbp+240h], rcx
0x180088252  jnz     loc_180088606
0x180088258  cmp     byte ptr cs:Microsoft_Windows_WinINetEnableBits+2, 0
0x18008825f  jge     short loc_1800882C2
0x180088261  mov     eax, [rbp+10h]
0x180088264  lea     rdx, WININET_SOCKET_RECEIVE_DELAY_STOP
0x18008826b  mov     [rsp+0E8h+var_80], eax
0x18008826f  lea     rcx, WININET_Context
0x180088276  lea     rax, [rsp+0E8h+PerformanceCount]
0x18008827b  mov     qword ptr [rsp+0E8h+PerformanceCount], rbp
0x180088280  mov     [rsp+0E8h+var_60], rax
0x180088288  mov     r9d, 3
0x18008828e  lea     rax, [rsp+0E8h+var_80]
0x180088293  mov     [rsp+0E8h+var_58], 8
0x18008829f  mov     [rsp+0E8h+var_50], rax
0x1800882a7  lea     rax, [rsp+0E8h+var_70]
0x1800882ac  mov     [rsp+0E8h+lpFlags], rax
0x1800882b1  mov     [rsp+0E8h+var_48], 4
0x1800882bd  call    McGenEventWrite_EventWriteTransfer
0x1800882c2  mov     rcx, [rbp+18h]; pio
0x1800882c6  call    cs:__imp_StartThreadpoolIo
0x1800882cc  mov     rcx, [rbp+10h]; s
0x1800882d0  lea     rax, [rbx+8]
0x1800882d4  mov     [rsp+0E8h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1800882dd  lea     r9, [rsp+0E8h+NumberOfBytesRecvd]; lpNumberOfBytesRecvd
0x1800882e2  mov     [rsp+0E8h+lpOverlapped], rax; lpOverlapped
0x1800882e7  mov     r8d, r13d; dwBufferCount
0x1800882ea  lea     rax, [rsp+0E8h+Flags]
0x1800882ef  mov     rdx, r12; lpBuffers
0x1800882f2  mov     [rsp+0E8h+lpFlags], rax; lpFlags
0x1800882f7  call    cs:__imp_WSARecv
0x1800882fd  cmp     eax, esi
0x1800882ff  jnz     short loc_180088325
0x180088301  call    cs:__imp_WSAGetLastError
0x180088307  mov     r15d, eax
0x18008830a  test    eax, eax
0x18008830c  jz      loc_180088622
0x180088312  cmp     cs:qword_180269EA8, 0
0x18008831a  jz      short loc_180088325
0x18008831c  test    r15d, r15d
0x18008831f  jnz     loc_18008841E
0x180088325  cmp     r15d, 3E5h
0x18008832c  jz      short loc_180088338
0x18008832e  mov     rcx, [rbp+18h]; pio
0x180088332  call    cs:__imp_CancelThreadpoolIo
0x180088338  mov     eax, esi
0x18008833a  lock xadd [rbx], eax
0x18008833e  cmp     eax, 1
0x180088341  jz      loc_180088411
0x180088347  test    r15d, r15d
0x18008834a  jnz     loc_180088408
0x180088350  mov     ebp, [rsp+0E8h+NumberOfBytesRecvd]
0x180088354  mov     rcx, rdi; SRWLock
0x180088357  call    cs:__imp_ReleaseSRWLockShared
0x18008835d  cmp     r15d, 3E5h
0x180088364  jz      loc_180088634
0x18008836a  mov     rax, [rbx+30h]
0x18008836e  mov     r8d, ebp
0x180088371  mov     rdx, rbx
0x180088374  mov     ecx, r15d
0x180088377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008837c  mov     edi, eax
0x18008837e  test    eax, eax
0x180088380  jle     short loc_18008838B
0x180088382  movzx   edi, ax
0x180088385  or      edi, 80070000h
0x18008838b  test    edi, edi
0x18008838d  js      loc_180088646
0x180088393  mov     [r14], ebp
0x180088396  lock xadd [rbx], esi
0x18008839a  cmp     esi, 1
0x18008839d  jz      short loc_1800883DF
0x18008839f  mov     r15, [rsp+0E8h+var_38]
0x1800883a7  mov     eax, edi
0x1800883a9  mov     r13, [rsp+0E8h+var_30]
0x1800883b1  mov     rsi, [rsp+0E8h+var_28]
0x1800883b9  mov     rbx, [rsp+0E8h+arg_10]
0x1800883c1  mov     rcx, [rsp+0E8h+var_40]
0x1800883c9  xor     rcx, rsp; StackCookie
0x1800883cc  call    __security_check_cookie
0x1800883d1  add     rsp, 0C8h
0x1800883d8  pop     r14
0x1800883da  pop     r12
0x1800883dc  pop     rdi
0x1800883dd  pop     rbp
0x1800883de  retn
0x1800883df  mov     rcx, rbx; this
0x1800883e2  call    ??1CWxIoContext@@AEAA@XZ; CWxIoContext::~CWxIoContext(void)
0x1800883e7  mov     edx, 60h ; '`'; unsigned __int64
0x1800883ec  mov     rcx, rbx; void *
0x1800883ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800883f4  jmp     short loc_18008839F
0x1800883f6  mov     eax, [rbp+12Ch]
0x1800883fc  mov     r15d, 54Fh
0x180088402  test    eax, eax
0x180088404  cmovnz  r15d, eax
0x180088408  mov     ebp, [rsp+0E8h+var_A8]
0x18008840c  jmp     loc_180088354
0x180088411  mov     rcx, rbx; this
0x180088414  call    ??_GCWxIoContext@@AEAAPEAXI@Z; CWxIoContext::`scalar deleting destructor'(uint)
0x180088419  jmp     loc_180088347
0x18008841e  cmp     r15d, 3E5h
0x180088425  jz      loc_180088338
0x18008842b  cmp     r15d, 2F76h
0x180088432  jz      loc_180088325
0x180088438  cmp     r15d, 2EFCh
0x18008843f  jz      loc_180088325
0x180088445  cmp     r15d, 7Ah ; 'z'
0x180088449  jz      loc_180088325
0x18008844f  lock xadd cs:dword_180269EA4, r13d
0x180088458  mov     rcx, cs:qword_180269EA8
0x18008845f  inc     r13d
0x180088462  movzx   edi, r13b
0x180088466  shl     rdi, 4
0x18008846a  add     rcx, rdi; lpSystemTimeAsFileTime
0x18008846d  call    cs:__imp_GetSystemTimeAsFileTime
0x180088473  mov     rax, cs:qword_180269EA8
0x18008847a  mov     [rdi+rax+8], r15d
0x18008847f  call    cs:__imp_RtlGetLastNtStatus
0x180088485  mov     ecx, eax
0x180088487  mov     rax, cs:qword_180269EA8
0x18008848e  mov     [rdi+rax+0Ch], ecx
0x180088492  lea     rdi, [rbp+8]
0x180088496  jmp     loc_180088325
0x18008849b  mov     eax, [rbp+0F0h]
0x1800884a1  dec     eax
0x1800884a3  cmp     eax, 0FFFFFFFDh
0x1800884a6  ja      loc_1800881E3
0x1800884ac  mov     [rbp+0FCh], r13d
0x1800884b3  lock inc dword ptr [rbp+0]
0x1800884b7  mov     rax, cs:?g_pTimerWheel@@3PEAVCWxTimerWheel@@EA; CWxTimerWheel * g_pTimerWheel
0x1800884be  mov     ecx, [rbp+0F0h]; unsigned int
0x1800884c4  mov     qword ptr [rsp+0E8h+PerformanceCount], rax
0x1800884c9  add     rax, 20h ; ' '
0x1800884cd  mov     [rsp+0E8h+var_A0], rax
0x1800884d2  mov     [rsp+0E8h+NumberOfBytesRecvd], ecx
0x1800884d6  mov     [rsp+0E8h+Flags], 0
0x1800884de  call    ?GetNewSlot@CWxTimerWheel@@CAKK@Z; CWxTimerWheel::GetNewSlot(ulong)
0x1800884e3  mov     rcx, [rsp+0E8h+var_A0]
0x1800884e8  mov     [rsp+0E8h+var_A8], eax
0x1800884ec  and     eax, 3FFh
0x1800884f1  lea     rax, [rax+rax*2]
0x1800884f5  lea     rax, ds:0[rax*8]
0x1800884fd  add     rcx, rax; SRWLock
0x180088500  mov     [rsp+0E8h+var_98], rax
0x180088505  call    cs:__imp_AcquireSRWLockExclusive
0x18008850b  mov     rcx, qword ptr [rsp+0E8h+PerformanceCount]
0x180088510  mov     r8d, [rsp+0E8h+var_A8]
0x180088515  mov     r9, [rsp+0E8h+var_98]
0x18008851a  cmp     r8d, [rcx+0Ch]
0x18008851e  jbe     short loc_180088570
0x180088520  lea     rax, [rbp+100h]
0x180088527  mov     [rax+18h], rbp
0x18008852b  lea     rdx, [r9+10h]
0x18008852f  add     rdx, rcx
0x180088532  mov     [rax+20h], r8d
0x180088536  mov     [rax+24h], r13d
0x18008853a  lea     r10, ?Callback@CWxSocketTimer@@SAXPEAX@Z; CWxSocketTimer::Callback(void *)
0x180088541  mov     [rax+10h], r10
0x180088545  mov     r8, [rdx+8]
0x180088549  cmp     [r8], rdx
0x18008854c  jnz     short loc_1800885AF
0x18008854e  mov     [rax], rdx
0x180088551  mov     [rax+8], r8
0x180088555  mov     [r8], rax
0x180088558  mov     [rdx+8], rax
0x18008855c  mov     eax, r13d
0x18008855f  mov     [rsp+0E8h+Flags], r13d
0x180088564  lock xadd [rcx+8], eax
0x180088569  inc     eax
0x18008856b  cmp     eax, r13d
0x18008856e  jz      short loc_180088592
0x180088570  mov     rcx, [rsp+0E8h+var_A0]
0x180088575  add     rcx, r9; SRWLock
0x180088578  call    cs:__imp_ReleaseSRWLockExclusive
0x18008857e  cmp     [rsp+0E8h+Flags], 0
0x180088583  jnz     loc_1800881E3
0x180088589  mov     ecx, [rsp+0E8h+NumberOfBytesRecvd]
0x18008858d  jmp     loc_1800884DE
0x180088592  mov     rcx, [rsp+0E8h+var_A0]
0x180088597  add     rcx, r9; SRWLock
0x18008859a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800885a0  mov     rcx, qword ptr [rsp+0E8h+PerformanceCount]; this
0x1800885a5  call    ?ScheduleTimer@CWxTimerWheel@@AEAAXXZ; CWxTimerWheel::ScheduleTimer(void)
0x1800885aa  jmp     loc_1800881E3
0x1800885af  mov     ecx, 3
0x1800885b4  int     29h; Win8: RtlFailFast(ecx)
0x1800885b6  mov     rcx, rdi; this
0x1800885b9  call    ??1CWxSocket@@AEAA@XZ; CWxSocket::~CWxSocket(void)
0x1800885be  mov     edx, 270h; unsigned __int64
0x1800885c3  mov     rcx, rdi; void *
0x1800885c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800885cb  jmp     loc_180088187
0x1800885d0  mov     edi, 80070057h
  ... truncated ...
```
