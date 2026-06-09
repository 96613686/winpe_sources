# CConfirmCredentialPage::_CollectAndVerifyUsersCredential(void)

- ea: `0x180053900`
- end: `0x180053f4b`
- name: `?_CollectAndVerifyUsersCredential@CConfirmCredentialPage@@AEAAJXZ`
- size: `1611`
- prototype: `__int64 __fastcall(CConfirmCredentialPage *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180053650`

## callees

- `0x180006a54`
- `0x180006a74`
- `0x18005323c`
- `0x1800532b8`
- `0x18005385c`
- `0x180053900`
- `0x180053f54`
- `0x180053f84`
- `0x180063bc8`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053bfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053b8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053c0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053a3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053b8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053c0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053db4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053a7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053a7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053a33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053eb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053a33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053eb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ef8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f17`
- `credui!CredPackAuthenticationBufferW` at `0x180053a6c`
- `credui!CredPackAuthenticationBufferW` at `0x180053ad6`
- `credui!CredPackAuthenticationBufferW` at `0x180053a6c`
- `credui!CredPackAuthenticationBufferW` at `0x180053ad6`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180053cdc`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180053cdc`
- `ntdll!RtlInitString` at `0x18005396f`
- `ntdll!RtlInitString` at `0x180053987`
- `ntdll!RtlInitString` at `0x18005396f`
- `ntdll!RtlInitString` at `0x180053987`
- `ntdll!RtlNtStatusToDosError` at `0x180053c6b`
- `ntdll!RtlNtStatusToDosError` at `0x180053c6b`
- `SspiCli!LsaLogonUser` at `0x180053d77`
- `SspiCli!LsaLogonUser` at `0x180053d77`
- `SspiCli!LsaConnectUntrusted` at `0x1800539ae`
- `SspiCli!LsaConnectUntrusted` at `0x1800539ae`
- `SspiCli!LsaFreeReturnBuffer` at `0x180053d88`
- `SspiCli!LsaFreeReturnBuffer` at `0x180053d88`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800539d5`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800539d5`

## string_xrefs

- `0x180053b03`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`
- `0x180053e4f`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`
- `0x180053e76`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`
- `0x180053ecd`: `shell\cpls\usercpl\taskflows\pages\confirmcredentialpage.cpp`

## pseudocode

