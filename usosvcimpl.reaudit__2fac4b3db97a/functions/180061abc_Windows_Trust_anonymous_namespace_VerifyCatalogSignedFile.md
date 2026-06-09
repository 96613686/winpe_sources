# Windows::Trust::_anonymous_namespace_::VerifyCatalogSignedFile

- ea: `0x180061abc`
- end: `0x18006200d`
- name: `Windows::Trust::_anonymous_namespace_::VerifyCatalogSignedFile`
- size: `1361`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18006222c`

## callees

- `0x1800108b4`
- `0x180061a68`
- `0x180061abc`
- `0x180062b98`
- `0x180062d54`
- `0x180062de4`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061fda`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061b1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061b1e`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180061dab`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x180061dab`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180061b5d`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x180061b5d`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180061dc5`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180061dc5`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x180061bc4`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x180061bc4`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180061cdb`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x180061cdb`
- `WINTRUST!WinVerifyTrust` at `0x180061d7f`
- `WINTRUST!WinVerifyTrust` at `0x180061e09`
- `WINTRUST!WinVerifyTrust` at `0x180061e85`
- `WINTRUST!WinVerifyTrust` at `0x180061d7f`
- `WINTRUST!WinVerifyTrust` at `0x180061e09`
- `WINTRUST!WinVerifyTrust` at `0x180061e85`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Trust::_anonymous_namespace_::VerifyCatalogSignedFile(__int64 a1, LPCWSTR *a2)
{
  char *FileW; // rbx
  signed int v4; // edi
  unsigned int v5; // ecx
  HCATADMIN *v6; // rax
  signed int v7; // edi
  unsigned int v8; // ecx
  volatile signed __int32 *v9; // rdi
  void (__fastcall **v10)(_QWORD); // rax
  volatile signed __int32 *v11; // rcx
  DWORD v12; // ecx
  volatile signed __int32 *v13; // rsi
  GUID *v14; // rdx
  CRYPT_PROVIDER_DATA *v15; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  signed int LastError; // edi
  unsigned int v20; // ecx
  signed int v21; // edi
  unsigned int v22; // ecx
  __int128 v24; // [rsp+40h] [rbp-C0h] BYREF
  char *v25; // [rsp+58h] [rbp-A8h]
  _QWORD pWVTData[12]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v27[10]; // [rsp+C0h] [rbp-40h] BYREF
  GUID v28; // [rsp+110h] [rbp+10h] BYREF
  GUID pgActionID; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v30[4]; // [rsp+130h] [rbp+30h] BYREF
  DWORD pcbHash[2]; // [rsp+140h] [rbp+40h] BYREF
  HCATINFO hCatInfo[4]; // [rsp+148h] [rbp+48h] BYREF
  DWORD v33; // [rsp+168h] [rbp+68h]
  char v34; // [rsp+16Ch] [rbp+6Ch]
  BYTE pbHash[64]; // [rsp+170h] [rbp+70h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+1B0h] [rbp+B0h] BYREF

  *(_QWORD *)pcbHash = a1;
  FileW = (char *)CreateFileW(*a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v25 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset(pbHash, 0, sizeof(pbHash));
    pcbHash[0] = 64;
    if ( CryptCATAdminCalcHashFromFileHandle(FileW, pcbHash, pbHash, 0) )
    {
      v24 = 0;
      v6 = (HCATADMIN *)__I__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CryptCATAdminReleaseContextNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil___wil__QEAAPEAPEAXXZ(&v24);
      if ( CryptCATAdminAcquireContext(v6, 0, 0) )
      {
        v12 = pcbHash[0];
        v13 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
        if ( *((_QWORD *)&v24 + 1) )
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL));
        hCatInfo[0] = 0;
        hCatInfo[1] = (HCATINFO)v24;
        hCatInfo[2] = (HCATINFO)v13;
        hCatInfo[3] = pbHash;
        v33 = v12;
        v34 = 1;
        wil::details::crypt_catalog_enumerator::move_next((wil::details::crypt_catalog_enumerator *)hCatInfo);
        while ( hCatInfo[0] )
        {
          psCatInfo.cbStruct = 524;
          memset(psCatInfo.wszCatalogFile, 0, sizeof(psCatInfo.wszCatalogFile));
          if ( !CryptCATCatalogInfoFromContext(hCatInfo[0], &psCatInfo, 0) )
          {
            LastError = GetLastError();
            *(_OWORD *)a1 = 0;
            *(_QWORD *)(a1 + 16) = 0;
            *(_QWORD *)(a1 + 24) = 0;
            std::wstring::_Construct<1,wchar_t const *>(a1, L"CryptCATCatalogInfoFromContext returned false", 45);
            v20 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v20 = LastError;
            *(_DWORD *)(a1 + 32) = v20;
            goto LABEL_36;
          }
          memset(v27, 0, 0x48u);
          LODWORD(v27[0]) = 72;
          v27[4] = FileW;
          v27[5] = pbHash;
          LODWORD(v27[6]) = pcbHash[0];
          v27[1] = psCatInfo.wszCatalogFile;
          memset(pWVTData, 0, 0x58u);
          LODWORD(pWVTData[0]) = 88;
          pWVTData[3] = 0x100000002LL;
          LODWORD(pWVTData[9]) = 4160;
          LODWORD(pWVTData[4]) = 2;
          pWVTData[5] = v27;
          LODWORD(pWVTData[6]) = 1;
          pgActionID.Data1 = 11191659;
          *(_DWORD *)&pgActionID.Data2 = 298896708;
          *(_DWORD *)pgActionID.Data4 = -1073692020;
          *(_DWORD *)&pgActionID.Data4[4] = -292175281;
          if ( WinVerifyTrust(0, &pgActionID, pWVTData) )
          {
            v30[0] = 11191659;
            v30[1] = 298896708;
            v30[2] = -1073692020;
            v30[3] = -292175281;
            v14 = (GUID *)v30;
          }
          else
          {
            v15 = WTHelperProvDataFromStateData((HANDLE)pWVTData[7]);
            if ( !v15 )
            {
              v17 = 29;
              v18 = L"WTHelperProvDataFromStateData";
              goto LABEL_31;
            }
            ProvSignerFromChain = WTHelperGetProvSignerFromChain(v15, 0, 0, 0);
            if ( !ProvSignerFromChain )
            {
              v17 = 30;
              v18 = L"WTHelperGetProvSignerFromChain";
LABEL_31:
              *(_OWORD *)a1 = 0;
              *(_QWORD *)(a1 + 24) = 0;
              *(_QWORD *)(a1 + 16) = 0;
              std::wstring::_Construct<1,wchar_t const *>(a1, v18, v17);
              *(_DWORD *)(a1 + 32) = -2147024882;
LABEL_29:
              v28.Data1 = 11191659;
              *(_DWORD *)&v28.Data2 = 298896708;
              *(_DWORD *)v28.Data4 = -1073692020;
              *(_DWORD *)&v28.Data4[4] = -292175281;
              LODWORD(pWVTData[6]) = 2;
              WinVerifyTrust(HWND_MESSAGE|0x2LL, &v28, pWVTData);
LABEL_36:
              wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>(hCatInfo);
              goto LABEL_37;
            }
            if ( !(unsigned __int8)Windows::Trust::_anonymous_namespace_::VerifyCertificateChains(ProvSignerFromChain->pChainContext) )
            {
              *(_OWORD *)a1 = 0;
              *(_QWORD *)(a1 + 16) = 0;
              *(_QWORD *)(a1 + 24) = 0;
              std::wstring::_Construct<1,wchar_t const *>(a1, L"VerifyCertificateChains returned false", 38);
              *(_DWORD *)(a1 + 32) = -2147024891;
              goto LABEL_29;
            }
            v28.Data1 = 11191659;
            *(_DWORD *)&v28.Data2 = 298896708;
            *(_DWORD *)v28.Data4 = -1073692020;
            *(_DWORD *)&v28.Data4[4] = -292175281;
            v14 = &v28;
          }
          LODWORD(pWVTData[6]) = 2;
          WinVerifyTrust(HWND_MESSAGE|0x2LL, v14, pWVTData);
          if ( v34 && hCatInfo[0] )
            wil::details::crypt_catalog_enumerator::move_next((wil::details::crypt_catalog_enumerator *)hCatInfo);
        }
        wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>(hCatInfo);
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        std::wstring::_Construct<1,wchar_t const *>(a1, &S1, 0);
        *(_DWORD *)(a1 + 32) = 0;
LABEL_37:
        if ( !v13 )
          goto LABEL_46;
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) != 1 )
          goto LABEL_46;
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) != 1 )
          goto LABEL_46;
        v10 = *(void (__fastcall ***)(_QWORD))v13;
        v11 = v13;
      }
      else
      {
        v7 = GetLastError();
        *(_OWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        std::wstring::_Construct<1,wchar_t const *>(a1, L"CryptCATAdminAcquireContext returned false", 42);
        v8 = (unsigned __int16)v7 | 0x80070000;
        if ( v7 <= 0 )
          v8 = v7;
        *(_DWORD *)(a1 + 32) = v8;
        v9 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
        if ( !*((_QWORD *)&v24 + 1) )
          goto LABEL_46;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) != 1 )
          goto LABEL_46;
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) != 1 )
          goto LABEL_46;
        v10 = *(void (__fastcall ***)(_QWORD))v9;
        v11 = v9;
      }
      ((void (__fastcall **)(volatile signed __int32 *))v10)[1](v11);
    }
    else
    {
      v4 = GetLastError();
      *(_OWORD *)a1 = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      std::wstring::_Construct<1,wchar_t const *>(a1, L"CryptCATAdminCalcHashFromFileHandle returned false", 50);
      v5 = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        v5 = v4;
      *(_DWORD *)(a1 + 32) = v5;
    }
LABEL_46:
    CloseHandle(FileW);
    return a1;
  }
  v21 = GetLastError();
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a1, L"Invalid file handle", 19);
  v22 = (unsigned __int16)v21 | 0x80070000;
  if ( v21 <= 0 )
    v22 = v21;
  *(_DWORD *)(a1 + 32) = v22;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_46;
  return a1;
}

```

