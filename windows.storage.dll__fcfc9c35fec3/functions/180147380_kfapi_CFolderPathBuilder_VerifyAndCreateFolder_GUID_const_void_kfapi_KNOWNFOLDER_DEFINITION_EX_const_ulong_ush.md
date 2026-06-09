# kfapi::CFolderPathBuilder::VerifyAndCreateFolder(_GUID const &,void *,kfapi::KNOWNFOLDER_DEFINITION_EX const &,ulong,ushort const *,kfapi::CFolderCache *)

- ea: `0x180147380`
- end: `0x1801478f3`
- name: `?VerifyAndCreateFolder@CFolderPathBuilder@kfapi@@SAJAEBU_GUID@@PEAXAEBUKNOWNFOLDER_DEFINITION_EX@2@KPEBGPEAVCFolderCache@2@@Z`
- size: `1395`
- prototype: `static int(const struct _GUID *, void *, const struct kfapi::KNOWNFOLDER_DEFINITION_EX *, unsigned int, const unsigned __int16 *, struct kfapi::CFolderCache *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180039f10`
- `0x1804f25c0`

## callees

- `0x18003a8e8`
- `0x18003b080`
- `0x1800746f4`
- `0x180077880`
- `0x1801029d8`
- `0x180147380`
- `0x1801478fc`
- `0x180147944`
- `0x180147ae8`
- `0x180147b40`
- `0x180147bfc`
- `0x180147c24`
- `0x180147dbc`
- `0x180148610`
- `0x1801488ec`
- `0x18037aaec`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801476f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801476f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18066b33f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18066b33f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18066b2cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18066b2cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014752d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014752d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801476dd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801476dd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180147554`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180147554`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180147876`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180147876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014746d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014746d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801473f9`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801473f9`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1801474f4`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1801474f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801477c9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801477c9`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18066b2fc`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18066b325`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18066b2fc`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x18066b325`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x18066b295`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x18066b295`

## pseudocode

```c
__int64 __fastcall kfapi::CFolderPathBuilder::VerifyAndCreateFolder(
        struct _GUID *a1,
        struct _GUID *a2,
        const struct kfapi::KNOWNFOLDER_DEFINITION_EX *a3,
        int a4,
        WCHAR *pszPath,
        struct kfapi::CFolderCache *a6)
{
  struct _GUID *v6; // rax
  int v8; // r14d
  int v11; // r13d
  int Error; // ebx
  unsigned int v13; // eax
  __int64 v14; // rax
  const unsigned __int16 *v15; // r8
  const WCHAR *v16; // rcx
  WCHAR *v17; // rax
  int v18; // eax
  void *v19; // r8
  void *v20; // rcx
  DWORD FileAttributesW; // ebx
  int v22; // eax
  struct _GUID *v23; // r13
  int v24; // eax
  int v25; // ecx
  int v26; // r8d
  __int64 *v27; // rdx
  signed int LastError; // eax
  int v30; // eax
  DWORD *pcbData; // [rsp+28h] [rbp-A1h]
  bool v32; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-91h] BYREF
  HKEY hkey; // [rsp+40h] [rbp-89h] BYREF
  struct _GUID *v35; // [rsp+48h] [rbp-81h]
  LPVOID pv; // [rsp+50h] [rbp-79h] BYREF
  void *v37; // [rsp+58h] [rbp-71h] BYREF
  WCHAR *v38; // [rsp+60h] [rbp-69h]
  kfapi::CFolderCache *v39; // [rsp+68h] [rbp-61h]
  WCHAR pszValue[8]; // [rsp+70h] [rbp-59h] BYREF
  void **v41; // [rsp+80h] [rbp-49h]
  unsigned __int64 v42; // [rsp+88h] [rbp-41h]
  WCHAR *v43; // [rsp+A8h] [rbp-21h]

  v6 = a1;
  v8 = 0;
  v35 = a1;
  v39 = a6;
  v11 = 0;
  Error = 0;
  if ( (a4 & 0x8000) == 0 )
    goto LABEL_30;
  v13 = *(_DWORD *)a3 - 3;
  v33 = a4;
  v37 = a2;
  if ( v13 <= 1 )
  {
    if ( (unsigned int)SHWindowsPolicy(POLID_DisableKnownFolders) )
    {
      if ( (int)SHStringFromGUIDW(v35, pszValue, 39) >= 0 )
      {
        hkey = 0;
        if ( !RegOpenKeyExW(
                HKEY_CURRENT_USER,
                L"Software\\Policies\\Microsoft\\Windows\\Explorer\\DisableKnownFolders",
                0,
                0x20019u,
                &hkey) )
        {
          if ( !SHQueryValueExW(hkey, pszValue, 0, 0, 0, 0) || !SHQueryValueExW(hkey, *((LPCWSTR *)a3 + 1), 0, 0, 0, 0) )
            Error = -2147023636;
          RegCloseKey(hkey);
        }
      }
    }
  }
  LODWORD(hkey) = Error;
  if ( Error < 0 )
    goto LABEL_70;
  v14 = *((_QWORD *)a3 + 3) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v14 )
    v14 = *((_QWORD *)a3 + 4) - *(_QWORD *)GUID_NULL.Data4;
  if ( v14 )
  {
    pv = 0;
    Error = SHGetKnownFolderPath_Internal(
              (struct _GUID *)((char *)a3 + 24),
              v33 & 0xEFFFF7FF,
              v37,
              (unsigned __int16 **)&pv);
    LODWORD(hkey) = Error;
    if ( (v33 & 0x20000000) != 0 )
      CZeroInitNew::operator delete(pv);
    else
      CoTaskMemFree(pv);
  }
  *(_QWORD *)pszValue = off_18068E5E0;
  *(_QWORD *)&pszValue[4] = &v33;
  v41 = &v37;
  v43 = pszValue;
  kfapi::ApplyToDependees(a3, v33, pszValue);
  if ( Error < 0 )
  {
LABEL_70:
    DataLayerTelemetry::CreateKnownFolder<_GUID const &,unsigned long &,long &>(v35, &v33, &hkey);
    v23 = v35;
    if ( (Microsoft_Windows_KnownFoldersEnableBits & 1) == 0 )
      goto LABEL_38;
    v26 = Error;
    v27 = Operational_KnownFolder_ErrorCreating;
    goto LABEL_37;
  }
  if ( (*((_BYTE *)a3 + 92) & 0x10) == 0 )
  {
    v41 = 0;
    v16 = (const WCHAR *)*((_QWORD *)a3 + 10);
    LODWORD(hkey) = v33;
    v17 = 0;
    pv = 0;
    v38 = 0;
    *(_OWORD *)pszValue = 0;
    if ( v16 )
    {
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v16, 1u, &pv, 0) )
      {
        *(_QWORD *)&pszValue[4] = pv;
        v17 = pszValue;
        v38 = pszValue;
        wcscpy(pszValue, L"\x18");
        LODWORD(v41) = 0;
      }
      else
      {
        Error = ResultFromLastError();
        if ( Error < 0 )
        {
LABEL_17:
          v20 = pv;
          pv = 0;
          LocalFree(v20);
          goto LABEL_18;
        }
        v17 = 0;
      }
    }
    v18 = SHCreateDirectoryExW(0, pszPath, (const SECURITY_ATTRIBUTES *)v17);
    Error = v18;
    if ( v18 > 0 )
      Error = (unsigned __int16)v18 | 0x80070000;
    if ( (Error == -2147024713 || Error == -2147024816) && v38 && ((unsigned int)hkey & 0x10000000) != 0 )
      Error = kfapi::_ApplyAces(pszPath, *(PSECURITY_DESCRIPTOR *)&pszValue[4], v19);
    goto LABEL_17;
  }
  Error = kfapi::_CreateFile(a3, pszPath, v15);
