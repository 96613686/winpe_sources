# I_CreateAik

- ea: `0x18001ec10`
- end: `0x18001f27f`
- name: `I_CreateAik`
- size: `1647`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800253f0`

## callees

- `0x1800011ec`
- `0x1800016d0`
- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x180015638`
- `0x180016040`
- `0x18001a31c`
- `0x18001cb44`
- `0x18001cb88`
- `0x18001cef0`
- `0x18001cf28`
- `0x18001cfa8`
- `0x18001e554`
- `0x18001e92c`
- `0x18001ec10`
- `0x1800207b4`
- `0x180025480`
- `0x180025548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f090`
- `ncrypt!NCryptFinalizeKey` at `0x18001efe0`
- `ncrypt!NCryptFinalizeKey` at `0x18001efe0`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001eed6`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001eed6`
- `ncrypt!NCryptSetProperty` at `0x18001ef7e`
- `ncrypt!NCryptSetProperty` at `0x18001f11f`
- `ncrypt!NCryptSetProperty` at `0x18001ef7e`
- `ncrypt!NCryptSetProperty` at `0x18001f11f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f074`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f074`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001f0fd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001f0fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f230`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f230`

## string_xrefs

- `0x18001ec59`: `I_CreateAik`
- `0x18001ef20`: `Unable to create KSP key`
- `0x18001f0cc`: `Unable to create security descriptor`
- `0x18001f113`: `Security Descr`
- `0x18001f177`: `Unable to set security descriptor property`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall I_CreateAik(__int64 a1, __int64 a2, NCRYPT_KEY_HANDLE *a3, const WCHAR *a4, int a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  _DWORD *v14; // r9
  int LastError; // ebx
  _QWORD *v16; // rcx
  int v17; // edx
  const char *v18; // rax
  __int64 v19; // rcx
  char v20; // r8
  _QWORD *v21; // rcx
  int v22; // edx
  const char *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  BOOL v26; // ebx
  __int64 v27; // rcx
  DWORD SecurityDescriptorLength; // eax
  __int64 v29; // rcx
  char v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // r9d
  NCRYPT_KEY_HANDLE v34; // rax
  PSECURITY_DESCRIPTOR v35; // rcx
  bool v36; // zf
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  char v39; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  char v41[4]; // [rsp+64h] [rbp-9Ch] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  BYTE pbInput[4]; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+7Ch] [rbp-84h] BYREF
  int v46; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v47; // [rsp+88h] [rbp-78h] BYREF
  int v48; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v50; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v51[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v52[6]; // [rsp+C0h] [rbp-40h] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+F0h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v55; // [rsp+100h] [rbp+0h]
  int v56; // [rsp+110h] [rbp+10h] BYREF
  char v57; // [rsp+114h] [rbp+14h]
  _BYTE v58[16]; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v59[4]; // [rsp+128h] [rbp+28h] BYREF
  char v60[16]; // [rsp+138h] [rbp+38h] BYREF

  v39 = 7;
  v38 = 0;
  v40 = 0;
  v49 = 0;
  v45 = 0;
  strcpy(v60, "I_CreateAik");
  v51[0] = v60;
  v51[1] = &v45;
  v51[2] = &v38;
  lambda_dcf782e15e48f3a135f779609c1495af_::operator()(v51);
  v45 = 1;
  v50 = v51;
  v56 = 0;
  v57 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(
    (__int64)&v56,
    v8,
    v9,
    v10);
  if ( (unsigned int)dword_180048098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048098, 0x400000000000LL, v12, v13) )
  {
    v46 = a5;
    v41[0] = v39;
    LODWORD(v47) = v49;
    v48 = v40;
    *(_DWORD *)pbInput = v38;
    if ( v57 && (v59[0] || v59[1] || v59[2] || v59[3]) )
      v14 = v59;
    else
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180048098,
      (__int64)byte_18003EF45,
      (__int64)v58,
      (__int64)v14,
      (__int64)pbInput,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)v41,
      (__int64)&v46);
  }
  v52[0] = &v56;
  v52[1] = &v38;
  v52[2] = &v40;
  v52[3] = &v49;
  v52[4] = &v39;
  v52[5] = &a5;
  v47 = v52;
  if ( (unsigned int)(a5 - 1) > 1 )
  {
    WppTraceIndent(v11, 2u);
    LastError = 50;
    v38 = 50;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 22;
      v18 = "Attestation type not supported.";
LABEL_21:
      WPP_SF_sDs(
        v16[2],
        v17,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        50,
        (__int64)v18);
      LastError = v38;
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( (v39 & 0xF) == 7 )
  {
    phKey = 0;
    std::chrono::steady_clock::now(&v48);
    p_pSecurityDescriptor = (PSECURITY_DESCRIPTOR *)&v49;
    SecurityDescriptor = &v48;
    v55 = 258;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v40 = NCryptCreatePersistedKey(*(_QWORD *)(a1 + 88), &phKey, L"RSA", a4, 0, 0);
    if ( v40 )
    {
      WppTraceIndent(v19, 2u);
      LastError = I_MapSecurityStatusToWinError(v40);
      v38 = LastError;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v22 = 24;
      v23 = "Unable to create KSP key";
LABEL_27:
      WPP_SF_sDs(
        v21[2],
        v22,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v20,
        (__int64)v23);
      LastError = v38;
LABEL_28:
      wil::details::ScopeExitFnGuard__lambda_966117fc7d4d5b00e63d9571ec6983a0___::operator()(&p_pSecurityDescriptor);
LABEL_61:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      goto LABEL_62;
    }
    *(_DWORD *)pbInput = 8;
    v40 = NCryptSetProperty(phKey, L"PCP_KEY_USAGE_POLICY", pbInput, 4u, 0);
    if ( v40 )
    {
      WppTraceIndent(v24, 2u);
      LastError = I_MapSecurityStatusToWinError(v40);
      v38 = LastError;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v22 = 25;
      v23 = "Unable to set key usage policy";
      goto LABEL_27;
    }
    v40 = NCryptFinalizeKey(phKey, 0x40u);
    if ( v40 )
    {
      WppTraceIndent(v25, 2u);
      LastError = I_MapSecurityStatusToWinError(v40);
      v38 = LastError;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v22 = 26;
      v23 = "Unable to finalize key";
      goto LABEL_27;
    }
    wil::details::ScopeExitFnGuard__lambda_966117fc7d4d5b00e63d9571ec6983a0___::operator()(&p_pSecurityDescriptor);
    pSecurityDescriptor = 0;
    p_pSecurityDescriptor = &pSecurityDescriptor;
    SecurityDescriptor = 0;
    LOBYTE(v55) = 1;
    v26 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;;GA;;;CO)(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;NS)",
            1u,
            &SecurityDescriptor,
            0);
    wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_pSecurityDescriptor);
    if ( !v26 )
    {
      WppTraceIndent(v27, 2u);
      LastError = GetLastError();
      v38 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError,
          (__int64)"Unable to create security descriptor");
        goto LABEL_58;
      }
LABEL_59:
      v35 = pSecurityDescriptor;
      v36 = pSecurityDescriptor == 0;
      pSecurityDescriptor = 0;
      if ( !v36 )
        LocalFree(v35);
      goto LABEL_61;
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    v40 = NCryptSetProperty(phKey, L"Security Descr", (PBYTE)pSecurityDescriptor, SecurityDescriptorLength, 4u);
    if ( v40 )
    {
      WppTraceIndent(v29, 2u);
      LastError = I_MapSecurityStatusToWinError(v40);
      v38 = LastError;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v30,
        (__int64)"Unable to set security descriptor property");
    }
    else
    {
      if ( a5 != 2
        || (std::wstring::wstring(&p_pSecurityDescriptor, a4),
            LastError = I_EnrollForAikCertificate(v31, &p_pSecurityDescriptor),
            std::wstring::_Tidy_deallocate((__int64)&p_pSecurityDescriptor),
            LastError >= 0) )
      {
        if ( a3 )
        {
          v34 = phKey;
          phKey = 0;
          *a3 = v34;
        }
        goto LABEL_58;
      }
      WppTraceIndent(v32, 2u);
      v38 = LastError;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_59;
      }
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        v33,
        LastError,
        (__int64)"Unable to enroll for AIK certificate");
    }
LABEL_58:
    LastError = v38;
    goto LABEL_59;
  }
  WppTraceIndent(v11, 2u);
  LastError = 50;
  v38 = 50;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 23;
    v18 = "Invalid algorithm";
    goto LABEL_21;
  }
LABEL_62:
  ScTraceUnwinder__lambda_0d312ade8b4e689cc8ad23bf911963d8____::_ScTraceUnwinder__lambda_0d312ade8b4e689cc8ad23bf911963d8____(&v47);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v56);
  WppTraceUnwinder__lambda_dcf782e15e48f3a135f779609c1495af____::_WppTraceUnwinder__lambda_dcf782e15e48f3a135f779609c1495af____(&v50);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001ec10  push    rbp
0x18001ec12  push    rbx
0x18001ec13  push    rsi
0x18001ec14  push    rdi
0x18001ec15  push    r12
0x18001ec17  push    r14
0x18001ec19  push    r15
0x18001ec1b  lea     rbp, [rsp-50h]
0x18001ec20  sub     rsp, 150h
0x18001ec27  mov     rax, cs:__security_cookie
0x18001ec2e  xor     rax, rsp
0x18001ec31  mov     [rbp+80h+var_38], rax
0x18001ec35  mov     r14, r9
0x18001ec38  mov     rsi, r8
0x18001ec3b  mov     rbx, rcx
0x18001ec3e  mov     [rsp+180h+var_128], 7
0x18001ec43  xor     r15d, r15d
0x18001ec46  mov     [rsp+180h+var_130], r15d
0x18001ec4b  mov     [rsp+180h+var_120], r15d
0x18001ec50  mov     [rbp+80h+var_E8], r15
0x18001ec54  mov     [rsp+180h+var_104], r15d
0x18001ec59  movsd   xmm0, qword ptr cs:aICreateaik; "I_CreateAik"
0x18001ec61  movsd   qword ptr [rbp+80h+var_48], xmm0
0x18001ec66  mov     eax, dword ptr cs:aICreateaik+8; "Aik"
0x18001ec6c  mov     dword ptr [rbp+80h+var_48+8], eax
0x18001ec6f  lea     rax, [rbp+80h+var_48]
0x18001ec73  mov     [rbp+80h+var_D8], rax
0x18001ec77  lea     rax, [rsp+180h+var_104]
0x18001ec7c  mov     [rbp+80h+var_D0], rax
0x18001ec80  lea     rax, [rsp+180h+var_130]
0x18001ec85  mov     [rbp+80h+var_C8], rax
0x18001ec89  lea     rcx, [rbp+80h+var_D8]
0x18001ec8d  call    _lambda_dcf782e15e48f3a135f779609c1495af___operator__
0x18001ec92  lea     r12d, [r15+1]
0x18001ec96  mov     [rsp+180h+var_104], r12d
0x18001ec9b  lea     rax, [rbp+80h+var_D8]
0x18001ec9f  mov     [rbp+80h+var_E0], rax
0x18001eca3  mov     [rbp+80h+var_70], r15d
0x18001eca7  mov     [rbp+80h+var_6C], r15b
0x18001ecab  lea     rcx, [rbp+80h+var_70]
0x18001ecaf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18001ecb4  mov     eax, cs:dword_180048098
0x18001ecba  cmp     eax, 5
0x18001ecbd  jbe     loc_18001ED74
0x18001ecc3  mov     rdx, 400000000000h
0x18001eccd  lea     rcx, dword_180048098
0x18001ecd4  call    _tlgKeywordOn
0x18001ecd9  test    al, al
0x18001ecdb  jz      loc_18001ED74
0x18001ece1  mov     eax, [rbp+80h+arg_20]
0x18001ece7  mov     [rbp+80h+var_100], eax
0x18001ecea  mov     al, [rsp+180h+var_128]
0x18001ecee  mov     [rsp+180h+var_11C], al
0x18001ecf2  mov     eax, dword ptr [rbp+80h+var_E8]
0x18001ecf5  mov     dword ptr [rbp+80h+var_F8], eax
0x18001ecf8  mov     eax, [rsp+180h+var_120]
0x18001ecfc  mov     [rbp+80h+var_F0], eax
0x18001ecff  mov     eax, [rsp+180h+var_130]
0x18001ed03  mov     dword ptr [rsp+180h+pbInput], eax
0x18001ed07  cmp     [rbp+80h+var_6C], r15b
0x18001ed0b  jz      short loc_18001ED2B
0x18001ed0d  cmp     [rbp+80h+var_58], r15d
0x18001ed11  jnz     short loc_18001ED25
0x18001ed13  cmp     [rbp+80h+var_54], r15d
0x18001ed17  jnz     short loc_18001ED25
0x18001ed19  cmp     [rbp+80h+var_50], r15d
0x18001ed1d  jnz     short loc_18001ED25
0x18001ed1f  cmp     [rbp+80h+var_4C], r15d
0x18001ed23  jz      short loc_18001ED2B
0x18001ed25  lea     r9, [rbp+80h+var_58]
0x18001ed29  jmp     short loc_18001ED2E
0x18001ed2b  mov     r9, r15
0x18001ed2e  lea     rax, [rbp+80h+var_100]
0x18001ed32  mov     [rsp+180h+var_140], rax
0x18001ed37  lea     rax, [rsp+180h+var_11C]
0x18001ed3c  mov     [rsp+180h+var_148], rax
0x18001ed41  lea     rax, [rbp+80h+var_F8]
0x18001ed45  mov     [rsp+180h+var_150], rax
0x18001ed4a  lea     rax, [rbp+80h+var_F0]
0x18001ed4e  mov     qword ptr [rsp+180h+dwFlags], rax
0x18001ed53  lea     rax, [rsp+180h+pbInput]
0x18001ed58  mov     qword ptr [rsp+180h+dwLegacyKeySpec], rax
0x18001ed5d  lea     r8, [rbp+80h+var_68]
0x18001ed61  lea     rdx, byte_18003EF45
0x18001ed68  lea     rcx, dword_180048098
0x18001ed6f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18001ed74  lea     rax, [rbp+80h+var_70]
0x18001ed78  mov     [rbp+80h+var_C0], rax
0x18001ed7c  lea     rax, [rsp+180h+var_130]
0x18001ed81  mov     [rbp+80h+var_B8], rax
0x18001ed85  lea     rax, [rsp+180h+var_120]
0x18001ed8a  mov     [rbp+80h+var_B0], rax
0x18001ed8e  lea     rax, [rbp+80h+var_E8]
0x18001ed92  mov     [rbp+80h+var_A8], rax
0x18001ed96  lea     rax, [rsp+180h+var_128]
0x18001ed9b  mov     [rbp+80h+var_A0], rax
0x18001ed9f  lea     rax, [rbp+80h+arg_20]
0x18001eda6  mov     [rbp+80h+var_98], rax
0x18001edaa  lea     rax, [rbp+80h+var_C0]
0x18001edae  mov     [rbp+80h+var_F8], rax
0x18001edb2  mov     eax, [rbp+80h+arg_20]
0x18001edb8  dec     eax
0x18001edba  cmp     eax, r12d
0x18001edbd  jbe     short loc_18001EE09
0x18001edbf  mov     edi, 2
0x18001edc4  mov     edx, edi
0x18001edc6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001edcb  lea     ebx, [rdi+30h]
0x18001edce  mov     [rsp+180h+var_130], ebx
0x18001edd2  lea     rax, WPP_GLOBAL_Control
0x18001edd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ede0  cmp     rcx, rax
0x18001ede3  jz      loc_18001F242
0x18001ede9  test    [rcx+1Ch], r12b
0x18001eded  jz      loc_18001F242
0x18001edf3  cmp     [rcx+19h], dil
0x18001edf7  jb      loc_18001F242
0x18001edfd  lea     edx, [rdi+14h]
0x18001ee00  lea     rax, aAttestationTyp; "Attestation type not supported."
0x18001ee07  jmp     short loc_18001EE5B
0x18001ee09  mov     al, [rsp+180h+var_128]
0x18001ee0d  and     al, 0Fh
0x18001ee0f  cmp     al, 7
0x18001ee11  jz      short loc_18001EE84
0x18001ee13  mov     edi, 2
0x18001ee18  mov     edx, edi
0x18001ee1a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001ee1f  lea     ebx, [rdi+30h]
0x18001ee22  mov     [rsp+180h+var_130], ebx
0x18001ee26  lea     rax, WPP_GLOBAL_Control
0x18001ee2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee34  cmp     rcx, rax
0x18001ee37  jz      loc_18001F242
0x18001ee3d  test    [rcx+1Ch], r12b
0x18001ee41  jz      loc_18001F242
0x18001ee47  cmp     [rcx+19h], dil
0x18001ee4b  jb      loc_18001F242
0x18001ee51  lea     edx, [rdi+15h]
0x18001ee54  lea     rax, aInvalidAlgorit; "Invalid algorithm"
0x18001ee5b  mov     qword ptr [rsp+180h+dwFlags], rax
0x18001ee60  mov     [rsp+180h+dwLegacyKeySpec], ebx
0x18001ee64  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ee6b  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001ee72  mov     rcx, [rcx+10h]
0x18001ee76  call    WPP_SF_sDs
0x18001ee7b  mov     ebx, [rsp+180h+var_130]
0x18001ee7f  jmp     loc_18001F242
0x18001ee84  mov     [rsp+180h+phKey], r15
0x18001ee89  lea     rcx, [rbp+80h+var_F0]
0x18001ee8d  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18001ee92  lea     rax, [rbp+80h+var_E8]
0x18001ee96  mov     [rbp+80h+var_90], rax
0x18001ee9a  lea     rax, [rbp+80h+var_F0]
0x18001ee9e  mov     [rbp+80h+SecurityDescriptor], rax
0x18001eea2  mov     edi, 2
0x18001eea7  mov     [rbp+80h+var_80], 102h
0x18001eead  xor     edx, edx
0x18001eeaf  lea     rcx, [rsp+180h+phKey]
0x18001eeb4  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18001eeb9  mov     [rsp+180h+dwFlags], r15d; dwFlags
0x18001eebe  mov     [rsp+180h+dwLegacyKeySpec], r15d; dwLegacyKeySpec
0x18001eec3  mov     r9, r14; pszKeyName
0x18001eec6  lea     r8, pszAlgId; "RSA"
0x18001eecd  lea     rdx, [rsp+180h+phKey]; phKey
0x18001eed2  mov     rcx, [rbx+58h]; hProvider
0x18001eed6  call    cs:__imp_NCryptCreatePersistedKey
0x18001eedc  mov     [rsp+180h+var_120], eax
0x18001eee0  test    eax, eax
0x18001eee2  jz      short loc_18001EF5A
0x18001eee4  mov     edx, edi
0x18001eee6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001eeeb  mov     r8d, [rsp+180h+var_120]
0x18001eef0  mov     ecx, r8d; int
0x18001eef3  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001eef8  mov     ebx, eax
0x18001eefa  mov     [rsp+180h+var_130], eax
0x18001eefe  lea     rax, WPP_GLOBAL_Control
0x18001ef05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef0c  cmp     rcx, rax
0x18001ef0f  jz      short loc_18001EF4C
0x18001ef11  test    [rcx+1Ch], r12b
0x18001ef15  jz      short loc_18001EF4C
0x18001ef17  cmp     [rcx+19h], dil
0x18001ef1b  jb      short loc_18001EF4C
0x18001ef1d  lea     edx, [rdi+16h]
0x18001ef20  lea     rax, aUnableToCreate_11; "Unable to create KSP key"
0x18001ef27  mov     qword ptr [rsp+180h+dwFlags], rax
0x18001ef2c  mov     [rsp+180h+dwLegacyKeySpec], r8d
0x18001ef31  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ef38  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001ef3f  mov     rcx, [rcx+10h]
0x18001ef43  call    WPP_SF_sDs
0x18001ef48  mov     ebx, [rsp+180h+var_130]
0x18001ef4c  lea     rcx, [rbp+80h+var_90]
0x18001ef50  call    wil__details__ScopeExitFnGuard__lambda_966117fc7d4d5b00e63d9571ec6983a0_____operator__
0x18001ef55  jmp     loc_18001F237
0x18001ef5a  mov     dword ptr [rsp+180h+pbInput], 8
0x18001ef62  mov     [rsp+180h+dwLegacyKeySpec], r15d; dwFlags
0x18001ef67  mov     r9d, 4; cbInput
0x18001ef6d  lea     r8, [rsp+180h+pbInput]; pbInput
0x18001ef72  lea     rdx, aPcpKeyUsagePol; "PCP_KEY_USAGE_POLICY"
0x18001ef79  mov     rcx, [rsp+180h+phKey]; hObject
0x18001ef7e  call    cs:__imp_NCryptSetProperty
0x18001ef84  mov     [rsp+180h+var_120], eax
0x18001ef88  test    eax, eax
0x18001ef8a  jz      short loc_18001EFD6
0x18001ef8c  mov     edx, edi
0x18001ef8e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001ef93  mov     r8d, [rsp+180h+var_120]
0x18001ef98  mov     ecx, r8d; int
0x18001ef9b  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001efa0  mov     ebx, eax
0x18001efa2  mov     [rsp+180h+var_130], eax
0x18001efa6  lea     rax, WPP_GLOBAL_Control
0x18001efad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efb4  cmp     rcx, rax
0x18001efb7  jz      short loc_18001EF4C
0x18001efb9  test    [rcx+1Ch], r12b
0x18001efbd  jz      short loc_18001EF4C
0x18001efbf  cmp     [rcx+19h], dil
0x18001efc3  jb      short loc_18001EF4C
0x18001efc5  mov     edx, 19h
0x18001efca  lea     rax, aUnableToSetKey_1; "Unable to set key usage policy"
0x18001efd1  jmp     loc_18001EF27
0x18001efd6  mov     edx, 40h ; '@'; dwFlags
0x18001efdb  mov     rcx, [rsp+180h+phKey]; hKey
0x18001efe0  call    cs:__imp_NCryptFinalizeKey
0x18001efe6  mov     [rsp+180h+var_120], eax
0x18001efea  test    eax, eax
0x18001efec  jz      short loc_18001F044
0x18001efee  mov     edx, edi
0x18001eff0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001eff5  mov     r8d, [rsp+180h+var_120]
0x18001effa  mov     ecx, r8d; int
0x18001effd  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18001f002  mov     ebx, eax
0x18001f004  mov     [rsp+180h+var_130], eax
0x18001f008  lea     rax, WPP_GLOBAL_Control
0x18001f00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f016  cmp     rcx, rax
0x18001f019  jz      loc_18001EF4C
0x18001f01f  test    [rcx+1Ch], r12b
0x18001f023  jz      loc_18001EF4C
0x18001f029  cmp     [rcx+19h], dil
0x18001f02d  jb      loc_18001EF4C
0x18001f033  mov     edx, 1Ah
0x18001f038  lea     rax, aUnableToFinali; "Unable to finalize key"
0x18001f03f  jmp     loc_18001EF27
0x18001f044  lea     rcx, [rbp+80h+var_90]
0x18001f048  call    wil__details__ScopeExitFnGuard__lambda_966117fc7d4d5b00e63d9571ec6983a0_____operator__
0x18001f04d  mov     [rsp+180h+pSecurityDescriptor], r15
0x18001f052  lea     rax, [rsp+180h+pSecurityDescriptor]
0x18001f057  mov     [rbp+80h+var_90], rax
0x18001f05b  mov     [rbp+80h+SecurityDescriptor], r15
0x18001f05f  mov     byte ptr [rbp+80h+var_80], r12b
0x18001f063  xor     r9d, r9d; SecurityDescriptorSize
0x18001f066  lea     r8, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x18001f06a  mov     edx, r12d; StringSDRevision
0x18001f06d  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;CO)(A;;GA;;;SY)(A;;GA;;;BA)"...
0x18001f074  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001f07a  mov     ebx, eax
0x18001f07c  lea     rcx, [rbp+80h+var_90]
0x18001f080  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f085  test    ebx, ebx
0x18001f087  jnz     short loc_18001F0F8
0x18001f089  mov     edx, edi
0x18001f08b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f090  call    cs:__imp_GetLastError
0x18001f096  mov     ebx, eax
0x18001f098  mov     [rsp+180h+var_130], eax
0x18001f09c  lea     rax, WPP_GLOBAL_Control
0x18001f0a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0aa  cmp     rcx, rax
0x18001f0ad  jz      loc_18001F221
0x18001f0b3  test    [rcx+1Ch], r12b
0x18001f0b7  jz      loc_18001F221
0x18001f0bd  cmp     [rcx+19h], dil
0x18001f0c1  jb      loc_18001F221
0x18001f0c7  mov     edx, 1Bh
0x18001f0cc  lea     rax, aUnableToCreate; "Unable to create security descriptor"
0x18001f0d3  mov     qword ptr [rsp+180h+dwFlags], rax
0x18001f0d8  mov     [rsp+180h+dwLegacyKeySpec], ebx
0x18001f0dc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f0e3  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f0ea  mov     rcx, [rcx+10h]
0x18001f0ee  call    WPP_SF_sDs
0x18001f0f3  jmp     loc_18001F21D
0x18001f0f8  mov     rcx, [rsp+180h+pSecurityDescriptor]; pSecurityDescriptor
0x18001f0fd  call    cs:__imp_GetSecurityDescriptorLength
0x18001f103  mov     [rsp+180h+dwLegacyKeySpec], 4; dwFlags
0x18001f10b  mov     r9d, eax; cbInput
0x18001f10e  mov     r8, [rsp+180h+pSecurityDescriptor]; pbInput
0x18001f113  lea     rdx, aSecurityDescr; "Security Descr"
0x18001f11a  mov     rcx, [rsp+180h+phKey]; hObject
0x18001f11f  call    cs:__imp_NCryptSetProperty
0x18001f125  mov     [rsp+180h+var_120], eax
0x18001f129  test    eax, eax
0x18001f12b  jz      short loc_18001F18D
0x18001f12d  mov     edx, edi
0x18001f12f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
  ... truncated ...
```
