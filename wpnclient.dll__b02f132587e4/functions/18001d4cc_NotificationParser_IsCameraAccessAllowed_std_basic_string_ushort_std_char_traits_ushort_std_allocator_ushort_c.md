# NotificationParser::IsCameraAccessAllowed(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x18001d4cc`
- end: `0x18001d84d`
- name: `?IsCameraAccessAllowed@NotificationParser@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800192d4`

## callees

- `0x1800070e8`
- `0x18000f720`
- `0x180013740`
- `0x18001478c`
- `0x180015854`
- `0x18001d4cc`
- `0x18001d854`
- `0x18001ff00`
- `0x18002cdbc`
- `0x18002df8c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d5ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d70f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d5ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d70f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d5d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d5d6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d542`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d613`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d542`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d613`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d58f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d58f`

## string_xrefs

- `0x18001d5cf`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`
- `0x18001d514`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NotificationParser::IsCameraAccessAllowed(__int64 a1, _QWORD *a2, bool *a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  __int64 v7; // rdx
  NotificationParser *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  HSTRING v11; // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD **); // rbx
  __int64 v15; // rax
  int v16; // eax
  _QWORD *v17; // rbx
  __int64 v18; // r14
  __int64 v19; // rsi
  const WCHAR *v20; // rdi
  unsigned __int64 v21; // rcx
  signed int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE Sid[80]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v35 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&string,
    L"Windows.Internal.CapabilityAccess.CapabilityAccess",
    0x33u,
    0x32u);
  v5 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v35);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 830;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
LABEL_31:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    return v9;
  }
  ActivationFactory = NotificationParser::WpnGetUserSid(v8, v7, Sid);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v10 = 834;
    goto LABEL_5;
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x345,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0x8000FFFFLL,
      v28);
LABEL_30:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_31;
  }
  v29 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
         0x45u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v11 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v12 = RoGetActivationFactory(v11, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v29);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v12,
      v28);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    goto LABEL_30;
  }
  v31 = 0;
  v13 = v29;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v29 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &c_szCapabilityWebcam);
  v16 = v14(v13, *(_QWORD *)(v15 + 24), &v31);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v16,
      v28);
LABEL_28:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    goto LABEL_29;
  }
  v32 = 0;
  v17 = v31;
  v18 = *v31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_QWORD *)v33 = a2;
  v19 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v38, v33) + 24);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  v20 = StringSid;
  v33[0] = 0;
  v21 = -1;
  do
    ++v21;
  while ( StringSid[v21] );
  v22 = ULongLongToUInt(v21, v33);
  if ( v22 < 0 )
  {
    RaiseException(v22, 1u, 0, 0);
    __debugbreak();
  }
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v33[0]);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&string, v20, v23, v33[0]);
  v24 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64, __int64 *))(v18 + 88))(
          v17,
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
          v19,
          &v32);
  v9 = v24;
  if ( v24 < 0 )
  {
    v25 = 851;
LABEL_26:
    v26 = (unsigned int)v24;
    goto LABEL_27;
  }
  if ( !v32 )
  {
    v9 = -2147024894;
    v26 = 2147942402LL;
    v25 = 854;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)v26,
      v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    goto LABEL_28;
  }
  v34 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 88LL))(v32, &v34);
  v9 = v24;
  if ( v24 < 0 )
  {
    v25 = 857;
    goto LABEL_26;
  }
  *a3 = v34 == 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return 0;
}

```

## disassembly

