# UtilAddAccessToPath(wchar_t const *,ulong)

- ea: `0x14000a804`
- end: `0x14000b0d2`
- name: `?UtilAddAccessToPath@@YAJPEB_WK@Z`
- size: `2254`
- prototype: `__int64 __fastcall(WCHAR *, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140008ce4`

## callees

- `0x140001270`
- `0x14000162c`
- `0x140003200`
- `0x140003224`
- `0x140003230`
- `0x140003254`
- `0x1400033bc`
- `0x14000473c`
- `0x14000a804`
- `0x14000c798`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ac2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000ac2d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000ab94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000ab94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000ab81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000ab81`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000ac3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000ac3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aa92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000acfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000adab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aa92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ac4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000acfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000adab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b08b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b067`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b08b`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x14000af9e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x14000af9e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14000af2d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14000af2d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14000aeb8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14000aeb8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000aaff`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14000aaff`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000a98f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000aa88`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000a98f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14000aa88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000acf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000ad9f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000acf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000ad9f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a8a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000a8a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ae3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b09c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ae3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b09c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14000ae56`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x14000ae56`

## pseudocode

```c
__int64 __fastcall UtilAddAccessToPath(WCHAR *a1, const struct std::nothrow_t *a2)
{
  void *v3; // r13
  LPWCH *v4; // r12
  char *FileW; // r15
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  char *v13; // rdx
  signed int v14; // eax
  DWORD v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  void **v18; // rbx
  HANDLE CurrentThread; // rax
  signed int v20; // eax
  signed int v21; // ecx
  void **v22; // rbx
  HANDLE CurrentProcess; // rax
  signed int v24; // eax
  char *v25; // rdx
  signed int v26; // eax
  DWORD v27; // eax
  signed int v28; // eax
  HLOCAL v29; // rcx
  signed int v30; // eax
  signed int v31; // eax
  signed int v32; // eax
  signed int v33; // eax
  __int64 v35; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nLengthNeeded; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v37; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+70h] [rbp-90h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h]
  char *v46; // [rsp+D8h] [rbp-28h]
  _BYTE v47[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]

  nLengthNeeded = 0;
  v3 = 0;
  v37 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v45 = 0;
  pDacl = 0;
  hMem = 0;
  TokenHandle = 0;
  v4 = 0;
  v35 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  FileW = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_140;
  }
  FileW = (char *)CreateFileW(a1, 0x60000u, 3u, 0, 3u, 0x2200000u, 0);
  v46 = FileW;
  if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    if ( (unsigned int)dword_14002C000 > 2 )
    {
      v12 = qword_14002C018;
      if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        LODWORD(v35) = v6;
        v13 = (char *)word_1400265EA;
LABEL_139:
        v37 = a1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v12,
          (_DWORD)v13,
          v10,
          v11,
          (__int64)&v37,
          (__int64)&v35);
        goto LABEL_140;
      }
    }
    goto LABEL_140;
  }
  v6 = UtilVerifyFilePath(a1, FileW, v7, v8);
  if ( v6 >= 0 )
  {
    if ( GetKernelObjectSecurity(FileW, 4u, 0, 0, &nLengthNeeded) )
    {
      v15 = nLengthNeeded;
    }
    else
    {
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      v15 = nLengthNeeded;
      if ( !nLengthNeeded || v6 != -2147024774 )
      {
        if ( (unsigned int)dword_14002C000 > 2 )
        {
          v12 = qword_14002C018;
          if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
          {
            LODWORD(v35) = v6;
            v13 = (char *)word_140026572;
            goto LABEL_139;
          }
        }
        goto LABEL_140;
      }
    }
    v3 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v3 )
    {
      v6 = -2147024882;
      if ( (unsigned int)dword_14002C000 <= 2 )
        goto LABEL_140;
      v12 = qword_14002C018;
      if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
        goto LABEL_140;
      v13 = byte_140026535;
      goto LABEL_138;
    }
    if ( !GetKernelObjectSecurity(FileW, 4u, v3, nLengthNeeded, &nLengthNeeded) )
    {
      v16 = GetLastError();
      v6 = v16;
      if ( v16 > 0 )
        v6 = (unsigned __int16)v16 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14002C000 > 2 )
      {
        v12 = qword_14002C018;
        if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
        {
          LODWORD(v35) = v6;
          v13 = (char *)&word_1400264F6;
          goto LABEL_139;
        }
      }
      goto LABEL_140;
    }
    if ( !GetSecurityDescriptorDacl(v3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v17 = GetLastError();
      v6 = v17;
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14002C000 > 2 )
      {
        v12 = qword_14002C018;
        if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
        {
          LODWORD(v35) = v6;
          v13 = (char *)&dword_1400264BC;
          goto LABEL_139;
        }
      }
      goto LABEL_140;
    }
    if ( !bDaclPresent )
      pDacl = 0;
    v18 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, v18) )
      goto LABEL_153;
    v20 = GetLastError();
    v21 = v20;
    if ( v20 > 0 )
      v21 = (unsigned __int16)v20 | 0x80070000;
    if ( v21 >= 0 )
      v21 = -2147467259;
    if ( (unsigned int)dword_14002C000 > 3 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      LODWORD(v35) = v21;
      v48 = &v35;
      v49 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, &dword_140026484, 0, 0, 3, v47);
    }
    v22 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, v22) )
    {
LABEL_153:
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &nLengthNeeded) )
      {
        v27 = nLengthNeeded;
      }
      else
      {
        v26 = GetLastError();
        v6 = v26;
        if ( v26 > 0 )
          v6 = (unsigned __int16)v26 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        v27 = nLengthNeeded;
        if ( !nLengthNeeded || v6 != -2147024774 )
        {
          if ( (unsigned int)dword_14002C000 <= 2
            || (qword_14002C010 & 8) == 0
            || (qword_14002C018 & 8) != qword_14002C018 )
          {
            goto LABEL_140;
          }
          v25 = byte_140026415;
          goto LABEL_72;
        }
      }
      v4 = (LPWCH *)operator new(v27, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v4 )
      {
        v4 = 0;
        v6 = -2147024882;
        if ( (unsigned int)dword_14002C000 <= 2 )
          goto LABEL_140;
        v12 = qword_14002C018;
        if ( (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
          goto LABEL_140;
        v13 = byte_1400263D5;
LABEL_138:
        LODWORD(v35) = -2147024882;
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
        v29 = hMem;
        hMem = 0;
        if ( v29 )
          LocalFree(v29);
        v30 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, (PACL *)&hMem);
        v6 = v30;
        if ( !v30 )
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
              v33 = GetLastError();
              v6 = v33;
              if ( v33 > 0 )
                v6 = (unsigned __int16)v33 | 0x80070000;
              if ( v6 >= 0 )
                v6 = -2147467259;
              if ( (unsigned int)dword_14002C000 > 2 )
              {
                v12 = qword_14002C018;
                if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
                {
                  LODWORD(v35) = v6;
                  v13 = byte_1400262AD;
                  goto LABEL_139;
                }
              }
            }
            else
            {
              v32 = GetLastError();
              v6 = v32;
              if ( v32 > 0 )
                v6 = (unsigned __int16)v32 | 0x80070000;
              if ( v6 >= 0 )
                v6 = -2147467259;
              if ( (unsigned int)dword_14002C000 > 2 )
              {
                v12 = qword_14002C018;
                if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
                {
                  LODWORD(v35) = v6;
                  v13 = byte_1400262F1;
                  goto LABEL_139;
                }
              }
            }
          }
          else
          {
            v31 = GetLastError();
            v6 = v31;
            if ( v31 > 0 )
              v6 = (unsigned __int16)v31 | 0x80070000;
            if ( v6 >= 0 )
              v6 = -2147467259;
            if ( (unsigned int)dword_14002C000 > 2 )
            {
              v12 = qword_14002C018;
              if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
              {
                LODWORD(v35) = v6;
                v13 = byte_14002632B;
                goto LABEL_139;
              }
            }
          }
          goto LABEL_140;
        }
        if ( v30 > 0 )
          v6 = (unsigned __int16)v30 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        if ( (unsigned int)dword_14002C000 <= 2
          || (qword_14002C010 & 8) == 0
          || (qword_14002C018 & 8) != qword_14002C018 )
        {
          goto LABEL_140;
        }
        v25 = (char *)&dword_14002636C;
      }
      else
      {
        v28 = GetLastError();
        v6 = v28;
        if ( v28 > 0 )
          v6 = (unsigned __int16)v28 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        if ( (unsigned int)dword_14002C000 <= 2
          || (qword_14002C010 & 8) == 0
          || (qword_14002C018 & 8) != qword_14002C018 )
        {
          goto LABEL_140;
        }
        v25 = &byte_14002639F;
      }
    }
    else
    {
      v24 = GetLastError();
      v6 = v24;
      if ( v24 > 0 )
        v6 = (unsigned __int16)v24 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14002C000 <= 2 || (qword_14002C010 & 8) == 0 || (qword_14002C018 & 8) != qword_14002C018 )
        goto LABEL_140;
      v25 = byte_14002644B;
    }
LABEL_72:
    v48 = &v35;
    v49 = 4;
    LODWORD(v35) = v6;
    tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, v25, 0, 0, 3, v47);
    goto LABEL_140;
  }
  if ( (unsigned int)dword_14002C000 > 2 )
  {
    a2 = (const struct std::nothrow_t *)qword_14002C018;
    v12 = qword_14002C010;
    if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      LODWORD(v35) = v6;
      v13 = byte_1400265B1;
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
0x14000a804  push    rbp
0x14000a806  push    rbx
0x14000a807  push    rsi
0x14000a808  push    rdi
0x14000a809  push    r12
0x14000a80b  push    r13
0x14000a80d  push    r14
0x14000a80f  push    r15
0x14000a811  lea     rbp, [rsp-28h]
0x14000a816  sub     rsp, 128h
0x14000a81d  mov     rax, cs:__security_cookie
0x14000a824  xor     rax, rsp
0x14000a827  mov     [rbp+60h+var_50], rax
0x14000a82b  mov     rsi, rcx
0x14000a82e  mov     [rsp+160h+nLengthNeeded], 0
0x14000a836  xor     r13d, r13d
0x14000a839  mov     [rsp+160h+var_110], r13
0x14000a83e  xorps   xmm0, xmm0
0x14000a841  xor     eax, eax
0x14000a843  movups  [rbp+60h+pSecurityDescriptor], xmm0
0x14000a847  movups  [rbp+60h+var_A0], xmm0
0x14000a84b  mov     [rbp+60h+var_90], rax
0x14000a84f  mov     [rsp+160h+pDacl], rax
0x14000a854  mov     [rsp+160h+hMem], rax
0x14000a859  mov     [rsp+160h+TokenHandle], rax
0x14000a85e  xor     r12d, r12d
0x14000a861  mov     [rsp+160h+var_120], r12
0x14000a866  mov     [rsp+160h+bDaclPresent], r12d
0x14000a86b  mov     [rsp+160h+bDaclDefaulted], r12d
0x14000a870  xor     r15d, r15d
0x14000a873  test    rcx, rcx
0x14000a876  jnz     short loc_14000A882
0x14000a878  mov     ebx, 80070057h
0x14000a87d  jmp     loc_14000B05A
0x14000a882  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x14000a88b  mov     [rsp+160h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x14000a893  mov     eax, 3
0x14000a898  mov     [rsp+160h+dwCreationDisposition], eax; dwCreationDisposition
0x14000a89c  xor     r9d, r9d; lpSecurityAttributes
0x14000a89f  mov     r8d, eax; dwShareMode
0x14000a8a2  mov     edx, 60000h; dwDesiredAccess
0x14000a8a7  call    cs:__imp_CreateFileW
0x14000a8ad  mov     r15, rax
0x14000a8b0  mov     [rbp+60h+var_88], rax
0x14000a8b4  inc     rax
0x14000a8b7  cmp     rax, 1
0x14000a8bb  ja      short loc_14000A922
0x14000a8bd  call    cs:__imp_GetLastError
0x14000a8c3  mov     ebx, eax
0x14000a8c5  test    eax, eax
0x14000a8c7  jle     short loc_14000A8D2
0x14000a8c9  movzx   ebx, ax
0x14000a8cc  or      ebx, 80070000h
0x14000a8d2  mov     r14d, 80004005h
0x14000a8d8  test    ebx, ebx
0x14000a8da  cmovns  ebx, r14d
0x14000a8de  mov     eax, cs:dword_14002C000
0x14000a8e4  cmp     eax, 2
0x14000a8e7  jbe     loc_14000B05A
0x14000a8ed  mov     rcx, cs:qword_14002C018
0x14000a8f4  mov     rax, cs:qword_14002C010
0x14000a8fb  test    al, 8
0x14000a8fd  jz      loc_14000B05A
0x14000a903  mov     rax, rcx
0x14000a906  and     eax, 8
0x14000a909  cmp     rax, rcx
0x14000a90c  jnz     loc_14000B05A
0x14000a912  mov     dword ptr [rsp+160h+var_120], ebx
0x14000a916  lea     rdx, word_1400265EA
0x14000a91d  jmp     loc_14000B03B
0x14000a922  mov     rdx, r15; void *
0x14000a925  mov     rcx, rsi; wchar_t *
0x14000a928  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x14000a92d  mov     ebx, eax
0x14000a92f  test    eax, eax
0x14000a931  jns     short loc_14000A978
0x14000a933  mov     ecx, cs:dword_14002C000
0x14000a939  cmp     ecx, 2
0x14000a93c  jbe     loc_14000B05A
0x14000a942  mov     rdx, cs:qword_14002C018
0x14000a949  mov     rcx, cs:qword_14002C010
0x14000a950  test    cl, 8
0x14000a953  jz      loc_14000B05A
0x14000a959  mov     rax, rdx
0x14000a95c  and     eax, 8
0x14000a95f  cmp     rax, rdx
0x14000a962  jnz     loc_14000B05A
0x14000a968  mov     dword ptr [rsp+160h+var_120], ebx
0x14000a96c  lea     rdx, byte_1400265B1
0x14000a973  jmp     loc_14000B03B
0x14000a978  lea     rax, [rsp+160h+nLengthNeeded]
0x14000a97d  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; lpnLengthNeeded
0x14000a982  xor     r9d, r9d; nLength
0x14000a985  xor     r8d, r8d; pSecurityDescriptor
0x14000a988  lea     edx, [r9+4]; RequestedInformation
0x14000a98c  mov     rcx, r15; Handle
0x14000a98f  call    cs:__imp_GetKernelObjectSecurity
0x14000a995  mov     edi, 80070000h
0x14000a99a  mov     r14d, 80004005h
0x14000a9a0  test    eax, eax
0x14000a9a2  jnz     short loc_14000AA0F
0x14000a9a4  call    cs:__imp_GetLastError
0x14000a9aa  mov     ebx, eax
0x14000a9ac  test    eax, eax
0x14000a9ae  jle     short loc_14000A9B5
0x14000a9b0  movzx   ebx, ax
0x14000a9b3  or      ebx, edi
0x14000a9b5  test    ebx, ebx
0x14000a9b7  cmovns  ebx, r14d
0x14000a9bb  mov     eax, [rsp+160h+nLengthNeeded]
0x14000a9bf  test    eax, eax
0x14000a9c1  jz      short loc_14000A9CB
0x14000a9c3  cmp     ebx, 8007007Ah
0x14000a9c9  jz      short loc_14000AA13
0x14000a9cb  mov     eax, cs:dword_14002C000
0x14000a9d1  cmp     eax, 2
0x14000a9d4  jbe     loc_14000B05A
0x14000a9da  mov     rcx, cs:qword_14002C018
0x14000a9e1  mov     rax, cs:qword_14002C010
0x14000a9e8  test    al, 8
0x14000a9ea  jz      loc_14000B05A
0x14000a9f0  mov     rax, rcx
0x14000a9f3  and     eax, 8
0x14000a9f6  cmp     rax, rcx
0x14000a9f9  jnz     loc_14000B05A
0x14000a9ff  mov     dword ptr [rsp+160h+var_120], ebx
0x14000aa03  lea     rdx, word_140026572
0x14000aa0a  jmp     loc_14000B03B
0x14000aa0f  mov     eax, [rsp+160h+nLengthNeeded]
0x14000aa13  mov     ecx, eax; unsigned __int64
0x14000aa15  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000aa1c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000aa21  mov     r13, rax
0x14000aa24  test    rax, rax
0x14000aa27  jnz     short loc_14000AA6E
0x14000aa29  mov     ebx, 8007000Eh
0x14000aa2e  mov     eax, cs:dword_14002C000
0x14000aa34  cmp     eax, 2
0x14000aa37  jbe     loc_14000B05A
0x14000aa3d  mov     rcx, cs:qword_14002C018
0x14000aa44  mov     rax, cs:qword_14002C010
0x14000aa4b  test    al, 8
0x14000aa4d  jz      loc_14000B05A
0x14000aa53  mov     rax, rcx
0x14000aa56  and     eax, 8
0x14000aa59  cmp     rax, rcx
0x14000aa5c  jnz     loc_14000B05A
0x14000aa62  lea     rdx, byte_140026535
0x14000aa69  jmp     loc_14000B033
0x14000aa6e  lea     rax, [rsp+160h+nLengthNeeded]
0x14000aa73  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; lpnLengthNeeded
0x14000aa78  mov     r9d, [rsp+160h+nLengthNeeded]; nLength
0x14000aa7d  mov     r8, r13; pSecurityDescriptor
0x14000aa80  mov     edx, 4; RequestedInformation
0x14000aa85  mov     rcx, r15; Handle
0x14000aa88  call    cs:__imp_GetKernelObjectSecurity
0x14000aa8e  test    eax, eax
0x14000aa90  jnz     short loc_14000AAED
0x14000aa92  call    cs:__imp_GetLastError
0x14000aa98  mov     ebx, eax
0x14000aa9a  test    eax, eax
0x14000aa9c  jle     short loc_14000AAA3
0x14000aa9e  movzx   ebx, ax
0x14000aaa1  or      ebx, edi
0x14000aaa3  test    ebx, ebx
0x14000aaa5  cmovns  ebx, r14d
0x14000aaa9  mov     eax, cs:dword_14002C000
0x14000aaaf  cmp     eax, 2
0x14000aab2  jbe     loc_14000B05A
0x14000aab8  mov     rcx, cs:qword_14002C018
0x14000aabf  mov     rax, cs:qword_14002C010
0x14000aac6  test    al, 8
0x14000aac8  jz      loc_14000B05A
0x14000aace  mov     rax, rcx
0x14000aad1  and     eax, 8
0x14000aad4  cmp     rax, rcx
0x14000aad7  jnz     loc_14000B05A
0x14000aadd  mov     dword ptr [rsp+160h+var_120], ebx
0x14000aae1  lea     rdx, word_1400264F6
0x14000aae8  jmp     loc_14000B03B
0x14000aaed  lea     r9, [rsp+160h+bDaclDefaulted]; lpbDaclDefaulted
0x14000aaf2  lea     r8, [rsp+160h+pDacl]; pDacl
0x14000aaf7  lea     rdx, [rsp+160h+bDaclPresent]; lpbDaclPresent
0x14000aafc  mov     rcx, r13; pSecurityDescriptor
0x14000aaff  call    cs:__imp_GetSecurityDescriptorDacl
0x14000ab05  test    eax, eax
0x14000ab07  jnz     short loc_14000AB64
0x14000ab09  call    cs:__imp_GetLastError
0x14000ab0f  mov     ebx, eax
0x14000ab11  test    eax, eax
0x14000ab13  jle     short loc_14000AB1A
0x14000ab15  movzx   ebx, ax
0x14000ab18  or      ebx, edi
0x14000ab1a  test    ebx, ebx
0x14000ab1c  cmovns  ebx, r14d
0x14000ab20  mov     eax, cs:dword_14002C000
0x14000ab26  cmp     eax, 2
0x14000ab29  jbe     loc_14000B05A
0x14000ab2f  mov     rcx, cs:qword_14002C018
0x14000ab36  mov     rax, cs:qword_14002C010
0x14000ab3d  test    al, 8
0x14000ab3f  jz      loc_14000B05A
0x14000ab45  mov     rax, rcx
0x14000ab48  and     eax, 8
0x14000ab4b  cmp     rax, rcx
0x14000ab4e  jnz     loc_14000B05A
0x14000ab54  mov     dword ptr [rsp+160h+var_120], ebx
0x14000ab58  lea     rdx, dword_1400264BC
0x14000ab5f  jmp     loc_14000B03B
0x14000ab64  cmp     [rsp+160h+bDaclPresent], 0
0x14000ab69  jnz     short loc_14000AB74
0x14000ab6b  mov     [rsp+160h+pDacl], 0
0x14000ab74  lea     rcx, [rsp+160h+TokenHandle]
0x14000ab79  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14000ab7e  mov     rbx, rax
0x14000ab81  call    cs:__imp_GetCurrentThread
0x14000ab87  mov     r9, rbx; TokenHandle
0x14000ab8a  xor     r8d, r8d; OpenAsSelf
0x14000ab8d  lea     edx, [r8+8]; DesiredAccess
0x14000ab91  mov     rcx, rax; ThreadHandle
0x14000ab94  call    cs:__imp_OpenThreadToken
0x14000ab9a  test    eax, eax
0x14000ab9c  jnz     loc_14000ACDB
0x14000aba2  call    cs:__imp_GetLastError
0x14000aba8  mov     ecx, eax
0x14000abaa  test    eax, eax
0x14000abac  jle     short loc_14000ABB3
0x14000abae  movzx   ecx, ax
0x14000abb1  or      ecx, edi
0x14000abb3  test    ecx, ecx
0x14000abb5  cmovns  ecx, r14d
0x14000abb9  mov     eax, cs:dword_14002C000
0x14000abbf  cmp     eax, 3
0x14000abc2  jbe     short loc_14000AC20
0x14000abc4  mov     rdx, cs:qword_14002C018
0x14000abcb  mov     rax, cs:qword_14002C010
0x14000abd2  test    al, 8
0x14000abd4  jz      short loc_14000AC20
0x14000abd6  mov     rax, rdx
0x14000abd9  and     eax, 8
0x14000abdc  cmp     rax, rdx
0x14000abdf  jnz     short loc_14000AC20
0x14000abe1  mov     dword ptr [rsp+160h+var_120], ecx
0x14000abe5  lea     rax, [rsp+160h+var_120]
0x14000abea  mov     [rbp+60h+var_60], rax
0x14000abee  mov     [rbp+60h+var_58], 4
0x14000abf6  lea     rax, [rbp+60h+var_80]
0x14000abfa  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rax
0x14000abff  mov     [rsp+160h+dwCreationDisposition], 3
0x14000ac07  xor     r9d, r9d
0x14000ac0a  xor     r8d, r8d
0x14000ac0d  lea     rdx, dword_140026484
0x14000ac14  lea     rcx, dword_14002C000
0x14000ac1b  call    _tlgWriteTransfer_EventWriteTransfer
0x14000ac20  lea     rcx, [rsp+160h+TokenHandle]
0x14000ac25  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14000ac2a  mov     rbx, rax
0x14000ac2d  call    cs:__imp_GetCurrentProcess
0x14000ac33  mov     r8, rbx; TokenHandle
0x14000ac36  mov     edx, 8; DesiredAccess
0x14000ac3b  mov     rcx, rax; ProcessHandle
0x14000ac3e  call    cs:__imp_OpenProcessToken
0x14000ac44  test    eax, eax
0x14000ac46  jnz     loc_14000ACDB
0x14000ac4c  call    cs:__imp_GetLastError
0x14000ac52  mov     ebx, eax
0x14000ac54  test    eax, eax
0x14000ac56  jle     short loc_14000AC5D
0x14000ac58  movzx   ebx, ax
0x14000ac5b  or      ebx, edi
0x14000ac5d  test    ebx, ebx
0x14000ac5f  cmovns  ebx, r14d
0x14000ac63  mov     eax, cs:dword_14002C000
0x14000ac69  cmp     eax, 2
0x14000ac6c  jbe     loc_14000B05A
0x14000ac72  mov     rcx, cs:qword_14002C018
0x14000ac79  mov     rax, cs:qword_14002C010
0x14000ac80  test    al, 8
0x14000ac82  jz      loc_14000B05A
0x14000ac88  mov     rax, rcx
0x14000ac8b  and     eax, 8
0x14000ac8e  cmp     rax, rcx
0x14000ac91  jnz     loc_14000B05A
0x14000ac97  lea     rdx, byte_14002644B
0x14000ac9e  lea     rax, [rsp+160h+var_120]
0x14000aca3  mov     [rbp+60h+var_60], rax
0x14000aca7  lea     rax, [rbp+60h+var_80]
0x14000acab  xor     r9d, r9d
0x14000acae  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rax
0x14000acb3  xor     r8d, r8d
0x14000acb6  mov     [rsp+160h+dwCreationDisposition], 3
0x14000acbe  mov     [rbp+60h+var_58], 4
0x14000acc6  mov     dword ptr [rsp+160h+var_120], ebx
0x14000acca  lea     rcx, dword_14002C000
0x14000acd1  call    _tlgWriteTransfer_EventWriteTransfer
0x14000acd6  jmp     loc_14000B05A
0x14000acdb  lea     rax, [rsp+160h+nLengthNeeded]
0x14000ace0  mov     qword ptr [rsp+160h+dwCreationDisposition], rax; ReturnLength
0x14000ace5  xor     r9d, r9d; TokenInformationLength
0x14000ace8  xor     r8d, r8d; TokenInformation
  ... truncated ...
```
