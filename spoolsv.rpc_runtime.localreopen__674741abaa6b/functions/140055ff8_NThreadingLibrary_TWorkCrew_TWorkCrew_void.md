# NThreadingLibrary::TWorkCrew::~TWorkCrew(void)

- ea: `0x140055ff8`
- end: `0x1400560ef`
- name: `??1TWorkCrew@NThreadingLibrary@@UEAA@XZ`
- size: `247`
- prototype: `void __fastcall(NThreadingLibrary::TWorkCrew *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140056210`

## callees

- `0x14000bf00`
- `0x14000dfd0`
- `0x140010e7c`
- `0x140055ff8`
- `0x1400568c8`

## import_xrefs

- `ntdll!TpReleasePool` at `0x140056082`
- `ntdll!TpReleasePool` at `0x140056082`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400560b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400560b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140056052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005606a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140056052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005606a`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::~TWorkCrew(struct _RTL_CRITICAL_SECTION *this, void **a2)
{
  bool v2; // sf
  void *v4; // rcx
  HANDLE LockSemaphore; // rcx

  v2 = (this[4].SpinCount & 0x8000000000000000uLL) != 0LL;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&NThreadingLibrary::TWorkCrew::`vftable'{for `NCoreLibrary::TReferenceCount'};
  this->OwningThread = &NThreadingLibrary::TWorkCrew::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'};
  if ( !v2 )
  {
    if ( !LODWORD(this[4].OwningThread) )
      NThreadingLibrary::TWorkCrew::Shutdown((NThreadingLibrary::TWorkCrew *)this, a2);
    NThreadingLibrary::TWorkCrew::CancelWorkThread(0, this, 0);
  }
  v4 = *(void **)&this[5].LockCount;
  if ( v4 )
    CloseHandle(v4);
  LockSemaphore = this[4].LockSemaphore;
  if ( LockSemaphore )
    CloseHandle(LockSemaphore);
  if ( this[5].LockSemaphore )
  {
    TpReleasePool();
    this[5].LockSemaphore = 0;
  }
  NCoreLibrary::TList<NRouter::TUserTokenTable::TSessionEntry>::~TList<NRouter::TUserTokenTable::TSessionEntry>(&this[3].OwningThread);
  NCoreLibrary::TList<NRouter::TUserTokenTable::TSessionEntry>::~TList<NRouter::TUserTokenTable::TSessionEntry>(&this[2].OwningThread);
  if ( this[2].LockCount >= 0 )
  {
    DeleteCriticalSection(this + 1);
    this[2].LockCount = -2147467259;
  }
  NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv((NThreadingLibrary::TTpSetWorkEnv *)&this->OwningThread);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&NCoreLibrary::TReferenceCount::`vftable';
}

```

## disassembly

```asm
0x140055ff8  mov     [rsp+arg_0], rbx
0x140055ffd  mov     [rsp+arg_8], rsi
0x140056002  push    rdi
0x140056003  sub     rsp, 20h
0x140056007  cmp     dword ptr [rcx+0C4h], 0
0x14005600e  lea     rax, ??_7TWorkCrew@NThreadingLibrary@@6BTReferenceCount@NCoreLibrary@@@; const NThreadingLibrary::TWorkCrew::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x140056015  mov     [rcx], rax
0x140056018  mov     rbx, rcx
0x14005601b  lea     rax, ??_7TWorkCrew@NThreadingLibrary@@6BTTpSetWorkEnv@1@@; const NThreadingLibrary::TWorkCrew::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x140056022  mov     [rcx+10h], rax
0x140056026  jl      short loc_140056046
0x140056028  cmp     dword ptr [rcx+0B0h], 0
0x14005602f  jnz     short loc_140056036
0x140056031  call    ?Shutdown@TWorkCrew@NThreadingLibrary@@QEAAJPEAPEAX@Z; NThreadingLibrary::TWorkCrew::Shutdown(void * *)
0x140056036  xor     r9d, r9d; int
0x140056039  xor     r8d, r8d; struct _TP_WAIT *
0x14005603c  mov     rdx, rbx; void *
0x14005603f  xor     ecx, ecx; struct _TP_CALLBACK_INSTANCE *
0x140056041  call    ?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x140056046  mov     rcx, [rbx+0D0h]; hObject
0x14005604d  test    rcx, rcx
0x140056050  jz      short loc_14005605E
0x140056052  call    cs:__imp_CloseHandle
0x140056059  nop     dword ptr [rax+rax+00h]
0x14005605e  mov     rcx, [rbx+0B8h]; hObject
0x140056065  test    rcx, rcx
0x140056068  jz      short loc_140056076
0x14005606a  call    cs:__imp_CloseHandle
0x140056071  nop     dword ptr [rax+rax+00h]
0x140056076  mov     rcx, [rbx+0E0h]
0x14005607d  test    rcx, rcx
0x140056080  jz      short loc_140056099
0x140056082  call    cs:__imp_TpReleasePool
0x140056089  nop     dword ptr [rax+rax+00h]
0x14005608e  mov     qword ptr [rbx+0E0h], 0
0x140056099  lea     rcx, [rbx+88h]
0x1400560a0  call    ??1?$TList@VTSessionEntry@TUserTokenTable@NRouter@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NRouter::TUserTokenTable::TSessionEntry>::~TList<NRouter::TUserTokenTable::TSessionEntry>(void)
0x1400560a5  lea     rcx, [rbx+60h]
0x1400560a9  call    ??1?$TList@VTSessionEntry@TUserTokenTable@NRouter@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NRouter::TUserTokenTable::TSessionEntry>::~TList<NRouter::TUserTokenTable::TSessionEntry>(void)
0x1400560ae  cmp     dword ptr [rbx+58h], 0
0x1400560b2  jl      short loc_1400560CB
0x1400560b4  lea     rcx, [rbx+28h]; lpCriticalSection
0x1400560b8  call    cs:__imp_DeleteCriticalSection
0x1400560bf  nop     dword ptr [rax+rax+00h]
0x1400560c4  mov     dword ptr [rbx+58h], 80004005h
0x1400560cb  lea     rcx, [rbx+10h]; this
0x1400560cf  call    ??1TTpSetWorkEnv@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(void)
0x1400560d4  mov     rsi, [rsp+28h+arg_8]
0x1400560d9  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x1400560e0  mov     [rbx], rax
0x1400560e3  mov     rbx, [rsp+28h+arg_0]
0x1400560e8  add     rsp, 20h
0x1400560ec  pop     rdi
0x1400560ed  retn
```
