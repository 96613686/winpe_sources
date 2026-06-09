# ChatCapabilitiesContext::GetCapabilitiesFromNetwork(ushort const *,ulong,RCSeState *)

- ea: `0x1800fd3bc`
- end: `0x1800fd702`
- name: `?GetCapabilitiesFromNetwork@ChatCapabilitiesContext@@QEAAJPEBGKPEAW4RCSeState@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(ChatCapabilitiesContext *__hidden this, const unsigned __int16 *, unsigned int, enum RCSeState *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800fefb0`

## callees

- `0x180004658`
- `0x180005c2c`
- `0x180007760`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x18006db44`
- `0x180072ccc`
- `0x1800924c4`
- `0x1800a847c`
- `0x1800fcfa0`
- `0x1800fd3bc`
- `0x1800fde54`
- `0x1800fe750`
- `0x1800fe92c`
- `0x1800fec04`
- `0x1801009fc`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `PhoneUtil!MaskPhoneUri` at `0x1800fd62d`
- `PhoneUtil!MaskPhoneUri` at `0x1800fd62d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fd471`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fd4fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fd471`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fd4fd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fd440`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fd4c9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fd440`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fd4c9`

## string_xrefs

- `0x1800fd528`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`
- `0x1800fd57c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`
- `0x1800fd5c8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`
- `0x1800fd689`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`
- `0x1800fd6ba`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcapabilitiescontext.cpp`

## pseudocode

```c
__int64 __fastcall ChatCapabilitiesContext::GetCapabilitiesFromNetwork(
        ChatCapabilitiesContext *this,
        const unsigned __int16 *a2,
        __int64 a3,
        enum RCSeState *a4)
{
  unsigned int v5; // esi
  RcsServiceManager *v8; // rbx
  __int64 result; // rax
  RcsServiceManager *v10; // rbx
  int ImsClientIdForProviderId; // eax
  unsigned int v12; // ebx
  int v13; // eax
  __int64 v14; // r9
  int v15; // eax
  ChatCapabilitiesContext *v16; // rcx
  __int64 v17; // r9
  unsigned int v18; // ebx
  __int64 v19; // rcx
  int updated; // eax
  __int64 v21; // rcx
  int v22; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v26[4]; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v27; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v28[128]; // [rsp+80h] [rbp-80h] BYREF

  v5 = a3;
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      RcsGetCapabilitiesFromNetwork,
      a3,
      1,
      &v27);
  fPending = 0;
  Context = 0;
  InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
  v8 = (RcsServiceManager *)Context;
  if ( !Context )
  {
    RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
    v25 = 0;
    InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
    v8 = (RcsServiceManager *)qword_18015DCE0;
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v25);
  }
  result = RcsServiceManager::IsCapabilitySupported(v8, v5);
  if ( !(_DWORD)result )
  {
    *(_DWORD *)a4 = 0;
    return result;
  }
  fPending = 0;
  Context = 0;
  v27 = 0;
  InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
  v10 = (RcsServiceManager *)Context;
  if ( !Context )
  {
    v10 = (RcsServiceManager *)qword_18015DCE0;
    RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
    v25 = 0;
    InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
    tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v25);
  }
  ImsClientIdForProviderId = RcsServiceManager::GetImsClientIdForProviderId(v10, v5, &v27);
  v12 = ImsClientIdForProviderId;
  if ( ImsClientIdForProviderId >= 0 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v26);
    v13 = ChatCapabilitiesContext::DialStringToUriString(a2, v26);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v13 = ChatCapabilitiesContext::_EnsureService(this, &v27);
      v12 = v13;
      if ( v13 >= 0 )
      {
        Context = 0;
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&Context);
        v15 = ChatCapabilitiesContext::_RequestCapabilities(
                this,
                v26[0],
                &v27,
                (struct Windows::Phone::Restricted::Cellular::Rcs::IRcsCapabilities **)&Context);
        v12 = v15;
        if ( v15 >= 0 )
        {
          fPending = 0;
          v15 = ChatCapabilitiesContext::_EvaluateCapabilities(
                  v16,
                  (struct Windows::Phone::Restricted::Cellular::Rcs::IRcsCapabilities *)Context,
                  (enum RCSeState *)&fPending);
          v12 = v15;
          if ( v15 >= 0 )
          {
            memset_0(v28, 0, sizeof(v28));
            MaskPhoneUri(v26[0], v28, 64);
            v18 = fPending;
            if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x20) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
                CapabilitiesRetrieved,
                v28,
                (unsigned int)fPending);
            v19 = *(_QWORD *)this;
            fPending = 0;
            updated = UpdateAllContactCapabilities(v19, a2, v26[0], v18);
            if ( updated < 0 )
              Log_HREvent(
                (unsigned int)updated,
                0,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
                312);
            if ( !fPending )
            {
              v22 = ChatCapabilitiesContext::_UpdateCachedPhoneNumberCapabilities(v21, a2, &v27, v18);
              if ( v22 < 0 )
                Log_HREvent(
                  (unsigned int)v22,
                  0,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
                  316);
            }
            *(_DWORD *)a4 = v18;
            Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&Context);
            v12 = 0;
            goto LABEL_29;
          }
          v17 = 305;
        }
        else
        {
          v17 = 302;
        }
        Log_HREvent(
          (unsigned int)v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
          v17);
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&Context);
LABEL_29:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v26);
        return v12;
      }
      v14 = 299;
    }
    else
    {
      v14 = 297;
    }
    Log_HREvent(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
      v14);
    goto LABEL_29;
  }
  Log_HREvent(
    (unsigned int)ImsClientIdForProviderId,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcapabilitiescontext.cpp",
    294);
  return v12;
}

```

