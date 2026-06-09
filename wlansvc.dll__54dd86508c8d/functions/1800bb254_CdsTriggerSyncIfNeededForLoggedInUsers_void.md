# CdsTriggerSyncIfNeededForLoggedInUsers(void)

- ea: `0x1800bb254`
- end: `0x1800bb528`
- name: `?CdsTriggerSyncIfNeededForLoggedInUsers@@YAJXZ`
- size: `724`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003702c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18001c9ec`
- `0x1800a539c`
- `0x1800a9e18`
- `0x1800bb254`
- `0x1800bb53c`
- `0x1800bb560`
- `0x1800bb598`
- `0x1800bb5b8`
- `0x1800bb69c`
- `0x1800bb9fc`
- `0x1800bba54`
- `0x180108368`
- `0x180206db4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb43e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb3d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb43e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800bb3ca`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800bb3ca`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800bb364`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800bb364`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800bb312`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800bb312`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800bb2a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CdsTriggerSyncIfNeededForLoggedInUsers(void)
{
  bool *v0; // rdx
  int IsWiFiCloudStoreFeaturePresent; // eax
  unsigned int v2; // ebx
  wil::details::in1diag3 *v3; // rcx
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  unsigned int i; // esi
  int v7; // eax
  signed int LastError; // eax
  __int64 v9; // rdx
  int v10; // eax
  bool *v11; // r8
  int IsSyncNeededForUser; // eax
  __int64 v14; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+28h] [rbp-30h] BYREF
  __int64 v16; // [rsp+30h] [rbp-28h]
  __int64 *v17; // [rsp+38h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-18h] BYREF
  char v19; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  char v21; // [rsp+80h] [rbp+28h] BYREF
  unsigned int v22; // [rsp+88h] [rbp+30h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+90h] [rbp+38h] BYREF
  void *DuplicateTokenHandle; // [rsp+98h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_15b2cdc2ff7235693c8ecde4fa5e3f2a_Traceguids);
  }
  if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v2 = -2147467263;
    goto LABEL_35;
  }
  v15 = UMgrFreeSessionUsers;
  v16 = 0;
  v21 = 0;
  IsWiFiCloudStoreFeaturePresent = Windows::Internal::WiFiCloudStore::IsWiFiCloudStoreFeaturePresent(
                                     (Windows::Internal::WiFiCloudStore *)&v21,
                                     v0);
  v2 = IsWiFiCloudStoreFeaturePresent;
  v3 = retaddr;
  if ( IsWiFiCloudStoreFeaturePresent >= 0 )
  {
    if ( !v21 )
      goto LABEL_31;
    v22 = 0;
    v17 = &v15;
    v18 = 0;
    v19 = 1;
    v2 = UMgrEnumerateSessionUsers(&v22, &v18);
    wil::details::out_param_t<std::unique_ptr<_SESSION_USER_CONTEXT,void (*)(_SESSION_USER_CONTEXT *)>>::~out_param_t<std::unique_ptr<_SESSION_USER_CONTEXT,void (*)(_SESSION_USER_CONTEXT *)>>(&v17);
    v3 = retaddr;
    if ( (v2 & 0x80000000) != 0 )
    {
      v4 = v2;
      v5 = 509;
      goto LABEL_8;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v22 )
        goto LABEL_31;
      ExistingTokenHandle = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &ExistingTokenHandle,
        0);
      v7 = UMgrQueryUserToken(*(_QWORD *)(v16 + 16LL * i), &ExistingTokenHandle);
      v2 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x206,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\cds.cpp",
          (const char *)(unsigned int)v7,
          v14);
        goto LABEL_33;
      }
      v21 = 0;
      if ( (char *)ExistingTokenHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x229,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\cds.cpp",
          (const char *)0x800703F0LL,
          v14);
      }
      else
      {
        v14 = -1;
        DuplicateTokenHandle = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &DuplicateTokenHandle,
          0);
        if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v9 = 533;
LABEL_21:
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)v9,
            (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\cds.cpp",
            (const char *)(unsigned int)LastError,
            v14);