```asm
0x18001d4cc  mov     [rsp-8+arg_0], rbx
0x18001d4d1  mov     [rsp-8+arg_18], rsi
0x18001d4d6  push    rbp
0x18001d4d7  push    rdi
0x18001d4d8  push    r12
0x18001d4da  push    r14
0x18001d4dc  push    r15
0x18001d4de  lea     rbp, [rsp-10h]
0x18001d4e3  sub     rsp, 110h
0x18001d4ea  mov     rax, cs:__security_cookie
0x18001d4f1  xor     rax, rsp
0x18001d4f4  mov     [rbp+30h+var_30], rax
0x18001d4f8  mov     r15, r8
0x18001d4fb  mov     rsi, rdx
0x18001d4fe  xor     r12d, r12d
0x18001d501  mov     [rsp+130h+var_D0], r12
0x18001d506  mov     qword ptr [rbp+30h+hstringHeader.Reserved+10h], r12
0x18001d50a  lea     r9d, [r12+32h]; unsigned int
0x18001d50f  lea     r8d, [r12+33h]; unsigned int
0x18001d514  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18001d51b  lea     rcx, [rsp+130h+string]; hstringHeader
0x18001d520  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d525  mov     rbx, qword ptr [rbp+30h+hstringHeader.Reserved+10h]
0x18001d529  lea     rcx, [rsp+130h+var_D0]
0x18001d52e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d533  lea     r8, [rsp+130h+var_D0]
0x18001d538  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18001d53f  mov     rcx, rbx
0x18001d542  call    cs:__imp_RoGetActivationFactory
0x18001d548  mov     ebx, eax
0x18001d54a  test    eax, eax
0x18001d54c  jns     short loc_18001D555
0x18001d54e  mov     edx, 33Eh
0x18001d553  jmp     short loc_18001D569
0x18001d555  lea     r8, [rbp+30h+Sid]; void *
0x18001d559  call    ?WpnGetUserSid@NotificationParser@@AEAAJKPEAX@Z; NotificationParser::WpnGetUserSid(ulong,void *)
0x18001d55e  mov     ebx, eax
0x18001d560  test    eax, eax
0x18001d562  jns     short loc_18001D581
0x18001d564  mov     edx, 342h; void *
0x18001d569  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d570  mov     r9d, eax; char *
0x18001d573  mov     rcx, [rbp+38h]; this
0x18001d577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d57c  jmp     loc_18001D7D4
0x18001d581  mov     [rsp+130h+StringSid], r12
0x18001d586  lea     rdx, [rsp+130h+StringSid]; StringSid
0x18001d58b  lea     rcx, [rbp+30h+Sid]; Sid
0x18001d58f  call    cs:__imp_ConvertSidToStringSidW
0x18001d595  test    eax, eax
0x18001d597  jnz     short loc_18001D5BB
0x18001d599  mov     rcx, [rbp+38h]; this
0x18001d59d  mov     ebx, 8000FFFFh
0x18001d5a2  mov     r9d, ebx; char *
0x18001d5a5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d5ac  mov     edx, 345h; void *
0x18001d5b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d5b6  jmp     loc_18001D7C9
0x18001d5bb  mov     [rsp+130h+var_100], r12
0x18001d5c0  lea     r9, [rsp+130h+string]; string
0x18001d5c5  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x18001d5ca  mov     edx, 45h ; 'E'; length
0x18001d5cf  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x18001d5d6  call    cs:__imp_WindowsCreateStringReference
0x18001d5dc  test    eax, eax
0x18001d5de  jns     short loc_18001D5F5
0x18001d5e0  xor     r9d, r9d; lpArguments
0x18001d5e3  xor     r8d, r8d; nNumberOfArguments
0x18001d5e6  lea     edx, [r9+1]; dwExceptionFlags
0x18001d5ea  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001d5ef  call    cs:__imp_RaiseException
0x18001d5f5  mov     rbx, [rsp+130h+string]
0x18001d5fa  lea     rcx, [rsp+130h+var_100]
0x18001d5ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d604  lea     r8, [rsp+130h+var_100]
0x18001d609  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x18001d610  mov     rcx, rbx
0x18001d613  call    cs:__imp_RoGetActivationFactory
0x18001d619  mov     ebx, eax
0x18001d61b  test    eax, eax
0x18001d61d  jns     short loc_18001D63C
0x18001d61f  mov     rcx, [rbp+38h]; this
0x18001d623  mov     r9d, eax; char *
0x18001d626  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d62d  mov     edx, 34Ah; void *
0x18001d632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d637  jmp     loc_18001D7BE
0x18001d63c  mov     [rsp+130h+var_F0], r12
0x18001d641  mov     rdi, [rsp+130h+var_100]
0x18001d646  mov     rax, [rdi]
0x18001d649  mov     rbx, [rax+30h]
0x18001d64d  lea     rcx, [rsp+130h+var_F0]
0x18001d652  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d657  lea     rdx, ?c_szCapabilityWebcam@@3QEBGEB; ushort const * const c_szCapabilityWebcam
0x18001d65e  lea     rcx, [rsp+130h+string]
0x18001d663  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d668  nop
0x18001d669  lea     r8, [rsp+130h+var_F0]
0x18001d66e  mov     rdx, [rax+18h]
0x18001d672  mov     rcx, rdi
0x18001d675  mov     rax, rbx
0x18001d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d67d  mov     ebx, eax
0x18001d67f  test    eax, eax
0x18001d681  jns     short loc_18001D6A0
0x18001d683  mov     rcx, [rbp+38h]; this
0x18001d687  mov     r9d, eax; char *
0x18001d68a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d691  mov     edx, 34Dh; void *
0x18001d696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d69b  jmp     loc_18001D7B3
0x18001d6a0  mov     [rsp+130h+var_E8], r12
0x18001d6a5  mov     rbx, [rsp+130h+var_F0]
0x18001d6aa  mov     r14, [rbx]
0x18001d6ad  lea     rcx, [rsp+130h+var_E8]
0x18001d6b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d6b7  cmp     qword ptr [rsi+18h], 7
0x18001d6bc  jbe     short loc_18001D6C1
0x18001d6be  mov     rsi, [rsi]
0x18001d6c1  mov     qword ptr [rsp+130h+var_E0], rsi
0x18001d6c6  lea     rdx, [rsp+130h+var_E0]
0x18001d6cb  lea     rcx, [rbp+30h+var_A8]
0x18001d6cf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d6d4  nop
0x18001d6d5  mov     rsi, [rax+18h]
0x18001d6d9  mov     qword ptr [rbp+30h+hstringHeader.Reserved+10h], r12
0x18001d6dd  mov     rdi, [rsp+130h+StringSid]
0x18001d6e2  mov     [rsp+130h+var_E0], r12d
0x18001d6e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001d6eb  inc     rcx; unsigned __int64
0x18001d6ee  cmp     [rdi+rcx*2], r12w
0x18001d6f3  jnz     short loc_18001D6EB
0x18001d6f5  lea     rdx, [rsp+130h+var_E0]; unsigned int *
0x18001d6fa  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001d6ff  test    eax, eax
0x18001d701  jns     short loc_18001D716
0x18001d703  xor     r9d, r9d; lpArguments
0x18001d706  xor     r8d, r8d; nNumberOfArguments
0x18001d709  lea     edx, [r9+1]; dwExceptionFlags
0x18001d70d  mov     ecx, eax; dwExceptionCode
0x18001d70f  call    cs:__imp_RaiseException
0x18001d715  int     3; Trap to Debugger
0x18001d716  mov     ecx, [rsp+130h+var_E0]; unsigned int
0x18001d71a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001d71f  mov     r9d, [rsp+130h+var_E0]; unsigned int
0x18001d724  mov     r8d, eax; unsigned int
0x18001d727  mov     rdx, rdi; sourceString
0x18001d72a  lea     rcx, [rsp+130h+string]; hstringHeader
0x18001d72f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d734  nop
0x18001d735  lea     r9, [rsp+130h+var_E8]
0x18001d73a  mov     r8, rsi
0x18001d73d  mov     rdx, qword ptr [rbp+30h+hstringHeader.Reserved+10h]
0x18001d741  mov     rcx, rbx
0x18001d744  mov     rax, [r14+58h]
0x18001d748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d74d  mov     ebx, eax
0x18001d74f  test    eax, eax
0x18001d751  jns     short loc_18001D75A
0x18001d753  mov     edx, 353h
0x18001d758  jmp     short loc_18001D794
0x18001d75a  mov     rcx, [rsp+130h+var_E8]
0x18001d75f  test    rcx, rcx
0x18001d762  jnz     short loc_18001D773
0x18001d764  mov     ebx, 80070002h
0x18001d769  mov     r9d, ebx
0x18001d76c  mov     edx, 356h
0x18001d771  jmp     short loc_18001D797
0x18001d773  mov     [rsp+130h+var_D8], r12d
0x18001d778  mov     rax, [rcx]
0x18001d77b  lea     rdx, [rsp+130h+var_D8]
0x18001d780  mov     rax, [rax+58h]
0x18001d784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d789  mov     ebx, eax
0x18001d78b  test    eax, eax
0x18001d78d  jns     short loc_18001D7E2
0x18001d78f  mov     edx, 359h; void *
0x18001d794  mov     r9d, eax; char *
0x18001d797  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d79e  mov     rcx, [rbp+38h]; this
0x18001d7a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d7a7  nop
0x18001d7a8  lea     rcx, [rsp+130h+var_E8]
0x18001d7ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d7b2  nop
0x18001d7b3  lea     rcx, [rsp+130h+var_F0]
0x18001d7b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d7bd  nop
0x18001d7be  lea     rcx, [rsp+130h+var_100]
0x18001d7c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d7c8  nop
0x18001d7c9  lea     rcx, [rsp+130h+StringSid]
0x18001d7ce  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d7d3  nop
0x18001d7d4  lea     rcx, [rsp+130h+var_D0]
0x18001d7d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d7de  mov     eax, ebx
0x18001d7e0  jmp     short loc_18001D825
0x18001d7e2  cmp     [rsp+130h+var_D8], 1
0x18001d7e7  setz    al
0x18001d7ea  mov     [r15], al
0x18001d7ed  lea     rcx, [rsp+130h+var_E8]
0x18001d7f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d7f7  nop
0x18001d7f8  lea     rcx, [rsp+130h+var_F0]
0x18001d7fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d802  nop
0x18001d803  lea     rcx, [rsp+130h+var_100]
0x18001d808  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d80d  nop
0x18001d80e  lea     rcx, [rsp+130h+StringSid]
0x18001d813  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d818  nop
0x18001d819  lea     rcx, [rsp+130h+var_D0]
0x18001d81e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d823  xor     eax, eax
0x18001d825  mov     rcx, [rbp+30h+var_30]
0x18001d829  xor     rcx, rsp; StackCookie
0x18001d82c  call    __security_check_cookie
0x18001d831  lea     r11, [rsp+130h+var_20]
0x18001d839  mov     rbx, [r11+30h]
0x18001d83d  mov     rsi, [r11+48h]
0x18001d841  mov     rsp, r11
0x18001d844  pop     r15
0x18001d846  pop     r14
0x18001d848  pop     r12
0x18001d84a  pop     rdi
0x18001d84b  pop     rbp
0x18001d84c  retn
```
