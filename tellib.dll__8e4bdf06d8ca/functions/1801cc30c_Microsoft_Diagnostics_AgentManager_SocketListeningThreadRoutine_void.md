# Microsoft::Diagnostics::AgentManager::SocketListeningThreadRoutine(void)

- ea: `0x1801cc30c`
- end: `0x1801cca0d`
- name: `?SocketListeningThreadRoutine@AgentManager@Diagnostics@Microsoft@@AEAAJXZ`
- size: `1793`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::AgentManager *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801ccdd0`

## callees

- `0x180001bf4`
- `0x180001e90`
- `0x1800023fc`
- `0x18001cf30`
- `0x180020fbc`
- `0x180026ecc`
- `0x1800326cc`
- `0x18003fd8c`
- `0x18005479c`
- `0x180054ca4`
- `0x1800571c8`
- `0x18005a554`
- `0x18005d050`
- `0x180071110`
- `0x18007fae8`
- `0x18008bd1c`
- `0x1800a0d08`
- `0x1800ad148`
- `0x1800d0d9c`
- `0x180105d34`
- `0x18012de40`
- `0x18012eb08`
- `0x180177b0c`
- `0x1801a7eb4`
- `0x1801c9cf0`
- `0x1801c9d28`
- `0x1801cc30c`
- `0x1801cca14`
- `0x1801ccb84`
- `0x1801ccea4`
- `0x1801cd7ec`
- `0x1801ec4fc`
- `0x1801ef004`
- `0x1802bf3b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1801cc693`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1801cc89e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1801cc693`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1801cc89e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801cc4a4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801cc4a4`
- `WS2_32!__imp_WSAStartup` at `0x1801cc3ce`
- `WS2_32!__imp_WSAStartup` at `0x1801cc3ce`

## string_xrefs

- `0x1801cc3e9`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc421`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc461`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc5a5`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc667`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc83e`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc9a2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc9e7`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801cc9f7`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AgentManager::SocketListeningThreadRoutine(
        __int64 ****this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  Microsoft::Diagnostics::ScenarioManager *v5; // rcx
  unsigned int InitialSettingsReadyMaxWait; // edi
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  const char *v8; // r9
  unsigned int v9; // eax
  int started; // eax
  unsigned int v12; // ebx
  int v13; // eax
  DWORD v14; // eax
  const char *v15; // r9
  __int64 ***v16; // rdi
  __int64 **j; // rbx
  __int64 v18; // rbx
  int v19; // eax
  Microsoft::Diagnostics::HeartBeat *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // eax
  __int64 *v25; // rbx
  __int64 *v26; // rdi
  __int64 v27; // r15
  __int64 *v28; // r12
  std::_Ref_count_base *v29; // r12
  unsigned int v30; // edi
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  PTP_IO *v34; // rbx
  int v35; // eax
  __int64 *v36; // r8
  __int64 *v37; // rax
  __int64 *v38; // rcx
  __int64 *i; // rdx
  Microsoft::Diagnostics::HeartBeat *HeartbeatManager; // rax
  unsigned int v41; // [rsp+20h] [rbp-2B8h]
  int v42[2]; // [rsp+30h] [rbp-2A8h] BYREF
  __int64 *v43; // [rsp+38h] [rbp-2A0h] BYREF
  __int128 v44; // [rsp+40h] [rbp-298h] BYREF
  std::_Ref_count_base *v45[2]; // [rsp+50h] [rbp-288h] BYREF
  __int128 v46; // [rsp+60h] [rbp-278h] BYREF
  __int64 ***v47; // [rsp+70h] [rbp-268h]
  __int128 v48; // [rsp+80h] [rbp-258h] BYREF
  __int128 v49; // [rsp+90h] [rbp-248h] BYREF
  HANDLE Handles[2]; // [rsp+A0h] [rbp-238h] BYREF
  _BYTE v51[16]; // [rsp+B0h] [rbp-228h] BYREF
  __int128 v52; // [rsp+C0h] [rbp-218h] BYREF
  _BYTE v53[16]; // [rsp+D0h] [rbp-208h] BYREF
  _BYTE v54[16]; // [rsp+E0h] [rbp-1F8h] BYREF
  _BYTE v55[16]; // [rsp+F0h] [rbp-1E8h] BYREF
  struct WSAData WSAData; // [rsp+100h] [rbp-1D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( (unsigned __int16)(qword_18043C08A - 3) > 1u )
  {
    if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF10, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        a4);
    Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    InitialSettingsReadyMaxWait = Microsoft::Diagnostics::ScenarioManager::GetInitialSettingsReadyMaxWait(v5);
    ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(*((void **)ScenarioManager + 4), InitialSettingsReadyMaxWait) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        v8);
  }
  memset_0(&WSAData, 0, sizeof(WSAData));
  v9 = WSAStartup(0x202u, &WSAData);
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x82,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
             (const char *)v9,
             v41);
  wil::details::unique_storage<wil::details::resource_policy<bool,void (bool),&void wilp::CleanupWinsock(bool),wistd::integral_constant<unsigned __int64,0>,bool,bool,0,std::nullptr_t>>::reset(this + 15);
  started = Microsoft::Diagnostics::AgentManager::StartAcceptingWindowsConnections((Microsoft::Diagnostics::AgentManager *)this);
  v12 = started;
  if ( started >= 0 )
  {
    if ( (unsigned __int16)(qword_18043C08A - 3) > 1u )
    {
      v13 = Microsoft::Diagnostics::AgentManager::StartAcceptingLinuxConnections((Microsoft::Diagnostics::AgentManager *)this);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v13,
          v41);
    }
    Handles[0] = this[13];
    Handles[1] = this[14];
    while ( 1 )
    {
      v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v14 )
        break;
      if ( v14 != 1 )
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x102,
                 (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
                 v15);
      v46 = 0;
      v47 = 0;
      std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v51, this + 28);
      v25 = (__int64 *)(this + 38);
      v26 = (__int64 *)(this + 39);
      if ( &v46 == (__int128 *)(this + 38) )
      {
        v28 = 0;
        v27 = 0;
      }
      else
      {
        std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(&v46);
        v27 = *v25;
        *(_QWORD *)&v46 = *v25;
        v28 = (__int64 *)*v26;
        *((_QWORD *)&v46 + 1) = *v26;
        v47 = this[40];
        *v25 = 0;
        *v26 = 0;
        this[40] = 0;
      }
      v43 = v28;
      if ( *v25 != *v26 )
        *v26 = *v25;
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v51);
      while ( (__int64 *)v27 != v28 )
      {
        v29 = *(std::_Ref_count_base **)v27;
        *(_QWORD *)&v44 = *(_QWORD *)v27;
        v30 = *(_DWORD *)(v27 + 8);
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 32784) )
        {
          v42[0] = v30;
          v45[0] = v29;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            v31,
            (unsigned int)&unk_1803C7C9C,
            v32,
            v33,
            (__int64)v45,
            (__int64)v42);
        }
        *(_OWORD *)v45 = 0;
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v53, this + 16);
        std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::find(
          this + 26,
          &v48,
          &v44);
        if ( (__int64 ***)v48 == this[26] )
        {
          v34 = (PTP_IO *)v45[0];
        }
        else
        {
          std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(v45, v48 + 40);
          v34 = (PTP_IO *)v45[0];
          std::wstring::operator std::wstring_view((char *)v45[0] + 264, &v52);
          v44 = v52;
          Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(&v44, v30);
          v35 = Microsoft::Diagnostics::AgentTransport::Disconnect(
                  (Microsoft::Diagnostics::AgentTransport *)v34,
                  1,
                  v30,
                  1);
          if ( v35 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xEB,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
              (const char *)(unsigned int)v35,
              v41);
        }
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v53);
        if ( v34 )
        {
          v44 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v34, v55);
          Microsoft::Diagnostics::AgentWatsonCrashManager::ClearWatsonCrashRequestForAgent(this + 101, &v44);
          WaitForThreadpoolIoCallbacks(v34[32], 1);
        }
        if ( v45[1] )
          std::_Ref_count_base::_Decref(v45[1]);
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v54, this + 16);
        v36 = (__int64 *)this[26];
        v37 = (__int64 *)v36[1];
        v38 = v37;
        for ( i = v36; !*((_BYTE *)v38 + 25); v38 = (__int64 *)*v38 )
        {
          if ( v38[4] >= (unsigned __int64)v29 )
          {
            if ( *((_BYTE *)i + 25) && (unsigned __int64)v29 < v38[4] )
              i = v38;
            v36 = v38;
          }
          else
          {
            v38 += 2;
          }
        }
        if ( !*((_BYTE *)i + 25) )
          v37 = (__int64 *)*i;
        while ( !*((_BYTE *)v37 + 25) )
        {
          if ( (unsigned __int64)v29 >= v37[4] )
          {
            v37 = (__int64 *)v37[2];
          }
          else
          {
            i = v37;
            v37 = (__int64 *)*v37;
          }
        }
        *(_QWORD *)&v49 = v36;
        *((_QWORD *)&v49 + 1) = i;
        std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<Microsoft::Diagnostics::AgentTransport>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Diagnostics::AgentTransport>>>,0>>::_Erase(
          this + 26,
          &v49);
        HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        Microsoft::Diagnostics::HeartBeat::DecreaseActiveAgentConnectionCount(HeartbeatManager);
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v54);
        v27 += 16;
        v28 = v43;
      }
      std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(&v46);
    }
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 32784) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C7D09);
    v16 = this[42];
    for ( j = *v16; j != (__int64 **)v16; j = (__int64 **)*j )
    {
      if ( j[4] )
      {
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 32784) )
        {
          v43 = j[3];
          *(_QWORD *)v42 = j[4];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v21,
            (unsigned int)&unk_1803C7D32,
            v22,
            v23,
            (__int64)v42,
            (__int64)&v43);
        }
        v24 = Microsoft::Diagnostics::AgentTransport::Disconnect(
                (Microsoft::Diagnostics::AgentTransport *)j[4],
                0,
                0,
                0);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)(unsigned int)v24,
            v41);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(
          j + 3,
          -1);
        WaitForThreadpoolIoCallbacks((PTP_IO)j[4][32], 1);
      }
    }
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 32784) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C7CDC);
    std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v44, this + 16);
    v18 = (__int64)*this[26];
    *(_QWORD *)v42 = v18;
    while ( !*(_BYTE *)(v18 + 25) )
    {
      std::wstring::operator std::wstring_view(*(_QWORD *)(v18 + 40) + 264LL, &v49);
      v48 = v49;
      Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(&v48, 0);
      v19 = Microsoft::Diagnostics::AgentTransport::Disconnect(
              *(Microsoft::Diagnostics::AgentTransport **)(v18 + 40),
              1,
              0,
              1);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBE,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v19,
          v41);
      v20 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::DecreaseActiveAgentConnectionCount(v20);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(v42);
      v18 = *(_QWORD *)v42;
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v44);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)(unsigned int)started,
      v41);
    return v12;
  }
}

