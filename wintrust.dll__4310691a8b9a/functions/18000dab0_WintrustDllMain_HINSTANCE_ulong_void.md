# WintrustDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18000dab0`
- end: `0x18000dc89`
- name: `?WintrustDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `473`
- prototype: `int(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800265e8`

## callees

- `0x18000dab0`
- `0x18000dc90`
- `0x18000dd4c`
- `0x18000dd94`
- `0x18000de38`
- `0x18000de84`
- `0x18000df38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000dad6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000dad6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dc35`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dc35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dba8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000dba8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18000daf7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18000db4a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18000daf7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18000db4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000db19`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000db66`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000db82`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000db19`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000db66`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000db82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbef`
- `CRYPT32!I_CryptFreeLruCache` at `0x18000dc28`
- `CRYPT32!I_CryptFreeLruCache` at `0x18000dc28`

## pseudocode

```c
__int64 __fastcall WintrustDllMain(HINSTANCE a1, unsigned int a2, void *a3)
{
  CCatalogCache *v4; // rcx
  HANDLE *v6; // rcx

  if ( !a2 )
  {
    if ( qword_180069DC0 )
      I_CryptFreeLruCache(qword_180069DC0, 0, 0);
    DeleteCriticalSection(&g_CatalogCache);
    WintrustUnloadProviderList();
    StoreProviderUnload();
    LockFree(&sProvLock);
    LockFree(&sStoreLock);
    EventFree();
    return ASNDllMain(a1, a2, a3);
  }
  if ( a2 != 1 )
    return ASNDllMain(a1, a2, a3);
  hMeDLL = (__int64)a1;
  DisableThreadLibraryCalls(a1);
  dword_180069D54 = 0x20000;
  dword_180069D50 = 0;
  sProvLock = CreateMutexA(0, 0, 0);
  if ( sProvLock )
  {
    hEvent = CreateEventA(0, a2, a2, 0);
    if ( !hEvent )
    {
      CloseHandle(sProvLock);
      sProvLock = 0;
      return 0;
    }
    dword_180069D3C = 0x20000;
    dword_180069D38 = 0;
    sStoreLock = CreateMutexA(0, 0, 0);
    if ( sStoreLock )
    {
      qword_180069D30 = (__int64)CreateEventA(0, a2, a2, 0);
      if ( qword_180069D30 )
      {
        hStoreEvent = CreateEventA(0, a2, a2, 0);
        if ( hStoreEvent )
        {
          if ( (unsigned int)CCatalogCache::Initialize(v4) )
          {
            SetEvent(hStoreEvent);
            return ASNDllMain(a1, a2, a3);
          }
          LockFree(&sProvLock);
          LockFree(&sStoreLock);
          EventFree();
          return 0;
        }
        LockFree(&sProvLock);
        v6 = &sStoreLock;
LABEL_13:
        LockFree(v6);
        return 0;
      }
      CloseHandle(sStoreLock);
      sStoreLock = 0;
    }
    v6 = &sProvLock;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dab0  mov     [rsp+arg_0], rbx
0x18000dab5  push    rsi
0x18000dab6  sub     rsp, 20h
0x18000daba  mov     ebx, edx
0x18000dabc  mov     eax, edx
0x18000dabe  test    edx, edx
0x18000dac0  jz      loc_18000DC17
0x18000dac6  cmp     eax, 1
0x18000dac9  jnz     loc_18000DBAE
0x18000dacf  mov     cs:hMeDLL, rcx
0x18000dad6  call    cs:__imp_DisableThreadLibraryCalls
0x18000dadc  xor     r8d, r8d; lpName
0x18000dadf  mov     cs:dword_180069D54, 20000h
0x18000dae9  xor     edx, edx; bInitialOwner
0x18000daeb  mov     cs:dword_180069D50, 0
0x18000daf5  xor     ecx, ecx; lpMutexAttributes
0x18000daf7  call    cs:__imp_CreateMutexA
0x18000dafd  mov     cs:sProvLock, rax
0x18000db04  test    rax, rax
0x18000db07  jz      loc_18000DBDB
0x18000db0d  xor     r9d, r9d; lpName
0x18000db10  mov     r8d, ebx; bInitialState
0x18000db13  mov     edx, ebx; bManualReset
0x18000db15  xor     ecx, ecx; lpEventAttributes
0x18000db17  mov     esi, ebx
0x18000db19  call    cs:__imp_CreateEventA
0x18000db1f  mov     cs:hEvent, rax
0x18000db26  test    rax, rax
0x18000db29  jz      loc_18000DBE8
0x18000db2f  xor     r8d, r8d; lpName
0x18000db32  mov     cs:dword_180069D3C, 20000h
0x18000db3c  xor     edx, edx; bInitialOwner
0x18000db3e  mov     cs:dword_180069D38, 0
0x18000db48  xor     ecx, ecx; lpMutexAttributes
0x18000db4a  call    cs:__imp_CreateMutexA
0x18000db50  mov     cs:sStoreLock, rax
0x18000db57  test    rax, rax
0x18000db5a  jz      short loc_18000DBCF
0x18000db5c  xor     r9d, r9d; lpName
0x18000db5f  mov     r8d, ebx; bInitialState
0x18000db62  mov     edx, ebx; bManualReset
0x18000db64  xor     ecx, ecx; lpEventAttributes
0x18000db66  call    cs:__imp_CreateEventA
0x18000db6c  mov     cs:qword_180069D30, rax
0x18000db73  test    rax, rax
0x18000db76  jz      short loc_18000DBB7
0x18000db78  xor     r9d, r9d; lpName
0x18000db7b  mov     r8d, ebx; bInitialState
0x18000db7e  mov     edx, ebx; bManualReset
0x18000db80  xor     ecx, ecx; lpEventAttributes
0x18000db82  call    cs:__imp_CreateEventA
0x18000db88  mov     cs:hStoreEvent, rax
0x18000db8f  test    rax, rax
0x18000db92  jz      short loc_18000DC02
0x18000db94  call    ?Initialize@CCatalogCache@@QEAAHXZ; CCatalogCache::Initialize(void)
0x18000db99  test    eax, eax
0x18000db9b  jz      loc_18000DC67
0x18000dba1  mov     rcx, cs:hStoreEvent; hEvent
0x18000dba8  call    cs:__imp_SetEvent
0x18000dbae  mov     edx, ebx; unsigned int
0x18000dbb0  call    ?ASNDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z; ASNDllMain(HINSTANCE__ *,ulong,void *)
0x18000dbb5  jmp     short loc_18000DBDD
0x18000dbb7  mov     rcx, cs:sStoreLock; hObject
0x18000dbbe  call    cs:__imp_CloseHandle
0x18000dbc4  mov     cs:sStoreLock, 0
0x18000dbcf  lea     rcx, sProvLock
0x18000dbd6  call    LockFree
0x18000dbdb  xor     eax, eax
0x18000dbdd  mov     rbx, [rsp+28h+arg_0]
0x18000dbe2  add     rsp, 20h
0x18000dbe6  pop     rsi
0x18000dbe7  retn
0x18000dbe8  mov     rcx, cs:sProvLock; hObject
0x18000dbef  call    cs:__imp_CloseHandle
0x18000dbf5  mov     cs:sProvLock, 0
0x18000dc00  jmp     short loc_18000DBDB
0x18000dc02  lea     rcx, sProvLock
0x18000dc09  call    LockFree
0x18000dc0e  lea     rcx, sStoreLock
0x18000dc15  jmp     short loc_18000DBD6
0x18000dc17  mov     rcx, cs:qword_180069DC0
0x18000dc1e  test    rcx, rcx
0x18000dc21  jz      short loc_18000DC2E
0x18000dc23  xor     r8d, r8d
0x18000dc26  xor     edx, edx
0x18000dc28  call    cs:__imp_I_CryptFreeLruCache
0x18000dc2e  lea     rcx, ?g_CatalogCache@@3VCCatalogCache@@A; lpCriticalSection
0x18000dc35  call    cs:__imp_DeleteCriticalSection
0x18000dc3b  call    ?WintrustUnloadProviderList@@YAHXZ; WintrustUnloadProviderList(void)
0x18000dc40  call    StoreProviderUnload
0x18000dc45  lea     rcx, sProvLock
0x18000dc4c  call    LockFree
0x18000dc51  lea     rcx, sStoreLock
0x18000dc58  call    LockFree
0x18000dc5d  call    EventFree
0x18000dc62  jmp     loc_18000DBAE
0x18000dc67  lea     rcx, sProvLock
0x18000dc6e  call    LockFree
0x18000dc73  lea     rcx, sStoreLock
0x18000dc7a  call    LockFree
0x18000dc7f  call    EventFree
0x18000dc84  jmp     loc_18000DBDB
```
