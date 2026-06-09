# _lambda_788b10927cacc053a7f19f4ea25f50f3_::operator()(void)

- ea: `0x180070c00`
- end: `0x180070e26`
- name: `??R_lambda_788b10927cacc053a7f19f4ea25f50f3_@@QEBA@XZ`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073320`

## callees

- `0x1800088e8`
- `0x18005ee88`
- `0x18005eec0`
- `0x180061e1c`
- `0x18006fb50`
- `0x180070c00`
- `0x180072868`
- `0x180075060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070dd8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070dd8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070c5a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180070c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070d8a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180070d80`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180070d80`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180070c1e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180070c1e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180070dc8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180070dff`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180070dc8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180070dff`

## string_xrefs

- `0x180070c3f`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180070c8d`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall _lambda_788b10927cacc053a7f19f4ea25f50f3_::operator()(LPVOID *a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  HANDLE EventW; // rax
  UserManagerService *v6; // rcx
  int v7; // edi
  __int64 v8; // rdx
  LPVOID v9; // rdi
  __int64 v10; // rcx
  __int64 *v11; // rax
  signed int LastError; // eax
  int v13; // [rsp+20h] [rbp-38h]
  char *v14; // [rsp+40h] [rbp-18h] BYREF
  char v15; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *((_QWORD *)*a1 + 1) = RegisterServiceCtrlHandlerExW(
                           L"UserManager",
                           Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic,
                           *a1);
  if ( !*((_QWORD *)*a1 + 1) )
  {
    v3 = 509;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v6 = (UserManagerService *)*a1;
  *((_QWORD *)*a1 + 6) = EventW;
  if ( !*((_QWORD *)*a1 + 6) )
  {
    v3 = 512;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  v7 = UserManagerService::OnServiceStarting(v6);
  if ( v7 < 0 )
  {
    v8 = 516;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v7,
      v13);
    return (unsigned int)v7;
  }
  v9 = *a1;
  if ( *(_BYTE *)a1[1] )
  {
    v10 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create();
    if ( *(_QWORD *)(v10 + 48) )
      goto LABEL_15;
    byte_180148528 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_180148520 = (__int64)std::basic_ios<unsigned short>::_Add_vtordisp2;
    v11 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_;
    byte_180148510 = 0;
    qword_180148518 = (__int64)v9;
  }
  else
  {
    v10 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    if ( *(_QWORD *)(v10 + 48) )
      goto LABEL_15;
    byte_1801486F8 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_1801486F0 = (__int64)std::basic_ios<unsigned short>::_Add_vtordisp2;
    v11 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_;
    byte_1801486E0 = 0;
    qword_1801486E8 = (__int64)v9;
  }
  *(_QWORD *)(v10 + 48) = v11;
LABEL_15:
  *(_QWORD *)a1[2] = v10;
  v7 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(
         *(Windows::Internal::ServiceModuleBase **)a1[2],
         *(_BYTE *)a1[1]);
  if ( v7 < 0 )
  {
    v8 = 545;
    goto LABEL_8;
  }
  v7 = 0;
  if ( !QueueUserWorkItem(UserManagerService::ThreadProcInitialize, *a1, 0x10u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  *(_DWORD *)a1[3] = v7;
  if ( v7 < 0 )
  {
    v8 = 547;
    goto LABEL_8;
  }
  v14 = (char *)*a1;
  v15 = 1;
  SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v14 + 1), (LPSERVICE_STATUS)(v14 + 16));
  WaitForSingleObject(*((HANDLE *)*a1 + 6), 0xFFFFFFFF);
  if ( ((*((_DWORD *)*a1 + 5) - 1) & 0xFFFFFFFD) != 0 )
  {
    *((_DWORD *)*a1 + 5) = 3;
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)*a1 + 1), (LPSERVICE_STATUS)((char *)*a1 + 16));
  }
  wil::details::lambda_call<_lambda_7a538ab5404eeec992554d47e399dc1a_>::reset(&v14);
  wil::details::lambda_call<_lambda_7a538ab5404eeec992554d47e399dc1a_>::reset(&v14);
  return 0;
}

```

