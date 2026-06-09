# CSslGlobals::InitializePeriodicCleanupHandler(void)

- ea: `0x18007198c`
- end: `0x180071a23`
- name: `?InitializePeriodicCleanupHandler@CSslGlobals@@SAKXZ`
- size: `151`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025c38`
- `0x180069a3c`

## callees

- `0x1800716ec`
- `0x18007198c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800719fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800719fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800719b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800719b8`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800719ea`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800719ea`

## pseudocode

```c
__int64 CSslGlobals::InitializePeriodicCleanupHandler(void)
{
  DWORD v0; // ebx
  HANDLE EventA; // rax
  DWORD LastError; // edi

  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CSslGlobals::m_lReentryCount) <= 1 )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    CSslGlobals::m_hCleanupEvent = EventA;
    if ( !EventA
      || (LastError = 0,
          (CSslGlobals::m_hCleanupWaitObject = (HANDLE)RegisterWaitForSingleObjectEx(
                                                         EventA,
                                                         CSslGlobals::PeriodicCleanupHandler,
                                                         0,
                                                         1000 * CSslGlobals::m_dwCleanupIntervalInSeconds,
                                                         0)) == 0) )
    {
      LastError = GetLastError();
      if ( LastError )
        CSslGlobals::CleanupPeriodicCleanupHandler();
    }
    v0 = LastError;
  }
  else
  {
    v0 = 0;
  }
  _InterlockedDecrement((volatile signed __int32 *)&CSslGlobals::m_lReentryCount);
  return v0;
}

```

## disassembly

```asm
0x18007198c  mov     [rsp+arg_0], rbx
0x180071991  push    rdi
0x180071992  sub     rsp, 30h
0x180071996  mov     eax, 1
0x18007199b  lock xadd cs:?m_lReentryCount@CSslGlobals@@2KA, eax; ulong CSslGlobals::m_lReentryCount
0x1800719a3  inc     eax
0x1800719a5  cmp     eax, 1
0x1800719a8  jbe     short loc_1800719AE
0x1800719aa  xor     ebx, ebx
0x1800719ac  jmp     short loc_180071A0F
0x1800719ae  xor     r9d, r9d; lpName
0x1800719b1  xor     r8d, r8d; bInitialState
0x1800719b4  xor     edx, edx; bManualReset
0x1800719b6  xor     ecx, ecx; lpEventAttributes
0x1800719b8  call    cs:__imp_CreateEventA
0x1800719be  xor     ebx, ebx
0x1800719c0  mov     cs:?m_hCleanupEvent@CSslGlobals@@2PEAXEA, rax; void * CSslGlobals::m_hCleanupEvent
0x1800719c7  test    rax, rax
0x1800719ca  jz      short loc_1800719FC
0x1800719cc  imul    r9d, cs:?m_dwCleanupIntervalInSeconds@CSslGlobals@@2KA, 3E8h; ulong CSslGlobals::m_dwCleanupIntervalInSeconds
0x1800719d7  lea     rdx, ?PeriodicCleanupHandler@CSslGlobals@@SAXPEAXE@Z; CSslGlobals::PeriodicCleanupHandler(void *,uchar)
0x1800719de  xor     r8d, r8d
0x1800719e1  mov     [rsp+38h+var_18], ebx
0x1800719e5  mov     rcx, rax
0x1800719e8  mov     edi, ebx
0x1800719ea  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800719f0  mov     cs:?m_hCleanupWaitObject@CSslGlobals@@2PEAXEA, rax; void * CSslGlobals::m_hCleanupWaitObject
0x1800719f7  test    rax, rax
0x1800719fa  jnz     short loc_180071A0D
0x1800719fc  call    cs:__imp_GetLastError
0x180071a02  mov     edi, eax
0x180071a04  test    eax, eax
0x180071a06  jz      short loc_180071A0D
0x180071a08  call    ?CleanupPeriodicCleanupHandler@CSslGlobals@@SAXXZ; CSslGlobals::CleanupPeriodicCleanupHandler(void)
0x180071a0d  mov     ebx, edi
0x180071a0f  lock dec cs:?m_lReentryCount@CSslGlobals@@2KA; ulong CSslGlobals::m_lReentryCount
0x180071a16  mov     eax, ebx
0x180071a18  mov     rbx, [rsp+38h+arg_0]
0x180071a1d  add     rsp, 30h
0x180071a21  pop     rdi
0x180071a22  retn
```