```c
__int64 __fastcall CConfirmCredentialPage::_CollectAndVerifyUsersCredential(CConfirmCredentialPage *this)
{
  NTSTATUS v2; // eax
  int v3; // esi
  __int64 v4; // rdx
  NTSTATUS v5; // eax
  __int64 *v6; // rcx
  __int64 v7; // rax
  LUID *v8; // rdi
  LUID SourceIdentifier; // r15
  void *v10; // r14
  DWORD LastError; // ebx
  __int64 v12; // rdi
  _BYTE *v13; // rax
  void *v14; // rbx
  _BYTE *i; // rcx
  const char *v16; // r9
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r8
  LUID *v20; // r14
  LUID v21; // r12
  void *v22; // r15
  DWORD v23; // edi
  unsigned int v24; // r8d
  LUID *v25; // r14
  LUID v26; // r12
  void *v27; // r15
  DWORD v28; // edi
  int v29; // edi
  ULONG v30; // eax
  _BYTE *v31; // rcx
  DWORD v32; // edi
  __int64 v33; // rdx
  DWORD v34; // eax
  void *v35; // rdx
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  NTSTATUS v38; // eax
  int v39; // eax
  unsigned __int64 v40; // r9
  int v42; // eax
  DWORD *pcbPackedCredentials; // [rsp+20h] [rbp-E0h]
  DWORD *pcbPackedCredentialsa; // [rsp+20h] [rbp-E0h]
  unsigned int pcbPackedCredentialsb; // [rsp+20h] [rbp-E0h]
  LPWSTR pszUserName; // [rsp+70h] [rbp-90h] BYREF
  ULONG AuthenticationInformationLength; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v48; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v49; // [rsp+88h] [rbp-78h] BYREF
  DWORD ulInAuthBufferSize; // [rsp+90h] [rbp-70h] BYREF
  ULONG AuthenticationPackage; // [rsp+94h] [rbp-6Ch] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  char *SubStatus; // [rsp+A0h] [rbp-60h] BYREF
  void *LsaHandle; // [rsp+A8h] [rbp-58h] BYREF
  void *v55; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+B8h] [rbp-48h] BYREF
  ULONG ProfileBufferLength; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v58[3]; // [rsp+C8h] [rbp-38h] BYREF
  char v59; // [rsp+E0h] [rbp-20h]
  HWND v60; // [rsp+E8h] [rbp-18h] BYREF
  PVOID ProfileBuffer; // [rsp+F0h] [rbp-10h] BYREF
  struct _LUID LogonId; // [rsp+F8h] [rbp-8h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+100h] [rbp+0h] BYREF
  _STRING DestinationString; // [rsp+128h] [rbp+28h] BYREF
  struct _STRING v65; // [rsp+138h] [rbp+38h] BYREF
  _TOKEN_SOURCE SourceContext; // [rsp+148h] [rbp+48h] BYREF
  char v67; // [rsp+158h] [rbp+58h]
  struct _QUOTA_LIMITS Quotas; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  LsaHandle = 0;
  v55 = 0;
  ulInAuthBufferSize = 0;
  pv = 0;
  AuthenticationInformationLength = 0;
  AuthenticationPackage = 0;
  pszUserName = 0;
  v60 = 0;
  v49 = 0;
  v48 = 0;
  DestinationString = 0;
  RtlInitString(&DestinationString, "Negotiate");
  v65 = 0;
  RtlInitString(&v65, "ConfirmCredential");
  v59 = 1;
  v58[0] = &LsaHandle;
  v58[1] = &pv;
  v58[2] = &AuthenticationInformationLength;
  v2 = LsaConnectUntrusted(&LsaHandle);
  v3 = v2 | 0x10000000;
  if ( v2 < 0 )
  {
    v4 = 216;
    goto LABEL_59;
  }
  v5 = LsaLookupAuthenticationPackage(LsaHandle, (PLSA_STRING)&DestinationString, &AuthenticationPackage);
  v3 = v5 | 0x10000000;
  if ( v5 < 0 )
  {
    v4 = 217;
    goto LABEL_59;
  }
  v6 = (__int64 *)*((_QWORD *)this + 6);
  v7 = *v6;
  *(_QWORD *)SourceContext.SourceName = &pszUserName;
  SourceContext.SourceIdentifier = 0;
  v67 = 1;
  v3 = (*(__int64 (__fastcall **)(__int64 *, LUID *))(v7 + 32))(v6, &SourceContext.SourceIdentifier);
  if ( v67 )
  {
    v8 = *(LUID **)SourceContext.SourceName;
    SourceIdentifier = SourceContext.SourceIdentifier;
    v10 = **(void ***)SourceContext.SourceName;
    if ( **(_QWORD **)SourceContext.SourceName )
    {
      LastError = GetLastError();
      CoTaskMemFree(v10);
      SetLastError(LastError);
    }
    *v8 = SourceIdentifier;
  }
  if ( v3 < 0 )
  {
    v4 = 218;
    goto LABEL_59;
  }
  if ( CredPackAuthenticationBufferW(0, pszUserName, (LPWSTR)&Class, 0, &ulInAuthBufferSize) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
      (const char *)0x8000FFFFLL,
      (int)pcbPackedCredentials);
    wil::details::lambda_call<_lambda_e824a722d2c628b59f84eaf3742c9a73_>::~lambda_call<_lambda_e824a722d2c628b59f84eaf3742c9a73_>((__int64)v58);
    if ( v48 )
      CoTaskMemFree(v48);
    if ( v49 )
      CoTaskMemFree(v49);
    if ( pszUserName )
      CoTaskMemFree(pszUserName);
    wistd::unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>(&v55);
    return 2147549183LL;
  }
  else
  {
    v12 = ulInAuthBufferSize;
    v13 = CoTaskMemAlloc(ulInAuthBufferSize);
    v14 = v13;
    if ( v13 )
    {
      for ( i = &v13[v12]; v13 != i; ++v13 )
        *v13 = 0;
    }
    hObject = 0;
    v55 = v14;
    wistd::unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>(&hObject);
    if ( !v14 )
    {
      v3 = -2147024882;
      v4 = 224;
LABEL_59:
      v40 = (unsigned int)v3;
LABEL_60:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
        (const char *)v40,
        (int)pcbPackedCredentials);
LABEL_61:
      wil::details::lambda_call<_lambda_e824a722d2c628b59f84eaf3742c9a73_>::~lambda_call<_lambda_e824a722d2c628b59f84eaf3742c9a73_>((__int64)v58);
      if ( v48 )
        CoTaskMemFree(v48);
      if ( v49 )
        CoTaskMemFree(v49);
      if ( pszUserName )
        CoTaskMemFree(pszUserName);
      wistd::unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>(&v55);
      return (unsigned int)v3;
    }
    if ( !CredPackAuthenticationBufferW(0, pszUserName, (LPWSTR)&Class, (PBYTE)v14, &ulInAuthBufferSize) )
    {
      v42 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xE1,
              (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
              v16);
LABEL_56:
      v3 = v42;
      goto LABEL_61;
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD, HWND *))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3), &v60);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"shell\\cpls\\usercpl\\taskflows\\pages\\confirmcredentialpage.cpp",
        (const char *)(unsigned int)v17,
        (int)pcbPackedCredentialsa);
    pUiInfo.hwndParent = v60;
    *(_QWORD *)&pUiInfo.cbSize = 40;
    *(_QWORD *)SourceContext.SourceName = &v49;
    memset(&pUiInfo.pszMessageText, 0, 24);
    SourceContext.SourceIdentifier = 0;
    v67 = 1;
    v3 = TResourceStringAllocCopyEx<unsigned short *>(
           g_hinst,
           3364,
           v18,
           (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
           pcbPackedCredentialsa,
           (char *)&SourceContext.SourceIdentifier);
    if ( v67 )
    {
      v20 = *(LUID **)SourceContext.SourceName;
      v21 = SourceContext.SourceIdentifier;
      v22 = **(void ***)SourceContext.SourceName;
      if ( **(_QWORD **)SourceContext.SourceName )
      {
        v23 = GetLastError();
        CoTaskMemFree(v22);
        SetLastError(v23);
      }
      *v20 = v21;
    }
    if ( v3 < 0 )
    {
      v4 = 237;
      goto LABEL_59;
    }
    pUiInfo.pszCaptionText = (PCWSTR)v49;
    *(_QWORD *)SourceContext.SourceName = &v48;
    SourceContext.SourceIdentifier = 0;
    v67 = 1;
    v3 = TResourceStringAllocCopyEx<unsigned short *>(
           g_hinst,
           3365,
           v19,
           (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
           pcbPackedCredentials,
           (char *)&SourceContext.SourceIdentifier);
    if ( v67 )
    {
      v25 = *(LUID **)SourceContext.SourceName;
      v26 = SourceContext.SourceIdentifier;
      v27 = **(void ***)SourceContext.SourceName;
      if ( **(_QWORD **)SourceContext.SourceName )
      {
        v28 = GetLastError();
        CoTaskMemFree(v27);
        SetLastError(v28);
      }
      *v25 = v26;
    }
    if ( v3 < 0 )
    {
      v4 = 239;
      goto LABEL_59;
    }
    v29 = 0;
    pUiInfo.pszMessageText = (PCWSTR)v48;
    LODWORD(SubStatus) = 0;
    while ( 1 )
    {
      if ( (int)SubStatus < 0 )
        wil::details::in1diag3::_Log_NtStatus(
          retaddr,
          (void *)0xF8,
          v24,
          (const char *)(unsigned int)SubStatus,
          (int)pcbPackedCredentials);
      v30 = RtlNtStatusToDosError(v29);
      v31 = pv;
      v32 = v30;
      if ( pv )
      {
        v33 = AuthenticationInformationLength;
        if ( AuthenticationInformationLength )
        {
          do
          {
            *v31++ = 0;
            --v33;
          }
          while ( v33 );
          CoTaskMemFree(pv);
          pv = 0;
          AuthenticationInformationLength = 0;
        }
      }
      v34 = CredUIPromptForWindowsCredentialsW(
              &pUiInfo,
              v32,
              &AuthenticationPackage,
              v14,
              ulInAuthBufferSize,
              &pv,
              &AuthenticationInformationLength,
              0,
              0x8000220u);
      if ( v34 )
      {
        v42 = wil::details::in1diag3::Return_Win32(retaddr, v35, v36, (const char *)v34, pcbPackedCredentialsb);
        goto LABEL_56;
      }
      SourceContext = 0;
      ProfileBuffer = 0;
      ProfileBufferLength = 0;
      LogonId = 0;
      memset(&Quotas, 0, sizeof(Quotas));
      hObject = 0;
      v29 = LsaLogonUser(
              LsaHandle,
              (PLSA_STRING)&v65,
              Interactive,
              AuthenticationPackage,
              pv,
              AuthenticationInformationLength,
              0,
              &SourceContext,
              &ProfileBuffer,
              &ProfileBufferLength,
              &LogonId,
              &hObject,
              &Quotas,
              (PNTSTATUS)&SubStatus);
      if ( ProfileBuffer )
      {
        v38 = LsaFreeReturnBuffer(ProfileBuffer);
        if ( v38 < 0 )
          wil::details::in1diag3::_Log_NtStatus(
            retaddr,
            (void *)0x12B,
            v37,
            (const char *)(unsigned int)v38,
            (int)pcbPackedCredentials);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( v29 >= 0 )
        break;
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0xF7,
        v37,
        (const char *)(unsigned int)v29,
        (int)pcbPackedCredentials);
    }
    v39 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD))(**((_QWORD **)this + 6) + 40LL))(
            *((_QWORD *)this + 6),
            pv,
            AuthenticationInformationLength);
    v3 = v39;
    if ( v39 < 0 )
    {
      v40 = (unsigned int)v39;
      v4 = 304;
      goto LABEL_60;
    }
    wil::details::lambda_call<_lambda_e824a722d2c628b59f84eaf3742c9a73_>::~lambda_call<_lambda_e824a722d2c628b59f84eaf3742c9a73_>((__int64)v58);
    if ( v48 )
      CoTaskMemFree(v48);
    if ( v49 )
      CoTaskMemFree(v49);
    if ( pszUserName )
      CoTaskMemFree(pszUserName);
    wistd::unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned char [0],wil::cotaskmem_secure_deleter>(&v55);
    return 0;
  }
}

```

