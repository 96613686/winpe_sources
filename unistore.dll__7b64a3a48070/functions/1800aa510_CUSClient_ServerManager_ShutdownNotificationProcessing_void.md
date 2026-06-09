# CUSClient_ServerManager::ShutdownNotificationProcessing(void)

- ea: `0x1800aa510`
- end: `0x1800aa661`
- name: `?ShutdownNotificationProcessing@CUSClient_ServerManager@@UEAAXXZ`
- size: `337`
- prototype: `void __fastcall(CUSClient_ServerManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18003e764`
- `0x18006432c`
- `0x1800aa510`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa534`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa5ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa534`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aa5ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa5d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa5e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa5d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa5e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800aa632`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800aa632`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aa623`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800aa623`

## pseudocode

```c
void __fastcall CUSClient_ServerManager::ShutdownNotificationProcessing(CUSClient_ServerManager *this)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v2; // rcx
  struct _LIST_ENTRY **p_Flink; // rcx
  __int64 *v4; // rbx
  __int64 *v5; // rax
  __int64 *v6; // [rsp+20h] [rbp-10h] BYREF
  struct _LIST_ENTRY *v7; // [rsp+28h] [rbp-8h]

  v6 = (__int64 *)&v6;
  v7 = (struct _LIST_ENTRY *)&v6;
  EnterCriticalSection(&g_clientNotifyLock);
  g_notificationShutdown = 1;
  while ( 1 )
  {
    Flink = g_adviseList.Flink;
    if ( g_adviseList.Flink == &g_adviseList )
      break;
    if ( g_adviseList.Flink->Blink != &g_adviseList
      || (v2 = g_adviseList.Flink->Flink, g_adviseList.Flink->Flink->Blink != g_adviseList.Flink)
      || (g_adviseList.Flink = g_adviseList.Flink->Flink,
          v2->Blink = &g_adviseList,
          Flink->Blink = Flink,
          Flink->Flink = Flink,
          p_Flink = &v7->Flink,
          (__int64 **)v7->Flink != &v6) )
    {
LABEL_14:
      __fastfail(3u);
    }
    Flink->Blink = v7;
    Flink->Flink = (struct _LIST_ENTRY *)&v6;
    *p_Flink = Flink;
    v7 = Flink;
  }
  EnterCriticalSection(&g_cookieAdvisorMapLock);
  utl::_HashTable<USOID,utl::pair<USOID const,CSyncSessionChanges::SExceptionInfo>,CSyncSessionChanges::USOIDHashTraits,utl::equal_to<USOID>,utl::allocator<utl::pair<USOID const,CSyncSessionChanges::SExceptionInfo>>,0>::_ClearList(&g_cookieAdvisorMap);
  if ( xmmword_18010D380 )
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,unsigned __int64>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned __int64>>,0>::_InitBuckets();
  LeaveCriticalSection(&g_cookieAdvisorMapLock);
  LeaveCriticalSection(&g_clientNotifyLock);
  while ( 1 )
  {
    v4 = v6;
    if ( v6 == (__int64 *)&v6 )
      break;
    if ( (__int64 **)v6[1] != &v6 )
      goto LABEL_14;
    v5 = (__int64 *)*v6;
    if ( *(__int64 **)(*v6 + 8) != v6 )
      goto LABEL_14;
    v6 = (__int64 *)*v6;
    v5[1] = (__int64)&v6;
    v4[1] = (__int64)v4;
    *v4 = (__int64)v4;
    SetThreadpoolWait((PTP_WAIT)*(v4 - 2), 0, 0);
    WaitForThreadpoolWaitCallbacks((PTP_WAIT)*(v4 - 2), 1);
    (*(void (__fastcall **)(__int64 *, __int64))*(v4 - 6))(v4 - 6, 1);
  }
}

```

## disassembly

