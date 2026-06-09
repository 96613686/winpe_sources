# USDllMainImpl(void *,ulong,void *)

- ea: `0x1800635ec`
- end: `0x1800636c0`
- name: `?USDllMainImpl@@YAJPEAXK0@Z`
- size: `212`
- prototype: `__int64 __fastcall(void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c388`

## callees

- `0x180024d28`
- `0x1800635ec`
- `0x180063760`
- `0x180065c44`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006363e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006363e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063657`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063657`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800636b3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800636b3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180063678`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180063678`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18006366b`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18006366b`

## pseudocode

```c
__int64 __fastcall USDllMainImpl(HMODULE a1, __int64 a2, void *a3)
{
  DWORD v3; // ecx
  __int64 v4; // rdx

  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 == 1 )
    {
      DisableThreadLibraryCalls(a1);
      McGenEventRegister_EventRegister(
        MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE,
        v4,
        &MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context,
        &MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context);
      EventSetInformation(
        MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context,
        2,
        &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
        (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
    }
  }
  else
  {
    dword_18010C278 = 1;
    if ( g_pFactory )
    {
      (*(void (__fastcall **)(struct IUSFactory *, __int64, void *))(*(_QWORD *)g_pFactory + 16LL))(g_pFactory, a2, a3);
      g_pFactory = 0;
    }
    McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context, a2, a3);
    CStoreManager::s_dwDeviceStoreId = 0;
    EnterCriticalSection(&DBAccess::ms_csLock);
    utl::list<DBAccess::CachedAccess,utl::allocator<DBAccess::CachedAccess>>::clear(&DBAccess::ms_accessors);
    LeaveCriticalSection(&DBAccess::ms_csLock);
    v3 = _InterlockedExchange((volatile __int32 *)&g_dwCallerClientIdSlot, -1);
    if ( v3 != -1 )
      TlsFree(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800635ec  sub     rsp, 28h
0x1800635f0  test    edx, edx
0x1800635f2  jnz     short loc_180063673
0x1800635f4  mov     rcx, cs:?g_pFactory@@3PEAUIUSFactory@@EA; IUSFactory * g_pFactory
0x1800635fb  mov     cs:dword_18010C278, 1
0x180063605  test    rcx, rcx
0x180063608  jz      short loc_180063621
0x18006360a  mov     rax, [rcx]
0x18006360d  mov     rax, [rax+10h]
0x180063611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063616  mov     cs:?g_pFactory@@3PEAUIUSFactory@@EA, 0; IUSFactory * g_pFactory
0x180063621  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context
0x180063628  call    McGenEventUnregister_EventUnregister
0x18006362d  lea     rcx, ?ms_csLock@DBAccess@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x180063634  mov     cs:?s_dwDeviceStoreId@CStoreManager@@0KA, 0; ulong CStoreManager::s_dwDeviceStoreId
0x18006363e  call    cs:__imp_EnterCriticalSection
0x180063644  lea     rcx, ?ms_accessors@DBAccess@@0V?$list@UCachedAccess@DBAccess@@V?$allocator@UCachedAccess@DBAccess@@@utl@@@utl@@A; utl::list<DBAccess::CachedAccess,utl::allocator<DBAccess::CachedAccess>> DBAccess::ms_accessors
0x18006364b  call    ?clear@?$list@UCachedAccess@DBAccess@@V?$allocator@UCachedAccess@DBAccess@@@utl@@@utl@@QEAAXXZ; utl::list<DBAccess::CachedAccess,utl::allocator<DBAccess::CachedAccess>>::clear(void)
0x180063650  lea     rcx, ?ms_csLock@DBAccess@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x180063657  call    cs:__imp_LeaveCriticalSection
0x18006365d  or      ecx, 0FFFFFFFFh
0x180063660  xchg    ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x180063666  cmp     ecx, 0FFFFFFFFh
0x180063669  jz      short loc_1800636B9
0x18006366b  call    cs:__imp_TlsFree
0x180063671  jmp     short loc_1800636B9
0x180063673  cmp     edx, 1
0x180063676  jnz     short loc_1800636B9
0x180063678  call    cs:__imp_DisableThreadLibraryCalls
0x18006367e  lea     r9, MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context
0x180063685  lea     r8, MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context
0x18006368c  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE
0x180063693  call    McGenEventRegister_EventRegister
0x180063698  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x1800636a0  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x1800636a7  mov     rcx, cs:MICROSOFT_WINDOWS_USERDATAACCESS_UNIFIEDSTORE_Context
0x1800636ae  mov     edx, 2
0x1800636b3  call    cs:__imp_EventSetInformation
0x1800636b9  xor     eax, eax
0x1800636bb  add     rsp, 28h
0x1800636bf  retn
```