LABEL_22:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v14);
          goto LABEL_33;
        }
        v10 = wil::impersonate_token_nothrow(DuplicateTokenHandle, (void **)&v14);
        if ( v10 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x219,
            (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\cds.cpp",
            (const char *)(unsigned int)v10,
            v14);
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v9 = 547;
          goto LABEL_21;
        }
        IsSyncNeededForUser = Windows::Internal::WiFiCloudStore::IsSyncNeededForUser(
                                (Windows::Internal::WiFiCloudStore *)ExistingTokenHandle,
                                &v21,
                                v11);
        v2 = IsSyncNeededForUser;
        if ( IsSyncNeededForUser < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x21C,
            (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\cds.cpp",
            (const char *)(unsigned int)IsSyncNeededForUser,
            v14);
          goto LABEL_22;
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v14);
        if ( v21 )
        {
          v2 = Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay();
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
          goto LABEL_31;
        }
      }
LABEL_33:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
    }
  }
  v4 = (unsigned int)IsWiFiCloudStoreFeaturePresent;
  v5 = 502;
LABEL_8:
  wil::details::in1diag3::_Log_Hr(
    v3,
    (void *)v5,
    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\cds.cpp",
    (const char *)v4,
    v14);
LABEL_31:
  std::unique_ptr<void,int (*)(void *)>::~unique_ptr<void,int (*)(void *)>(&v15);
