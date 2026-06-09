# CService::Start(void)

- ea: `0x18003bc94`
- end: `0x18003c0e6`
- name: `?Start@CService@@QEAAJXZ`
- size: `1106`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b8e0`

## callees

- `0x180009940`
- `0x18001d530`
- `0x180027d34`
- `0x180030ad4`
- `0x180033f60`
- `0x180034e64`
- `0x18003b14c`
- `0x18003bbbc`
- `0x18003bc94`
- `0x18003c204`
- `0x18003c28c`
- `0x1800a235c`
- `0x1800a3074`
- `0x1800ce010`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18003bd58`
- `ntdll!EtwEventRegister` at `0x18003bd58`
- `ntdll!EtwEventUnregister` at `0x18003bd1f`
- `ntdll!EtwEventUnregister` at `0x18003bd1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003be48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003be96`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bed3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003be48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003be96`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003beae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003be65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003beae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bf7d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003bf65`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003bf65`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x18003bcb9`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x18003bcb9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18003bcf2`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18003bcf2`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003bf00`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003bf00`
- `WS2_32!__imp_WSAStartup` at `0x18003c084`
- `WS2_32!__imp_WSAStartup` at `0x18003c084`

## string_xrefs

- `0x18003c029`: `CService::Start`
- `0x18003be09`: `UpdateServiceStatus failed: 0x%x in %s`
- `0x18003be80`: `CreateEvent failed: 0x%x in %s`
- `0x18003bf32`: `RegisterServiceCtrlHandlerEx failed: %x`
- `0x18003bfaf`: `WaitForReadyMiscThread failed: 0x%x in %s`
- `0x18003bef9`: `TermService`
- `0x18003bfe9`: `TermService`

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
  if ( qword_180131B50 )
  {
    EtwEventUnregister();
    qword_180131B50 = 0;
  }
  CrimsonHelper::s_instance = S_TermService;
  if ( !(unsigned int)EtwEventRegister(&CrimsonHelper::s_instance, 0, 0, &qword_180131B50) )
    byte_180131B58 = 1;
  byte_180131B59 = 1;
  qword_180131B10 = (__int64)TRACE_INF;
  qword_180131B18 = (__int64)TRACE_WRN;
  qword_180131B30 = (__int64)TRACE_INF;
  qword_180131B20 = (__int64)TRACE_ERR;
  qword_180131B28 = (__int64)TRACE_FATAL;
  qword_180131B38 = (__int64)TRACE_ENT;
  qword_180131B40 = (__int64)TRACE_EXIT;
  qword_180131B48 = (__int64)TRACE_DUMP;
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
  qword_18012E758 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_18012E758 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_16;
  }
  qword_18012E768 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_18012E768 )
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
  qword_18012E750 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_18012E750 )
    goto LABEL_27;
  qword_18012E718 = (__int64)RegisterServiceCtrlHandlerExW(
                               L"TermService",
                               CService::staticServiceCtrlHandler,
                               &_Service);
  if ( !qword_18012E718 )
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
  v14 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, __int64, void (__fastcall *)(void *, unsigned __int8), void *, int))(qword_18012E740 + 192))(
          &qword_18012E748,
          L"TermService",
          qword_18012E750,
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
0x18003bc94  mov     [rsp+arg_0], rbx
0x18003bc99  mov     [rsp+arg_8], rsi
0x18003bc9e  push    r14
0x18003bca0  sub     rsp, 210h
0x18003bca7  mov     rax, cs:__security_cookie
0x18003bcae  xor     rax, rsp
0x18003bcb1  mov     [rsp+218h+var_18], rax
0x18003bcb9  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x18003bcc0  nop     dword ptr [rax+rax+00h]
0x18003bcc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TermsrvRedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TermsrvRedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TermsrvRedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_TermsrvRedirectionGuard>::GetImpl(void)'::`2'::impl
0x18003bccc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TermsrvRedirectionGuard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TermsrvRedirectionGuard>::__private_IsEnabled(void)
0x18003bcd1  test    al, al
0x18003bcd3  jz      short loc_18003BCFE
0x18003bcd5  call    ?OptOutTermsrvRedirectionGuard@CUtils@@SAHXZ; CUtils::OptOutTermsrvRedirectionGuard(void)
0x18003bcda  test    eax, eax
0x18003bcdc  jnz     short loc_18003BCFE
0x18003bcde  lea     r8d, [rax+4]
0x18003bce2  mov     [rsp+218h+var_1D8], 1
0x18003bcea  lea     rdx, [rsp+218h+var_1D8]
0x18003bcef  lea     ecx, [rax+10h]
0x18003bcf2  call    cs:__imp_SetProcessMitigationPolicy
0x18003bcf9  nop     dword ptr [rax+rax+00h]
0x18003bcfe  movups  xmm0, xmmword ptr cs:CLSID_RemoteConnectionManager.Data1
0x18003bd05  mov     rcx, cs:qword_180131B50
0x18003bd0c  mov     [rsp+218h+ThreadId], 0
0x18003bd14  movdqu  xmmword ptr [rsp+218h+var_1D0.Data1], xmm0
0x18003bd1a  test    rcx, rcx
0x18003bd1d  jz      short loc_18003BD36
0x18003bd1f  call    cs:__imp_EtwEventUnregister
0x18003bd26  nop     dword ptr [rax+rax+00h]
0x18003bd2b  mov     cs:qword_180131B50, 0
0x18003bd36  movups  xmm0, cs:S_TermService
0x18003bd3d  lea     r9, qword_180131B50
0x18003bd44  xor     r8d, r8d
0x18003bd47  xor     edx, edx
0x18003bd49  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18003bd50  movdqu  cs:?s_instance@CrimsonHelper@@0V1@A, xmm0; CrimsonHelper CrimsonHelper::s_instance
0x18003bd58  call    cs:__imp_EtwEventRegister
0x18003bd5f  nop     dword ptr [rax+rax+00h]
0x18003bd64  test    eax, eax
0x18003bd66  jnz     short loc_18003BD6F
0x18003bd68  mov     cs:byte_180131B58, 1
0x18003bd6f  lea     rcx, TRACE_INF
0x18003bd76  mov     cs:byte_180131B59, 1
0x18003bd7d  lea     rax, TRACE_WRN
0x18003bd84  mov     cs:qword_180131B10, rcx
0x18003bd8b  mov     cs:qword_180131B18, rax
0x18003bd92  lea     r14, ?_Service@@3VCService@@A; CService _Service
0x18003bd99  lea     rax, TRACE_ERR
0x18003bda0  mov     cs:qword_180131B30, rcx
0x18003bda7  mov     cs:qword_180131B20, rax
0x18003bdae  mov     edx, 2; unsigned int
0x18003bdb3  lea     rax, TRACE_FATAL
0x18003bdba  mov     [rsp+218h+dwCreationFlags], 0; unsigned int
0x18003bdc2  mov     cs:qword_180131B28, rax
0x18003bdc9  mov     rcx, r14; this
0x18003bdcc  lea     rax, TRACE_ENT
0x18003bdd3  mov     cs:qword_180131B38, rax
0x18003bdda  lea     r9d, [rdx-1]; unsigned int
0x18003bdde  lea     rax, TRACE_EXIT
0x18003bde5  mov     cs:qword_180131B40, rax
0x18003bdec  lea     rax, TRACE_DUMP
0x18003bdf3  mov     cs:qword_180131B48, rax
0x18003bdfa  call    ?UpdateServiceStatus@CService@@IEAAHKKKK@Z; CService::UpdateServiceStatus(ulong,ulong,ulong,ulong)
0x18003bdff  mov     ebx, eax
0x18003be01  or      ebx, 10000000h
0x18003be07  jge     short loc_18003BE15
0x18003be09  lea     rdx, aUpdateservices; "UpdateServiceStatus failed: 0x%x in %s"
0x18003be10  jmp     loc_18003C026
0x18003be15  call    ?Initialize@CUtils@@SAJXZ; CUtils::Initialize(void)
0x18003be1a  mov     ebx, eax
0x18003be1c  test    eax, eax
0x18003be1e  jns     short loc_18003BE39
0x18003be20  mov     r8d, eax
0x18003be23  lea     rdx, aCutilsInitiali_0; "CUtils::Initialize failed: 0x%x"
0x18003be2a  mov     ecx, 8; int
0x18003be2f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003be34  jmp     loc_18003C03A
0x18003be39  call    ?RegisterTraceLoggingProvider@@YAXXZ; RegisterTraceLoggingProvider(void)
0x18003be3e  xor     r9d, r9d; lpName
0x18003be41  xor     r8d, r8d; bInitialState
0x18003be44  xor     edx, edx; bManualReset
0x18003be46  xor     ecx, ecx; lpEventAttributes
0x18003be48  call    cs:__imp_CreateEventW
0x18003be4f  nop     dword ptr [rax+rax+00h]
0x18003be54  mov     cs:qword_18012E758, rax
0x18003be5b  mov     esi, 80070000h
0x18003be60  test    rax, rax
0x18003be63  jnz     short loc_18003BE8C
0x18003be65  call    cs:__imp_GetLastError
0x18003be6c  nop     dword ptr [rax+rax+00h]
0x18003be71  mov     ebx, eax
0x18003be73  test    eax, eax
0x18003be75  jle     short loc_18003BE7C
0x18003be77  movzx   ebx, ax
0x18003be7a  or      ebx, esi
0x18003be7c  test    ebx, ebx
0x18003be7e  jns     short loc_18003BE8C
0x18003be80  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18003be87  jmp     loc_18003C026
0x18003be8c  xor     r9d, r9d; lpName
0x18003be8f  xor     r8d, r8d; bInitialState
0x18003be92  xor     edx, edx; bManualReset
0x18003be94  xor     ecx, ecx; lpEventAttributes
0x18003be96  call    cs:__imp_CreateEventW
0x18003be9d  nop     dword ptr [rax+rax+00h]
0x18003bea2  mov     cs:qword_18012E768, rax
0x18003bea9  test    rax, rax
0x18003beac  jnz     short loc_18003BEC9
0x18003beae  call    cs:__imp_GetLastError
0x18003beb5  nop     dword ptr [rax+rax+00h]
0x18003beba  mov     ebx, eax
0x18003bebc  test    eax, eax
0x18003bebe  jle     short loc_18003BEC5
0x18003bec0  movzx   ebx, ax
0x18003bec3  or      ebx, esi
0x18003bec5  test    ebx, ebx
0x18003bec7  js      short loc_18003BE80
0x18003bec9  xor     r9d, r9d; lpName
0x18003becc  xor     r8d, r8d; bInitialState
0x18003becf  xor     edx, edx; bManualReset
0x18003bed1  xor     ecx, ecx; lpEventAttributes
0x18003bed3  call    cs:__imp_CreateEventW
0x18003beda  nop     dword ptr [rax+rax+00h]
0x18003bedf  mov     cs:qword_18012E750, rax
0x18003bee6  test    rax, rax
0x18003bee9  jz      loc_18003BF7D
0x18003beef  mov     r8, r14; lpContext
0x18003bef2  lea     rdx, ?staticServiceCtrlHandler@CService@@KAKKKPEAX0@Z; lpHandlerProc
0x18003bef9  lea     rcx, ?SERVICE_NAME@CService@@1QBGB; "TermService"
0x18003bf00  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18003bf07  nop     dword ptr [rax+rax+00h]
0x18003bf0c  mov     cs:qword_18012E718, rax
0x18003bf13  test    rax, rax
0x18003bf16  jnz     short loc_18003BF45
0x18003bf18  call    cs:__imp_GetLastError
0x18003bf1f  nop     dword ptr [rax+rax+00h]
0x18003bf24  mov     ebx, eax
0x18003bf26  test    eax, eax
0x18003bf28  jle     short loc_18003BF2F
0x18003bf2a  movzx   ebx, ax
0x18003bf2d  or      ebx, esi
0x18003bf2f  mov     r8d, ebx
0x18003bf32  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerEx failed: %x"
0x18003bf39  mov     ecx, 8; int
0x18003bf3e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003bf43  jmp     short loc_18003BF94
0x18003bf45  lea     rax, [rsp+218h+ThreadId]
0x18003bf4a  mov     r9, r14; lpParameter
0x18003bf4d  mov     [rsp+218h+lpThreadId], rax; lpThreadId
0x18003bf52  lea     r8, ?staticMiscThread@CService@@KAKPEAX@Z; lpStartAddress
0x18003bf59  xor     edx, edx; dwStackSize
0x18003bf5b  mov     [rsp+218h+dwCreationFlags], 0; dwCreationFlags
0x18003bf63  xor     ecx, ecx; lpThreadAttributes
0x18003bf65  call    cs:__imp_CreateThread
0x18003bf6c  nop     dword ptr [rax+rax+00h]
0x18003bf71  mov     cs:hThread, rax
0x18003bf78  test    rax, rax
0x18003bf7b  jnz     short loc_18003BFA1
0x18003bf7d  call    cs:__imp_GetLastError
0x18003bf84  nop     dword ptr [rax+rax+00h]
0x18003bf89  mov     ebx, eax
0x18003bf8b  test    eax, eax
0x18003bf8d  jle     short loc_18003BF94
0x18003bf8f  movzx   ebx, ax
0x18003bf92  or      ebx, esi
0x18003bf94  test    ebx, ebx
0x18003bf96  jns     loc_18003C0BD
0x18003bf9c  jmp     loc_18003C03A
0x18003bfa1  call    ?WaitForReadyMiscThread@CService@@IEAAJXZ; CService::WaitForReadyMiscThread(void)
0x18003bfa6  mov     ebx, eax
0x18003bfa8  test    eax, eax
0x18003bfaa  jns     short loc_18003BFB8
0x18003bfac  mov     r8d, eax
0x18003bfaf  lea     rdx, aWaitforreadymi; "WaitForReadyMiscThread failed: 0x%x in "...
0x18003bfb6  jmp     short loc_18003C029
0x18003bfb8  lea     rdx, [rsp+218h+var_1D0]; struct _GUID *
0x18003bfbd  call    ?InitServer@CRCMModule@@QEAAJAEAU_GUID@@@Z; CRCMModule::InitServer(_GUID &)
0x18003bfc2  mov     ebx, eax
0x18003bfc4  test    eax, eax
0x18003bfc6  jns     short loc_18003BFD4
0x18003bfc8  mov     r8d, eax
0x18003bfcb  lea     rdx, aAtlmoduleInits; "_AtlModule.InitServer failed: 0x%x in %"...
0x18003bfd2  jmp     short loc_18003C029
0x18003bfd4  mov     rax, cs:qword_18012E740
0x18003bfdb  lea     r9, ?staticStopServiceCallback@CService@@KAXPEAXE@Z; CService::staticStopServiceCallback(void *,uchar)
0x18003bfe2  mov     r8, cs:qword_18012E750
0x18003bfe9  lea     rdx, ?SERVICE_NAME@CService@@1QBGB; "TermService"
0x18003bff0  mov     dword ptr [rsp+218h+lpThreadId], 8
0x18003bff8  lea     rcx, qword_18012E748
0x18003bfff  mov     qword ptr [rsp+218h+dwCreationFlags], r14
0x18003c004  mov     rax, [rax+0C0h]
0x18003c00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c010  mov     ebx, eax
0x18003c012  test    eax, eax
0x18003c014  jle     short loc_18003C01B
0x18003c016  movzx   ebx, ax
0x18003c019  or      ebx, esi
0x18003c01b  test    ebx, ebx
0x18003c01d  jns     short loc_18003C044
0x18003c01f  lea     rdx, aSvcsglobalsReg; "svcsGlobals->RegisterStopCallback faile"...
0x18003c026  mov     r8d, ebx
0x18003c029  lea     r9, aCserviceStart; "CService::Start"
0x18003c030  mov     ecx, 8; int
0x18003c035  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003c03a  mov     rcx, r14; this
0x18003c03d  call    ?Shutdown@CService@@IEAAXXZ; CService::Shutdown(void)
0x18003c042  jmp     short loc_18003C0BD
0x18003c044  xor     r9d, r9d; unsigned int
0x18003c047  mov     [rsp+218h+dwCreationFlags], 0; unsigned int
0x18003c04f  mov     rcx, r14; this
0x18003c052  lea     edx, [r9+4]; unsigned int
0x18003c056  call    ?UpdateServiceStatus@CService@@IEAAHKKKK@Z; CService::UpdateServiceStatus(ulong,ulong,ulong,ulong)
0x18003c05b  mov     edx, 1; int
0x18003c060  mov     rcx, r14; this
0x18003c063  call    ?Advertise@CService@@IEAAJH@Z; CService::Advertise(int)
0x18003c068  xor     edx, edx; Val
0x18003c06a  lea     rcx, [rsp+218h+WSAData]; void *
0x18003c06f  mov     r8d, 198h; Size
0x18003c075  call    memset_0
0x18003c07a  mov     ecx, 202h; wVersionRequested
0x18003c07f  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x18003c084  call    cs:__imp_WSAStartup
0x18003c08b  nop     dword ptr [rax+rax+00h]
0x18003c090  test    eax, eax
0x18003c092  jle     short loc_18003C09B
0x18003c094  movzx   eax, ax
0x18003c097  or      eax, esi
0x18003c099  test    eax, eax
0x18003c09b  jns     short loc_18003C0B3
0x18003c09d  mov     r8d, eax
0x18003c0a0  lea     rdx, aWsastartupFail; "WSAStartup Failed: 0x%x"
0x18003c0a7  mov     ecx, 4; int
0x18003c0ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003c0b1  jmp     short loc_18003C0BD
0x18003c0b3  mov     cs:?_Service@@3VCService@@A, 1; CService _Service
0x18003c0bd  mov     eax, ebx
0x18003c0bf  mov     rcx, [rsp+218h+var_18]
0x18003c0c7  xor     rcx, rsp; StackCookie
0x18003c0ca  call    __security_check_cookie
0x18003c0cf  lea     r11, [rsp+218h+var_8]
0x18003c0d7  mov     rbx, [r11+10h]
0x18003c0db  mov     rsi, [r11+18h]
0x18003c0df  mov     rsp, r11
0x18003c0e2  pop     r14
0x18003c0e4  retn
```
