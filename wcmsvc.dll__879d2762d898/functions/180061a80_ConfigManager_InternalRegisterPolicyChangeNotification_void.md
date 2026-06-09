# ConfigManager::InternalRegisterPolicyChangeNotification(void)

- ea: `0x180061a80`
- end: `0x180061d96`
- name: `?InternalRegisterPolicyChangeNotification@ConfigManager@@AEAAJXZ`
- size: `790`
- prototype: `__int64 __fastcall(ConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180060784`

## callees

- `0x180019434`
- `0x180027250`
- `0x180027630`
- `0x1800355b4`
- `0x180061a80`
- `0x180061d9c`
- `0x180061ddc`
- `0x1800627e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061c41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061cfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061d16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061b70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061c41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061cfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180061d16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061ad1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061c00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061ad1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061c00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180061d2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180061d3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180061d2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180061d3f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180061b37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180061c67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180061b37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180061c67`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180061b9b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180061ccb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180061b9b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180061ccb`

## string_xrefs

- `0x180061af5`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180061b53`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180061bad`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180061c24`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180061c83`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180061cdd`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`

## pseudocode

```c
__int64 __fastcall ConfigManager::InternalRegisterPolicyChangeNotification(ConfigManager *this)
{
  PTP_WAIT *v2; // r14
  HANDLE EventW; // rax
  const char *v4; // r9
  unsigned int LastError; // edi
  PTP_WAIT ThreadpoolWait; // rax
  const char *v7; // r9
  unsigned int v8; // eax
  PTP_WAIT *v9; // rsi
  HANDLE v10; // rax
  const char *v11; // r9
  PTP_WAIT v12; // rax
  const char *v13; // r9
  unsigned int v14; // eax
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  LPCRITICAL_SECTION lpCriticalSection[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, &s_keyLock);
  if ( s_wcmRootKey )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this,
      EventW);
    if ( ((*(_QWORD *)this + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6AC,
                    (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                    v4);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
      goto LABEL_28;
    }
    v2 = (PTP_WAIT *)((char *)this + 16);
    ThreadpoolWait = CreateThreadpoolWait(ConfigManager::RegistryPolicyChangeCallback, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      (char *)this + 16,
      ThreadpoolWait);
    if ( !*((_QWORD *)this + 2) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6B2,
                    (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                    v7);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
      goto LABEL_28;
    }
    v8 = RegNotifyChangeKeyValue(s_wcmRootKey, 1, 0x10000007u, *(HANDLE *)this, 1);
    if ( v8 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x6B9,
                    (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                    (const char *)v8,
                    fAsynchronous);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
      goto LABEL_28;
    }
  }
  else
  {
    v2 = (PTP_WAIT *)((char *)this + 16);
  }
  if ( s_wcmRootPolicyKey )
  {
    v10 = CreateEventW(0, 1, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 8,
      v10);
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v9 = (PTP_WAIT *)((char *)this + 24);
      v12 = CreateThreadpoolWait(ConfigManager::RegistryPolicyChangeCallback, (PVOID)1, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
        (char *)this + 24,
        v12);
      if ( *((_QWORD *)this + 3) )
      {
        v14 = RegNotifyChangeKeyValue(s_wcmRootPolicyKey, 1, 0x10000007u, *((HANDLE *)this + 1), 1);
        if ( !v14 )
          goto LABEL_29;
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x6D1,
                      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                      (const char *)v14,
                      fAsynchronousa);
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x6CA,
                      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                      v13);
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6C4,
                    (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
                    v11);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
    }
LABEL_28:
    ConfigManager::InternalUnregisterPolicyChangeNotification(this);
    return LastError;
  }
  v9 = (PTP_WAIT *)((char *)this + 24);
LABEL_29:
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  if ( *v2 )
    SetThreadpoolWait(*v2, *(HANDLE *)this, 0);
  if ( *v9 )
    SetThreadpoolWait(*v9, *((HANDLE *)this + 1), 0);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 66, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180061a80  mov     rax, rsp
