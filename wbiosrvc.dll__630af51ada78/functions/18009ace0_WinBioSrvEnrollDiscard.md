# WinBioSrvEnrollDiscard

- ea: `0x18009ace0`
- end: `0x18009b0f4`
- name: `WinBioSrvEnrollDiscard`
- size: `1044`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000b760`
- `0x18000f090`
- `0x18001434c`
- `0x18001d730`
- `0x18001fb04`
- `0x180020ca4`
- `0x180032f34`
- `0x180033798`
- `0x18003f2dc`
- `0x180043744`
- `0x180043d50`
- `0x180057da0`
- `0x180068f60`
- `0x18006963c`
- `0x18006e4c4`
- `0x18008b4a4`
- `0x1800914c4`
- `0x1800992bc`
- `0x180099478`
- `0x180099974`
- `0x18009ace0`
- `0x1800bb4f4`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ae5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ae5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18009ad9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18009ad9c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18009adb8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18009adb8`
- `RPCRT4!RpcServerTestCancel` at `0x18009ae8c`
- `RPCRT4!RpcServerTestCancel` at `0x18009ae8c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18009add6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18009add6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18009ade3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18009ade3`

## string_xrefs

- `0x18009ae20`: `onecore\ds\security\biometrics\service\server\winbiosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinBioSrvEnrollDiscard(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned __int64 v5; // rsi
  DWORD active; // eax
  int v7; // eax
  struct CBioTraceLogging *v8; // rbx
  __int64 v9; // rax
  void *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rdx
  const char *v14; // r9
  int v15; // [rsp+20h] [rbp-E8h]
  __int64 v16; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD *v17; // [rsp+38h] [rbp-D0h] BYREF
  int v18; // [rsp+40h] [rbp-C8h] BYREF
  CClientSession *v19; // [rsp+48h] [rbp-C0h] BYREF
  std::_Ref_count_base *v20; // [rsp+50h] [rbp-B8h]
  __int64 v21; // [rsp+58h] [rbp-B0h] BYREF
  struct _FILETIME FileTime; // [rsp+60h] [rbp-A8h] BYREF
  void *phToken; // [rsp+68h] [rbp-A0h] BYREF
  std::_Ref_count_base *v24; // [rsp+70h] [rbp-98h]
  __int64 v25[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v26[2]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v27[32]; // [rsp+98h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-50h] BYREF
  char v29[24]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v25[0] = a1;
  v16 = _InterlockedExchange64(v25, 0);
  v18 = 0;
  strcpy(v29, "WinBioSrvEnrollDiscard");
  v26[0] = v29;
  v26[1] = &v18;
  lambda_44e9758a318855f03ab035f25c74b5ff_::operator()(v26);
  v18 = 1;
  v17 = v26;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    FileTime = 0;
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v5 = (unsigned __int64)FileTime;
    phToken = 0;
    active = WTSGetActiveConsoleSessionId();
    if ( WTSQueryUserToken(active, &phToken) )
    {
      v21 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v21,
        0);
      v7 = SHGetUserSid(phToken, &v21);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8A6,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
          (const char *)(unsigned int)v7,
          v15);
      v8 = CBioTraceLogging::Instance();
      v9 = std::wstring::wstring((__int64)v27, v21);
      CBioTraceLogging::SetCurrentUserSid(v8, v9);
      CloseHandle(phToken);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    }
    CBioTraceLogging::SendTelemetry(0, 0, 9, 2u, v5, 0);
  }
  if ( !RpcServerTestCancel(0) )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____::_WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____(&v17);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
  }
  CSessionManager::Find(&v19, a2);
  if ( !v19 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2147024890);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
LABEL_24:
    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____::_WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____(&v17);
    return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
  }
  if ( !a3 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2147467261);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    goto LABEL_24;
  }
  if ( (*((_BYTE *)v19 + 160) & 0x10) == 0 )
  {
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2147024891);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    goto LABEL_24;
  }
  if ( !BindingHelper::IsEnrolling((CClientSession *)((char *)v19 + 16)) )
  {
    *a3 = 0;
    CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861012);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    goto LABEL_24;
  }
  *a3 = CClientSession::EnrollmentUnitId(v19);
  try
  {
    v11 = operator new(0x58u);
    v25[1] = (__int64)v11;
    v12 = CClientSession::EnrollmentUnitId(v19);
    v13 = CWinBioSrvEnrollDiscard::CWinBioSrvEnrollDiscard(v11, &v16, &v19, v12);
    std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(&phToken, v13);
    CClientSession::ParentBsp(v19, &SystemTime);
    if ( *(_QWORD *)&SystemTime.wYear )
      (*(void (__fastcall **)(_QWORD, CClientSession **, void **))(**(_QWORD **)&SystemTime.wYear + 56LL))(
        *(_QWORD *)&SystemTime.wYear,
        &v19,
        &phToken);
    if ( *(_QWORD *)&SystemTime.wHour )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&SystemTime.wHour);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____::_WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____(&v17);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x8ED,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\winbiosrv.cpp",
      v14);
  }
  return CRpcAsyncStatePointer::CompleteRequest((CRpcAsyncStatePointer *)&v16, -2146861052);
}

```

