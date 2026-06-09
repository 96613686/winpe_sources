# CnsPayloadProvider::GetCnsFlightPayload(PushNotificationPayload &,PushNotificationAppToRefresh &,ushort const *,wil::com_ptr_t<Windows::Data::Json::IJsonValue,wil::err_exception_policy>,CnsFlightPayload &,bool &)

- ea: `0x18004879c`
- end: `0x180048960`
- name: `?GetCnsFlightPayload@CnsPayloadProvider@@CAJAEAUPushNotificationPayload@@AEAUPushNotificationAppToRefresh@@PEBGV?$com_ptr_t@UIJsonValue@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUCnsFlightPayload@@AEA_N@Z`
- size: `452`
- prototype: `__int64(__int64, __int64, __int64, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180048968`

## callees

- `0x180009fcc`
- `0x1800101fc`
- `0x180011a44`
- `0x180020748`
- `0x18002dc50`
- `0x180047e24`
- `0x18004879c`
- `0x180049968`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800488ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800488ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800488ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800488ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CnsPayloadProvider::GetCnsFlightPayload(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, ...)
{
  _BYTE *v6; // r12
  HSTRING v7; // r14
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  __int64 v22; // [rsp+60h] [rbp+40h] BYREF
  char v23; // [rsp+68h] [rbp+48h] BYREF
  _QWORD *v24; // [rsp+78h] [rbp+58h]
  HSTRING string; // [rsp+80h] [rbp+60h] BYREF
  va_list stringa; // [rsp+80h] [rbp+60h]
  _BYTE *v27; // [rsp+88h] [rbp+68h] BYREF
  va_list va1; // [rsp+88h] [rbp+68h]
  va_list va2; // [rsp+90h] [rbp+70h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(stringa, a4);
  string = va_arg(va1, HSTRING);
  va_copy(va2, va1);
  v27 = va_arg(va2, _BYTE *);
  v24 = a4;
  v6 = v27;
  *v27 = 0;
  v7 = string;
  *(_DWORD *)string = *(_DWORD *)(HSTRING)(a1 + 68);
  *(_QWORD *)(v7 + 1) = *(_QWORD *)(a1 + 72);
  std::wstring::operator=(v7 + 4);
  std::wstring::operator=(v7 + 12);
  LODWORD(v27) = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE **))(*(_QWORD *)*a4 + 48LL))(*a4, (_BYTE **)va1);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
  if ( (_DWORD)v27 == 5 )
  {
    v22 = 0;
    v9 = *a4;
    v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a4 + 96LL);
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(&v22);
    v11 = v10(v9, &v22);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v11,
        savedregs);
    string = 0;
    v12 = *a4;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a4 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, (HSTRING *)stringa);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v14,
        savedregs);
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(a3 + 2 * v16) );
    std::wstring::_Assign<unsigned short>(v7 + 20, a3);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    do
      ++v15;
    while ( StringRawBuffer[v15] );
    std::wstring::_Assign<unsigned short>(v7 + 36, StringRawBuffer);
    v18 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
            &v23,
            &v22);
    CnsPayloadProvider::SetCnsFlightVersionFromJson(v18, v7);
    *v6 = 1;
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v22);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(a4);
  return 0;
}

