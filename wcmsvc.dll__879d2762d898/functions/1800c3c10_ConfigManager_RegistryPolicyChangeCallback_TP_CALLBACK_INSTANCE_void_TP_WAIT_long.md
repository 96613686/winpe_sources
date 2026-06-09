# ConfigManager::RegistryPolicyChangeCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800c3c10`
- end: `0x1800c3e58`
- name: `?RegistryPolicyChangeCallback@ConfigManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `584`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task`

## callees

- `0x18000dfc0`
- `0x180010080`
- `0x180011c20`
- `0x1800137a0`
- `0x180027630`
- `0x180037c80`
- `0x18003fe94`
- `0x180084f50`
- `0x1800c3c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ded`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c3ded`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c3cd4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c3d8b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c3cd4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c3d8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c3e01`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800c3e01`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c3d0d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c3da7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c3d0d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c3da7`

## string_xrefs

- `0x1800c3c6a`: `ServiceSetting`
- `0x1800c3c58`: `<unknown ConfigManagerPolicyType>`

## pseudocode

```c
void __fastcall ConfigManager::RegistryPolicyChangeCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v4; // edi
  __int64 v5; // rcx
  const char *v6; // r9
  std::_Ref_count_base *v7; // rbx
  unsigned int v8; // eax
  unsigned int v9; // edi
  HANDLE v10; // rdx
  struct _TP_WAIT *v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // edi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+38h] [rbp-40h] BYREF

  v4 = (int)Context;
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    if ( (_DWORD)Context )
    {
      if ( (_DWORD)Context == 1 )
        v6 = "PolicySetting";
      else
        v6 = "<unknown ConfigManagerPolicyType>";
    }
    else
    {
      v6 = "ServiceSetting";
    }
    WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 67, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v6);
  }
  *(_OWORD *)v15 = 0;
  std::weak_ptr<ConfigManager>::lock(v5, v15);
  v7 = v15[0];
  if ( v15[0] )
  {
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        lpCriticalSection = 0;
        wil::EnterCriticalSection(&lpCriticalSection, &s_keyLock);
        ResetEvent(*((HANDLE *)v7 + 1));
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &s_wcmLocalPolicyKey,
          0);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &s_wcmGroupPolicyKey,
          0);
        v8 = RegNotifyChangeKeyValue(s_wcmRootPolicyKey, 1, 0x10000007u, *((HANDLE *)v7 + 1), 1);
        v9 = v8;
        if ( v8
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 69, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v8);
        }
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        if ( !v9 )
        {
          v10 = (HANDLE)*((_QWORD *)v7 + 1);
          v11 = (struct _TP_WAIT *)*((_QWORD *)v7 + 3);
LABEL_31:
          SetThreadpoolWait(v11, v10, 0);
        }
      }
    }
    else
    {
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, &s_keyLock);
      ResetEvent(*(HANDLE *)v7);
      v12 = RegNotifyChangeKeyValue(s_wcmRootKey, 1, 0x10000007u, *(HANDLE *)v7, 1);
      v13 = v12;
      if ( v12
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 68, WPP_d1926522bc273c8e7056db3405527a30_Traceguids, v12);
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      if ( !v13 )
      {
        v10 = *(HANDLE *)v7;
        v11 = (struct _TP_WAIT *)*((_QWORD *)v7 + 2);
        goto LABEL_31;
      }
    }
  }
  NotificationEngine::QueueCdeEventWorkItem((__int64)&GUID_NULL, 0x10005u, 0x100u, 0, 0, 0);
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
}

```

## disassembly

