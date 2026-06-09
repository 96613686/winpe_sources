# CnsPayloadProvider::GetCnsFlightVersionFromJson(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180048ab8`
- end: `0x180048cb6`
- name: `?GetCnsFlightVersionFromJson@CnsPayloadProvider@@CAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800482b4`
- `0x180049968`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x180009fcc`
- `0x18000e5ac`
- `0x1800101fc`
- `0x180011a44`
- `0x180020748`
- `0x180048ab8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048bc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048bc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180048c20`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CnsPayloadProvider::GetCnsFlightVersionFromJson(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v17; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // r8
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+28h] [rbp-48h] BYREF
  int v23; // [rsp+30h] [rbp-40h] BYREF
  __int64 v24[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER v25; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v24[1] = (__int64)a1;
  v22 = 0;
  v4 = *a1;
  v5 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)*a1 + 48LL);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
         &v25,
         (const WCHAR **)&CnsPayloadProvider::s_tagCnsHistory);
  v7 = v5(v4, v6[1].Reserved.Reserved1, &v22);
  v8 = v7;
  if ( v7 == -2089484279 )
    goto LABEL_11;
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v10 = 298;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)v9,
      (int)string);
    goto LABEL_15;
  }
  v23 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 48LL))(v22, &v23);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v11,
      (int)string);
  if ( v23 != 5 )
  {
    v8 = -2147418113;
    v9 = 2147549183LL;
    v10 = 304;
    goto LABEL_4;
  }
  v24[0] = 0;
  v12 = v22;
  v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 96LL);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(v24);
  v14 = v13(v12, v24);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
      (const char *)(unsigned int)v14,
      (int)string);
  string = 0;
  v15 = v24[0];
  v16 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v24[0] + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v25,
          (const WCHAR **)&CnsPayloadProvider::s_tagCnsFlightVersion);
  v8 = v16(v15, v17[1].Reserved.Reserved1, &string);
  if ( v8 == -2089484279 )
  {
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v24);
LABEL_11:
    v8 = 0;
    goto LABEL_15;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v19 = -1;
  do
    ++v19;
  while ( StringRawBuffer[v19] );
  std::wstring::_Assign<unsigned short>(a2, StringRawBuffer);
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v24);
LABEL_15:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v22);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(a1);
  return v8;
}

```

## disassembly