## disassembly

```asm
0x18009ace0  mov     r11, rsp
0x18009ace3  mov     [r11+10h], rbx
0x18009ace7  push    rsi
0x18009ace8  push    rdi
0x18009ace9  push    r14
0x18009aceb  sub     rsp, 0F0h
0x18009acf2  mov     rax, cs:__security_cookie
0x18009acf9  xor     rax, rsp
0x18009acfc  mov     [rsp+108h+var_28], rax
0x18009ad04  mov     rdi, r8
0x18009ad07  mov     r14, rdx
0x18009ad0a  mov     [rsp+108h+var_90], rcx
0x18009ad0f  mov     [rsp+108h+var_D8], 0
0x18009ad18  xor     eax, eax
0x18009ad1a  xchg    rax, [rsp+108h+var_90]
0x18009ad1f  mov     [rsp+108h+var_D8], rax
0x18009ad24  mov     [rsp+108h+var_C8], 0
0x18009ad2c  movups  xmm0, xmmword ptr cs:aWinbiosrvenrol_0; "WinBioSrvEnrollDiscard"
0x18009ad33  movups  xmmword ptr [r11-40h], xmm0
0x18009ad38  movsd   xmm1, qword ptr cs:aWinbiosrvenrol_0+0Fh; "Discard"
0x18009ad40  movsd   qword ptr [r11-31h], xmm1
0x18009ad46  lea     rax, [r11-40h]
0x18009ad4a  mov     [r11-80h], rax
0x18009ad4e  lea     rax, [rsp+108h+var_C8]
0x18009ad53  mov     [r11-78h], rax
0x18009ad57  lea     rcx, [r11-80h]
0x18009ad5b  call    _lambda_44e9758a318855f03ab035f25c74b5ff___operator__
0x18009ad60  mov     [rsp+108h+var_C8], 1
0x18009ad68  lea     rax, [rsp+108h+var_80]
0x18009ad70  mov     [rsp+108h+var_D0], rax
0x18009ad75  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x18009ad7c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18009ad81  test    al, al
0x18009ad83  jz      loc_18009AE8A
0x18009ad89  xorps   xmm0, xmm0
0x18009ad8c  movups  xmmword ptr [rsp+108h+SystemTime.wYear], xmm0
0x18009ad94  lea     rcx, [rsp+108h+SystemTime]; lpSystemTime
0x18009ad9c  call    cs:__imp_GetSystemTime
0x18009ada2  mov     qword ptr [rsp+108h+FileTime.dwLowDateTime], 0
0x18009adab  lea     rdx, [rsp+108h+FileTime]; lpFileTime
0x18009adb0  lea     rcx, [rsp+108h+SystemTime]; lpSystemTime
0x18009adb8  call    cs:__imp_SystemTimeToFileTime
0x18009adbe  mov     esi, [rsp+108h+FileTime.dwHighDateTime]
0x18009adc2  shl     rsi, 20h
0x18009adc6  mov     eax, [rsp+108h+FileTime.dwLowDateTime]
0x18009adca  or      rsi, rax
0x18009adcd  mov     [rsp+108h+phToken], 0
0x18009add6  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18009addc  mov     ecx, eax; SessionId
0x18009adde  lea     rdx, [rsp+108h+phToken]; phToken
0x18009ade3  call    cs:__imp_WTSQueryUserToken
0x18009ade9  test    eax, eax
0x18009adeb  jz      short loc_18009AE6C
0x18009aded  mov     [rsp+108h+var_B0], 0
0x18009adf6  xor     edx, edx
0x18009adf8  lea     rcx, [rsp+108h+var_B0]
0x18009adfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009ae02  lea     rdx, [rsp+108h+var_B0]
0x18009ae07  mov     rcx, [rsp+108h+phToken]
0x18009ae0c  call    SHGetUserSid
0x18009ae11  mov     rcx, [rsp+108h]; this
0x18009ae19  test    eax, eax
0x18009ae1b  jns     short loc_18009AE31
0x18009ae1d  mov     r9d, eax; char *
0x18009ae20  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\biometrics\\serv"...
0x18009ae27  mov     edx, 8A6h; void *
0x18009ae2c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009ae31  call    ?Instance@CBioTraceLogging@@SAAEAV1@XZ; CBioTraceLogging::Instance(void)
0x18009ae36  mov     rbx, rax
0x18009ae39  mov     rdx, [rsp+108h+var_B0]
0x18009ae3e  lea     rcx, [rsp+108h+var_70]
0x18009ae46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009ae4b  mov     rdx, rax
0x18009ae4e  mov     rcx, rbx
0x18009ae51  call    ?SetCurrentUserSid@CBioTraceLogging@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBioTraceLogging::SetCurrentUserSid(std::wstring)
0x18009ae56  mov     rcx, [rsp+108h+phToken]; hObject
0x18009ae5b  call    cs:__imp_CloseHandle
0x18009ae61  nop
0x18009ae62  lea     rcx, [rsp+108h+var_B0]
0x18009ae67  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009ae6c  mov     [rsp+108h+var_E0], 0; int
0x18009ae74  mov     [rsp+108h+var_E8], rsi; unsigned __int64
0x18009ae79  xor     edx, edx; int
0x18009ae7b  xor     ecx, ecx; int
0x18009ae7d  lea     r9d, [rdx+2]; unsigned int
0x18009ae81  lea     r8d, [rdx+9]; int
0x18009ae85  call    ?SendTelemetry@CBioTraceLogging@@SAXJJHI_KH@Z; CBioTraceLogging::SendTelemetry(long,long,int,uint,unsigned __int64,int)
0x18009ae8a  xor     ecx, ecx; BindingHandle
0x18009ae8c  call    cs:__imp_RpcServerTestCancel
0x18009ae92  test    eax, eax
0x18009ae94  jnz     short loc_18009AEE5
0x18009ae96  mov     edx, 80098004h; int
0x18009ae9b  lea     rcx, [rsp+108h+var_D8]; this
0x18009aea0  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009aea5  nop
0x18009aea6  lea     rcx, [rsp+108h+var_D0]
0x18009aeab  call    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff_______WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____
0x18009aeb0  nop
0x18009aeb1  mov     edx, 80098004h; int
0x18009aeb6  lea     rcx, [rsp+108h+var_D8]; this
0x18009aebb  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009aec0  nop
0x18009aec1  mov     rcx, [rsp+108h+var_28]
0x18009aec9  xor     rcx, rsp; StackCookie
0x18009aecc  call    __security_check_cookie
0x18009aed1  mov     rbx, [rsp+108h+arg_8]
0x18009aed9  add     rsp, 0F0h
0x18009aee0  pop     r14
0x18009aee2  pop     rdi
0x18009aee3  pop     rsi
0x18009aee4  retn
0x18009aee5  mov     rdx, r14
0x18009aee8  lea     rcx, [rsp+108h+var_C0]
0x18009aeed  call    ?Find@CSessionManager@@SA?AV?$shared_ptr@VCClientSession@@@std@@PEAX@Z; CSessionManager::Find(void *)
0x18009aef2  nop
0x18009aef3  mov     rcx, [rsp+108h+var_C0]
0x18009aef8  test    rcx, rcx
0x18009aefb  jnz     short loc_18009AF3A
0x18009aefd  mov     edx, 80070006h; int
0x18009af02  lea     rcx, [rsp+108h+var_D8]; this
0x18009af07  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009af0c  nop
0x18009af0d  mov     rcx, [rsp+108h+var_B8]; this
0x18009af12  test    rcx, rcx
0x18009af15  jz      short loc_18009AF1D
0x18009af17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009af1c  nop
0x18009af1d  lea     rcx, [rsp+108h+var_D0]
0x18009af22  call    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff_______WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____
0x18009af27  nop
0x18009af28  mov     edx, 80098004h; int
0x18009af2d  lea     rcx, [rsp+108h+var_D8]; this
0x18009af32  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009af37  nop
0x18009af38  jmp     short loc_18009AEC1
0x18009af3a  test    rdi, rdi
0x18009af3d  jnz     short loc_18009AF7F
0x18009af3f  mov     edx, 80004003h; int
0x18009af44  lea     rcx, [rsp+108h+var_D8]; this
0x18009af49  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009af4e  nop
0x18009af4f  mov     rcx, [rsp+108h+var_B8]; this
0x18009af54  test    rcx, rcx
0x18009af57  jz      short loc_18009AF5F
0x18009af59  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009af5e  nop
0x18009af5f  lea     rcx, [rsp+108h+var_D0]
0x18009af64  call    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff_______WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____
0x18009af69  nop
0x18009af6a  mov     edx, 80098004h; int
0x18009af6f  lea     rcx, [rsp+108h+var_D8]; this
0x18009af74  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009af79  nop
0x18009af7a  jmp     loc_18009AEC1
0x18009af7f  test    byte ptr [rcx+0A0h], 10h
0x18009af86  jnz     short loc_18009AFC8
0x18009af88  mov     edx, 80070005h; int
0x18009af8d  lea     rcx, [rsp+108h+var_D8]; this
0x18009af92  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009af97  nop
0x18009af98  mov     rcx, [rsp+108h+var_B8]; this
0x18009af9d  test    rcx, rcx
0x18009afa0  jz      short loc_18009AFA8
0x18009afa2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009afa7  nop
0x18009afa8  lea     rcx, [rsp+108h+var_D0]
0x18009afad  call    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff_______WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____
0x18009afb2  nop
0x18009afb3  mov     edx, 80098004h; int
0x18009afb8  lea     rcx, [rsp+108h+var_D8]; this
0x18009afbd  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009afc2  nop
0x18009afc3  jmp     loc_18009AEC1
0x18009afc8  add     rcx, 10h; this
0x18009afcc  call    ?IsEnrolling@BindingHelper@@QEAA_NXZ; BindingHelper::IsEnrolling(void)
0x18009afd1  test    al, al
0x18009afd3  jnz     short loc_18009B01B
0x18009afd5  mov     dword ptr [rdi], 0
0x18009afdb  mov     edx, 8009802Ch; int
0x18009afe0  lea     rcx, [rsp+108h+var_D8]; this
0x18009afe5  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009afea  nop
0x18009afeb  mov     rcx, [rsp+108h+var_B8]; this
0x18009aff0  test    rcx, rcx
0x18009aff3  jz      short loc_18009AFFB
0x18009aff5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009affa  nop
0x18009affb  lea     rcx, [rsp+108h+var_D0]
0x18009b000  call    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff_______WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____
0x18009b005  nop
0x18009b006  mov     edx, 80098004h; int
0x18009b00b  lea     rcx, [rsp+108h+var_D8]; this
0x18009b010  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009b015  nop
0x18009b016  jmp     loc_18009AEC1
0x18009b01b  mov     rcx, [rsp+108h+var_C0]; this
0x18009b020  call    ?EnrollmentUnitId@CClientSession@@QEAAKXZ; CClientSession::EnrollmentUnitId(void)
0x18009b025  mov     [rdi], eax
0x18009b027  mov     ecx, 58h ; 'X'; Size
0x18009b02c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009b031  mov     rbx, rax
0x18009b034  mov     [rsp+108h+var_88], rax
0x18009b03c  mov     rcx, [rsp+108h+var_C0]; this
0x18009b041  call    ?EnrollmentUnitId@CClientSession@@QEAAKXZ; CClientSession::EnrollmentUnitId(void)
0x18009b046  mov     r9d, eax
0x18009b049  lea     r8, [rsp+108h+var_C0]
0x18009b04e  lea     rdx, [rsp+108h+var_D8]
0x18009b053  mov     rcx, rbx
0x18009b056  call    ??0CWinBioSrvEnrollDiscard@@QEAA@AEAVCRpcAsyncStatePointer@@AEAV?$shared_ptr@VCClientSession@@@std@@K@Z; CWinBioSrvEnrollDiscard::CWinBioSrvEnrollDiscard(CRpcAsyncStatePointer &,std::shared_ptr<CClientSession> &,ulong)
0x18009b05b  nop
0x18009b05c  mov     rdx, rax
0x18009b05f  lea     rcx, [rsp+108h+phToken]
0x18009b064  call    ??$?0VCWinBioSrvEnrollDiscard@@$0A@@?$shared_ptr@VCAsyncWorkItem@@@std@@QEAA@PEAVCWinBioSrvEnrollDiscard@@@Z; std::shared_ptr<CAsyncWorkItem>::shared_ptr<CAsyncWorkItem>(CWinBioSrvEnrollDiscard *)
0x18009b069  nop
0x18009b06a  lea     rdx, [rsp+108h+SystemTime]
0x18009b072  mov     rcx, [rsp+108h+var_C0]
0x18009b077  call    ?ParentBsp@CClientSession@@QEAA?AV?$shared_ptr@VCBiometricServiceProvider@@@std@@XZ; CClientSession::ParentBsp(void)
0x18009b07c  nop
0x18009b07d  mov     rcx, qword ptr [rsp+108h+SystemTime.wYear]
0x18009b085  test    rcx, rcx
0x18009b088  jz      short loc_18009B0A1
0x18009b08a  mov     rax, [rcx]
0x18009b08d  lea     r8, [rsp+108h+phToken]
0x18009b092  lea     rdx, [rsp+108h+var_C0]
0x18009b097  mov     rax, [rax+38h]
0x18009b09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0a0  nop
0x18009b0a1  mov     rcx, qword ptr [rsp+108h+SystemTime.wHour]; this
0x18009b0a9  test    rcx, rcx
0x18009b0ac  jz      short loc_18009B0B4
0x18009b0ae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009b0b3  nop
0x18009b0b4  mov     rcx, [rsp+108h+var_98]; this
0x18009b0b9  test    rcx, rcx
0x18009b0bc  jz      short loc_18009B0C4
0x18009b0be  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009b0c3  nop
0x18009b0c4  mov     rcx, [rsp+108h+var_B8]; this
0x18009b0c9  test    rcx, rcx
0x18009b0cc  jz      short loc_18009B0D4
0x18009b0ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009b0d3  nop
0x18009b0d4  lea     rcx, [rsp+108h+var_D0]
0x18009b0d9  call    WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff_______WppTraceUnwinder__lambda_44e9758a318855f03ab035f25c74b5ff____
0x18009b0de  nop
0x18009b0df  mov     edx, 80098004h; int
0x18009b0e4  lea     rcx, [rsp+108h+var_D8]; this
0x18009b0e9  call    ?CompleteRequest@CRpcAsyncStatePointer@@QEAAJJ@Z; CRpcAsyncStatePointer::CompleteRequest(long)
0x18009b0ee  nop
0x18009b0ef  jmp     loc_18009AEC1
```
