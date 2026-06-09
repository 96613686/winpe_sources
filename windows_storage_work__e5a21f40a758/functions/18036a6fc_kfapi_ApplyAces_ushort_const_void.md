# kfapi::_ApplyAces(ushort const *,void *)

- ea: `0x18036a6fc`
- end: `0x18036aaac`
- name: `?_ApplyAces@kfapi@@YAJPEBGPEAX@Z`
- size: `944`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180136360`

## callees

- `0x18001abcc`
- `0x1800432f0`
- `0x180060a10`
- `0x18007e930`
- `0x18033b5a8`
- `0x18036a6fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18036a805`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18036a805`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18036a915`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18036a915`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18036a73c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18036a73c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18036a84d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18036a84d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18036a941`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18036a9be`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18036a941`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18036a9be`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18036a88d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18036a8ba`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18036a994`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18036a88d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18036a8ba`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18036a994`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18036a8fc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18036a8fc`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18036a7c2`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18036a7c2`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18036aa04`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18036aa7b`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18036aa04`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18036aa7b`

## string_xrefs

- `0x18036a74a`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18036a81b`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18036a860`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18036aa12`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18036aa8e`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`

## pseudocode

```c
__int64 __fastcall kfapi::_ApplyAces(LPWSTR pObjectName, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *a3)
{
  const char *v4; // r9
  DWORD NamedSecurityInfoW; // eax
  __int64 v7; // rdx
  DWORD v8; // edi
  struct _ACL *v9; // rax
  struct _ACL *v10; // rbx
  unsigned int v11; // ebx
  const char *v12; // r9
  __int64 v13; // rdx
  int LastError; // eax
  DWORD v15; // esi
  unsigned __int16 *v16; // r9
  DWORD i; // r14d
  SIZE_T v18; // rdi
  DWORD j; // edi
  DWORD v20; // eax
  unsigned int ppsidGroup; // [rsp+20h] [rbp-60h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-60h]
  struct _ACL *v23; // [rsp+40h] [rbp-40h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-38h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-30h] BYREF
  PACL pAcl; // [rsp+58h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+60h] [rbp-20h] BYREF
  LPVOID Source2; // [rsp+68h] [rbp-18h] BYREF
  LPVOID pAceList; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  WINBOOL bSaclPresent; // [rsp+C0h] [rbp+40h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+C8h] [rbp+48h] BYREF

  pSacl = 0;
  bSaclDefaulted = 0;
  bSaclPresent = 0;
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x84,
             (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\folderpathbuilder.cpp",
             v4);
  if ( !bSaclPresent || !pSacl || !pSacl->AceCount )
    return 0;
  pAcl = 0;
  ppSecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppSecurityDescriptor,
    0);
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x30u, 0, 0, 0, &pAcl, &ppSecurityDescriptor);
  if ( NamedSecurityInfoW )
  {
    v7 = 140;
LABEL_53:
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v7,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\folderpathbuilder.cpp",
            (const char *)NamedSecurityInfoW,
            ppsidGroup);
    goto LABEL_54;
  }
  if ( !pAcl || !pAcl->AceCount )
  {
    NamedSecurityInfoW = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x30u, 0, 0, 0, pSacl);
    if ( NamedSecurityInfoW )
    {
      v7 = 210;
      goto LABEL_53;
    }
LABEL_49:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
    return 0;
  }
  v8 = pAcl->AclSize - 8 + pSacl->AclSize;
  v9 = (struct _ACL *)LocalAlloc(0x40u, v8);
  v23 = v9;
  v10 = v9;
  if ( v9 )
  {
    if ( !InitializeAcl(v9, v8, 2u) )
    {
      v13 = 152;
LABEL_15:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v13,
                    (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\folderpathbuilder.cpp",
                    v12);
LABEL_16:
      v11 = LastError;
      goto LABEL_12;
    }
    pAce = 0;
    v15 = 0;
    while ( 2 )
    {
      if ( v15 < pSacl->AceCount )
      {
        if ( GetAce(pSacl, v15, &pAce) )
        {
          v16 = (unsigned __int16 *)pAce;
          for ( i = 0; i < pAcl->AceCount; ++i )
          {
            Source2 = 0;
            if ( !GetAce(pAcl, i, &Source2) )
            {
              v13 = 166;
              goto LABEL_15;
            }
            v16 = (unsigned __int16 *)pAce;
            if ( *((_WORD *)pAce + 1) == *((_WORD *)Source2 + 1)
              && *((_BYTE *)pAce + 1) == *((_BYTE *)Source2 + 1)
              && *(_BYTE *)pAce == *(_BYTE *)Source2
              && *((_DWORD *)pAce + 1) == *((_DWORD *)Source2 + 1) )
            {
              if ( EqualSid((char *)pAce + 8, (char *)Source2 + 8) )
              {
                v18 = *((unsigned __int16 *)pAce + 1);
                if ( RtlCompareMemory(pAce, Source2, v18) == v18 )
                  goto LABEL_32;
              }
              v16 = (unsigned __int16 *)pAce;
            }
          }
          if ( AddAce(v10, 2u, 0xFFFFFFFF, v16, v16[1]) )
          {
LABEL_32:
            ++v15;
            continue;
          }
          v13 = 180;
        }
        else
        {
          v13 = 159;
        }
        goto LABEL_15;
      }
      break;
    }
    if ( v10->AceCount )
    {
      for ( j = 0; j < pAcl->AceCount; ++j )
      {
        pAceList = 0;
        if ( !GetAce(pAcl, j, &pAceList) )
        {
          v13 = 191;
          goto LABEL_15;
        }
        if ( (*((_BYTE *)pAceList + 1) & 0x10) == 0
          && !AddAce(v10, 2u, 0xFFFFFFFF, pAceList, *((unsigned __int16 *)pAceList + 1)) )
        {
          v13 = 195;
          goto LABEL_15;
        }
      }
      if ( v10->AceCount )
      {
        v20 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x30u, 0, 0, 0, v10);
        if ( v20 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xCB,
                        (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\folderpathbuilder.cpp",
                        (const char *)v20,
                        ppsidGroupa);
          goto LABEL_16;
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&v23);
    goto LABEL_49;
  }
  v11 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x95,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\folderpathbuilder.cpp",
    (const char *)0x8007000ELL,
    ppsidGroup);
LABEL_12:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&v23);
LABEL_54:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
  return v11;
}

```

