# UnloadProxyApi(void)

- ea: `0x18001476c`
- end: `0x18001489c`
- name: `?UnloadProxyApi@@YAJXZ`
- size: `304`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001441c`
- `0x18001451c`
- `0x180016200`
- `0x18005ed48`
- `0x1800abb3c`
- `0x1800c1984`
- `0x1800c1c30`

## callees

- `0x18001476c`
- `0x1800a3da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014781`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800147af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014781`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800147af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001488f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014872`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001488f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800147c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800147c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014813`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001484d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014813`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001484d`

## pseudocode

```c
__int64 UnloadProxyApi(void)
{
  LruResourceManager *v0; // rbx
  LruResourceManager *v1; // rbx

  EnterCriticalSection(&g_csProxyInit);
  if ( g_ullProxyRefs )
  {
    if ( !--g_ullProxyRefs )
    {
      EnterCriticalSection(&g_csDllRef);
      if ( !--g_ullRefs )
      {
        SetEvent(g_hTerminateEvent);
        g_hTerminateEvent = 0;
      }
      LeaveCriticalSection(&g_csDllRef);
      if ( g_fProxyEtwInitialized )
        g_fProxyEtwInitialized = 0;
      v0 = g_pLruResourceManager;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)g_pLruResourceManager, 0xFFFFFFFF) == 1 && v0 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v0 + 32));
        operator delete(v0);
      }
      v1 = g_pLruUsageManager;
      g_pLruResourceManager = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)g_pLruUsageManager, 0xFFFFFFFF) == 1 )
      {
        if ( v1 )
        {
          DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 32));
          operator delete(v1);
        }
      }
      g_pLruUsageManager = 0;
    }
    LeaveCriticalSection(&g_csProxyInit);
    return 0;
  }
  else
  {
    LeaveCriticalSection(&g_csProxyInit);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18001476c  push    rbx
0x18001476e  sub     rsp, 20h
0x180014772  lea     rcx, ?g_csProxyInit@@3VWxCriticalSection@@A; lpCriticalSection
0x180014779  mov     [rsp+28h+arg_4], 0
0x180014781  call    cs:__imp_EnterCriticalSection
0x180014787  mov     rax, cs:?g_ullProxyRefs@@3_KA; unsigned __int64 g_ullProxyRefs
0x18001478e  test    rax, rax
0x180014791  jz      loc_180014880
0x180014797  sub     rax, 1
0x18001479b  mov     cs:?g_ullProxyRefs@@3_KA, rax; unsigned __int64 g_ullProxyRefs
0x1800147a2  jnz     loc_18001486B
0x1800147a8  lea     rcx, ?g_csDllRef@@3VWxCriticalSection@@A; lpCriticalSection
0x1800147af  call    cs:__imp_EnterCriticalSection
0x1800147b5  sub     cs:?g_ullRefs@@3_KA, 1; unsigned __int64 g_ullRefs
0x1800147bd  jnz     short loc_1800147D7
0x1800147bf  mov     rcx, cs:?g_hTerminateEvent@@3PEAXEA; hEvent
0x1800147c6  call    cs:__imp_SetEvent
0x1800147cc  mov     cs:?g_hTerminateEvent@@3PEAXEA, 0; void * g_hTerminateEvent
0x1800147d7  lea     rcx, ?g_csDllRef@@3VWxCriticalSection@@A; lpCriticalSection
0x1800147de  call    cs:__imp_LeaveCriticalSection
0x1800147e4  cmp     cs:?g_fProxyEtwInitialized@@3HA, 0; int g_fProxyEtwInitialized
0x1800147eb  jz      short loc_1800147F7
0x1800147ed  mov     cs:?g_fProxyEtwInitialized@@3HA, 0; int g_fProxyEtwInitialized
0x1800147f7  mov     rbx, cs:?g_pLruResourceManager@@3PEAVLruResourceManager@@EA; LruResourceManager * g_pLruResourceManager
0x1800147fe  or      eax, 0FFFFFFFFh
0x180014801  lock xadd [rbx], eax
0x180014805  cmp     eax, 1
0x180014808  jnz     short loc_180014826
0x18001480a  test    rbx, rbx
0x18001480d  jz      short loc_180014826
0x18001480f  lea     rcx, [rbx+20h]; lpCriticalSection
0x180014813  call    cs:__imp_DeleteCriticalSection
0x180014819  mov     edx, 50h ; 'P'; unsigned __int64
0x18001481e  mov     rcx, rbx; void *
0x180014821  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014826  mov     rbx, cs:?g_pLruUsageManager@@3PEAVLruResourceManager@@EA; LruResourceManager * g_pLruUsageManager
0x18001482d  or      eax, 0FFFFFFFFh
0x180014830  mov     cs:?g_pLruResourceManager@@3PEAVLruResourceManager@@EA, 0; LruResourceManager * g_pLruResourceManager
0x18001483b  lock xadd [rbx], eax
0x18001483f  cmp     eax, 1
0x180014842  jnz     short loc_180014860
0x180014844  test    rbx, rbx
0x180014847  jz      short loc_180014860
0x180014849  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001484d  call    cs:__imp_DeleteCriticalSection
0x180014853  mov     edx, 50h ; 'P'; unsigned __int64
0x180014858  mov     rcx, rbx; void *
0x18001485b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014860  mov     cs:?g_pLruUsageManager@@3PEAVLruResourceManager@@EA, 0; LruResourceManager * g_pLruUsageManager
0x18001486b  lea     rcx, ?g_csProxyInit@@3VWxCriticalSection@@A; lpCriticalSection
0x180014872  call    cs:__imp_LeaveCriticalSection
0x180014878  xor     eax, eax
0x18001487a  add     rsp, 20h
0x18001487e  pop     rbx
0x18001487f  retn
0x180014880  lea     rcx, ?g_csProxyInit@@3VWxCriticalSection@@A; lpCriticalSection
0x180014887  mov     [rsp+28h+arg_4], 0A6h
0x18001488f  call    cs:__imp_LeaveCriticalSection
0x180014895  mov     eax, 8000FFFFh
0x18001489a  jmp     short loc_18001487A
```
