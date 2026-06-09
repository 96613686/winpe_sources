# I_InitializeProviders(VCARD_DATA *)

- ea: `0x180028610`
- end: `0x180028901`
- name: `?I_InitializeProviders@@YAKPEAUVCARD_DATA@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(struct VCARD_DATA *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016954`
- `0x1800292e8`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x180015384`
- `0x180016040`
- `0x18001a31c`
- `0x1800271e0`
- `0x180027534`
- `0x180027e28`
- `0x180028610`
- `0x180029d7c`
- `0x180029f00`
- `0x1800348a0`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800286c7`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800286c7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002878e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028819`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028887`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002878e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028819`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028887`

## string_xrefs

- `0x18002873b`: `Unable to open KSP`

## pseudocode

```c
__int64 __fastcall I_InitializeProviders(struct VCARD_DATA *a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  struct VCARD_DATA *v3; // rbx
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  NTSTATUS v9; // ebx
  struct VCARD_DATA *v10; // rbx
  __int64 v11; // rcx
  int v12; // r9d
  _QWORD *v13; // rcx
  int v14; // edx
  const char *v15; // rax
  struct VCARD_DATA *v16; // rbx
  __int64 v17; // rcx
  struct VCARD_DATA *v18; // rbx
  __int64 v19; // rcx
  NTSTATUS v21; // [rsp+30h] [rbp-39h] BYREF
  struct VCARD_DATA *v22; // [rsp+38h] [rbp-31h] BYREF
  int v23; // [rsp+40h] [rbp-29h] BYREF
  struct VCARD_DATA **v24; // [rsp+48h] [rbp-21h] BYREF
  __int16 v25; // [rsp+50h] [rbp-19h]
  _QWORD *v26; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v27[3]; // [rsp+60h] [rbp-9h] BYREF
  char v28[24]; // [rsp+78h] [rbp+Fh] BYREF

  v22 = a1;
  v21 = 0;
  v23 = 0;
  strcpy(v28, "I_InitializeProviders");
  v27[0] = v28;
  v27[1] = &v23;
  v27[2] = &v21;
  lambda_02984a94624d6ca3006aa5b981ee8c5b_::operator()(v27);
  v23 = 1;
  v26 = v27;
  v3 = v22;
  if ( !v22 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v2, v1);
    v3 = v22;
  }
  v24 = &v22;
  v25 = 258;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    (char *)v3 + 88,
    0);
  v5 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)v3 + 11, L"Microsoft Platform Crypto Provider", 0);
  if ( !v5 )
  {
    v10 = v22;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)v22 + 96,
      0);
    v9 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)v10 + 12, L"RNG", L"Microsoft Primitive Provider", 0);
    if ( v9 >= 0 )
    {
      v16 = v22;
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)v22 + 104,
        0);
      v9 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)v16 + 13, L"3DES", L"Microsoft Primitive Provider", 0);
      if ( v9 >= 0 )
      {
        v18 = v22;
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          (char *)v22 + 112,
          0);
        v9 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)v18 + 14, L"AES", L"Microsoft Primitive Provider", 0);
        if ( v9 >= 0 )
        {
          HIBYTE(v25) = 0;
          goto LABEL_27;
        }
        WppTraceIndent(v19, 2);
        v21 = v9;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v14 = 28;
        v15 = "Unable to load AES algorithm provider";
      }
      else
      {
        WppTraceIndent(v17, 2);
        v21 = v9;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_28;
        }
        v14 = 27;
        v15 = "Unable to load 3-key 3DES algorithm provider";
      }
    }
    else
    {
      WppTraceIndent(v11, 2);
      v21 = v9;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v14 = 26;
      v15 = "Unable to load random number generator";
    }
    WPP_SF_sds(v13[2], v14, (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids, v12, v9, (__int64)v15);
    goto LABEL_27;
  }
  if ( (Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits & 1) != 0 )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    McTemplateU0zq_EventWriteTransfer(v8, v7, v6, v5);
  }
  WppTraceIndent(v4, 2);
  v9 = I_MapSecurityStatusToWinError(v5);
  v21 = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
      (_DWORD)WPP_pszIndent,
      v5,
      (__int64)"Unable to open KSP");
LABEL_27:
    v9 = v21;
  }
LABEL_28:
  wil::details::ScopeExitFnGuard__lambda_9f011a697e1b95e65aca0069327968e8___::operator()(&v24);
  WppTraceUnwinder__lambda_02984a94624d6ca3006aa5b981ee8c5b____::_WppTraceUnwinder__lambda_02984a94624d6ca3006aa5b981ee8c5b____(&v26);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180028610  push    rbp
0x180028612  push    rbx
0x180028613  push    rsi
0x180028614  push    rdi
0x180028615  lea     rbp, [rsp-3Fh]
0x18002861a  sub     rsp, 0A8h
0x180028621  mov     rax, cs:__security_cookie
0x180028628  xor     rax, rsp
0x18002862b  mov     [rbp+57h+var_30], rax
0x18002862f  mov     [rbp+57h+var_88], rcx
0x180028633  mov     [rbp+57h+var_90], 0
0x18002863a  mov     [rbp+57h+var_80], 0
0x180028641  movups  xmm0, xmmword ptr cs:aIInitializepro; "I_InitializeProviders"
0x180028648  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18002864c  movsd   xmm1, qword ptr cs:aIInitializepro+0Eh; "oviders"
0x180028654  movsd   qword ptr [rbp+57h+var_48+0Eh], xmm1
0x180028659  lea     rax, [rbp+57h+var_48]
0x18002865d  mov     [rbp+57h+var_60], rax
0x180028661  lea     rax, [rbp+57h+var_80]
0x180028665  mov     [rbp+57h+var_58], rax
0x180028669  lea     rax, [rbp+57h+var_90]
0x18002866d  mov     [rbp+57h+var_50], rax
0x180028671  lea     rcx, [rbp+57h+var_60]
0x180028675  call    _lambda_02984a94624d6ca3006aa5b981ee8c5b___operator__
0x18002867a  mov     [rbp+57h+var_80], 1
0x180028681  lea     rax, [rbp+57h+var_60]
0x180028685  mov     [rbp+57h+var_68], rax
0x180028689  mov     rbx, [rbp+57h+var_88]
0x18002868d  test    rbx, rbx
0x180028690  jnz     short loc_18002869B
0x180028692  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180028697  mov     rbx, [rbp+57h+var_88]
0x18002869b  lea     rax, [rbp+57h+var_88]
0x18002869f  mov     [rbp+57h+var_78], rax
0x1800286a3  mov     esi, 2
0x1800286a8  mov     [rbp+57h+var_70], 102h
0x1800286ae  xor     edx, edx
0x1800286b0  lea     rcx, [rbx+58h]
0x1800286b4  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800286b9  xor     r8d, r8d; dwFlags
0x1800286bc  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800286c3  lea     rcx, [rbx+58h]; phProvider
0x1800286c7  call    cs:__imp_NCryptOpenStorageProvider
0x1800286cd  mov     edi, eax
0x1800286cf  test    eax, eax
0x1800286d1  jz      loc_180028767
0x1800286d7  test    cs:Microsoft_Windows_SmartCard_TPM_VCard_ModuleEnableBits, 1
0x1800286de  jz      short loc_1800286F8
0x1800286e0  mov     rcx, [rbp+57h+var_88]
0x1800286e4  add     rcx, 18h
0x1800286e8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800286ed  mov     r9d, edi
0x1800286f0  mov     r8, rax
0x1800286f3  call    McTemplateU0zq_EventWriteTransfer
0x1800286f8  mov     edx, esi
0x1800286fa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800286ff  mov     ecx, edi; int
0x180028701  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x180028706  mov     ebx, eax
0x180028708  mov     [rbp+57h+var_90], eax
0x18002870b  lea     rax, WPP_GLOBAL_Control
0x180028712  mov     rcx, cs:WPP_GLOBAL_Control
0x180028719  cmp     rcx, rax
0x18002871c  jz      loc_1800288D4
0x180028722  test    byte ptr [rcx+1Ch], 1
0x180028726  jz      loc_1800288D4
0x18002872c  cmp     [rcx+19h], sil
0x180028730  jb      loc_1800288D4
0x180028736  mov     edx, 19h
0x18002873b  lea     rax, aUnableToOpenKs_0; "Unable to open KSP"
0x180028742  mov     [rsp+0C0h+var_98], rax
0x180028747  mov     [rsp+0C0h+var_A0], edi
0x18002874b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028752  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180028759  mov     rcx, [rcx+10h]
0x18002875d  call    WPP_SF_sDs
0x180028762  jmp     loc_1800288D1
0x180028767  mov     rbx, [rbp+57h+var_88]
0x18002876b  xor     edx, edx
0x18002876d  lea     rcx, [rbx+60h]
0x180028771  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028776  xor     r9d, r9d; dwFlags
0x180028779  lea     rdi, pszImplementation; "Microsoft Primitive Provider"
0x180028780  mov     r8, rdi; pszImplementation
0x180028783  lea     rdx, aRng; "RNG"
0x18002878a  lea     rcx, [rbx+60h]; phAlgorithm
0x18002878e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180028794  mov     ebx, eax
0x180028796  test    eax, eax
0x180028798  jns     short loc_1800287F9
0x18002879a  mov     edx, esi
0x18002879c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800287a1  mov     [rbp+57h+var_90], ebx
0x1800287a4  lea     rax, WPP_GLOBAL_Control
0x1800287ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287b2  cmp     rcx, rax
0x1800287b5  jz      loc_1800288D4
0x1800287bb  test    byte ptr [rcx+1Ch], 1
0x1800287bf  jz      loc_1800288D4
0x1800287c5  cmp     [rcx+19h], sil
0x1800287c9  jb      loc_1800288D4
0x1800287cf  mov     edx, 1Ah
0x1800287d4  lea     rax, aUnableToLoadRa; "Unable to load random number generator"
0x1800287db  mov     [rsp+0C0h+var_98], rax
0x1800287e0  mov     [rsp+0C0h+var_A0], ebx
0x1800287e4  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x1800287eb  mov     rcx, [rcx+10h]
0x1800287ef  call    WPP_SF_sds
0x1800287f4  jmp     loc_1800288D1
0x1800287f9  mov     rbx, [rbp+57h+var_88]
0x1800287fd  xor     edx, edx
0x1800287ff  lea     rcx, [rbx+68h]
0x180028803  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028808  xor     r9d, r9d; dwFlags
0x18002880b  mov     r8, rdi; pszImplementation
0x18002880e  lea     rdx, a3des; "3DES"
0x180028815  lea     rcx, [rbx+68h]; phAlgorithm
0x180028819  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002881f  mov     ebx, eax
0x180028821  test    eax, eax
0x180028823  jns     short loc_180028867
0x180028825  mov     edx, esi
0x180028827  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002882c  mov     [rbp+57h+var_90], ebx
0x18002882f  lea     rax, WPP_GLOBAL_Control
0x180028836  mov     rcx, cs:WPP_GLOBAL_Control
0x18002883d  cmp     rcx, rax
0x180028840  jz      loc_1800288D4
0x180028846  test    byte ptr [rcx+1Ch], 1
0x18002884a  jz      loc_1800288D4
0x180028850  cmp     [rcx+19h], sil
0x180028854  jb      short loc_1800288D4
0x180028856  mov     edx, 1Bh
0x18002885b  lea     rax, aUnableToLoad3K; "Unable to load 3-key 3DES algorithm pro"...
0x180028862  jmp     loc_1800287DB
0x180028867  mov     rbx, [rbp+57h+var_88]
0x18002886b  xor     edx, edx
0x18002886d  lea     rcx, [rbx+70h]
0x180028871  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180028876  xor     r9d, r9d; dwFlags
0x180028879  mov     r8, rdi; pszImplementation
0x18002887c  lea     rdx, aAes; "AES"
0x180028883  lea     rcx, [rbx+70h]; phAlgorithm
0x180028887  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002888d  mov     ebx, eax
0x18002888f  test    eax, eax
0x180028891  jns     short loc_1800288CD
0x180028893  mov     edx, esi
0x180028895  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002889a  mov     [rbp+57h+var_90], ebx
0x18002889d  lea     rax, WPP_GLOBAL_Control
0x1800288a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288ab  cmp     rcx, rax
0x1800288ae  jz      short loc_1800288D4
0x1800288b0  test    byte ptr [rcx+1Ch], 1
0x1800288b4  jz      short loc_1800288D4
0x1800288b6  cmp     [rcx+19h], sil
0x1800288ba  jb      short loc_1800288D4
0x1800288bc  mov     edx, 1Ch
0x1800288c1  lea     rax, aUnableToLoadAe; "Unable to load AES algorithm provider"
0x1800288c8  jmp     loc_1800287DB
0x1800288cd  mov     byte ptr [rbp+57h+var_70+1], 0
0x1800288d1  mov     ebx, [rbp+57h+var_90]
0x1800288d4  lea     rcx, [rbp+57h+var_78]
0x1800288d8  call    wil__details__ScopeExitFnGuard__lambda_9f011a697e1b95e65aca0069327968e8_____operator__
0x1800288dd  nop
0x1800288de  lea     rcx, [rbp+57h+var_68]
0x1800288e2  call    WppTraceUnwinder__lambda_02984a94624d6ca3006aa5b981ee8c5b_______WppTraceUnwinder__lambda_02984a94624d6ca3006aa5b981ee8c5b____
0x1800288e7  mov     eax, ebx
0x1800288e9  mov     rcx, [rbp+57h+var_30]
0x1800288ed  xor     rcx, rsp; StackCookie
0x1800288f0  call    __security_check_cookie
0x1800288f5  add     rsp, 0A8h
0x1800288fc  pop     rdi
0x1800288fd  pop     rsi
0x1800288fe  pop     rbx
0x1800288ff  pop     rbp
0x180028900  retn
```
