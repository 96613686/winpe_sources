# kfapi::CFolderCreator::CreateTargetFolder(kfapi::CFolderCreationInfo &)

- ea: `0x1803869a4`
- end: `0x180386ebb`
- name: `?CreateTargetFolder@CFolderCreator@kfapi@@CAJAEAVCFolderCreationInfo@2@@Z`
- size: `1303`
- prototype: `__int64 __fastcall(struct kfapi::CFolderCreationInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1803869a4`
- `0x18061e4fc`

## callees

- `0x180033d90`
- `0x1800899a4`
- `0x1800d9e50`
- `0x180147bfc`
- `0x1803869a4`
- `0x180386ec4`
- `0x1803870b4`
- `0x18061e47c`
- `0x18061e6e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180386c2f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180386c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180386a1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180386bf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180386a1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180386bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180386bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180386bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180386bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180386bfe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180386a02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180386a02`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180386a36`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180386a36`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180386bda`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180386ca1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180386bda`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180386ca1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1803869be`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1803869be`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180386de1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180386de1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180386aec`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180386d9c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180386aec`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180386d9c`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180386aae`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180386d42`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180386aae`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180386d42`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180386b16`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180386e93`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180386b16`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180386e93`

## pseudocode

```c
signed int __fastcall kfapi::CFolderCreator::CreateTargetFolder(struct kfapi::CFolderCreationInfo *a1)
{
  BOOL IsRootW; // eax
  const WCHAR *v3; // rcx
  LPCWSTR v4; // rax
  _BYTE *v5; // rbx
  bool v6; // zf
  signed int TokenUser; // r14d
  const WCHAR *v8; // rcx
  signed int NamedSecurityInfoW; // eax
  bool v10; // cc
  PSECURITY_DESCRIPTOR v11; // rcx
  PSID *v12; // r14
  PSECURITY_DESCRIPTOR v13; // rcx
  int v14; // eax
  int v15; // eax
  signed int result; // eax
  unsigned int v17; // edx
  DWORD FileAttributesW; // eax
  DWORD v19; // ecx
  signed int LastError; // eax
  wchar_t *v21; // rax
  wchar_t *v22; // r15
  int v23; // edi
  int v24; // ebx
  int TargetFolder; // eax
  char v26; // bl
  DWORD v27; // eax
  int v28; // r11d
  int v29; // ecx
  int v30; // r11d
  SECURITY_INFORMATION v31; // r8d
  signed int v32; // eax
  PSECURITY_DESCRIPTOR v33; // rcx
  PSID *v34; // r14
  PSECURITY_DESCRIPTOR v35; // rcx
  int Error; // eax
  PSECURITY_DESCRIPTOR v37; // rcx
  int v38; // ebx
  int v39; // eax
  PSECURITY_DESCRIPTOR v40; // rcx
  unsigned int v41; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp-38h] BYREF
  WORD pControl; // [rsp+48h] [rbp-30h] BYREF
  PSID pSid1; // [rsp+50h] [rbp-28h] BYREF
  PSID ppsidOwner; // [rsp+58h] [rbp-20h] BYREF
  DWORD dwRevision[2]; // [rsp+60h] [rbp-18h] BYREF
  __int64 v49; // [rsp+68h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  IsRootW = PathIsRootW(*(LPCWSTR *)a1);
  v3 = *(const WCHAR **)a1;
  if ( IsRootW )
  {
    ppsidOwner = CreateFileW(v3, 0, 7u, 0, 3u, 0x2000000u, 0);
    if ( ppsidOwner != (PSID)-1LL )
      SetLastError(0xB7u);
    CAutoHandle<void *>::~CAutoHandle<void *>(&ppsidOwner);
    goto LABEL_31;
  }
  if ( CreateDirectoryW(v3, 0) )
  {
    v4 = *(LPCWSTR *)a1;
    v5 = (char *)a1 + 8;
    v6 = (*((_BYTE *)a1 + 8) & 8) == 0;
    *((_BYTE *)a1 + 45) = 1;
    *(_QWORD *)dwRevision = v4;
    if ( !v6 )
    {
      pSid1 = 0;
      TokenUser = kfapi::CFolderCreationInfo::GetTokenUser(a1, (struct _TOKEN_USER **)&pSid1);
      if ( TokenUser < 0 )
      {
LABEL_21:
        kfapi::CDirectoryRemover::~CDirectoryRemover((kfapi::CDirectoryRemover *)dwRevision);
        return TokenUser;
      }
      v8 = *(const WCHAR **)a1;
      ppsidOwner = 0;
      pSecurityDescriptor = 0;
      NamedSecurityInfoW = GetNamedSecurityInfoW(v8, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &pSecurityDescriptor);
      TokenUser = NamedSecurityInfoW;
      v10 = NamedSecurityInfoW <= 0;
      if ( NamedSecurityInfoW
        || ((v12 = (PSID *)pSid1, !ppsidOwner) || !EqualSid(ppsidOwner, *(PSID *)pSid1))
        && (NamedSecurityInfoW = SetNamedSecurityInfoW(*(LPWSTR *)a1, SE_FILE_OBJECT, 1u, *v12, 0, 0, 0),
            TokenUser = NamedSecurityInfoW,
            v10 = NamedSecurityInfoW <= 0,
            NamedSecurityInfoW) )
      {
        if ( !v10 )
          TokenUser = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
        v11 = pSecurityDescriptor;
        pSecurityDescriptor = 0;
        CTContainer_PolicyLocalMem::DestroyMem(v11);
        goto LABEL_21;
      }
      v13 = pSecurityDescriptor;
      pSecurityDescriptor = 0;
      CTContainer_PolicyLocalMem::DestroyMem(v13);
    }
    if ( (*v5 & 1) != 0 )
    {
      pSid1 = 0;
      v14 = kfapi::CFolderCreationInfo::GetTokenUser(a1, (struct _TOKEN_USER **)&pSid1);
      if ( v14 < 0 )
      {
        TokenUser = v14;
        goto LABEL_21;
      }
      v15 = kfapi::CFolderCreator::SetDirectoryUserExclusive(*(LPWSTR *)a1, *(PSID *)pSid1);
      TokenUser = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\foldercreator.cpp",
          (const char *)(unsigned int)v15,
          dwCreationDisposition);
        goto LABEL_21;
      }
    }
    v17 = *((_DWORD *)a1 + 10);
    if ( v17 != -1 )
      kfapi::CFolderCreator::CopyFolderAttributes(*(LPCWSTR *)a1, v17, *((_BYTE *)a1 + 46));
    *(_QWORD *)dwRevision = 0;
    kfapi::CDirectoryRemover::~CDirectoryRemover((kfapi::CDirectoryRemover *)dwRevision);
    goto LABEL_65;
  }
  if ( GetLastError() == 5 )
  {
    FileAttributesW = GetFileAttributesW(*(LPCWSTR *)a1);
    v19 = 5;
    if ( FileAttributesW != -1 )
      v19 = 183;
    SetLastError(v19);
  }
