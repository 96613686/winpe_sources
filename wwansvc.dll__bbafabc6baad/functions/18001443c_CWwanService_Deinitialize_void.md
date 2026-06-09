# CWwanService::Deinitialize(void)

- ea: `0x18001443c`
- end: `0x180014572`
- name: `?Deinitialize@CWwanService@@QEAAXXZ`
- size: `310`
- prototype: `void __fastcall(CWwanService *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012c38`

## callees

- `0x180008a7c`
- `0x18001443c`
- `0x180014f1c`
- `0x180015d6c`
- `0x180016fd4`
- `0x18001c49c`
- `0x180074150`
- `0x18008a680`
- `0x18009cd1c`
- `0x1800a64ec`
- `0x1800aaad8`
- `0x1800b65f8`
- `0x1800b6798`
- `0x1800b784c`
- `0x1800c0430`
- `0x1800c15a4`
- `0x1800c2dd0`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014473`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014473`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014522`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014522`
- `MobileNetworking!HtDestroyHandleTable` at `0x18001453f`
- `MobileNetworking!HtDestroyHandleTable` at `0x18001453f`

## string_xrefs

- `0x180014514`: `CWwanService::Deinitialize`
- `0x18001455b`: `CWwanService::Deinitialize`
- `0x18001454f`: `WWANSVC Modules Deinitialization Completed`

## pseudocode

```c
void __fastcall CWwanService::Deinitialize(CWwanService *this)
{
  struct _GUID *v2; // rbx
  void *v3; // rbx
  void *v4; // rcx

  if ( *(_BYTE *)this )
  {
    WwanDeinitThreadpool(this);
    g_pWwanThreadpool = 0;
    MBAEUpdaterDeinit();
    WwanGPDeInit();
    DeleteCriticalSection(&stru_180152880);
    WwanSapMgrDeinit();
    WwanNhDeinit();
    WwanNlaPlgDeinit();
    WwanPmDeinit();
    v2 = CWwanRoutePolicyManager::pWwanRoutePolicyManagerInstance;
    if ( CWwanRoutePolicyManager::pWwanRoutePolicyManagerInstance )
    {
      CWwanRoutePolicyManager::~CWwanRoutePolicyManager((CWwanRoutePolicyManager *)CWwanRoutePolicyManager::pWwanRoutePolicyManagerInstance);
      operator delete(v2);
      CWwanRoutePolicyManager::pWwanRoutePolicyManagerInstance = 0;
    }
    v3 = ProfileAdmin::s_pProfileAdminInstance;
    if ( ProfileAdmin::s_pProfileAdminInstance )
    {
      std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ProfileHolder>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProfileHolder>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ProfileHolder>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProfileHolder>>>,0>>(ProfileAdmin::s_pProfileAdminInstance);
      operator delete(v3);
      ProfileAdmin::s_pProfileAdminInstance = 0;
    }
    CWwanManager::DestroyInstance();
    CWwanAoAcHelper::DestroyInstance();
    if ( (__int64)(xmmword_180153A38 - (_QWORD)g_Txm) >> 3 )
    {
      do
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        WwanLog::Warning(
          "CWwanService::Deinitialize",
          0,
          L"g_Txm: global transaction manager list is not empty. Spinning until empty");
        Sleep(0);
      }
      while ( (void *)xmmword_180153A38 != g_Txm );
    }
    HtDestroyHandleTable(g_hHandleTable);
    WwanDimDeinit();
    WwanTimerDeinit(v4);
    *(_BYTE *)this = 0;
    WwanLog::Info("CWwanService::Deinitialize", 0, L"WWANSVC Modules Deinitialization Completed");
  }
}

```

## disassembly