LABEL_18:
  LODWORD(hkey) = Error;
  if ( Error < 0 )
  {
    if ( Error != -2147024713 && Error != -2147024816 && (Error != -2147024891 || !PathIsRootW(pszPath)) )
      goto LABEL_26;
    FileAttributesW = GetFileAttributesW(pszPath);
    if ( FileAttributesW == -1 )
    {
      v22 = ResultFromLastError();
      if ( v22 < 0 )
        goto LABEL_23;
    }
    else
    {
      v22 = 0;
    }
    if ( ((*((_BYTE *)a3 + 92) | (unsigned __int8)FileAttributesW) & 0x10) == 0 )
    {
      v22 = -2147024816;
      Error = -2147024816;
      LODWORD(hkey) = -2147024816;
      goto LABEL_24;
    }
LABEL_23:
    LODWORD(hkey) = v22;
    Error = v22;
    v32 = 0;
    if ( v22 == -2147024891 )
    {
      if ( IsRunningInAppContainer(v37, &v32) < 0 || !v32 )
        goto LABEL_26;
      Error = 0;
      LODWORD(hkey) = 0;
      goto LABEL_25;
    }
LABEL_24:
    if ( v22 < 0 )
      goto LABEL_26;
LABEL_25:
    if ( (v33 & 0x10000000) == 0 )
      goto LABEL_26;
    goto LABEL_49;
  }
  v11 = 1;
  DataLayerTelemetry::CreateKnownFolder<_GUID const &,unsigned long &,long &>(v35, &v33, &hkey);
