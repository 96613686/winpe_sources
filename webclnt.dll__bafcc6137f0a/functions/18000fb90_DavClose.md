# DavClose

- ea: `0x18000fb90`
- end: `0x18000fcd9`
- name: `DavClose`
- size: `329`
- prototype: `void()`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180025bf8`

## callees

- `0x180003f8c`
- `0x18000fb24`
- `0x18000fb90`
- `0x180010b08`
- `0x18002bfa4`
- `0x18002c814`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18000fc16`
- `ntdll!RtlDeleteResource` at `0x18000fc16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fc92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fc9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fc92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fc9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fc56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fc63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fc56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fc63`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbaa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbb7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbc4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbde`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fca8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbaa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbb7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbc4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fbde`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fca8`
- `KERNEL32!LocalFree` at `0x18000fc32`
- `KERNEL32!LocalFree` at `0x18000fcb1`
- `KERNEL32!LocalFree` at `0x18000fc32`
- `KERNEL32!LocalFree` at `0x18000fcb1`

## pseudocode

```c
void DavClose()
{
  char *v0; // rbx
  _QWORD *v1; // rdx
  HLOCAL *v2; // rax

  if ( ServerTableLockSet )
  {
    DeleteCriticalSection(&HashServerEntryTableLock);
    DeleteCriticalSection(&ServerShareTableLock);
    DeleteCriticalSection(&DavPassportLock);
    DeleteCriticalSection(&NonDAVServerListLock);
    DeleteCriticalSection(&HashExtErrorTableLock);
    DavCleanupExtErrorEntries(1);
    DavFinalizeToBeFinalizedList(1);
    ServerTableLockSet = 0;
  }
  if ( didDavUseObjectInitialize )
  {
    DavDeleteUserEntries();
    RtlDeleteResource(&Resource);
    didDavUseObjectInitialize = 0;
  }
  if ( DAVUserAgent )
  {
    LocalFree((HLOCAL)DAVUserAgent);
    DAVUserAgent = 0;
  }
  v0 = (char *)DavTfsStore;
  if ( DavTfsStore )
  {
    EnterCriticalSection(&TfsGlobalLock);
    EnterCriticalSection((LPCRITICAL_SECTION)(v0 + 56));
    v1 = *(_QWORD **)v0;
    if ( *(char **)(*(_QWORD *)v0 + 8LL) != v0 || (v2 = (HLOCAL *)*((_QWORD *)v0 + 1), *v2 != v0) )
      __fastfail(3u);
    *v2 = v1;
    v1[1] = v2;
    TfsScavengeStoreEntries((__int64)v0, 4u);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v0 + 56));
    LeaveCriticalSection(&TfsGlobalLock);
    DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 56));
    LocalFree(v0);
    TfsShutdown();
    DavTfsStore = 0;
  }
}

```

## disassembly

```asm
0x18000fb90  mov     [rsp+arg_0], rbx
0x18000fb95  push    rdi
0x18000fb96  sub     rsp, 20h
0x18000fb9a  cmp     cs:ServerTableLockSet, 0
0x18000fba1  jz      short loc_18000FC01
0x18000fba3  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x18000fbaa  call    cs:__imp_DeleteCriticalSection
0x18000fbb0  lea     rcx, ServerShareTableLock; lpCriticalSection
0x18000fbb7  call    cs:__imp_DeleteCriticalSection
0x18000fbbd  lea     rcx, DavPassportLock; lpCriticalSection
0x18000fbc4  call    cs:__imp_DeleteCriticalSection
0x18000fbca  lea     rcx, NonDAVServerListLock; lpCriticalSection
0x18000fbd1  call    cs:__imp_DeleteCriticalSection
0x18000fbd7  lea     rcx, HashExtErrorTableLock; lpCriticalSection
0x18000fbde  call    cs:__imp_DeleteCriticalSection
0x18000fbe4  mov     ebx, 1
0x18000fbe9  mov     ecx, ebx
0x18000fbeb  call    DavCleanupExtErrorEntries
0x18000fbf0  mov     ecx, ebx
0x18000fbf2  call    DavFinalizeToBeFinalizedList
0x18000fbf7  mov     cs:ServerTableLockSet, 0
0x18000fc01  cmp     cs:didDavUseObjectInitialize, 0
0x18000fc08  jz      short loc_18000FC26
0x18000fc0a  call    DavDeleteUserEntries
0x18000fc0f  lea     rcx, Resource; Resource
0x18000fc16  call    cs:__imp_RtlDeleteResource
0x18000fc1c  mov     cs:didDavUseObjectInitialize, 0
0x18000fc26  mov     rcx, cs:DAVUserAgent; hMem
0x18000fc2d  test    rcx, rcx
0x18000fc30  jz      short loc_18000FC43
0x18000fc32  call    cs:__imp_LocalFree
0x18000fc38  mov     cs:DAVUserAgent, 0
0x18000fc43  mov     rbx, cs:DavTfsStore
0x18000fc4a  test    rbx, rbx
0x18000fc4d  jz      short loc_18000FCC7
0x18000fc4f  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18000fc56  call    cs:__imp_EnterCriticalSection
0x18000fc5c  lea     rdi, [rbx+38h]
0x18000fc60  mov     rcx, rdi; lpCriticalSection
0x18000fc63  call    cs:__imp_EnterCriticalSection
0x18000fc69  mov     rdx, [rbx]
0x18000fc6c  cmp     [rdx+8], rbx
0x18000fc70  jnz     short loc_18000FCD2
0x18000fc72  mov     rax, [rbx+8]
0x18000fc76  cmp     [rax], rbx
0x18000fc79  jnz     short loc_18000FCD2
0x18000fc7b  mov     [rax], rdx
0x18000fc7e  mov     rcx, rbx
0x18000fc81  mov     [rdx+8], rax
0x18000fc85  mov     edx, 4
0x18000fc8a  call    TfsScavengeStoreEntries
0x18000fc8f  mov     rcx, rdi; lpCriticalSection
0x18000fc92  call    cs:__imp_LeaveCriticalSection
0x18000fc98  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18000fc9f  call    cs:__imp_LeaveCriticalSection
0x18000fca5  mov     rcx, rdi; lpCriticalSection
0x18000fca8  call    cs:__imp_DeleteCriticalSection
0x18000fcae  mov     rcx, rbx; hMem
0x18000fcb1  call    cs:__imp_LocalFree
0x18000fcb7  call    TfsShutdown
0x18000fcbc  mov     cs:DavTfsStore, 0
0x18000fcc7  mov     rbx, [rsp+28h+arg_0]
0x18000fccc  add     rsp, 20h
0x18000fcd0  pop     rdi
0x18000fcd1  retn
0x18000fcd2  mov     ecx, 3
0x18000fcd7  int     29h; Win8: RtlFailFast(ecx)
```
