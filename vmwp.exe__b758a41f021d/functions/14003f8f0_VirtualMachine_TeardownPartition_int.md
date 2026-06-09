# VirtualMachine::TeardownPartition(int)

- ea: `0x14003f8f0`
- end: `0x14003fb1f`
- name: `?TeardownPartition@VirtualMachine@@AEAAXH@Z`
- size: `559`
- prototype: `void __fastcall(VirtualMachine *__hidden this, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14003f2cc`
- `0x140154640`
- `0x140158cb0`

## callees

- `0x1400364a0`
- `0x14003f8f0`
- `0x1400557e0`
- `0x140083940`
- `0x140084ad4`
- `0x1400c174c`
- `0x140102580`
- `0x140110924`
- `0x1401fe040`
- `0x1402cb010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14003f935`
- `msvcp_win!_Mtx_unlock` at `0x14003f935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003f971`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003f971`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003f9a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003f9a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fa30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fa30`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14003f9bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14003f9bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14003f9d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14003f9d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003f98c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14003f98c`
- `vid!VidChangePartitionLifeState` at `0x14003fa20`
- `vid!VidChangePartitionLifeState` at `0x14003fa20`

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
          VmlDebugTraceWithError(16416, &off_1402E2260, v9);
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
0x14003f8f0  mov     [rsp+arg_8], rbx
0x14003f8f5  mov     [rsp+arg_10], rsi
0x14003f8fa  push    rdi
0x14003f8fb  sub     rsp, 20h
0x14003f8ff  mov     esi, edx
0x14003f901  mov     rdi, rcx
0x14003f904  test    edx, edx
0x14003f906  jnz     short loc_14003F941
0x14003f908  lea     rbx, [rcx+500h]
0x14003f90f  mov     [rcx+4FCh], edx
0x14003f915  mov     rcx, rbx; this
0x14003f918  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14003f91d  mov     rcx, [rbx+60h]
0x14003f921  mov     rcx, [rcx+8]; this
0x14003f925  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x14003f92a  mov     rcx, rbx; this
0x14003f92d  call    ?EndTimedCancel@CancellationTokenProvider@@AEAAXXZ; CancellationTokenProvider::EndTimedCancel(void)
0x14003f932  mov     rcx, rbx; _Mtx_t
0x14003f935  call    cs:__imp__Mtx_unlock
0x14003f93c  nop     dword ptr [rax+rax+00h]
0x14003f941  mov     rcx, [rdi+428h]
0x14003f948  test    rcx, rcx
0x14003f94b  jz      short loc_14003F959
0x14003f94d  mov     rax, [rcx]
0x14003f950  mov     rax, [rax+8]
0x14003f954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f959  cmp     qword ptr [rdi+9C0h], 0
0x14003f961  jz      loc_14003F9EB
0x14003f967  lea     rbx, [rdi+998h]
0x14003f96e  mov     rcx, rbx; lpCriticalSection
0x14003f971  call    cs:__imp_EnterCriticalSection
0x14003f978  nop     dword ptr [rax+rax+00h]
0x14003f97d  mov     rcx, [rdi+9C0h]; pti
0x14003f984  xor     r9d, r9d; msWindowLength
0x14003f987  xor     r8d, r8d; msPeriod
0x14003f98a  xor     edx, edx; pftDueTime
0x14003f98c  call    cs:__imp_SetThreadpoolTimer
0x14003f993  nop     dword ptr [rax+rax+00h]
0x14003f998  mov     rcx, rbx; lpCriticalSection
0x14003f99b  mov     dword ptr [rdi+9C8h], 0
0x14003f9a5  call    cs:__imp_LeaveCriticalSection
0x14003f9ac  nop     dword ptr [rax+rax+00h]
0x14003f9b1  mov     rcx, [rdi+9C0h]; pti
0x14003f9b8  mov     edx, 1; fCancelPendingCallbacks
0x14003f9bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14003f9c4  nop     dword ptr [rax+rax+00h]
0x14003f9c9  test    esi, esi
0x14003f9cb  jnz     short loc_14003F9EB
0x14003f9cd  mov     rcx, [rdi+9C0h]; pti
0x14003f9d4  call    cs:__imp_CloseThreadpoolTimer
0x14003f9db  nop     dword ptr [rax+rax+00h]
0x14003f9e0  mov     qword ptr [rdi+9C0h], 0
0x14003f9eb  cmp     byte ptr [rdi+0AB8h], 0
0x14003f9f2  jz      short loc_14003FA73
0x14003f9f4  cmp     dword ptr [rdi+4F4h], 3
0x14003f9fb  jz      short loc_14003FA6C
0x14003f9fd  mov     rcx, [rdi+400h]
0x14003fa04  add     rcx, 18h
0x14003fa08  mov     rax, [rcx]
0x14003fa0b  mov     rax, [rax]
0x14003fa0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fa13  xor     r9d, r9d
0x14003fa16  mov     rcx, rax
0x14003fa19  xor     r8d, r8d
0x14003fa1c  lea     edx, [r9+4]
0x14003fa20  call    cs:__imp_VidChangePartitionLifeState
0x14003fa27  nop     dword ptr [rax+rax+00h]
0x14003fa2c  test    eax, eax
0x14003fa2e  jnz     short loc_14003FA6C
0x14003fa30  call    cs:__imp_GetLastError
0x14003fa37  nop     dword ptr [rax+rax+00h]
0x14003fa3c  mov     ebx, eax
0x14003fa3e  test    eax, eax
0x14003fa40  jle     short loc_14003FA4B
0x14003fa42  movzx   ebx, ax
0x14003fa45  or      ebx, 80070000h
0x14003fa4b  mov     esi, 4020h
0x14003fa50  mov     ecx, esi
0x14003fa52  call    VmlIsDebugTraceEnabled
0x14003fa57  test    eax, eax
0x14003fa59  jz      short loc_14003FA6C
0x14003fa5b  mov     r8d, ebx
0x14003fa5e  lea     rdx, off_1402E2260; "Unable to transition partition into sec"...
0x14003fa65  mov     ecx, esi
0x14003fa67  call    VmlDebugTraceWithError
0x14003fa6c  mov     byte ptr [rdi+0AB8h], 0
0x14003fa73  mov     rcx, [rdi+410h]
0x14003fa7a  test    rcx, rcx
0x14003fa7d  jz      short loc_14003FAB4
0x14003fa7f  mov     rax, [rcx]
0x14003fa82  mov     rax, [rax+0A0h]
0x14003fa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fa8e  test    eax, eax
0x14003fa90  jz      short loc_14003FA9E
0x14003fa92  lea     rcx, [rdi+5D8h]; this
0x14003fa99  call    ?DisableAndWait@AsyncTimer@@QEAAHXZ; AsyncTimer::DisableAndWait(void)
0x14003fa9e  mov     rcx, [rdi+410h]
0x14003faa5  mov     rax, [rcx]
0x14003faa8  mov     rax, [rax+110h]
0x14003faaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fab4  mov     rax, [rdi+418h]
0x14003fabb  test    rax, rax
0x14003fabe  jz      short loc_14003FAE5
0x14003fac0  lea     rbx, [rax+0F8h]
0x14003fac7  mov     rcx, [rbx]
0x14003faca  test    rcx, rcx
0x14003facd  jz      short loc_14003FAE5
0x14003facf  mov     rax, [rcx]
0x14003fad2  mov     rax, [rax+50h]
0x14003fad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fadb  xor     edx, edx
0x14003fadd  mov     rcx, rbx
0x14003fae0  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x14003fae5  mov     rcx, [rdi+3E0h]; this
0x14003faec  test    rcx, rcx
0x14003faef  jz      short loc_14003FAF6
0x14003faf1  call    ?TeardownGmoStats@MemoryManager@@QEAAXXZ; MemoryManager::TeardownGmoStats(void)
0x14003faf6  mov     rcx, [rdi+400h]
0x14003fafd  test    rcx, rcx
0x14003fb00  jz      short loc_14003FB0E
0x14003fb02  mov     rax, [rcx]
0x14003fb05  mov     rax, [rax+60h]
0x14003fb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fb0e  mov     rbx, [rsp+28h+arg_8]
0x14003fb13  mov     rsi, [rsp+28h+arg_10]
0x14003fb18  add     rsp, 20h
0x14003fb1c  pop     rdi
0x14003fb1d  retn
```
