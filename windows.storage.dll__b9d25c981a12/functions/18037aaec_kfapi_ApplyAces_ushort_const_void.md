# kfapi::_ApplyAces(ushort const *,void *)

- ea: `0x18037aaec`
- end: `0x18037aeef`
- name: `?_ApplyAces@kfapi@@YAJPEBGPEAX@Z`
- size: `1027`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180147380`

## callees

- `0x180038f50`
- `0x1800783fc`
- `0x180083c94`
- `0x1800ee270`
- `0x180370e34`
- `0x18037aaec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18037ac01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18037ac01`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18037ad33`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18037ad33`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18037ab2c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18037ab2c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18037ac4f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18037ac4f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18037ad65`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18037adee`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18037ad65`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18037adee`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18037ac95`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18037accc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18037adbe`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18037ac95`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18037accc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18037adbe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18037ad14`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18037ad14`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18037abb8`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18037abb8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18037ae3a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18037aeb8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18037ae3a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18037aeb8`

## string_xrefs

- `0x18037ab40`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18037ac1d`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18037ac68`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18037ae4e`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`
- `0x18037aed1`: `onecoreuap\shell\windows.storage\kfapi\folderpathbuilder.cpp`

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
0x18037aaec  mov     [rsp-28h+arg_0], rbx
0x18037aaf1  mov     [rsp-28h+arg_8], rsi
0x18037aaf6  push    rbp
0x18037aaf7  push    rdi
0x18037aaf8  push    r12
0x18037aafa  push    r14
0x18037aafc  push    r15
0x18037aafe  mov     rbp, rsp
0x18037ab01  sub     rsp, 80h
0x18037ab08  mov     rax, rdx
0x18037ab0b  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x18037ab0f  xor     r12d, r12d
0x18037ab12  lea     r8, [rbp+pSacl]; pSacl
0x18037ab16  mov     r15, rcx
0x18037ab19  mov     [rbp+pSacl], r12
0x18037ab1d  mov     rcx, rax; pSecurityDescriptor
0x18037ab20  mov     [rbp+bSaclDefaulted], r12d
0x18037ab24  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x18037ab28  mov     [rbp+bSaclPresent], r12d
0x18037ab2c  call    cs:__imp_GetSecurityDescriptorSacl
0x18037ab33  nop     dword ptr [rax+rax+00h]
0x18037ab38  test    eax, eax
0x18037ab3a  jnz     short loc_18037AB56
0x18037ab3c  mov     rcx, [rbp+28h]; this
0x18037ab40  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18037ab47  mov     edx, 84h; void *
0x18037ab4c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18037ab51  jmp     loc_18037AE7B
0x18037ab56  cmp     [rbp+bSaclPresent], r12d
0x18037ab5a  jz      loc_18037AE79
0x18037ab60  mov     rax, [rbp+pSacl]
0x18037ab64  test    rax, rax
0x18037ab67  jz      loc_18037AE79
0x18037ab6d  cmp     [rax+4], r12w
0x18037ab72  jbe     loc_18037AE79
0x18037ab78  xor     edx, edx
0x18037ab7a  mov     [rbp+pAcl], r12
0x18037ab7e  lea     rcx, [rbp+var_20]
0x18037ab82  mov     [rbp+var_20], r12
0x18037ab86  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18037ab8b  xor     r9d, r9d; ppsidOwner
0x18037ab8e  lea     rax, [rbp+var_20]
0x18037ab92  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18037ab97  mov     rcx, r15; pObjectName
0x18037ab9a  lea     rax, [rbp+pAcl]
0x18037ab9e  mov     [rsp+80h+ppSacl], rax; ppSacl
0x18037aba3  lea     r14d, [r9+30h]
0x18037aba7  mov     [rsp+80h+ppDacl], r12; ppDacl
0x18037abac  mov     r8d, r14d; SecurityInfo
0x18037abaf  mov     [rsp+80h+ppsidGroup], r12; int
0x18037abb4  lea     edx, [r9+1]; ObjectType
0x18037abb8  call    cs:__imp_GetNamedSecurityInfoW
0x18037abbf  nop     dword ptr [rax+rax+00h]
0x18037abc4  test    eax, eax
0x18037abc6  jz      short loc_18037ABD1
0x18037abc8  lea     edx, [r14+5Ch]
0x18037abcc  jmp     loc_18037AECD
0x18037abd1  mov     rax, [rbp+pAcl]
0x18037abd5  test    rax, rax
0x18037abd8  jz      loc_18037AE98
0x18037abde  cmp     [rax+4], r12w
0x18037abe3  jbe     loc_18037AE98
0x18037abe9  movzx   edx, word ptr [rax+2]
0x18037abed  mov     ecx, 40h ; '@'; uFlags
0x18037abf2  mov     rax, [rbp+pSacl]
0x18037abf6  add     edx, 0FFFFFFF8h
0x18037abf9  movzx   edi, word ptr [rax+2]
0x18037abfd  add     edi, edx
0x18037abff  mov     edx, edi; uBytes
0x18037ac01  call    cs:__imp_LocalAlloc
0x18037ac08  nop     dword ptr [rax+rax+00h]
0x18037ac0d  mov     [rbp+var_40], rax
0x18037ac11  mov     rbx, rax
0x18037ac14  test    rax, rax
0x18037ac17  jnz     short loc_18037AC44
0x18037ac19  mov     rcx, [rbp+28h]; this
0x18037ac1d  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18037ac24  mov     ebx, 8007000Eh
0x18037ac29  mov     edx, 95h; void *
0x18037ac2e  mov     r9d, ebx; char *
0x18037ac31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18037ac36  lea     rcx, [rbp+var_40]
0x18037ac3a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18037ac3f  jmp     loc_18037AEE2
0x18037ac44  mov     r8d, 2; dwAclRevision
0x18037ac4a  mov     edx, edi; nAclLength
0x18037ac4c  mov     rcx, rbx; pAcl
0x18037ac4f  call    cs:__imp_InitializeAcl
0x18037ac56  nop     dword ptr [rax+rax+00h]
0x18037ac5b  test    eax, eax
0x18037ac5d  jnz     short loc_18037AC78
0x18037ac5f  mov     edx, 98h; void *
0x18037ac64  mov     rcx, [rbp+28h]; this
0x18037ac68  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18037ac6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18037ac74  mov     ebx, eax
0x18037ac76  jmp     short loc_18037AC36
0x18037ac78  mov     [rbp+pAce], r12
0x18037ac7c  mov     esi, r12d
0x18037ac7f  mov     rcx, [rbp+pSacl]; pAcl
0x18037ac83  movzx   eax, word ptr [rcx+4]
0x18037ac87  cmp     esi, eax
0x18037ac89  jnb     loc_18037AD9A
0x18037ac8f  lea     r8, [rbp+pAce]; pAce
0x18037ac93  mov     edx, esi; dwAceIndex
0x18037ac95  call    cs:__imp_GetAce
0x18037ac9c  nop     dword ptr [rax+rax+00h]
0x18037aca1  test    eax, eax
0x18037aca3  jz      loc_18037AD90
0x18037aca9  mov     r9, [rbp+pAce]; pAceList
0x18037acad  mov     r14d, r12d
0x18037acb0  mov     rcx, [rbp+pAcl]; pAcl
0x18037acb4  movzx   eax, word ptr [rcx+4]
0x18037acb8  cmp     r14d, eax
0x18037acbb  jnb     loc_18037AD50
0x18037acc1  lea     r8, [rbp+Source2]; pAce
0x18037acc5  mov     [rbp+Source2], r12
0x18037acc9  mov     edx, r14d; dwAceIndex
0x18037accc  call    cs:__imp_GetAce
0x18037acd3  nop     dword ptr [rax+rax+00h]
0x18037acd8  test    eax, eax
0x18037acda  jz      loc_18037AD7C
0x18037ace0  mov     rdx, [rbp+Source2]
0x18037ace4  mov     r9, [rbp+pAce]
0x18037ace8  movzx   eax, word ptr [rdx+2]
0x18037acec  cmp     [r9+2], ax
0x18037acf1  jnz     short loc_18037AD48
0x18037acf3  mov     al, [rdx+1]
0x18037acf6  cmp     [r9+1], al
0x18037acfa  jnz     short loc_18037AD48
0x18037acfc  mov     al, [rdx]
0x18037acfe  cmp     [r9], al
0x18037ad01  jnz     short loc_18037AD48
0x18037ad03  mov     eax, [rdx+4]
0x18037ad06  cmp     [r9+4], eax
0x18037ad0a  jnz     short loc_18037AD48
0x18037ad0c  add     rdx, 8; pSid2
0x18037ad10  lea     rcx, [r9+8]; pSid1
0x18037ad14  call    cs:__imp_EqualSid
0x18037ad1b  nop     dword ptr [rax+rax+00h]
0x18037ad20  test    eax, eax
0x18037ad22  jz      short loc_18037AD44
0x18037ad24  mov     rcx, [rbp+pAce]; Source1
0x18037ad28  mov     rdx, [rbp+Source2]; Source2
0x18037ad2c  movzx   edi, word ptr [rcx+2]
0x18037ad30  mov     r8d, edi; Length
0x18037ad33  call    cs:__imp_RtlCompareMemory
0x18037ad3a  nop     dword ptr [rax+rax+00h]
0x18037ad3f  cmp     rax, rdi
0x18037ad42  jz      short loc_18037AD75
0x18037ad44  mov     r9, [rbp+pAce]
0x18037ad48  inc     r14d
0x18037ad4b  jmp     loc_18037ACB0
0x18037ad50  movzx   eax, word ptr [r9+2]
0x18037ad55  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18037ad59  mov     edx, 2; dwAceRevision
0x18037ad5e  mov     dword ptr [rsp+80h+ppsidGroup], eax; nAceListLength
0x18037ad62  mov     rcx, rbx; pAcl
0x18037ad65  call    cs:__imp_AddAce
0x18037ad6c  nop     dword ptr [rax+rax+00h]
0x18037ad71  test    eax, eax
0x18037ad73  jz      short loc_18037AD86
0x18037ad75  inc     esi
0x18037ad77  jmp     loc_18037AC7F
0x18037ad7c  mov     edx, 0A6h
0x18037ad81  jmp     loc_18037AC64
0x18037ad86  mov     edx, 0B4h
0x18037ad8b  jmp     loc_18037AC64
0x18037ad90  mov     edx, 9Fh
0x18037ad95  jmp     loc_18037AC64
0x18037ad9a  cmp     [rbx+4], r12w
0x18037ad9f  jbe     loc_18037AE67
0x18037ada5  mov     edi, r12d
0x18037ada8  mov     rcx, [rbp+pAcl]; pAcl
0x18037adac  movzx   eax, word ptr [rcx+4]
0x18037adb0  cmp     edi, eax
0x18037adb2  jnb     short loc_18037AE16
0x18037adb4  lea     r8, [rbp+pAceList]; pAce
0x18037adb8  mov     [rbp+pAceList], r12
0x18037adbc  mov     edx, edi; dwAceIndex
0x18037adbe  call    cs:__imp_GetAce
0x18037adc5  nop     dword ptr [rax+rax+00h]
0x18037adca  test    eax, eax
0x18037adcc  jz      short loc_18037AE0C
0x18037adce  mov     r9, [rbp+pAceList]; pAceList
0x18037add2  test    byte ptr [r9+1], 10h
0x18037add7  jnz     short loc_18037ADFE
0x18037add9  movzx   eax, word ptr [r9+2]
0x18037adde  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18037ade2  mov     edx, 2; dwAceRevision
0x18037ade7  mov     dword ptr [rsp+80h+ppsidGroup], eax; nAceListLength
0x18037adeb  mov     rcx, rbx; pAcl
0x18037adee  call    cs:__imp_AddAce
0x18037adf5  nop     dword ptr [rax+rax+00h]
0x18037adfa  test    eax, eax
0x18037adfc  jz      short loc_18037AE02
0x18037adfe  inc     edi
0x18037ae00  jmp     short loc_18037ADA8
0x18037ae02  mov     edx, 0C3h
0x18037ae07  jmp     loc_18037AC64
0x18037ae0c  mov     edx, 0BFh
0x18037ae11  jmp     loc_18037AC64
0x18037ae16  cmp     [rbx+4], r12w
0x18037ae1b  jbe     short loc_18037AE67
0x18037ae1d  xor     r9d, r9d; psidOwner
0x18037ae20  mov     [rsp+80h+ppSacl], rbx; pSacl
0x18037ae25  mov     [rsp+80h+ppDacl], r12; pDacl
0x18037ae2a  mov     rcx, r15; pObjectName
0x18037ae2d  mov     [rsp+80h+ppsidGroup], r12; unsigned int
0x18037ae32  lea     edx, [r9+1]; ObjectType
0x18037ae36  lea     r8d, [r9+30h]; SecurityInfo
0x18037ae3a  call    cs:__imp_SetNamedSecurityInfoW
0x18037ae41  nop     dword ptr [rax+rax+00h]
0x18037ae46  test    eax, eax
0x18037ae48  jz      short loc_18037AE67
0x18037ae4a  mov     rcx, [rbp+28h]; this
0x18037ae4e  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18037ae55  mov     r9d, eax; char *
0x18037ae58  mov     edx, 0CBh; void *
0x18037ae5d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18037ae62  jmp     loc_18037AC74
0x18037ae67  lea     rcx, [rbp+var_40]
0x18037ae6b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18037ae70  lea     rcx, [rbp+var_20]
0x18037ae74  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18037ae79  xor     eax, eax
0x18037ae7b  lea     r11, [rsp+80h+var_s0]
0x18037ae83  mov     rbx, [r11+30h]
0x18037ae87  mov     rsi, [r11+38h]
0x18037ae8b  mov     rsp, r11
0x18037ae8e  pop     r15
0x18037ae90  pop     r14
0x18037ae92  pop     r12
0x18037ae94  pop     rdi
0x18037ae95  pop     rbp
0x18037ae96  retn
0x18037ae98  mov     rax, [rbp+pSacl]
0x18037ae9c  xor     r9d, r9d; psidOwner
0x18037ae9f  mov     [rsp+80h+ppSacl], rax; pSacl
0x18037aea4  mov     r8d, r14d; SecurityInfo
0x18037aea7  mov     [rsp+80h+ppDacl], r12; pDacl
0x18037aeac  mov     rcx, r15; pObjectName
0x18037aeaf  mov     [rsp+80h+ppsidGroup], r12; unsigned int
0x18037aeb4  lea     edx, [r9+1]; ObjectType
0x18037aeb8  call    cs:__imp_SetNamedSecurityInfoW
0x18037aebf  nop     dword ptr [rax+rax+00h]
0x18037aec4  test    eax, eax
0x18037aec6  jz      short loc_18037AE70
0x18037aec8  mov     edx, 0D2h; void *
0x18037aecd  mov     rcx, [rbp+28h]; this
0x18037aed1  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\windows.storage\\kfa"...
0x18037aed8  mov     r9d, eax; char *
0x18037aedb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18037aee0  mov     ebx, eax
0x18037aee2  lea     rcx, [rbp+var_20]
0x18037aee6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAEP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<uchar *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>>(void)
0x18037aeeb  mov     eax, ebx
0x18037aeed  jmp     short loc_18037AE7B
```
