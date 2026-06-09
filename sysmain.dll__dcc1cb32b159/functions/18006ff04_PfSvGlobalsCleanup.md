# PfSvGlobalsCleanup

- ea: `0x18006ff04`
- end: `0x18007025a`
- name: `PfSvGlobalsCleanup`
- size: `854`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180073494`
- `0x18007376c`
- `0x180088220`

## callees

- `0x180028550`
- `0x180035cc4`
- `0x180051420`
- `0x180059594`
- `0x1800677b4`
- `0x18006ff04`
- `0x180070260`
- `0x18007028c`
- `0x1800702fc`
- `0x180070364`
- `0x18007114c`

## import_xrefs

- `msvcrt!fclose` at `0x180070232`
- `msvcrt!fclose` at `0x180070244`
- `msvcrt!fclose` at `0x180070232`
- `msvcrt!fclose` at `0x180070244`
- `ntdll!NtClose` at `0x18006ff70`
- `ntdll!NtClose` at `0x18006ff70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ff7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ff87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007000a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007003b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800700d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070174`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070211`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ff7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ff87`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007000a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007003b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800700d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070174`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070211`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007005f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070083`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007005f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070083`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070095`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180070095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ffc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007001c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007002e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007004d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070143`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ffc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007001c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007002e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007004d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070143`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701b5`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18006ff40`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18006ff40`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180070220`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180070220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070001`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070001`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070204`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800700c9`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800700e8`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800700c9`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800700e8`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800700b3`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800700b3`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18007015e`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18007015e`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsVaMgrCleanup` at `0x1800701a2`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsVaMgrCleanup` at `0x1800701a2`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsVaMgrFree` at `0x180070198`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsVaMgrFree` at `0x180070198`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18006ff26`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18006ff26`

## pseudocode

```c
void PfSvGlobalsCleanup()
{
  __int64 v0; // rbx
  void *v1; // rcx
  void *v2; // rcx
  void *v3; // rcx
  unsigned int i; // esi
  void *v5; // r8
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  HKEY v9; // rcx
  HKEY v10; // rcx
  HKEY v11; // rcx
  HMODULE v12; // rcx
  TRACEHANDLE v13; // rcx
  REGHANDLE v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  void *v17; // rcx
  __int64 j; // rdi
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // r8
  void *v22; // rcx
  FILE *v23; // rcx
  FILE *v24; // rcx

  v0 = *(_QWORD *)&PfSvcGlobals;
  if ( *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 4280LL) )
    CrmUnregister();
  v1 = *(void **)(v0 + 1888);
  if ( v1 )
    VirtualFree(v1, 0, 0x8000u);
  PfSvMemMonitorCtxCleanup(v0 + 3880);
  PfSvScenCtxScenarioEnd(v0 + 3696, 1);
  v2 = *(void **)(v0 + 3696);
  if ( v2 )
    NtClose(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 3720));
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 1800));
  PfSvConsoleSessionInfoCleanup(v0 + 1840);
  PfSvConsoleSessionInfoCleanup(v0 + 1856);
  PfSvConsoleSessionInfoCleanup(v0 + 1872);
  v3 = *(void **)(v0 + 1760);
  if ( v3 )
    CloseHandle(v3);
  for ( i = 1; i <= *(_DWORD *)(v0 + 1784); ++i )
    PfsActionItemCleanup(*(_QWORD *)(v0 + 1776) + 24LL * i);
  v5 = *(void **)(v0 + 1776);
  if ( v5 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 1720));
  v6 = *(void **)(v0 + 1664);
  if ( v6 )
    CloseHandle(v6);
  v7 = *(void **)(v0 + 1672);
  if ( v7 )
    CloseHandle(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 1624));
  v8 = *(void **)(v0 + 880);
  if ( v8 )
    CloseHandle(v8);
  v9 = *(HKEY *)(v0 + 1432);
  if ( v9 )
    RegCloseKey(v9);
  v10 = *(HKEY *)(v0 + 1440);
  if ( v10 )
    RegCloseKey(v10);
  v11 = *(HKEY *)(v0 + 1448);
  if ( v11 )
    RegCloseKey(v11);
  v12 = *(HMODULE *)(v0 + 1416);
  if ( v12 )
    FreeLibrary(v12);
  PfDiContextCleanup(v0 + 1576);
  v13 = *(_QWORD *)(v0 + 384);
  if ( v13 )
    UnregisterTraceGuids(v13);
  if ( *(_DWORD *)(v0 + 400) )
    EventUnregister(*(_QWORD *)(v0 + 392));
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 408));
  v14 = *(_QWORD *)(v0 + 472);
  if ( v14 )
    EventUnregister(v14);
  v15 = *(_QWORD *)(v0 + 3664);
  if ( v15 )
    PfScStringDereferenceEx(*(_QWORD *)&PfSvcGlobals + 96LL, v15, 0);
  v16 = *(_QWORD *)(v0 + 3672);
  if ( v16 )
    PfScStringDereferenceEx(*(_QWORD *)&PfSvcGlobals + 96LL, v16, 0);
  PfScCleanupEx(v0 + 96, 0);
  v17 = *(void **)(v0 + 3656);
  if ( v17 )
    CloseHandle(v17);
  for ( j = 0; j != 4; ++j )
  {
    v19 = *(void **)(v0 + 16 * j + 1512);
    if ( v19 )
      PowerSettingUnregisterNotification(v19);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 1472));
  PfHpChunkHeapCleanup(v0 + 3928);
  if ( *(_QWORD *)v0 )
    PfsVaMgrFree(*(_QWORD *)(v0 + 8), *(_QWORD *)v0, 0x10000);
  PfsVaMgrCleanup(v0 + 16);
  v20 = *(void **)(v0 + 512);
  if ( v20 != (void *)-1LL )
    CloseHandle(v20);
  PfSvStackTraceContextCleanup(v0 + 4360);
  PfSvStackTraceContextCleanup(v0 + 4392);
  PfSvStackTraceContextCleanup(v0 + 4424);
  PfSvDbgHeapCleanup(v0 + 4152);
  v21 = *(void **)(v0 + 4296);
  if ( v21 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v21);
  DeleteCriticalSection((LPCRITICAL_SECTION)(v0 + 4304));
  v22 = *(void **)(v0 + 88);
  if ( v22 )
    HeapDestroy(v22);
  v23 = *(FILE **)(v0 + 3680);
  if ( v23 )
    fclose(v23);
  v24 = *(FILE **)(v0 + 3688);
  if ( v24 )
    fclose(v24);
}

