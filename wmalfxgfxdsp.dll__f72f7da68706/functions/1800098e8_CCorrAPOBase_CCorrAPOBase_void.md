# CCorrAPOBase::~CCorrAPOBase(void)

- ea: `0x1800098e8`
- end: `0x1800099b3`
- name: `??1CCorrAPOBase@@UEAA@XZ`
- size: `203`
- prototype: `void __fastcall(CCorrAPOBase *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c98`
- `0x1800097cc`
- `0x180077050`

## callees

- `0x1800098e8`
- `0x1800099bc`
- `0x180009a68`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000996d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000997a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000996d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000997a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099ab`

## pseudocode

```c
void __fastcall CCorrAPOBase::~CCorrAPOBase(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // rcx
  HANDLE OwningThread; // rcx
  HANDLE v4; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CCorrAPO::`vftable'{for `CWMDSPPropImpl'};
  *(_QWORD *)&this[2].LockCount = &CCorrAPOBase::`vftable'{for `CWMDSPComBase'};
  this[2].SpinCount = (ULONG_PTR)&CCorrAPOBase::`vftable'{for `IAudioProcessingObject'};
  this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CCorrAPO::`vftable'{for `IAudioProcessingObjectRT'};
  *(_QWORD *)&this[3].LockCount = &CCorrAPOBase::`vftable'{for `IAudioProcessingObjectConfiguration'};
  v2 = *(_QWORD *)&this[9].LockCount;
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  OwningThread = this[9].OwningThread;
  if ( OwningThread )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)OwningThread + 16LL))(OwningThread);
  corr_delete(&this[6].LockSemaphore);
  DeleteCriticalSection(this + 7);
  DeleteCriticalSection(this + 8);
  v4 = this[4].OwningThread;
  if ( v4 )
    CloseHandle(v4);
  *(_QWORD *)&this[2].LockCount = &CWMDSPComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  CWMDSPPropImpl::~CWMDSPPropImpl((CWMDSPPropImpl *)this);
}

```

## disassembly

```asm
0x1800098e8  push    rbx
0x1800098ea  sub     rsp, 20h
0x1800098ee  lea     rax, ??_7CCorrAPO@@6BCWMDSPPropImpl@@@; const CCorrAPO::`vftable'{for `CWMDSPPropImpl'}
0x1800098f5  mov     rbx, rcx
0x1800098f8  mov     [rcx], rax
0x1800098fb  lea     rax, ??_7CCorrAPOBase@@6BCWMDSPComBase@@@; const CCorrAPOBase::`vftable'{for `CWMDSPComBase'}
0x180009902  mov     [rcx+58h], rax
0x180009906  lea     rax, ??_7CCorrAPOBase@@6BIAudioProcessingObject@@@; const CCorrAPOBase::`vftable'{for `IAudioProcessingObject'}
0x18000990d  mov     [rcx+70h], rax
0x180009911  lea     rax, ??_7CCorrAPO@@6BIAudioProcessingObjectRT@@@; const CCorrAPO::`vftable'{for `IAudioProcessingObjectRT'}
0x180009918  mov     [rcx+78h], rax
0x18000991c  lea     rax, ??_7CCorrAPOBase@@6BIAudioProcessingObjectConfiguration@@@; const CCorrAPOBase::`vftable'{for `IAudioProcessingObjectConfiguration'}
0x180009923  mov     [rcx+80h], rax
0x18000992a  mov     rcx, [rcx+170h]
0x180009931  test    rcx, rcx
0x180009934  jz      short loc_180009942
0x180009936  mov     rax, [rcx]
0x180009939  mov     rax, [rax+10h]
0x18000993d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009942  mov     rcx, [rbx+178h]
0x180009949  test    rcx, rcx
0x18000994c  jz      short loc_18000995A
0x18000994e  mov     rax, [rcx]
0x180009951  mov     rax, [rax+10h]
0x180009955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000995a  lea     rcx, [rbx+108h]
0x180009961  call    corr_delete
0x180009966  lea     rcx, [rbx+118h]; lpCriticalSection
0x18000996d  call    cs:__imp_DeleteCriticalSection
0x180009973  lea     rcx, [rbx+140h]; lpCriticalSection
0x18000997a  call    cs:__imp_DeleteCriticalSection
0x180009980  mov     rcx, [rbx+0B0h]; hObject
0x180009987  test    rcx, rcx
0x18000998a  jnz     short loc_1800099AB
0x18000998c  lea     rax, ??_7CWMDSPComBase@@6B@; const CWMDSPComBase::`vftable'
0x180009993  mov     rcx, rbx; this
0x180009996  mov     [rbx+58h], rax
0x18000999a  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800099a1  add     rsp, 20h
0x1800099a5  pop     rbx
0x1800099a6  jmp     ??1CWMDSPPropImpl@@QEAA@XZ; CWMDSPPropImpl::~CWMDSPPropImpl(void)
0x1800099ab  call    cs:__imp_CloseHandle
0x1800099b1  jmp     short loc_18000998C
```