```asm
0x180048ab8  mov     [rsp-28h+arg_10], rbx
0x180048abd  push    rbp
0x180048abe  push    rsi
0x180048abf  push    rdi
0x180048ac0  push    r14
0x180048ac2  push    r15
0x180048ac4  mov     rbp, rsp
0x180048ac7  sub     rsp, 70h
0x180048acb  mov     rax, cs:__security_cookie
0x180048ad2  xor     rax, rsp
0x180048ad5  mov     [rbp+var_8], rax
0x180048ad9  mov     r14, rdx
0x180048adc  mov     rsi, rcx
0x180048adf  mov     [rbp+var_30], rcx
0x180048ae3  xor     r15d, r15d
0x180048ae6  mov     [rbp+var_48], r15
0x180048aea  mov     rdi, [rcx]
0x180048aed  mov     rax, [rdi]
0x180048af0  mov     rbx, [rax+30h]
0x180048af4  mov     [rbp+var_48], r15
0x180048af8  lea     rdx, ?s_tagCnsHistory@CnsPayloadProvider@@0QEBGEB; ushort const * const CnsPayloadProvider::s_tagCnsHistory
0x180048aff  lea     rcx, [rbp+var_28]
0x180048b03  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180048b08  nop
0x180048b09  lea     r8, [rbp+var_48]
0x180048b0d  mov     rdx, [rax+18h]
0x180048b11  mov     rcx, rdi
0x180048b14  mov     rax, rbx
0x180048b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b1c  mov     ebx, eax
0x180048b1e  cmp     eax, 83750009h
0x180048b23  jz      loc_180048C15
0x180048b29  test    eax, eax
0x180048b2b  jns     short loc_180048B4A
0x180048b2d  mov     r9d, eax; char *
0x180048b30  mov     edx, 12Ah; void *
0x180048b35  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048b3c  mov     rcx, [rbp+28h]; this
0x180048b40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048b45  jmp     loc_180048C58
0x180048b4a  mov     [rbp+var_40], r15d
0x180048b4e  mov     rcx, [rbp+var_48]
0x180048b52  mov     rax, [rcx]
0x180048b55  lea     rdx, [rbp+var_40]
0x180048b59  mov     rax, [rax+30h]
0x180048b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b62  mov     rcx, [rbp+28h]; this
0x180048b66  test    eax, eax
0x180048b68  js      loc_180048CA1
0x180048b6e  cmp     [rbp+var_40], 5
0x180048b72  jz      short loc_180048B83
0x180048b74  mov     ebx, 8000FFFFh
0x180048b79  mov     r9d, ebx
0x180048b7c  mov     edx, 130h
0x180048b81  jmp     short loc_180048B35
0x180048b83  mov     [rbp+var_38], r15
0x180048b87  mov     rdi, [rbp+var_48]
0x180048b8b  mov     rax, [rdi]
0x180048b8e  mov     rbx, [rax+60h]
0x180048b92  lea     rcx, [rbp+var_38]
0x180048b96  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x180048b9b  lea     rdx, [rbp+var_38]
0x180048b9f  mov     rcx, rdi
0x180048ba2  mov     rax, rbx
0x180048ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048baa  mov     rcx, [rbp+28h]; this
0x180048bae  test    eax, eax
0x180048bb0  js      loc_180048C8C
0x180048bb6  mov     [rbp+string], r15
0x180048bba  mov     rdi, [rbp+var_38]
0x180048bbe  mov     rax, [rdi]
0x180048bc1  mov     rbx, [rax+50h]
0x180048bc5  xor     ecx, ecx; string
0x180048bc7  call    cs:__imp_WindowsDeleteString
0x180048bcd  mov     [rbp+string], r15
0x180048bd1  lea     rdx, ?s_tagCnsFlightVersion@CnsPayloadProvider@@0QEBGEB; ushort const * const CnsPayloadProvider::s_tagCnsFlightVersion
0x180048bd8  lea     rcx, [rbp+var_28]
0x180048bdc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180048be1  nop
0x180048be2  lea     r8, [rbp+string]
0x180048be6  mov     rdx, [rax+18h]
0x180048bea  mov     rcx, rdi
0x180048bed  mov     rax, rbx
0x180048bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bf5  mov     ebx, eax
0x180048bf7  cmp     eax, 83750009h
0x180048bfc  jnz     short loc_180048C1A
0x180048bfe  mov     rcx, [rbp+string]; string
0x180048c02  call    cs:__imp_WindowsDeleteString
0x180048c08  mov     [rbp+string], r15
0x180048c0c  lea     rcx, [rbp+var_38]
0x180048c10  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048c15  mov     ebx, r15d
0x180048c18  jmp     short loc_180048C58
0x180048c1a  xor     edx, edx; length
0x180048c1c  mov     rcx, [rbp+string]; string
0x180048c20  call    cs:__imp_WindowsGetStringRawBuffer
0x180048c26  or      r8, 0FFFFFFFFFFFFFFFFh
0x180048c2a  inc     r8
0x180048c2d  cmp     [rax+r8*2], r15w
0x180048c32  jnz     short loc_180048C2A
0x180048c34  mov     rdx, rax
0x180048c37  mov     rcx, r14
0x180048c3a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180048c3f  nop
0x180048c40  mov     rcx, [rbp+string]; string
0x180048c44  call    cs:__imp_WindowsDeleteString
0x180048c4a  mov     [rbp+string], r15
0x180048c4e  lea     rcx, [rbp+var_38]
0x180048c52  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048c57  nop
0x180048c58  lea     rcx, [rbp+var_48]
0x180048c5c  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048c61  nop
0x180048c62  mov     rcx, rsi
0x180048c65  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180048c6a  mov     eax, ebx
0x180048c6c  mov     rcx, [rbp+var_8]
0x180048c70  xor     rcx, rsp; StackCookie
0x180048c73  call    __security_check_cookie
0x180048c78  mov     rbx, [rsp+70h+arg_10]
0x180048c80  add     rsp, 70h
0x180048c84  pop     r15
0x180048c86  pop     r14
0x180048c88  pop     rdi
0x180048c89  pop     rsi
0x180048c8a  pop     rbp
0x180048c8b  retn
0x180048c8c  mov     r9d, eax; char *
0x180048c8f  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048c96  mov     edx, 133h; void *
0x180048c9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048ca1  mov     r9d, eax; char *
0x180048ca4  lea     r8, aOnecoreBaseFli_38; "onecore\\base\\flighting\\onesettings\\"...
0x180048cab  mov     edx, 12Dh; void *
0x180048cb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
