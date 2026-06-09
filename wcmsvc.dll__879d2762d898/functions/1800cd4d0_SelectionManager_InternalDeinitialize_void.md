# SelectionManager::InternalDeinitialize(void)

- ea: `0x1800cd4d0`
- end: `0x1800cd63b`
- name: `?InternalDeinitialize@SelectionManager@@IEAAXXZ`
- size: `363`
- prototype: `void __fastcall(SelectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065414`

## callees

- `0x180010080`
- `0x180019434`
- `0x1800cd4d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cd51e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cd572`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cd5c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cd51e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cd572`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cd5c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd52b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd5d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd52b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd5d3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cd5f0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cd5f0`
- `ext-ms-win-net-cmvpn-l1-1-0!VpnCmOracleShutdown` at `0x1800cd4e2`
- `ext-ms-win-net-cmvpn-l1-1-0!VpnCmOracleShutdown` at `0x1800cd4e2`

## pseudocode

```c
void __fastcall SelectionManager::InternalDeinitialize(SelectionManager *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx

  if ( *((_BYTE *)this + 465) )
    VpnCmOracleShutdown();
  v2 = qword_180140110;
  MappingPolicyManager::s_MappingPolicyManagerInstance = 0;
  qword_180140110 = 0;
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  if ( g_mappingPolicyManagerExitHandle )
  {
    WaitForSingleObject(g_mappingPolicyManagerExitHandle, 0xFFFFFFFF);
    CloseHandle(g_mappingPolicyManagerExitHandle);
    g_mappingPolicyManagerExitHandle = 0;
  }
  v3 = qword_1801400E0;
  RoutePolicyManager::s_RoutePolicyManagerInstance = 0;
  qword_1801400E0 = 0;
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  if ( g_routePolicyManagerExitHandle )
  {
    WaitForSingleObject(g_routePolicyManagerExitHandle, 0xFFFFFFFF);
    CloseHandle(g_routePolicyManagerExitHandle);
    g_routePolicyManagerExitHandle = 0;
  }
  v4 = qword_180140100;
  HttpPolicyManager::s_HttpPolicyManagerInstance = 0;
  qword_180140100 = 0;
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  if ( g_httpPolicyManagerExitHandle )
  {
    WaitForSingleObject(g_httpPolicyManagerExitHandle, 0xFFFFFFFF);
    CloseHandle(g_httpPolicyManagerExitHandle);
    g_httpPolicyManagerExitHandle = 0;
  }
  if ( *((_QWORD *)this + 57) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 57) = 0;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_1e598accbd0633246e27c279a8537074_Traceguids);
  }
}

```

## disassembly