```

## disassembly

```asm
0x18004879c  mov     [rsp-38h+arg_10], rbx
0x1800487a1  mov     [rsp-38h+arg_18], r9
0x1800487a6  push    rbp
0x1800487a7  push    rsi
0x1800487a8  push    rdi
0x1800487a9  push    r12
0x1800487ab  push    r13
0x1800487ad  push    r14
0x1800487af  push    r15; int
0x1800487b1  mov     rbp, rsp
0x1800487b4  sub     rsp, 20h
0x1800487b8  mov     rsi, r9
0x1800487bb  mov     r15, r8
0x1800487be  mov     rbx, rdx
0x1800487c1  xor     r13d, r13d
0x1800487c4  mov     r12, [rbp+arg_28]
0x1800487c8  mov     [r12], r13b
0x1800487cc  mov     eax, [rcx+44h]
0x1800487cf  mov     r14, [rbp+string]
0x1800487d3  mov     [r14], eax
0x1800487d6  mov     rax, [rcx+48h]
0x1800487da  mov     [r14+4], rax
0x1800487de  lea     rcx, [r14+10h]
0x1800487e2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800487e7  lea     rdx, [rbx+20h]
0x1800487eb  lea     rcx, [r14+30h]
0x1800487ef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800487f4  mov     dword ptr [rbp+arg_28], r13d
0x1800487f8  mov     rcx, [rsi]
0x1800487fb  mov     rax, [rcx]
0x1800487fe  lea     rdx, [rbp+arg_28]
0x180048802  mov     rax, [rax+30h]
0x180048806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004880b  mov     rcx, [rbp+38h]; this
0x18004880f  test    eax, eax
0x180048811  js      loc_180048936
0x180048817  cmp     dword ptr [rbp+arg_28], 5
0x18004881b  jnz     loc_180048902
0x180048821  mov     [rbp+arg_0], r13
0x180048825  mov     rdi, [rsi]
0x180048828  mov     rax, [rdi]
0x18004882b  mov     rbx, [rax+60h]
0x18004882f  lea     rcx, [rbp+arg_0]
0x180048833  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x180048838  lea     rdx, [rbp+arg_0]
0x18004883c  mov     rcx, rdi
0x18004883f  mov     rax, rbx
0x180048842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048847  mov     rcx, [rbp+38h]; this
0x18004884b  test    eax, eax
0x18004884d  js      loc_18004894B
0x180048853  mov     [rbp+string], r13
0x180048857  mov     rdi, [rsi]
0x18004885a  mov     rax, [rdi]
0x18004885d  mov     rbx, [rax+38h]
0x180048861  xor     ecx, ecx; string
0x180048863  call    cs:__imp_WindowsDeleteString
0x180048869  mov     [rbp+string], r13
0x18004886d  lea     rdx, [rbp+string]
0x180048871  mov     rcx, rdi
0x180048874  mov     rax, rbx
0x180048877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004887c  mov     rcx, [rbp+38h]; this
0x180048880  test    eax, eax
0x180048882  js      loc_180048921
0x180048888  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004888c  mov     r8, rbx
0x18004888f  inc     r8
0x180048892  cmp     [r15+r8*2], r13w
0x180048897  jnz     short loc_18004888F
0x180048899  lea     rcx, [r14+50h]
0x18004889d  mov     rdx, r15
0x1800488a0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800488a5  xor     edx, edx; length
0x1800488a7  mov     rcx, [rbp+string]; string
0x1800488ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800488b1  inc     rbx
0x1800488b4  cmp     [rax+rbx*2], r13w
0x1800488b9  jnz     short loc_1800488B1
0x1800488bb  lea     rcx, [r14+90h]
0x1800488c2  mov     r8, rbx
0x1800488c5  mov     rdx, rax
0x1800488c8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800488cd  lea     rdx, [rbp+arg_0]
0x1800488d1  lea     rcx, [rbp+arg_8]
0x1800488d5  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x1800488da  mov     rdx, r14
0x1800488dd  mov     rcx, rax
0x1800488e0  call    ?SetCnsFlightVersionFromJson@CnsPayloadProvider@@CAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUCnsFlightPayload@@@Z; CnsPayloadProvider::SetCnsFlightVersionFromJson(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,CnsFlightPayload &)
0x1800488e5  mov     byte ptr [r12], 1
0x1800488ea  mov     rcx, [rbp+string]; string
0x1800488ee  call    cs:__imp_WindowsDeleteString
0x1800488f4  mov     [rbp+string], r13
0x1800488f8  lea     rcx, [rbp+arg_0]
0x1800488fc  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048901  nop
0x180048902  mov     rcx, rsi
0x180048905  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004890a  xor     eax, eax
0x18004890c  mov     rbx, [rsp+20h+arg_10]
0x180048911  add     rsp, 20h
0x180048915  pop     r15
0x180048917  pop     r14
0x180048919  pop     r13
0x18004891b  pop     r12
0x18004891d  pop     rdi
0x18004891e  pop     rsi
0x18004891f  pop     rbp
0x180048920  retn
0x180048921  mov     r9d, eax; char *
0x180048924  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x18004892b  mov     edx, 114h; void *
0x180048930  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048936  mov     r9d, eax; char *
0x180048939  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048940  mov     edx, 107h; void *
0x180048945  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004894b  mov     r9d, eax; char *
0x18004894e  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048955  mov     edx, 111h; void *
0x18004895a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
