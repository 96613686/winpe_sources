# FileStream::OpenFile(ushort const *,IStream * *)

- ea: `0x180010f3c`
- end: `0x1800113d6`
- name: `?OpenFile@FileStream@@SAJPEBGPEAPEAUIStream@@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct IStream **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f974`
- `0x180010e30`

## callees

- `0x180007c80`
- `0x18000827c`
- `0x180008360`
- `0x180008700`
- `0x180008850`
- `0x180010f3c`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180011398`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001118f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001118f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001133d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001133d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800112db`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800112db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001138a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001138a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180011267`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180011267`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010ffb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800110fd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011185`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010ffb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800110fd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180011185`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011357`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011367`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011377`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011357`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011367`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011377`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180011226`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180011226`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800111ec`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800111ec`

## string_xrefs

- `0x18001101e`: `CreateSecurityDescriptor: AllocateAndInitializeSid function failed with error %d`
- `0x180011205`: `CreateSecurityDescriptor: SetEntriesInAcl function failed with error %d`
- `0x180011249`: `CreateSecurityDescriptor: InitializeSecurityDescriptor function failed with error %d`
- `0x18001128a`: `CreateSecurityDescriptor: SetSecurityDescriptorDacl function failed with error %d`
- `0x1800112ff`: `FileStream::OpenFile: CreateFileW failed to open xml file with error %d`

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
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_31;
      v7 = L"CreateSecurityDescriptor: AllocateAndInitializeSid function failed with error %d";
