# SharedDataManager::~SharedDataManager(void)

- ea: `0x180004fa4`
- end: `0x180005065`
- name: `??1SharedDataManager@@QEAA@XZ`
- size: `193`
- prototype: `void __fastcall(SharedDataManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800062cc`
- `0x18000fcd0`

## callees

- `0x180004e34`
- `0x180004fa4`
- `0x180005144`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004fe2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004fe2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000505e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004fc8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180004fc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180004fbf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180004fbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SharedDataManager::~SharedDataManager(SharedDataManager *this)
{
  struct _TP_WORK *v2; // rdi
  void *v3; // rdi
  volatile signed __int32 *v4; // rdi
  __int64 v5; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 15), 0);
    CloseThreadpoolWork(v2);
  }
  v3 = (void *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    wil::details::event_watcher_state::~event_watcher_state(*((wil::details::event_watcher_state **)this + 14));
    operator delete(v3);
  }
  ProcessMonitor::~ProcessMonitor((SharedDataManager *)((char *)this + 64));
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
  {
    *((_QWORD *)this + 5) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180004fa4  mov     [rsp+arg_0], rbx
0x180004fa9  push    rdi
0x180004faa  sub     rsp, 20h
0x180004fae  mov     rbx, rcx
0x180004fb1  mov     rdi, [rcx+78h]
0x180004fb5  test    rdi, rdi
0x180004fb8  jz      short loc_180004FCE
0x180004fba  xor     edx, edx; fCancelPendingCallbacks
0x180004fbc  mov     rcx, rdi; pwk
0x180004fbf  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180004fc5  mov     rcx, rdi; pwk
0x180004fc8  call    cs:__imp_CloseThreadpoolWork
0x180004fce  mov     rdi, [rbx+70h]
0x180004fd2  test    rdi, rdi
0x180004fd5  jz      short loc_180004FE8
0x180004fd7  mov     rcx, rdi; this
0x180004fda  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x180004fdf  mov     rcx, rdi
0x180004fe2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004fe8  lea     rcx, [rbx+40h]; this
0x180004fec  call    ??1ProcessMonitor@@UEAA@XZ; ProcessMonitor::~ProcessMonitor(void)
0x180004ff1  nop
0x180004ff2  mov     rdi, [rbx+38h]
0x180004ff6  test    rdi, rdi
0x180004ff9  jz      short loc_180005033
0x180004ffb  or      eax, 0FFFFFFFFh
0x180004ffe  lock xadd [rdi+8], eax
0x180005003  cmp     eax, 1
0x180005006  jnz     short loc_180005033
0x180005008  mov     rax, [rdi]
0x18000500b  mov     rcx, rdi
0x18000500e  mov     rax, [rax]
0x180005011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005016  or      eax, 0FFFFFFFFh
0x180005019  lock xadd [rdi+0Ch], eax
0x18000501e  cmp     eax, 1
0x180005021  jnz     short loc_180005033
0x180005023  mov     rax, [rdi]
0x180005026  mov     rcx, rdi
0x180005029  mov     rax, [rax+8]
0x18000502d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005032  nop
0x180005033  mov     rcx, [rbx+28h]
0x180005037  test    rcx, rcx
0x18000503a  jz      short loc_180005051
0x18000503c  mov     qword ptr [rbx+28h], 0
0x180005044  mov     rax, [rcx]
0x180005047  mov     rax, [rax+10h]
0x18000504b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005050  nop
0x180005051  mov     rcx, rbx
0x180005054  mov     rbx, [rsp+28h+arg_0]
0x180005059  add     rsp, 20h
0x18000505d  pop     rdi
0x18000505e  jmp     cs:__imp_DeleteCriticalSection
```