0x180061a83  mov     [rax+10h], rbx
0x180061a87  mov     [rax+18h], rsi
0x180061a8b  push    rdi
0x180061a8c  push    r14
0x180061a8e  push    r15
0x180061a90  sub     rsp, 40h
0x180061a94  mov     rbx, rcx
0x180061a97  mov     qword ptr [rax-28h], 0
0x180061a9f  lea     rdx, ?s_keyLock@@3Vcritical_section@wil@@A; wil::critical_section s_keyLock
0x180061aa6  lea     rcx, [rax-28h]
0x180061aaa  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180061aaf  mov     edi, 1
0x180061ab4  cmp     cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootKey
0x180061abc  jnz     short loc_180061AC7
0x180061abe  lea     r14, [rbx+10h]
0x180061ac2  jmp     loc_180061BDF
0x180061ac7  xor     r9d, r9d; lpName
0x180061aca  xor     r8d, r8d; bInitialState
0x180061acd  mov     edx, edi; bManualReset
0x180061acf  xor     ecx, ecx; lpEventAttributes
0x180061ad1  call    cs:__imp_CreateEventW
0x180061ad7  mov     rdx, rax
0x180061ada  mov     rcx, rbx
0x180061add  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180061ae2  mov     rax, [rbx]
0x180061ae5  add     rax, rdi
0x180061ae8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180061aee  jnz     short loc_180061B27
0x180061af0  mov     rcx, [rsp+58h]; this
0x180061af5  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061afc  mov     edx, 6ACh; void *
0x180061b01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061b06  mov     edi, eax
0x180061b08  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061b0d  test    rcx, rcx
0x180061b10  jz      short loc_180061B18
0x180061b12  call    cs:__imp_LeaveCriticalSection
0x180061b18  mov     rcx, rbx; this
0x180061b1b  call    ?InternalUnregisterPolicyChangeNotification@ConfigManager@@AEAAXXZ; ConfigManager::InternalUnregisterPolicyChangeNotification(void)
0x180061b20  mov     eax, edi
0x180061b22  jmp     loc_180061D81
0x180061b27  lea     r14, [rbx+10h]
0x180061b2b  xor     r8d, r8d; pcbe
0x180061b2e  xor     edx, edx; pv
0x180061b30  lea     rcx, ?RegistryPolicyChangeCallback@ConfigManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180061b37  call    cs:__imp_CreateThreadpoolWait
0x180061b3d  mov     rdx, rax
0x180061b40  mov     rcx, r14
0x180061b43  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180061b48  cmp     qword ptr [r14], 0
0x180061b4c  jnz     short loc_180061B85
0x180061b4e  mov     rcx, [rsp+58h]; this
0x180061b53  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061b5a  mov     edx, 6B2h; void *
0x180061b5f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061b64  mov     edi, eax
0x180061b66  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061b6b  test    rcx, rcx
0x180061b6e  jz      short loc_180061B76
0x180061b70  call    cs:__imp_LeaveCriticalSection
0x180061b76  mov     rcx, rbx; this
0x180061b79  call    ?InternalUnregisterPolicyChangeNotification@ConfigManager@@AEAAXXZ; ConfigManager::InternalUnregisterPolicyChangeNotification(void)
0x180061b7e  mov     eax, edi
0x180061b80  jmp     loc_180061D81
0x180061b85  mov     [rsp+58h+fAsynchronous], edi; unsigned int
0x180061b89  mov     r9, [rbx]; hEvent
0x180061b8c  mov     r8d, 10000007h; dwNotifyFilter
0x180061b92  mov     edx, edi; bWatchSubtree
0x180061b94  mov     rcx, cs:?s_wcmRootKey@@3VKey@Registry@WcmCommon@@A; hKey
0x180061b9b  call    cs:__imp_RegNotifyChangeKeyValue
0x180061ba1  test    eax, eax
0x180061ba3  jz      short loc_180061BDF
0x180061ba5  mov     rcx, [rsp+58h]; this
0x180061baa  mov     r9d, eax; char *
0x180061bad  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061bb4  mov     edx, 6B9h; void *
0x180061bb9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061bbe  mov     edi, eax
0x180061bc0  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061bc5  test    rcx, rcx
0x180061bc8  jz      short loc_180061BD0
0x180061bca  call    cs:__imp_LeaveCriticalSection
0x180061bd0  mov     rcx, rbx; this
0x180061bd3  call    ?InternalUnregisterPolicyChangeNotification@ConfigManager@@AEAAXXZ; ConfigManager::InternalUnregisterPolicyChangeNotification(void)
0x180061bd8  mov     eax, edi
0x180061bda  jmp     loc_180061D81
0x180061bdf  cmp     cs:?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A, 0; WcmCommon::Registry::Key s_wcmRootPolicyKey
0x180061be7  jnz     short loc_180061BF2
0x180061be9  lea     rsi, [rbx+18h]
0x180061bed  jmp     loc_180061D0C
0x180061bf2  lea     r15, [rbx+8]
0x180061bf6  xor     r9d, r9d; lpName
0x180061bf9  xor     r8d, r8d; bInitialState
0x180061bfc  mov     edx, edi; bManualReset
0x180061bfe  xor     ecx, ecx; lpEventAttributes
0x180061c00  call    cs:__imp_CreateEventW
0x180061c06  mov     rdx, rax
0x180061c09  mov     rcx, r15
0x180061c0c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180061c11  mov     rax, [r15]
0x180061c14  add     rax, rdi
0x180061c17  test    rax, 0FFFFFFFFFFFFFFFEh
0x180061c1d  jnz     short loc_180061C56
0x180061c1f  mov     rcx, [rsp+58h]; this
0x180061c24  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061c2b  mov     edx, 6C4h; void *
0x180061c30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061c35  mov     edi, eax
0x180061c37  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061c3c  test    rcx, rcx
0x180061c3f  jz      short loc_180061C47
0x180061c41  call    cs:__imp_LeaveCriticalSection
0x180061c47  mov     rcx, rbx; this
0x180061c4a  call    ?InternalUnregisterPolicyChangeNotification@ConfigManager@@AEAAXXZ; ConfigManager::InternalUnregisterPolicyChangeNotification(void)
0x180061c4f  mov     eax, edi
0x180061c51  jmp     loc_180061D81
0x180061c56  lea     rsi, [rbx+18h]
0x180061c5a  xor     r8d, r8d; pcbe
0x180061c5d  mov     rdx, rdi; pv
0x180061c60  lea     rcx, ?RegistryPolicyChangeCallback@ConfigManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180061c67  call    cs:__imp_CreateThreadpoolWait
0x180061c6d  mov     rdx, rax
0x180061c70  mov     rcx, rsi
0x180061c73  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180061c78  cmp     qword ptr [rsi], 0
0x180061c7c  jnz     short loc_180061CB5
0x180061c7e  mov     rcx, [rsp+58h]; this
0x180061c83  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061c8a  mov     edx, 6CAh; void *
0x180061c8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180061c94  mov     edi, eax
0x180061c96  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061c9b  test    rcx, rcx
0x180061c9e  jz      short loc_180061CA6
0x180061ca0  call    cs:__imp_LeaveCriticalSection
0x180061ca6  mov     rcx, rbx; this
0x180061ca9  call    ?InternalUnregisterPolicyChangeNotification@ConfigManager@@AEAAXXZ; ConfigManager::InternalUnregisterPolicyChangeNotification(void)
0x180061cae  mov     eax, edi
0x180061cb0  jmp     loc_180061D81
0x180061cb5  mov     [rsp+58h+fAsynchronous], edi; unsigned int
0x180061cb9  mov     r9, [r15]; hEvent
0x180061cbc  mov     r8d, 10000007h; dwNotifyFilter
0x180061cc2  mov     edx, edi; bWatchSubtree
0x180061cc4  mov     rcx, cs:?s_wcmRootPolicyKey@@3VKey@Registry@WcmCommon@@A; hKey
0x180061ccb  call    cs:__imp_RegNotifyChangeKeyValue
0x180061cd1  test    eax, eax
0x180061cd3  jz      short loc_180061D0C
0x180061cd5  mov     rcx, [rsp+58h]; this
0x180061cda  mov     r9d, eax; char *
0x180061cdd  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180061ce4  mov     edx, 6D1h; void *
0x180061ce9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061cee  mov     edi, eax
0x180061cf0  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061cf5  test    rcx, rcx
0x180061cf8  jz      short loc_180061D00
0x180061cfa  call    cs:__imp_LeaveCriticalSection
0x180061d00  mov     rcx, rbx; this
0x180061d03  call    ?InternalUnregisterPolicyChangeNotification@ConfigManager@@AEAAXXZ; ConfigManager::InternalUnregisterPolicyChangeNotification(void)
0x180061d08  mov     eax, edi
0x180061d0a  jmp     short loc_180061D81
0x180061d0c  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x180061d11  test    rcx, rcx
0x180061d14  jz      short loc_180061D1C
0x180061d16  call    cs:__imp_LeaveCriticalSection
0x180061d1c  mov     rcx, [r14]; pwa
0x180061d1f  test    rcx, rcx
0x180061d22  jz      short loc_180061D30
0x180061d24  xor     r8d, r8d; pftTimeout
0x180061d27  mov     rdx, [rbx]; h
0x180061d2a  call    cs:__imp_SetThreadpoolWait
0x180061d30  mov     rcx, [rsi]; pwa
0x180061d33  test    rcx, rcx
0x180061d36  jz      short loc_180061D45
0x180061d38  xor     r8d, r8d; pftTimeout
0x180061d3b  mov     rdx, [rbx+8]; h
0x180061d3f  call    cs:__imp_SetThreadpoolWait
0x180061d45  lea     rax, WPP_GLOBAL_Control
0x180061d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d53  cmp     rcx, rax
0x180061d56  jz      short loc_180061D79
0x180061d58  cmp     byte ptr [rcx+19h], 4
0x180061d5c  jb      short loc_180061D79
0x180061d5e  test    [rcx+1Ch], dil
0x180061d62  jz      short loc_180061D79
0x180061d64  mov     edx, 42h ; 'B'
0x180061d69  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x180061d70  mov     rcx, [rcx+10h]
0x180061d74  call    WPP_SF_
0x180061d79  xor     eax, eax
0x180061d7b  jmp     short loc_180061D81
0x180061d7d  mov     eax, dword ptr [rsp+58h+lpCriticalSection]
0x180061d81  mov     rbx, [rsp+58h+arg_8]
0x180061d86  mov     rsi, [rsp+58h+arg_10]
0x180061d8b  add     rsp, 40h
0x180061d8f  pop     r15
0x180061d91  pop     r14
0x180061d93  pop     rdi
0x180061d94  retn
```