## disassembly

```asm
0x18036a6fc  mov     [rsp-28h+arg_0], rbx
0x18036a701  mov     [rsp-28h+arg_8], rsi
0x18036a706  push    rbp
0x18036a707  push    rdi
0x18036a708  push    r12
0x18036a70a  push    r14
0x18036a70c  push    r15
0x18036a70e  mov     rbp, rsp
0x18036a711  sub     rsp, 80h
0x18036a718  mov     rax, rdx
0x18036a71b  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x18036a71f  xor     r12d, r12d
0x18036a722  lea     r8, [rbp+pSacl]; pSacl
0x18036a726  mov     r15, rcx
0x18036a729  mov     [rbp+pSacl], r12
0x18036a72d  mov     rcx, rax; pSecurityDescriptor
0x18036a730  mov     [rbp+bSaclDefaulted], r12d
0x18036a734  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x18036a738  mov     [rbp+bSaclPresent], r12d
0x18036a73c  call    cs:__imp_GetSecurityDescriptorSacl
0x18036a742  test    eax, eax
0x18036a744  jnz     short loc_18036A760
0x18036a746  mov     rcx, [rbp+28h]; this
0x18036a74a  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18036a751  mov     edx, 84h; void *
0x18036a756  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18036a75b  jmp     loc_18036AA3F
0x18036a760  cmp     [rbp+bSaclPresent], r12d
0x18036a764  jz      loc_18036AA3D
0x18036a76a  mov     rax, [rbp+pSacl]
0x18036a76e  test    rax, rax
0x18036a771  jz      loc_18036AA3D
0x18036a777  cmp     [rax+4], r12w
0x18036a77c  jbe     loc_18036AA3D
0x18036a782  xor     edx, edx
0x18036a784  mov     [rbp+pAcl], r12
0x18036a788  lea     rcx, [rbp+var_20]
0x18036a78c  mov     [rbp+var_20], r12
0x18036a790  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18036a795  xor     r9d, r9d; ppsidOwner
0x18036a798  lea     rax, [rbp+var_20]
0x18036a79c  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18036a7a1  mov     rcx, r15; pObjectName
0x18036a7a4  lea     rax, [rbp+pAcl]
0x18036a7a8  mov     [rsp+80h+ppSacl], rax; ppSacl
0x18036a7ad  lea     r14d, [r9+30h]
0x18036a7b1  mov     [rsp+80h+ppDacl], r12; ppDacl
0x18036a7b6  mov     r8d, r14d; SecurityInfo
0x18036a7b9  mov     [rsp+80h+ppsidGroup], r12; int
0x18036a7be  lea     edx, [r9+1]; ObjectType
0x18036a7c2  call    cs:__imp_GetNamedSecurityInfoW
0x18036a7c8  test    eax, eax
0x18036a7ca  jz      short loc_18036A7D5
0x18036a7cc  lea     edx, [r14+5Ch]
0x18036a7d0  jmp     loc_18036AA8A
0x18036a7d5  mov     rax, [rbp+pAcl]
0x18036a7d9  test    rax, rax
0x18036a7dc  jz      loc_18036AA5B
0x18036a7e2  cmp     [rax+4], r12w
0x18036a7e7  jbe     loc_18036AA5B
0x18036a7ed  movzx   edx, word ptr [rax+2]
0x18036a7f1  mov     ecx, 40h ; '@'; uFlags
0x18036a7f6  mov     rax, [rbp+pSacl]
0x18036a7fa  add     edx, 0FFFFFFF8h
0x18036a7fd  movzx   edi, word ptr [rax+2]
0x18036a801  add     edi, edx
0x18036a803  mov     edx, edi; uBytes
0x18036a805  call    cs:__imp_LocalAlloc
0x18036a80b  mov     [rbp+var_40], rax
0x18036a80f  mov     rbx, rax
0x18036a812  test    rax, rax
0x18036a815  jnz     short loc_18036A842
0x18036a817  mov     rcx, [rbp+28h]; this
0x18036a81b  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18036a822  mov     ebx, 8007000Eh
0x18036a827  mov     edx, 95h; void *
0x18036a82c  mov     r9d, ebx; char *
0x18036a82f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18036a834  lea     rcx, [rbp+var_40]
0x18036a838  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18036a83d  jmp     loc_18036AA9F
0x18036a842  mov     r8d, 2; dwAclRevision
0x18036a848  mov     edx, edi; nAclLength
0x18036a84a  mov     rcx, rbx; pAcl
0x18036a84d  call    cs:__imp_InitializeAcl
0x18036a853  test    eax, eax
0x18036a855  jnz     short loc_18036A870
0x18036a857  mov     edx, 98h; void *
0x18036a85c  mov     rcx, [rbp+28h]; this
0x18036a860  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18036a867  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18036a86c  mov     ebx, eax
0x18036a86e  jmp     short loc_18036A834
0x18036a870  mov     [rbp+pAce], r12
0x18036a874  mov     esi, r12d
0x18036a877  mov     rcx, [rbp+pSacl]; pAcl
0x18036a87b  movzx   eax, word ptr [rcx+4]
0x18036a87f  cmp     esi, eax
0x18036a881  jnb     loc_18036A970
0x18036a887  lea     r8, [rbp+pAce]; pAce
0x18036a88b  mov     edx, esi; dwAceIndex
0x18036a88d  call    cs:__imp_GetAce
0x18036a893  test    eax, eax
0x18036a895  jz      loc_18036A966
0x18036a89b  mov     r9, [rbp+pAce]; pAceList
0x18036a89f  mov     r14d, r12d
0x18036a8a2  mov     rcx, [rbp+pAcl]; pAcl
0x18036a8a6  movzx   eax, word ptr [rcx+4]
0x18036a8aa  cmp     r14d, eax
0x18036a8ad  jnb     short loc_18036A92C
0x18036a8af  lea     r8, [rbp+Source2]; pAce
0x18036a8b3  mov     [rbp+Source2], r12
0x18036a8b7  mov     edx, r14d; dwAceIndex
0x18036a8ba  call    cs:__imp_GetAce
0x18036a8c0  test    eax, eax
0x18036a8c2  jz      loc_18036A952
0x18036a8c8  mov     rdx, [rbp+Source2]
0x18036a8cc  mov     r9, [rbp+pAce]
0x18036a8d0  movzx   eax, word ptr [rdx+2]
0x18036a8d4  cmp     [r9+2], ax
0x18036a8d9  jnz     short loc_18036A924
0x18036a8db  mov     al, [rdx+1]
0x18036a8de  cmp     [r9+1], al
0x18036a8e2  jnz     short loc_18036A924
0x18036a8e4  mov     al, [rdx]
0x18036a8e6  cmp     [r9], al
0x18036a8e9  jnz     short loc_18036A924
0x18036a8eb  mov     eax, [rdx+4]
0x18036a8ee  cmp     [r9+4], eax
0x18036a8f2  jnz     short loc_18036A924
0x18036a8f4  add     rdx, 8; pSid2
0x18036a8f8  lea     rcx, [r9+8]; pSid1
0x18036a8fc  call    cs:__imp_EqualSid
0x18036a902  test    eax, eax
0x18036a904  jz      short loc_18036A920
0x18036a906  mov     rcx, [rbp+pAce]; Source1
0x18036a90a  mov     rdx, [rbp+Source2]; Source2
0x18036a90e  movzx   edi, word ptr [rcx+2]
0x18036a912  mov     r8d, edi; Length
0x18036a915  call    cs:__imp_RtlCompareMemory
0x18036a91b  cmp     rax, rdi
0x18036a91e  jz      short loc_18036A94B
0x18036a920  mov     r9, [rbp+pAce]
0x18036a924  inc     r14d
0x18036a927  jmp     loc_18036A8A2
0x18036a92c  movzx   eax, word ptr [r9+2]
0x18036a931  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18036a935  mov     edx, 2; dwAceRevision
0x18036a93a  mov     dword ptr [rsp+80h+ppsidGroup], eax; nAceListLength
0x18036a93e  mov     rcx, rbx; pAcl
0x18036a941  call    cs:__imp_AddAce
0x18036a947  test    eax, eax
0x18036a949  jz      short loc_18036A95C
0x18036a94b  inc     esi
0x18036a94d  jmp     loc_18036A877
0x18036a952  mov     edx, 0A6h
0x18036a957  jmp     loc_18036A85C
0x18036a95c  mov     edx, 0B4h
0x18036a961  jmp     loc_18036A85C
0x18036a966  mov     edx, 9Fh
0x18036a96b  jmp     loc_18036A85C
0x18036a970  cmp     [rbx+4], r12w
0x18036a975  jbe     loc_18036AA2B
0x18036a97b  mov     edi, r12d
0x18036a97e  mov     rcx, [rbp+pAcl]; pAcl
0x18036a982  movzx   eax, word ptr [rcx+4]
0x18036a986  cmp     edi, eax
0x18036a988  jnb     short loc_18036A9E0
0x18036a98a  lea     r8, [rbp+pAceList]; pAce
0x18036a98e  mov     [rbp+pAceList], r12
0x18036a992  mov     edx, edi; dwAceIndex
0x18036a994  call    cs:__imp_GetAce
0x18036a99a  test    eax, eax
0x18036a99c  jz      short loc_18036A9D6
0x18036a99e  mov     r9, [rbp+pAceList]; pAceList
0x18036a9a2  test    byte ptr [r9+1], 10h
0x18036a9a7  jnz     short loc_18036A9C8
0x18036a9a9  movzx   eax, word ptr [r9+2]
0x18036a9ae  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18036a9b2  mov     edx, 2; dwAceRevision
0x18036a9b7  mov     dword ptr [rsp+80h+ppsidGroup], eax; nAceListLength
0x18036a9bb  mov     rcx, rbx; pAcl
0x18036a9be  call    cs:__imp_AddAce
0x18036a9c4  test    eax, eax
0x18036a9c6  jz      short loc_18036A9CC
0x18036a9c8  inc     edi
0x18036a9ca  jmp     short loc_18036A97E
0x18036a9cc  mov     edx, 0C3h
0x18036a9d1  jmp     loc_18036A85C
0x18036a9d6  mov     edx, 0BFh
0x18036a9db  jmp     loc_18036A85C
0x18036a9e0  cmp     [rbx+4], r12w
0x18036a9e5  jbe     short loc_18036AA2B
0x18036a9e7  xor     r9d, r9d; psidOwner
0x18036a9ea  mov     [rsp+80h+ppSacl], rbx; pSacl
0x18036a9ef  mov     [rsp+80h+ppDacl], r12; pDacl
0x18036a9f4  mov     rcx, r15; pObjectName
0x18036a9f7  mov     [rsp+80h+ppsidGroup], r12; unsigned int
0x18036a9fc  lea     edx, [r9+1]; ObjectType
0x18036aa00  lea     r8d, [r9+30h]; SecurityInfo
0x18036aa04  call    cs:__imp_SetNamedSecurityInfoW
0x18036aa0a  test    eax, eax
0x18036aa0c  jz      short loc_18036AA2B
0x18036aa0e  mov     rcx, [rbp+28h]; this
0x18036aa12  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18036aa19  mov     r9d, eax; char *
0x18036aa1c  mov     edx, 0CBh; void *
0x18036aa21  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18036aa26  jmp     loc_18036A86C
0x18036aa2b  lea     rcx, [rbp+var_40]
0x18036aa2f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18036aa34  lea     rcx, [rbp+var_20]
0x18036aa38  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18036aa3d  xor     eax, eax
0x18036aa3f  lea     r11, [rsp+80h+var_s0]
0x18036aa47  mov     rbx, [r11+30h]
0x18036aa4b  mov     rsi, [r11+38h]
0x18036aa4f  mov     rsp, r11
0x18036aa52  pop     r15
0x18036aa54  pop     r14
0x18036aa56  pop     r12
0x18036aa58  pop     rdi
0x18036aa59  pop     rbp
0x18036aa5a  retn
0x18036aa5b  mov     rax, [rbp+pSacl]
0x18036aa5f  xor     r9d, r9d; psidOwner
0x18036aa62  mov     [rsp+80h+ppSacl], rax; pSacl
0x18036aa67  mov     r8d, r14d; SecurityInfo
0x18036aa6a  mov     [rsp+80h+ppDacl], r12; pDacl
0x18036aa6f  mov     rcx, r15; pObjectName
0x18036aa72  mov     [rsp+80h+ppsidGroup], r12; unsigned int
0x18036aa77  lea     edx, [r9+1]; ObjectType
0x18036aa7b  call    cs:__imp_SetNamedSecurityInfoW
0x18036aa81  test    eax, eax
0x18036aa83  jz      short loc_18036AA34
0x18036aa85  mov     edx, 0D2h; void *
0x18036aa8a  mov     rcx, [rbp+28h]; this
0x18036aa8e  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18036aa95  mov     r9d, eax; char *
0x18036aa98  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18036aa9d  mov     ebx, eax
0x18036aa9f  lea     rcx, [rbp+var_20]
0x18036aaa3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18036aaa8  mov     eax, ebx
0x18036aaaa  jmp     short loc_18036AA3F
```