## disassembly

```asm
0x180070c00  mov     [rsp+arg_0], rbx
0x180070c05  push    rdi
0x180070c06  sub     rsp, 50h
0x180070c0a  mov     r8, [rcx]; lpContext
0x180070c0d  lea     rdx, ?HandlerExStatic@?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x180070c14  mov     rbx, rcx
0x180070c17  lea     rcx, ServiceName; "UserManager"
0x180070c1e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180070c24  mov     rdx, [rbx]
0x180070c27  mov     [rdx+8], rax
0x180070c2b  mov     rax, [rbx]
0x180070c2e  cmp     qword ptr [rax+8], 0
0x180070c33  jnz     short loc_180070C50
0x180070c35  mov     edx, 1FDh; void *
0x180070c3a  mov     rcx, [rsp+58h]; this
0x180070c3f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x180070c46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180070c4b  jmp     loc_180070E1B
0x180070c50  xor     r9d, r9d; lpName
0x180070c53  xor     r8d, r8d; bInitialState
0x180070c56  xor     edx, edx; bManualReset
0x180070c58  xor     ecx, ecx; lpEventAttributes
0x180070c5a  call    cs:__imp_CreateEventW
0x180070c60  mov     rcx, [rbx]; this
0x180070c63  mov     [rcx+30h], rax
0x180070c67  mov     rax, [rbx]
0x180070c6a  cmp     qword ptr [rax+30h], 0
0x180070c6f  jnz     short loc_180070C78
0x180070c71  mov     edx, 200h
0x180070c76  jmp     short loc_180070C3A
0x180070c78  call    ?OnServiceStarting@UserManagerService@@QEAAJXZ; UserManagerService::OnServiceStarting(void)
0x180070c7d  mov     edi, eax
0x180070c7f  test    eax, eax
0x180070c81  jns     short loc_180070CA3
0x180070c83  mov     edx, 204h; void *
0x180070c88  mov     rcx, [rsp+58h]; this
0x180070c8d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\com\\inc\\comservice"...
0x180070c94  mov     r9d, edi; char *
0x180070c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070c9c  mov     eax, edi
0x180070c9e  jmp     loc_180070E1B
0x180070ca3  mov     rax, [rbx+8]
0x180070ca7  mov     rdi, [rbx]
0x180070caa  cmp     byte ptr [rax], 0
0x180070cad  jz      short loc_180070CFC
0x180070caf  call    ?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)
0x180070cb4  mov     rcx, rax
0x180070cb7  cmp     qword ptr [rax+30h], 0
0x180070cbc  jnz     loc_180070D47
0x180070cc2  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180070cc9  mov     cs:byte_180148528, 1
0x180070cd0  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180070cd7  lea     rax, ?_Add_vtordisp2@?$basic_ios@GU?$char_traits@G@std@@@std@@UEAAXXZ; std::basic_ios<ushort>::_Add_vtordisp2(void)
0x180070cde  mov     cs:qword_180148520, rax
0x180070ce5  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x180070cec  mov     cs:byte_180148510, 0
0x180070cf3  mov     cs:qword_180148518, rdi
0x180070cfa  jmp     short loc_180070D43
0x180070cfc  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x180070d01  mov     rcx, rax
0x180070d04  cmp     qword ptr [rax+30h], 0
0x180070d09  jnz     short loc_180070D47
0x180070d0b  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180070d12  mov     cs:byte_1801486F8, 1
0x180070d19  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180070d20  lea     rax, ?_Add_vtordisp2@?$basic_ios@GU?$char_traits@G@std@@@std@@UEAAXXZ; std::basic_ios<ushort>::_Add_vtordisp2(void)
0x180070d27  mov     cs:qword_1801486F0, rax
0x180070d2e  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VUserManagerService@@$02USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<UserManagerService,3,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180070d35  mov     cs:byte_1801486E0, 0
0x180070d3c  mov     cs:qword_1801486E8, rdi
0x180070d43  mov     [rcx+30h], rax
0x180070d47  mov     rax, [rbx+10h]
0x180070d4b  mov     [rax], rcx
0x180070d4e  mov     rdx, [rbx+8]
0x180070d52  mov     rcx, [rbx+10h]
0x180070d56  mov     dl, [rdx]
0x180070d58  mov     rcx, [rcx]
0x180070d5b  call    ??$Initialize@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x180070d60  mov     edi, eax
0x180070d62  test    eax, eax
0x180070d64  jns     short loc_180070D70
0x180070d66  mov     edx, 221h
0x180070d6b  jmp     loc_180070C88
0x180070d70  mov     rdx, [rbx]; Context
0x180070d73  lea     rcx, ?ThreadProcInitialize@UserManagerService@@CAKPEAX@Z; Function
0x180070d7a  xor     edi, edi
0x180070d7c  lea     r8d, [rdi+10h]; Flags
0x180070d80  call    cs:__imp_QueueUserWorkItem
0x180070d86  test    eax, eax
0x180070d88  jnz     short loc_180070D9F
0x180070d8a  call    cs:__imp_GetLastError
0x180070d90  mov     edi, eax
0x180070d92  test    eax, eax
0x180070d94  jle     short loc_180070D9F
0x180070d96  movzx   edi, ax
0x180070d99  or      edi, 80070000h
0x180070d9f  mov     rcx, [rbx+18h]
0x180070da3  mov     [rcx], edi
0x180070da5  test    edi, edi
0x180070da7  jns     short loc_180070DB3
0x180070da9  mov     edx, 223h
0x180070dae  jmp     loc_180070C88
0x180070db3  mov     rcx, [rbx]
0x180070db6  mov     [rsp+58h+var_18], rcx
0x180070dbb  mov     [rsp+58h+var_10], 1
0x180070dc0  lea     rdx, [rcx+10h]; lpServiceStatus
0x180070dc4  mov     rcx, [rcx+8]; hServiceStatus
0x180070dc8  call    cs:__imp_SetServiceStatus
0x180070dce  mov     rcx, [rbx]
0x180070dd1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180070dd4  mov     rcx, [rcx+30h]; hHandle
0x180070dd8  call    cs:__imp_WaitForSingleObject
0x180070dde  mov     rcx, [rbx]
0x180070de1  mov     eax, [rcx+14h]
0x180070de4  dec     eax
0x180070de6  test    eax, 0FFFFFFFDh
0x180070deb  jz      short loc_180070E05
0x180070ded  mov     dword ptr [rcx+14h], 3
0x180070df4  mov     rcx, [rbx]
0x180070df7  lea     rdx, [rcx+10h]; lpServiceStatus
0x180070dfb  mov     rcx, [rcx+8]; hServiceStatus
0x180070dff  call    cs:__imp_SetServiceStatus
0x180070e05  lea     rcx, [rsp+58h+var_18]
0x180070e0a  call    ?reset@?$lambda_call@V_lambda_7a538ab5404eeec992554d47e399dc1a_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_7a538ab5404eeec992554d47e399dc1a_>::reset(void)
0x180070e0f  lea     rcx, [rsp+58h+var_18]
0x180070e14  call    ?reset@?$lambda_call@V_lambda_7a538ab5404eeec992554d47e399dc1a_@@@details@wil@@QEAAXXZ; wil::details::lambda_call<_lambda_7a538ab5404eeec992554d47e399dc1a_>::reset(void)
0x180070e19  xor     eax, eax
0x180070e1b  mov     rbx, [rsp+58h+arg_0]
0x180070e20  add     rsp, 50h
0x180070e24  pop     rdi
0x180070e25  retn
```
