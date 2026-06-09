# GetTargetsForRequest(ushort const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>> &)

- ea: `0x180038e80`
- end: `0x1800390df`
- name: `?GetTargetsForRequest@@YAJPEBGAEAV?$ComPtr@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038194`

## callees

- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18001a0d0`
- `0x18002ae68`
- `0x18002f2b0`
- `0x180037c98`
- `0x180037ce4`
- `0x180037d30`
- `0x180038e80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039000`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039014`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039014`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038f9f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038f9f`

## string_xrefs

- `0x180038f75`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x180038f2e`: `hr = Vector<OnlineIdServiceTicketRequest*>::Make(&spTargets)`
- `0x180038fac`: `hr = GetActivationFactory( StringReference(RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest).Get(), &spOnlineIdServiceTicketRequestFactory)`
- `0x18003904a`: `hr = spOnlineIdServiceTicketRequestFactory->CreateOnlineIdServiceTicketRequest( StringReference(PPCRL_LOGIN_PROOF_TOKEN_URI).Get(), StringReference(pPolicy).Get(), &spOnlineIdServiceTicketRequest)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetTargetsForRequest(PCWSTR sourceString, _QWORD *a2)
{
  __int64 v4; // rcx
  int ActivationFactory; // eax
  const char *v6; // rcx
  unsigned int v7; // r8d
  int v8; // r9d
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, HSTRING, __int64 *); // r15
  unsigned __int64 v12; // rcx
  HSTRING v13; // rbx
  _QWORD *v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  char *v18; // [rsp+20h] [rbp-89h]
  char *v19; // [rsp+20h] [rbp-89h]
  int v20; // [rsp+30h] [rbp-79h] BYREF
  UINT32 length; // [rsp+34h] [rbp-75h] BYREF
  __int64 v22; // [rsp+38h] [rbp-71h] BYREF
  __int64 v23; // [rsp+40h] [rbp-69h] BYREF
  int *v24[4]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v25[4]; // [rsp+68h] [rbp-41h] BYREF
  HSTRING string; // [rsp+88h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-19h] BYREF
  HSTRING v28; // [rsp+A8h] [rbp-1h] BYREF

  v20 = 0;
  v25[0] = "GetTargetsForRequest";
  v25[1] = &v20;
  v25[2] = 0;
  v25[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "GetTargetsForRequest",
    (const char *)0x3F,
    0,
    (const unsigned __int16 *)v18);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v24, "GetTargetsForRequest", &v20, 0xAu, &qword_18006BBB0);
  v23 = 0;
  v22 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  ActivationFactory = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(
                        v4,
                        a2);
  v20 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v6 = "hr = Vector<OnlineIdServiceTicketRequest*>::Make(&spTargets)";
    v7 = 73;
LABEL_3:
    v8 = ActivationFactory;
    v19 = (char *)v6;
LABEL_4:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
      "GetTargetsForRequest",
      v7,
      v8,
      v19);
    goto LABEL_17;
  }
  if ( !*a2 )
  {
    v8 = -2147024882;
    v20 = -2147024882;
    v19 = "hr = E_OUTOFMEMORY";
    v7 = 76;
    goto LABEL_4;
  }
  v9 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                    &string,
                    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest");
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  ActivationFactory = RoGetActivationFactory(v9, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v22);
  v20 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v6 = "hr = GetActivationFactory( StringReference(RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServic"
         "eTicketRequest).Get(), &spOnlineIdServiceTicketRequestFactory)";
    v7 = 81;
    goto LABEL_3;
  }
  v10 = v22;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v22 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  length = 0;
  v12 = -1;
  do
    ++v12;
  while ( sourceString[v12] );
  if ( (int)ULongLongToUInt(v12, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(sourceString, length, &hstringHeader, &string);
  v13 = string;
  v14 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v28, L"http://Passport.NET/purpose");
  v15 = v11(v10, *v14, v13, &v23);
  v20 = v15;
  if ( v15 >= 0 )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 104LL))(*a2, v23);
  else
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
      "GetTargetsForRequest",
      0x56u,
      v15,
      "hr = spOnlineIdServiceTicketRequestFactory->CreateOnlineIdServiceTicketRequest( StringReference(PPCRL_LOGIN_PROOF_"
      "TOKEN_URI).Get(), StringReference(pPolicy).Get(), &spOnlineIdServiceTicketRequest)");
