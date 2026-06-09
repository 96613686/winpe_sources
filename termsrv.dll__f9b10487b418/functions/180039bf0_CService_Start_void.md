# CService::Start(void)

- ea: `0x180039bf0`
- end: `0x180039fe9`
- name: `?Start@CService@@QEAAJXZ`
- size: `1017`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039860`

## callees

- `0x18000a210`
- `0x18001c71c`
- `0x18002693c`
- `0x18002ef90`
- `0x1800321f0`
- `0x1800330c4`
- `0x18003912c`
- `0x180039b34`
- `0x180039bf0`
- `0x18003a0e4`
- `0x18003a144`
- `0x18009d4cc`
- `0x18009e0a0`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180039ca2`
- `ntdll!EtwEventRegister` at `0x180039ca2`
- `ntdll!EtwEventUnregister` at `0x180039c6f`
- `ntdll!EtwEventUnregister` at `0x180039c6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039d8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039dce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039dff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039d8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039dce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e8d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180039e7b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180039e7b`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x180039c15`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x180039c15`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180039c48`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180039c48`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180039e22`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180039e22`
- `WS2_32!__imp_WSAStartup` at `0x180039f8e`
- `WS2_32!__imp_WSAStartup` at `0x180039f8e`

## string_xrefs

- `0x180039f33`: `CService::Start`
- `0x180039d4d`: `UpdateServiceStatus failed: 0x%x in %s`
- `0x180039db8`: `CreateEvent failed: 0x%x in %s`
- `0x180039e48`: `RegisterServiceCtrlHandlerEx failed: %x`
- `0x180039eb9`: `WaitForReadyMiscThread failed: 0x%x in %s`
- `0x180039e1b`: `TermService`
- `0x180039ef3`: `TermService`

## pseudocode