## disassembly

```asm
0x1800fd3bc  push    rbp
0x1800fd3be  push    rbx
0x1800fd3bf  push    rsi
0x1800fd3c0  push    rdi
0x1800fd3c1  push    r13
0x1800fd3c3  push    r14
0x1800fd3c5  push    r15
0x1800fd3c7  lea     rbp, [rsp-10h]
0x1800fd3cc  sub     rsp, 110h
0x1800fd3d3  mov     rax, cs:__security_cookie
0x1800fd3da  xor     rax, rsp
0x1800fd3dd  mov     [rbp+40h+var_40], rax
0x1800fd3e1  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x1800fd3e8  mov     rdi, r9
0x1800fd3eb  mov     esi, r8d
0x1800fd3ee  mov     r15, rdx
0x1800fd3f1  mov     r14, rcx
0x1800fd3f4  mov     r13d, 1
0x1800fd3fa  jz      short loc_1800FD41C
0x1800fd3fc  lea     rax, [rsp+140h+var_D8]
0x1800fd401  mov     r9d, r13d
0x1800fd404  lea     rdx, RcsGetCapabilitiesFromNetwork
0x1800fd40b  mov     [rsp+140h+var_120], rax
0x1800fd410  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x1800fd417  call    McGenEventWrite_EventWriteTransfer
0x1800fd41c  lea     r9, [rsp+140h+Context]; lpContext
0x1800fd421  mov     [rsp+140h+fPending], 0
0x1800fd429  lea     r8, [rsp+140h+fPending]; fPending
0x1800fd42e  mov     [rsp+140h+Context], 0
0x1800fd437  xor     edx, edx; dwFlags
0x1800fd439  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800fd440  call    cs:__imp_InitOnceBeginInitialize
0x1800fd446  mov     rbx, [rsp+140h+Context]
0x1800fd44b  test    rbx, rbx
0x1800fd44e  jnz     short loc_1800FD488
0x1800fd450  lea     rcx, qword_18015DCE0; this
0x1800fd457  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fd45c  lea     r8, qword_18015DCE0; lpContext
0x1800fd463  mov     [rsp+140h+var_100], rbx
0x1800fd468  xor     edx, edx; dwFlags
0x1800fd46a  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800fd471  call    cs:__imp_InitOnceComplete
0x1800fd477  lea     rcx, [rsp+140h+var_100]
0x1800fd47c  lea     rbx, qword_18015DCE0
0x1800fd483  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fd488  mov     edx, esi; unsigned int
0x1800fd48a  mov     rcx, rbx; this
0x1800fd48d  call    ?IsCapabilitySupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsCapabilitySupported(ulong)
0x1800fd492  test    eax, eax
0x1800fd494  jnz     short loc_1800FD49D
0x1800fd496  mov     [rdi], eax
0x1800fd498  jmp     loc_1800FD6E4
0x1800fd49d  xorps   xmm0, xmm0
0x1800fd4a0  mov     [rsp+140h+fPending], 0
0x1800fd4a8  lea     r9, [rsp+140h+Context]; lpContext
0x1800fd4ad  mov     [rsp+140h+Context], 0
0x1800fd4b6  lea     r8, [rsp+140h+fPending]; fPending
0x1800fd4bb  xor     edx, edx; dwFlags
0x1800fd4bd  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800fd4c4  movups  xmmword ptr [rsp+140h+var_D8.Data1], xmm0
0x1800fd4c9  call    cs:__imp_InitOnceBeginInitialize
0x1800fd4cf  mov     rbx, [rsp+140h+Context]
0x1800fd4d4  test    rbx, rbx
0x1800fd4d7  jnz     short loc_1800FD50D
0x1800fd4d9  lea     rbx, qword_18015DCE0
0x1800fd4e0  mov     rcx, rbx; this
0x1800fd4e3  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fd4e8  mov     r8, rbx; lpContext
0x1800fd4eb  mov     [rsp+140h+var_100], 0
0x1800fd4f4  xor     edx, edx; dwFlags
0x1800fd4f6  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800fd4fd  call    cs:__imp_InitOnceComplete
0x1800fd503  lea     rcx, [rsp+140h+var_100]
0x1800fd508  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fd50d  lea     r8, [rsp+140h+var_D8]; struct _GUID *
0x1800fd512  mov     edx, esi; unsigned int
0x1800fd514  mov     rcx, rbx; this
0x1800fd517  call    ?GetImsClientIdForProviderId@RcsServiceManager@@QEAAJKAEAU_GUID@@@Z; RcsServiceManager::GetImsClientIdForProviderId(ulong,_GUID &)
0x1800fd51c  mov     ebx, eax
0x1800fd51e  test    eax, eax
0x1800fd520  jns     short loc_1800FD53E
0x1800fd522  mov     r9d, 126h
0x1800fd528  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fd52f  mov     edx, r13d
0x1800fd532  mov     ecx, eax
0x1800fd534  call    Log_HREvent
0x1800fd539  jmp     loc_1800FD6E2
0x1800fd53e  lea     rcx, [rsp+140h+var_F8]; void *
0x1800fd543  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800fd548  lea     rdx, [rsp+140h+var_F8]
0x1800fd54d  mov     rcx, r15
0x1800fd550  call    ?DialStringToUriString@ChatCapabilitiesContext@@SAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ChatCapabilitiesContext::DialStringToUriString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800fd555  mov     ebx, eax
0x1800fd557  test    eax, eax
0x1800fd559  jns     short loc_1800FD563
0x1800fd55b  mov     r9d, 129h
0x1800fd561  jmp     short loc_1800FD57C
0x1800fd563  lea     rdx, [rsp+140h+var_D8]; struct _GUID *
0x1800fd568  mov     rcx, r14; this
0x1800fd56b  call    ?_EnsureService@ChatCapabilitiesContext@@IEAAJAEBU_GUID@@@Z; ChatCapabilitiesContext::_EnsureService(_GUID const &)
0x1800fd570  mov     ebx, eax
0x1800fd572  test    eax, eax
0x1800fd574  jns     short loc_1800FD592
0x1800fd576  mov     r9d, 12Bh
0x1800fd57c  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fd583  mov     edx, r13d
0x1800fd586  mov     ecx, eax
0x1800fd588  call    Log_HREvent
0x1800fd58d  jmp     loc_1800FD6D8
0x1800fd592  lea     rcx, [rsp+140h+Context]
0x1800fd597  mov     [rsp+140h+Context], 0
0x1800fd5a0  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800fd5a5  mov     rdx, [rsp+140h+var_F8]; unsigned __int16 *
0x1800fd5aa  lea     r9, [rsp+140h+Context]; struct Windows::Phone::Restricted::Cellular::Rcs::IRcsCapabilities **
0x1800fd5af  lea     r8, [rsp+140h+var_D8]; struct _GUID *
0x1800fd5b4  mov     rcx, r14; this
0x1800fd5b7  call    ?_RequestCapabilities@ChatCapabilitiesContext@@IEAAJPEBGAEBU_GUID@@PEAPEAUIRcsCapabilities@Rcs@Cellular@Restricted@Phone@Windows@@@Z; ChatCapabilitiesContext::_RequestCapabilities(ushort const *,_GUID const &,Windows::Phone::Restricted::Cellular::Rcs::IRcsCapabilities * *)
0x1800fd5bc  mov     ebx, eax
0x1800fd5be  test    eax, eax
0x1800fd5c0  jns     short loc_1800FD5E8
0x1800fd5c2  mov     r9d, 12Eh
0x1800fd5c8  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fd5cf  mov     edx, r13d
0x1800fd5d2  mov     ecx, eax
0x1800fd5d4  call    Log_HREvent
0x1800fd5d9  lea     rcx, [rsp+140h+Context]
0x1800fd5de  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800fd5e3  jmp     loc_1800FD6D8
0x1800fd5e8  mov     rdx, [rsp+140h+Context]; struct Windows::Phone::Restricted::Cellular::Rcs::IRcsCapabilities *
0x1800fd5ed  lea     r8, [rsp+140h+fPending]; enum RCSeState *
0x1800fd5f2  mov     [rsp+140h+fPending], 0
0x1800fd5fa  call    ?_EvaluateCapabilities@ChatCapabilitiesContext@@IEAAJPEAUIRcsCapabilities@Rcs@Cellular@Restricted@Phone@Windows@@PEAW4RCSeState@@@Z; ChatCapabilitiesContext::_EvaluateCapabilities(Windows::Phone::Restricted::Cellular::Rcs::IRcsCapabilities *,RCSeState *)
0x1800fd5ff  mov     ebx, eax
0x1800fd601  test    eax, eax
0x1800fd603  jns     short loc_1800FD60D
0x1800fd605  mov     r9d, 131h
0x1800fd60b  jmp     short loc_1800FD5C8
0x1800fd60d  xor     edx, edx; Val
0x1800fd60f  lea     rcx, [rbp+40h+var_C0]; void *
0x1800fd613  mov     r8d, 80h; Size
0x1800fd619  call    memset_0
0x1800fd61e  mov     rcx, [rsp+140h+var_F8]
0x1800fd623  lea     rdx, [rbp+40h+var_C0]
0x1800fd627  mov     r8d, 40h ; '@'
0x1800fd62d  call    cs:__imp_MaskPhoneUri
0x1800fd633  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 20h
0x1800fd63a  mov     ebx, [rsp+140h+fPending]
0x1800fd63e  jz      short loc_1800FD65A
0x1800fd640  mov     r9d, ebx
0x1800fd643  lea     r8, [rbp+40h+var_C0]
0x1800fd647  lea     rdx, CapabilitiesRetrieved
0x1800fd64e  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x1800fd655  call    McTemplateU0zq_EventWriteTransfer
0x1800fd65a  mov     r8, [rsp+140h+var_F8]
0x1800fd65f  lea     rax, [rsp+140h+fPending]
0x1800fd664  mov     rcx, [r14]
0x1800fd667  mov     r9d, ebx
0x1800fd66a  mov     rdx, r15
0x1800fd66d  mov     [rsp+140h+var_118], rax
0x1800fd672  mov     [rsp+140h+fPending], 0
0x1800fd67a  call    ?UpdateAllContactCapabilities@@YAJPEAUIPOutlookApp3@@PEBG1W4RCSeState@@KPEAH@Z; UpdateAllContactCapabilities(IPOutlookApp3 *,ushort const *,ushort const *,RCSeState,ulong,int *)
0x1800fd67f  test    eax, eax
0x1800fd681  jns     short loc_1800FD699
0x1800fd683  mov     r9d, 138h
0x1800fd689  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fd690  xor     edx, edx
0x1800fd692  mov     ecx, eax
0x1800fd694  call    Log_HREvent
0x1800fd699  cmp     [rsp+140h+fPending], 0
0x1800fd69e  jnz     short loc_1800FD6CA
0x1800fd6a0  mov     r9d, ebx
0x1800fd6a3  lea     r8, [rsp+140h+var_D8]
0x1800fd6a8  mov     rdx, r15
0x1800fd6ab  call    ?_UpdateCachedPhoneNumberCapabilities@ChatCapabilitiesContext@@IEAAJPEBGAEBU_GUID@@W4RCSeState@@@Z; ChatCapabilitiesContext::_UpdateCachedPhoneNumberCapabilities(ushort const *,_GUID const &,RCSeState)
0x1800fd6b0  test    eax, eax
0x1800fd6b2  jns     short loc_1800FD6CA
0x1800fd6b4  mov     r9d, 13Ch
0x1800fd6ba  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800fd6c1  xor     edx, edx
0x1800fd6c3  mov     ecx, eax
0x1800fd6c5  call    Log_HREvent
0x1800fd6ca  lea     rcx, [rsp+140h+Context]
0x1800fd6cf  mov     [rdi], ebx
0x1800fd6d1  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800fd6d6  xor     ebx, ebx
0x1800fd6d8  lea     rcx, [rsp+140h+var_F8]; void *
0x1800fd6dd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800fd6e2  mov     eax, ebx
0x1800fd6e4  mov     rcx, [rbp+40h+var_40]
0x1800fd6e8  xor     rcx, rsp; StackCookie
0x1800fd6eb  call    __security_check_cookie
0x1800fd6f0  add     rsp, 110h
0x1800fd6f7  pop     r15
0x1800fd6f9  pop     r14
0x1800fd6fb  pop     r13
0x1800fd6fd  pop     rdi
0x1800fd6fe  pop     rsi
0x1800fd6ff  pop     rbx
0x1800fd700  pop     rbp
0x1800fd701  retn
```
