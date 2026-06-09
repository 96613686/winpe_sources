# NThreadingLibrary::TWorkCrew::~TWorkCrew(void)

- ea: `0x1400131c4`
- end: `0x1400132a2`
- name: `??1TWorkCrew@NThreadingLibrary@@UEAA@XZ`
- size: `222`
- prototype: `void __fastcall(NThreadingLibrary::TWorkCrew *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400108dc`
- `0x140010c60`
- `0x140013380`

## callees

- `0x140010614`
- `0x140013174`
- `0x1400131c4`
- `0x140013640`
- `0x140013b24`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001321e`
- `KERNEL32!CloseHandle` at `0x140013230`
- `KERNEL32!CloseHandle` at `0x14001321e`
- `KERNEL32!CloseHandle` at `0x140013230`
- `KERNEL32!DeleteCriticalSection` at `0x140013272`
- `KERNEL32!DeleteCriticalSection` at `0x140013272`
- `ntdll!TpReleasePool` at `0x140013242`
- `ntdll!TpReleasePool` at `0x140013242`

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
  NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(&this[3].OwningThread);
  NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(&this[2].OwningThread);
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
0x1400131c4  mov     [rsp+arg_0], rbx
0x1400131c9  mov     [rsp+arg_8], rsi
0x1400131ce  push    rdi
0x1400131cf  sub     rsp, 20h
0x1400131d3  cmp     dword ptr [rcx+0C4h], 0
0x1400131da  lea     rax, ??_7TWorkCrew@NThreadingLibrary@@6BTReferenceCount@NCoreLibrary@@@; const NThreadingLibrary::TWorkCrew::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x1400131e1  mov     [rcx], rax
0x1400131e4  mov     rbx, rcx
0x1400131e7  lea     rax, ??_7TWorkCrew@NThreadingLibrary@@6BTTpSetWorkEnv@1@@; const NThreadingLibrary::TWorkCrew::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x1400131ee  mov     [rcx+10h], rax
0x1400131f2  jl      short loc_140013212
0x1400131f4  cmp     dword ptr [rcx+0B0h], 0
0x1400131fb  jnz     short loc_140013202
0x1400131fd  call    ?Shutdown@TWorkCrew@NThreadingLibrary@@QEAAJPEAPEAX@Z; NThreadingLibrary::TWorkCrew::Shutdown(void * *)
0x140013202  xor     r9d, r9d; int
0x140013205  xor     r8d, r8d; struct _TP_WAIT *
0x140013208  mov     rdx, rbx; void *
0x14001320b  xor     ecx, ecx; struct _TP_CALLBACK_INSTANCE *
0x14001320d  call    ?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x140013212  mov     rcx, [rbx+0D0h]; hObject
0x140013219  test    rcx, rcx
0x14001321c  jz      short loc_140013224
0x14001321e  call    cs:__imp_CloseHandle
0x140013224  mov     rcx, [rbx+0B8h]; hObject
0x14001322b  test    rcx, rcx
0x14001322e  jz      short loc_140013236
0x140013230  call    cs:__imp_CloseHandle
0x140013236  mov     rcx, [rbx+0E0h]
0x14001323d  test    rcx, rcx
0x140013240  jz      short loc_140013253
0x140013242  call    cs:__imp_TpReleasePool
0x140013248  mov     qword ptr [rbx+0E0h], 0
0x140013253  lea     rcx, [rbx+88h]
0x14001325a  call    ??1?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(void)
0x14001325f  lea     rcx, [rbx+60h]
0x140013263  call    ??1?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(void)
0x140013268  cmp     dword ptr [rbx+58h], 0
0x14001326c  jl      short loc_14001327F
0x14001326e  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013272  call    cs:__imp_DeleteCriticalSection
0x140013278  mov     dword ptr [rbx+58h], 80004005h
0x14001327f  lea     rcx, [rbx+10h]; this
0x140013283  call    ??1TTpSetWorkEnv@NThreadingLibrary@@UEAA@XZ; NThreadingLibrary::TTpSetWorkEnv::~TTpSetWorkEnv(void)
0x140013288  mov     rsi, [rsp+28h+arg_8]
0x14001328d  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x140013294  mov     [rbx], rax
0x140013297  mov     rbx, [rsp+28h+arg_0]
0x14001329c  add     rsp, 20h
0x1400132a0  pop     rdi
0x1400132a1  retn
```