## disassembly

```asm
0x180053900  push    rbp
0x180053902  push    rbx
0x180053903  push    rsi
0x180053904  push    rdi
0x180053905  push    r12
0x180053907  push    r13
0x180053909  push    r14
0x18005390b  push    r15
0x18005390d  lea     rbp, [rsp-0A8h]
0x180053915  sub     rsp, 1A8h
0x18005391c  mov     rax, cs:__security_cookie
0x180053923  xor     rax, rsp
0x180053926  mov     [rbp+0E0h+var_50], rax
0x18005392d  xor     r12d, r12d
0x180053930  lea     rdx, SourceString; "Negotiate"
0x180053937  mov     r13, rcx
0x18005393a  mov     [rbp+0E0h+LsaHandle], r12
0x18005393e  xorps   xmm0, xmm0
0x180053941  mov     [rbp+0E0h+var_130], r12
0x180053945  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x180053949  mov     [rbp+0E0h+ulInAuthBufferSize], r12d
0x18005394d  mov     [rbp+0E0h+pv], r12
0x180053951  mov     [rsp+1E0h+AuthenticationInformationLength], r12d
0x180053956  mov     [rbp+0E0h+AuthenticationPackage], r12d
0x18005395a  mov     [rsp+1E0h+pszUserName], r12
0x18005395f  mov     [rbp+0E0h+var_F8], r12
0x180053963  mov     [rbp+0E0h+var_158], r12
0x180053967  mov     [rbp+0E0h+var_160], r12
0x18005396b  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x18005396f  call    cs:__imp_RtlInitString
0x180053975  xorps   xmm0, xmm0
0x180053978  lea     rdx, aConfirmcredent; "ConfirmCredential"
0x18005397f  lea     rcx, [rbp+0E0h+var_A8]; DestinationString
0x180053983  movups  xmmword ptr [rbp+0E0h+var_A8.Length], xmm0
0x180053987  call    cs:__imp_RtlInitString
0x18005398d  lea     rax, [rbp+0E0h+LsaHandle]
0x180053991  mov     [rbp+0E0h+var_100], 1
0x180053995  mov     [rbp+0E0h+var_118], rax
0x180053999  lea     rcx, [rbp+0E0h+LsaHandle]; LsaHandle
0x18005399d  lea     rax, [rbp+0E0h+pv]
0x1800539a1  mov     [rbp+0E0h+var_110], rax
0x1800539a5  lea     rax, [rsp+1E0h+AuthenticationInformationLength]
0x1800539aa  mov     [rbp+0E0h+var_108], rax
0x1800539ae  call    cs:__imp_LsaConnectUntrusted
0x1800539b4  mov     esi, eax
0x1800539b6  mov     ebx, 10000000h
0x1800539bb  or      esi, ebx
0x1800539bd  jge     short loc_1800539C9
0x1800539bf  mov     edx, 0D8h
0x1800539c4  jmp     loc_180053E6C
0x1800539c9  mov     rcx, [rbp+0E0h+LsaHandle]; LsaHandle
0x1800539cd  lea     r8, [rbp+0E0h+AuthenticationPackage]; AuthenticationPackage
0x1800539d1  lea     rdx, [rbp+0E0h+DestinationString]; PackageName
0x1800539d5  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800539db  mov     esi, eax
0x1800539dd  or      esi, ebx
0x1800539df  jge     short loc_1800539EB
0x1800539e1  mov     edx, 0D9h
0x1800539e6  jmp     loc_180053E6C
0x1800539eb  mov     rcx, [r13+30h]
0x1800539ef  lea     rdx, [rsp+1E0h+pszUserName]
0x1800539f4  mov     rax, [rcx]
0x1800539f7  mov     qword ptr [rbp+0E0h+SourceContext.SourceName], rdx
0x1800539fb  lea     rdx, [rbp+0E0h+SourceContext.SourceIdentifier]
0x1800539ff  mov     qword ptr [rbp+0E0h+SourceContext.SourceIdentifier.LowPart], r12
0x180053a03  mov     [rbp+0E0h+var_88], 1
0x180053a07  mov     rax, [rax+20h]
0x180053a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a10  mov     esi, eax
0x180053a12  cmp     [rbp+0E0h+var_88], r12b
0x180053a16  jz      short loc_180053A44
0x180053a18  mov     rdi, qword ptr [rbp+0E0h+SourceContext.SourceName]
0x180053a1c  mov     r15, qword ptr [rbp+0E0h+SourceContext.SourceIdentifier.LowPart]
0x180053a20  mov     r14, [rdi]
0x180053a23  test    r14, r14
0x180053a26  jz      short loc_180053A41
0x180053a28  call    cs:__imp_GetLastError
0x180053a2e  mov     rcx, r14; pv
0x180053a31  mov     ebx, eax
0x180053a33  call    cs:__imp_CoTaskMemFree
0x180053a39  mov     ecx, ebx; dwErrCode
0x180053a3b  call    cs:__imp_SetLastError
0x180053a41  mov     [rdi], r15
0x180053a44  test    esi, esi
0x180053a46  jns     short loc_180053A52
0x180053a48  mov     edx, 0DAh
0x180053a4d  jmp     loc_180053E6C
0x180053a52  mov     rdx, [rsp+1E0h+pszUserName]; pszUserName
0x180053a57  lea     rax, [rbp+0E0h+ulInAuthBufferSize]
0x180053a5b  xor     r9d, r9d; pPackedCredentials
0x180053a5e  mov     [rsp+1E0h+pcbPackedCredentials], rax; int
0x180053a63  lea     r8, Class; pszPassword
0x180053a6a  xor     ecx, ecx; dwFlags
0x180053a6c  call    cs:__imp_CredPackAuthenticationBufferW
0x180053a72  test    eax, eax
0x180053a74  jnz     loc_180053EC6
0x180053a7a  mov     edi, [rbp+0E0h+ulInAuthBufferSize]
0x180053a7d  mov     ecx, edi; cb
0x180053a7f  call    cs:__imp_CoTaskMemAlloc
0x180053a85  mov     rbx, rax
0x180053a88  test    rax, rax
0x180053a8b  jz      short loc_180053AA2
0x180053a8d  lea     rcx, [rax+rdi]
0x180053a91  cmp     rax, rcx
0x180053a94  jz      short loc_180053AA2
0x180053a96  xor     edx, edx
0x180053a98  mov     [rax], dl
0x180053a9a  inc     rax
0x180053a9d  cmp     rax, rcx
0x180053aa0  jnz     short loc_180053A96
0x180053aa2  lea     rcx, [rbp+0E0h+hObject]
0x180053aa6  mov     [rbp+0E0h+hObject], r12
0x180053aaa  mov     [rbp+0E0h+var_130], rbx
0x180053aae  call    ??1?$unique_ptr@$$BY0A@EUcotaskmem_secure_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<uchar [0],wil::cotaskmem_secure_deleter>::~unique_ptr<uchar [0],wil::cotaskmem_secure_deleter>(void)
0x180053ab3  test    rbx, rbx
0x180053ab6  jz      loc_180053E62
0x180053abc  mov     rdx, [rsp+1E0h+pszUserName]; pszUserName
0x180053ac1  lea     rax, [rbp+0E0h+ulInAuthBufferSize]
0x180053ac5  mov     r9, rbx; pPackedCredentials
0x180053ac8  mov     [rsp+1E0h+pcbPackedCredentials], rax; int
0x180053acd  lea     r8, Class; pszPassword
0x180053ad4  xor     ecx, ecx; dwFlags
0x180053ad6  call    cs:__imp_CredPackAuthenticationBufferW
0x180053adc  test    eax, eax
0x180053ade  jz      loc_180053E48
0x180053ae4  mov     rcx, [r13+18h]
0x180053ae8  lea     rdx, [rbp+0E0h+var_F8]
0x180053aec  mov     rax, [rcx]
0x180053aef  mov     rax, [rax+48h]
0x180053af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053af8  test    eax, eax
0x180053afa  jns     short loc_180053B17
0x180053afc  mov     rcx, [rbp+0E8h]; this
0x180053b03  lea     r8, aShellCplsUserc_0; "shell\\cpls\\usercpl\\taskflows\\pages"...
0x180053b0a  mov     r9d, eax; char *
0x180053b0d  mov     edx, 0E8h; void *
0x180053b12  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053b17  mov     rax, [rbp+0E0h+var_F8]
0x180053b1b  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x180053b22  mov     rcx, cs:g_hinst; int
0x180053b29  xorps   xmm0, xmm0
0x180053b2c  mov     [rbp+0E0h+pUiInfo.hwndParent], rax
0x180053b30  mov     edx, 0D24h; int
0x180053b35  lea     rax, [rbp+0E0h+var_158]
0x180053b39  mov     qword ptr [rbp+0E0h+pUiInfo.cbSize], 28h ; '('
0x180053b41  mov     qword ptr [rbp+0E0h+SourceContext.SourceName], rax
0x180053b45  lea     rax, [rbp+0E0h+SourceContext.SourceIdentifier]
0x180053b49  mov     [rsp+1E0h+ppvOutAuthBuffer], rax; void *
0x180053b4e  movdqu  xmmword ptr [rbp+0E0h+pUiInfo.pszMessageText], xmm0
0x180053b53  mov     [rbp+0E0h+pUiInfo.hbmBanner], r12
0x180053b57  mov     qword ptr [rbp+0E0h+SourceContext.SourceIdentifier.LowPart], r12
0x180053b5b  mov     [rbp+0E0h+var_88], 1
0x180053b5f  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180053b64  mov     esi, eax
0x180053b66  cmp     [rbp+0E0h+var_88], r12b
0x180053b6a  jz      short loc_180053B9B
0x180053b6c  mov     r14, qword ptr [rbp+0E0h+SourceContext.SourceName]
0x180053b70  mov     r12, qword ptr [rbp+0E0h+SourceContext.SourceIdentifier.LowPart]
0x180053b74  mov     r15, [r14]
0x180053b77  test    r15, r15
0x180053b7a  jz      short loc_180053B95
0x180053b7c  call    cs:__imp_GetLastError
0x180053b82  mov     rcx, r15; pv
0x180053b85  mov     edi, eax
0x180053b87  call    cs:__imp_CoTaskMemFree
0x180053b8d  mov     ecx, edi; dwErrCode
0x180053b8f  call    cs:__imp_SetLastError
0x180053b95  mov     [r14], r12
0x180053b98  xor     r12d, r12d
0x180053b9b  test    esi, esi
0x180053b9d  jns     short loc_180053BA9
0x180053b9f  mov     edx, 0EDh
0x180053ba4  jmp     loc_180053E6C
0x180053ba9  mov     rax, [rbp+0E0h+var_158]
0x180053bad  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x180053bb4  mov     rcx, cs:g_hinst; int
0x180053bbb  mov     edx, 0D25h; int
0x180053bc0  mov     [rbp+0E0h+pUiInfo.pszCaptionText], rax
0x180053bc4  lea     rax, [rbp+0E0h+var_160]
0x180053bc8  mov     qword ptr [rbp+0E0h+SourceContext.SourceName], rax
0x180053bcc  lea     rax, [rbp+0E0h+SourceContext.SourceIdentifier]
0x180053bd0  mov     [rsp+1E0h+ppvOutAuthBuffer], rax; void *
0x180053bd5  mov     qword ptr [rbp+0E0h+SourceContext.SourceIdentifier.LowPart], r12
0x180053bd9  mov     [rbp+0E0h+var_88], 1
0x180053bdd  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180053be2  mov     esi, eax
0x180053be4  cmp     [rbp+0E0h+var_88], r12b
0x180053be8  jz      short loc_180053C19
0x180053bea  mov     r14, qword ptr [rbp+0E0h+SourceContext.SourceName]
0x180053bee  mov     r12, qword ptr [rbp+0E0h+SourceContext.SourceIdentifier.LowPart]
0x180053bf2  mov     r15, [r14]
0x180053bf5  test    r15, r15
0x180053bf8  jz      short loc_180053C13
0x180053bfa  call    cs:__imp_GetLastError
0x180053c00  mov     rcx, r15; pv
0x180053c03  mov     edi, eax
0x180053c05  call    cs:__imp_CoTaskMemFree
0x180053c0b  mov     ecx, edi; dwErrCode
0x180053c0d  call    cs:__imp_SetLastError
0x180053c13  mov     [r14], r12
0x180053c16  xor     r12d, r12d
0x180053c19  test    esi, esi
0x180053c1b  jns     short loc_180053C27
0x180053c1d  mov     edx, 0EFh
0x180053c22  jmp     loc_180053E6C
0x180053c27  mov     rax, [rbp+0E0h+var_160]
0x180053c2b  mov     edi, r12d
0x180053c2e  mov     [rbp+0E0h+pUiInfo.pszMessageText], rax
0x180053c32  mov     dword ptr [rbp+0E0h+var_140], r12d
0x180053c36  test    r12d, r12d
0x180053c39  jns     short loc_180053C4F
0x180053c3b  mov     rcx, [rbp+0E8h]; this
0x180053c42  mov     r9d, edi; char *
0x180053c45  mov     edx, 0F7h; void *
0x180053c4a  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180053c4f  mov     r9d, dword ptr [rbp+0E0h+var_140]; char *
0x180053c53  test    r9d, r9d
0x180053c56  jns     short loc_180053C69
0x180053c58  mov     rcx, [rbp+0E8h]; this
0x180053c5f  mov     edx, 0F8h; void *
0x180053c64  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180053c69  mov     ecx, edi; Status
0x180053c6b  call    cs:__imp_RtlNtStatusToDosError
0x180053c71  mov     rcx, [rbp+0E0h+pv]
0x180053c75  mov     edi, eax
0x180053c77  test    rcx, rcx
0x180053c7a  jz      short loc_180053CA8
0x180053c7c  mov     edx, [rsp+1E0h+AuthenticationInformationLength]
0x180053c80  test    edx, edx
0x180053c82  jz      short loc_180053CA8
0x180053c84  test    rdx, rdx
0x180053c87  jz      short loc_180053C99
0x180053c89  mov     [rcx], r12b
0x180053c8c  inc     rcx
0x180053c8f  sub     rdx, 1
0x180053c93  jnz     short loc_180053C89
0x180053c95  mov     rcx, [rbp+0E0h+pv]; pv
0x180053c99  call    cs:__imp_CoTaskMemFree
0x180053c9f  mov     [rbp+0E0h+pv], r12
0x180053ca3  mov     [rsp+1E0h+AuthenticationInformationLength], r12d
0x180053ca8  mov     eax, [rbp+0E0h+ulInAuthBufferSize]
0x180053cab  lea     rcx, [rsp+1E0h+AuthenticationInformationLength]
0x180053cb0  mov     [rsp+1E0h+dwFlags], 8000220h; dwFlags
0x180053cb8  lea     r8, [rbp+0E0h+AuthenticationPackage]; pulAuthPackage
0x180053cbc  mov     [rsp+1E0h+pfSave], r12; pfSave
0x180053cc1  mov     r9, rbx; pvInAuthBuffer
0x180053cc4  mov     [rsp+1E0h+pulOutAuthBufferSize], rcx; pulOutAuthBufferSize
0x180053cc9  mov     edx, edi; dwAuthError
0x180053ccb  lea     rcx, [rbp+0E0h+pv]
0x180053ccf  mov     [rsp+1E0h+ppvOutAuthBuffer], rcx; ppvOutAuthBuffer
0x180053cd4  lea     rcx, [rbp+0E0h+pUiInfo]; pUiInfo
0x180053cd8  mov     dword ptr [rsp+1E0h+pcbPackedCredentials], eax; unsigned int
0x180053cdc  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x180053ce2  test    eax, eax
0x180053ce4  jnz     loc_180053E35
0x180053cea  mov     rdx, [rbp+0E0h+pv]
0x180053cee  lea     rcx, [rbp+0E0h+var_140]
0x180053cf2  mov     eax, [rsp+1E0h+AuthenticationInformationLength]
0x180053cf6  xorps   xmm0, xmm0
0x180053cf9  mov     r9d, [rbp+0E0h+AuthenticationPackage]; AuthenticationPackage
0x180053cfd  mov     r8d, 2; LogonType
0x180053d03  mov     [rsp+1E0h+SubStatus], rcx; SubStatus
0x180053d08  lea     rcx, [rbp+0E0h+var_80]
0x180053d0c  mov     [rsp+1E0h+Quotas], rcx; Quotas
0x180053d11  lea     rcx, [rbp+0E0h+hObject]
0x180053d15  mov     [rsp+1E0h+Token], rcx; Token
0x180053d1a  lea     rcx, [rbp+0E0h+var_E8]
0x180053d1e  mov     [rsp+1E0h+LogonId], rcx; LogonId
0x180053d23  lea     rcx, [rbp+0E0h+var_120]
0x180053d27  mov     [rsp+1E0h+ProfileBufferLength], rcx; ProfileBufferLength
0x180053d2c  lea     rcx, [rbp+0E0h+ProfileBuffer]
0x180053d30  mov     qword ptr [rsp+1E0h+dwFlags], rcx; ProfileBuffer
0x180053d35  lea     rcx, [rbp+0E0h+SourceContext]
0x180053d39  mov     [rsp+1E0h+pfSave], rcx; SourceContext
0x180053d3e  mov     rcx, [rbp+0E0h+LsaHandle]; LsaHandle
0x180053d42  mov     [rsp+1E0h+pulOutAuthBufferSize], r12; LocalGroups
0x180053d47  mov     dword ptr [rsp+1E0h+ppvOutAuthBuffer], eax; AuthenticationInformationLength
0x180053d4b  mov     [rsp+1E0h+pcbPackedCredentials], rdx; int
0x180053d50  lea     rdx, [rbp+0E0h+var_A8]; OriginName
0x180053d54  movups  xmmword ptr [rbp+0E0h+SourceContext.SourceName], xmm0
0x180053d58  mov     [rbp+0E0h+ProfileBuffer], r12
0x180053d5c  mov     [rbp+0E0h+var_120], r12d
0x180053d60  mov     qword ptr [rbp+0E0h+var_E8.LowPart], r12
0x180053d64  movups  xmmword ptr [rbp+0E0h+var_80.PagedPoolLimit], xmm0
0x180053d68  mov     [rbp+0E0h+hObject], r12
0x180053d6c  movups  xmmword ptr [rbp+0E0h+var_80.MinimumWorkingSetSize], xmm0
0x180053d70  movups  xmmword ptr [rbp+0E0h+var_80.PagefileLimit], xmm0
0x180053d77  call    cs:__imp_LsaLogonUser
0x180053d7d  mov     rcx, [rbp+0E0h+ProfileBuffer]; Buffer
0x180053d81  mov     edi, eax
0x180053d83  test    rcx, rcx
0x180053d86  jz      short loc_180053DA6
0x180053d88  call    cs:__imp_LsaFreeReturnBuffer
0x180053d8e  test    eax, eax
0x180053d90  jns     short loc_180053DA6
0x180053d92  mov     rcx, [rbp+0E8h]; this
0x180053d99  mov     r9d, eax; char *
0x180053d9c  mov     edx, 12Bh; void *
0x180053da1  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180053da6  mov     rcx, [rbp+0E0h+hObject]; hObject
  ... truncated ...
```