LABEL_49:
  if ( (*((_DWORD *)a3 + 22) & 0x182027) != 0 && !SetFileAttributesW(pszPath, *((_DWORD *)a3 + 22) & 0x182027) )
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
      Error = -2147467259;
    LODWORD(hkey) = Error;
  }
LABEL_26:
  if ( Error < 0 )
    goto LABEL_70;
  if ( v11 )
    kfapi::CFolderCache::InvalidateIDLists(v39, v35, a2);
  v6 = v35;
LABEL_30:
  if ( (a4 & 0x80000800) == 0 && !v11 )
  {
LABEL_32:
    v23 = v35;
    if ( Error < 0 )
      goto LABEL_38;
    goto LABEL_33;
  }
  v30 = kfapi::CFolderPathBuilder::_Init(v6, a3, pszPath, a4 & 0x80000000);
  Error = v30;
  if ( v30 )
  {
    if ( v30 != 1 && (v11 || a4 >= 0) )
      goto LABEL_32;
    v23 = v35;
    Error = 0;
  }
  else
  {
    v23 = v35;
    kfapi::CFolderCache::InvalidateIDLists(v39, v35, a2);
  }
LABEL_33:
  if ( (a4 & 0xC800) == 0 )
  {
    v24 = kfapi::CFolderPathBuilder::_Verify(a3, pszPath);
    Error = v24;
    if ( v24 < 0 && (Microsoft_Windows_KnownFoldersEnableBits & 1) != 0 )
    {
      v26 = v24;
      v27 = Operational_KnownFolder_ErrorVerify;
LABEL_37:
      McTemplateU0djz_EtwEventWriteTransfer(v25, (_DWORD)v27, v26, (_DWORD)v23, (__int64)pszPath);
    }
  }
LABEL_38:
  if ( ((Error + 2147024894) & 0xFFFFFFFC) == 0 && Error != -2147024892 )
  {
    kfapi::GetRegistryOverride(pszValue, v23, a2);
    if ( !v41 )
      v8 = Error;
    Error = v8;
    if ( v42 > 7 )
      std::_Deallocate<16>(*(_QWORD *)pszValue, 2 * v42 + 2);
  }
  if ( Error >= 0 )
    kfapi::EnsureDataProtectionForFolder(
      (kfapi *)v23,
      a2,
      a3,
      (const struct kfapi::KNOWNFOLDER_DEFINITION_EX *)(unsigned int)a4,
      (unsigned int)pszPath,
      (const unsigned __int16 *)pcbData);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180147380  push    rbp