```asm
0x1800aa510  mov     [rsp-8+arg_0], rbx
0x1800aa515  push    rbp
0x1800aa516  mov     rbp, rsp
0x1800aa519  sub     rsp, 30h
0x1800aa51d  lea     rax, [rbp+var_10]
0x1800aa521  mov     [rbp+var_10], rax
0x1800aa525  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800aa52c  lea     rax, [rbp+var_10]
0x1800aa530  mov     [rbp+var_8], rax
0x1800aa534  call    cs:__imp_EnterCriticalSection
0x1800aa53a  lea     r8, ?g_adviseList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_adviseList
0x1800aa541  mov     cs:?g_notificationShutdown@@3HA, 1; int g_notificationShutdown
0x1800aa54b  mov     rax, cs:?g_adviseList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_adviseList
0x1800aa552  cmp     rax, r8
0x1800aa555  jz      short loc_1800AA5A5
0x1800aa557  cmp     [rax+8], r8
0x1800aa55b  jnz     loc_1800AA64F
0x1800aa561  mov     rcx, [rax]
0x1800aa564  cmp     [rcx+8], rax
0x1800aa568  jnz     loc_1800AA64F
0x1800aa56e  mov     cs:?g_adviseList@@3U_LIST_ENTRY@@A, rcx; _LIST_ENTRY g_adviseList
0x1800aa575  lea     rdx, [rbp+var_10]
0x1800aa579  mov     [rcx+8], r8
0x1800aa57d  mov     [rax+8], rax
0x1800aa581  mov     [rax], rax
0x1800aa584  mov     rcx, [rbp+var_8]
0x1800aa588  cmp     [rcx], rdx
0x1800aa58b  jnz     loc_1800AA64F
0x1800aa591  mov     [rax+8], rcx
0x1800aa595  lea     rdx, [rbp+var_10]
0x1800aa599  mov     [rax], rdx
0x1800aa59c  mov     [rcx], rax
0x1800aa59f  mov     [rbp+var_8], rax
0x1800aa5a3  jmp     short loc_1800AA54B
0x1800aa5a5  lea     rcx, ?g_cookieAdvisorMapLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800aa5ac  call    cs:__imp_EnterCriticalSection
0x1800aa5b2  lea     rcx, ?g_cookieAdvisorMap@@3V?$unordered_map@K_KU?$hash@K@utl@@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_K@utl@@@2@@utl@@A; utl::unordered_map<ulong,unsigned __int64,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,unsigned __int64>>> g_cookieAdvisorMap
0x1800aa5b9  call    ?_ClearList@?$_HashTable@UUSOID@@U?$pair@$$CBUUSOID@@USExceptionInfo@CSyncSessionChanges@@@utl@@UUSOIDHashTraits@CSyncSessionChanges@@U?$equal_to@UUSOID@@@3@V?$allocator@U?$pair@$$CBUUSOID@@USExceptionInfo@CSyncSessionChanges@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<USOID,utl::pair<USOID const,CSyncSessionChanges::SExceptionInfo>,CSyncSessionChanges::USOIDHashTraits,utl::equal_to<USOID>,utl::allocator<utl::pair<USOID const,CSyncSessionChanges::SExceptionInfo>>,0>::_ClearList(void)
0x1800aa5be  cmp     qword ptr cs:xmmword_18010D380, 0
0x1800aa5c6  jz      short loc_1800AA5CD
0x1800aa5c8  call    ?_InitBuckets@?$_HashTable@KU?$pair@$$CBK_K@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_K@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,unsigned __int64>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,unsigned __int64>>,0>::_InitBuckets(void)
0x1800aa5cd  lea     rcx, ?g_cookieAdvisorMapLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800aa5d4  call    cs:__imp_LeaveCriticalSection
0x1800aa5da  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800aa5e1  call    cs:__imp_LeaveCriticalSection
0x1800aa5e7  mov     rbx, [rbp+var_10]
0x1800aa5eb  lea     rax, [rbp+var_10]
0x1800aa5ef  cmp     rbx, rax
0x1800aa5f2  jz      short loc_1800AA656
0x1800aa5f4  lea     rax, [rbp+var_10]
0x1800aa5f8  cmp     [rbx+8], rax
0x1800aa5fc  jnz     short loc_1800AA64F
0x1800aa5fe  mov     rax, [rbx]
0x1800aa601  cmp     [rax+8], rbx
0x1800aa605  jnz     short loc_1800AA64F
0x1800aa607  mov     [rbp+var_10], rax
0x1800aa60b  lea     rcx, [rbp+var_10]
0x1800aa60f  mov     [rax+8], rcx
0x1800aa613  xor     r8d, r8d; pftTimeout
0x1800aa616  mov     [rbx+8], rbx
0x1800aa61a  xor     edx, edx; h
0x1800aa61c  mov     [rbx], rbx
0x1800aa61f  mov     rcx, [rbx-10h]; pwa
0x1800aa623  call    cs:__imp_SetThreadpoolWait
0x1800aa629  mov     rcx, [rbx-10h]; pwa
0x1800aa62d  mov     edx, 1; fCancelPendingCallbacks
0x1800aa632  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800aa638  mov     rax, [rbx-30h]
0x1800aa63c  lea     rcx, [rbx-30h]
0x1800aa640  mov     edx, 1
0x1800aa645  mov     rax, [rax]
0x1800aa648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa64d  jmp     short loc_1800AA5E7
0x1800aa64f  mov     ecx, 3
0x1800aa654  int     29h; Win8: RtlFailFast(ecx)
0x1800aa656  mov     rbx, [rsp+30h+arg_0]
0x1800aa65b  add     rsp, 30h
0x1800aa65f  pop     rbp
0x1800aa660  retn
```