```asm
0x18001443c  mov     [rsp+arg_0], rbx
0x180014441  push    rdi
0x180014442  sub     rsp, 20h
0x180014446  cmp     byte ptr [rcx], 0
0x180014449  mov     rdi, rcx
0x18001444c  jz      loc_180014567
0x180014452  call    ?WwanDeinitThreadpool@@YAXPEAU_WWAN_TP@@@Z; WwanDeinitThreadpool(_WWAN_TP *)
0x180014457  mov     cs:?g_pWwanThreadpool@@3PEAU_WWAN_TP@@EA, 0; _WWAN_TP * g_pWwanThreadpool
0x180014462  call    ?MBAEUpdaterDeinit@@YAKXZ; MBAEUpdaterDeinit(void)
0x180014467  call    WwanGPDeInit
0x18001446c  lea     rcx, stru_180152880; lpCriticalSection
0x180014473  call    cs:__imp_DeleteCriticalSection
0x180014479  call    ?WwanSapMgrDeinit@@YAXXZ; WwanSapMgrDeinit(void)
0x18001447e  call    ?WwanNhDeinit@@YAXXZ; WwanNhDeinit(void)
0x180014483  call    WwanNlaPlgDeinit
0x180014488  call    WwanPmDeinit
0x18001448d  mov     rbx, cs:?pWwanRoutePolicyManagerInstance@CWwanRoutePolicyManager@@0PEAV1@EA; CWwanRoutePolicyManager * CWwanRoutePolicyManager::pWwanRoutePolicyManagerInstance
0x180014494  test    rbx, rbx
0x180014497  jz      short loc_1800144B9
0x180014499  mov     rcx, rbx; this
0x18001449c  call    ??1CWwanRoutePolicyManager@@QEAA@XZ; CWwanRoutePolicyManager::~CWwanRoutePolicyManager(void)
0x1800144a1  mov     edx, 30h ; '0'
0x1800144a6  mov     rcx, rbx; Block
0x1800144a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800144ae  mov     cs:?pWwanRoutePolicyManagerInstance@CWwanRoutePolicyManager@@0PEAV1@EA, 0; CWwanRoutePolicyManager * CWwanRoutePolicyManager::pWwanRoutePolicyManagerInstance
0x1800144b9  mov     rbx, cs:?s_pProfileAdminInstance@ProfileAdmin@@0PEAV1@EA; ProfileAdmin * ProfileAdmin::s_pProfileAdminInstance
0x1800144c0  test    rbx, rbx
0x1800144c3  jz      short loc_1800144E5
0x1800144c5  mov     rcx, rbx
0x1800144c8  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProfileHolder@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProfileHolder@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ProfileHolder>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProfileHolder>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ProfileHolder>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ProfileHolder>>>,0>>(void)
0x1800144cd  mov     edx, 48h ; 'H'
0x1800144d2  mov     rcx, rbx; Block
0x1800144d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800144da  mov     cs:?s_pProfileAdminInstance@ProfileAdmin@@0PEAV1@EA, 0; ProfileAdmin * ProfileAdmin::s_pProfileAdminInstance
0x1800144e5  call    ?DestroyInstance@CWwanManager@@SAXXZ; CWwanManager::DestroyInstance(void)
0x1800144ea  call    ?DestroyInstance@CWwanAoAcHelper@@SAXXZ; CWwanAoAcHelper::DestroyInstance(void)
0x1800144ef  mov     rax, qword ptr cs:xmmword_180153A38
0x1800144f6  sub     rax, cs:?g_Txm@@3V?$vector@PEAUWWAN_TXM@@V?$allocator@PEAUWWAN_TXM@@@std@@@std@@A; std::vector<WWAN_TXM *> g_Txm
0x1800144fd  sar     rax, 3
0x180014501  test    rax, rax
0x180014504  jz      short loc_180014538
0x180014506  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001450b  lea     r8, aGTxmGlobalTran; "g_Txm: global transaction manager list "...
0x180014512  xor     edx, edx; struct _GUID *
0x180014514  lea     rcx, aCwwanserviceDe; "CWwanService::Deinitialize"
0x18001451b  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x180014520  xor     ecx, ecx; dwMilliseconds
0x180014522  call    cs:__imp_Sleep
0x180014528  mov     rax, qword ptr cs:xmmword_180153A38
0x18001452f  cmp     rax, cs:?g_Txm@@3V?$vector@PEAUWWAN_TXM@@V?$allocator@PEAUWWAN_TXM@@@std@@@std@@A; std::vector<WWAN_TXM *> g_Txm
0x180014536  jnz     short loc_180014506
0x180014538  mov     rcx, cs:g_hHandleTable
0x18001453f  call    cs:__imp_HtDestroyHandleTable
0x180014545  call    ?WwanDimDeinit@@YAXXZ; WwanDimDeinit(void)
0x18001454a  call    ?WwanTimerDeinit@@YAXPEAX@Z; WwanTimerDeinit(void *)
0x18001454f  lea     r8, aWwansvcModules_0; "WWANSVC Modules Deinitialization Comple"...
0x180014556  mov     byte ptr [rdi], 0
0x180014559  xor     edx, edx; struct _GUID *
0x18001455b  lea     rcx, aCwwanserviceDe; "CWwanService::Deinitialize"
0x180014562  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180014567  mov     rbx, [rsp+28h+arg_0]
0x18001456c  add     rsp, 20h
0x180014570  pop     rdi
0x180014571  retn
```
