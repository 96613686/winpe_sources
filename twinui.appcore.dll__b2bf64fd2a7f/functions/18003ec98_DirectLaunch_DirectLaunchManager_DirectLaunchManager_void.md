# DirectLaunch::DirectLaunchManager::~DirectLaunchManager(void)

- ea: `0x18003ec98`
- end: `0x18003ed50`
- name: `??1DirectLaunchManager@DirectLaunch@@QEAA@XZ`
- size: `184`
- prototype: `void __fastcall(DirectLaunch::DirectLaunchManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fc90`

## callees

- `0x18002265c`
- `0x18003e5a0`
- `0x18003e5bc`
- `0x18003e62c`
- `0x18003e6c8`
- `0x18003ec98`
- `0x180040134`
- `0x180043224`
- `0x180043a2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003ecb3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003ecb3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003ece0`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003ece0`

## pseudocode

```c
void __fastcall DirectLaunch::DirectLaunchManager::~DirectLaunchManager(DirectLaunch::DirectLaunchManager *this)
{
  HKEY *v1; // rdi
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  std::_Ref_count_base *v6; // rcx
  unsigned int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (HKEY *)((char *)this + 40);
  v3 = (HKEY)*((_QWORD *)this + 5);
  if ( v3 )
  {
    v4 = RegDeleteTreeW(v3, 0);
    if ( v4 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchManager.h",
        (const char *)v4,
        v7);
    v5 = RegDeleteKeyW(*v1, &pszDefault);
    if ( v5 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecoreuap\\shell\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchManager.h",
        (const char *)v5,
        v7);
  }
  DirectLaunch::details::DirectLaunchTelemetry::DirectLaunchManagerDestroyed();
  std::_Optional_destruct_base<DirectLaunch::details::DefaultAssociationMonitor,0>::~_Optional_destruct_base<DirectLaunch::details::DefaultAssociationMonitor,0>((char *)this + 192);
  std::_Optional_destruct_base<UserChoiceUtil::DefaultAssociationChangeWatcher,0>::~_Optional_destruct_base<UserChoiceUtil::DefaultAssociationChangeWatcher,0>((char *)this + 64);
  wil::com_ptr_t<IShellItemArray,wil::err_returncode_policy>::~com_ptr_t<IShellItemArray,wil::err_returncode_policy>((char *)this + 56);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v1);
  std::_Tree<std::_Tmap_traits<std::wstring,DirectLaunch::DirectLaunchManager::HandlerEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,DirectLaunch::DirectLaunchManager::HandlerEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>,0>>((char *)this + 24);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
  if ( v6 )
    std::_Ref_count_base::_Decwref(v6);
}

```

## disassembly

```asm
0x18003ec98  mov     [rsp+arg_0], rbx
0x18003ec9d  push    rdi; unsigned int
0x18003ec9e  sub     rsp, 20h
0x18003eca2  lea     rdi, [rcx+28h]
0x18003eca6  mov     rbx, rcx
0x18003eca9  mov     rcx, [rdi]; hKey
0x18003ecac  test    rcx, rcx
0x18003ecaf  jz      short loc_18003ED03
0x18003ecb1  xor     edx, edx; lpSubKey
0x18003ecb3  call    cs:__imp_RegDeleteTreeW
0x18003ecb9  test    eax, eax
0x18003ecbb  jz      short loc_18003ECD6
0x18003ecbd  mov     rcx, [rsp+28h]; this
0x18003ecc2  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\SrcPkg\\DirectLaunch"...
0x18003ecc9  mov     r9d, eax; char *
0x18003eccc  mov     edx, 151h; void *
0x18003ecd1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003ecd6  mov     rcx, [rdi]; hKey
0x18003ecd9  lea     rdx, pszDefault; lpSubKey
0x18003ece0  call    cs:__imp_RegDeleteKeyW
0x18003ece6  test    eax, eax
0x18003ece8  jz      short loc_18003ED03
0x18003ecea  mov     rcx, [rsp+28h]; this
0x18003ecef  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\SrcPkg\\DirectLaunch"...
0x18003ecf6  mov     r9d, eax; char *
0x18003ecf9  mov     edx, 152h; void *
0x18003ecfe  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003ed03  call    ?DirectLaunchManagerDestroyed@DirectLaunchTelemetry@details@DirectLaunch@@SAXXZ; DirectLaunch::details::DirectLaunchTelemetry::DirectLaunchManagerDestroyed(void)
0x18003ed08  lea     rcx, [rbx+0C0h]
0x18003ed0f  call    ??1?$_Optional_destruct_base@VDefaultAssociationMonitor@details@DirectLaunch@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<DirectLaunch::details::DefaultAssociationMonitor,0>::~_Optional_destruct_base<DirectLaunch::details::DefaultAssociationMonitor,0>(void)
0x18003ed14  lea     rcx, [rbx+40h]
0x18003ed18  call    ??1?$_Optional_destruct_base@VDefaultAssociationChangeWatcher@UserChoiceUtil@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<UserChoiceUtil::DefaultAssociationChangeWatcher,0>::~_Optional_destruct_base<UserChoiceUtil::DefaultAssociationChangeWatcher,0>(void)
0x18003ed1d  lea     rcx, [rbx+38h]
0x18003ed21  call    ??1?$com_ptr_t@UIShellItemArray@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellItemArray,wil::err_returncode_policy>::~com_ptr_t<IShellItemArray,wil::err_returncode_policy>(void)
0x18003ed26  mov     rcx, rdi
0x18003ed29  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ed2e  lea     rcx, [rbx+18h]
0x18003ed32  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UHandlerEntry@DirectLaunchManager@DirectLaunch@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,DirectLaunch::DirectLaunchManager::HandlerEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,DirectLaunch::DirectLaunchManager::HandlerEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,DirectLaunch::DirectLaunchManager::HandlerEntry>>,0>>(void)
0x18003ed37  mov     rcx, [rbx+8]; this
0x18003ed3b  test    rcx, rcx
0x18003ed3e  jz      short loc_18003ED45
0x18003ed40  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003ed45  mov     rbx, [rsp+28h+arg_0]
0x18003ed4a  add     rsp, 20h
0x18003ed4e  pop     rdi
0x18003ed4f  retn
```
