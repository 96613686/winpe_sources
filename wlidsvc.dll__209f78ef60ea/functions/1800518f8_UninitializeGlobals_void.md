# UninitializeGlobals(void)

- ea: `0x1800518f8`
- end: `0x1800519eb`
- name: `?UninitializeGlobals@@YAXXZ`
- size: `243`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ee98`

## callees

- `0x1800518f8`
- `0x1800a400c`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005190a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005190a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051927`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051966`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051966`
- `CRYPTSP!CryptReleaseContext` at `0x180051946`
- `CRYPTSP!CryptReleaseContext` at `0x180051946`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x1800519c2`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x1800519df`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x1800519c2`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x1800519df`

## pseudocode

```c
void UninitializeGlobals(void)
{
  LPCRITICAL_SECTION v0; // rbx

  if ( g_hServiceStopped )
  {
    CloseHandle(g_hServiceStopped);
    g_hServiceStopped = 0;
  }
  if ( g_hServiceStarted )
  {
    CloseHandle(g_hServiceStarted);
    g_hServiceStarted = 0;
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  v0 = InterruptNotifications::_pUpdateStateCritSec;
  if ( InterruptNotifications::_pUpdateStateCritSec )
  {
    DeleteCriticalSection(InterruptNotifications::_pUpdateStateCritSec);
    operator delete(v0);
    InterruptNotifications::_pUpdateStateCritSec = 0;
  }
  if ( CStringSrv::m_pRWLock )
  {
    (**(void (__fastcall ***)(struct CReadWriteLockEx *, __int64))CStringSrv::m_pRWLock)(CStringSrv::m_pRWLock, 1);
    CStringSrv::m_pRWLock = 0;
  }
  if ( byte_1801C7024 )
  {
    byte_1801C7024 = 0;
    MappingFreeServices(g_scriptAutoDetection);
  }
  if ( byte_1801C7034 )
  {
    byte_1801C7034 = 0;
    MappingFreeServices(g_koreanDecomposition);
  }
}

```

## disassembly

```asm
0x1800518f8  push    rbx
0x1800518fa  sub     rsp, 20h
0x1800518fe  mov     rcx, cs:?g_hServiceStopped@@3PEAXEA; hObject
0x180051905  test    rcx, rcx
0x180051908  jz      short loc_18005191B
0x18005190a  call    cs:__imp_CloseHandle
0x180051910  mov     cs:?g_hServiceStopped@@3PEAXEA, 0; void * g_hServiceStopped
0x18005191b  mov     rcx, cs:?g_hServiceStarted@@3PEAXEA; hObject
0x180051922  test    rcx, rcx
0x180051925  jz      short loc_180051938
0x180051927  call    cs:__imp_CloseHandle
0x18005192d  mov     cs:?g_hServiceStarted@@3PEAXEA, 0; void * g_hServiceStarted
0x180051938  mov     rcx, cs:hProv; hProv
0x18005193f  test    rcx, rcx
0x180051942  jz      short loc_180051957
0x180051944  xor     edx, edx; dwFlags
0x180051946  call    cs:__imp_CryptReleaseContext
0x18005194c  mov     cs:hProv, 0
0x180051957  mov     rbx, cs:?_pUpdateStateCritSec@InterruptNotifications@@1PEAVCComAutoCriticalSection@ATL@@EA; ATL::CComAutoCriticalSection * InterruptNotifications::_pUpdateStateCritSec
0x18005195e  test    rbx, rbx
0x180051961  jz      short loc_180051984
0x180051963  mov     rcx, rbx; lpCriticalSection
0x180051966  call    cs:__imp_DeleteCriticalSection
0x18005196c  mov     edx, 28h ; '('
0x180051971  mov     rcx, rbx; Block
0x180051974  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180051979  mov     cs:?_pUpdateStateCritSec@InterruptNotifications@@1PEAVCComAutoCriticalSection@ATL@@EA, 0; ATL::CComAutoCriticalSection * InterruptNotifications::_pUpdateStateCritSec
0x180051984  mov     rcx, cs:?m_pRWLock@CStringSrv@@0PEAVCReadWriteLockEx@@EA; CReadWriteLockEx * CStringSrv::m_pRWLock
0x18005198b  test    rcx, rcx
0x18005198e  jz      short loc_1800519AB
0x180051990  mov     rax, [rcx]
0x180051993  mov     edx, 1
0x180051998  mov     rax, [rax]
0x18005199b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519a0  mov     cs:?m_pRWLock@CStringSrv@@0PEAVCReadWriteLockEx@@EA, 0; CReadWriteLockEx * CStringSrv::m_pRWLock
0x1800519ab  cmp     cs:byte_1801C7024, 0
0x1800519b2  jz      short loc_1800519C8
0x1800519b4  mov     rcx, cs:?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; pServiceInfo
0x1800519bb  mov     cs:byte_1801C7024, 0
0x1800519c2  call    cs:__imp_MappingFreeServices
0x1800519c8  cmp     cs:byte_1801C7034, 0
0x1800519cf  jz      short loc_1800519E5
0x1800519d1  mov     rcx, cs:?g_koreanDecomposition@@3VCKoreanDecomposition@@A; pServiceInfo
0x1800519d8  mov     cs:byte_1801C7034, 0
0x1800519df  call    cs:__imp_MappingFreeServices
0x1800519e5  add     rsp, 20h
0x1800519e9  pop     rbx
0x1800519ea  retn
```
