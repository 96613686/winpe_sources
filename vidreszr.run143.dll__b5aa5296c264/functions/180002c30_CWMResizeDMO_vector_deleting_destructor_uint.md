# CWMResizeDMO::`vector deleting destructor'(uint)

- ea: `0x180002c30`
- end: `0x180002da9`
- name: `??_ECWMResizeDMO@@UEAAPEAXI@Z`
- size: `377`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bd0`

## callees

- `0x180001968`
- `0x180002ac0`
- `0x180002c30`
- `0x180011ab0`
- `0x1800147cc`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d5b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002d5b`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CWMResizeDMO::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int64 a2)
{
  char v3; // si
  ULONG_PTR SpinCount; // rcx
  WMSDKRESIZER *DebugInfo; // rcx
  WMSDKRESIZER *OwningThread; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v7; // rcx
  void *v8; // rcx
  HANDLE v9; // rcx
  void *v10; // rcx
  HANDLE LockSemaphore; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWMResizeDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  v3 = a2;
  *(_QWORD *)&this[1].LockCount = &CWMResizeDMO::`vftable'{for `IMediaObject'};
  this[7].SpinCount = (ULONG_PTR)&CWMResizeDMO::`vftable'{for `IWMResizerProps'};
  this[8].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWMResizeDMO::`vftable'{for `CWMDSPPropImpl'};
  *(_QWORD *)&this[10].LockCount = &CWMResizeDMO::`vftable'{for `IMFRealTimeClient'};
  this[10].OwningThread = &CWMResizeDMO::`vftable'{for `CComBase'};
  SpinCount = this[30].SpinCount;
  if ( SpinCount )
  {
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 16LL))(SpinCount);
    this[30].SpinCount = 0;
  }
  DebugInfo = (WMSDKRESIZER *)this[12].DebugInfo;
  if ( DebugInfo )
  {
    WMSDKRESIZER::`scalar deleting destructor'(DebugInfo, a2);
    this[12].DebugInfo = 0;
  }
  OwningThread = (WMSDKRESIZER *)this[12].OwningThread;
  if ( OwningThread )
  {
    WMSDKRESIZER::`scalar deleting destructor'(OwningThread, a2);
    this[12].OwningThread = 0;
  }
  v7 = this[16].DebugInfo;
  if ( v7 )
  {
    operator delete(v7, a2);
    this[16].DebugInfo = 0;
  }
  v8 = *(void **)&this[16].LockCount;
  if ( v8 )
  {
    operator delete(v8, a2);
    *(_QWORD *)&this[16].LockCount = 0;
  }
  v9 = this[16].OwningThread;
  if ( v9 )
  {
    operator delete(v9, a2);
    this[16].OwningThread = 0;
  }
  v10 = *(void **)&this[30].LockCount;
  if ( v10 )
    operator delete(v10, a2);
  LockSemaphore = this[30].LockSemaphore;
  *(_QWORD *)&this[30].LockCount = 0;
  if ( LockSemaphore )
    operator delete(LockSemaphore, a2);
  this[30].LockSemaphore = 0;
  DeleteCriticalSection(this + 11);
  this[10].OwningThread = &CComBase::`vftable';
  _InterlockedDecrement(&g_cActiveObjects);
  CWMDSPPropImpl::~CWMDSPPropImpl((CWMDSPPropImpl *)&this[8]);
  CWMDSPDMOWMILoggingBase<C1in1outDMO>::~CWMDSPDMOWMILoggingBase<C1in1outDMO>((C1in1outDMO *)this);
  if ( (v3 & 1) != 0 )
    operator delete(this, 0x5F0u);
  return this;
}

```

## disassembly