```

## disassembly

```asm
0x1801cc30c  mov     [rsp+arg_8], rbx
0x1801cc311  mov     [rsp+arg_10], rsi
0x1801cc316  push    rdi
0x1801cc317  push    r12
0x1801cc319  push    r13
0x1801cc31b  push    r14
0x1801cc31d  push    r15
0x1801cc31f  sub     rsp, 2B0h
0x1801cc326  mov     rax, cs:__security_cookie
0x1801cc32d  xor     rax, rsp
0x1801cc330  mov     [rsp+2D8h+var_38], rax
0x1801cc338  mov     r14, rcx
0x1801cc33b  movzx   eax, word ptr cs:qword_18043C08A
0x1801cc342  sub     ax, 3
0x1801cc346  mov     r12d, 1
0x1801cc34c  xor     esi, esi
0x1801cc34e  cmp     ax, r12w
0x1801cc352  jbe     short loc_1801CC3AC
0x1801cc354  xor     eax, eax
0x1801cc356  lock cmpxchg qword ptr cs:xmmword_18043BF10, rsi
0x1801cc35f  setz    al
0x1801cc362  mov     rcx, [rsp+2D8h]; this
0x1801cc36a  test    al, al
0x1801cc36c  jnz     loc_1801CC9E7
0x1801cc372  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801cc379  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x1801cc37e  call    ?GetInitialSettingsReadyMaxWait@ScenarioManager@Diagnostics@Microsoft@@QEAAKXZ; Microsoft::Diagnostics::ScenarioManager::GetInitialSettingsReadyMaxWait(void)
0x1801cc383  mov     edi, eax
0x1801cc385  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801cc38c  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x1801cc391  mov     rbx, [rsp+2D8h]
0x1801cc399  mov     edx, edi; unsigned int
0x1801cc39b  mov     rcx, [rax+20h]; void *
0x1801cc39f  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x1801cc3a4  test    al, al
0x1801cc3a6  jz      loc_1801CC9F7
0x1801cc3ac  xor     edx, edx; Val
0x1801cc3ae  mov     r8d, 198h; Size
0x1801cc3b4  lea     rcx, [rsp+2D8h+WSAData]; void *
0x1801cc3bc  call    memset_0
0x1801cc3c1  mov     ecx, 202h; wVersionRequested
0x1801cc3c6  lea     rdx, [rsp+2D8h+WSAData]; lpWSAData
0x1801cc3ce  call    cs:__imp_WSAStartup
0x1801cc3d5  nop     dword ptr [rax+rax+00h]
0x1801cc3da  test    eax, eax
0x1801cc3dc  jz      short loc_1801CC3FF
0x1801cc3de  mov     rcx, [rsp+2D8h]; this
0x1801cc3e6  mov     r9d, eax; char *
0x1801cc3e9  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801cc3f0  mov     edx, 82h; void *
0x1801cc3f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801cc3fa  jmp     loc_1801CC9B9
0x1801cc3ff  lea     rcx, [r14+78h]
0x1801cc403  call    ?reset@?$unique_storage@U?$resource_policy@_N$$A6AX_N@Z$1?CleanupWinsock@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_N_N$0A@$$T@details@wil@@@details@wil@@QEAAX_N@Z; wil::details::unique_storage<wil::details::resource_policy<bool,void (bool),&wilp::CleanupWinsock(bool),wistd::integral_constant<unsigned __int64,0>,bool,bool,0,std::nullptr_t>>::reset(bool)
0x1801cc408  mov     rcx, r14; this
0x1801cc40b  call    ?StartAcceptingWindowsConnections@AgentManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::AgentManager::StartAcceptingWindowsConnections(void)
0x1801cc410  mov     ebx, eax
0x1801cc412  test    eax, eax
0x1801cc414  jns     short loc_1801CC439
0x1801cc416  mov     rcx, [rsp+2D8h]; this
0x1801cc41e  mov     r9d, eax; char *
0x1801cc421  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801cc428  mov     edx, 86h; void *
0x1801cc42d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801cc432  mov     eax, ebx
0x1801cc434  jmp     loc_1801CC9B9
0x1801cc439  movzx   eax, word ptr cs:qword_18043C08A
0x1801cc440  sub     ax, 3
0x1801cc444  cmp     ax, r12w
0x1801cc448  jbe     short loc_1801CC472
0x1801cc44a  mov     rcx, r14; this
0x1801cc44d  call    ?StartAcceptingLinuxConnections@AgentManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::AgentManager::StartAcceptingLinuxConnections(void)
0x1801cc452  mov     rcx, [rsp+2D8h]; this
0x1801cc45a  test    eax, eax
0x1801cc45c  jns     short loc_1801CC472
0x1801cc45e  mov     r9d, eax; char *
0x1801cc461  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801cc468  mov     edx, 8Ah; void *
0x1801cc46d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801cc472  mov     rax, [r14+68h]
0x1801cc476  mov     [rsp+2D8h+Handles], rax
0x1801cc47e  mov     rax, [r14+70h]
0x1801cc482  mov     [rsp+2D8h+var_230], rax
0x1801cc48a  lea     r13, dword_18042D328
0x1801cc491  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1801cc495  xor     r8d, r8d; bWaitAll
0x1801cc498  lea     rdx, [rsp+2D8h+Handles]; lpHandles
0x1801cc4a0  lea     ecx, [r8+2]; nCount
0x1801cc4a4  call    cs:__imp_WaitForMultipleObjects
0x1801cc4ab  nop     dword ptr [rax+rax+00h]
0x1801cc4b0  test    eax, eax
0x1801cc4b2  jnz     loc_1801CC6A7
0x1801cc4b8  mov     eax, cs:dword_18042D328
0x1801cc4be  cmp     eax, 4
0x1801cc4c1  jbe     short loc_1801CC4E3
0x1801cc4c3  mov     edx, 8010h
0x1801cc4c8  mov     rcx, r13
0x1801cc4cb  call    _tlgKeywordOn
0x1801cc4d0  test    al, al
0x1801cc4d2  jz      short loc_1801CC4E3
0x1801cc4d4  lea     rdx, unk_1803C7D09
0x1801cc4db  mov     rcx, r13
0x1801cc4de  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801cc4e3  mov     rdi, [r14+150h]
0x1801cc4ea  mov     rbx, [rdi]
0x1801cc4ed  cmp     rbx, rdi
0x1801cc4f0  jnz     loc_1801CC5EF
0x1801cc4f6  mov     eax, cs:dword_18042D328
0x1801cc4fc  cmp     eax, 4
0x1801cc4ff  jbe     short loc_1801CC521
0x1801cc501  mov     edx, 8010h
0x1801cc506  mov     rcx, r13
0x1801cc509  call    _tlgKeywordOn
0x1801cc50e  test    al, al
0x1801cc510  jz      short loc_1801CC521
0x1801cc512  lea     rdx, unk_1803C7CDC
0x1801cc519  mov     rcx, r13
0x1801cc51c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801cc521  lea     rdx, [r14+80h]
0x1801cc528  lea     rcx, [rsp+2D8h+var_298]
0x1801cc52d  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801cc532  nop
0x1801cc533  mov     rbx, [r14+0D0h]
0x1801cc53a  mov     rbx, [rbx]
0x1801cc53d  mov     qword ptr [rsp+2D8h+var_2A8], rbx
0x1801cc542  cmp     [rbx+19h], sil
0x1801cc546  jnz     loc_1801CC5DE
0x1801cc54c  mov     rcx, [rbx+28h]
0x1801cc550  add     rcx, 108h
0x1801cc557  lea     rdx, [rsp+2D8h+var_248]
0x1801cc55f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801cc564  movaps  xmm0, [rsp+2D8h+var_248]
0x1801cc56c  movdqa  [rsp+2D8h+var_258], xmm0
0x1801cc575  xor     edx, edx
0x1801cc577  lea     rcx, [rsp+2D8h+var_258]
0x1801cc57f  call    ?LogConnectionTerminatedSynthetic@AgentManager@Diagnostics@Microsoft@@CAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@J@Z; Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(std::wstring_view,long)
0x1801cc584  mov     r9b, r12b; bool
0x1801cc587  xor     r8d, r8d; int
0x1801cc58a  mov     dl, r12b; bool
0x1801cc58d  mov     rcx, [rbx+28h]; this
0x1801cc591  call    ?Disconnect@AgentTransport@Diagnostics@Microsoft@@QEAAJ_NJ0@Z; Microsoft::Diagnostics::AgentTransport::Disconnect(bool,long,bool)
0x1801cc596  mov     rcx, [rsp+2D8h]; this
0x1801cc59e  test    eax, eax
0x1801cc5a0  jns     short loc_1801CC5B6
0x1801cc5a2  mov     r9d, eax; char *
0x1801cc5a5  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801cc5ac  mov     edx, 0BEh; void *
0x1801cc5b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801cc5b6  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801cc5bd  call    ?GetHeartbeatManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVHeartbeatManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(void)
0x1801cc5c2  mov     rcx, rax; this
0x1801cc5c5  call    ?DecreaseActiveAgentConnectionCount@HeartBeat@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::HeartBeat::DecreaseActiveAgentConnectionCount(void)
0x1801cc5ca  lea     rcx, [rsp+2D8h+var_2A8]
0x1801cc5cf  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(void)
0x1801cc5d4  mov     rbx, qword ptr [rsp+2D8h+var_2A8]
0x1801cc5d9  jmp     loc_1801CC542
0x1801cc5de  lea     rcx, [rsp+2D8h+var_298]
0x1801cc5e3  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801cc5e8  xor     eax, eax
0x1801cc5ea  jmp     loc_1801CC9B9
0x1801cc5ef  cmp     [rbx+20h], rsi
0x1801cc5f3  jz      loc_1801CC69F
0x1801cc5f9  mov     eax, cs:dword_18042D328
0x1801cc5ff  cmp     eax, 4
0x1801cc602  jbe     short loc_1801CC647
0x1801cc604  mov     edx, 8010h
0x1801cc609  mov     rcx, r13
0x1801cc60c  call    _tlgKeywordOn
0x1801cc611  test    al, al
0x1801cc613  jz      short loc_1801CC647
0x1801cc615  mov     rax, [rbx+18h]
0x1801cc619  mov     [rsp+2D8h+var_2A0], rax
0x1801cc61e  mov     rax, [rbx+20h]
0x1801cc622  mov     qword ptr [rsp+2D8h+var_2A8], rax
0x1801cc627  lea     rax, [rsp+2D8h+var_2A0]
0x1801cc62c  mov     [rsp+2D8h+var_2B0], rax
0x1801cc631  lea     rax, [rsp+2D8h+var_2A8]
0x1801cc636  mov     qword ptr [rsp+2D8h+var_2B8], rax; int
0x1801cc63b  lea     rdx, unk_1803C7D32
0x1801cc642  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1801cc647  xor     r9d, r9d; bool
0x1801cc64a  xor     r8d, r8d; int
0x1801cc64d  xor     edx, edx; bool
0x1801cc64f  mov     rcx, [rbx+20h]; this
0x1801cc653  call    ?Disconnect@AgentTransport@Diagnostics@Microsoft@@QEAAJ_NJ0@Z; Microsoft::Diagnostics::AgentTransport::Disconnect(bool,long,bool)
0x1801cc658  test    eax, eax
0x1801cc65a  jns     short loc_1801CC678
0x1801cc65c  mov     rcx, [rsp+2D8h]; this
0x1801cc664  mov     r9d, eax; char *
0x1801cc667  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801cc66e  mov     edx, 0ACh; void *
0x1801cc673  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801cc678  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801cc67c  lea     rcx, [rbx+18h]
0x1801cc680  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(unsigned __int64)
0x1801cc685  mov     rcx, [rbx+20h]
0x1801cc689  mov     edx, r12d; fCancelPendingCallbacks
0x1801cc68c  mov     rcx, [rcx+100h]; pio
0x1801cc693  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1801cc69a  nop     dword ptr [rax+rax+00h]
0x1801cc69f  mov     rbx, [rbx]
0x1801cc6a2  jmp     loc_1801CC4ED
0x1801cc6a7  cmp     eax, r12d
0x1801cc6aa  jnz     loc_1801CC99A
0x1801cc6b0  xorps   xmm0, xmm0
0x1801cc6b3  movdqu  [rsp+2D8h+var_278], xmm0
0x1801cc6b9  mov     [rsp+2D8h+var_268], rsi
0x1801cc6be  lea     rdx, [r14+0E0h]
0x1801cc6c5  lea     rcx, [rsp+2D8h+var_228]
0x1801cc6cd  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801cc6d2  lea     rbx, [r14+130h]
0x1801cc6d9  lea     rdi, [rbx+8]
0x1801cc6dd  lea     rax, [rsp+2D8h+var_278]
0x1801cc6e2  cmp     rax, rbx
0x1801cc6e5  jz      short loc_1801CC716
0x1801cc6e7  lea     rcx, [rsp+2D8h+var_278]
0x1801cc6ec  call    ?_Tidy@?$vector@UScenarioDbLookupPair@Diagnostics@Microsoft@@V?$allocator@UScenarioDbLookupPair@Diagnostics@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Tidy(void)
0x1801cc6f1  mov     r15, [rbx]
0x1801cc6f4  mov     qword ptr [rsp+2D8h+var_278], r15
0x1801cc6f9  mov     r12, [rdi]
0x1801cc6fc  mov     qword ptr [rsp+2D8h+var_278+8], r12
0x1801cc701  mov     rax, [rbx+10h]
0x1801cc705  mov     [rsp+2D8h+var_268], rax
0x1801cc70a  mov     [rbx], rsi
0x1801cc70d  mov     [rdi], rsi
0x1801cc710  mov     [rbx+10h], rsi
0x1801cc714  jmp     short loc_1801CC71C
0x1801cc716  mov     r12, rsi
0x1801cc719  mov     r15, rsi
0x1801cc71c  mov     [rsp+2D8h+var_2A0], r12
0x1801cc721  mov     rax, [rbx]
0x1801cc724  cmp     rax, [rdi]
0x1801cc727  jz      short loc_1801CC72C
0x1801cc729  mov     [rdi], rax
0x1801cc72c  lea     rcx, [rsp+2D8h+var_228]
0x1801cc734  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801cc739  cmp     r15, r12
0x1801cc73c  jz      loc_1801CC985
0x1801cc742  mov     r12, [r15]
0x1801cc745  mov     qword ptr [rsp+2D8h+var_298], r12
0x1801cc74a  mov     edi, [r15+8]
0x1801cc74e  mov     eax, cs:dword_18042D328
0x1801cc754  cmp     eax, 4
0x1801cc757  jbe     short loc_1801CC793
0x1801cc759  mov     edx, 8010h
0x1801cc75e  mov     rcx, r13
0x1801cc761  call    _tlgKeywordOn
0x1801cc766  test    al, al
0x1801cc768  jz      short loc_1801CC793
0x1801cc76a  mov     [rsp+2D8h+var_2A8], edi
0x1801cc76e  mov     [rsp+2D8h+var_288], r12
0x1801cc773  lea     rax, [rsp+2D8h+var_2A8]
0x1801cc778  mov     [rsp+2D8h+var_2B0], rax
0x1801cc77d  lea     rax, [rsp+2D8h+var_288]
0x1801cc782  mov     qword ptr [rsp+2D8h+var_2B8], rax; int
0x1801cc787  lea     rdx, unk_1803C7C9C
0x1801cc78e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1801cc793  xorps   xmm0, xmm0
0x1801cc796  movdqu  xmmword ptr [rsp+2D8h+var_288], xmm0
0x1801cc79c  lea     r13, [r14+80h]
0x1801cc7a3  mov     rdx, r13
0x1801cc7a6  lea     rcx, [rsp+2D8h+var_208]
0x1801cc7ae  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801cc7b3  nop
0x1801cc7b4  lea     rbx, [r14+0D0h]
0x1801cc7bb  lea     r8, [rsp+2D8h+var_298]
0x1801cc7c0  lea     rdx, [rsp+2D8h+var_258]
0x1801cc7c8  mov     rcx, rbx
0x1801cc7cb  call    ?find@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@_K@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::find(unsigned __int64 const &)
0x1801cc7d0  mov     rdx, qword ptr [rsp+2D8h+var_258]
0x1801cc7d8  cmp     rdx, [rbx]
0x1801cc7db  jz      short loc_1801CC851
0x1801cc7dd  add     rdx, 28h ; '('
0x1801cc7e1  lea     rcx, [rsp+2D8h+var_288]
0x1801cc7e6  call    ??4?$shared_ptr@VITriggerInst@Diagnostics@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(std::shared_ptr<Microsoft::Diagnostics::ITriggerInst> const &)
0x1801cc7eb  mov     rbx, [rsp+2D8h+var_288]
0x1801cc7f0  lea     rcx, [rbx+108h]
0x1801cc7f7  lea     rdx, [rsp+2D8h+var_218]
0x1801cc7ff  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801cc804  movaps  xmm0, [rsp+2D8h+var_218]
0x1801cc80c  movdqa  [rsp+2D8h+var_298], xmm0
0x1801cc812  mov     edx, edi
0x1801cc814  lea     rcx, [rsp+2D8h+var_298]
0x1801cc819  call    ?LogConnectionTerminatedSynthetic@AgentManager@Diagnostics@Microsoft@@CAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@J@Z; Microsoft::Diagnostics::AgentManager::LogConnectionTerminatedSynthetic(std::wstring_view,long)
0x1801cc81e  mov     r9b, 1; bool
0x1801cc821  mov     r8d, edi; int
0x1801cc824  mov     dl, r9b; bool
0x1801cc827  mov     rcx, rbx; this
0x1801cc82a  call    ?Disconnect@AgentTransport@Diagnostics@Microsoft@@QEAAJ_NJ0@Z; Microsoft::Diagnostics::AgentTransport::Disconnect(bool,long,bool)
0x1801cc82f  mov     rcx, [rsp+2D8h]; this
0x1801cc837  test    eax, eax
0x1801cc839  jns     short loc_1801CC856
0x1801cc83b  mov     r9d, eax; char *
0x1801cc83e  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801cc845  mov     edx, 0EBh; void *
0x1801cc84a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801cc84f  jmp     short loc_1801CC856
0x1801cc851  mov     rbx, [rsp+2D8h+var_288]
0x1801cc856  lea     rcx, [rsp+2D8h+var_208]
0x1801cc85e  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
  ... truncated ...
```
