# UtilAddAccessToPath(wchar_t const *,ulong)

- ea: `0x18006498c`
- end: `0x1800650a4`
- name: `?UtilAddAccessToPath@@YAJPEB_WK@Z`
- size: `1816`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180063dc4`
- `0x18008b42c`

## callees

- `0x18000716c`
- `0x1800072cc`
- `0x180007e10`
- `0x180007e34`
- `0x18001c650`
- `0x18001daa8`
- `0x180023dc4`
- `0x180023e8c`
- `0x18002bed4`
- `0x18002cdd0`
- `0x1800303dc`
- `0x180045184`
- `0x18006498c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064cbc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064cbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180064ca7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064d2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006501a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064cca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006501a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064a16`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064a16`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180064f68`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180064f68`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180064fc1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180064fc1`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180065010`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180065010`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180064c44`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180064c44`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064af5`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064be8`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064af5`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180064be8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064d9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064e8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064d9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064f07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064f07`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180064f1c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180064f1c`

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
  void *v11; // rdx
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
  void *v33; // rdx
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
    if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
    {
      v11 = &unk_1800C7561;
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
        if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
        {
          v11 = &unk_1800C75D7;
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
      if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v61 = -2147024882;
        v48 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&unk_1800C7616,
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
      if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v11 = &unk_1800C7653;
        goto LABEL_7;
      }
      goto LABEL_77;
    }
    if ( !GetSecurityDescriptorDacl(v15, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v20 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v20);
      if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v11 = &unk_1800C7692;
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
      if ( (unsigned int)dword_1800D9000 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v61 = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)&unk_1800C76CC,
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
        if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
          goto LABEL_77;
        v33 = &unk_1800C7704;
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
        if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
          goto LABEL_77;
        v33 = &unk_1800C773D;
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
      if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
      {
        v61 = -2147024882;
        v48 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v38,
          (unsigned int)&unk_1800C7773,
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
            if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
            {
              v11 = &unk_1800C7897;
              goto LABEL_7;
            }
          }
          else
          {
            v45 = GetLastError();
            v4 = ERROR_HR_FROM_WIN32(v45);
            if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
            {
              v11 = &unk_1800C785D;
              goto LABEL_7;
            }
          }
        }
        else
        {
          v44 = GetLastError();
          v4 = ERROR_HR_FROM_WIN32(v44);
          if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
          {
            v11 = &unk_1800C781C;
            goto LABEL_7;
          }
        }
        goto LABEL_77;
      }
      v4 = ERROR_HR_FROM_WIN32(v43);
      if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
        goto LABEL_77;
      v33 = &unk_1800C77E9;
    }
    else
    {
      v41 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v41);
      if ( (unsigned int)dword_1800D9000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
        goto LABEL_77;
      v33 = &unk_1800C77B3;
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
  if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v11 = &unk_1800C759E;
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
0x18006498c  mov     [rsp-8+arg_8], rbx
0x180064991  push    rbp
0x180064992  push    rsi
0x180064993  push    rdi
0x180064994  push    r12
0x180064996  push    r13
0x180064998  push    r14
0x18006499a  push    r15
0x18006499c  lea     rbp, [rsp-27h]
0x1800649a1  sub     rsp, 0E0h
0x1800649a8  mov     r15d, edx
0x1800649ab  mov     r14, rcx
0x1800649ae  xor     r12d, r12d
0x1800649b1  mov     [rbp+57h+nLengthNeeded], r12d
0x1800649b5  mov     [rbp+57h+pSecurityDescriptor], r12
0x1800649b9  xorps   xmm0, xmm0
0x1800649bc  xor     eax, eax
0x1800649be  movups  [rbp+57h+SecurityDescriptor], xmm0
0x1800649c2  movups  [rbp+57h+var_50], xmm0
0x1800649c6  mov     [rbp+57h+var_40], rax
0x1800649ca  mov     [rbp+57h+pDacl], r12
0x1800649ce  mov     [rbp+57h+hMem], r12
0x1800649d2  mov     [rbp+57h+TokenHandle], r12
0x1800649d6  mov     [rbp+57h+TokenInformation], r12
0x1800649da  mov     [rbp+57h+bDaclPresent], r12d
0x1800649de  mov     [rbp+57h+bDaclDefaulted], r12d
0x1800649e2  mov     [rbp+57h+Handle], r12
0x1800649e6  test    rcx, rcx
0x1800649e9  jnz     short loc_1800649F5
0x1800649eb  mov     ebx, 80070057h
0x1800649f0  jmp     loc_180065056
0x1800649f5  mov     [rsp+110h+hTemplateFile], r12; hTemplateFile
0x1800649fa  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180064a02  mov     eax, 3
0x180064a07  mov     [rsp+110h+dwCreationDisposition], eax; dwCreationDisposition
0x180064a0b  xor     r9d, r9d; lpSecurityAttributes
0x180064a0e  mov     r8d, eax; dwShareMode
0x180064a11  mov     edx, 60000h; dwDesiredAccess
0x180064a16  call    cs:__imp_CreateFileW
0x180064a1c  mov     rdx, rax
0x180064a1f  lea     rcx, [rbp+57h+Handle]
0x180064a23  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180064a28  mov     rdi, [rbp+57h+Handle]
0x180064a2c  lea     rax, [rdi+1]
0x180064a30  mov     r13d, 1
0x180064a36  cmp     rax, r13
0x180064a39  ja      short loc_180064A9B
0x180064a3b  call    cs:__imp_GetLastError
0x180064a41  mov     ecx, eax; unsigned int
0x180064a43  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064a48  mov     ebx, eax
0x180064a4a  mov     eax, cs:dword_1800D9000
0x180064a50  cmp     eax, 2
0x180064a53  jbe     loc_180065056
0x180064a59  lea     edx, [r13+7]
0x180064a5d  lea     rcx, dword_1800D9000
0x180064a64  call    _tlgKeywordOn
0x180064a69  test    al, al
0x180064a6b  jz      loc_180065056
0x180064a71  lea     rdx, unk_1800C7561
0x180064a78  lea     rax, [rbp+57h+arg_18]
0x180064a7c  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180064a81  lea     rax, [rbp+57h+var_D0]
0x180064a85  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064a8a  mov     [rbp+57h+var_D0], r14
0x180064a8e  mov     [rbp+57h+arg_18], ebx
0x180064a91  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180064a96  jmp     loc_180065056
0x180064a9b  mov     rdx, rdi; void *
0x180064a9e  mov     rcx, r14; wchar_t *
0x180064aa1  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180064aa6  mov     ebx, eax
0x180064aa8  test    eax, eax
0x180064aaa  jns     short loc_180064ADD
0x180064aac  mov     ecx, cs:dword_1800D9000
0x180064ab2  cmp     ecx, 2
0x180064ab5  jbe     loc_180065056
0x180064abb  mov     edx, 8
0x180064ac0  lea     rcx, dword_1800D9000
0x180064ac7  call    _tlgKeywordOn
0x180064acc  test    al, al
0x180064ace  jz      loc_180065056
0x180064ad4  lea     rdx, unk_1800C759E
0x180064adb  jmp     short loc_180064A78
0x180064add  lea     rax, [rbp+57h+nLengthNeeded]
0x180064ae1  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpnLengthNeeded
0x180064ae6  xor     r9d, r9d; nLength
0x180064ae9  xor     r8d, r8d; pSecurityDescriptor
0x180064aec  lea     esi, [r9+4]
0x180064af0  mov     edx, esi; RequestedInformation
0x180064af2  mov     rcx, rdi; Handle
0x180064af5  call    cs:__imp_GetKernelObjectSecurity
0x180064afb  test    eax, eax
0x180064afd  jnz     short loc_180064B51
0x180064aff  call    cs:__imp_GetLastError
0x180064b05  mov     ecx, eax; unsigned int
0x180064b07  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064b0c  mov     ebx, eax
0x180064b0e  mov     eax, [rbp+57h+nLengthNeeded]
0x180064b11  test    eax, eax
0x180064b13  jz      short loc_180064B1D
0x180064b15  cmp     ebx, 8007007Ah
0x180064b1b  jz      short loc_180064B54
0x180064b1d  mov     eax, cs:dword_1800D9000
0x180064b23  cmp     eax, 2
0x180064b26  jbe     loc_180065056
0x180064b2c  mov     edx, 8
0x180064b31  lea     rcx, dword_1800D9000
0x180064b38  call    _tlgKeywordOn
0x180064b3d  test    al, al
0x180064b3f  jz      loc_180065056
0x180064b45  lea     rdx, unk_1800C75D7
0x180064b4c  jmp     loc_180064A78
0x180064b51  mov     eax, [rbp+57h+nLengthNeeded]
0x180064b54  mov     edx, eax
0x180064b56  lea     rcx, [rbp+57h+arg_18]
0x180064b5a  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180064b5f  mov     rdx, rax
0x180064b62  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x180064b66  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180064b6b  lea     rcx, [rbp+57h+arg_18]; void *
0x180064b6f  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180064b74  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180064b78  test    rbx, rbx
0x180064b7b  jnz     short loc_180064BD3
0x180064b7d  mov     ebx, 8007000Eh
0x180064b82  mov     eax, cs:dword_1800D9000
0x180064b88  cmp     eax, 2
0x180064b8b  jbe     loc_180065056
0x180064b91  mov     edx, 8
0x180064b96  lea     rcx, dword_1800D9000
0x180064b9d  call    _tlgKeywordOn
0x180064ba2  test    al, al
0x180064ba4  jz      loc_180065056
0x180064baa  mov     [rbp+57h+arg_18], 8007000Eh
0x180064bb1  mov     [rbp+57h+var_D0], r14
0x180064bb5  lea     rax, [rbp+57h+arg_18]
0x180064bb9  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180064bbe  lea     rax, [rbp+57h+var_D0]
0x180064bc2  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064bc7  lea     rdx, unk_1800C7616
0x180064bce  jmp     loc_180064A91
0x180064bd3  lea     rax, [rbp+57h+nLengthNeeded]
0x180064bd7  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; lpnLengthNeeded
0x180064bdc  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180064be0  mov     r8, rbx; pSecurityDescriptor
0x180064be3  mov     edx, esi; RequestedInformation
0x180064be5  mov     rcx, rdi; Handle
0x180064be8  call    cs:__imp_GetKernelObjectSecurity
0x180064bee  test    eax, eax
0x180064bf0  jnz     short loc_180064C35
0x180064bf2  call    cs:__imp_GetLastError
0x180064bf8  mov     ecx, eax; unsigned int
0x180064bfa  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064bff  mov     ebx, eax
0x180064c01  mov     eax, cs:dword_1800D9000
0x180064c07  cmp     eax, 2
0x180064c0a  jbe     loc_180065056
0x180064c10  mov     edx, 8
0x180064c15  lea     rcx, dword_1800D9000
0x180064c1c  call    _tlgKeywordOn
0x180064c21  test    al, al
0x180064c23  jz      loc_180065056
0x180064c29  lea     rdx, unk_1800C7653
0x180064c30  jmp     loc_180064A78
0x180064c35  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180064c39  lea     r8, [rbp+57h+pDacl]; pDacl
0x180064c3d  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180064c41  mov     rcx, rbx; pSecurityDescriptor
0x180064c44  call    cs:__imp_GetSecurityDescriptorDacl
0x180064c4a  test    eax, eax
0x180064c4c  jnz     short loc_180064C91
0x180064c4e  call    cs:__imp_GetLastError
0x180064c54  mov     ecx, eax; unsigned int
0x180064c56  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064c5b  mov     ebx, eax
0x180064c5d  mov     eax, cs:dword_1800D9000
0x180064c63  cmp     eax, 2
0x180064c66  jbe     loc_180065056
0x180064c6c  mov     edx, 8
0x180064c71  lea     rcx, dword_1800D9000
0x180064c78  call    _tlgKeywordOn
0x180064c7d  test    al, al
0x180064c7f  jz      loc_180065056
0x180064c85  lea     rdx, unk_1800C7692
0x180064c8c  jmp     loc_180064A78
0x180064c91  cmp     [rbp+57h+bDaclPresent], r12d
0x180064c95  jnz     short loc_180064C9B
0x180064c97  mov     [rbp+57h+pDacl], r12
0x180064c9b  lea     rcx, [rbp+57h+TokenHandle]
0x180064c9f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180064ca4  mov     rbx, rax
0x180064ca7  call    cs:__imp_GetCurrentThread
0x180064cad  mov     r9, rbx; TokenHandle
0x180064cb0  xor     r8d, r8d; OpenAsSelf
0x180064cb3  lea     esi, [r8+8]
0x180064cb7  mov     edx, esi; DesiredAccess
0x180064cb9  mov     rcx, rax; ThreadHandle
0x180064cbc  call    cs:__imp_OpenThreadToken
0x180064cc2  test    eax, eax
0x180064cc4  jnz     loc_180064D86
0x180064cca  call    cs:__imp_GetLastError
0x180064cd0  mov     ecx, eax; unsigned int
0x180064cd2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064cd7  mov     r8d, eax
0x180064cda  mov     ecx, cs:dword_1800D9000
0x180064ce0  cmp     ecx, 3
0x180064ce3  jbe     short loc_180064D10
0x180064ce5  mov     edx, esi
0x180064ce7  lea     rcx, dword_1800D9000
0x180064cee  call    _tlgKeywordOn
0x180064cf3  test    al, al
0x180064cf5  jz      short loc_180064D10
0x180064cf7  mov     [rbp+57h+arg_18], r8d
0x180064cfb  lea     rax, [rbp+57h+arg_18]
0x180064cff  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064d04  lea     rdx, unk_1800C76CC
0x180064d0b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180064d10  lea     rcx, [rbp+57h+TokenHandle]
0x180064d14  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180064d19  mov     rbx, rax
0x180064d1c  call    cs:__imp_GetCurrentProcess
0x180064d22  mov     r8, rbx; TokenHandle
0x180064d25  mov     edx, esi; DesiredAccess
0x180064d27  mov     rcx, rax; ProcessHandle
0x180064d2a  call    cs:__imp_OpenProcessToken
0x180064d30  test    eax, eax
0x180064d32  jnz     short loc_180064D86
0x180064d34  call    cs:__imp_GetLastError
0x180064d3a  mov     ecx, eax; unsigned int
0x180064d3c  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064d41  mov     ebx, eax
0x180064d43  mov     eax, cs:dword_1800D9000
0x180064d49  cmp     eax, 2
0x180064d4c  jbe     loc_180065056
0x180064d52  mov     rdx, rsi
0x180064d55  lea     rcx, dword_1800D9000
0x180064d5c  call    _tlgKeywordOn
0x180064d61  test    al, al
0x180064d63  jz      loc_180065056
0x180064d69  lea     rdx, unk_1800C7704
0x180064d70  lea     rax, [rbp+57h+arg_18]
0x180064d74  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x180064d79  mov     [rbp+57h+arg_18], ebx
0x180064d7c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180064d81  jmp     loc_180065056
0x180064d86  lea     rax, [rbp+57h+nLengthNeeded]
0x180064d8a  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; ReturnLength
0x180064d8f  xor     r9d, r9d; TokenInformationLength
0x180064d92  xor     r8d, r8d; TokenInformation
0x180064d95  mov     edx, r13d; TokenInformationClass
0x180064d98  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180064d9c  call    cs:__imp_GetTokenInformation
0x180064da2  test    eax, eax
0x180064da4  jnz     short loc_180064DF6
0x180064da6  call    cs:__imp_GetLastError
0x180064dac  mov     ecx, eax; unsigned int
0x180064dae  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180064db3  mov     ebx, eax
0x180064db5  mov     eax, [rbp+57h+nLengthNeeded]
0x180064db8  test    eax, eax
0x180064dba  jz      short loc_180064DC4
0x180064dbc  cmp     ebx, 8007007Ah
0x180064dc2  jz      short loc_180064DF9
0x180064dc4  mov     eax, cs:dword_1800D9000
0x180064dca  cmp     eax, 2
0x180064dcd  jbe     loc_180065056
0x180064dd3  mov     rdx, rsi
0x180064dd6  lea     rcx, dword_1800D9000
0x180064ddd  call    _tlgKeywordOn
0x180064de2  test    al, al
0x180064de4  jz      loc_180065056
0x180064dea  lea     rdx, unk_1800C773D
0x180064df1  jmp     loc_180064D70
0x180064df6  mov     eax, [rbp+57h+nLengthNeeded]
0x180064df9  mov     edx, eax
0x180064dfb  lea     rcx, [rbp+57h+arg_18]
0x180064dff  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x180064e04  mov     rdx, rax
0x180064e07  lea     rcx, [rbp+57h+TokenInformation]
0x180064e0b  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x180064e10  lea     rcx, [rbp+57h+arg_18]; void *
0x180064e14  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x180064e19  mov     rbx, [rbp+57h+TokenInformation]
0x180064e1d  test    rbx, rbx
0x180064e20  jnz     short loc_180064E76
0x180064e22  mov     ebx, 8007000Eh
0x180064e27  mov     eax, cs:dword_1800D9000
0x180064e2d  cmp     eax, 2
0x180064e30  jbe     loc_180065056
0x180064e36  mov     rdx, rsi
0x180064e39  lea     rcx, dword_1800D9000
0x180064e40  call    _tlgKeywordOn
0x180064e45  test    al, al
0x180064e47  jz      loc_180065056
0x180064e4d  mov     [rbp+57h+arg_18], 8007000Eh
0x180064e54  mov     [rbp+57h+var_D0], r14
0x180064e58  lea     rax, [rbp+57h+arg_18]
0x180064e5c  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x180064e61  lea     rax, [rbp+57h+var_D0]
  ... truncated ...
```