LABEL_31:
  LastError = GetLastError();
  if ( LastError > 0 )
    TokenUser = (unsigned __int16)LastError | 0x80070000;
  else
    TokenUser = LastError;
  if ( LastError == 3 )
  {
    if ( !*((_BYTE *)a1 + 44) )
    {
      v21 = wcsrchr(*(const wchar_t **)a1, 0x5Cu);
      v22 = v21;
      if ( v21 )
      {
        *v21 = 0;
        v23 = *((_DWORD *)a1 + 2);
        v24 = *((_DWORD *)a1 + 10);
        *((_DWORD *)a1 + 2) = v23 & 8;
        *((_DWORD *)a1 + 10) = -1;
        TargetFolder = kfapi::CFolderCreator::CreateTargetFolder(a1);
        *((_DWORD *)a1 + 10) = v24;
        TokenUser = TargetFolder;
        *((_DWORD *)a1 + 2) = v23;
        *v22 = 92;
        if ( TargetFolder >= 0 )
        {
          v26 = *((_BYTE *)a1 + 44);
          *((_BYTE *)a1 + 44) = 1;
          TokenUser = kfapi::CFolderCreator::CreateTargetFolder(a1);
          *((_BYTE *)a1 + 44) = v26;
        }
      }
    }
    return TokenUser;
  }
  if ( LastError != 183 )
    return TokenUser;
  v27 = GetFileAttributesW(*(LPCWSTR *)a1);
  if ( v27 == -1 )
    return ResultFromLastError();
  if ( (v27 & 0x10) == 0 )
    return -2147024816;
  v5 = (char *)a1 + 8;
  v28 = *((_DWORD *)a1 + 2);
  if ( (v28 & 5) != 0 )
  {
    pSid1 = 0;
    v29 = v28 & 4;
    v49 = 0;
    pSecurityDescriptor = 0;
    v30 = v28 & 1;
    v31 = (v29 != 0) | 4;
    if ( !v30 )
      v31 = v29 != 0;
    v32 = GetNamedSecurityInfoW(
            *(LPCWSTR *)a1,
            SE_FILE_OBJECT,
            v31,
            (PSID *)((unsigned __int64)&pSid1 & -(__int64)(v29 != 0)),
            0,
            (PACL *)((unsigned __int64)&v49 & -(__int64)(v30 != 0)),
            0,
            &pSecurityDescriptor);
    TokenUser = v32;
    if ( v32 )
    {
      if ( v32 > 0 )
        TokenUser = (unsigned __int16)v32 | 0x80070000;
      goto LABEL_50;
    }
    ppsidOwner = 0;
    TokenUser = kfapi::CFolderCreationInfo::GetTokenUser(a1, (struct _TOKEN_USER **)&ppsidOwner);
    if ( TokenUser < 0 )
    {
LABEL_50:
      v33 = pSecurityDescriptor;
      pSecurityDescriptor = 0;
      CTContainer_PolicyLocalMem::DestroyMem(v33);
      return TokenUser;
    }
    v34 = (PSID *)ppsidOwner;
    if ( (*v5 & 4) != 0 && (!pSid1 || !EqualSid(pSid1, *(PSID *)ppsidOwner)) )
    {
      v35 = pSecurityDescriptor;
      pSecurityDescriptor = 0;
      CTContainer_PolicyLocalMem::DestroyMem(v35);
      return -2147023589;
    }
    if ( (*v5 & 1) != 0 )
    {
      pControl = 0;
      dwRevision[0] = 0;
      if ( !GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, dwRevision) )
      {
        Error = ResultFromLastError();
        v37 = pSecurityDescriptor;
        v38 = Error;
        pSecurityDescriptor = 0;
        CTContainer_PolicyLocalMem::DestroyMem(v37);
        return v38;
      }
      if ( (pControl & 0x1004) != 0x1004 )
      {
        v39 = kfapi::CFolderCreator::SetDirectoryUserExclusive(*(LPWSTR *)a1, *v34);
        TokenUser = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1A9,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\foldercreator.cpp",
            (const char *)(unsigned int)v39,
            dwCreationDispositiona);
          goto LABEL_50;
        }
      }
    }
    v40 = pSecurityDescriptor;
    pSecurityDescriptor = 0;
    CTContainer_PolicyLocalMem::DestroyMem(v40);
  }
  v41 = *((_DWORD *)a1 + 10);
  if ( v41 != -1 )
    kfapi::CFolderCreator::CopyFolderAttributes(*(LPCWSTR *)a1, v41, *((_BYTE *)a1 + 46));
