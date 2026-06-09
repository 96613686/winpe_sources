# CRegistrarSingleton::~CRegistrarSingleton(void)

- ea: `0x1800327dc`
- end: `0x1800328a8`
- name: `??1CRegistrarSingleton@@QEAA@XZ`
- size: `204`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180054530`

## callees

- `0x1800117bc`
- `0x180017240`
- `0x180017f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003283c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003284a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003283c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003284a`

## pseudocode

```c
void __fastcall CRegistrarSingleton::~CRegistrarSingleton(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE *p_LockSemaphore; // r14
  LONG *p_LockCount; // rdi
  HANDLE *p_OwningThread; // rbx

  p_LockSemaphore = &this[3].LockSemaphore;
  CRegistrarSingleton::m_fRegObjDeleted = 1;
  p_LockCount = &this[3].LockCount;
  p_OwningThread = &this[3].OwningThread;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CRegistrarSingleton::`vftable';
  this[2].LockSemaphore = 0;
  this[2].SpinCount = 0;
  this[3].DebugInfo = 0;
  this[3].LockSemaphore = 0;
  *(_QWORD *)&this[3].LockCount = 0;
  this[3].OwningThread = 0;
  pCRegSingleton = 0;
  DeleteCriticalSection(this + 5);
  DeleteCriticalSection(this + 4);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)p_LockSemaphore);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)p_OwningThread);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)p_LockCount);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&this[3]);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&this[2].SpinCount);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&this[2].LockSemaphore);
  CTable<CUString,CProvider>::~CTable<CUString,CProvider>(&this[1].SpinCount);
  CDeviceManager::~CDeviceManager((CDeviceManager *)&this->LockCount);
}

```

## disassembly

```asm
0x1800327dc  push    rbx
0x1800327de  push    rbp
0x1800327df  push    rsi
0x1800327e0  push    rdi
0x1800327e1  push    r12
0x1800327e3  push    r14
0x1800327e5  push    r15
0x1800327e7  sub     rsp, 20h
0x1800327eb  lea     r14, [rcx+90h]
0x1800327f2  mov     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, 1; int CRegistrarSingleton::m_fRegObjDeleted
0x1800327fc  lea     rdi, [rcx+80h]
0x180032803  mov     r12, rcx
0x180032806  lea     rbx, [rcx+88h]
0x18003280d  lea     rax, ??_7CRegistrarSingleton@@6B@; const CRegistrarSingleton::`vftable'
0x180032814  mov     [rcx], rax
0x180032817  xor     eax, eax
0x180032819  mov     [rcx+68h], rax
0x18003281d  mov     [rcx+70h], rax
0x180032821  mov     [rcx+78h], rax
0x180032825  add     rcx, 0C8h; lpCriticalSection
0x18003282c  mov     [r14], rax
0x18003282f  mov     [rdi], rax
0x180032832  mov     [rbx], rax
0x180032835  mov     cs:?pCRegSingleton@@3PEAVCRegistrarSingleton@@EA, rax; CRegistrarSingleton * pCRegSingleton
0x18003283c  call    cs:__imp_DeleteCriticalSection
0x180032842  lea     rcx, [r12+0A0h]; lpCriticalSection
0x18003284a  call    cs:__imp_DeleteCriticalSection
0x180032850  mov     rcx, r14
0x180032853  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180032858  mov     rcx, rbx
0x18003285b  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180032860  mov     rcx, rdi
0x180032863  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180032868  lea     rcx, [r12+78h]
0x18003286d  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180032872  lea     rcx, [r12+70h]
0x180032877  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18003287c  lea     rcx, [r12+68h]
0x180032881  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180032886  lea     rcx, [r12+48h]
0x18003288b  call    ??1?$CTable@VCUString@@VCProvider@@@@QEAA@XZ; CTable<CUString,CProvider>::~CTable<CUString,CProvider>(void)
0x180032890  lea     rcx, [r12+8]; this
0x180032895  add     rsp, 20h
0x180032899  pop     r15
0x18003289b  pop     r14
0x18003289d  pop     r12
0x18003289f  pop     rdi
0x1800328a0  pop     rsi
0x1800328a1  pop     rbp
0x1800328a2  pop     rbx
0x1800328a3  jmp     ??1CDeviceManager@@QEAA@XZ; CDeviceManager::~CDeviceManager(void)
```