```c
__int64 __fastcall CService::Start(CService *this)
{
  unsigned int v1; // r8d
  int updated; // eax
  int v3; // ebx
  const char *v4; // rdx
  int v5; // eax
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  CService *v9; // rcx
  signed int v10; // eax
  int ready; // eax
  CRCMModule *v12; // rcx
  int inited; // eax
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // eax
  bool v17; // sf
  int v19; // [rsp+40h] [rbp-1D8h] BYREF
  DWORD ThreadId; // [rsp+44h] [rbp-1D4h] BYREF
  struct _GUID v21; // [rsp+48h] [rbp-1D0h] BYREF
  WSAData WSAData; // [rsp+60h] [rbp-1B8h] BYREF

  I_RpcServerDisableExceptionFilter(this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TermsrvRedirectionGuard>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TermsrvRedirectionGuard>::GetImpl'::`2'::impl)
    && !(unsigned int)CUtils::OptOutTermsrvRedirectionGuard() )
  {
    v19 = 1;
    SetProcessMitigationPolicy(16, &v19, 4);
  }
  ThreadId = 0;
  v21 = CLSID_RemoteConnectionManager;
  if ( qword_18012BB50 )
  {
    EtwEventUnregister();
    qword_18012BB50 = 0;
  }
  CrimsonHelper::s_instance = S_TermService;
  if ( !(unsigned int)EtwEventRegister(&CrimsonHelper::s_instance, 0, 0, &qword_18012BB50) )
    byte_18012BB58 = 1;
  byte_18012BB59 = 1;
  qword_18012BB10 = (__int64)TRACE_INF;
  qword_18012BB18 = (__int64)TRACE_WRN;
  qword_18012BB30 = (__int64)TRACE_INF;
  qword_18012BB20 = (__int64)TRACE_ERR;
  qword_18012BB28 = (__int64)TRACE_FATAL;
  qword_18012BB38 = (__int64)TRACE_ENT;
  qword_18012BB40 = (__int64)TRACE_EXIT;
  qword_18012BB48 = (__int64)TRACE_DUMP;
  updated = CService::UpdateServiceStatus((CService *)&_Service, 2u, v1, 1u, 0);
  v3 = updated | 0x10000000;
  if ( updated < 0 )
  {
    v4 = "UpdateServiceStatus failed: 0x%x in %s";
LABEL_39:
    _DbgPrintMessage(8, v4, (unsigned int)v3, "CService::Start");
    goto LABEL_40;
  }
  v5 = CUtils::Initialize();
  v3 = v5;
  if ( v5 < 0 )
  {
    _DbgPrintMessage(8, "CUtils::Initialize failed: 0x%x", v5);
LABEL_40:
    CService::Shutdown((CService *)&_Service);
    return (unsigned int)v3;
  }
  RegisterTraceLoggingProvider();
  qword_180128758 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_180128758 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_16;
  }
  qword_180128768 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_180128768 )
  {
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 < 0 )
    {
LABEL_16:
      v4 = "CreateEvent failed: 0x%x in %s";
      goto LABEL_39;
    }
  }
  qword_180128750 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_180128750 )
    goto LABEL_27;
  qword_180128718 = (__int64)RegisterServiceCtrlHandlerExW(
                               L"TermService",
                               CService::staticServiceCtrlHandler,
                               &_Service);
  if ( !qword_180128718 )
  {
    v8 = GetLastError();
    v3 = v8;
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    _DbgPrintMessage(8, "RegisterServiceCtrlHandlerEx failed: %x", v3);
    goto LABEL_29;
  }
  hThread = CreateThread(0, 0, CService::staticMiscThread, &_Service, 0, &ThreadId);
  if ( !hThread )
  {
LABEL_27:
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
LABEL_29:
    if ( v3 < 0 )
      goto LABEL_40;
    return (unsigned int)v3;
  }
  ready = CService::WaitForReadyMiscThread(v9);
  v3 = ready;
  if ( ready < 0 )
  {
    _DbgPrintMessage(8, "WaitForReadyMiscThread failed: 0x%x in %s", (unsigned int)ready, "CService::Start");
    goto LABEL_40;
  }
  inited = CRCMModule::InitServer(v12, &v21);
  v3 = inited;
  if ( inited < 0 )
  {
    _DbgPrintMessage(8, "_AtlModule.InitServer failed: 0x%x in %s", (unsigned int)inited, "CService::Start");
    goto LABEL_40;
  }
  v14 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, __int64, void (__fastcall *)(void *, unsigned __int8), void *, int))(qword_180128740 + 192))(
          &qword_180128748,
          L"TermService",
          qword_180128750,
          CService::staticStopServiceCallback,
          &_Service,
          8);
  v3 = v14;
  if ( v14 > 0 )
    v3 = (unsigned __int16)v14 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = "svcsGlobals->RegisterStopCallback failed: 0x%x in %s";
    goto LABEL_39;
  }
  CService::UpdateServiceStatus((CService *)&_Service, 4u, v15, 0, 0);
  CService::Advertise((CService *)&_Service, 1);
  memset_0(&WSAData, 0, sizeof(WSAData));
  v16 = WSAStartup(0x202u, &WSAData);
  v17 = v16 < 0;
  if ( v16 > 0 )
  {
    v16 = (unsigned __int16)v16 | 0x80070000;
    v17 = v16 < 0;
  }
  if ( v17 )
    _DbgPrintMessage(4, "WSAStartup Failed: 0x%x", v16);
  else
    _Service = 1;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180039bf0  mov     [rsp+arg_0], rbx