LABEL_5:
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, v7, LastError);
      if ( (byte_18002D803 & 8) != 0 )
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
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_31;
    v7 = L"CreateSecurityDescriptor: SetEntriesInAcl function failed with error %d";
    goto LABEL_5;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v4 = operator new[](0x28u);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v31) )
    {
      v6 = 8;
      v4 = 0;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180011345);
      goto LABEL_31;
    }
  }
  if ( !InitializeSecurityDescriptor(v4, 1u) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( (byte_18002D803 & 8) == 0 )
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
      if ( (byte_18002D803 & 8) == 0 )
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
      if ( (byte_18002D803 & 8) == 0 )
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
0x180010f3c  mov     r11, rsp
0x180010f3f  mov     [r11+18h], rbx
0x180010f43  mov     [r11+20h], rsi
0x180010f47  push    rdi
0x180010f48  push    r14
0x180010f4a  push    r15
0x180010f4c  sub     rsp, 950h
0x180010f53  mov     rax, cs:__security_cookie
0x180010f5a  xor     rax, rsp
0x180010f5d  mov     [rsp+968h+var_20], rax
0x180010f65  mov     r15, rdx
0x180010f68  mov     r14, rcx
0x180010f6b  xorps   xmm0, xmm0
0x180010f6e  xor     eax, eax
0x180010f70  movups  xmmword ptr [rsp+968h+SecurityAttributes.nLength], xmm0
0x180010f78  mov     [r11-8C8h], rax
0x180010f7f  xor     ebx, ebx
0x180010f81  mov     [rsp+968h+var_900], rbx
0x180010f86  mov     [rsp+968h+var_8F8], rbx
0x180010f8b  mov     [rsp+968h+var_8F0], rbx
0x180010f90  mov     [r11-8E8h], rbx
0x180010f97  mov     dword ptr [rsp+968h+pIdentifierAuthority.Value], ebx
0x180010f9e  mov     word ptr [rsp+968h+pIdentifierAuthority.Value+4], 500h
0x180010fa8  mov     esi, ebx
0x180010faa  mov     [rsp+968h+var_828], ebx
0x180010fb1  xor     edx, edx; Val
0x180010fb3  mov     r8d, 7FCh; Size
0x180010fb9  lea     rcx, [r11-824h]; void *
0x180010fc0  call    memset_0
0x180010fc5  mov     [r15], rbx
0x180010fc8  lea     rax, [rsp+968h+var_900]
0x180010fcd  mov     [rsp+968h+pSid], rax; pSid
0x180010fd2  mov     [rsp+968h+nSubAuthority7], ebx; nSubAuthority7
0x180010fd6  mov     [rsp+968h+nSubAuthority6], ebx; nSubAuthority6
0x180010fda  mov     [rsp+968h+nSubAuthority5], ebx; nSubAuthority5
0x180010fde  mov     [rsp+968h+nSubAuthority4], ebx; nSubAuthority4
0x180010fe2  mov     [rsp+968h+nSubAuthority3], ebx; nSubAuthority3
0x180010fe6  mov     [rsp+968h+nSubAuthority2], ebx; nSubAuthority2
0x180010fea  xor     r9d, r9d; nSubAuthority1
0x180010fed  lea     r8d, [rbx+0Bh]; nSubAuthority0
0x180010ff1  mov     dl, 1; nSubAuthorityCount
0x180010ff3  lea     rcx, [rsp+968h+pIdentifierAuthority]; pIdentifierAuthority
0x180010ffb  call    cs:__imp_AllocateAndInitializeSid
0x180011001  test    eax, eax
0x180011003  jnz     short loc_18001106A
0x180011005  call    cs:__imp_GetLastError
0x18001100b  mov     edi, eax
0x18001100d  test    eax, eax
0x18001100f  jz      short loc_18001106A
0x180011011  test    cs:byte_18002D803, 8
0x180011018  jz      loc_18001134D
0x18001101e  lea     rdx, aCreatesecurity_2; "CreateSecurityDescriptor: AllocateAndIn"...
0x180011025  mov     word ptr [rsp+968h+var_828], bx
0x18001102d  mov     r8d, eax
0x180011030  lea     rcx, [rsp+968h+var_828]
0x180011038  call    FormatRRASErrorString
0x18001103d  test    cs:byte_18002D803, 8
0x180011044  jz      loc_18001134D
0x18001104a  lea     r8, [rsp+968h+var_828]
0x180011052  lea     rdx, RasSSTPSvcTraceError
0x180011059  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011060  call    McTemplateU0z_EventWriteTransfer
0x180011065  jmp     loc_18001134D
0x18001106a  xor     edx, edx; Val
0x18001106c  mov     r8d, 90h; Size
0x180011072  lea     rcx, [rsp+968h+pListOfExplicitEntries]; void *
0x18001107a  call    memset_0
0x18001107f  mov     [rsp+968h+pListOfExplicitEntries.grfAccessPermissions], 120089h
0x18001108a  mov     qword ptr [rsp+968h+pListOfExplicitEntries.grfAccessMode], 2
0x180011096  mov     [rsp+968h+pListOfExplicitEntries.Trustee.TrusteeForm], ebx
0x18001109d  mov     [rsp+968h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800110a8  mov     rax, [rsp+968h+var_900]
0x1800110ad  mov     [rsp+968h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800110b5  lea     rax, [rsp+968h+var_8F8]
0x1800110ba  mov     [rsp+968h+pSid], rax; pSid
0x1800110bf  mov     [rsp+968h+nSubAuthority7], ebx; nSubAuthority7
0x1800110c3  mov     [rsp+968h+nSubAuthority6], ebx; nSubAuthority6
0x1800110c7  mov     [rsp+968h+nSubAuthority5], 0AF2BD0DAh; nSubAuthority5
0x1800110cf  mov     [rsp+968h+nSubAuthority4], 0C06BE3BAh; nSubAuthority4
0x1800110d7  mov     [rsp+968h+nSubAuthority3], 0E1FBEBC1h; nSubAuthority3
0x1800110df  mov     [rsp+968h+nSubAuthority2], 2FA7AE2Ah; nSubAuthority2
0x1800110e7  mov     r9d, 0CCC8A67Eh; nSubAuthority1
0x1800110ed  mov     r8d, 50h ; 'P'; nSubAuthority0
0x1800110f3  mov     dl, 6; nSubAuthorityCount
0x1800110f5  lea     rcx, [rsp+968h+pIdentifierAuthority]; pIdentifierAuthority
0x1800110fd  call    cs:__imp_AllocateAndInitializeSid
0x180011103  test    eax, eax
0x180011105  jnz     short loc_180011117
0x180011107  call    cs:__imp_GetLastError
0x18001110d  mov     edi, eax
0x18001110f  test    eax, eax
0x180011111  jnz     loc_180011011
0x180011117  mov     [rsp+968h+var_888], 1F01FFh
0x180011122  mov     [rsp+968h+var_884], 2
0x18001112e  mov     [rsp+968h+var_86C], ebx
0x180011135  mov     [rsp+968h+var_868], 1
0x180011140  mov     rax, [rsp+968h+var_8F8]
0x180011145  mov     [rsp+968h+var_860], rax
0x18001114d  lea     rax, [rsp+968h+var_8F0]
0x180011152  mov     [rsp+968h+pSid], rax; pSid
0x180011157  mov     [rsp+968h+nSubAuthority7], ebx; nSubAuthority7
0x18001115b  mov     [rsp+968h+nSubAuthority6], ebx; nSubAuthority6
0x18001115f  mov     [rsp+968h+nSubAuthority5], ebx; nSubAuthority5
0x180011163  mov     [rsp+968h+nSubAuthority4], ebx; nSubAuthority4
0x180011167  mov     [rsp+968h+nSubAuthority3], ebx; nSubAuthority3
0x18001116b  mov     [rsp+968h+nSubAuthority2], ebx; nSubAuthority2
0x18001116f  mov     r9d, 220h; nSubAuthority1
0x180011175  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001117b  mov     dl, 2; nSubAuthorityCount
0x18001117d  lea     rcx, [rsp+968h+pIdentifierAuthority]; pIdentifierAuthority
0x180011185  call    cs:__imp_AllocateAndInitializeSid
0x18001118b  test    eax, eax
0x18001118d  jnz     short loc_18001119F
0x18001118f  call    cs:__imp_GetLastError
0x180011195  mov     edi, eax
0x180011197  test    eax, eax
0x180011199  jnz     loc_180011011
0x18001119f  mov     [rsp+968h+var_858], 120116h
0x1800111aa  mov     [rsp+968h+var_854], 2
0x1800111b6  mov     [rsp+968h+var_83C], ebx
0x1800111bd  mov     [rsp+968h+var_838], 2
0x1800111c8  mov     rax, [rsp+968h+var_8F0]
0x1800111cd  mov     [rsp+968h+var_830], rax
0x1800111d5  lea     r9, [rsp+968h+NewAcl]; NewAcl
0x1800111dd  xor     r8d, r8d; OldAcl
0x1800111e0  lea     rdx, [rsp+968h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800111e8  lea     ecx, [r8+3]; cCountOfExplicitEntries
0x1800111ec  call    cs:__imp_SetEntriesInAclW
0x1800111f2  mov     edi, eax
0x1800111f4  test    eax, eax
0x1800111f6  jz      short loc_180011211
0x1800111f8  test    cs:byte_18002D803, 8
0x1800111ff  jz      loc_18001134D
0x180011205  lea     rdx, aCreatesecurity_1; "CreateSecurityDescriptor: SetEntriesInA"...
0x18001120c  jmp     loc_180011025
0x180011211  mov     ecx, 28h ; '('; unsigned __int64
0x180011216  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001121b  mov     rsi, rax
0x18001121e  mov     edx, 1; dwRevision
0x180011223  mov     rcx, rsi; pSecurityDescriptor
0x180011226  call    cs:__imp_InitializeSecurityDescriptor
0x18001122c  test    eax, eax
0x18001122e  jnz     short loc_180011255
0x180011230  call    cs:__imp_GetLastError
0x180011236  mov     edi, eax
0x180011238  test    eax, eax
0x18001123a  jz      short loc_180011255
0x18001123c  test    cs:byte_18002D803, 8
0x180011243  jz      loc_18001134D
0x180011249  lea     rdx, aCreatesecurity_0; "CreateSecurityDescriptor: InitializeSec"...
0x180011250  jmp     loc_180011025
0x180011255  xor     r9d, r9d; bDaclDefaulted
0x180011258  mov     r8, [rsp+968h+NewAcl]; pDacl
0x180011260  lea     edx, [r9+1]; bDaclPresent
0x180011264  mov     rcx, rsi; pSecurityDescriptor
0x180011267  call    cs:__imp_SetSecurityDescriptorDacl
0x18001126d  test    eax, eax
0x18001126f  jnz     short loc_180011296
0x180011271  call    cs:__imp_GetLastError
0x180011277  mov     edi, eax
0x180011279  test    eax, eax
0x18001127b  jz      short loc_180011296
0x18001127d  test    cs:byte_18002D803, 8
0x180011284  jz      loc_18001134D
0x18001128a  lea     rdx, aCreatesecurity; "CreateSecurityDescriptor: SetSecurityDe"...
0x180011291  jmp     loc_180011025
0x180011296  mov     [rsp+968h+SecurityAttributes.nLength], 18h
0x1800112a1  mov     [rsp+968h+SecurityAttributes.lpSecurityDescriptor], rsi
0x1800112a9  mov     [rsp+968h+SecurityAttributes.bInheritHandle], ebx
0x1800112b0  mov     qword ptr [rsp+968h+nSubAuthority4], rbx; hTemplateFile
0x1800112b5  mov     [rsp+968h+nSubAuthority3], 80h; dwFlagsAndAttributes
0x1800112bd  mov     [rsp+968h+nSubAuthority2], 4; dwCreationDisposition
0x1800112c5  lea     r9, [rsp+968h+SecurityAttributes]; lpSecurityAttributes
0x1800112cd  mov     edx, 0C0000000h; dwDesiredAccess
0x1800112d2  mov     r8d, 1; dwShareMode
0x1800112d8  mov     rcx, r14; lpFileName
0x1800112db  call    cs:__imp_CreateFileW
0x1800112e1  mov     r14, rax
0x1800112e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800112e8  jnz     short loc_18001130B
0x1800112ea  call    cs:__imp_GetLastError
0x1800112f0  mov     edi, eax
0x1800112f2  test    eax, eax
0x1800112f4  jz      short loc_18001130B
0x1800112f6  test    cs:byte_18002D803, 8
0x1800112fd  jz      short loc_18001134D
0x1800112ff  lea     rdx, aFilestreamOpen; "FileStream::OpenFile: CreateFileW faile"...
0x180011306  jmp     loc_180011025
0x18001130b  mov     ecx, 18h; Size
0x180011310  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011315  mov     [rsp+968h+var_8E0], rax
0x18001131d  test    rax, rax
0x180011320  jz      short loc_180011337
0x180011322  mov     rdx, r14; void *
0x180011325  mov     rcx, rax; this
0x180011328  call    ??0FileStream@@AEAA@PEAX@Z; FileStream::FileStream(void *)
0x18001132d  mov     [r15], rax
0x180011330  test    rax, rax
0x180011333  jnz     short loc_18001134D
0x180011335  jmp     short loc_18001133A
0x180011337  mov     [r15], rbx
0x18001133a  mov     rcx, r14; hObject
0x18001133d  call    cs:__imp_CloseHandle
0x180011343  jmp     short loc_18001134D
0x180011345  xor     ebx, ebx
0x180011347  mov     edi, [rsp+968h+var_908]
0x18001134b  mov     esi, ebx
0x18001134d  mov     rcx, [rsp+968h+var_900]; pSid
0x180011352  test    rcx, rcx
0x180011355  jz      short loc_18001135D
0x180011357  call    cs:__imp_FreeSid
0x18001135d  mov     rcx, [rsp+968h+var_8F8]; pSid
0x180011362  test    rcx, rcx
0x180011365  jz      short loc_18001136D
0x180011367  call    cs:__imp_FreeSid
0x18001136d  mov     rcx, [rsp+968h+var_8F0]; pSid
0x180011372  test    rcx, rcx
0x180011375  jz      short loc_18001137D
0x180011377  call    cs:__imp_FreeSid
0x18001137d  mov     rcx, [rsp+968h+NewAcl]; hMem
0x180011385  test    rcx, rcx
0x180011388  jz      short loc_180011390
0x18001138a  call    cs:__imp_LocalFree
0x180011390  test    rsi, rsi
0x180011393  jz      short loc_18001139E
0x180011395  mov     rcx, rsi
0x180011398  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001139e  test    edi, edi
0x1800113a0  jle     short loc_1800113AB
0x1800113a2  movzx   edi, di
0x1800113a5  or      edi, 80070000h
0x1800113ab  mov     eax, edi
0x1800113ad  mov     rcx, [rsp+968h+var_20]
0x1800113b5  xor     rcx, rsp; StackCookie
0x1800113b8  call    __security_check_cookie
0x1800113bd  lea     r11, [rsp+968h+var_18]
0x1800113c5  mov     rbx, [r11+30h]
0x1800113c9  mov     rsi, [r11+38h]
0x1800113cd  mov     rsp, r11
0x1800113d0  pop     r15
0x1800113d2  pop     r14
0x1800113d4  pop     rdi
0x1800113d5  retn
```