LABEL_65:
  if ( (*v5 & 2) == 0 )
    return 0;
  result = SetNamedSecurityInfoW(*(LPWSTR *)a1, SE_FILE_OBJECT, 0x80000004, 0, 0, *((PACL *)a1 + 2), 0);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1803869a4  push    rbp
0x1803869a6  push    rbx
0x1803869a7  push    rsi
0x1803869a8  push    rdi
0x1803869a9  push    r12
0x1803869ab  push    r13
0x1803869ad  push    r14
0x1803869af  push    r15
0x1803869b1  mov     rbp, rsp
0x1803869b4  sub     rsp, 78h
0x1803869b8  mov     rsi, rcx
0x1803869bb  mov     rcx, [rcx]; pszPath
0x1803869be  call    cs:__imp_PathIsRootW
0x1803869c5  nop     dword ptr [rax+rax+00h]
0x1803869ca  mov     rcx, [rsi]; lpPathName
0x1803869cd  or      r13d, 0FFFFFFFFh
0x1803869d1  xor     r12d, r12d
0x1803869d4  mov     r15d, 80070000h
0x1803869da  mov     ebx, 0B7h
0x1803869df  test    eax, eax
0x1803869e1  jz      short loc_180386A34
0x1803869e3  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x1803869e8  lea     r8d, [r12+7]; dwShareMode
0x1803869ed  mov     [rsp+78h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1803869f5  xor     r9d, r9d; lpSecurityAttributes
0x1803869f8  xor     edx, edx; dwDesiredAccess
0x1803869fa  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180386a02  call    cs:__imp_CreateFileW
0x180386a09  nop     dword ptr [rax+rax+00h]
0x180386a0e  mov     [rbp+ppsidOwner], rax
0x180386a12  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180386a16  jz      short loc_180386A26
0x180386a18  mov     ecx, ebx; dwErrCode
0x180386a1a  call    cs:__imp_SetLastError
0x180386a21  nop     dword ptr [rax+rax+00h]
0x180386a26  lea     rcx, [rbp+ppsidOwner]
0x180386a2a  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180386a2f  jmp     loc_180386BFE
0x180386a34  xor     edx, edx; lpSecurityAttributes
0x180386a36  call    cs:__imp_CreateDirectoryW
0x180386a3d  nop     dword ptr [rax+rax+00h]
0x180386a42  test    eax, eax
0x180386a44  jz      loc_180386BC6
0x180386a4a  mov     rax, [rsi]
0x180386a4d  lea     rbx, [rsi+8]
0x180386a51  test    byte ptr [rbx], 8
0x180386a54  mov     edi, 1
0x180386a59  mov     [rsi+2Dh], dil
0x180386a5d  mov     qword ptr [rbp+dwRevision], rax
0x180386a61  jz      loc_180386B36
0x180386a67  lea     rdx, [rbp+pSid1]; struct _TOKEN_USER **
0x180386a6b  mov     [rbp+pSid1], r12
0x180386a6f  mov     rcx, rsi; this
0x180386a72  call    ?GetTokenUser@CFolderCreationInfo@kfapi@@QEAAJPEAPEAU_TOKEN_USER@@@Z; kfapi::CFolderCreationInfo::GetTokenUser(_TOKEN_USER * *)
0x180386a77  mov     r14d, eax
0x180386a7a  test    eax, eax
0x180386a7c  js      loc_180386B82
0x180386a82  mov     rcx, [rsi]; pObjectName
0x180386a85  lea     rax, [rbp+pSecurityDescriptor]
0x180386a89  mov     [rsp+78h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180386a8e  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x180386a92  mov     [rsp+78h+hTemplateFile], r12; ppSacl
0x180386a97  mov     r8d, edi; SecurityInfo
0x180386a9a  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; ppDacl
0x180386a9f  mov     edx, edi; ObjectType
0x180386aa1  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; ppsidGroup
0x180386aa6  mov     [rbp+ppsidOwner], r12
0x180386aaa  mov     [rbp+pSecurityDescriptor], r12
0x180386aae  call    cs:__imp_GetNamedSecurityInfoW
0x180386ab5  nop     dword ptr [rax+rax+00h]
0x180386aba  mov     r14d, eax
0x180386abd  test    eax, eax
0x180386abf  jz      short loc_180386ADC
0x180386ac1  jle     short loc_180386ACA
0x180386ac3  movzx   r14d, ax
0x180386ac7  or      r14d, r15d
0x180386aca  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180386ace  mov     [rbp+pSecurityDescriptor], r12
0x180386ad2  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180386ad7  jmp     loc_180386B82
0x180386adc  mov     rcx, [rbp+ppsidOwner]; pSid1
0x180386ae0  mov     r14, [rbp+pSid1]
0x180386ae4  test    rcx, rcx
0x180386ae7  jz      short loc_180386AFC
0x180386ae9  mov     rdx, [r14]; pSid2
0x180386aec  call    cs:__imp_EqualSid
0x180386af3  nop     dword ptr [rax+rax+00h]
0x180386af8  test    eax, eax
0x180386afa  jnz     short loc_180386B29
0x180386afc  mov     r9, [r14]; psidOwner
0x180386aff  mov     r8d, edi; SecurityInfo
0x180386b02  mov     rcx, [rsi]; pObjectName
0x180386b05  mov     edx, edi; ObjectType
0x180386b07  mov     [rsp+78h+hTemplateFile], r12; pSacl
0x180386b0c  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; pDacl
0x180386b11  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; int
0x180386b16  call    cs:__imp_SetNamedSecurityInfoW
0x180386b1d  nop     dword ptr [rax+rax+00h]
0x180386b22  mov     r14d, eax
0x180386b25  test    eax, eax
0x180386b27  jnz     short loc_180386AC1
0x180386b29  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180386b2d  mov     [rbp+pSecurityDescriptor], r12
0x180386b31  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180386b36  test    [rbx], dil
0x180386b39  jz      short loc_180386BA0
0x180386b3b  lea     rdx, [rbp+pSid1]; struct _TOKEN_USER **
0x180386b3f  mov     [rbp+pSid1], r12
0x180386b43  mov     rcx, rsi; this
0x180386b46  call    ?GetTokenUser@CFolderCreationInfo@kfapi@@QEAAJPEAPEAU_TOKEN_USER@@@Z; kfapi::CFolderCreationInfo::GetTokenUser(_TOKEN_USER * *)
0x180386b4b  test    eax, eax
0x180386b4d  jns     short loc_180386B54
0x180386b4f  mov     r14d, eax
0x180386b52  jmp     short loc_180386B82
0x180386b54  mov     rdx, [rbp+pSid1]
0x180386b58  mov     rcx, [rsi]; pObjectName
0x180386b5b  mov     rdx, [rdx]; pSid
0x180386b5e  call    ?SetDirectoryUserExclusive@CFolderCreator@kfapi@@CAJPEBGPEAX@Z; kfapi::CFolderCreator::SetDirectoryUserExclusive(ushort const *,void *)
0x180386b63  mov     r14d, eax
0x180386b66  test    eax, eax
0x180386b68  jns     short loc_180386BA0
0x180386b6a  mov     rcx, [rbp+40h]; this
0x180386b6e  lea     r8, aOnecoreuapShel_96; "onecoreuap\\shell\\windows.storage\\kfa"...
0x180386b75  mov     r9d, eax; char *
0x180386b78  mov     edx, 121h; void *
0x180386b7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180386b82  lea     rcx, [rbp+dwRevision]; this
0x180386b86  call    ??1CDirectoryRemover@kfapi@@QEAA@XZ; kfapi::CDirectoryRemover::~CDirectoryRemover(void)
0x180386b8b  mov     eax, r14d
0x180386b8e  add     rsp, 78h
0x180386b92  pop     r15
0x180386b94  pop     r14
0x180386b96  pop     r13
0x180386b98  pop     r12
0x180386b9a  pop     rdi
0x180386b9b  pop     rsi
0x180386b9c  pop     rbx
0x180386b9d  pop     rbp
0x180386b9e  retn
0x180386ba0  mov     edx, [rsi+28h]; unsigned int
0x180386ba3  cmp     edx, r13d
0x180386ba6  jz      short loc_180386BB4
0x180386ba8  mov     r8b, [rsi+2Eh]; bool
0x180386bac  mov     rcx, [rsi]; lpFileName
0x180386baf  call    ?CopyFolderAttributes@CFolderCreator@kfapi@@CAJPEBGK_N@Z; kfapi::CFolderCreator::CopyFolderAttributes(ushort const *,ulong,bool)
0x180386bb4  lea     rcx, [rbp+dwRevision]; this
0x180386bb8  mov     qword ptr [rbp+dwRevision], r12
0x180386bbc  call    ??1CDirectoryRemover@kfapi@@QEAA@XZ; kfapi::CDirectoryRemover::~CDirectoryRemover(void)
0x180386bc1  jmp     loc_180386E6D
0x180386bc6  call    cs:__imp_GetLastError
0x180386bcd  nop     dword ptr [rax+rax+00h]
0x180386bd2  cmp     eax, 5
0x180386bd5  jnz     short loc_180386BFE
0x180386bd7  mov     rcx, [rsi]; lpFileName
0x180386bda  call    cs:__imp_GetFileAttributesW
0x180386be1  nop     dword ptr [rax+rax+00h]
0x180386be6  mov     ecx, 5
0x180386beb  cmp     eax, r13d
0x180386bee  jz      short loc_180386BF2
0x180386bf0  mov     ecx, ebx; dwErrCode
0x180386bf2  call    cs:__imp_SetLastError
0x180386bf9  nop     dword ptr [rax+rax+00h]
0x180386bfe  call    cs:__imp_GetLastError
0x180386c05  nop     dword ptr [rax+rax+00h]
0x180386c0a  test    eax, eax
0x180386c0c  jg      short loc_180386C13
0x180386c0e  mov     r14d, eax
0x180386c11  jmp     short loc_180386C1A
0x180386c13  movzx   r14d, ax
0x180386c17  or      r14d, r15d
0x180386c1a  cmp     eax, 3
0x180386c1d  jnz     short loc_180386C96
0x180386c1f  cmp     [rsi+2Ch], r12b
0x180386c23  jnz     loc_180386B8B
0x180386c29  mov     rcx, [rsi]; Str
0x180386c2c  lea     edx, [rax+59h]; Ch
0x180386c2f  call    cs:__imp_wcsrchr
0x180386c36  nop     dword ptr [rax+rax+00h]
0x180386c3b  mov     r15, rax
0x180386c3e  test    rax, rax
0x180386c41  jz      loc_180386B8B
0x180386c47  mov     [rax], r12w
0x180386c4b  mov     edi, [rsi+8]
0x180386c4e  mov     ecx, edi
0x180386c50  mov     ebx, [rsi+28h]
0x180386c53  and     ecx, 8
0x180386c56  mov     [rsi+8], ecx
0x180386c59  mov     rcx, rsi; struct kfapi::CFolderCreationInfo *
0x180386c5c  mov     [rsi+28h], r13d
0x180386c60  call    ?CreateTargetFolder@CFolderCreator@kfapi@@CAJAEAVCFolderCreationInfo@2@@Z; kfapi::CFolderCreator::CreateTargetFolder(kfapi::CFolderCreationInfo &)
0x180386c65  mov     [rsi+28h], ebx
0x180386c68  mov     r14d, eax
0x180386c6b  mov     [rsi+8], edi
0x180386c6e  mov     word ptr [r15], 5Ch ; '\'
0x180386c74  test    eax, eax
0x180386c76  js      loc_180386B8B
0x180386c7c  mov     bl, [rsi+2Ch]
0x180386c7f  mov     rcx, rsi; struct kfapi::CFolderCreationInfo *
0x180386c82  mov     byte ptr [rsi+2Ch], 1
0x180386c86  call    ?CreateTargetFolder@CFolderCreator@kfapi@@CAJAEAVCFolderCreationInfo@2@@Z; kfapi::CFolderCreator::CreateTargetFolder(kfapi::CFolderCreationInfo &)
0x180386c8b  mov     r14d, eax
0x180386c8e  mov     [rsi+2Ch], bl
0x180386c91  jmp     loc_180386B8B
0x180386c96  cmp     eax, ebx
0x180386c98  jnz     loc_180386B8B
0x180386c9e  mov     rcx, [rsi]; lpFileName
0x180386ca1  call    cs:__imp_GetFileAttributesW
0x180386ca8  nop     dword ptr [rax+rax+00h]
0x180386cad  cmp     eax, r13d
0x180386cb0  jnz     short loc_180386CBC
0x180386cb2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180386cb7  jmp     loc_180386B8E
0x180386cbc  test    al, 10h
0x180386cbe  jnz     short loc_180386CCA
0x180386cc0  mov     eax, 80070050h
0x180386cc5  jmp     loc_180386B8E
0x180386cca  lea     rbx, [rsi+8]
0x180386cce  mov     edi, 1
0x180386cd3  mov     r11d, [rbx]
0x180386cd6  test    r11b, 5
0x180386cda  jz      loc_180386E59
0x180386ce0  mov     ecx, r11d
0x180386ce3  mov     [rbp+pSid1], r12
0x180386ce7  and     ecx, 4
0x180386cea  mov     [rbp+var_10], r12
0x180386cee  mov     r10d, r12d
0x180386cf1  mov     [rbp+pSecurityDescriptor], r12
0x180386cf5  setnz   r10b
0x180386cf9  and     r11d, edi
0x180386cfc  mov     eax, r11d
0x180386cff  mov     r8d, r10d
0x180386d02  neg     eax
0x180386d04  lea     rax, [rbp+var_10]
0x180386d08  sbb     rdx, rdx
0x180386d0b  and     rdx, rax
0x180386d0e  lea     rax, [rbp+pSid1]
0x180386d12  neg     ecx
0x180386d14  mov     rcx, [rsi]; pObjectName
0x180386d17  sbb     r9, r9
0x180386d1a  or      r8d, 4
0x180386d1e  and     r9, rax; ppsidOwner
0x180386d21  lea     rax, [rbp+pSecurityDescriptor]
0x180386d25  mov     [rsp+78h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180386d2a  test    r11d, r11d
0x180386d2d  mov     [rsp+78h+hTemplateFile], r12; ppSacl
0x180386d32  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rdx; ppDacl
0x180386d37  cmovz   r8d, r10d; SecurityInfo
0x180386d3b  mov     edx, edi; ObjectType
0x180386d3d  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; int
0x180386d42  call    cs:__imp_GetNamedSecurityInfoW
0x180386d49  nop     dword ptr [rax+rax+00h]
0x180386d4e  mov     r14d, eax
0x180386d51  test    eax, eax
0x180386d53  jz      short loc_180386D70
0x180386d55  jle     short loc_180386D5E
0x180386d57  movzx   r14d, ax
0x180386d5b  or      r14d, r15d
0x180386d5e  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180386d62  mov     [rbp+pSecurityDescriptor], r12
0x180386d66  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180386d6b  jmp     loc_180386B8B
0x180386d70  lea     rdx, [rbp+ppsidOwner]; struct _TOKEN_USER **
0x180386d74  mov     [rbp+ppsidOwner], r12
0x180386d78  mov     rcx, rsi; this
0x180386d7b  call    ?GetTokenUser@CFolderCreationInfo@kfapi@@QEAAJPEAPEAU_TOKEN_USER@@@Z; kfapi::CFolderCreationInfo::GetTokenUser(_TOKEN_USER * *)
0x180386d80  mov     r14d, eax
0x180386d83  test    eax, eax
0x180386d85  js      short loc_180386D5E
0x180386d87  test    byte ptr [rbx], 4
0x180386d8a  mov     r14, [rbp+ppsidOwner]
0x180386d8e  jz      short loc_180386DC3
0x180386d90  mov     rcx, [rbp+pSid1]; pSid1
0x180386d94  test    rcx, rcx
0x180386d97  jz      short loc_180386DAC
0x180386d99  mov     rdx, [r14]; pSid2
0x180386d9c  call    cs:__imp_EqualSid
0x180386da3  nop     dword ptr [rax+rax+00h]
0x180386da8  test    eax, eax
0x180386daa  jnz     short loc_180386DC3
0x180386dac  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180386db0  mov     [rbp+pSecurityDescriptor], r12
0x180386db4  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180386db9  mov     eax, 8007051Bh
0x180386dbe  jmp     loc_180386B8E
0x180386dc3  test    [rbx], dil
0x180386dc6  jz      loc_180386E4C
0x180386dcc  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180386dd0  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180386dd4  lea     rdx, [rbp+pControl]; pControl
0x180386dd8  mov     [rbp+pControl], r12w
0x180386ddd  mov     [rbp+dwRevision], r12d
0x180386de1  call    cs:__imp_GetSecurityDescriptorControl
0x180386de8  nop     dword ptr [rax+rax+00h]
0x180386ded  test    eax, eax
0x180386def  jnz     short loc_180386E0C
0x180386df1  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180386df6  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180386dfa  mov     ebx, eax
0x180386dfc  mov     [rbp+pSecurityDescriptor], r12
0x180386e00  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
  ... truncated ...
```
