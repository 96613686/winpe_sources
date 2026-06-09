# FileStream::OpenFile(ushort const *,IStream * *)

- ea: `0x180011de8`
- end: `0x1800122f5`
- name: `?OpenFile@FileStream@@SAJPEBGPEAPEAUIStream@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct IStream **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001072c`
- `0x180011cd4`

## callees

- `0x180008454`
- `0x1800089dc`
- `0x180008b90`
- `0x180008f6c`
- `0x1800090c0`
- `0x180011de8`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800122b0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800122b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001210c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001210c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012237`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800121c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800121c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001229c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001229c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180012149`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180012149`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011ea7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011fb5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012049`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011ea7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011fb5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180012049`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012257`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001226d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012283`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012257`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001226d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180012283`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800120fc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800120fc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800120bc`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800120bc`

## string_xrefs

- `0x180011ed6`: `CreateSecurityDescriptor: AllocateAndInitializeSid function failed with error %d`
- `0x1800120db`: `CreateSecurityDescriptor: SetEntriesInAcl function failed with error %d`
- `0x18001212b`: `CreateSecurityDescriptor: InitializeSecurityDescriptor function failed with error %d`
- `0x180012178`: `CreateSecurityDescriptor: SetSecurityDescriptorDacl function failed with error %d`
- `0x1800121f9`: `FileStream::OpenFile: CreateFileW failed to open xml file with error %d`

## pseudocode

```c
__int64 __fastcall FileStream::OpenFile(LPCWSTR lpFileName, struct IStream **a2)
{
  void *v4; // rsi
  DWORD LastError; // eax
  int v6; // edi
  const wchar_t *v7; // rdx
  HANDLE v8; // r14
  ACL *v9; // rax
  struct IStream *v10; // rax
  PSID pSid; // [rsp+68h] [rbp-900h] BYREF
  PSID v13; // [rsp+70h] [rbp-8F8h] BYREF
  PSID v14; // [rsp+78h] [rbp-8F0h] BYREF
  PACL NewAcl[2]; // [rsp+80h] [rbp-8E8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+90h] [rbp-8D8h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp-8C0h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+B0h] [rbp-8B8h] BYREF
  int v19; // [rsp+E0h] [rbp-888h]
  __int64 v20; // [rsp+E4h] [rbp-884h]
  int v21; // [rsp+FCh] [rbp-86Ch]
  int v22; // [rsp+100h] [rbp-868h]
  PSID v23; // [rsp+108h] [rbp-860h]
  int v24; // [rsp+110h] [rbp-858h]
  __int64 v25; // [rsp+114h] [rbp-854h]
  int v26; // [rsp+12Ch] [rbp-83Ch]
  int v27; // [rsp+130h] [rbp-838h]
  PSID v28; // [rsp+138h] [rbp-830h]
  int v29; // [rsp+140h] [rbp-828h] BYREF
  int v30; // [rsp+144h] [rbp-824h] BYREF
  std::bad_alloc *v31; // [rsp+940h] [rbp-28h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  pSid = 0;
  v13 = 0;
  v14 = 0;
  NewAcl[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v4 = 0;
  v29 = 0;
  memset_0(&v30, 0, 0x7FCu);
  *a2 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
      goto LABEL_3;
  }
  memset_0(&pListOfExplicitEntries, 0, 0x90u);
  pListOfExplicitEntries.grfAccessPermissions = 1179785;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0xCCC8A67E,
          0x2FA7AE2Au,
          0xE1FBEBC1,
          0xC06BE3BA,
          0xAF2BD0DA,
          0,
          0,
          &v13) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
      goto LABEL_3;
  }
  v19 = 2032127;
  v20 = 2;
  v21 = 0;
  v22 = 1;
  v23 = v13;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v14) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
LABEL_3:
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_31;
      v7 = L"CreateSecurityDescriptor: AllocateAndInitializeSid function failed with error %d";
