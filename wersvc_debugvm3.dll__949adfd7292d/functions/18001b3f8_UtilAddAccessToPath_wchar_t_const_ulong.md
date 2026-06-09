# UtilAddAccessToPath(wchar_t const *,ulong)

- ea: `0x18001b3f8`
- end: `0x18001bcc6`
- name: `?UtilAddAccessToPath@@YAJPEB_WK@Z`
- size: `2254`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800167a4`

## callees

- `0x18000113c`
- `0x18000134c`
- `0x1800029d0`
- `0x1800029f4`
- `0x180002a00`
- `0x180002a24`
- `0x180002ff0`
- `0x180007cf8`
- `0x1800106f4`
- `0x18001b3f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001b821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001b821`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b788`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001b775`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001b832`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001b832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b8f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb9c`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18001b583`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18001b67c`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18001b583`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18001b67c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001b6f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001b6f3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001baac`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001baac`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001bb21`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001bb21`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001b8e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001b993`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001b8e8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001b993`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18001bb92`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18001bb92`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b49b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b49b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bc7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bc90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bc90`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001ba4a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18001ba4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilAddAccessToPath(const wchar_t *a1, const struct std::nothrow_t *a2)
{
  void *v3; // r13
  LPWCH *v4; // r12
  char *FileW; // r15
  signed int v6; // ebx
  signed int LastError; // eax
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  __int16 *v11; // rdx
  signed int v12; // eax
  DWORD v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  void **v16; // rbx
  HANDLE CurrentThread; // rax
  signed int v18; // eax
  signed int v19; // ecx
  void **v20; // rbx
  HANDLE CurrentProcess; // rax
  signed int v22; // eax
  __int16 *v23; // rdx
  signed int v24; // eax
  DWORD v25; // eax
  signed int v26; // eax
  HLOCAL v27; // rcx
  signed int v28; // eax
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nLengthNeeded; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v35; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+70h] [rbp-90h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  char *v44; // [rsp+D8h] [rbp-28h]
  _BYTE v45[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]

  nLengthNeeded = 0;
  v3 = 0;
  v35 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v43 = 0;
  pDacl = 0;
  hMem = 0;
  TokenHandle = 0;
  v4 = 0;
  v33 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  FileW = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_140;
  }
  FileW = (char *)CreateFileW(a1, 0x60000u, 3u, 0, 3u, 0x2200000u, 0);
  v44 = FileW;
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    if ( (unsigned int)dword_180047000 > 2 )
    {
      v10 = qword_180047018;
      if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        LODWORD(v33) = v6;
        v11 = (__int16 *)byte_18003FA7B;
LABEL_139:
        v35 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v10,
          (_DWORD)v11,
          v8,
          v9,
          (__int64)&v35,
          (__int64)&v33);
        goto LABEL_140;
      }
    }
    goto LABEL_140;
  }
  v6 = UtilVerifyFilePath(a1, FileW);
  if ( v6 >= 0 )
  {
    if ( GetKernelObjectSecurity(FileW, 4u, 0, 0, &nLengthNeeded) )
    {
      v13 = nLengthNeeded;
    }
    else
    {
      v12 = GetLastError();
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      v13 = nLengthNeeded;
      if ( !nLengthNeeded || v6 != -2147024774 )
      {
        if ( (unsigned int)dword_180047000 > 2 )
        {
          v10 = qword_180047018;
          if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
          {
            LODWORD(v33) = v6;
            v11 = (__int16 *)byte_18003FA03;
            goto LABEL_139;
          }
        }
        goto LABEL_140;
      }
    }
    v3 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v3 )
    {
      v6 = -2147024882;
      if ( (unsigned int)dword_180047000 <= 2 )
        goto LABEL_140;
      v10 = qword_180047018;
      if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
        goto LABEL_140;
      v11 = &word_18003F9C6;
      goto LABEL_138;
    }
    if ( !GetKernelObjectSecurity(FileW, 4u, v3, nLengthNeeded, &nLengthNeeded) )
    {
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_180047000 > 2 )
      {
        v10 = qword_180047018;
        if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
        {
          LODWORD(v33) = v6;
          v11 = (__int16 *)&byte_18003F987;
          goto LABEL_139;
        }
      }
      goto LABEL_140;
    }
    if ( !GetSecurityDescriptorDacl(v3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v15 = GetLastError();
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_180047000 > 2 )
      {
        v10 = qword_180047018;
        if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
        {
          LODWORD(v33) = v6;
          v11 = (__int16 *)byte_18003F94D;
          goto LABEL_139;
        }
      }
      goto LABEL_140;
    }
    if ( !bDaclPresent )
      pDacl = 0;
    v16 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, v16) )
      goto LABEL_153;
    v18 = GetLastError();
    v19 = v18;
    if ( v18 > 0 )
      v19 = (unsigned __int16)v18 | 0x80070000;
    if ( v19 >= 0 )
      v19 = -2147467259;
    if ( (unsigned int)dword_180047000 > 3 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      LODWORD(v33) = v19;
      v46 = &v33;
      v47 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180047000, byte_18003F915, 0, 0, 3, v45);
    }
    v20 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, v20) )
    {
LABEL_153:
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &nLengthNeeded) )
      {
        v25 = nLengthNeeded;
      }
      else
      {
        v24 = GetLastError();
        v6 = v24;
        if ( v24 > 0 )
          v6 = (unsigned __int16)v24 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        v25 = nLengthNeeded;
        if ( !nLengthNeeded || v6 != -2147024774 )
        {
          if ( (unsigned int)dword_180047000 <= 2
            || (qword_180047010 & 8) == 0
            || (qword_180047018 & 8) != qword_180047018 )
          {
            goto LABEL_140;
          }
          v23 = &word_18003F8A6;
          goto LABEL_72;
        }
      }
      v4 = (LPWCH *)operator new(v25, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v4 )
      {
        v4 = 0;
        v6 = -2147024882;
        if ( (unsigned int)dword_180047000 <= 2 )
          goto LABEL_140;
        v10 = qword_180047018;
        if ( (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
          goto LABEL_140;
        v11 = &word_18003F866;
LABEL_138:
        LODWORD(v33) = -2147024882;
        goto LABEL_139;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v4, nLengthNeeded, &nLengthNeeded) )
      {
        pListOfExplicitEntries.grfAccessPermissions = 65856;
        pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
        pListOfExplicitEntries.grfInheritance = 3;
        pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
        *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
        pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
        pListOfExplicitEntries.Trustee.ptstrName = *v4;
        v27 = hMem;
        hMem = 0;
        if ( v27 )
          LocalFree(v27);
        v28 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, (PACL *)&hMem);
        v6 = v28;
        if ( !v28 )
        {
          if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)hMem, 0) )
            {
              if ( SetKernelObjectSecurity(FileW, 4u, pSecurityDescriptor) )
              {
                v6 = 0;
                goto LABEL_140;
              }
              v31 = GetLastError();
              v6 = v31;
              if ( v31 > 0 )
                v6 = (unsigned __int16)v31 | 0x80070000;
              if ( v6 >= 0 )
                v6 = -2147467259;
              if ( (unsigned int)dword_180047000 > 2 )
              {
                v10 = qword_180047018;
                if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
                {
                  LODWORD(v33) = v6;
                  v11 = &word_18003F73E;
                  goto LABEL_139;
                }
              }
            }
            else
            {
              v30 = GetLastError();
              v6 = v30;
              if ( v30 > 0 )
                v6 = (unsigned __int16)v30 | 0x80070000;
              if ( v6 >= 0 )
                v6 = -2147467259;
              if ( (unsigned int)dword_180047000 > 2 )
              {
                v10 = qword_180047018;
                if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
                {
                  LODWORD(v33) = v6;
                  v11 = word_18003F782;
                  goto LABEL_139;
                }
              }
            }
          }
          else
          {
            v29 = GetLastError();
            v6 = v29;
            if ( v29 > 0 )
              v6 = (unsigned __int16)v29 | 0x80070000;
            if ( v6 >= 0 )
              v6 = -2147467259;
            if ( (unsigned int)dword_180047000 > 2 )
            {
              v10 = qword_180047018;
              if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
              {
                LODWORD(v33) = v6;
                v11 = (__int16 *)&dword_18003F7BC;
                goto LABEL_139;
              }
            }
          }
          goto LABEL_140;
        }
        if ( v28 > 0 )
          v6 = (unsigned __int16)v28 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        if ( (unsigned int)dword_180047000 <= 2
          || (qword_180047010 & 8) == 0
          || (qword_180047018 & 8) != qword_180047018 )
        {
          goto LABEL_140;
        }
        v23 = (__int16 *)byte_18003F7FD;
      }
      else
      {
        v26 = GetLastError();
        v6 = v26;
        if ( v26 > 0 )
          v6 = (unsigned __int16)v26 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        if ( (unsigned int)dword_180047000 <= 2
          || (qword_180047010 & 8) == 0
          || (qword_180047018 & 8) != qword_180047018 )
        {
          goto LABEL_140;
        }
        v23 = (__int16 *)&unk_18003F830;
      }
    }
    else
    {
      v22 = GetLastError();
      v6 = v22;
      if ( v22 > 0 )
        v6 = (unsigned __int16)v22 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_180047000 <= 2 || (qword_180047010 & 8) == 0 || (qword_180047018 & 8) != qword_180047018 )
        goto LABEL_140;
      v23 = (__int16 *)&dword_18003F8DC;
    }
LABEL_72:
    v46 = &v33;
    v47 = 4;
    LODWORD(v33) = v6;
    tlgWriteTransfer_EventWriteTransfer(&dword_180047000, v23, 0, 0, 3, v45);
    goto LABEL_140;
  }
  if ( (unsigned int)dword_180047000 > 2 )
  {
    a2 = (const struct std::nothrow_t *)qword_180047018;
    v10 = qword_180047010;
    if ( (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      LODWORD(v33) = v6;
      v11 = word_18003FA42;
      goto LABEL_139;
    }
  }
LABEL_140:
  if ( (unsigned __int64)(FileW + 1) > 1 )
    CloseHandle(FileW);
  if ( v4 )
    operator delete(v4);
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  if ( hMem )
    LocalFree(hMem);
  if ( v3 )
    operator delete(v3, a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b3f8  push    rbp
0x18001b3fa  push    rbx
0x18001b3fb  push    rsi
0x18001b3fc  push    rdi
0x18001b3fd  push    r12
0x18001b3ff  push    r13
0x18001b401  push    r14
0x18001b403  push    r15
0x18001b405  lea     rbp, [rsp-28h]
0x18001b40a  sub     rsp, 128h
0x18001b411  mov     rax, cs:__security_cookie
0x18001b418  xor     rax, rsp
0x18001b41b  mov     [rbp+60h+var_50], rax
0x18001b41f  mov     rsi, rcx
0x18001b422  mov     [rsp+160h+nLengthNeeded], 0
0x18001b42a  xor     r13d, r13d
0x18001b42d  mov     [rsp+160h+var_110], r13
0x18001b432  xorps   xmm0, xmm0
0x18001b435  xor     eax, eax
0x18001b437  movups  [rbp+60h+pSecurityDescriptor], xmm0
0x18001b43b  movups  [rbp+60h+var_A0], xmm0
0x18001b43f  mov     [rbp+60h+var_90], rax
0x18001b443  mov     [rsp+160h+pDacl], rax
0x18001b448  mov     [rsp+160h+hMem], rax
0x18001b44d  mov     [rsp+160h+TokenHandle], rax
0x18001b452  xor     r12d, r12d
0x18001b455  mov     [rsp+160h+var_120], r12
0x18001b45a  mov     [rsp+160h+bDaclPresent], r12d
0x18001b45f  mov     [rsp+160h+bDaclDefaulted], r12d
0x18001b464  xor     r15d, r15d
0x18001b467  test    rcx, rcx
0x18001b46a  jnz     short loc_18001B476
0x18001b46c  mov     ebx, 80070057h
0x18001b471  jmp     loc_18001BC4E
0x18001b476  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x18001b47f  mov     [rsp+160h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001b487  mov     eax, 3
0x18001b48c  mov     [rsp+160h+dwCreationDisposition], eax; dwCreationDisposition
0x18001b490  xor     r9d, r9d; lpSecurityAttributes
0x18001b493  mov     r8d, eax; dwShareMode
0x18001b496  mov     edx, 60000h; dwDesiredAccess
0x18001b49b  call    cs:__imp_CreateFileW
0x18001b4a1  mov     r15, rax
0x18001b4a4  mov     [rbp+60h+var_88], rax
0x18001b4a8  inc     rax
0x18001b4ab  cmp     rax, 1
0x18001b4af  ja      short loc_18001B516
0x18001b4b1  call    cs:__imp_GetLastError
0x18001b4b7  mov     ebx, eax
0x18001b4b9  test    eax, eax
0x18001b4bb  jle     short loc_18001B4C6
0x18001b4bd  movzx   ebx, ax
0x18001b4c0  or      ebx, 80070000h
0x18001b4c6  mov     r14d, 80004005h
0x18001b4cc  test    ebx, ebx
0x18001b4ce  cmovns  ebx, r14d
0x18001b4d2  mov     eax, cs:dword_180047000
0x18001b4d8  cmp     eax, 2
0x18001b4db  jbe     loc_18001BC4E
0x18001b4e1  mov     rcx, cs:qword_180047018
0x18001b4e8  mov     rax, cs:qword_180047010
0x18001b4ef  test    al, 8
0x18001b4f1  jz      loc_18001BC4E
0x18001b4f7  mov     rax, rcx
0x18001b4fa  and     eax, 8
0x18001b4fd  cmp     rax, rcx
0x18001b500  jnz     loc_18001BC4E
0x18001b506  mov     dword ptr [rsp+160h+var_120], ebx
0x18001b50a  lea     rdx, byte_18003FA7B
0x18001b511  jmp     loc_18001BC2F
0x18001b516  mov     rdx, r15; void *
0x18001b519  mov     rcx, rsi; wchar_t *
0x18001b51c  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18001b521  mov     ebx, eax
0x18001b523  test    eax, eax
0x18001b525  jns     short loc_18001B56C
0x18001b527  mov     ecx, cs:dword_180047000
0x18001b52d  cmp     ecx, 2
0x18001b530  jbe     loc_18001BC4E
0x18001b536  mov     rdx, cs:qword_180047018
0x18001b53d  mov     rcx, cs:qword_180047010
0x18001b544  test    cl, 8
0x18001b547  jz      loc_18001BC4E
0x18001b54d  mov     rax, rdx
0x18001b550  and     eax, 8
0x18001b553  cmp     rax, rdx
0x18001b556  jnz     loc_18001BC4E
0x18001b55c  mov     dword ptr [rsp+160h+var_120], ebx
0x18001b560  lea     rdx, word_18003FA42
0x18001b567  jmp     loc_18001BC2F
0x18001b56c  lea     rax, [rsp+160h+nLengthNeeded]
0x18001b571  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; lpnLengthNeeded
0x18001b576  xor     r9d, r9d; nLength
0x18001b579  xor     r8d, r8d; pSecurityDescriptor
0x18001b57c  lea     edx, [r9+4]; RequestedInformation
0x18001b580  mov     rcx, r15; Handle
0x18001b583  call    cs:__imp_GetKernelObjectSecurity
0x18001b589  mov     edi, 80070000h
0x18001b58e  mov     r14d, 80004005h
0x18001b594  test    eax, eax
0x18001b596  jnz     short loc_18001B603
0x18001b598  call    cs:__imp_GetLastError
0x18001b59e  mov     ebx, eax
0x18001b5a0  test    eax, eax
0x18001b5a2  jle     short loc_18001B5A9
0x18001b5a4  movzx   ebx, ax
0x18001b5a7  or      ebx, edi
0x18001b5a9  test    ebx, ebx
0x18001b5ab  cmovns  ebx, r14d
0x18001b5af  mov     eax, [rsp+160h+nLengthNeeded]
0x18001b5b3  test    eax, eax
0x18001b5b5  jz      short loc_18001B5BF
0x18001b5b7  cmp     ebx, 8007007Ah
0x18001b5bd  jz      short loc_18001B607
0x18001b5bf  mov     eax, cs:dword_180047000
0x18001b5c5  cmp     eax, 2
0x18001b5c8  jbe     loc_18001BC4E
0x18001b5ce  mov     rcx, cs:qword_180047018
0x18001b5d5  mov     rax, cs:qword_180047010
0x18001b5dc  test    al, 8
0x18001b5de  jz      loc_18001BC4E
0x18001b5e4  mov     rax, rcx
0x18001b5e7  and     eax, 8
0x18001b5ea  cmp     rax, rcx
0x18001b5ed  jnz     loc_18001BC4E
0x18001b5f3  mov     dword ptr [rsp+160h+var_120], ebx
0x18001b5f7  lea     rdx, byte_18003FA03
0x18001b5fe  jmp     loc_18001BC2F
0x18001b603  mov     eax, [rsp+160h+nLengthNeeded]
0x18001b607  mov     ecx, eax; unsigned __int64
0x18001b609  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b610  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b615  mov     r13, rax
0x18001b618  test    rax, rax
0x18001b61b  jnz     short loc_18001B662
0x18001b61d  mov     ebx, 8007000Eh
0x18001b622  mov     eax, cs:dword_180047000
0x18001b628  cmp     eax, 2
0x18001b62b  jbe     loc_18001BC4E
0x18001b631  mov     rcx, cs:qword_180047018
0x18001b638  mov     rax, cs:qword_180047010
0x18001b63f  test    al, 8
0x18001b641  jz      loc_18001BC4E
0x18001b647  mov     rax, rcx
0x18001b64a  and     eax, 8
0x18001b64d  cmp     rax, rcx
0x18001b650  jnz     loc_18001BC4E
0x18001b656  lea     rdx, word_18003F9C6
0x18001b65d  jmp     loc_18001BC27
0x18001b662  lea     rax, [rsp+160h+nLengthNeeded]
0x18001b667  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; lpnLengthNeeded
0x18001b66c  mov     r9d, [rsp+160h+nLengthNeeded]; nLength
0x18001b671  mov     r8, r13; pSecurityDescriptor
0x18001b674  mov     edx, 4; RequestedInformation
0x18001b679  mov     rcx, r15; Handle
0x18001b67c  call    cs:__imp_GetKernelObjectSecurity
0x18001b682  test    eax, eax
0x18001b684  jnz     short loc_18001B6E1
0x18001b686  call    cs:__imp_GetLastError
0x18001b68c  mov     ebx, eax
0x18001b68e  test    eax, eax
0x18001b690  jle     short loc_18001B697
0x18001b692  movzx   ebx, ax
0x18001b695  or      ebx, edi
0x18001b697  test    ebx, ebx
0x18001b699  cmovns  ebx, r14d
0x18001b69d  mov     eax, cs:dword_180047000
0x18001b6a3  cmp     eax, 2
0x18001b6a6  jbe     loc_18001BC4E
0x18001b6ac  mov     rcx, cs:qword_180047018
0x18001b6b3  mov     rax, cs:qword_180047010
0x18001b6ba  test    al, 8
0x18001b6bc  jz      loc_18001BC4E
0x18001b6c2  mov     rax, rcx
0x18001b6c5  and     eax, 8
0x18001b6c8  cmp     rax, rcx
0x18001b6cb  jnz     loc_18001BC4E
0x18001b6d1  mov     dword ptr [rsp+160h+var_120], ebx
0x18001b6d5  lea     rdx, byte_18003F987
0x18001b6dc  jmp     loc_18001BC2F
0x18001b6e1  lea     r9, [rsp+160h+bDaclDefaulted]; lpbDaclDefaulted
0x18001b6e6  lea     r8, [rsp+160h+pDacl]; pDacl
0x18001b6eb  lea     rdx, [rsp+160h+bDaclPresent]; lpbDaclPresent
0x18001b6f0  mov     rcx, r13; pSecurityDescriptor
0x18001b6f3  call    cs:__imp_GetSecurityDescriptorDacl
0x18001b6f9  test    eax, eax
0x18001b6fb  jnz     short loc_18001B758
0x18001b6fd  call    cs:__imp_GetLastError
0x18001b703  mov     ebx, eax
0x18001b705  test    eax, eax
0x18001b707  jle     short loc_18001B70E
0x18001b709  movzx   ebx, ax
0x18001b70c  or      ebx, edi
0x18001b70e  test    ebx, ebx
0x18001b710  cmovns  ebx, r14d
0x18001b714  mov     eax, cs:dword_180047000
0x18001b71a  cmp     eax, 2
0x18001b71d  jbe     loc_18001BC4E
0x18001b723  mov     rcx, cs:qword_180047018
0x18001b72a  mov     rax, cs:qword_180047010
0x18001b731  test    al, 8
0x18001b733  jz      loc_18001BC4E
0x18001b739  mov     rax, rcx
0x18001b73c  and     eax, 8
0x18001b73f  cmp     rax, rcx
0x18001b742  jnz     loc_18001BC4E
0x18001b748  mov     dword ptr [rsp+160h+var_120], ebx
0x18001b74c  lea     rdx, byte_18003F94D
0x18001b753  jmp     loc_18001BC2F
0x18001b758  cmp     [rsp+160h+bDaclPresent], 0
0x18001b75d  jnz     short loc_18001B768
0x18001b75f  mov     [rsp+160h+pDacl], 0
0x18001b768  lea     rcx, [rsp+160h+TokenHandle]
0x18001b76d  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001b772  mov     rbx, rax
0x18001b775  call    cs:__imp_GetCurrentThread
0x18001b77b  mov     r9, rbx; TokenHandle
0x18001b77e  xor     r8d, r8d; OpenAsSelf
0x18001b781  lea     edx, [r8+8]; DesiredAccess
0x18001b785  mov     rcx, rax; ThreadHandle
0x18001b788  call    cs:__imp_OpenThreadToken
0x18001b78e  test    eax, eax
0x18001b790  jnz     loc_18001B8CF
0x18001b796  call    cs:__imp_GetLastError
0x18001b79c  mov     ecx, eax
0x18001b79e  test    eax, eax
0x18001b7a0  jle     short loc_18001B7A7
0x18001b7a2  movzx   ecx, ax
0x18001b7a5  or      ecx, edi
0x18001b7a7  test    ecx, ecx
0x18001b7a9  cmovns  ecx, r14d
0x18001b7ad  mov     eax, cs:dword_180047000
0x18001b7b3  cmp     eax, 3
0x18001b7b6  jbe     short loc_18001B814
0x18001b7b8  mov     rdx, cs:qword_180047018
0x18001b7bf  mov     rax, cs:qword_180047010
0x18001b7c6  test    al, 8
0x18001b7c8  jz      short loc_18001B814
0x18001b7ca  mov     rax, rdx
0x18001b7cd  and     eax, 8
0x18001b7d0  cmp     rax, rdx
0x18001b7d3  jnz     short loc_18001B814
0x18001b7d5  mov     dword ptr [rsp+160h+var_120], ecx
0x18001b7d9  lea     rax, [rsp+160h+var_120]
0x18001b7de  mov     [rbp+60h+var_60], rax
0x18001b7e2  mov     [rbp+60h+var_58], 4
0x18001b7ea  lea     rax, [rbp+60h+var_80]
0x18001b7ee  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rax
0x18001b7f3  mov     [rsp+160h+dwCreationDisposition], 3
0x18001b7fb  xor     r9d, r9d
0x18001b7fe  xor     r8d, r8d
0x18001b801  lea     rdx, byte_18003F915
0x18001b808  lea     rcx, dword_180047000
0x18001b80f  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b814  lea     rcx, [rsp+160h+TokenHandle]
0x18001b819  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001b81e  mov     rbx, rax
0x18001b821  call    cs:__imp_GetCurrentProcess
0x18001b827  mov     r8, rbx; TokenHandle
0x18001b82a  mov     edx, 8; DesiredAccess
0x18001b82f  mov     rcx, rax; ProcessHandle
0x18001b832  call    cs:__imp_OpenProcessToken
0x18001b838  test    eax, eax
0x18001b83a  jnz     loc_18001B8CF
0x18001b840  call    cs:__imp_GetLastError
0x18001b846  mov     ebx, eax
0x18001b848  test    eax, eax
0x18001b84a  jle     short loc_18001B851
0x18001b84c  movzx   ebx, ax
0x18001b84f  or      ebx, edi
0x18001b851  test    ebx, ebx
0x18001b853  cmovns  ebx, r14d
0x18001b857  mov     eax, cs:dword_180047000
0x18001b85d  cmp     eax, 2
0x18001b860  jbe     loc_18001BC4E
0x18001b866  mov     rcx, cs:qword_180047018
0x18001b86d  mov     rax, cs:qword_180047010
0x18001b874  test    al, 8
0x18001b876  jz      loc_18001BC4E
0x18001b87c  mov     rax, rcx
0x18001b87f  and     eax, 8
0x18001b882  cmp     rax, rcx
0x18001b885  jnz     loc_18001BC4E
0x18001b88b  lea     rdx, dword_18003F8DC
0x18001b892  lea     rax, [rsp+160h+var_120]
0x18001b897  mov     [rbp+60h+var_60], rax
0x18001b89b  lea     rax, [rbp+60h+var_80]
0x18001b89f  xor     r9d, r9d
0x18001b8a2  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rax
0x18001b8a7  xor     r8d, r8d
0x18001b8aa  mov     [rsp+160h+dwCreationDisposition], 3
0x18001b8b2  mov     [rbp+60h+var_58], 4
0x18001b8ba  mov     dword ptr [rsp+160h+var_120], ebx
0x18001b8be  lea     rcx, dword_180047000
0x18001b8c5  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b8ca  jmp     loc_18001BC4E
0x18001b8cf  lea     rax, [rsp+160h+nLengthNeeded]
0x18001b8d4  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; ReturnLength
0x18001b8d9  xor     r9d, r9d; TokenInformationLength
0x18001b8dc  xor     r8d, r8d; TokenInformation
  ... truncated ...
```
