# CRegistrarSingleton::~CRegistrarSingleton(void)

- ea: `0x1800345e4`
- end: `0x1800346bc`
- name: `??1CRegistrarSingleton@@QEAA@XZ`
- size: `216`
- prototype: `void __fastcall(CRegistrarSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180057ee0`

## callees

- `0x1800056d8`
- `0x18000b5d4`
- `0x18000c094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034644`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034658`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034644`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034658`

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
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(p_LockSemaphore);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(p_OwningThread);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(p_LockCount);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&this[3]);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&this[2].SpinCount);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&this[2].LockSemaphore);
  CTable<CUString,CProvider>::~CTable<CUString,CProvider>(&this[1].SpinCount);
  CDeviceManager::~CDeviceManager((CDeviceManager *)&this->LockCount);
}

```

## disassembly

```asm
0x1800345e4  push    rbx
0x1800345e6  push    rbp
0x1800345e7  push    rsi
0x1800345e8  push    rdi
0x1800345e9  push    r12
0x1800345eb  push    r14
0x1800345ed  push    r15
0x1800345ef  sub     rsp, 20h
0x1800345f3  lea     r14, [rcx+90h]
0x1800345fa  mov     cs:?m_fRegObjDeleted@CRegistrarSingleton@@1HA, 1; int CRegistrarSingleton::m_fRegObjDeleted
0x180034604  lea     rdi, [rcx+80h]
0x18003460b  mov     r12, rcx
0x18003460e  lea     rbx, [rcx+88h]
0x180034615  lea     rax, ??_7CRegistrarSingleton@@6B@; const CRegistrarSingleton::`vftable'
0x18003461c  mov     [rcx], rax
0x18003461f  xor     eax, eax
0x180034621  mov     [rcx+68h], rax
0x180034625  mov     [rcx+70h], rax
0x180034629  mov     [rcx+78h], rax
0x18003462d  add     rcx, 0C8h; lpCriticalSection
0x180034634  mov     [r14], rax
0x180034637  mov     [rdi], rax
0x18003463a  mov     [rbx], rax
0x18003463d  mov     cs:?pCRegSingleton@@3PEAVCRegistrarSingleton@@EA, rax; CRegistrarSingleton * pCRegSingleton
0x180034644  call    cs:__imp_DeleteCriticalSection
0x18003464b  nop     dword ptr [rax+rax+00h]
0x180034650  lea     rcx, [r12+0A0h]; lpCriticalSection
0x180034658  call    cs:__imp_DeleteCriticalSection
0x18003465f  nop     dword ptr [rax+rax+00h]
0x180034664  mov     rcx, r14
0x180034667  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18003466c  mov     rcx, rbx
0x18003466f  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180034674  mov     rcx, rdi
0x180034677  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18003467c  lea     rcx, [r12+78h]
0x180034681  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180034686  lea     rcx, [r12+70h]
0x18003468b  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180034690  lea     rcx, [r12+68h]
0x180034695  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18003469a  lea     rcx, [r12+48h]
0x18003469f  call    ??1?$CTable@VCUString@@VCProvider@@@@QEAA@XZ; CTable<CUString,CProvider>::~CTable<CUString,CProvider>(void)
0x1800346a4  lea     rcx, [r12+8]; this
0x1800346a9  add     rsp, 20h
0x1800346ad  pop     r15
0x1800346af  pop     r14
0x1800346b1  pop     r12
0x1800346b3  pop     rdi
0x1800346b4  pop     rsi
0x1800346b5  pop     rbp
0x1800346b6  pop     rbx
0x1800346b7  jmp     ??1CDeviceManager@@QEAA@XZ; CDeviceManager::~CDeviceManager(void)
```