```asm
0x1800c3c10  push    rbx
0x1800c3c12  push    rbp
0x1800c3c13  push    rdi
0x1800c3c14  push    r14
0x1800c3c16  sub     rsp, 58h
0x1800c3c1a  mov     rax, cs:__security_cookie
0x1800c3c21  xor     rax, rsp
0x1800c3c24  mov     [rsp+78h+var_30], rax
0x1800c3c29  mov     rdi, rdx
0x1800c3c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3c33  lea     r14, WPP_GLOBAL_Control
0x1800c3c3a  mov     ebp, 1
0x1800c3c3f  cmp     rcx, r14
0x1800c3c42  jz      short loc_1800C3C86
0x1800c3c44  cmp     byte ptr [rcx+19h], 4
0x1800c3c48  jb      short loc_1800C3C86
0x1800c3c4a  test    [rcx+1Ch], bpl
0x1800c3c4e  jz      short loc_1800C3C86
0x1800c3c50  test    edi, edi
0x1800c3c52  jz      short loc_1800C3C6A
0x1800c3c54  cmp     edi, ebp
0x1800c3c56  jz      short loc_1800C3C61
0x1800c3c58  lea     r9, aUnknownConfigm; "<unknown ConfigManagerPolicyType>"
0x1800c3c5f  jmp     short loc_1800C3C71
0x1800c3c61  lea     r9, aPolicysetting; "PolicySetting"
0x1800c3c68  jmp     short loc_1800C3C71
0x1800c3c6a  lea     r9, aServicesetting; "ServiceSetting"
0x1800c3c71  mov     rcx, [rcx+10h]
0x1800c3c75  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x1800c3c7c  mov     edx, 43h ; 'C'
0x1800c3c81  call    WPP_SF_s
0x1800c3c86  xorps   xmm0, xmm0
0x1800c3c89  lea     rdx, [rsp+78h+var_40]
0x1800c3c8e  movups  xmmword ptr [rsp+78h+var_40], xmm0
0x1800c3c93  call    ?lock@?$weak_ptr@VConfigManager@@@std@@QEBA?AV?$shared_ptr@VConfigManager@@@2@XZ; std::weak_ptr<ConfigManager>::lock(void)
0x1800c3c98  mov     rbx, [rsp+78h+var_40]
0x1800c3c9d  test    rbx, rbx
0x1800c3ca0  jz      loc_1800C3E07
0x1800c3ca6  test    edi, edi
0x1800c3ca8  jz      loc_1800C3D6E
0x1800c3cae  cmp     edi, ebp
0x1800c3cb0  jnz     loc_1800C3E07
0x1800c3cb6  lea     rdx, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x1800c3cbd  mov     [rsp+78h+lpCriticalSection], 0
0x1800c3cc6  lea     rcx, [rsp+78h+lpCriticalSection]
0x1800c3ccb  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c3cd0  mov     rcx, [rbx+8]; hEvent
0x1800c3cd4  call    cs:__imp_ResetEvent
0x1800c3cda  xor     edx, edx
0x1800c3cdc  lea     rcx, ?s_wcmLocalPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmLocalPolicyKey
0x1800c3ce3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c3ce8  xor     edx, edx
0x1800c3cea  lea     rcx, ?s_wcmGroupPolicyKey@@3VKey@Registry@WcmCommon@@A; WcmCommon::Registry::Key s_wcmGroupPolicyKey
0x1800c3cf1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c3cf6  mov     r9, [rbx+8]; hEvent
0x1800c3cfa  mov     r8d, 10000007h; dwNotifyFilter
0x1800c3d00  mov     rcx, cs:?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A; hKey
0x1800c3d07  mov     edx, ebp; bWatchSubtree
0x1800c3d09  mov     [rsp+78h+fAsynchronous], ebp; fAsynchronous
0x1800c3d0d  call    cs:__imp_RegNotifyChangeKeyValue
0x1800c3d13  mov     edi, eax
0x1800c3d15  test    eax, eax
0x1800c3d17  jz      short loc_1800C3D49
0x1800c3d19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3d20  cmp     rcx, r14
0x1800c3d23  jz      short loc_1800C3D49
0x1800c3d25  cmp     [rcx+19h], bpl
0x1800c3d29  jb      short loc_1800C3D49
0x1800c3d2b  test    [rcx+1Ch], bpl
0x1800c3d2f  jz      short loc_1800C3D49
0x1800c3d31  mov     rcx, [rcx+10h]
0x1800c3d35  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x1800c3d3c  mov     edx, 45h ; 'E'
0x1800c3d41  mov     r9d, eax
0x1800c3d44  call    WPP_SF_d
0x1800c3d49  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800c3d4e  test    rcx, rcx
0x1800c3d51  jz      short loc_1800C3D59
0x1800c3d53  call    cs:__imp_LeaveCriticalSection
0x1800c3d59  test    edi, edi
0x1800c3d5b  jnz     loc_1800C3E07
0x1800c3d61  mov     rdx, [rbx+8]
0x1800c3d65  mov     rcx, [rbx+18h]
0x1800c3d69  jmp     loc_1800C3DFE
0x1800c3d6e  lea     rdx, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x1800c3d75  mov     [rsp+78h+lpCriticalSection], 0
0x1800c3d7e  lea     rcx, [rsp+78h+lpCriticalSection]
0x1800c3d83  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c3d88  mov     rcx, [rbx]; hEvent
0x1800c3d8b  call    cs:__imp_ResetEvent
0x1800c3d91  mov     r9, [rbx]; hEvent
0x1800c3d94  mov     r8d, 10000007h; dwNotifyFilter
0x1800c3d9a  mov     rcx, cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A; hKey
0x1800c3da1  mov     edx, ebp; bWatchSubtree
0x1800c3da3  mov     [rsp+78h+fAsynchronous], ebp; fAsynchronous
0x1800c3da7  call    cs:__imp_RegNotifyChangeKeyValue
0x1800c3dad  mov     edi, eax
0x1800c3daf  test    eax, eax
0x1800c3db1  jz      short loc_1800C3DE3
0x1800c3db3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3dba  cmp     rcx, r14
0x1800c3dbd  jz      short loc_1800C3DE3
0x1800c3dbf  cmp     [rcx+19h], bpl
0x1800c3dc3  jb      short loc_1800C3DE3
0x1800c3dc5  test    [rcx+1Ch], bpl
0x1800c3dc9  jz      short loc_1800C3DE3
0x1800c3dcb  mov     rcx, [rcx+10h]
0x1800c3dcf  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x1800c3dd6  mov     edx, 44h ; 'D'
0x1800c3ddb  mov     r9d, eax
0x1800c3dde  call    WPP_SF_d
0x1800c3de3  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800c3de8  test    rcx, rcx
0x1800c3deb  jz      short loc_1800C3DF3
0x1800c3ded  call    cs:__imp_LeaveCriticalSection
0x1800c3df3  test    edi, edi
0x1800c3df5  jnz     short loc_1800C3E07
0x1800c3df7  mov     rdx, [rbx]; h
0x1800c3dfa  mov     rcx, [rbx+10h]; pwa
0x1800c3dfe  xor     r8d, r8d; pftTimeout
0x1800c3e01  call    cs:__imp_SetThreadpoolWait
0x1800c3e07  mov     r8d, 100h
0x1800c3e0d  mov     [rsp+78h+var_50], 0
0x1800c3e15  xor     r9d, r9d
0x1800c3e18  mov     qword ptr [rsp+78h+fAsynchronous], 0
0x1800c3e21  mov     edx, 10005h
0x1800c3e26  lea     rcx, GUID_NULL
0x1800c3e2d  call    ?QueueCdeEventWorkItem@NotificationEngine@@SAXAEBU_GUID@@KGW4_WCM_MEDIA_TYPE@@PEBXK@Z; NotificationEngine::QueueCdeEventWorkItem(_GUID const &,ulong,ushort,_WCM_MEDIA_TYPE,void const *,ulong)
0x1800c3e32  mov     rcx, [rsp+78h+var_40+8]; this
0x1800c3e37  test    rcx, rcx
0x1800c3e3a  jz      short loc_1800C3E41
0x1800c3e3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c3e41  mov     rcx, [rsp+78h+var_30]
0x1800c3e46  xor     rcx, rsp; StackCookie
0x1800c3e49  call    __security_check_cookie
0x1800c3e4e  add     rsp, 58h
0x1800c3e52  pop     r14
0x1800c3e54  pop     rdi
0x1800c3e55  pop     rbp
0x1800c3e56  pop     rbx
0x1800c3e57  retn
```