0x180147382  push    rbx
0x180147383  push    rsi
0x180147384  push    rdi
0x180147385  push    r12
0x180147387  push    r13
0x180147389  push    r15
0x18014738b  lea     rbp, [rsp-17h]
0x180147390  sub     rsp, 0E0h
0x180147397  mov     rax, cs:__security_cookie
0x18014739e  xor     rax, rsp
0x1801473a1  mov     [rbp+47h+var_50], rax
0x1801473a5  mov     r15, [rbp+47h+pszPath]
0x1801473a9  mov     rax, rcx
0x1801473ac  mov     [rsp+110h+var_38], r14
0x1801473b4  mov     edi, r9d
0x1801473b7  xor     r14d, r14d
0x1801473ba  mov     [rsp+110h+var_C8], rcx
0x1801473bf  mov     rcx, [rbp+47h+arg_28]
0x1801473c3  mov     rsi, r8
0x1801473c6  mov     [rbp+47h+var_A8], rcx
0x1801473ca  mov     r12, rdx
0x1801473cd  mov     r13d, r14d
0x1801473d0  mov     ebx, r14d
0x1801473d3  bt      r9d, 0Fh
0x1801473d8  jnb     loc_1801475B8
0x1801473de  mov     eax, [r8]
0x1801473e1  sub     eax, 3
0x1801473e4  mov     [rsp+110h+var_D8], r9d
0x1801473e9  mov     [rbp+47h+var_B8], rdx
0x1801473ed  cmp     eax, 1
0x1801473f0  ja      short loc_18014740D
0x1801473f2  lea     rcx, POLID_DisableKnownFolders
0x1801473f9  call    cs:__imp_SHWindowsPolicy
0x180147400  nop     dword ptr [rax+rax+00h]
0x180147405  test    eax, eax
0x180147407  jnz     loc_18066B286
0x18014740d  mov     dword ptr [rsp+110h+hkey], ebx
0x180147411  test    ebx, ebx
0x180147413  js      loc_18014781E
0x180147419  mov     rax, [rsi+18h]
0x18014741d  lea     rcx, [rsi+18h]; struct _GUID *
0x180147421  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180147428  jnz     short loc_180147435
0x18014742a  mov     rax, [rcx+8]
0x18014742e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180147435  test    rax, rax
0x180147438  jz      short loc_180147479
0x18014743a  mov     edx, [rsp+110h+var_D8]
0x18014743e  lea     r9, [rbp+47h+pv]; unsigned __int16 **
0x180147442  mov     r8, [rbp+47h+var_B8]; void *
0x180147446  and     edx, 0EFFFF7FFh; unsigned int
0x18014744c  mov     [rbp+47h+pv], r14
0x180147450  call    SHGetKnownFolderPath_Internal
0x180147455  test    [rsp+110h+var_D8], 20000000h
0x18014745d  mov     ebx, eax
0x18014745f  mov     rcx, [rbp+47h+pv]; lpMem
0x180147463  mov     dword ptr [rsp+110h+hkey], eax
0x180147467  jnz     loc_1801476A7
0x18014746d  call    cs:__imp_CoTaskMemFree
0x180147474  nop     dword ptr [rax+rax+00h]
0x180147479  mov     edx, [rsp+110h+var_D8]
0x18014747d  lea     rax, off_18068E5E0
0x180147484  mov     qword ptr [rbp+47h+pszValue], rax
0x180147488  lea     r8, [rbp+47h+pszValue]
0x18014748c  lea     rax, [rsp+110h+var_D8]
0x180147491  mov     rcx, rsi
0x180147494  mov     qword ptr [rbp+47h+pszValue+8], rax
0x180147498  lea     rax, [rbp+47h+var_B8]
0x18014749c  mov     [rbp+47h+var_90], rax
0x1801474a0  lea     rax, [rbp+47h+pszValue]
0x1801474a4  mov     [rbp+47h+var_68], rax
0x1801474a8  call    ?ApplyToDependees@kfapi@@YAXAEBUKNOWNFOLDER_DEFINITION_EX@1@KV?$function@$$A6AXAEBU_GUID@@K@Z@std@@@Z; kfapi::ApplyToDependees(kfapi::KNOWNFOLDER_DEFINITION_EX const &,ulong,std::function<void (_GUID const &,ulong)>)
0x1801474ad  test    ebx, ebx
0x1801474af  js      loc_18014781E
0x1801474b5  test    byte ptr [rsi+5Ch], 10h
0x1801474b9  jnz     loc_180147731
0x1801474bf  mov     eax, [rsp+110h+var_D8]
0x1801474c3  xor     ecx, ecx
0x1801474c5  mov     [rbp+47h+var_90], rcx
0x1801474c9  xorps   xmm0, xmm0
0x1801474cc  mov     rcx, [rsi+50h]; StringSecurityDescriptor
0x1801474d0  mov     dword ptr [rsp+110h+hkey], eax
0x1801474d4  mov     rax, r14
0x1801474d7  mov     [rbp+47h+pv], r14
0x1801474db  mov     [rbp+47h+var_B0], rax
0x1801474df  movups  xmmword ptr [rbp+47h+pszValue], xmm0
0x1801474e3  test    rcx, rcx
0x1801474e6  jnz     loc_1801477BD
0x1801474ec  mov     r8, rax; psa
0x1801474ef  mov     rdx, r15; pszPath
0x1801474f2  xor     ecx, ecx; hwnd
0x1801474f4  call    cs:__imp_SHCreateDirectoryExW
0x1801474fb  nop     dword ptr [rax+rax+00h]
0x180147500  mov     ebx, eax
0x180147502  test    eax, eax
0x180147504  jle     short loc_18014750F
0x180147506  movzx   ebx, ax
0x180147509  or      ebx, 80070000h
0x18014750f  cmp     ebx, 800700B7h
0x180147515  jnz     loc_1801478B6
0x18014751b  cmp     [rbp+47h+var_B0], r13
0x18014751f  jnz     loc_1801477FD
0x180147525  mov     rcx, [rbp+47h+pv]; hMem
0x180147529  mov     [rbp+47h+pv], r14
0x18014752d  call    cs:__imp_LocalFree
0x180147534  nop     dword ptr [rax+rax+00h]
0x180147539  mov     dword ptr [rsp+110h+hkey], ebx
0x18014753d  test    ebx, ebx
0x18014753f  jns     loc_1801476B1
0x180147545  cmp     ebx, 800700B7h
0x18014754b  jnz     loc_18014785B
0x180147551  mov     rcx, r15; lpFileName
0x180147554  call    cs:__imp_GetFileAttributesW
0x18014755b  nop     dword ptr [rax+rax+00h]
0x180147560  mov     ebx, eax
0x180147562  cmp     eax, 0FFFFFFFFh
0x180147565  jz      loc_18014771F
0x18014756b  mov     eax, r14d
0x18014756e  or      ebx, [rsi+5Ch]
0x180147571  test    bl, 10h
0x180147574  jz      loc_18014788F
0x18014757a  mov     dword ptr [rsp+110h+hkey], eax
0x18014757e  mov     ebx, eax
0x180147580  mov     [rsp+110h+var_E0], r13b
0x180147585  cmp     eax, 80070005h
0x18014758a  jz      loc_180147777
0x180147590  test    eax, eax
0x180147592  js      short loc_1801475A2
0x180147594  test    [rsp+110h+var_D8], 10000000h
0x18014759c  jnz     loc_1801476CB
0x1801475a2  test    ebx, ebx
0x1801475a4  js      loc_18014781E
0x1801475aa  test    r13d, r13d
0x1801475ad  jnz     loc_1801478C7
0x1801475b3  mov     rax, [rsp+110h+var_C8]
0x1801475b8  test    edi, 80000800h
0x1801475be  jnz     loc_180147743
0x1801475c4  test    r13d, r13d
0x1801475c7  jnz     loc_180147743
0x1801475cd  mov     r13, [rsp+110h+var_C8]
0x1801475d2  test    ebx, ebx
0x1801475d4  js      short loc_18014760F
0x1801475d6  test    edi, 0C800h
0x1801475dc  jnz     short loc_18014760F
0x1801475de  mov     rdx, r15; unsigned __int16 *
0x1801475e1  mov     rcx, rsi; struct kfapi::KNOWNFOLDER_DEFINITION_EX *
0x1801475e4  call    ?_Verify@CFolderPathBuilder@kfapi@@CAJAEBUKNOWNFOLDER_DEFINITION_EX@2@PEBG@Z; kfapi::CFolderPathBuilder::_Verify(kfapi::KNOWNFOLDER_DEFINITION_EX const &,ushort const *)
0x1801475e9  mov     ebx, eax
0x1801475eb  test    eax, eax
0x1801475ed  jns     short loc_18014760F
0x1801475ef  test    cs:Microsoft_Windows_KnownFoldersEnableBits, 1
0x1801475f6  jz      short loc_18014760F
0x1801475f8  mov     r8d, eax
0x1801475fb  lea     rdx, Operational_KnownFolder_ErrorVerify
0x180147602  mov     r9, r13
0x180147605  mov     [rsp+110h+phkResult], r15
0x18014760a  call    McTemplateU0djz_EtwEventWriteTransfer
0x18014760f  lea     eax, [rbx+7FF8FFFEh]
0x180147615  test    eax, 0FFFFFFFCh
0x18014761a  jz      short loc_18014765F
0x18014761c  mov     r14, [rsp+110h+var_38]
0x180147624  test    ebx, ebx
0x180147626  js      short loc_18014763E
0x180147628  mov     r9d, edi; struct kfapi::KNOWNFOLDER_DEFINITION_EX *
0x18014762b  mov     [rsp+110h+phkResult], r15; unsigned int
0x180147630  mov     r8, rsi; void *
0x180147633  mov     rdx, r12; struct _GUID *
0x180147636  mov     rcx, r13; this
0x180147639  call    ?EnsureDataProtectionForFolder@kfapi@@YAXAEBU_GUID@@PEAXAEBUKNOWNFOLDER_DEFINITION_EX@1@KPEBG@Z; kfapi::EnsureDataProtectionForFolder(_GUID const &,void *,kfapi::KNOWNFOLDER_DEFINITION_EX const &,ulong,ushort const *)
0x18014763e  mov     eax, ebx
0x180147640  mov     rcx, [rbp+47h+var_50]
0x180147644  xor     rcx, rsp; StackCookie
0x180147647  call    __security_check_cookie
0x18014764c  add     rsp, 0E0h
0x180147653  pop     r15
0x180147655  pop     r13
0x180147657  pop     r12
0x180147659  pop     rdi
0x18014765a  pop     rsi
0x18014765b  pop     rbx
0x18014765c  pop     rbp
0x18014765d  retn
0x18014765f  cmp     ebx, 80070004h
0x180147665  jz      short loc_18014761C
0x180147667  mov     r8, r12
0x18014766a  lea     rcx, [rbp+47h+pszValue]
0x18014766e  mov     rdx, r13
0x180147671  call    ?GetRegistryOverride@kfapi@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEAX@Z; kfapi::GetRegistryOverride(_GUID const &,void *)
0x180147676  cmp     [rbp+47h+var_90], 0
0x18014767b  mov     rdx, [rbp+47h+var_88]
0x18014767f  setz    al
0x180147682  test    al, al
0x180147684  cmovnz  r14d, ebx
0x180147688  mov     ebx, r14d
0x18014768b  cmp     rdx, 7
0x18014768f  jbe     short loc_18014761C
0x180147691  mov     rcx, qword ptr [rbp+47h+pszValue]
0x180147695  lea     rdx, ds:2[rdx*2]
0x18014769d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801476a2  jmp     loc_18014761C
0x1801476a7  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x1801476ac  jmp     loc_180147479
0x1801476b1  mov     rcx, [rsp+110h+var_C8]
0x1801476b6  lea     r8, [rsp+110h+hkey]
0x1801476bb  lea     rdx, [rsp+110h+var_D8]
0x1801476c0  mov     r13d, 1
0x1801476c6  call    ??$CreateKnownFolder@AEBU_GUID@@AEAKAEAJ@DataLayerTelemetry@@SAXAEBU_GUID@@AEAKAEAJ@Z; DataLayerTelemetry::CreateKnownFolder<_GUID const &,ulong &,long &>(_GUID const &,ulong &,long &)
0x1801476cb  mov     edx, [rsi+58h]
0x1801476ce  and     edx, 182027h; dwFileAttributes
0x1801476d4  jz      loc_1801475A2
0x1801476da  mov     rcx, r15; lpFileName
0x1801476dd  call    cs:__imp_SetFileAttributesW
0x1801476e4  nop     dword ptr [rax+rax+00h]
0x1801476e9  test    eax, eax
0x1801476eb  jnz     loc_1801475A2
0x1801476f1  call    cs:__imp_GetLastError
0x1801476f8  nop     dword ptr [rax+rax+00h]
0x1801476fd  mov     ebx, eax
0x1801476ff  test    eax, eax
0x180147701  jle     short loc_18014770C
0x180147703  movzx   ebx, ax
0x180147706  or      ebx, 80070000h
0x18014770c  test    ebx, ebx
0x18014770e  mov     eax, 80004005h
0x180147713  cmovns  ebx, eax
0x180147716  mov     dword ptr [rsp+110h+hkey], ebx
0x18014771a  jmp     loc_1801475A2
0x18014771f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180147724  test    eax, eax
0x180147726  jns     loc_18014756E
0x18014772c  jmp     loc_18014757A
0x180147731  mov     rdx, r15; struct kfapi::KNOWNFOLDER_DEFINITION_EX *
0x180147734  mov     rcx, rsi; this
0x180147737  call    ?_CreateFile@kfapi@@YAJAEBUKNOWNFOLDER_DEFINITION_EX@1@PEBG@Z; kfapi::_CreateFile(kfapi::KNOWNFOLDER_DEFINITION_EX const &,ushort const *)
0x18014773c  mov     ebx, eax
0x18014773e  jmp     loc_180147539
0x180147743  mov     r9d, edi
0x180147746  mov     r8, r15; unsigned __int16 *
0x180147749  and     r9d, 80000000h; int
0x180147750  mov     rdx, rsi; struct kfapi::KNOWNFOLDER_DEFINITION_EX *
0x180147753  mov     rcx, rax; struct _GUID *
0x180147756  call    ?_Init@CFolderPathBuilder@kfapi@@CAJAEBU_GUID@@AEBUKNOWNFOLDER_DEFINITION_EX@2@PEBGH@Z; kfapi::CFolderPathBuilder::_Init(_GUID const &,kfapi::KNOWNFOLDER_DEFINITION_EX const &,ushort const *,int)
0x18014775b  mov     ebx, eax
0x18014775d  test    eax, eax
0x18014775f  jz      short loc_1801477A4
0x180147761  cmp     eax, 1
0x180147764  jnz     loc_1801478DD
0x18014776a  mov     r13, [rsp+110h+var_C8]
0x18014776f  mov     ebx, r14d
0x180147772  jmp     loc_1801475D6
0x180147777  mov     rcx, [rbp+47h+var_B8]; void *
0x18014777b  lea     rdx, [rsp+110h+var_E0]; bool *
0x180147780  call    ?IsRunningInAppContainer@@YAJPEAXPEA_N@Z; IsRunningInAppContainer(void *,bool *)
0x180147785  test    eax, eax
0x180147787  js      loc_1801475A2
0x18014778d  cmp     [rsp+110h+var_E0], r13b
0x180147792  jz      loc_1801475A2
0x180147798  mov     ebx, r14d
0x18014779b  mov     dword ptr [rsp+110h+hkey], ebx
0x18014779f  jmp     loc_180147594
0x1801477a4  mov     r13, [rsp+110h+var_C8]
0x1801477a9  mov     r8, r12; void *
0x1801477ac  mov     rcx, [rbp+47h+var_A8]; this
0x1801477b0  mov     rdx, r13; struct _GUID *
0x1801477b3  call    ?InvalidateIDLists@CFolderCache@kfapi@@QEAAXAEBU_GUID@@PEAX@Z; kfapi::CFolderCache::InvalidateIDLists(_GUID const &,void *)
0x1801477b8  jmp     loc_1801475D6
0x1801477bd  xor     r9d, r9d; SecurityDescriptorSize
0x1801477c0  lea     r8, [rbp+47h+pv]; SecurityDescriptor
0x1801477c4  mov     edx, 1; StringSDRevision
0x1801477c9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801477d0  nop     dword ptr [rax+rax+00h]
0x1801477d5  test    eax, eax
0x1801477d7  jz      loc_18014789F
0x1801477dd  mov     rax, [rbp+47h+pv]
0x1801477e1  mov     qword ptr [rbp+47h+pszValue+8], rax
0x1801477e5  lea     rax, [rbp+47h+pszValue]
0x1801477e9  mov     [rbp+47h+var_B0], rax
0x1801477ed  mov     dword ptr [rbp+47h+pszValue], 18h
0x1801477f4  mov     dword ptr [rbp+47h+var_90], r14d
0x1801477f8  jmp     loc_1801474EC
0x1801477fd  test    dword ptr [rsp+110h+hkey], 10000000h
0x180147805  jz      loc_180147525
0x18014780b  mov     rdx, qword ptr [rbp+47h+pszValue+8]; pSecurityDescriptor
0x18014780f  mov     rcx, r15; pObjectName
0x180147812  call    ?_ApplyAces@kfapi@@YAJPEBGPEAX@Z; kfapi::_ApplyAces(ushort const *,void *)
0x180147817  mov     ebx, eax
0x180147819  jmp     loc_180147525
0x18014781e  mov     rcx, [rsp+110h+var_C8]
0x180147823  lea     r8, [rsp+110h+hkey]
0x180147828  lea     rdx, [rsp+110h+var_D8]
0x18014782d  call    ??$CreateKnownFolder@AEBU_GUID@@AEAKAEAJ@DataLayerTelemetry@@SAXAEBU_GUID@@AEAKAEAJ@Z; DataLayerTelemetry::CreateKnownFolder<_GUID const &,ulong &,long &>(_GUID const &,ulong &,long &)
0x180147832  test    ebx, ebx
0x180147834  jns     loc_1801475AA
0x18014783a  test    cs:Microsoft_Windows_KnownFoldersEnableBits, 1
0x180147841  mov     r13, [rsp+110h+var_C8]
0x180147846  jz      loc_18014760F
0x18014784c  mov     r8d, ebx
0x18014784f  lea     rdx, Operational_KnownFolder_ErrorCreating
0x180147856  jmp     loc_180147602
  ... truncated ...
```
