# kfapi::CFolderCreator::CreateTargetFolder(kfapi::CFolderCreationInfo &)

- ea: `0x1803772d4`
- end: `0x180377780`
- name: `?CreateTargetFolder@CFolderCreator@kfapi@@CAJAEAVCFolderCreationInfo@2@@Z`
- size: `1196`
- prototype: `__int64 __fastcall(struct kfapi::CFolderCreationInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1803772d4`
- `0x1805fe0f8`

## callees

- `0x18003e390`
- `0x1800dd190`
- `0x1800ef3d0`
- `0x180136974`
- `0x1803772d4`
- `0x180377788`
- `0x18037794c`
- `0x1805fe084`
- `0x1805fe230`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18037751c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18037751c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18037733e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1803774eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18037733e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1803774eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803774cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803774f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803774cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803774f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18037732c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18037732c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180377354`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180377354`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1803774d9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180377588`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1803774d9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180377588`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1803772ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1803772ee`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1803776b2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1803776b2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1803773fe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180377677`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1803773fe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180377677`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1803773c6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180377623`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1803773c6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180377623`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180377422`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18037775e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180377422`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18037775e`

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
0x1803772d4  push    rbp
0x1803772d6  push    rbx
0x1803772d7  push    rsi
0x1803772d8  push    rdi
0x1803772d9  push    r12
0x1803772db  push    r13
0x1803772dd  push    r14
0x1803772df  push    r15
0x1803772e1  mov     rbp, rsp
0x1803772e4  sub     rsp, 78h
0x1803772e8  mov     rsi, rcx
0x1803772eb  mov     rcx, [rcx]; pszPath
0x1803772ee  call    cs:__imp_PathIsRootW
0x1803772f4  mov     rcx, [rsi]; lpPathName
0x1803772f7  or      r13d, 0FFFFFFFFh
0x1803772fb  xor     r12d, r12d
0x1803772fe  mov     r15d, 80070000h
0x180377304  mov     ebx, 0B7h
0x180377309  test    eax, eax
0x18037730b  jz      short loc_180377352
0x18037730d  mov     [rsp+78h+hTemplateFile], r12; hTemplateFile
0x180377312  lea     r8d, [r12+7]; dwShareMode
0x180377317  mov     [rsp+78h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18037731f  xor     r9d, r9d; lpSecurityAttributes
0x180377322  xor     edx, edx; dwDesiredAccess
0x180377324  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18037732c  call    cs:__imp_CreateFileW
0x180377332  mov     [rbp+ppsidOwner], rax
0x180377336  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18037733a  jz      short loc_180377344
0x18037733c  mov     ecx, ebx; dwErrCode
0x18037733e  call    cs:__imp_SetLastError
0x180377344  lea     rcx, [rbp+ppsidOwner]
0x180377348  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18037734d  jmp     loc_1803774F1
0x180377352  xor     edx, edx; lpSecurityAttributes
0x180377354  call    cs:__imp_CreateDirectoryW
0x18037735a  test    eax, eax
0x18037735c  jz      loc_1803774CB
0x180377362  mov     rax, [rsi]
0x180377365  lea     rbx, [rsi+8]
0x180377369  test    byte ptr [rbx], 8
0x18037736c  mov     edi, 1
0x180377371  mov     [rsi+2Dh], dil
0x180377375  mov     qword ptr [rbp+dwRevision], rax
0x180377379  jz      loc_18037743C
0x18037737f  lea     rdx, [rbp+pSid1]; struct _TOKEN_USER **
0x180377383  mov     [rbp+pSid1], r12
0x180377387  mov     rcx, rsi; this
0x18037738a  call    ?GetTokenUser@CFolderCreationInfo@kfapi@@QEAAJPEAPEAU_TOKEN_USER@@@Z; kfapi::CFolderCreationInfo::GetTokenUser(_TOKEN_USER * *)
0x18037738f  mov     r14d, eax
0x180377392  test    eax, eax
0x180377394  js      loc_180377488
0x18037739a  mov     rcx, [rsi]; pObjectName
0x18037739d  lea     rax, [rbp+pSecurityDescriptor]
0x1803773a1  mov     [rsp+78h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1803773a6  lea     r9, [rbp+ppsidOwner]; ppsidOwner
0x1803773aa  mov     [rsp+78h+hTemplateFile], r12; ppSacl
0x1803773af  mov     r8d, edi; SecurityInfo
0x1803773b2  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; ppDacl
0x1803773b7  mov     edx, edi; ObjectType
0x1803773b9  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; ppsidGroup
0x1803773be  mov     [rbp+ppsidOwner], r12
0x1803773c2  mov     [rbp+pSecurityDescriptor], r12
0x1803773c6  call    cs:__imp_GetNamedSecurityInfoW
0x1803773cc  mov     r14d, eax
0x1803773cf  test    eax, eax
0x1803773d1  jz      short loc_1803773EE
0x1803773d3  jle     short loc_1803773DC
0x1803773d5  movzx   r14d, ax
0x1803773d9  or      r14d, r15d
0x1803773dc  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x1803773e0  mov     [rbp+pSecurityDescriptor], r12
0x1803773e4  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x1803773e9  jmp     loc_180377488
0x1803773ee  mov     rcx, [rbp+ppsidOwner]; pSid1
0x1803773f2  mov     r14, [rbp+pSid1]
0x1803773f6  test    rcx, rcx
0x1803773f9  jz      short loc_180377408
0x1803773fb  mov     rdx, [r14]; pSid2
0x1803773fe  call    cs:__imp_EqualSid
0x180377404  test    eax, eax
0x180377406  jnz     short loc_18037742F
0x180377408  mov     r9, [r14]; psidOwner
0x18037740b  mov     r8d, edi; SecurityInfo
0x18037740e  mov     rcx, [rsi]; pObjectName
0x180377411  mov     edx, edi; ObjectType
0x180377413  mov     [rsp+78h+hTemplateFile], r12; pSacl
0x180377418  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], r12; pDacl
0x18037741d  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; int
0x180377422  call    cs:__imp_SetNamedSecurityInfoW
0x180377428  mov     r14d, eax
0x18037742b  test    eax, eax
0x18037742d  jnz     short loc_1803773D3
0x18037742f  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180377433  mov     [rbp+pSecurityDescriptor], r12
0x180377437  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x18037743c  test    [rbx], dil
0x18037743f  jz      short loc_1803774A5
0x180377441  lea     rdx, [rbp+pSid1]; struct _TOKEN_USER **
0x180377445  mov     [rbp+pSid1], r12
0x180377449  mov     rcx, rsi; this
0x18037744c  call    ?GetTokenUser@CFolderCreationInfo@kfapi@@QEAAJPEAPEAU_TOKEN_USER@@@Z; kfapi::CFolderCreationInfo::GetTokenUser(_TOKEN_USER * *)
0x180377451  test    eax, eax
0x180377453  jns     short loc_18037745A
0x180377455  mov     r14d, eax
0x180377458  jmp     short loc_180377488
0x18037745a  mov     rdx, [rbp+pSid1]
0x18037745e  mov     rcx, [rsi]; pObjectName
0x180377461  mov     rdx, [rdx]; pSid
0x180377464  call    ?SetDirectoryUserExclusive@CFolderCreator@kfapi@@CAJPEBGPEAX@Z; kfapi::CFolderCreator::SetDirectoryUserExclusive(ushort const *,void *)
0x180377469  mov     r14d, eax
0x18037746c  test    eax, eax
0x18037746e  jns     short loc_1803774A5
0x180377470  mov     rcx, [rbp+40h]; this
0x180377474  lea     r8, aOnecoreuapShel_96; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18037747b  mov     r9d, eax; char *
0x18037747e  mov     edx, 121h; void *
0x180377483  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180377488  lea     rcx, [rbp+dwRevision]; this
0x18037748c  call    ??1CDirectoryRemover@kfapi@@QEAA@XZ; kfapi::CDirectoryRemover::~CDirectoryRemover(void)
0x180377491  mov     eax, r14d
0x180377494  add     rsp, 78h
0x180377498  pop     r15
0x18037749a  pop     r14
0x18037749c  pop     r13
0x18037749e  pop     r12
0x1803774a0  pop     rdi
0x1803774a1  pop     rsi
0x1803774a2  pop     rbx
0x1803774a3  pop     rbp
0x1803774a4  retn
0x1803774a5  mov     edx, [rsi+28h]; unsigned int
0x1803774a8  cmp     edx, r13d
0x1803774ab  jz      short loc_1803774B9
0x1803774ad  mov     r8b, [rsi+2Eh]; bool
0x1803774b1  mov     rcx, [rsi]; lpFileName
0x1803774b4  call    ?CopyFolderAttributes@CFolderCreator@kfapi@@CAJPEBGK_N@Z; kfapi::CFolderCreator::CopyFolderAttributes(ushort const *,ulong,bool)
0x1803774b9  lea     rcx, [rbp+dwRevision]; this
0x1803774bd  mov     qword ptr [rbp+dwRevision], r12
0x1803774c1  call    ??1CDirectoryRemover@kfapi@@QEAA@XZ; kfapi::CDirectoryRemover::~CDirectoryRemover(void)
0x1803774c6  jmp     loc_180377738
0x1803774cb  call    cs:__imp_GetLastError
0x1803774d1  cmp     eax, 5
0x1803774d4  jnz     short loc_1803774F1
0x1803774d6  mov     rcx, [rsi]; lpFileName
0x1803774d9  call    cs:__imp_GetFileAttributesW
0x1803774df  mov     ecx, 5
0x1803774e4  cmp     eax, r13d
0x1803774e7  jz      short loc_1803774EB
0x1803774e9  mov     ecx, ebx; dwErrCode
0x1803774eb  call    cs:__imp_SetLastError
0x1803774f1  call    cs:__imp_GetLastError
0x1803774f7  test    eax, eax
0x1803774f9  jg      short loc_180377500
0x1803774fb  mov     r14d, eax
0x1803774fe  jmp     short loc_180377507
0x180377500  movzx   r14d, ax
0x180377504  or      r14d, r15d
0x180377507  cmp     eax, 3
0x18037750a  jnz     short loc_18037757D
0x18037750c  cmp     [rsi+2Ch], r12b
0x180377510  jnz     loc_180377491
0x180377516  mov     rcx, [rsi]; Str
0x180377519  lea     edx, [rax+59h]; Ch
0x18037751c  call    cs:__imp_wcsrchr
0x180377522  mov     r15, rax
0x180377525  test    rax, rax
0x180377528  jz      loc_180377491
0x18037752e  mov     [rax], r12w
0x180377532  mov     edi, [rsi+8]
0x180377535  mov     ecx, edi
0x180377537  mov     ebx, [rsi+28h]
0x18037753a  and     ecx, 8
0x18037753d  mov     [rsi+8], ecx
0x180377540  mov     rcx, rsi; struct kfapi::CFolderCreationInfo *
0x180377543  mov     [rsi+28h], r13d
0x180377547  call    ?CreateTargetFolder@CFolderCreator@kfapi@@CAJAEAVCFolderCreationInfo@2@@Z; kfapi::CFolderCreator::CreateTargetFolder(kfapi::CFolderCreationInfo &)
0x18037754c  mov     [rsi+28h], ebx
0x18037754f  mov     r14d, eax
0x180377552  mov     [rsi+8], edi
0x180377555  mov     word ptr [r15], 5Ch ; '\'
0x18037755b  test    eax, eax
0x18037755d  js      loc_180377491
0x180377563  mov     bl, [rsi+2Ch]
0x180377566  mov     rcx, rsi; struct kfapi::CFolderCreationInfo *
0x180377569  mov     byte ptr [rsi+2Ch], 1
0x18037756d  call    ?CreateTargetFolder@CFolderCreator@kfapi@@CAJAEAVCFolderCreationInfo@2@@Z; kfapi::CFolderCreator::CreateTargetFolder(kfapi::CFolderCreationInfo &)
0x180377572  mov     r14d, eax
0x180377575  mov     [rsi+2Ch], bl
0x180377578  jmp     loc_180377491
0x18037757d  cmp     eax, ebx
0x18037757f  jnz     loc_180377491
0x180377585  mov     rcx, [rsi]; lpFileName
0x180377588  call    cs:__imp_GetFileAttributesW
0x18037758e  cmp     eax, r13d
0x180377591  jnz     short loc_18037759D
0x180377593  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180377598  jmp     loc_180377494
0x18037759d  test    al, 10h
0x18037759f  jnz     short loc_1803775AB
0x1803775a1  mov     eax, 80070050h
0x1803775a6  jmp     loc_180377494
0x1803775ab  lea     rbx, [rsi+8]
0x1803775af  mov     edi, 1
0x1803775b4  mov     r11d, [rbx]
0x1803775b7  test    r11b, 5
0x1803775bb  jz      loc_180377724
0x1803775c1  mov     ecx, r11d
0x1803775c4  mov     [rbp+pSid1], r12
0x1803775c8  and     ecx, 4
0x1803775cb  mov     [rbp+var_10], r12
0x1803775cf  mov     r10d, r12d
0x1803775d2  mov     [rbp+pSecurityDescriptor], r12
0x1803775d6  setnz   r10b
0x1803775da  and     r11d, edi
0x1803775dd  mov     eax, r11d
0x1803775e0  mov     r8d, r10d
0x1803775e3  neg     eax
0x1803775e5  lea     rax, [rbp+var_10]
0x1803775e9  sbb     rdx, rdx
0x1803775ec  and     rdx, rax
0x1803775ef  lea     rax, [rbp+pSid1]
0x1803775f3  neg     ecx
0x1803775f5  mov     rcx, [rsi]; pObjectName
0x1803775f8  sbb     r9, r9
0x1803775fb  or      r8d, 4
0x1803775ff  and     r9, rax; ppsidOwner
0x180377602  lea     rax, [rbp+pSecurityDescriptor]
0x180377606  mov     [rsp+78h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18037760b  test    r11d, r11d
0x18037760e  mov     [rsp+78h+hTemplateFile], r12; ppSacl
0x180377613  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rdx; ppDacl
0x180377618  cmovz   r8d, r10d; SecurityInfo
0x18037761c  mov     edx, edi; ObjectType
0x18037761e  mov     qword ptr [rsp+78h+dwCreationDisposition], r12; int
0x180377623  call    cs:__imp_GetNamedSecurityInfoW
0x180377629  mov     r14d, eax
0x18037762c  test    eax, eax
0x18037762e  jz      short loc_18037764B
0x180377630  jle     short loc_180377639
0x180377632  movzx   r14d, ax
0x180377636  or      r14d, r15d
0x180377639  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x18037763d  mov     [rbp+pSecurityDescriptor], r12
0x180377641  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180377646  jmp     loc_180377491
0x18037764b  lea     rdx, [rbp+ppsidOwner]; struct _TOKEN_USER **
0x18037764f  mov     [rbp+ppsidOwner], r12
0x180377653  mov     rcx, rsi; this
0x180377656  call    ?GetTokenUser@CFolderCreationInfo@kfapi@@QEAAJPEAPEAU_TOKEN_USER@@@Z; kfapi::CFolderCreationInfo::GetTokenUser(_TOKEN_USER * *)
0x18037765b  mov     r14d, eax
0x18037765e  test    eax, eax
0x180377660  js      short loc_180377639
0x180377662  test    byte ptr [rbx], 4
0x180377665  mov     r14, [rbp+ppsidOwner]
0x180377669  jz      short loc_180377698
0x18037766b  mov     rcx, [rbp+pSid1]; pSid1
0x18037766f  test    rcx, rcx
0x180377672  jz      short loc_180377681
0x180377674  mov     rdx, [r14]; pSid2
0x180377677  call    cs:__imp_EqualSid
0x18037767d  test    eax, eax
0x18037767f  jnz     short loc_180377698
0x180377681  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x180377685  mov     [rbp+pSecurityDescriptor], r12
0x180377689  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x18037768e  mov     eax, 8007051Bh
0x180377693  jmp     loc_180377494
0x180377698  test    [rbx], dil
0x18037769b  jz      short loc_180377717
0x18037769d  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1803776a1  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1803776a5  lea     rdx, [rbp+pControl]; pControl
0x1803776a9  mov     [rbp+pControl], r12w
0x1803776ae  mov     [rbp+dwRevision], r12d
0x1803776b2  call    cs:__imp_GetSecurityDescriptorControl
0x1803776b8  test    eax, eax
0x1803776ba  jnz     short loc_1803776D7
0x1803776bc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1803776c1  mov     rcx, [rbp+pSecurityDescriptor]; void *
0x1803776c5  mov     ebx, eax
0x1803776c7  mov     [rbp+pSecurityDescriptor], r12
0x1803776cb  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x1803776d0  mov     eax, ebx
0x1803776d2  jmp     loc_180377494
0x1803776d7  movzx   eax, [rbp+pControl]
0x1803776db  mov     ecx, 1004h
0x1803776e0  and     ax, cx
0x1803776e3  cmp     ax, cx
0x1803776e6  jz      short loc_180377717
0x1803776e8  mov     rdx, [r14]; pSid
0x1803776eb  mov     rcx, [rsi]; pObjectName
0x1803776ee  call    ?SetDirectoryUserExclusive@CFolderCreator@kfapi@@CAJPEBGPEAX@Z; kfapi::CFolderCreator::SetDirectoryUserExclusive(ushort const *,void *)
0x1803776f3  mov     r14d, eax
0x1803776f6  test    eax, eax
0x1803776f8  jns     short loc_180377717
0x1803776fa  mov     rcx, [rbp+40h]; this
0x1803776fe  lea     r8, aOnecoreuapShel_96; "onecoreuap\\shell\\windows.storage\\kfa"...
0x180377705  mov     r9d, eax; char *
  ... truncated ...
```
