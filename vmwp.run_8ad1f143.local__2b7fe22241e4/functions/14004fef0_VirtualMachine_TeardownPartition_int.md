# VirtualMachine::TeardownPartition(int)

- ea: `0x14004fef0`
- end: `0x14005011f`
- name: `?TeardownPartition@VirtualMachine@@AEAAXH@Z`
- size: `559`
- prototype: `void __fastcall(VirtualMachine *__hidden this, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14004f8cc`
- `0x140167240`
- `0x14016acd4`

## callees

- `0x140042260`
- `0x14004fef0`
- `0x140055a90`
- `0x1400598a0`
- `0x14005b5f8`
- `0x1400d438c`
- `0x140111090`
- `0x1401202b4`
- `0x14020ca00`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14004ff35`
- `msvcp_win!_Mtx_unlock` at `0x14004ff35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004ff71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004ff71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004ffa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004ffa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050030`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14004ffd4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14004ffd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14004ff8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14004ff8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14004ffbd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14004ffbd`
- `vid!VidChangePartitionLifeState` at `0x140050020`
- `vid!VidChangePartitionLifeState` at `0x140050020`

## pseudocode

```c
void __fastcall VirtualMachine::TeardownPartition(VirtualMachine *this, int a2)
{
  CancellationTokenProvider *v4; // rbx
  void *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  MemoryManager *v14; // rcx
  __int64 v15; // rcx

  if ( !a2 )
  {
    v4 = (VirtualMachine *)((char *)this + 1280);
    *((_DWORD *)this + 319) = 0;
    std::_Mutex_base::lock((VirtualMachine *)((char *)this + 1280));
    wil::details::ResetEvent(*(wil::details **)(*((_QWORD *)v4 + 12) + 8LL), v5);
    CancellationTokenProvider::EndTimedCancel(v4);
    _Mtx_unlock(v4);
  }
  v6 = *((_QWORD *)this + 133);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( *((_QWORD *)this + 312) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2456));
    SetThreadpoolTimer(*((PTP_TIMER *)this + 312), 0, 0, 0);
    *((_DWORD *)this + 626) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2456));
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 312), 1);
    if ( !a2 )
    {
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 312));
      *((_QWORD *)this + 312) = 0;
    }
  }
  if ( *((_BYTE *)this + 2744) )
  {
    if ( *((_DWORD *)this + 317) != 3 )
    {
      v7 = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)this + 128) + 24LL))(*((_QWORD *)this + 128) + 24LL);
      if ( !(unsigned int)VidChangePartitionLifeState(v7, 4, 0, 0) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
          VmlDebugTraceWithError(16416, &off_1402D8E90, v9);
      }
    }
    *((_BYTE *)this + 2744) = 0;
  }
  v10 = *((_QWORD *)this + 130);
  if ( v10 )
  {
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 160LL))(v10) )
      AsyncTimer::DisableAndWait((VirtualMachine *)((char *)this + 1496));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 130) + 272LL))(*((_QWORD *)this + 130));
  }
  v11 = *((_QWORD *)this + 131);
  if ( v11 )
  {
    v12 = v11 + 248;
    v13 = *(_QWORD *)(v11 + 248);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
      Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(v12, 0);
    }
  }
  v14 = (MemoryManager *)*((_QWORD *)this + 124);
  if ( v14 )
    MemoryManager::TeardownGmoStats(v14);
  v15 = *((_QWORD *)this + 128);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 96LL))(v15);
}

```

## disassembly