LABEL_17:
  v16 = v20;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  ErrorVerifier::CheckAgainstList((const char *)v24[3], *v24[2], (unsigned __int64)v24[1], v24[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v25);
  return v16;
}

```

## disassembly

```asm
0x180038e80  mov     [rsp-8+arg_10], rbx
0x180038e85  push    rbp
0x180038e86  push    rsi
0x180038e87  push    rdi
0x180038e88  push    r12
0x180038e8a  push    r13
0x180038e8c  push    r14
0x180038e8e  push    r15
0x180038e90  lea     rbp, [rsp-27h]
0x180038e95  sub     rsp, 0D0h
0x180038e9c  mov     rax, cs:__security_cookie
0x180038ea3  xor     rax, rsp
0x180038ea6  mov     [rbp+57h+var_38], rax
0x180038eaa  mov     rdi, rdx
0x180038ead  mov     r14, rcx
0x180038eb0  xor     r12d, r12d
0x180038eb3  mov     [rbp+57h+var_D0], r12d
0x180038eb7  lea     r13, aGettargetsforr; "GetTargetsForRequest"
0x180038ebe  mov     [rbp+57h+var_98], r13
0x180038ec2  lea     rax, [rbp+57h+var_D0]
0x180038ec6  mov     [rbp+57h+var_90], rax
0x180038eca  mov     [rbp+57h+var_88], r12
0x180038ece  mov     [rbp+57h+var_80], r12
0x180038ed2  xor     r9d, r9d; unsigned int
0x180038ed5  lea     r8d, [r12+3Fh]; char *
0x180038eda  mov     rdx, r13; char *
0x180038edd  lea     rsi, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180038ee4  mov     rcx, rsi; this
0x180038ee7  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180038eec  nop
0x180038eed  lea     rax, qword_18006BBB0
0x180038ef4  mov     [rsp+100h+var_E0], rax; int *
0x180038ef9  lea     r9d, [r12+0Ah]; unsigned __int64
0x180038efe  lea     r8, [rbp+57h+var_D0]; int *
0x180038f02  mov     rdx, r13; char *
0x180038f05  lea     rcx, [rbp+57h+var_B8]; this
0x180038f09  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180038f0e  nop
0x180038f0f  mov     [rbp+57h+var_C0], r12
0x180038f13  mov     [rbp+57h+var_C8], r12
0x180038f17  mov     rcx, rdi
0x180038f1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038f1f  mov     rdx, rdi
0x180038f22  call    ??$CreateExternalObjectVector@VOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest,Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>> * *)
0x180038f27  mov     [rbp+57h+var_D0], eax
0x180038f2a  test    eax, eax
0x180038f2c  jns     short loc_180038F52
0x180038f2e  lea     rcx, aHrVectorOnline; "hr = Vector<OnlineIdServiceTicketReques"...
0x180038f35  lea     r8d, [r12+49h]; unsigned int
0x180038f3a  mov     r9d, eax; int
0x180038f3d  mov     [rsp+100h+var_E0], rcx; char *
0x180038f42  mov     rcx, rsi; char *
0x180038f45  mov     rdx, r13; char *
0x180038f48  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180038f4d  jmp     loc_18003907E
0x180038f52  cmp     [rdi], r12
0x180038f55  jnz     short loc_180038F75
0x180038f57  mov     r9d, 8007000Eh
0x180038f5d  mov     [rbp+57h+var_D0], r9d
0x180038f61  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180038f68  mov     [rsp+100h+var_E0], rax
0x180038f6d  mov     r8d, 4Ch ; 'L'
0x180038f73  jmp     short loc_180038F42
0x180038f75  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x180038f7c  lea     rcx, [rbp+57h+string]; string
0x180038f80  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x180038f85  mov     rbx, [rax]
0x180038f88  lea     rcx, [rbp+57h+var_C8]
0x180038f8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038f91  lea     r8, [rbp+57h+var_C8]
0x180038f95  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180038f9c  mov     rcx, rbx
0x180038f9f  call    cs:__imp_RoGetActivationFactory
0x180038fa5  mov     [rbp+57h+var_D0], eax
0x180038fa8  test    eax, eax
0x180038faa  jns     short loc_180038FBE
0x180038fac  lea     rcx, aHrGetactivatio; "hr = GetActivationFactory( StringRefere"...
0x180038fb3  mov     r8d, 51h ; 'Q'
0x180038fb9  jmp     loc_180038F3A
0x180038fbe  mov     rsi, [rbp+57h+var_C8]
0x180038fc2  mov     rax, [rsi]
0x180038fc5  mov     r15, [rax+30h]
0x180038fc9  lea     rcx, [rbp+57h+var_C0]
0x180038fcd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038fd2  mov     [rbp+57h+length], r12d
0x180038fd6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180038fda  inc     rcx; unsigned __int64
0x180038fdd  cmp     [r14+rcx*2], r12w
0x180038fe2  jnz     short loc_180038FDA
0x180038fe4  lea     rdx, [rbp+57h+length]; unsigned int *
0x180038fe8  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180038fed  test    eax, eax
0x180038fef  jns     short loc_180039006
0x180038ff1  xor     r9d, r9d; lpArguments
0x180038ff4  xor     r8d, r8d; nNumberOfArguments
0x180038ff7  lea     edx, [r9+1]; dwExceptionFlags
0x180038ffb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180039000  call    cs:__imp_RaiseException
0x180039006  lea     r9, [rbp+57h+string]; string
0x18003900a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003900e  mov     edx, [rbp+57h+length]; length
0x180039011  mov     rcx, r14; sourceString
0x180039014  call    cs:__imp_WindowsCreateStringReference
0x18003901a  mov     rbx, [rbp+57h+string]
0x18003901e  lea     rdx, aHttpPassportNe; "http://Passport.NET/purpose"
0x180039025  lea     rcx, [rbp+57h+var_58]; string
0x180039029  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18003902e  lea     r9, [rbp+57h+var_C0]
0x180039032  mov     r8, rbx
0x180039035  mov     rdx, [rax]
0x180039038  mov     rcx, rsi
0x18003903b  mov     rax, r15
0x18003903e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039043  mov     [rbp+57h+var_D0], eax
0x180039046  test    eax, eax
0x180039048  jns     short loc_18003906B
0x18003904a  lea     rcx, aHrSponlineidse; "hr = spOnlineIdServiceTicketRequestFact"...
0x180039051  mov     [rsp+100h+var_E0], rcx
0x180039056  mov     r9d, eax
0x180039059  mov     r8d, 56h ; 'V'
0x18003905f  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180039066  jmp     loc_180038F45
0x18003906b  mov     rcx, [rdi]
0x18003906e  mov     rax, [rcx]
0x180039071  mov     rdx, [rbp+57h+var_C0]
0x180039075  mov     rax, [rax+68h]
0x180039079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003907e  mov     ebx, [rbp+57h+var_D0]
0x180039081  lea     rcx, [rbp+57h+var_C8]
0x180039085  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003908a  nop
0x18003908b  lea     rcx, [rbp+57h+var_C0]
0x18003908f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039094  nop
0x180039095  mov     r9, [rbp+57h+var_B8]; int *
0x180039099  mov     r8, [rbp+57h+var_B0]; unsigned __int64
0x18003909d  mov     rdx, [rbp+57h+var_A8]
0x1800390a1  mov     edx, [rdx]; int
0x1800390a3  mov     rcx, [rbp+57h+var_A0]; char *
0x1800390a7  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x1800390ac  nop
0x1800390ad  lea     rcx, [rbp+57h+var_98]
0x1800390b1  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800390b6  mov     eax, ebx
0x1800390b8  mov     rcx, [rbp+57h+var_38]
0x1800390bc  xor     rcx, rsp; StackCookie
0x1800390bf  call    __security_check_cookie
0x1800390c4  mov     rbx, [rsp+100h+arg_10]
0x1800390cc  add     rsp, 0D0h
0x1800390d3  pop     r15
0x1800390d5  pop     r14
0x1800390d7  pop     r13
0x1800390d9  pop     r12
0x1800390db  pop     rdi
0x1800390dc  pop     rsi
0x1800390dd  pop     rbp
0x1800390de  retn
```