```asm
0x1800cd4d0  push    rbx
0x1800cd4d2  sub     rsp, 20h
0x1800cd4d6  cmp     byte ptr [rcx+1D1h], 0
0x1800cd4dd  mov     rbx, rcx
0x1800cd4e0  jz      short loc_1800CD4E8
0x1800cd4e2  call    cs:__imp_VpnCmOracleShutdown
0x1800cd4e8  mov     rcx, cs:qword_180140110; this
0x1800cd4ef  mov     cs:?s_MappingPolicyManagerInstance@MappingPolicyManager@@0V?$shared_ptr@VMappingPolicyManager@@@std@@A, 0; std::shared_ptr<MappingPolicyManager> MappingPolicyManager::s_MappingPolicyManagerInstance
0x1800cd4fa  mov     cs:qword_180140110, 0
0x1800cd505  test    rcx, rcx
0x1800cd508  jz      short loc_1800CD50F
0x1800cd50a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cd50f  mov     rcx, cs:?g_mappingPolicyManagerExitHandle@@3PEAXEA; hHandle
0x1800cd516  test    rcx, rcx
0x1800cd519  jz      short loc_1800CD53C
0x1800cd51b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800cd51e  call    cs:__imp_WaitForSingleObject
0x1800cd524  mov     rcx, cs:?g_mappingPolicyManagerExitHandle@@3PEAXEA; hObject
0x1800cd52b  call    cs:__imp_CloseHandle
0x1800cd531  mov     cs:?g_mappingPolicyManagerExitHandle@@3PEAXEA, 0; void * g_mappingPolicyManagerExitHandle
0x1800cd53c  mov     rcx, cs:qword_1801400E0; this
0x1800cd543  mov     cs:?s_RoutePolicyManagerInstance@RoutePolicyManager@@0V?$shared_ptr@VRoutePolicyManager@@@std@@A, 0; std::shared_ptr<RoutePolicyManager> RoutePolicyManager::s_RoutePolicyManagerInstance
0x1800cd54e  mov     cs:qword_1801400E0, 0
0x1800cd559  test    rcx, rcx
0x1800cd55c  jz      short loc_1800CD563
0x1800cd55e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cd563  mov     rcx, cs:?g_routePolicyManagerExitHandle@@3PEAXEA; hHandle
0x1800cd56a  test    rcx, rcx
0x1800cd56d  jz      short loc_1800CD590
0x1800cd56f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800cd572  call    cs:__imp_WaitForSingleObject
0x1800cd578  mov     rcx, cs:?g_routePolicyManagerExitHandle@@3PEAXEA; hObject
0x1800cd57f  call    cs:__imp_CloseHandle
0x1800cd585  mov     cs:?g_routePolicyManagerExitHandle@@3PEAXEA, 0; void * g_routePolicyManagerExitHandle
0x1800cd590  mov     rcx, cs:qword_180140100; this
0x1800cd597  mov     cs:?s_HttpPolicyManagerInstance@HttpPolicyManager@@0V?$shared_ptr@VHttpPolicyManager@@@std@@A, 0; std::shared_ptr<HttpPolicyManager> HttpPolicyManager::s_HttpPolicyManagerInstance
0x1800cd5a2  mov     cs:qword_180140100, 0
0x1800cd5ad  test    rcx, rcx
0x1800cd5b0  jz      short loc_1800CD5B7
0x1800cd5b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cd5b7  mov     rcx, cs:?g_httpPolicyManagerExitHandle@@3PEAXEA; hHandle
0x1800cd5be  test    rcx, rcx
0x1800cd5c1  jz      short loc_1800CD5E4
0x1800cd5c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800cd5c6  call    cs:__imp_WaitForSingleObject
0x1800cd5cc  mov     rcx, cs:?g_httpPolicyManagerExitHandle@@3PEAXEA; hObject
0x1800cd5d3  call    cs:__imp_CloseHandle
0x1800cd5d9  mov     cs:?g_httpPolicyManagerExitHandle@@3PEAXEA, 0; void * g_httpPolicyManagerExitHandle
0x1800cd5e4  mov     rcx, [rbx+1C8h]
0x1800cd5eb  test    rcx, rcx
0x1800cd5ee  jz      short loc_1800CD601
0x1800cd5f0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cd5f6  mov     qword ptr [rbx+1C8h], 0
0x1800cd601  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd608  lea     rax, WPP_GLOBAL_Control
0x1800cd60f  cmp     rcx, rax
0x1800cd612  jz      short loc_1800CD635
0x1800cd614  cmp     byte ptr [rcx+19h], 4
0x1800cd618  jb      short loc_1800CD635
0x1800cd61a  test    byte ptr [rcx+1Ch], 1
0x1800cd61e  jz      short loc_1800CD635
0x1800cd620  mov     rcx, [rcx+10h]
0x1800cd624  lea     r8, WPP_1e598accbd0633246e27c279a8537074_Traceguids
0x1800cd62b  mov     edx, 0Eh
0x1800cd630  call    WPP_SF_
0x1800cd635  add     rsp, 20h
0x1800cd639  pop     rbx
0x1800cd63a  retn
```