LABEL_35:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_15b2cdc2ff7235693c8ecde4fa5e3f2a_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1800bb254  push    rbp
0x1800bb256  push    rbx
0x1800bb257  push    rsi
0x1800bb258  push    r12
0x1800bb25a  mov     rbp, rsp
0x1800bb25d  sub     rsp, 58h
0x1800bb261  lea     r12, WPP_GLOBAL_Control
0x1800bb268  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb26f  cmp     rcx, r12
0x1800bb272  jz      short loc_1800BB295
0x1800bb274  cmp     byte ptr [rcx+69h], 4
0x1800bb278  jb      short loc_1800BB295
0x1800bb27a  test    byte ptr [rcx+6Ch], 1
0x1800bb27e  jz      short loc_1800BB295
0x1800bb280  mov     edx, 1Bh
0x1800bb285  lea     r8, WPP_15b2cdc2ff7235693c8ecde4fa5e3f2a_Traceguids
0x1800bb28c  mov     rcx, [rcx+60h]
0x1800bb290  call    WPP_SF_
0x1800bb295  call    IsUMgrEnumerateSessionUsersPresent
0x1800bb29a  test    al, al
0x1800bb29c  jz      loc_1800BB4E7
0x1800bb2a2  mov     rax, cs:__imp_UMgrFreeSessionUsers
0x1800bb2a9  mov     [rbp+var_30], rax
0x1800bb2ad  mov     [rbp+var_28], 0
0x1800bb2b5  mov     [rbp+arg_0], 0
0x1800bb2b9  lea     rcx, [rbp+arg_0]; this
0x1800bb2bd  call    ?IsWiFiCloudStoreFeaturePresent@WiFiCloudStore@Internal@Windows@@YAJPEA_N@Z; Windows::Internal::WiFiCloudStore::IsWiFiCloudStoreFeaturePresent(bool *)
0x1800bb2c2  mov     ebx, eax
0x1800bb2c4  mov     rcx, [rbp+20h]; this
0x1800bb2c8  test    eax, eax
0x1800bb2ca  jns     short loc_1800BB2E5
0x1800bb2cc  mov     r9d, eax; char *
0x1800bb2cf  mov     edx, 1F6h; void *
0x1800bb2d4  lea     r8, aOnecoreuapNetW_60; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800bb2db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb2e0  jmp     loc_1800BB4B0
0x1800bb2e5  cmp     [rbp+arg_0], 0
0x1800bb2e9  jz      loc_1800BB4B0
0x1800bb2ef  mov     [rbp+arg_8], 0
0x1800bb2f6  lea     rax, [rbp+var_30]
0x1800bb2fa  mov     [rbp+var_20], rax
0x1800bb2fe  mov     [rbp+var_18], 0
0x1800bb306  mov     [rbp+var_10], 1
0x1800bb30a  lea     rdx, [rbp+var_18]
0x1800bb30e  lea     rcx, [rbp+arg_8]
0x1800bb312  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800bb318  mov     ebx, eax
0x1800bb31a  lea     rcx, [rbp+var_20]
0x1800bb31e  call    ??1?$out_param_t@V?$unique_ptr@U_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<_SESSION_USER_CONTEXT,void (*)(_SESSION_USER_CONTEXT *)>>::~out_param_t<std::unique_ptr<_SESSION_USER_CONTEXT,void (*)(_SESSION_USER_CONTEXT *)>>(void)
0x1800bb323  mov     rcx, [rbp+20h]
0x1800bb327  test    ebx, ebx
0x1800bb329  jns     short loc_1800BB335
0x1800bb32b  mov     r9d, ebx
0x1800bb32e  mov     edx, 1FDh
0x1800bb333  jmp     short loc_1800BB2D4
0x1800bb335  xor     esi, esi
0x1800bb337  cmp     esi, [rbp+arg_8]
0x1800bb33a  jnb     loc_1800BB4B0
0x1800bb340  mov     [rbp+ExistingTokenHandle], 0
0x1800bb348  xor     edx, edx
0x1800bb34a  lea     rcx, [rbp+ExistingTokenHandle]
0x1800bb34e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800bb353  mov     eax, esi
0x1800bb355  add     rax, rax
0x1800bb358  lea     rdx, [rbp+ExistingTokenHandle]
0x1800bb35c  mov     rcx, [rbp+var_28]
0x1800bb360  mov     rcx, [rcx+rax*8]
0x1800bb364  call    cs:__imp_UMgrQueryUserToken
0x1800bb36a  mov     ebx, eax
0x1800bb36c  mov     rcx, [rbp+20h]; this
0x1800bb370  test    eax, eax
0x1800bb372  jns     short loc_1800BB38D
0x1800bb374  mov     r9d, eax; char *
0x1800bb377  lea     r8, aOnecoreuapNetW_60; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800bb37e  mov     edx, 206h; void *
0x1800bb383  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb388  jmp     loc_1800BB4D7
0x1800bb38d  mov     [rbp+arg_0], 0
0x1800bb391  mov     rax, [rbp+ExistingTokenHandle]
0x1800bb395  dec     rax
0x1800bb398  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800bb39c  ja      loc_1800BB4BB
0x1800bb3a2  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFFh
0x1800bb3aa  mov     [rbp+DuplicateTokenHandle], 0
0x1800bb3b2  xor     edx, edx
0x1800bb3b4  lea     rcx, [rbp+DuplicateTokenHandle]
0x1800bb3b8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800bb3bd  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800bb3c1  mov     edx, 2; ImpersonationLevel
0x1800bb3c6  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x1800bb3ca  call    cs:__imp_DuplicateToken
0x1800bb3d0  test    eax, eax
0x1800bb3d2  jnz     short loc_1800BB415
0x1800bb3d4  call    cs:__imp_GetLastError
0x1800bb3da  test    eax, eax
0x1800bb3dc  jle     short loc_1800BB3E6
0x1800bb3de  movzx   eax, ax
0x1800bb3e1  or      eax, 80070000h
0x1800bb3e6  mov     edx, 215h; void *
0x1800bb3eb  lea     r8, aOnecoreuapNetW_60; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800bb3f2  mov     r9d, eax; char *
0x1800bb3f5  mov     rcx, [rbp+20h]; this
0x1800bb3f9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800bb3fe  lea     rcx, [rbp+DuplicateTokenHandle]
0x1800bb402  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800bb407  lea     rcx, [rbp+var_38]
0x1800bb40b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800bb410  jmp     loc_1800BB4D7
0x1800bb415  lea     rdx, [rbp+var_38]
0x1800bb419  mov     rcx, [rbp+DuplicateTokenHandle]; Token
0x1800bb41d  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800bb422  mov     rcx, [rbp+20h]; this
0x1800bb426  test    eax, eax
0x1800bb428  jns     short loc_1800BB457
0x1800bb42a  mov     r9d, eax; char *
0x1800bb42d  lea     r8, aOnecoreuapNetW_60; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800bb434  mov     edx, 219h; void *
0x1800bb439  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb43e  call    cs:__imp_GetLastError
0x1800bb444  test    eax, eax
0x1800bb446  jle     short loc_1800BB450
0x1800bb448  movzx   eax, ax
0x1800bb44b  or      eax, 80070000h
0x1800bb450  mov     edx, 223h
0x1800bb455  jmp     short loc_1800BB3EB
0x1800bb457  lea     rdx, [rbp+arg_0]; void *
0x1800bb45b  mov     rcx, [rbp+ExistingTokenHandle]; this
0x1800bb45f  call    ?IsSyncNeededForUser@WiFiCloudStore@Internal@Windows@@YAJQEAXPEA_N@Z; Windows::Internal::WiFiCloudStore::IsSyncNeededForUser(void * const,bool *)
0x1800bb464  mov     ebx, eax
0x1800bb466  mov     rcx, [rbp+20h]; this
0x1800bb46a  test    eax, eax
0x1800bb46c  jns     short loc_1800BB487
0x1800bb46e  mov     r9d, eax; char *
0x1800bb471  lea     r8, aOnecoreuapNetW_60; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800bb478  mov     edx, 21Ch; void *
0x1800bb47d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb482  jmp     loc_1800BB3FE
0x1800bb487  lea     rcx, [rbp+DuplicateTokenHandle]
0x1800bb48b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800bb490  lea     rcx, [rbp+var_38]
0x1800bb494  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800bb499  cmp     [rbp+arg_0], 0
0x1800bb49d  jz      short loc_1800BB4D7
0x1800bb49f  call    ?TriggerTaskWithDelay@WiFiCloudStore@Internal@Windows@@YAJW4TaskTrigger@123@@Z; Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay(Windows::Internal::WiFiCloudStore::TaskTrigger)
0x1800bb4a4  mov     ebx, eax
0x1800bb4a6  lea     rcx, [rbp+ExistingTokenHandle]
0x1800bb4aa  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800bb4af  nop
0x1800bb4b0  lea     rcx, [rbp+var_30]
0x1800bb4b4  call    ??1?$unique_ptr@XP6AHPEAX@Z@std@@QEAA@XZ; std::unique_ptr<void,int (*)(void *)>::~unique_ptr<void,int (*)(void *)>(void)
0x1800bb4b9  jmp     short loc_1800BB4EC
0x1800bb4bb  mov     rcx, [rbp+20h]; this
0x1800bb4bf  mov     r9d, 800703F0h; char *
0x1800bb4c5  lea     r8, aOnecoreuapNetW_60; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800bb4cc  mov     edx, 229h; void *
0x1800bb4d1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800bb4d6  nop
0x1800bb4d7  lea     rcx, [rbp+ExistingTokenHandle]
0x1800bb4db  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800bb4e0  inc     esi
0x1800bb4e2  jmp     loc_1800BB337
0x1800bb4e7  mov     ebx, 80004001h
0x1800bb4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb4f3  cmp     rcx, r12
0x1800bb4f6  jz      short loc_1800BB51C
0x1800bb4f8  cmp     byte ptr [rcx+69h], 4
0x1800bb4fc  jb      short loc_1800BB51C
0x1800bb4fe  test    byte ptr [rcx+6Ch], 1
0x1800bb502  jz      short loc_1800BB51C
0x1800bb504  mov     edx, 1Ch
0x1800bb509  mov     r9d, ebx
0x1800bb50c  lea     r8, WPP_15b2cdc2ff7235693c8ecde4fa5e3f2a_Traceguids
0x1800bb513  mov     rcx, [rcx+60h]
0x1800bb517  call    WPP_SF_d
0x1800bb51c  mov     eax, ebx
0x1800bb51e  add     rsp, 58h
0x1800bb522  pop     r12
0x1800bb524  pop     rsi
0x1800bb525  pop     rbx
0x1800bb526  pop     rbp
0x1800bb527  retn
```