```asm
0x180002c30  push    rbx
0x180002c32  push    rbp
0x180002c33  push    rsi
0x180002c34  push    rdi
0x180002c35  sub     rsp, 28h
0x180002c39  lea     rax, ??_7CWMResizeDMO@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const CWMResizeDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x180002c40  mov     rbx, rcx
0x180002c43  mov     [rcx], rax
0x180002c46  xor     ebp, ebp
0x180002c48  lea     rax, ??_7CWMResizeDMO@@6BIMediaObject@@@; const CWMResizeDMO::`vftable'{for `IMediaObject'}
0x180002c4f  mov     esi, edx
0x180002c51  mov     [rcx+30h], rax
0x180002c55  lea     rax, ??_7CWMResizeDMO@@6BIWMResizerProps@@@; const CWMResizeDMO::`vftable'{for `IWMResizerProps'}
0x180002c5c  mov     [rcx+138h], rax
0x180002c63  lea     rax, ??_7CWMResizeDMO@@6BCWMDSPPropImpl@@@; const CWMResizeDMO::`vftable'{for `CWMDSPPropImpl'}
0x180002c6a  mov     [rcx+140h], rax
0x180002c71  lea     rax, ??_7CWMResizeDMO@@6BIMFRealTimeClient@@@; const CWMResizeDMO::`vftable'{for `IMFRealTimeClient'}
0x180002c78  mov     [rcx+198h], rax
0x180002c7f  lea     rax, ??_7CWMResizeDMO@@6BCComBase@@@; const CWMResizeDMO::`vftable'{for `CComBase'}
0x180002c86  mov     [rcx+1A0h], rax
0x180002c8d  mov     rcx, [rcx+4D0h]
0x180002c94  test    rcx, rcx
0x180002c97  jz      short loc_180002CAC
0x180002c99  mov     rax, [rcx]
0x180002c9c  mov     rax, [rax+10h]
0x180002ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca5  mov     [rbx+4D0h], rbp
0x180002cac  mov     rcx, [rbx+1E0h]; this
0x180002cb3  test    rcx, rcx
0x180002cb6  jz      short loc_180002CC4
0x180002cb8  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x180002cbd  mov     [rbx+1E0h], rbp
0x180002cc4  mov     rcx, [rbx+1F0h]; this
0x180002ccb  test    rcx, rcx
0x180002cce  jz      short loc_180002CDC
0x180002cd0  call    ??_GWMSDKRESIZER@@QEAAPEAXI@Z; WMSDKRESIZER::`scalar deleting destructor'(uint)
0x180002cd5  mov     [rbx+1F0h], rbp
0x180002cdc  mov     rcx, [rbx+280h]; void *
0x180002ce3  test    rcx, rcx
0x180002ce6  jz      short loc_180002CF4
0x180002ce8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002ced  mov     [rbx+280h], rbp
0x180002cf4  mov     rcx, [rbx+288h]; void *
0x180002cfb  test    rcx, rcx
0x180002cfe  jz      short loc_180002D0C
0x180002d00  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002d05  mov     [rbx+288h], rbp
0x180002d0c  mov     rcx, [rbx+290h]; void *
0x180002d13  test    rcx, rcx
0x180002d16  jz      short loc_180002D24
0x180002d18  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002d1d  mov     [rbx+290h], rbp
0x180002d24  mov     rcx, [rbx+4B8h]; void *
0x180002d2b  test    rcx, rcx
0x180002d2e  jz      short loc_180002D35
0x180002d30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002d35  mov     rcx, [rbx+4C8h]; void *
0x180002d3c  mov     [rbx+4B8h], rbp
0x180002d43  test    rcx, rcx
0x180002d46  jz      short loc_180002D4D
0x180002d48  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002d4d  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x180002d54  mov     [rbx+4C8h], rbp
0x180002d5b  call    cs:__imp_DeleteCriticalSection
0x180002d61  lea     rax, ??_7CComBase@@6B@; const CComBase::`vftable'
0x180002d68  mov     [rbx+1A0h], rax
0x180002d6f  lea     rcx, [rbx+140h]; this
0x180002d76  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180002d7d  call    ??1CWMDSPPropImpl@@QEAA@XZ; CWMDSPPropImpl::~CWMDSPPropImpl(void)
0x180002d82  mov     rcx, rbx; this
0x180002d85  call    ??1?$CWMDSPDMOWMILoggingBase@VC1in1outDMO@@@@QEAA@XZ; CWMDSPDMOWMILoggingBase<C1in1outDMO>::~CWMDSPDMOWMILoggingBase<C1in1outDMO>(void)
0x180002d8a  test    sil, 1
0x180002d8e  jz      short loc_180002D9D
0x180002d90  mov     edx, 5F0h; unsigned __int64
0x180002d95  mov     rcx, rbx; void *
0x180002d98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002d9d  mov     rax, rbx
0x180002da0  add     rsp, 28h
0x180002da4  pop     rdi
0x180002da5  pop     rsi
0x180002da6  pop     rbp
0x180002da7  pop     rbx
0x180002da8  retn
```