LABEL_5:
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, v7, LastError);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v29);
      goto LABEL_31;
    }
  }
  v24 = 1179926;
  v25 = 2;
  v26 = 0;
  v27 = 2;
  v28 = v14;
  LastError = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, NewAcl);
  v6 = LastError;
  if ( LastError )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_31;
    v7 = L"CreateSecurityDescriptor: SetEntriesInAcl function failed with error %d";
    goto LABEL_5;
  }
  try
  {
    v4 = operator new[](0x28u);
  }
  catch ( std::bad_alloc *v31 )
  {
    v6 = 8;
    v4 = 0;
    goto LABEL_31;
  }
  if ( !InitializeSecurityDescriptor(v4, 1u) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_31;
      v7 = L"CreateSecurityDescriptor: InitializeSecurityDescriptor function failed with error %d";
      goto LABEL_5;
    }
  }
  if ( !SetSecurityDescriptorDacl(v4, 1, NewAcl[0], 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_31;
      v7 = L"CreateSecurityDescriptor: SetSecurityDescriptorDacl function failed with error %d";
      goto LABEL_5;
    }
  }
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = v4;
  SecurityAttributes.bInheritHandle = 0;
  v8 = CreateFileW(lpFileName, 0xC0000000, 1u, &SecurityAttributes, 4u, 0x80u, 0);
  if ( v8 == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_31;
      v7 = L"FileStream::OpenFile: CreateFileW failed to open xml file with error %d";
      goto LABEL_5;
    }
  }
  v9 = (ACL *)operator new(0x18u);
  NewAcl[1] = v9;
  if ( v9 )
  {
    v10 = (struct IStream *)FileStream::FileStream((FileStream *)v9, v8);
    *a2 = v10;
    if ( v10 )
      goto LABEL_31;
  }
  else
  {
    *a2 = 0;
  }
  CloseHandle(v8);
LABEL_31:
  if ( pSid )
    FreeSid(pSid);
  if ( v13 )
    FreeSid(v13);
  if ( v14 )
    FreeSid(v14);
  if ( NewAcl[0] )
    LocalFree(NewAcl[0]);
  if ( v4 )
    operator delete[](v4);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180011de8  mov     r11, rsp