```

## disassembly

```asm
0x18006ff04  mov     [rsp+arg_0], rbx
0x18006ff09  mov     [rsp+arg_8], rsi
0x18006ff0e  push    rdi
0x18006ff0f  sub     rsp, 20h
0x18006ff13  mov     rbx, cs:PfSvcGlobals
0x18006ff1a  mov     rcx, [rbx+10B8h]
0x18006ff21  test    rcx, rcx
0x18006ff24  jz      short loc_18006FF2C
0x18006ff26  call    cs:__imp_CrmUnregister
0x18006ff2c  mov     rcx, [rbx+760h]; lpAddress
0x18006ff33  test    rcx, rcx
0x18006ff36  jz      short loc_18006FF46
0x18006ff38  xor     edx, edx; dwSize
0x18006ff3a  mov     r8d, 8000h; dwFreeType
0x18006ff40  call    cs:__imp_VirtualFree
0x18006ff46  lea     rcx, [rbx+0F28h]
0x18006ff4d  call    PfSvMemMonitorCtxCleanup
0x18006ff52  xor     r8d, r8d
0x18006ff55  lea     rdi, [rbx+0E70h]
0x18006ff5c  mov     rcx, rdi
0x18006ff5f  lea     edx, [r8+1]
0x18006ff63  call    PfSvScenCtxScenarioEnd
0x18006ff68  mov     rcx, [rdi]; Handle
0x18006ff6b  test    rcx, rcx
0x18006ff6e  jz      short loc_18006FF76
0x18006ff70  call    cs:__imp_NtClose
0x18006ff76  lea     rcx, [rdi+18h]; lpCriticalSection
0x18006ff7a  call    cs:__imp_DeleteCriticalSection
0x18006ff80  lea     rcx, [rbx+708h]; lpCriticalSection
0x18006ff87  call    cs:__imp_DeleteCriticalSection
0x18006ff8d  lea     rcx, [rbx+730h]
0x18006ff94  call    PfSvConsoleSessionInfoCleanup
0x18006ff99  lea     rcx, [rbx+740h]
0x18006ffa0  call    PfSvConsoleSessionInfoCleanup
0x18006ffa5  lea     rcx, [rbx+750h]
0x18006ffac  call    PfSvConsoleSessionInfoCleanup
0x18006ffb1  lea     rdi, [rbx+6B8h]
0x18006ffb8  mov     rcx, [rdi+28h]; hObject
0x18006ffbc  test    rcx, rcx
0x18006ffbf  jz      short loc_18006FFC7
0x18006ffc1  call    cs:__imp_CloseHandle
0x18006ffc7  mov     esi, 1
0x18006ffcc  cmp     [rdi+40h], esi
0x18006ffcf  jb      short loc_18006FFEB
0x18006ffd1  mov     eax, esi
0x18006ffd3  lea     rcx, [rax+rax*2]
0x18006ffd7  mov     rax, [rdi+38h]
0x18006ffdb  lea     rcx, [rax+rcx*8]
0x18006ffdf  call    PfsActionItemCleanup
0x18006ffe4  inc     esi
0x18006ffe6  cmp     esi, [rdi+40h]
0x18006ffe9  jbe     short loc_18006FFD1
0x18006ffeb  mov     r8, [rdi+38h]; lpMem
0x18006ffef  test    r8, r8
0x18006fff2  jz      short loc_180070007
0x18006fff4  mov     rcx, cs:PfSvcGlobals
0x18006fffb  xor     edx, edx; dwFlags
0x18006fffd  mov     rcx, [rcx+58h]; hHeap
0x180070001  call    cs:__imp_HeapFree
0x180070007  mov     rcx, rdi; lpCriticalSection
0x18007000a  call    cs:__imp_DeleteCriticalSection
0x180070010  mov     rcx, [rbx+680h]; hObject
0x180070017  test    rcx, rcx
0x18007001a  jz      short loc_180070022
0x18007001c  call    cs:__imp_CloseHandle
0x180070022  mov     rcx, [rbx+688h]; hObject
0x180070029  test    rcx, rcx
0x18007002c  jz      short loc_180070034
0x18007002e  call    cs:__imp_CloseHandle
0x180070034  lea     rcx, [rbx+658h]; lpCriticalSection
0x18007003b  call    cs:__imp_DeleteCriticalSection
0x180070041  mov     rcx, [rbx+370h]; hObject
0x180070048  test    rcx, rcx
0x18007004b  jz      short loc_180070053
0x18007004d  call    cs:__imp_CloseHandle
0x180070053  mov     rcx, [rbx+598h]; hKey
0x18007005a  test    rcx, rcx
0x18007005d  jz      short loc_180070065
0x18007005f  call    cs:__imp_RegCloseKey
0x180070065  mov     rcx, [rbx+5A0h]; hKey
0x18007006c  test    rcx, rcx
0x18007006f  jz      short loc_180070077
0x180070071  call    cs:__imp_RegCloseKey
0x180070077  mov     rcx, [rbx+5A8h]; hKey
0x18007007e  test    rcx, rcx
0x180070081  jz      short loc_180070089
0x180070083  call    cs:__imp_RegCloseKey
0x180070089  mov     rcx, [rbx+588h]; hLibModule
0x180070090  test    rcx, rcx
0x180070093  jz      short loc_18007009B
0x180070095  call    cs:__imp_FreeLibrary
0x18007009b  lea     rcx, [rbx+628h]
0x1800700a2  call    PfDiContextCleanup
0x1800700a7  mov     rcx, [rbx+180h]; RegistrationHandle
0x1800700ae  test    rcx, rcx
0x1800700b1  jz      short loc_1800700B9
0x1800700b3  call    cs:__imp_UnregisterTraceGuids
0x1800700b9  cmp     dword ptr [rbx+190h], 0
0x1800700c0  jz      short loc_1800700CF
0x1800700c2  mov     rcx, [rbx+188h]; RegHandle
0x1800700c9  call    cs:__imp_EventUnregister
0x1800700cf  lea     rcx, [rbx+198h]; lpCriticalSection
0x1800700d6  call    cs:__imp_DeleteCriticalSection
0x1800700dc  mov     rcx, [rbx+1D8h]; RegHandle
0x1800700e3  test    rcx, rcx
0x1800700e6  jz      short loc_1800700EE
0x1800700e8  call    cs:__imp_EventUnregister
0x1800700ee  mov     rdx, [rbx+0E50h]
0x1800700f5  test    rdx, rdx
0x1800700f8  jz      short loc_18007010D
0x1800700fa  mov     rcx, cs:PfSvcGlobals
0x180070101  xor     r8d, r8d
0x180070104  add     rcx, 60h ; '`'
0x180070108  call    PfScStringDereferenceEx
0x18007010d  mov     rdx, [rbx+0E58h]
0x180070114  test    rdx, rdx
0x180070117  jz      short loc_18007012C
0x180070119  mov     rcx, cs:PfSvcGlobals
0x180070120  xor     r8d, r8d
0x180070123  add     rcx, 60h ; '`'
0x180070127  call    PfScStringDereferenceEx
0x18007012c  lea     rcx, [rbx+60h]
0x180070130  xor     edx, edx
0x180070132  call    PfScCleanupEx
0x180070137  mov     rcx, [rbx+0E48h]; hObject
0x18007013e  test    rcx, rcx
0x180070141  jz      short loc_180070149
0x180070143  call    cs:__imp_CloseHandle
0x180070149  xor     edi, edi
0x18007014b  mov     rax, rdi
0x18007014e  add     rax, rax
0x180070151  mov     rcx, [rbx+rax*8+5E8h]; RegistrationHandle
0x180070159  test    rcx, rcx
0x18007015c  jz      short loc_180070164
0x18007015e  call    cs:__imp_PowerSettingUnregisterNotification
0x180070164  inc     rdi
0x180070167  cmp     rdi, 4
0x18007016b  jnz     short loc_18007014B
0x18007016d  lea     rcx, [rbx+5C0h]; lpCriticalSection
0x180070174  call    cs:__imp_DeleteCriticalSection
0x18007017a  lea     rcx, [rbx+0F58h]
0x180070181  call    PfHpChunkHeapCleanup
0x180070186  mov     rdx, [rbx]
0x180070189  test    rdx, rdx
0x18007018c  jz      short loc_18007019E
0x18007018e  mov     rcx, [rbx+8]
0x180070192  mov     r8d, 10000h
0x180070198  call    cs:__imp_PfsVaMgrFree
0x18007019e  lea     rcx, [rbx+10h]
0x1800701a2  call    cs:__imp_PfsVaMgrCleanup
0x1800701a8  mov     rcx, [rbx+200h]; hObject
0x1800701af  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800701b3  jz      short loc_1800701BB
0x1800701b5  call    cs:__imp_CloseHandle
0x1800701bb  lea     rcx, [rbx+1108h]
0x1800701c2  call    PfSvStackTraceContextCleanup
0x1800701c7  lea     rcx, [rbx+1128h]
0x1800701ce  call    PfSvStackTraceContextCleanup
0x1800701d3  lea     rcx, [rbx+1148h]
0x1800701da  call    PfSvStackTraceContextCleanup
0x1800701df  lea     rcx, [rbx+1038h]
0x1800701e6  call    PfSvDbgHeapCleanup
0x1800701eb  mov     r8, [rbx+10C8h]; lpMem
0x1800701f2  test    r8, r8
0x1800701f5  jz      short loc_18007020A
0x1800701f7  mov     rcx, cs:PfSvcGlobals
0x1800701fe  xor     edx, edx; dwFlags
0x180070200  mov     rcx, [rcx+58h]; hHeap
0x180070204  call    cs:__imp_HeapFree
0x18007020a  lea     rcx, [rbx+10D0h]; lpCriticalSection
0x180070211  call    cs:__imp_DeleteCriticalSection
0x180070217  mov     rcx, [rbx+58h]; hHeap
0x18007021b  test    rcx, rcx
0x18007021e  jz      short loc_180070226
0x180070220  call    cs:__imp_HeapDestroy
0x180070226  mov     rcx, [rbx+0E60h]; Stream
0x18007022d  test    rcx, rcx
0x180070230  jz      short loc_180070238
0x180070232  call    cs:__imp_fclose
0x180070238  mov     rcx, [rbx+0E68h]; Stream
0x18007023f  test    rcx, rcx
0x180070242  jz      short loc_18007024A
0x180070244  call    cs:__imp_fclose
0x18007024a  mov     rbx, [rsp+28h+arg_0]
0x18007024f  mov     rsi, [rsp+28h+arg_8]
0x180070254  add     rsp, 20h
0x180070258  pop     rdi
0x180070259  retn
```
