# UtilAddAccessToPath(wchar_t const *,ulong)

- ea: `0x1800678d4`
- end: `0x180068089`
- name: `?UtilAddAccessToPath@@YAJPEB_WK@Z`
- size: `1973`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180066ba8`
- `0x18008f2ec`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18001c368`
- `0x18001e0d0`
- `0x18001e100`
- `0x1800235c8`
- `0x180023d28`
- `0x18002a758`
- `0x18002d930`
- `0x18002e94c`
- `0x180031cd0`
- `0x180045e58`
- `0x1800678d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067c3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067c3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180067ca6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180067ca6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067c1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067c1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180067cba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180067cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067ff8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006795e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006795e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180067f28`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180067f28`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180067f8d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180067f8d`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180067fe8`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180067fe8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180067bb0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180067bb0`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180067a49`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180067b48`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180067a49`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180067b48`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067d38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067e35`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067d38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180067e35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ebb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067ebb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180067ed6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180067ed6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilAddAccessToPath(const wchar_t *a1, DWORD a2)
{
  int v4; // ebx
  HANDLE FileW; // rax
  HANDLE v6; // rdi
  DWORD LastError; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  char *v11; // rdx
  DWORD v12; // eax
  DWORD v13; // eax
  __int64 unique_oversize_for; // rax
  PSECURITY_DESCRIPTOR v15; // rbx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  DWORD v19; // eax
  DWORD v20; // eax
  void **v21; // rbx
  HANDLE CurrentThread; // rax
  DWORD v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  void **v27; // rbx
  HANDLE CurrentProcess; // rax
  DWORD v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  char *v33; // rdx
  DWORD v34; // eax
  DWORD v35; // eax
  __int64 v36; // rax
  LPWCH *v37; // rbx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  DWORD v41; // eax
  HLOCAL v42; // rcx
  DWORD v43; // eax
  DWORD v44; // eax
  DWORD v45; // eax
  DWORD v46; // eax
  const wchar_t *v48; // [rsp+40h] [rbp-79h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-69h] BYREF
  BOOL bDaclDefaulted; // [rsp+58h] [rbp-61h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-51h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp-41h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-39h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v58; // [rsp+D0h] [rbp+17h]
  DWORD nLengthNeeded; // [rsp+120h] [rbp+67h] BYREF
  BOOL bDaclPresent; // [rsp+130h] [rbp+77h] BYREF
  int v61; // [rsp+138h] [rbp+7Fh] BYREF

  nLengthNeeded = 0;
  pSecurityDescriptor = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v58 = 0;
  pDacl = 0;
  hMem = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  Handle = 0;
  if ( !a1 )
  {
    v4 = -2147024809;
    goto LABEL_77;
  }
  FileW = CreateFileW(a1, 0x60000u, 3u, 0, 3u, 0x2200000u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&Handle, FileW);
  v6 = Handle;
  if ( (unsigned __int64)Handle + 1 <= 1 )
  {
    LastError = GetLastError();
    v4 = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
    {
      v11 = byte_1800CC611;
LABEL_7:
      v48 = a1;
      v61 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        v8,
        (_DWORD)v11,
        v9,
        v10,
        (__int64)&v48,
        (__int64)&v61);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  v4 = UtilVerifyFilePath(a1, Handle);
  if ( v4 >= 0 )
  {
    if ( GetKernelObjectSecurity(v6, 4u, 0, 0, &nLengthNeeded) )
    {
      v13 = nLengthNeeded;
    }
    else
    {
      v12 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v12);
      v13 = nLengthNeeded;
      if ( !nLengthNeeded || v4 != -2147024774 )
      {
        if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        {
          v11 = &byte_1800CC687;
          goto LABEL_7;
        }
        goto LABEL_77;
      }
    }
    unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v61, v13);
    utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
      &pSecurityDescriptor,
      unique_oversize_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v61);
    v15 = pSecurityDescriptor;
    if ( !pSecurityDescriptor )
    {
      v4 = -2147024882;
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v61 = -2147024882;
        v48 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&word_1800CC6C6,
          v17,
          v18,
          (__int64)&v48,
          (__int64)&v61);
      }
      goto LABEL_77;
    }
    if ( !GetKernelObjectSecurity(v6, 4u, pSecurityDescriptor, nLengthNeeded, &nLengthNeeded) )
    {
      v19 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v19);
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v11 = byte_1800CC703;
        goto LABEL_7;
      }
      goto LABEL_77;
    }
    if ( !GetSecurityDescriptorDacl(v15, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v20 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v20);
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v11 = (char *)word_1800CC742;
        goto LABEL_7;
      }
      goto LABEL_77;
    }
    if ( !bDaclPresent )
      pDacl = 0;
    v21 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, v21) )
    {
      v23 = GetLastError();
      ERROR_HR_FROM_WIN32(v23);
      if ( (unsigned int)dword_1800DE000 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v61 = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)&dword_1800CC77C,
          v25,
          v26,
          (__int64)&v61);
      }
      v27 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, v27) )
      {
        v29 = GetLastError();
        v4 = ERROR_HR_FROM_WIN32(v29);
        if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
          goto LABEL_77;
        v33 = (char *)&dword_1800CC7B4;
        goto LABEL_42;
      }
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &nLengthNeeded) )
    {
      v35 = nLengthNeeded;
    }
    else
    {
      v34 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v34);
      v35 = nLengthNeeded;
      if ( !nLengthNeeded || v4 != -2147024774 )
      {
        if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
          goto LABEL_77;
        v33 = byte_1800CC7ED;
        goto LABEL_42;
      }
    }
    v36 = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(&v61, v35);
    utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
      &TokenInformation,
      v36);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v61);
    v37 = (LPWCH *)TokenInformation;
    if ( !TokenInformation )
    {
      v4 = -2147024882;
      if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
      {
        v61 = -2147024882;
        v48 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v38,
          (unsigned int)byte_1800CC823,
          v39,
          v40,
          (__int64)&v48,
          (__int64)&v61);
      }
      goto LABEL_77;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, nLengthNeeded, &nLengthNeeded) )
    {
      pListOfExplicitEntries.grfAccessPermissions = a2;
      pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
      pListOfExplicitEntries.grfInheritance = 3;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
      pListOfExplicitEntries.Trustee.ptstrName = *v37;
      v42 = hMem;
      hMem = 0;
      if ( v42 )
        LocalFree(v42);
      v43 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, (PACL *)&hMem);
      if ( !v43 )
      {
        if ( InitializeSecurityDescriptor(SecurityDescriptor, 1u) )
        {
          if ( SetSecurityDescriptorDacl(SecurityDescriptor, 1, (PACL)hMem, 0) )
          {
            if ( SetKernelObjectSecurity(v6, 4u, SecurityDescriptor) )
            {
              v4 = 0;
              goto LABEL_77;
            }
            v46 = GetLastError();
            v4 = ERROR_HR_FROM_WIN32(v46);
            if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
            {
              v11 = &byte_1800CC947;
              goto LABEL_7;
            }
          }
          else
          {
            v45 = GetLastError();
            v4 = ERROR_HR_FROM_WIN32(v45);
            if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
            {
              v11 = byte_1800CC90D;
              goto LABEL_7;
            }
          }
        }
        else
        {
          v44 = GetLastError();
          v4 = ERROR_HR_FROM_WIN32(v44);
          if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
          {
            v11 = (char *)&dword_1800CC8CC;
            goto LABEL_7;
          }
        }
        goto LABEL_77;
      }
      v4 = ERROR_HR_FROM_WIN32(v43);
      if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        goto LABEL_77;
      v33 = byte_1800CC899;
    }
    else
    {
      v41 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v41);
      if ( (unsigned int)dword_1800DE000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
        goto LABEL_77;
      v33 = byte_1800CC863;
    }
LABEL_42:
    v61 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v30,
      (_DWORD)v33,
      v31,
      v32,
      (__int64)&v61);
    goto LABEL_77;
  }
  if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v11 = (char *)&word_1800CC64E;
    goto LABEL_7;
  }
LABEL_77:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&Handle);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&TokenInformation);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&hMem);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&pSecurityDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800678d4  mov     [rsp-8+arg_8], rbx
0x1800678d9  push    rbp
0x1800678da  push    rsi
0x1800678db  push    rdi
0x1800678dc  push    r12
0x1800678de  push    r13
0x1800678e0  push    r14
0x1800678e2  push    r15
0x1800678e4  lea     rbp, [rsp-27h]
0x1800678e9  sub     rsp, 0E0h
0x1800678f0  mov     r15d, edx
0x1800678f3  mov     r14, rcx
0x1800678f6  xor     r12d, r12d
0x1800678f9  mov     [rbp+57h+nLengthNeeded], r12d
0x1800678fd  mov     [rbp+57h+pSecurityDescriptor], r12
0x180067901  xorps   xmm0, xmm0
0x180067904  xor     eax, eax
0x180067906  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18006790a  movups  [rbp+57h+var_50], xmm0
0x18006790e  mov     [rbp+57h+var_40], rax
0x180067912  mov     [rbp+57h+pDacl], r12
0x180067916  mov     [rbp+57h+hMem], r12
0x18006791a  mov     [rbp+57h+TokenHandle], r12
0x18006791e  mov     [rbp+57h+TokenInformation], r12
0x180067922  mov     [rbp+57h+bDaclPresent], r12d
0x180067926  mov     [rbp+57h+bDaclDefaulted], r12d
0x18006792a  mov     [rbp+57h+Handle], r12
0x18006792e  test    rcx, rcx
0x180067931  jnz     short loc_18006793D
0x180067933  mov     ebx, 80070057h
0x180067938  jmp     loc_18006803A
0x18006793d  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x180067942  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18006794a  mov     eax, 3
0x18006794f  mov     [rsp+110h+dwCreationDisposition], eax; dwCreationDisposition
0x180067953  xor     r9d, r9d; lpSecurityAttributes
0x180067956  mov     r8d, eax; dwShareMode
0x180067959  mov     edx, 60000h; dwDesiredAccess
0x18006795e  call    cs:__imp_CreateFileW
0x180067965  nop     dword ptr [rax+rax+00h]
0x18006796a  mov     rdx, rax
0x18006796d  lea     rcx, [rbp+57h+Handle]
0x180067971  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180067976  mov     rdi, [rbp+57h+Handle]
0x18006797a  lea     rax, [rdi+1]
0x18006797e  mov     r13d, 1
0x180067984  cmp     rax, r13
0x180067987  ja      short loc_1800679EF
0x180067989  call    cs:__imp_GetLastError
0x180067990  nop     dword ptr [rax+rax+00h]
0x180067995  mov     ecx, eax; unsigned int
0x180067997  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006799c  mov     ebx, eax
0x18006799e  mov     eax, cs:dword_1800DE000
0x1800679a4  cmp     eax, 2
0x1800679a7  jbe     loc_18006803A
0x1800679ad  lea     edx, [r13+7]
0x1800679b1  lea     rcx, dword_1800DE000
0x1800679b8  call    _tlgKeywordOn
0x1800679bd  test    al, al
0x1800679bf  jz      loc_18006803A
0x1800679c5  lea     rdx, byte_1800CC611
0x1800679cc  lea     rax, [rbp+57h+arg_18]
0x1800679d0  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x1800679d5  lea     rax, [rbp+57h+var_D0]
0x1800679d9  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x1800679de  mov     [rbp+57h+var_D0], r14
0x1800679e2  mov     [rbp+57h+arg_18], ebx
0x1800679e5  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800679ea  jmp     loc_18006803A
0x1800679ef  mov     rdx, rdi; void *
0x1800679f2  mov     rcx, r14; wchar_t *
0x1800679f5  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x1800679fa  mov     ebx, eax
0x1800679fc  test    eax, eax
0x1800679fe  jns     short loc_180067A31
0x180067a00  mov     ecx, cs:dword_1800DE000
0x180067a06  cmp     ecx, 2
0x180067a09  jbe     loc_18006803A
0x180067a0f  mov     edx, 8
0x180067a14  lea     rcx, dword_1800DE000
0x180067a1b  call    _tlgKeywordOn
0x180067a20  test    al, al
0x180067a22  jz      loc_18006803A
0x180067a28  lea     rdx, word_1800CC64E
0x180067a2f  jmp     short loc_1800679CC
0x180067a31  lea     rax, [rbp+57h+nLengthNeeded]
0x180067a35  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpnLengthNeeded
0x180067a3a  xor     r9d, r9d; nLength
0x180067a3d  xor     r8d, r8d; pSecurityDescriptor
0x180067a40  lea     esi, [r9+4]
0x180067a44  mov     edx, esi; RequestedInformation
0x180067a46  mov     rcx, rdi; Handle
0x180067a49  call    cs:__imp_GetKernelObjectSecurity
0x180067a50  nop     dword ptr [rax+rax+00h]
0x180067a55  test    eax, eax
0x180067a57  jnz     short loc_180067AB1
0x180067a59  call    cs:__imp_GetLastError
0x180067a60  nop     dword ptr [rax+rax+00h]
0x180067a65  mov     ecx, eax; unsigned int
0x180067a67  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067a6c  mov     ebx, eax
0x180067a6e  mov     eax, [rbp+57h+nLengthNeeded]
0x180067a71  test    eax, eax
0x180067a73  jz      short loc_180067A7D
0x180067a75  cmp     ebx, 8007007Ah
0x180067a7b  jz      short loc_180067AB4
0x180067a7d  mov     eax, cs:dword_1800DE000
0x180067a83  cmp     eax, 2
0x180067a86  jbe     loc_18006803A
0x180067a8c  mov     edx, 8
0x180067a91  lea     rcx, dword_1800DE000
0x180067a98  call    _tlgKeywordOn
0x180067a9d  test    al, al
0x180067a9f  jz      loc_18006803A
0x180067aa5  lea     rdx, byte_1800CC687
0x180067aac  jmp     loc_1800679CC
0x180067ab1  mov     eax, [rbp+57h+nLengthNeeded]
0x180067ab4  mov     edx, eax
0x180067ab6  lea     rcx, [rbp+57h+arg_18]
0x180067aba  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180067abf  mov     rdx, rax
0x180067ac2  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180067ac6  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180067acb  lea     rcx, [rbp+57h+arg_18]; void *
0x180067acf  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180067ad4  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180067ad8  test    rbx, rbx
0x180067adb  jnz     short loc_180067B33
0x180067add  mov     ebx, 8007000Eh
0x180067ae2  mov     eax, cs:dword_1800DE000
0x180067ae8  cmp     eax, 2
0x180067aeb  jbe     loc_18006803A
0x180067af1  mov     edx, 8
0x180067af6  lea     rcx, dword_1800DE000
0x180067afd  call    _tlgKeywordOn
0x180067b02  test    al, al
0x180067b04  jz      loc_18006803A
0x180067b0a  mov     [rbp+57h+arg_18], 8007000Eh
0x180067b11  mov     [rbp+57h+var_D0], r14
0x180067b15  lea     rax, [rbp+57h+arg_18]
0x180067b19  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180067b1e  lea     rax, [rbp+57h+var_D0]
0x180067b22  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180067b27  lea     rdx, word_1800CC6C6
0x180067b2e  jmp     loc_1800679E5
0x180067b33  lea     rax, [rbp+57h+nLengthNeeded]
0x180067b37  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpnLengthNeeded
0x180067b3c  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180067b40  mov     r8, rbx; pSecurityDescriptor
0x180067b43  mov     edx, esi; RequestedInformation
0x180067b45  mov     rcx, rdi; Handle
0x180067b48  call    cs:__imp_GetKernelObjectSecurity
0x180067b4f  nop     dword ptr [rax+rax+00h]
0x180067b54  test    eax, eax
0x180067b56  jnz     short loc_180067BA1
0x180067b58  call    cs:__imp_GetLastError
0x180067b5f  nop     dword ptr [rax+rax+00h]
0x180067b64  mov     ecx, eax; unsigned int
0x180067b66  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067b6b  mov     ebx, eax
0x180067b6d  mov     eax, cs:dword_1800DE000
0x180067b73  cmp     eax, 2
0x180067b76  jbe     loc_18006803A
0x180067b7c  mov     edx, 8
0x180067b81  lea     rcx, dword_1800DE000
0x180067b88  call    _tlgKeywordOn
0x180067b8d  test    al, al
0x180067b8f  jz      loc_18006803A
0x180067b95  lea     rdx, byte_1800CC703
0x180067b9c  jmp     loc_1800679CC
0x180067ba1  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180067ba5  lea     r8, [rbp+57h+pDacl]; pDacl
0x180067ba9  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180067bad  mov     rcx, rbx; pSecurityDescriptor
0x180067bb0  call    cs:__imp_GetSecurityDescriptorDacl
0x180067bb7  nop     dword ptr [rax+rax+00h]
0x180067bbc  test    eax, eax
0x180067bbe  jnz     short loc_180067C09
0x180067bc0  call    cs:__imp_GetLastError
0x180067bc7  nop     dword ptr [rax+rax+00h]
0x180067bcc  mov     ecx, eax; unsigned int
0x180067bce  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067bd3  mov     ebx, eax
0x180067bd5  mov     eax, cs:dword_1800DE000
0x180067bdb  cmp     eax, 2
0x180067bde  jbe     loc_18006803A
0x180067be4  mov     edx, 8
0x180067be9  lea     rcx, dword_1800DE000
0x180067bf0  call    _tlgKeywordOn
0x180067bf5  test    al, al
0x180067bf7  jz      loc_18006803A
0x180067bfd  lea     rdx, word_1800CC742
0x180067c04  jmp     loc_1800679CC
0x180067c09  cmp     [rbp+57h+bDaclPresent], r12d
0x180067c0d  jnz     short loc_180067C13
0x180067c0f  mov     [rbp+57h+pDacl], r12
0x180067c13  lea     rcx, [rbp+57h+TokenHandle]
0x180067c17  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180067c1c  mov     rbx, rax
0x180067c1f  call    cs:__imp_GetCurrentThread
0x180067c26  nop     dword ptr [rax+rax+00h]
0x180067c2b  mov     r9, rbx; TokenHandle
0x180067c2e  xor     r8d, r8d; OpenAsSelf
0x180067c31  lea     esi, [r8+8]
0x180067c35  mov     edx, esi; DesiredAccess
0x180067c37  mov     rcx, rax; ThreadHandle
0x180067c3a  call    cs:__imp_OpenThreadToken
0x180067c41  nop     dword ptr [rax+rax+00h]
0x180067c46  test    eax, eax
0x180067c48  jnz     loc_180067D22
0x180067c4e  call    cs:__imp_GetLastError
0x180067c55  nop     dword ptr [rax+rax+00h]
0x180067c5a  mov     ecx, eax; unsigned int
0x180067c5c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067c61  mov     r8d, eax
0x180067c64  mov     ecx, cs:dword_1800DE000
0x180067c6a  cmp     ecx, 3
0x180067c6d  jbe     short loc_180067C9A
0x180067c6f  mov     edx, esi
0x180067c71  lea     rcx, dword_1800DE000
0x180067c78  call    _tlgKeywordOn
0x180067c7d  test    al, al
0x180067c7f  jz      short loc_180067C9A
0x180067c81  mov     [rbp+57h+arg_18], r8d
0x180067c85  lea     rax, [rbp+57h+arg_18]
0x180067c89  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180067c8e  lea     rdx, dword_1800CC77C
0x180067c95  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180067c9a  lea     rcx, [rbp+57h+TokenHandle]
0x180067c9e  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180067ca3  mov     rbx, rax
0x180067ca6  call    cs:__imp_GetCurrentProcess
0x180067cad  nop     dword ptr [rax+rax+00h]
0x180067cb2  mov     r8, rbx; TokenHandle
0x180067cb5  mov     edx, esi; DesiredAccess
0x180067cb7  mov     rcx, rax; ProcessHandle
0x180067cba  call    cs:__imp_OpenProcessToken
0x180067cc1  nop     dword ptr [rax+rax+00h]
0x180067cc6  test    eax, eax
0x180067cc8  jnz     short loc_180067D22
0x180067cca  call    cs:__imp_GetLastError
0x180067cd1  nop     dword ptr [rax+rax+00h]
0x180067cd6  mov     ecx, eax; unsigned int
0x180067cd8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067cdd  mov     ebx, eax
0x180067cdf  mov     eax, cs:dword_1800DE000
0x180067ce5  cmp     eax, 2
0x180067ce8  jbe     loc_18006803A
0x180067cee  mov     rdx, rsi
0x180067cf1  lea     rcx, dword_1800DE000
0x180067cf8  call    _tlgKeywordOn
0x180067cfd  test    al, al
0x180067cff  jz      loc_18006803A
0x180067d05  lea     rdx, dword_1800CC7B4
0x180067d0c  lea     rax, [rbp+57h+arg_18]
0x180067d10  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180067d15  mov     [rbp+57h+arg_18], ebx
0x180067d18  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180067d1d  jmp     loc_18006803A
0x180067d22  lea     rax, [rbp+57h+nLengthNeeded]
0x180067d26  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; ReturnLength
0x180067d2b  xor     r9d, r9d; TokenInformationLength
0x180067d2e  xor     r8d, r8d; TokenInformation
0x180067d31  mov     edx, r13d; TokenInformationClass
0x180067d34  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180067d38  call    cs:__imp_GetTokenInformation
0x180067d3f  nop     dword ptr [rax+rax+00h]
0x180067d44  test    eax, eax
0x180067d46  jnz     short loc_180067D9E
0x180067d48  call    cs:__imp_GetLastError
0x180067d4f  nop     dword ptr [rax+rax+00h]
0x180067d54  mov     ecx, eax; unsigned int
0x180067d56  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180067d5b  mov     ebx, eax
0x180067d5d  mov     eax, [rbp+57h+nLengthNeeded]
0x180067d60  test    eax, eax
0x180067d62  jz      short loc_180067D6C
0x180067d64  cmp     ebx, 8007007Ah
0x180067d6a  jz      short loc_180067DA1
0x180067d6c  mov     eax, cs:dword_1800DE000
0x180067d72  cmp     eax, 2
0x180067d75  jbe     loc_18006803A
0x180067d7b  mov     rdx, rsi
0x180067d7e  lea     rcx, dword_1800DE000
0x180067d85  call    _tlgKeywordOn
0x180067d8a  test    al, al
0x180067d8c  jz      loc_18006803A
0x180067d92  lea     rdx, byte_1800CC7ED
0x180067d99  jmp     loc_180067D0C
0x180067d9e  mov     eax, [rbp+57h+nLengthNeeded]
0x180067da1  mov     edx, eax
0x180067da3  lea     rcx, [rbp+57h+arg_18]
0x180067da7  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180067dac  mov     rdx, rax
0x180067daf  lea     rcx, [rbp+57h+TokenInformation]
0x180067db3  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180067db8  lea     rcx, [rbp+57h+arg_18]; void *
0x180067dbc  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180067dc1  mov     rbx, [rbp+57h+TokenInformation]
  ... truncated ...
```