0x180011deb  mov     [r11+18h], rbx
0x180011def  mov     [r11+20h], rsi
0x180011df3  push    rdi
0x180011df4  push    r14
0x180011df6  push    r15
0x180011df8  sub     rsp, 950h
0x180011dff  mov     rax, cs:__security_cookie
0x180011e06  xor     rax, rsp
0x180011e09  mov     [rsp+968h+var_20], rax
0x180011e11  mov     r15, rdx
0x180011e14  mov     r14, rcx
0x180011e17  xorps   xmm0, xmm0
0x180011e1a  xor     eax, eax
0x180011e1c  movups  xmmword ptr [rsp+968h+SecurityAttributes.nLength], xmm0
0x180011e24  mov     [r11-8C8h], rax
0x180011e2b  xor     ebx, ebx
0x180011e2d  mov     [rsp+968h+var_900], rbx
0x180011e32  mov     [rsp+968h+var_8F8], rbx
0x180011e37  mov     [rsp+968h+var_8F0], rbx
0x180011e3c  mov     [r11-8E8h], rbx
0x180011e43  mov     dword ptr [rsp+968h+pIdentifierAuthority.Value], ebx
0x180011e4a  mov     word ptr [rsp+968h+pIdentifierAuthority.Value+4], 500h
0x180011e54  mov     esi, ebx
0x180011e56  mov     [rsp+968h+var_828], ebx
0x180011e5d  xor     edx, edx; Val
0x180011e5f  mov     r8d, 7FCh; Size
0x180011e65  lea     rcx, [r11-824h]; void *
0x180011e6c  call    memset_0
0x180011e71  mov     [r15], rbx
0x180011e74  lea     rax, [rsp+968h+var_900]
0x180011e79  mov     [rsp+968h+pSid], rax; pSid
0x180011e7e  mov     [rsp+968h+nSubAuthority7], ebx; nSubAuthority7
0x180011e82  mov     [rsp+968h+nSubAuthority6], ebx; nSubAuthority6
0x180011e86  mov     [rsp+968h+nSubAuthority5], ebx; nSubAuthority5
0x180011e8a  mov     [rsp+968h+nSubAuthority4], ebx; nSubAuthority4
0x180011e8e  mov     [rsp+968h+nSubAuthority3], ebx; nSubAuthority3
0x180011e92  mov     [rsp+968h+nSubAuthority2], ebx; nSubAuthority2
0x180011e96  xor     r9d, r9d; nSubAuthority1
0x180011e99  lea     r8d, [rbx+0Bh]; nSubAuthority0
0x180011e9d  mov     dl, 1; nSubAuthorityCount
0x180011e9f  lea     rcx, [rsp+968h+pIdentifierAuthority]; pIdentifierAuthority
0x180011ea7  call    cs:__imp_AllocateAndInitializeSid
0x180011eae  nop     dword ptr [rax+rax+00h]
0x180011eb3  test    eax, eax
0x180011eb5  jnz     short loc_180011F22
0x180011eb7  call    cs:__imp_GetLastError
0x180011ebe  nop     dword ptr [rax+rax+00h]
0x180011ec3  mov     edi, eax
0x180011ec5  test    eax, eax
0x180011ec7  jz      short loc_180011F22
0x180011ec9  test    cs:byte_18002E903, 8
0x180011ed0  jz      loc_18001224D
0x180011ed6  lea     rdx, aCreatesecurity_2; "CreateSecurityDescriptor: AllocateAndIn"...
0x180011edd  mov     word ptr [rsp+968h+var_828], bx
0x180011ee5  mov     r8d, eax
0x180011ee8  lea     rcx, [rsp+968h+var_828]
0x180011ef0  call    FormatRRASErrorString
0x180011ef5  test    cs:byte_18002E903, 8
0x180011efc  jz      loc_18001224D
0x180011f02  lea     r8, [rsp+968h+var_828]
0x180011f0a  lea     rdx, RasSSTPSvcTraceError
0x180011f11  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011f18  call    McTemplateU0z_EventWriteTransfer
0x180011f1d  jmp     loc_18001224D
0x180011f22  xor     edx, edx; Val
0x180011f24  mov     r8d, 90h; Size
0x180011f2a  lea     rcx, [rsp+968h+pListOfExplicitEntries]; void *
0x180011f32  call    memset_0
0x180011f37  mov     [rsp+968h+pListOfExplicitEntries.grfAccessPermissions], 120089h
0x180011f42  mov     qword ptr [rsp+968h+pListOfExplicitEntries.grfAccessMode], 2
0x180011f4e  mov     [rsp+968h+pListOfExplicitEntries.Trustee.TrusteeForm], ebx
0x180011f55  mov     [rsp+968h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180011f60  mov     rax, [rsp+968h+var_900]
0x180011f65  mov     [rsp+968h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180011f6d  lea     rax, [rsp+968h+var_8F8]
0x180011f72  mov     [rsp+968h+pSid], rax; pSid
0x180011f77  mov     [rsp+968h+nSubAuthority7], ebx; nSubAuthority7
0x180011f7b  mov     [rsp+968h+nSubAuthority6], ebx; nSubAuthority6
0x180011f7f  mov     [rsp+968h+nSubAuthority5], 0AF2BD0DAh; nSubAuthority5
0x180011f87  mov     [rsp+968h+nSubAuthority4], 0C06BE3BAh; nSubAuthority4
0x180011f8f  mov     [rsp+968h+nSubAuthority3], 0E1FBEBC1h; nSubAuthority3
0x180011f97  mov     [rsp+968h+nSubAuthority2], 2FA7AE2Ah; nSubAuthority2
0x180011f9f  mov     r9d, 0CCC8A67Eh; nSubAuthority1
0x180011fa5  mov     r8d, 50h ; 'P'; nSubAuthority0
0x180011fab  mov     dl, 6; nSubAuthorityCount
0x180011fad  lea     rcx, [rsp+968h+pIdentifierAuthority]; pIdentifierAuthority
0x180011fb5  call    cs:__imp_AllocateAndInitializeSid
0x180011fbc  nop     dword ptr [rax+rax+00h]
0x180011fc1  test    eax, eax
0x180011fc3  jnz     short loc_180011FDB
0x180011fc5  call    cs:__imp_GetLastError
0x180011fcc  nop     dword ptr [rax+rax+00h]
0x180011fd1  mov     edi, eax
0x180011fd3  test    eax, eax
0x180011fd5  jnz     loc_180011EC9
0x180011fdb  mov     [rsp+968h+var_888], 1F01FFh
0x180011fe6  mov     [rsp+968h+var_884], 2
0x180011ff2  mov     [rsp+968h+var_86C], ebx
0x180011ff9  mov     [rsp+968h+var_868], 1
0x180012004  mov     rax, [rsp+968h+var_8F8]
0x180012009  mov     [rsp+968h+var_860], rax
0x180012011  lea     rax, [rsp+968h+var_8F0]
0x180012016  mov     [rsp+968h+pSid], rax; pSid
0x18001201b  mov     [rsp+968h+nSubAuthority7], ebx; nSubAuthority7
0x18001201f  mov     [rsp+968h+nSubAuthority6], ebx; nSubAuthority6
0x180012023  mov     [rsp+968h+nSubAuthority5], ebx; nSubAuthority5
0x180012027  mov     [rsp+968h+nSubAuthority4], ebx; nSubAuthority4
0x18001202b  mov     [rsp+968h+nSubAuthority3], ebx; nSubAuthority3
0x18001202f  mov     [rsp+968h+nSubAuthority2], ebx; nSubAuthority2
0x180012033  mov     r9d, 220h; nSubAuthority1
0x180012039  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001203f  mov     dl, 2; nSubAuthorityCount
0x180012041  lea     rcx, [rsp+968h+pIdentifierAuthority]; pIdentifierAuthority
0x180012049  call    cs:__imp_AllocateAndInitializeSid
0x180012050  nop     dword ptr [rax+rax+00h]
0x180012055  test    eax, eax
0x180012057  jnz     short loc_18001206F
0x180012059  call    cs:__imp_GetLastError
0x180012060  nop     dword ptr [rax+rax+00h]
0x180012065  mov     edi, eax
0x180012067  test    eax, eax
0x180012069  jnz     loc_180011EC9
0x18001206f  mov     [rsp+968h+var_858], 120116h
0x18001207a  mov     [rsp+968h+var_854], 2
0x180012086  mov     [rsp+968h+var_83C], ebx
0x18001208d  mov     [rsp+968h+var_838], 2
0x180012098  mov     rax, [rsp+968h+var_8F0]
0x18001209d  mov     [rsp+968h+var_830], rax
0x1800120a5  lea     r9, [rsp+968h+NewAcl]; NewAcl
0x1800120ad  xor     r8d, r8d; OldAcl
0x1800120b0  lea     rdx, [rsp+968h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800120b8  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x1800120bc  call    cs:__imp_SetEntriesInAclW
0x1800120c3  nop     dword ptr [rax+rax+00h]
0x1800120c8  mov     edi, eax
0x1800120ca  test    eax, eax
0x1800120cc  jz      short loc_1800120E7
0x1800120ce  test    cs:byte_18002E903, 8
0x1800120d5  jz      loc_18001224D
0x1800120db  lea     rdx, aCreatesecurity_1; "CreateSecurityDescriptor: SetEntriesInA"...
0x1800120e2  jmp     loc_180011EDD
0x1800120e7  mov     ecx, 28h ; '('; unsigned __int64
0x1800120ec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800120f1  mov     rsi, rax
0x1800120f4  mov     edx, 1; dwRevision
0x1800120f9  mov     rcx, rsi; pSecurityDescriptor
0x1800120fc  call    cs:__imp_InitializeSecurityDescriptor
0x180012103  nop     dword ptr [rax+rax+00h]
0x180012108  test    eax, eax
0x18001210a  jnz     short loc_180012137
0x18001210c  call    cs:__imp_GetLastError
0x180012113  nop     dword ptr [rax+rax+00h]
0x180012118  mov     edi, eax
0x18001211a  test    eax, eax
0x18001211c  jz      short loc_180012137
0x18001211e  test    cs:byte_18002E903, 8
0x180012125  jz      loc_18001224D
0x18001212b  lea     rdx, aCreatesecurity_0; "CreateSecurityDescriptor: InitializeSec"...
0x180012132  jmp     loc_180011EDD
0x180012137  xor     r9d, r9d; bDaclDefaulted
0x18001213a  mov     r8, [rsp+968h+NewAcl]; pDacl
0x180012142  lea     edx, [r9+1]; bDaclPresent
0x180012146  mov     rcx, rsi; pSecurityDescriptor
0x180012149  call    cs:__imp_SetSecurityDescriptorDacl
0x180012150  nop     dword ptr [rax+rax+00h]
0x180012155  test    eax, eax
0x180012157  jnz     short loc_180012184
0x180012159  call    cs:__imp_GetLastError
0x180012160  nop     dword ptr [rax+rax+00h]
0x180012165  mov     edi, eax
0x180012167  test    eax, eax
0x180012169  jz      short loc_180012184
0x18001216b  test    cs:byte_18002E903, 8
0x180012172  jz      loc_18001224D
0x180012178  lea     rdx, aCreatesecurity; "CreateSecurityDescriptor: SetSecurityDe"...
0x18001217f  jmp     loc_180011EDD
0x180012184  mov     [rsp+968h+SecurityAttributes.nLength], 18h
0x18001218f  mov     [rsp+968h+SecurityAttributes.lpSecurityDescriptor], rsi
0x180012197  mov     [rsp+968h+SecurityAttributes.bInheritHandle], ebx
0x18001219e  mov     qword ptr [rsp+968h+nSubAuthority4], rbx; hTemplateFile
0x1800121a3  mov     [rsp+968h+nSubAuthority3], 80h; dwFlagsAndAttributes
0x1800121ab  mov     [rsp+968h+nSubAuthority2], 4; dwCreationDisposition
0x1800121b3  lea     r9, [rsp+968h+SecurityAttributes]; lpSecurityAttributes
0x1800121bb  mov     edx, 0C0000000h; dwDesiredAccess
0x1800121c0  mov     r8d, 1; dwShareMode
0x1800121c6  mov     rcx, r14; lpFileName
0x1800121c9  call    cs:__imp_CreateFileW
0x1800121d0  nop     dword ptr [rax+rax+00h]
0x1800121d5  mov     r14, rax
0x1800121d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800121dc  jnz     short loc_180012205
0x1800121de  call    cs:__imp_GetLastError
0x1800121e5  nop     dword ptr [rax+rax+00h]
0x1800121ea  mov     edi, eax
0x1800121ec  test    eax, eax
0x1800121ee  jz      short loc_180012205
0x1800121f0  test    cs:byte_18002E903, 8
0x1800121f7  jz      short loc_18001224D
0x1800121f9  lea     rdx, aFilestreamOpen; "FileStream::OpenFile: CreateFileW faile"...
0x180012200  jmp     loc_180011EDD
0x180012205  mov     ecx, 18h; Size
0x18001220a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001220f  mov     [rsp+968h+var_8E0], rax
0x180012217  test    rax, rax
0x18001221a  jz      short loc_180012231
0x18001221c  mov     rdx, r14; void *
0x18001221f  mov     rcx, rax; this
0x180012222  call    ??0FileStream@@AEAA@PEAX@Z; FileStream::FileStream(void *)
0x180012227  mov     [r15], rax
0x18001222a  test    rax, rax
0x18001222d  jnz     short loc_18001224D
0x18001222f  jmp     short loc_180012234
0x180012231  mov     [r15], rbx
0x180012234  mov     rcx, r14; hObject
0x180012237  call    cs:__imp_CloseHandle
0x18001223e  nop     dword ptr [rax+rax+00h]
0x180012243  jmp     short loc_18001224D
0x180012245  xor     ebx, ebx
0x180012247  mov     edi, [rsp+968h+var_908]
0x18001224b  mov     esi, ebx
0x18001224d  mov     rcx, [rsp+968h+var_900]; pSid
0x180012252  test    rcx, rcx
0x180012255  jz      short loc_180012263
0x180012257  call    cs:__imp_FreeSid
0x18001225e  nop     dword ptr [rax+rax+00h]
0x180012263  mov     rcx, [rsp+968h+var_8F8]; pSid
0x180012268  test    rcx, rcx
0x18001226b  jz      short loc_180012279
0x18001226d  call    cs:__imp_FreeSid
0x180012274  nop     dword ptr [rax+rax+00h]
0x180012279  mov     rcx, [rsp+968h+var_8F0]; pSid
0x18001227e  test    rcx, rcx
0x180012281  jz      short loc_18001228F
0x180012283  call    cs:__imp_FreeSid
0x18001228a  nop     dword ptr [rax+rax+00h]
0x18001228f  mov     rcx, [rsp+968h+NewAcl]; hMem
0x180012297  test    rcx, rcx
0x18001229a  jz      short loc_1800122A8
0x18001229c  call    cs:__imp_LocalFree
0x1800122a3  nop     dword ptr [rax+rax+00h]
0x1800122a8  test    rsi, rsi
0x1800122ab  jz      short loc_1800122BC
0x1800122ad  mov     rcx, rsi
0x1800122b0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800122b7  nop     dword ptr [rax+rax+00h]
0x1800122bc  test    edi, edi
0x1800122be  jle     short loc_1800122C9
0x1800122c0  movzx   edi, di
0x1800122c3  or      edi, 80070000h
0x1800122c9  mov     eax, edi
0x1800122cb  mov     rcx, [rsp+968h+var_20]
0x1800122d3  xor     rcx, rsp; StackCookie
0x1800122d6  call    __security_check_cookie
0x1800122db  lea     r11, [rsp+968h+var_18]
0x1800122e3  mov     rbx, [r11+30h]
0x1800122e7  mov     rsi, [r11+38h]
0x1800122eb  mov     rsp, r11
0x1800122ee  pop     r15
0x1800122f0  pop     r14
0x1800122f2  pop     rdi
0x1800122f3  retn
```