## disassembly

```asm
0x180061abc  mov     [rsp-8+arg_10], rbx
0x180061ac1  push    rbp
0x180061ac2  push    rsi
0x180061ac3  push    rdi
0x180061ac4  push    r12
0x180061ac6  push    r13
0x180061ac8  push    r14
0x180061aca  push    r15
0x180061acc  lea     rbp, [rsp-2D0h]
0x180061ad4  sub     rsp, 3D0h
0x180061adb  mov     rax, cs:__security_cookie
0x180061ae2  xor     rax, rsp
0x180061ae5  mov     [rbp+300h+var_40], rax
0x180061aec  mov     rax, rdx
0x180061aef  mov     r14, rcx
0x180061af2  mov     qword ptr [rbp+300h+pcbHash], rcx
0x180061af6  xor     r12d, r12d
0x180061af9  mov     [rsp+400h+hTemplateFile], r12; hTemplateFile
0x180061afe  mov     [rsp+400h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180061b06  mov     [rsp+400h+dwCreationDisposition], 3; dwCreationDisposition
0x180061b0e  xor     r9d, r9d; lpSecurityAttributes
0x180061b11  mov     edx, 80000000h; dwDesiredAccess
0x180061b16  lea     r8d, [r12+1]; dwShareMode
0x180061b1b  mov     rcx, [rax]; lpFileName
0x180061b1e  call    cs:__imp_CreateFileW
0x180061b24  mov     rbx, rax
0x180061b27  mov     [rsp+400h+var_3A8], rax
0x180061b2c  dec     rax
0x180061b2f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061b33  ja      loc_180061F8F
0x180061b39  lea     edi, [r12+40h]
0x180061b3e  mov     r8d, edi; Size
0x180061b41  xor     edx, edx; Val
0x180061b43  lea     rcx, [rbp+300h+pbHash]; void *
0x180061b47  call    memset
0x180061b4c  mov     [rbp+300h+pcbHash], edi
0x180061b4f  xor     r9d, r9d; dwFlags
0x180061b52  lea     r8, [rbp+300h+pbHash]; pbHash
0x180061b56  lea     rdx, [rbp+300h+pcbHash]; pcbHash
0x180061b5a  mov     rcx, rbx; hFile
0x180061b5d  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x180061b63  test    eax, eax
0x180061b65  jnz     short loc_180061BA9
0x180061b67  call    cs:__imp_GetLastError
0x180061b6d  mov     edi, eax
0x180061b6f  xorps   xmm0, xmm0
0x180061b72  movups  xmmword ptr [r14], xmm0
0x180061b76  mov     [r14+10h], r12
0x180061b7a  mov     [r14+18h], r12
0x180061b7e  lea     r8d, [r12+32h]
0x180061b83  lea     rdx, aCryptcatadminc; "CryptCATAdminCalcHashFromFileHandle ret"...
0x180061b8a  mov     rcx, r14
0x180061b8d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180061b92  movzx   ecx, di
0x180061b95  or      ecx, 80070000h
0x180061b9b  test    edi, edi
0x180061b9d  cmovle  ecx, edi
0x180061ba0  mov     [r14+20h], ecx
0x180061ba4  jmp     loc_180061FD7
0x180061ba9  xorps   xmm1, xmm1
0x180061bac  movdqu  [rsp+400h+var_3C0], xmm1
0x180061bb2  lea     rcx, [rsp+400h+var_3C0]
0x180061bb7  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CryptCATAdminReleaseContextNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ
0x180061bbc  mov     rcx, rax; phCatAdmin
0x180061bbf  xor     r8d, r8d; dwFlags
0x180061bc2  xor     edx, edx; pgSubsystem
0x180061bc4  call    cs:__imp_CryptCATAdminAcquireContext
0x180061bca  test    eax, eax
0x180061bcc  jnz     loc_180061C59
0x180061bd2  call    cs:__imp_GetLastError
0x180061bd8  mov     edi, eax
0x180061bda  xorps   xmm0, xmm0
0x180061bdd  movups  xmmword ptr [r14], xmm0
0x180061be1  mov     [r14+10h], r12
0x180061be5  mov     [r14+18h], r12
0x180061be9  mov     r8d, 2Ah ; '*'
0x180061bef  lea     rdx, aCryptcatadmina; "CryptCATAdminAcquireContext returned fa"...
0x180061bf6  mov     rcx, r14
0x180061bf9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180061bfe  movzx   ecx, di
0x180061c01  or      ecx, 80070000h
0x180061c07  test    edi, edi
0x180061c09  cmovle  ecx, edi
0x180061c0c  mov     [r14+20h], ecx
0x180061c10  mov     rdi, qword ptr [rsp+400h+var_3C0+8]
0x180061c15  test    rdi, rdi
0x180061c18  jz      short loc_180061BA4
0x180061c1a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180061c1e  mov     eax, r15d
0x180061c21  lock xadd [rdi+8], eax
0x180061c26  add     eax, r15d
0x180061c29  jnz     loc_180061BA4
0x180061c2f  mov     rax, [rdi]
0x180061c32  mov     rcx, rdi
0x180061c35  mov     rax, [rax]
0x180061c38  call    _guard_dispatch_icall
0x180061c3d  mov     eax, r15d
0x180061c40  lock xadd [rdi+0Ch], eax
0x180061c45  add     eax, r15d
0x180061c48  jnz     loc_180061BA4
0x180061c4e  mov     rax, [rdi]
0x180061c51  mov     rcx, rdi
0x180061c54  jmp     loc_180061F51
0x180061c59  mov     ecx, [rbp+300h+pcbHash]
0x180061c5c  mov     rsi, qword ptr [rsp+400h+var_3C0+8]
0x180061c61  test    rsi, rsi
0x180061c64  jz      short loc_180061C6A
0x180061c66  lock inc dword ptr [rsi+8]
0x180061c6a  mov     [rbp+300h+hCatInfo], r12
0x180061c6e  mov     rax, qword ptr [rsp+400h+var_3C0]
0x180061c73  mov     [rbp+300h+var_2B0], rax
0x180061c77  mov     [rbp+300h+var_2A8], rsi
0x180061c7b  lea     rax, [rbp+300h+pbHash]
0x180061c7f  mov     [rbp+300h+var_2A0], rax
0x180061c83  mov     [rbp+300h+var_298], ecx
0x180061c86  mov     [rbp+300h+var_294], 1
0x180061c8a  lea     rcx, [rbp+300h+hCatInfo]; this
0x180061c8e  call    ?move_next@crypt_catalog_enumerator@details@wil@@AEAA_NXZ; wil::details::crypt_catalog_enumerator::move_next(void)
0x180061c93  or      r15, 0FFFFFFFFFFFFFFFFh
0x180061c97  lea     r13d, [r15+3]
0x180061c9b  mov     rdi, [rbp+300h+hCatInfo]
0x180061c9f  test    rdi, rdi
0x180061ca2  jz      loc_180061F5F
0x180061ca8  mov     [rbp+300h+psCatInfo.cbStruct], 20Ch
0x180061cb2  mov     [rbp+300h+psCatInfo.wszCatalogFile], r12w
0x180061cba  xor     edx, edx; Val
0x180061cbc  mov     r8d, 206h; Size
0x180061cc2  lea     rcx, [rbp+300h+psCatInfo.wszCatalogFile+2]; void *
0x180061cc9  call    memset
0x180061cce  xor     r8d, r8d; dwFlags
0x180061cd1  lea     rdx, [rbp+300h+psCatInfo]; psCatInfo
0x180061cd8  mov     rcx, rdi; hCatInfo
0x180061cdb  call    cs:__imp_CryptCATCatalogInfoFromContext
0x180061ce1  test    eax, eax
0x180061ce3  jz      loc_180061ECA
0x180061ce9  mov     edi, 48h ; 'H'
0x180061cee  mov     r8d, edi; Size
0x180061cf1  xor     edx, edx; Val
0x180061cf3  lea     rcx, [rbp+300h+var_340]; void *
0x180061cf7  call    memset
0x180061cfc  mov     [rbp+300h+var_340], edi
0x180061cff  mov     [rbp+300h+var_320], rbx
0x180061d03  lea     rax, [rbp+300h+pbHash]
0x180061d07  mov     [rbp+300h+var_318], rax
0x180061d0b  mov     eax, [rbp+300h+pcbHash]
0x180061d0e  mov     [rbp+300h+var_310], eax
0x180061d11  lea     rax, [rbp+300h+psCatInfo.wszCatalogFile]
0x180061d18  mov     [rbp+300h+var_338], rax
0x180061d1c  mov     edi, 58h ; 'X'
0x180061d21  mov     r8d, edi; Size
0x180061d24  xor     edx, edx; Val
0x180061d26  lea     rcx, [rsp+400h+pWVTData]; void *
0x180061d2b  call    memset
0x180061d30  nop
0x180061d31  mov     [rsp+400h+pWVTData], edi
0x180061d35  mov     [rsp+400h+var_388], r13d
0x180061d3a  lea     ecx, [rdi-57h]
0x180061d3d  mov     [rsp+400h+var_384], ecx
0x180061d41  mov     [rbp+300h+var_358], 1040h
0x180061d48  mov     [rbp+300h+var_380], r13d
0x180061d4c  lea     rax, [rbp+300h+var_340]
0x180061d50  mov     [rbp+300h+var_378], rax
0x180061d54  mov     [rbp+300h+var_370], ecx
0x180061d57  mov     edi, 0AAC56Bh
0x180061d5c  mov     [rbp+300h+pgActionID.Data1], edi
0x180061d5f  mov     dword ptr [rbp+300h+pgActionID.Data2], 11D0CD44h
0x180061d66  mov     dword ptr [rbp+300h+pgActionID.Data4], 0C000C28Ch
0x180061d6d  mov     dword ptr [rbp+300h+pgActionID.Data4+4], 0EE95C24Fh
0x180061d74  lea     r8, [rsp+400h+pWVTData]; pWVTData
0x180061d79  lea     rdx, [rbp+300h+pgActionID]; pgActionID
0x180061d7d  xor     ecx, ecx; hwnd
0x180061d7f  call    cs:__imp_WinVerifyTrust
0x180061d85  test    eax, eax
0x180061d87  jz      short loc_180061DA7
0x180061d89  mov     [rbp+300h+var_2D0], edi
0x180061d8c  mov     [rbp+300h+var_2CC], 11D0CD44h
0x180061d93  mov     [rbp+300h+var_2C8], 0C000C28Ch
0x180061d9a  mov     [rbp+300h+var_2C4], 0EE95C24Fh
0x180061da1  lea     rdx, [rbp+300h+var_2D0]
0x180061da5  jmp     short loc_180061DFD
0x180061da7  mov     rcx, [rbp+300h+hStateData]; hStateData
0x180061dab  call    cs:__imp_WTHelperProvDataFromStateData
0x180061db1  test    rax, rax
0x180061db4  jz      loc_180061EBB
0x180061dba  xor     r9d, r9d; idxCounterSigner
0x180061dbd  xor     r8d, r8d; fCounterSigner
0x180061dc0  xor     edx, edx; idxSigner
0x180061dc2  mov     rcx, rax; pProvData
0x180061dc5  call    cs:__imp_WTHelperGetProvSignerFromChain
0x180061dcb  test    rax, rax
0x180061dce  jz      loc_180061E8D
0x180061dd4  mov     rcx, [rax+38h]; pChainContext
0x180061dd8  call    Windows__Trust___anonymous_namespace___VerifyCertificateChains
0x180061ddd  test    al, al
0x180061ddf  jz      short loc_180061E31
0x180061de1  mov     [rbp+300h+var_2F0.Data1], edi
0x180061de4  mov     dword ptr [rbp+300h+var_2F0.Data2], 11D0CD44h
0x180061deb  mov     dword ptr [rbp+300h+var_2F0.Data4], 0C000C28Ch
0x180061df2  mov     dword ptr [rbp+300h+var_2F0.Data4+4], 0EE95C24Fh
0x180061df9  lea     rdx, [rbp+300h+var_2F0]; pgActionID
0x180061dfd  mov     [rbp+300h+var_370], r13d
0x180061e01  lea     r8, [rsp+400h+pWVTData]; pWVTData
0x180061e06  mov     rcx, r15; hwnd
0x180061e09  call    cs:__imp_WinVerifyTrust
0x180061e0f  cmp     [rbp+300h+var_294], r12b
0x180061e13  jz      loc_180061C9B
0x180061e19  cmp     [rbp+300h+hCatInfo], r12
0x180061e1d  jz      loc_180061C9B
0x180061e23  lea     rcx, [rbp+300h+hCatInfo]; this
0x180061e27  call    ?move_next@crypt_catalog_enumerator@details@wil@@AEAA_NXZ; wil::details::crypt_catalog_enumerator::move_next(void)
0x180061e2c  jmp     loc_180061C9B
0x180061e31  xorps   xmm0, xmm0
0x180061e34  movups  xmmword ptr [r14], xmm0
0x180061e38  mov     [r14+10h], r12
0x180061e3c  mov     [r14+18h], r12
0x180061e40  mov     r8d, 26h ; '&'
0x180061e46  lea     rdx, aVerifycertific; "VerifyCertificateChains returned false"
0x180061e4d  mov     rcx, r14
0x180061e50  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180061e55  mov     dword ptr [r14+20h], 80070005h
0x180061e5d  mov     [rbp+300h+var_2F0.Data1], edi
0x180061e60  mov     dword ptr [rbp+300h+var_2F0.Data2], 11D0CD44h
0x180061e67  mov     dword ptr [rbp+300h+var_2F0.Data4], 0C000C28Ch
0x180061e6e  mov     dword ptr [rbp+300h+var_2F0.Data4+4], 0EE95C24Fh
0x180061e75  mov     [rbp+300h+var_370], r13d
0x180061e79  lea     r8, [rsp+400h+pWVTData]; pWVTData
0x180061e7e  lea     rdx, [rbp+300h+var_2F0]; pgActionID
0x180061e82  mov     rcx, r15; hwnd
0x180061e85  call    cs:__imp_WinVerifyTrust
0x180061e8b  jmp     short loc_180061F08
0x180061e8d  mov     r8d, 1Eh
0x180061e93  lea     rdx, aWthelpergetpro; "WTHelperGetProvSignerFromChain"
0x180061e9a  xorps   xmm0, xmm0
0x180061e9d  movups  xmmword ptr [r14], xmm0
0x180061ea1  mov     [r14+18h], r12
0x180061ea5  mov     [r14+10h], r12
0x180061ea9  mov     rcx, r14
0x180061eac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180061eb1  mov     dword ptr [r14+20h], 8007000Eh
0x180061eb9  jmp     short loc_180061E5D
0x180061ebb  mov     r8d, 1Dh
0x180061ec1  lea     rdx, aWthelperprovda; "WTHelperProvDataFromStateData"
0x180061ec8  jmp     short loc_180061E9A
0x180061eca  call    cs:__imp_GetLastError
0x180061ed0  mov     edi, eax
0x180061ed2  xorps   xmm0, xmm0
0x180061ed5  movups  xmmword ptr [r14], xmm0
0x180061ed9  mov     [r14+10h], r12
0x180061edd  mov     [r14+18h], r12
0x180061ee1  mov     r8d, 2Dh ; '-'
0x180061ee7  lea     rdx, aCryptcatcatalo; "CryptCATCatalogInfoFromContext returned"...
0x180061eee  mov     rcx, r14
0x180061ef1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180061ef6  movzx   ecx, di
0x180061ef9  or      ecx, 80070000h
0x180061eff  test    edi, edi
0x180061f01  cmovle  ecx, edi
0x180061f04  mov     [r14+20h], ecx
0x180061f08  lea     rcx, [rbp+300h+hCatInfo]
0x180061f0c  call    ??1?$unique_ptr@XUhcatinfo_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>(void)
0x180061f11  nop
0x180061f12  test    rsi, rsi
0x180061f15  jz      loc_180061BA4
0x180061f1b  mov     eax, r15d
0x180061f1e  lock xadd [rsi+8], eax
0x180061f23  add     eax, r15d
0x180061f26  jnz     loc_180061BA4
0x180061f2c  mov     rax, [rsi]
0x180061f2f  mov     rcx, rsi
0x180061f32  mov     rax, [rax]
0x180061f35  call    _guard_dispatch_icall
0x180061f3a  mov     eax, r15d
0x180061f3d  lock xadd [rsi+0Ch], eax
0x180061f42  add     eax, r15d
0x180061f45  jnz     loc_180061BA4
0x180061f4b  mov     rax, [rsi]
0x180061f4e  mov     rcx, rsi
0x180061f51  mov     rax, [rax+8]
0x180061f55  call    _guard_dispatch_icall
0x180061f5a  jmp     loc_180061BA4
0x180061f5f  lea     rcx, [rbp+300h+hCatInfo]
0x180061f63  call    ??1?$unique_ptr@XUhcatinfo_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<void,wil::hcatinfo_deleter>::~unique_ptr<void,wil::hcatinfo_deleter>(void)
0x180061f68  xorps   xmm0, xmm0
0x180061f6b  movups  xmmword ptr [r14], xmm0
0x180061f6f  mov     [r14+10h], r12
0x180061f73  mov     [r14+18h], r12
0x180061f77  xor     r8d, r8d
0x180061f7a  lea     rdx, S1
0x180061f81  mov     rcx, r14
0x180061f84  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180061f89  mov     [r14+20h], r12d
0x180061f8d  jmp     short loc_180061F12
0x180061f8f  call    cs:__imp_GetLastError
0x180061f95  mov     edi, eax
0x180061f97  xorps   xmm0, xmm0
0x180061f9a  movups  xmmword ptr [r14], xmm0
0x180061f9e  mov     [r14+10h], r12
0x180061fa2  mov     [r14+18h], r12
0x180061fa6  mov     r8d, 13h
0x180061fac  lea     rdx, aInvalidFileHan; "Invalid file handle"
  ... truncated ...
```