0x180039bf5  mov     [rsp+arg_8], rsi
0x180039bfa  push    r14
0x180039bfc  sub     rsp, 210h
0x180039c03  mov     rax, cs:__security_cookie
0x180039c0a  xor     rax, rsp
0x180039c0d  mov     [rsp+218h+var_18], rax
0x180039c15  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x180039c1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TermsrvRedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TermsrvRedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TermsrvRedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_TermsrvRedirectionGuard>::GetImpl(void)'::`2'::impl
0x180039c22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TermsrvRedirectionGuard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TermsrvRedirectionGuard>::__private_IsEnabled(void)
0x180039c27  test    al, al
0x180039c29  jz      short loc_180039C4E
0x180039c2b  call    ?OptOutTermsrvRedirectionGuard@CUtils@@SAHXZ; CUtils::OptOutTermsrvRedirectionGuard(void)
0x180039c30  test    eax, eax
0x180039c32  jnz     short loc_180039C4E
0x180039c34  lea     r8d, [rax+4]
0x180039c38  mov     [rsp+218h+var_1D8], 1
0x180039c40  lea     rdx, [rsp+218h+var_1D8]
0x180039c45  lea     ecx, [rax+10h]
0x180039c48  call    cs:__imp_SetProcessMitigationPolicy
0x180039c4e  movups  xmm0, xmmword ptr cs:CLSID_RemoteConnectionManager.Data1
0x180039c55  mov     rcx, cs:qword_18012BB50
0x180039c5c  mov     [rsp+218h+ThreadId], 0
0x180039c64  movdqu  xmmword ptr [rsp+218h+var_1D0.Data1], xmm0
0x180039c6a  test    rcx, rcx
0x180039c6d  jz      short loc_180039C80
0x180039c6f  call    cs:__imp_EtwEventUnregister
0x180039c75  mov     cs:qword_18012BB50, 0
0x180039c80  movups  xmm0, cs:S_TermService
0x180039c87  lea     r9, qword_18012BB50
0x180039c8e  xor     r8d, r8d
0x180039c91  xor     edx, edx
0x180039c93  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180039c9a  movdqu  cs:?s_instance@CrimsonHelper@@0V1@A, xmm0; CrimsonHelper CrimsonHelper::s_instance
0x180039ca2  call    cs:__imp_EtwEventRegister
0x180039ca8  test    eax, eax
0x180039caa  jnz     short loc_180039CB3
0x180039cac  mov     cs:byte_18012BB58, 1
0x180039cb3  lea     rcx, TRACE_INF
0x180039cba  mov     cs:byte_18012BB59, 1
0x180039cc1  lea     rax, TRACE_WRN
0x180039cc8  mov     cs:qword_18012BB10, rcx
0x180039ccf  mov     cs:qword_18012BB18, rax
0x180039cd6  lea     r14, ?_Service@@3VCService@@A; CService _Service
0x180039cdd  lea     rax, TRACE_ERR
0x180039ce4  mov     cs:qword_18012BB30, rcx
0x180039ceb  mov     cs:qword_18012BB20, rax
0x180039cf2  mov     edx, 2; unsigned int
0x180039cf7  lea     rax, TRACE_FATAL
0x180039cfe  mov     [rsp+218h+dwCreationFlags], 0; unsigned int
0x180039d06  mov     cs:qword_18012BB28, rax
0x180039d0d  mov     rcx, r14; this
0x180039d10  lea     rax, TRACE_ENT
0x180039d17  mov     cs:qword_18012BB38, rax
0x180039d1e  lea     r9d, [rdx-1]; unsigned int
0x180039d22  lea     rax, TRACE_EXIT
0x180039d29  mov     cs:qword_18012BB40, rax
0x180039d30  lea     rax, TRACE_DUMP
0x180039d37  mov     cs:qword_18012BB48, rax
0x180039d3e  call    ?UpdateServiceStatus@CService@@IEAAHKKKK@Z; CService::UpdateServiceStatus(ulong,ulong,ulong,ulong)
0x180039d43  mov     ebx, eax
0x180039d45  or      ebx, 10000000h
0x180039d4b  jge     short loc_180039D59
0x180039d4d  lea     rdx, aUpdateservices; "UpdateServiceStatus failed: 0x%x in %s"
0x180039d54  jmp     loc_180039F30
0x180039d59  call    ?Initialize@CUtils@@SAJXZ; CUtils::Initialize(void)
0x180039d5e  mov     ebx, eax
0x180039d60  test    eax, eax
0x180039d62  jns     short loc_180039D7D
0x180039d64  mov     r8d, eax
0x180039d67  lea     rdx, aCutilsInitiali_0; "CUtils::Initialize failed: 0x%x"
0x180039d6e  mov     ecx, 8; int
0x180039d73  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039d78  jmp     loc_180039F44
0x180039d7d  call    ?RegisterTraceLoggingProvider@@YAXXZ; RegisterTraceLoggingProvider(void)
0x180039d82  xor     r9d, r9d; lpName
0x180039d85  xor     r8d, r8d; bInitialState
0x180039d88  xor     edx, edx; bManualReset
0x180039d8a  xor     ecx, ecx; lpEventAttributes
0x180039d8c  call    cs:__imp_CreateEventW
0x180039d92  mov     cs:qword_180128758, rax
0x180039d99  mov     esi, 80070000h
0x180039d9e  test    rax, rax
0x180039da1  jnz     short loc_180039DC4
0x180039da3  call    cs:__imp_GetLastError
0x180039da9  mov     ebx, eax
0x180039dab  test    eax, eax
0x180039dad  jle     short loc_180039DB4
0x180039daf  movzx   ebx, ax
0x180039db2  or      ebx, esi
0x180039db4  test    ebx, ebx
0x180039db6  jns     short loc_180039DC4
0x180039db8  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x180039dbf  jmp     loc_180039F30
0x180039dc4  xor     r9d, r9d; lpName
0x180039dc7  xor     r8d, r8d; bInitialState
0x180039dca  xor     edx, edx; bManualReset
0x180039dcc  xor     ecx, ecx; lpEventAttributes
0x180039dce  call    cs:__imp_CreateEventW
0x180039dd4  mov     cs:qword_180128768, rax
0x180039ddb  test    rax, rax
0x180039dde  jnz     short loc_180039DF5
0x180039de0  call    cs:__imp_GetLastError
0x180039de6  mov     ebx, eax
0x180039de8  test    eax, eax
0x180039dea  jle     short loc_180039DF1
0x180039dec  movzx   ebx, ax
0x180039def  or      ebx, esi
0x180039df1  test    ebx, ebx
0x180039df3  js      short loc_180039DB8
0x180039df5  xor     r9d, r9d; lpName
0x180039df8  xor     r8d, r8d; bInitialState
0x180039dfb  xor     edx, edx; bManualReset
0x180039dfd  xor     ecx, ecx; lpEventAttributes
0x180039dff  call    cs:__imp_CreateEventW
0x180039e05  mov     cs:qword_180128750, rax
0x180039e0c  test    rax, rax
0x180039e0f  jz      short loc_180039E8D
0x180039e11  mov     r8, r14; lpContext
0x180039e14  lea     rdx, ?staticServiceCtrlHandler@CService@@KAKKKPEAX0@Z; lpHandlerProc
0x180039e1b  lea     rcx, ?SERVICE_NAME@CService@@1QBGB; "TermService"
0x180039e22  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180039e28  mov     cs:qword_180128718, rax
0x180039e2f  test    rax, rax
0x180039e32  jnz     short loc_180039E5B
0x180039e34  call    cs:__imp_GetLastError
0x180039e3a  mov     ebx, eax
0x180039e3c  test    eax, eax
0x180039e3e  jle     short loc_180039E45
0x180039e40  movzx   ebx, ax
0x180039e43  or      ebx, esi
0x180039e45  mov     r8d, ebx
0x180039e48  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerEx failed: %x"
0x180039e4f  mov     ecx, 8; int
0x180039e54  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039e59  jmp     short loc_180039E9E
0x180039e5b  lea     rax, [rsp+218h+ThreadId]
0x180039e60  mov     r9, r14; lpParameter
0x180039e63  mov     [rsp+218h+lpThreadId], rax; lpThreadId
0x180039e68  lea     r8, ?staticMiscThread@CService@@KAKPEAX@Z; lpStartAddress
0x180039e6f  xor     edx, edx; dwStackSize
0x180039e71  mov     [rsp+218h+dwCreationFlags], 0; dwCreationFlags
0x180039e79  xor     ecx, ecx; lpThreadAttributes
0x180039e7b  call    cs:__imp_CreateThread
0x180039e81  mov     cs:hThread, rax
0x180039e88  test    rax, rax
0x180039e8b  jnz     short loc_180039EAB
0x180039e8d  call    cs:__imp_GetLastError
0x180039e93  mov     ebx, eax
0x180039e95  test    eax, eax
0x180039e97  jle     short loc_180039E9E
0x180039e99  movzx   ebx, ax
0x180039e9c  or      ebx, esi
0x180039e9e  test    ebx, ebx
0x180039ea0  jns     loc_180039FC1
0x180039ea6  jmp     loc_180039F44
0x180039eab  call    ?WaitForReadyMiscThread@CService@@IEAAJXZ; CService::WaitForReadyMiscThread(void)
0x180039eb0  mov     ebx, eax
0x180039eb2  test    eax, eax
0x180039eb4  jns     short loc_180039EC2
0x180039eb6  mov     r8d, eax
0x180039eb9  lea     rdx, aWaitforreadymi; "WaitForReadyMiscThread failed: 0x%x in "...
0x180039ec0  jmp     short loc_180039F33
0x180039ec2  lea     rdx, [rsp+218h+var_1D0]; struct _GUID *
0x180039ec7  call    ?InitServer@CRCMModule@@QEAAJAEAU_GUID@@@Z; CRCMModule::InitServer(_GUID &)
0x180039ecc  mov     ebx, eax
0x180039ece  test    eax, eax
0x180039ed0  jns     short loc_180039EDE
0x180039ed2  mov     r8d, eax
0x180039ed5  lea     rdx, aAtlmoduleInits; "_AtlModule.InitServer failed: 0x%x in %"...
0x180039edc  jmp     short loc_180039F33
0x180039ede  mov     rax, cs:qword_180128740
0x180039ee5  lea     r9, ?staticStopServiceCallback@CService@@KAXPEAXE@Z; CService::staticStopServiceCallback(void *,uchar)
0x180039eec  mov     r8, cs:qword_180128750
0x180039ef3  lea     rdx, ?SERVICE_NAME@CService@@1QBGB; "TermService"
0x180039efa  mov     dword ptr [rsp+218h+lpThreadId], 8
0x180039f02  lea     rcx, qword_180128748
0x180039f09  mov     qword ptr [rsp+218h+dwCreationFlags], r14
0x180039f0e  mov     rax, [rax+0C0h]
0x180039f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f1a  mov     ebx, eax
0x180039f1c  test    eax, eax
0x180039f1e  jle     short loc_180039F25
0x180039f20  movzx   ebx, ax
0x180039f23  or      ebx, esi
0x180039f25  test    ebx, ebx
0x180039f27  jns     short loc_180039F4E
0x180039f29  lea     rdx, aSvcsglobalsReg; "svcsGlobals->RegisterStopCallback faile"...
0x180039f30  mov     r8d, ebx
0x180039f33  lea     r9, aCserviceStart; "CService::Start"
0x180039f3a  mov     ecx, 8; int
0x180039f3f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039f44  mov     rcx, r14; this
0x180039f47  call    ?Shutdown@CService@@IEAAXXZ; CService::Shutdown(void)
0x180039f4c  jmp     short loc_180039FC1
0x180039f4e  xor     r9d, r9d; unsigned int
0x180039f51  mov     [rsp+218h+dwCreationFlags], 0; unsigned int
0x180039f59  mov     rcx, r14; this
0x180039f5c  lea     edx, [r9+4]; unsigned int
0x180039f60  call    ?UpdateServiceStatus@CService@@IEAAHKKKK@Z; CService::UpdateServiceStatus(ulong,ulong,ulong,ulong)
0x180039f65  mov     edx, 1; int
0x180039f6a  mov     rcx, r14; this
0x180039f6d  call    ?Advertise@CService@@IEAAJH@Z; CService::Advertise(int)
0x180039f72  xor     edx, edx; Val
0x180039f74  lea     rcx, [rsp+218h+WSAData]; void *
0x180039f79  mov     r8d, 198h; Size
0x180039f7f  call    memset_0
0x180039f84  mov     ecx, 202h; wVersionRequested
0x180039f89  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x180039f8e  call    cs:__imp_WSAStartup
0x180039f94  test    eax, eax
0x180039f96  jle     short loc_180039F9F
0x180039f98  movzx   eax, ax
0x180039f9b  or      eax, esi
0x180039f9d  test    eax, eax
0x180039f9f  jns     short loc_180039FB7
0x180039fa1  mov     r8d, eax
0x180039fa4  lea     rdx, aWsastartupFail; "WSAStartup Failed: 0x%x"
0x180039fab  mov     ecx, 4; int
0x180039fb0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039fb5  jmp     short loc_180039FC1
0x180039fb7  mov     cs:?_Service@@3VCService@@A, 1; CService _Service
0x180039fc1  mov     eax, ebx
0x180039fc3  mov     rcx, [rsp+218h+var_18]
0x180039fcb  xor     rcx, rsp; StackCookie
0x180039fce  call    __security_check_cookie
0x180039fd3  lea     r11, [rsp+218h+var_8]
0x180039fdb  mov     rbx, [r11+10h]
0x180039fdf  mov     rsi, [r11+18h]
0x180039fe3  mov     rsp, r11
0x180039fe6  pop     r14
0x180039fe8  retn
```