```asm
0x14004fef0  mov     [rsp+arg_8], rbx
0x14004fef5  mov     [rsp+arg_10], rsi
0x14004fefa  push    rdi
0x14004fefb  sub     rsp, 20h
0x14004feff  mov     esi, edx
0x14004ff01  mov     rdi, rcx
0x14004ff04  test    edx, edx
0x14004ff06  jnz     short loc_14004FF41
0x14004ff08  lea     rbx, [rcx+500h]
0x14004ff0f  mov     [rcx+4FCh], edx
0x14004ff15  mov     rcx, rbx; this
0x14004ff18  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14004ff1d  mov     rcx, [rbx+60h]
0x14004ff21  mov     rcx, [rcx+8]; this
0x14004ff25  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x14004ff2a  mov     rcx, rbx; this
0x14004ff2d  call    ?EndTimedCancel@CancellationTokenProvider@@AEAAXXZ; CancellationTokenProvider::EndTimedCancel(void)
0x14004ff32  mov     rcx, rbx; _Mtx_t
0x14004ff35  call    cs:__imp__Mtx_unlock
0x14004ff3c  nop     dword ptr [rax+rax+00h]
0x14004ff41  mov     rcx, [rdi+428h]
0x14004ff48  test    rcx, rcx
0x14004ff4b  jz      short loc_14004FF59
0x14004ff4d  mov     rax, [rcx]
0x14004ff50  mov     rax, [rax+8]
0x14004ff54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ff59  cmp     qword ptr [rdi+9C0h], 0
0x14004ff61  jz      loc_14004FFEB
0x14004ff67  lea     rbx, [rdi+998h]
0x14004ff6e  mov     rcx, rbx; lpCriticalSection
0x14004ff71  call    cs:__imp_EnterCriticalSection
0x14004ff78  nop     dword ptr [rax+rax+00h]
0x14004ff7d  mov     rcx, [rdi+9C0h]; pti
0x14004ff84  xor     r9d, r9d; msWindowLength
0x14004ff87  xor     r8d, r8d; msPeriod
0x14004ff8a  xor     edx, edx; pftDueTime
0x14004ff8c  call    cs:__imp_SetThreadpoolTimer
0x14004ff93  nop     dword ptr [rax+rax+00h]
0x14004ff98  mov     rcx, rbx; lpCriticalSection
0x14004ff9b  mov     dword ptr [rdi+9C8h], 0
0x14004ffa5  call    cs:__imp_LeaveCriticalSection
0x14004ffac  nop     dword ptr [rax+rax+00h]
0x14004ffb1  mov     rcx, [rdi+9C0h]; pti
0x14004ffb8  mov     edx, 1; fCancelPendingCallbacks
0x14004ffbd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14004ffc4  nop     dword ptr [rax+rax+00h]
0x14004ffc9  test    esi, esi
0x14004ffcb  jnz     short loc_14004FFEB
0x14004ffcd  mov     rcx, [rdi+9C0h]; pti
0x14004ffd4  call    cs:__imp_CloseThreadpoolTimer
0x14004ffdb  nop     dword ptr [rax+rax+00h]
0x14004ffe0  mov     qword ptr [rdi+9C0h], 0
0x14004ffeb  cmp     byte ptr [rdi+0AB8h], 0
0x14004fff2  jz      short loc_140050073
0x14004fff4  cmp     dword ptr [rdi+4F4h], 3
0x14004fffb  jz      short loc_14005006C
0x14004fffd  mov     rcx, [rdi+400h]
0x140050004  add     rcx, 18h
0x140050008  mov     rax, [rcx]
0x14005000b  mov     rax, [rax]
0x14005000e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050013  xor     r9d, r9d
0x140050016  mov     rcx, rax
0x140050019  xor     r8d, r8d
0x14005001c  lea     edx, [r9+4]
0x140050020  call    cs:__imp_VidChangePartitionLifeState
0x140050027  nop     dword ptr [rax+rax+00h]
0x14005002c  test    eax, eax
0x14005002e  jnz     short loc_14005006C
0x140050030  call    cs:__imp_GetLastError
0x140050037  nop     dword ptr [rax+rax+00h]
0x14005003c  mov     ebx, eax
0x14005003e  test    eax, eax
0x140050040  jle     short loc_14005004B
0x140050042  movzx   ebx, ax
0x140050045  or      ebx, 80070000h
0x14005004b  mov     esi, 4020h
0x140050050  mov     ecx, esi
0x140050052  call    VmlIsDebugTraceEnabled
0x140050057  test    eax, eax
0x140050059  jz      short loc_14005006C
0x14005005b  mov     r8d, ebx
0x14005005e  lea     rdx, off_1402D8E90; "Unable to transition partition into sec"...
0x140050065  mov     ecx, esi
0x140050067  call    VmlDebugTraceWithError
0x14005006c  mov     byte ptr [rdi+0AB8h], 0
0x140050073  mov     rcx, [rdi+410h]
0x14005007a  test    rcx, rcx
0x14005007d  jz      short loc_1400500B4
0x14005007f  mov     rax, [rcx]
0x140050082  mov     rax, [rax+0A0h]
0x140050089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005008e  test    eax, eax
0x140050090  jz      short loc_14005009E
0x140050092  lea     rcx, [rdi+5D8h]; this
0x140050099  call    ?DisableAndWait@AsyncTimer@@QEAAHXZ; AsyncTimer::DisableAndWait(void)
0x14005009e  mov     rcx, [rdi+410h]
0x1400500a5  mov     rax, [rcx]
0x1400500a8  mov     rax, [rax+110h]
0x1400500af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400500b4  mov     rax, [rdi+418h]
0x1400500bb  test    rax, rax
0x1400500be  jz      short loc_1400500E5
0x1400500c0  lea     rbx, [rax+0F8h]
0x1400500c7  mov     rcx, [rbx]
0x1400500ca  test    rcx, rcx
0x1400500cd  jz      short loc_1400500E5
0x1400500cf  mov     rax, [rcx]
0x1400500d2  mov     rax, [rax+50h]
0x1400500d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400500db  xor     edx, edx
0x1400500dd  mov     rcx, rbx
0x1400500e0  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x1400500e5  mov     rcx, [rdi+3E0h]; this
0x1400500ec  test    rcx, rcx
0x1400500ef  jz      short loc_1400500F6
0x1400500f1  call    ?TeardownGmoStats@MemoryManager@@QEAAXXZ; MemoryManager::TeardownGmoStats(void)
0x1400500f6  mov     rcx, [rdi+400h]
0x1400500fd  test    rcx, rcx
0x140050100  jz      short loc_14005010E
0x140050102  mov     rax, [rcx]
0x140050105  mov     rax, [rax+60h]
0x140050109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005010e  mov     rbx, [rsp+28h+arg_8]
0x140050113  mov     rsi, [rsp+28h+arg_10]
0x140050118  add     rsp, 20h
0x14005011c  pop     rdi
0x14005011d  retn
```
