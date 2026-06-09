# CnsPayloadProvider::GetCnsFlightPayloadFromKvp(PushNotificationPayload &,PushNotificationAppToRefresh &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *>>,CnsFlightPayload &,bool &)

- ea: `0x180048968`
- end: `0x180048aaf`
- name: `?GetCnsFlightPayloadFromKvp@CnsPayloadProvider@@CAJAEAUPushNotificationPayload@@AEAUPushNotificationAppToRefresh@@V?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUCnsFlightPayload@@AEA_N@Z`
- size: `327`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048d84`

## callees

- `0x180005f50`
- `0x180009fcc`
- `0x1800101fc`
- `0x18004879c`
- `0x180048968`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800489a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048a1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CnsPayloadProvider::GetCnsFlightPayloadFromKvp(
        __int64 a1,
        __int64 a2,
        __int64 **a3,
        __int64 a4,
        __int64 a5)
{
  __int64 *v9; // rdi
  __int64 (__fastcall *v10)(__int64 *, HSTRING *); // rbx
  int v11; // eax
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int CnsFlightPayload; // ebx
  int v18; // [rsp+20h] [rbp-30h]
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h] BYREF
  __int64 v21; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  string = 0;
  v9 = *a3;
  v10 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(**a3 + 48);
  WindowsDeleteString(0);
  string = 0;
  v11 = v10(v9, &string);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v11,
      v18);
  v20 = 0;
  v12 = *a3;
  v13 = **a3;
  v20 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v13 + 56))(v12, &v20);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v14,
      v18);
  v21 = v20;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  CnsFlightPayload = CnsPayloadProvider::GetCnsFlightPayload(a1, a2, StringRawBuffer, &v21, a4, a5);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v20);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  return CnsFlightPayload;
}

```

## disassembly

```asm
0x180048968  mov     [rsp-28h+arg_0], rbx
0x18004896d  mov     [rsp-28h+arg_8], rsi
0x180048972  mov     [rsp-28h+arg_10], r8
0x180048977  push    rbp
0x180048978  push    rdi
0x180048979  push    r12
0x18004897b  push    r14
0x18004897d  push    r15
0x18004897f  mov     rbp, rsp
0x180048982  sub     rsp, 50h
0x180048986  mov     r14, r9
0x180048989  mov     rsi, r8
0x18004898c  mov     r15, rdx
0x18004898f  mov     r12, rcx
0x180048992  mov     [rbp+string], 0
0x18004899a  mov     rdi, [r8]
0x18004899d  mov     rax, [rdi]
0x1800489a0  mov     rbx, [rax+30h]
0x1800489a4  xor     ecx, ecx; string
0x1800489a6  call    cs:__imp_WindowsDeleteString
0x1800489ac  mov     [rbp+string], 0
0x1800489b4  lea     rdx, [rbp+string]
0x1800489b8  mov     rcx, rdi
0x1800489bb  mov     rax, rbx
0x1800489be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489c3  mov     rcx, [rbp+28h]; this
0x1800489c7  test    eax, eax
0x1800489c9  js      loc_180048A9A
0x1800489cf  mov     [rbp+var_18], 0
0x1800489d7  mov     rcx, [rsi]
0x1800489da  mov     rax, [rcx]
0x1800489dd  mov     [rbp+var_18], 0
0x1800489e5  lea     rdx, [rbp+var_18]
0x1800489e9  mov     rax, [rax+38h]
0x1800489ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489f2  mov     rcx, [rbp+28h]; this
0x1800489f6  test    eax, eax
0x1800489f8  js      loc_180048A85
0x1800489fe  mov     rcx, [rbp+var_18]
0x180048a02  mov     [rbp+var_10], rcx
0x180048a06  test    rcx, rcx
0x180048a09  jz      short loc_180048A18
0x180048a0b  mov     rax, [rcx]
0x180048a0e  mov     rax, [rax+8]
0x180048a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a17  nop
0x180048a18  xor     edx, edx; length
0x180048a1a  mov     rcx, [rbp+string]; string
0x180048a1e  call    cs:__imp_WindowsGetStringRawBuffer
0x180048a24  mov     rcx, [rbp+arg_20]
0x180048a28  mov     [rsp+50h+var_28], rcx
0x180048a2d  mov     [rsp+50h+var_30], r14
0x180048a32  lea     r9, [rbp+var_10]
0x180048a36  mov     r8, rax
0x180048a39  mov     rdx, r15
0x180048a3c  mov     rcx, r12
0x180048a3f  call    ?GetCnsFlightPayload@CnsPayloadProvider@@CAJAEAUPushNotificationPayload@@AEAUPushNotificationAppToRefresh@@PEBGV?$com_ptr_t@UIJsonValue@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUCnsFlightPayload@@AEA_N@Z; CnsPayloadProvider::GetCnsFlightPayload(PushNotificationPayload &,PushNotificationAppToRefresh &,ushort const *,wil::com_ptr_t<Windows::Data::Json::IJsonValue,wil::err_exception_policy>,CnsFlightPayload &,bool &)
0x180048a44  mov     ebx, eax
0x180048a46  lea     rcx, [rbp+var_18]
0x180048a4a  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048a4f  nop
0x180048a50  mov     rcx, [rbp+string]; string
0x180048a54  call    cs:__imp_WindowsDeleteString
0x180048a5a  mov     [rbp+string], 0
0x180048a62  mov     rcx, rsi
0x180048a65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048a6a  mov     eax, ebx
0x180048a6c  lea     r11, [rsp+50h+var_s0]
0x180048a71  mov     rbx, [r11+30h]
0x180048a75  mov     rsi, [r11+38h]
0x180048a79  mov     rsp, r11
0x180048a7c  pop     r15
0x180048a7e  pop     r14
0x180048a80  pop     r12
0x180048a82  pop     rdi
0x180048a83  pop     rbp
0x180048a84  retn
0x180048a85  mov     r9d, eax; char *
0x180048a88  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048a8f  mov     edx, 147h; void *
0x180048a94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048a9a  mov     r9d, eax; char *
0x180048a9d  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048aa4  mov     edx, 144h; void *
0x180048aa9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
