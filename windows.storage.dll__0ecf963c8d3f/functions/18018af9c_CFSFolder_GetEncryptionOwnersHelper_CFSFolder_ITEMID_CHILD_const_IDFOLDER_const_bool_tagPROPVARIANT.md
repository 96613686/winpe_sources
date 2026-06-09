# CFSFolder::GetEncryptionOwnersHelper(CFSFolder *,_ITEMID_CHILD const *,IDFOLDER const *,bool,tagPROPVARIANT *)

- ea: `0x18018af9c`
- end: `0x18018b365`
- name: `?GetEncryptionOwnersHelper@CFSFolder@@KAJPEAV1@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@_NPEAUtagPROPVARIANT@@@Z`
- size: `969`
- prototype: `__int64 __fastcall(struct CFSFolder *, const struct _ITEMID_CHILD *, const struct IDFOLDER *, bool, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18018af60`
- `0x18018af80`

## callees

- `0x1800432f0`
- `0x18005f240`
- `0x18005f280`
- `0x18005f6c0`
- `0x180090a70`
- `0x1800d13a0`
- `0x18018a450`
- `0x18018af9c`
- `0x18018b36c`
- `0x18026e198`
- `0x1803010c8`
- `0x18033b5a8`
- `0x180362694`
- `0x1803a4cb0`
- `0x1803aee20`
- `0x18050dfe8`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b07e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b0bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b16c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b17c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b28f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b07e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b0bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b16c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b17c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018b28f`
- `efswrt!EnterpriseDataGetStatus` at `0x18018b1df`
- `efswrt!EnterpriseDataGetStatus` at `0x18018b1df`
- `efswrt!QueryIdentityProtectors` at `0x18018b0de`
- `efswrt!QueryIdentityProtectors` at `0x18018b0de`
- `efswrt!FreeIdentityProtectorList` at `0x18018b113`
- `efswrt!FreeIdentityProtectorList` at `0x18018b328`
- `efswrt!FreeIdentityProtectorList` at `0x18018b113`
- `efswrt!FreeIdentityProtectorList` at `0x18018b328`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18018b025`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18018b025`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!QueryUsersOnEncryptedFile` at `0x18018b2c2`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!QueryUsersOnEncryptedFile` at `0x18018b2c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::GetEncryptionOwnersHelper(
        struct CFSFolder *a1,
        const struct _ITEMID_CHILD *a2,
        const struct IDFOLDER *a3,
        char a4,
        struct tagPROPVARIANT *a5)
{
  char *v7; // rdi
  __int64 (__fastcall *v8)(char *, const struct _ITEMID_CHILD *, __int64, __int64); // rbx
  __int64 v9; // rax
  int Status; // ebx
  __int64 v11; // rdx
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  int v15; // eax
  struct tagPROPVARIANT *v16; // r8
  void *v17; // rbx
  int EncryptionIdentitiesForNetworkPath; // edi
  unsigned __int16 v19; // r8
  DWORD j; // ebx
  int v21; // eax
  int v22; // esi
  int v23; // eax
  DWORD v24; // eax
  __int64 v25; // rdx
  DWORD i; // ebx
  __int64 v27; // rdx
  int inited; // eax
  unsigned int v29; // [rsp+20h] [rbp-60h]
  unsigned __int16 v30[4]; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h]
  __int64 v33; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v34; // [rsp+50h] [rbp-30h] BYREF
  const struct _ITEMID_CHILD *v35; // [rsp+58h] [rbp-28h] BYREF
  LPCWSTR pszPath; // [rsp+60h] [rbp-20h] BYREF
  PENCRYPTION_CERTIFICATE_HASH_LIST pUsers; // [rsp+68h] [rbp-18h] BYREF
  int v38; // [rsp+70h] [rbp-10h] BYREF
  int v39; // [rsp+74h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v35 = a2;
  *(_OWORD *)&a5->vt = 0;
  a5->bstrblobVal.pData = 0;
  pszPath = 0;
  v7 = (char *)a1 + 312;
  v8 = *(__int64 (__fastcall **)(char *, const struct _ITEMID_CHILD *, __int64, __int64))(*((_QWORD *)a1 + 39) + 112LL);
  v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
  Status = v8(v7, v35, 1, v9);
  if ( Status < 0 )
  {
    v11 = 8963;
    goto LABEL_5;
  }
  if ( !PathIsNetworkPathW(pszPath) )
  {
    v38 = 0x2000;
    Status = (*(__int64 (__fastcall **)(char *, __int64, const struct _ITEMID_CHILD **, int *))(*((_QWORD *)a1 + 6)
                                                                                              + 72LL))(
               (char *)a1 + 48,
               1,
               &v35,
               &v38);
    if ( Status < 0 )
    {
      v11 = 8982;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)Status,
        v29);
LABEL_6:
      if ( pszPath )
        CoTaskMemFree((LPVOID)pszPath);
      return (unsigned int)Status;
    }
    if ( (v38 & 0x2000) == 0 )
      goto LABEL_10;
    if ( (unsigned __int8)IsSHELL32_SHIsVirtualDevicePresent()
      && EdpHelpers::IsLegacyEfsFile((EdpHelpers *)pszPath, v13) )
    {
      pUsers = 0;
      v24 = QueryUsersOnEncryptedFile(pszPath, &pUsers);
      if ( v24 )
      {
        Status = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x2328,
                   (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                   (const char *)v24,
                   v29);
LABEL_52:
        wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(&pUsers);
        goto LABEL_6;
      }
      pv = 0;
      v32 = 0;
      v33 = 0;
      for ( i = 0; i < pUsers->nCert_Hash; ++i )
      {
        v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                &pv,
                pUsers->pUsers[i]->lpDisplayInformation);
        if ( v22 < 0 )
        {
          v27 = 9005;
          goto LABEL_60;
        }
        *(_DWORD *)v30 = 59;
        v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv);
        if ( v22 < 0 )
        {
          v27 = 9006;
LABEL_60:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)(unsigned int)v22,
            v29);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(&pUsers);
          goto LABEL_39;
        }
      }
      inited = InitPropVariantFromStringEx((unsigned __int16 *)pv);
      Status = inited;
      if ( inited < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2330,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)inited,
          v29);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        goto LABEL_52;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(&pUsers);
      goto LABEL_10;
    }
    pUsers = 0;
    v14 = QueryIdentityProtectors(pszPath, &pUsers);
    Status = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2335,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v14,
        v29);
      if ( pUsers )
        FreeIdentityProtectorList();
      goto LABEL_6;
    }
    if ( pUsers->nCert_Hash )
    {
      pv = 0;
      v32 = 0;
      v33 = 0;
      v39 = 0;
      Status = EnterpriseDataGetStatus(pszPath, &v39);
      if ( Status < 0 )
      {
        v25 = 9026;
      }
      else
      {
        if ( !a4 || v39 != 2 )
          goto LABEL_30;
        Status = -2147023728;
        v34 = 0;
        v30[0] = 0;
        if ( !Windows::Internal::ResourceString::FindAndSize(
                g_hinst,
                0xC911u,
                v19,
                (const unsigned __int16 **)&v34,
                v30)
          || (Status = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv),
              Status < 0) )
        {
          v25 = 9030;
          goto LABEL_64;
        }
        *(_DWORD *)v30 = 59;
        Status = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv);
        if ( Status >= 0 )
        {
LABEL_30:
          for ( j = 0; j < pUsers->nCert_Hash; ++j )
          {
            v21 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                    &pv,
                    pUsers->pUsers[j]->pHash);
            v22 = v21;
            if ( v21 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x234C,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v21,
                v29);
              if ( pv )
                CoTaskMemFree(pv);
              if ( pUsers )
                FreeIdentityProtectorList();
              goto LABEL_39;
            }
            *(_DWORD *)v30 = 59;
            v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv);
            v22 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x234D,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)(unsigned int)v23,
                v29);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
              wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(&pUsers);
LABEL_39:
              if ( pszPath )
                CoTaskMemFree((LPVOID)pszPath);
              return (unsigned int)v22;
            }
          }
          Status = InitPropVariantFromStringEx((unsigned __int16 *)pv);
          if ( Status >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
            goto LABEL_50;
          }
          v25 = 9039;
          goto LABEL_64;
        }
        v25 = 9031;
      }
LABEL_64:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)Status,
        v29);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(&pUsers);
      goto LABEL_6;
    }
LABEL_50:
    wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(&pUsers);
LABEL_10:
    if ( pszPath )
      CoTaskMemFree((LPVOID)pszPath);
    return 0;
  }
  pv = 0;
  v32 = -1;
  v33 = -1;
  v15 = PathConvertToUNC(pszPath, (unsigned __int16 **)&pv);
  Status = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v15,
      v29);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_6;
  }
  v17 = pv;
  EncryptionIdentitiesForNetworkPath = EdpHelpers::GetEncryptionIdentitiesForNetworkPath((EdpHelpers *)pv, &a5->vt, v16);
  if ( EncryptionIdentitiesForNetworkPath >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    goto LABEL_10;
  }
  if ( v17 )
    CoTaskMemFree(v17);
  if ( pszPath )
    CoTaskMemFree((LPVOID)pszPath);
  return (unsigned int)EncryptionIdentitiesForNetworkPath;
}

```

## disassembly

```asm
0x18018af9c  mov     [rsp-38h+arg_10], rbx
0x18018afa1  push    rbp
0x18018afa2  push    rsi
0x18018afa3  push    rdi
0x18018afa4  push    r12
0x18018afa6  push    r13
0x18018afa8  push    r14
0x18018afaa  push    r15
0x18018afac  mov     rbp, rsp
0x18018afaf  sub     rsp, 80h
0x18018afb6  mov     rax, cs:__security_cookie
0x18018afbd  xor     rax, rsp
0x18018afc0  mov     [rbp+var_8], rax
0x18018afc4  mov     sil, r9b
0x18018afc7  mov     r15, rcx
0x18018afca  mov     [rbp+var_28], rdx
0x18018afce  mov     r14, [rbp+arg_20]
0x18018afd2  xorps   xmm0, xmm0
0x18018afd5  xor     eax, eax
0x18018afd7  movups  xmmword ptr [r14], xmm0
0x18018afdb  mov     [r14+10h], rax
0x18018afdf  xor     r12d, r12d
0x18018afe2  mov     [rbp+pszPath], r12
0x18018afe6  lea     rdi, [rcx+138h]
0x18018afed  mov     rax, [rdi]
0x18018aff0  mov     rbx, [rax+70h]
0x18018aff4  lea     rcx, [rbp+pszPath]
0x18018aff8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18018affd  mov     r9, rax
0x18018b000  lea     r13d, [r12+1]
0x18018b005  mov     r8d, r13d
0x18018b008  mov     rdx, [rbp+var_28]
0x18018b00c  mov     rcx, rdi
0x18018b00f  mov     rax, rbx
0x18018b012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b017  mov     ebx, eax
0x18018b019  test    eax, eax
0x18018b01b  js      loc_18018B11E
0x18018b021  mov     rcx, [rbp+pszPath]; pszPath
0x18018b025  call    cs:__imp_PathIsNetworkPathW
0x18018b02b  test    eax, eax
0x18018b02d  jnz     loc_18018B128
0x18018b033  mov     edi, 2000h
0x18018b038  mov     [rbp+var_10], edi
0x18018b03b  lea     rcx, [r15+30h]
0x18018b03f  mov     rax, [rcx]
0x18018b042  lea     r9, [rbp+var_10]
0x18018b046  lea     r8, [rbp+var_28]
0x18018b04a  mov     edx, r13d
0x18018b04d  mov     rax, [rax+48h]
0x18018b051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b056  mov     ebx, eax
0x18018b058  test    eax, eax
0x18018b05a  jns     short loc_18018B0AD
0x18018b05c  mov     edx, 2316h; void *
0x18018b061  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18018b068  mov     r9d, ebx; char *
0x18018b06b  mov     rcx, [rbp+38h]; this
0x18018b06f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018b074  nop
0x18018b075  mov     rcx, [rbp+pszPath]; pv
0x18018b079  test    rcx, rcx
0x18018b07c  jz      short loc_18018B084
0x18018b07e  call    cs:__imp_CoTaskMemFree
0x18018b084  mov     eax, ebx
0x18018b086  mov     rcx, [rbp+var_8]
0x18018b08a  xor     rcx, rsp; StackCookie
0x18018b08d  call    __security_check_cookie
0x18018b092  mov     rbx, [rsp+80h+arg_10]
0x18018b09a  add     rsp, 80h
0x18018b0a1  pop     r15
0x18018b0a3  pop     r14
0x18018b0a5  pop     r13
0x18018b0a7  pop     r12
0x18018b0a9  pop     rdi
0x18018b0aa  pop     rsi
0x18018b0ab  pop     rbp
0x18018b0ac  retn
0x18018b0ad  test    [rbp+var_10], edi
0x18018b0b0  jnz     short loc_18018B0C5
0x18018b0b2  mov     rcx, [rbp+pszPath]; pv
0x18018b0b6  test    rcx, rcx
0x18018b0b9  jz      short loc_18018B0C1
0x18018b0bb  call    cs:__imp_CoTaskMemFree
0x18018b0c1  xor     eax, eax
0x18018b0c3  jmp     short loc_18018B086
0x18018b0c5  call    IsSHELL32_SHIsVirtualDevicePresent
0x18018b0ca  test    al, al
0x18018b0cc  jnz     loc_18018B2A5
0x18018b0d2  mov     [rbp+pUsers], r12
0x18018b0d6  lea     rdx, [rbp+pUsers]
0x18018b0da  mov     rcx, [rbp+pszPath]
0x18018b0de  call    cs:__imp_QueryIdentityProtectors
0x18018b0e4  mov     ebx, eax
0x18018b0e6  test    eax, eax
0x18018b0e8  jns     loc_18018B1BA
0x18018b0ee  mov     rcx, [rbp+38h]; this
0x18018b0f2  mov     r9d, eax; char *
0x18018b0f5  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18018b0fc  mov     edx, 2335h; void *
0x18018b101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018b106  mov     rcx, [rbp+pUsers]
0x18018b10a  test    rcx, rcx
0x18018b10d  jz      loc_18018B075
0x18018b113  call    cs:__imp_FreeIdentityProtectorList
0x18018b119  jmp     loc_18018B075
0x18018b11e  mov     edx, 2303h
0x18018b123  jmp     loc_18018B061
0x18018b128  mov     [rbp+pv], r12
0x18018b12c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18018b130  mov     [rbp+var_40], rax
0x18018b134  mov     [rbp+var_38], rax
0x18018b138  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18018b13c  mov     rcx, [rbp+pszPath]; unsigned __int16 *
0x18018b140  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x18018b145  mov     ebx, eax
0x18018b147  test    eax, eax
0x18018b149  js      short loc_18018B189
0x18018b14b  mov     rdx, r14; unsigned __int16 *
0x18018b14e  mov     rbx, [rbp+pv]
0x18018b152  mov     rcx, rbx; this
0x18018b155  call    ?GetEncryptionIdentitiesForNetworkPath@EdpHelpers@@YAJPEBGPEAUtagPROPVARIANT@@@Z; EdpHelpers::GetEncryptionIdentitiesForNetworkPath(ushort const *,tagPROPVARIANT *)
0x18018b15a  mov     edi, eax
0x18018b15c  test    eax, eax
0x18018b15e  jns     loc_18018B297
0x18018b164  test    rbx, rbx
0x18018b167  jz      short loc_18018B173
0x18018b169  mov     rcx, rbx; pv
0x18018b16c  call    cs:__imp_CoTaskMemFree
0x18018b172  nop
0x18018b173  mov     rcx, [rbp+pszPath]; pv
0x18018b177  test    rcx, rcx
0x18018b17a  jz      short loc_18018B182
0x18018b17c  call    cs:__imp_CoTaskMemFree
0x18018b182  mov     eax, edi
0x18018b184  jmp     loc_18018B086
0x18018b189  mov     rcx, [rbp+38h]; this
0x18018b18d  mov     r9d, ebx; char *
0x18018b190  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18018b197  mov     edx, 230Eh; void *
0x18018b19c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018b1a1  nop
0x18018b1a2  mov     rcx, [rbp+pv]; pv
0x18018b1a6  test    rcx, rcx
0x18018b1a9  jz      loc_18018B075
0x18018b1af  call    cs:__imp_CoTaskMemFree
0x18018b1b5  jmp     loc_18018B075
0x18018b1ba  mov     rax, [rbp+pUsers]
0x18018b1be  cmp     [rax], r12d
0x18018b1c1  jz      loc_18018B357
0x18018b1c7  mov     [rbp+pv], r12
0x18018b1cb  mov     [rbp+var_40], r12
0x18018b1cf  mov     [rbp+var_38], r12
0x18018b1d3  mov     [rbp+var_C], r12d
0x18018b1d7  lea     rdx, [rbp+var_C]
0x18018b1db  mov     rcx, [rbp+pszPath]
0x18018b1df  call    cs:__imp_EnterpriseDataGetStatus
0x18018b1e5  mov     ebx, eax
0x18018b1e7  test    eax, eax
0x18018b1e9  js      loc_18018B2EF
0x18018b1ef  test    sil, sil
0x18018b1f2  jnz     loc_18064B225
0x18018b1f8  mov     ebx, r12d
0x18018b1fb  mov     rax, [rbp+pUsers]
0x18018b1ff  cmp     ebx, [rax]
0x18018b201  jnb     loc_18018B333
0x18018b207  movsxd  rdx, ebx
0x18018b20a  mov     rcx, [rax+8]
0x18018b20e  mov     rdx, [rcx+rdx*8]
0x18018b212  mov     rdx, [rdx+10h]
0x18018b216  lea     rcx, [rbp+pv]
0x18018b21a  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18018b21f  mov     esi, eax
0x18018b221  test    eax, eax
0x18018b223  js      short loc_18018B24B
0x18018b225  mov     dword ptr [rbp+var_50], 3Bh ; ';'
0x18018b22c  mov     r8, r13
0x18018b22f  lea     rdx, [rbp+var_50]
0x18018b233  lea     rcx, [rbp+pv]
0x18018b237  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18018b23c  mov     esi, eax
0x18018b23e  test    eax, eax
0x18018b240  js      loc_18018B2F9
0x18018b246  add     ebx, r13d
0x18018b249  jmp     short loc_18018B1FB
0x18018b24b  mov     rcx, [rbp+38h]; this
0x18018b24f  mov     r9d, esi; char *
0x18018b252  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18018b259  mov     edx, 234Ch; void *
0x18018b25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018b263  mov     rcx, [rbp+pv]; pv
0x18018b267  test    rcx, rcx
0x18018b26a  jnz     short loc_18018B28F
0x18018b26c  mov     rcx, [rbp+pUsers]
0x18018b270  test    rcx, rcx
0x18018b273  jnz     loc_18018B328
0x18018b279  mov     rcx, [rbp+pszPath]; pv
0x18018b27d  test    rcx, rcx
0x18018b280  jz      short loc_18018B288
0x18018b282  call    cs:__imp_CoTaskMemFree
0x18018b288  mov     eax, esi
0x18018b28a  jmp     loc_18018B086
0x18018b28f  call    cs:__imp_CoTaskMemFree
0x18018b295  jmp     short loc_18018B26C
0x18018b297  lea     rcx, [rbp+pv]; void *
0x18018b29b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18018b2a0  jmp     loc_18018B0B2
0x18018b2a5  mov     rcx, [rbp+pszPath]; this
0x18018b2a9  call    ?IsLegacyEfsFile@EdpHelpers@@YA_NPEBG@Z; EdpHelpers::IsLegacyEfsFile(ushort const *)
0x18018b2ae  test    al, al
0x18018b2b0  jz      loc_18018B0D2
0x18018b2b6  mov     [rbp+pUsers], r12
0x18018b2ba  lea     rdx, [rbp+pUsers]; pUsers
0x18018b2be  mov     rcx, [rbp+pszPath]; lpFileName
0x18018b2c2  call    cs:__imp_QueryUsersOnEncryptedFile
0x18018b2c8  test    eax, eax
0x18018b2ca  jz      loc_18064B134
0x18018b2d0  mov     rcx, [rbp+38h]; this
0x18018b2d4  mov     r9d, eax; char *
0x18018b2d7  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18018b2de  mov     edx, 2328h; void *
0x18018b2e3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018b2e8  mov     ebx, eax
0x18018b2ea  jmp     loc_18064B125
0x18018b2ef  mov     edx, 2342h
0x18018b2f4  jmp     loc_18064B1FA
0x18018b2f9  mov     rcx, [rbp+38h]; this
0x18018b2fd  mov     r9d, esi; char *
0x18018b300  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18018b307  mov     edx, 234Dh; void *
0x18018b30c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018b311  lea     rcx, [rbp+pv]; void *
0x18018b315  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18018b31a  lea     rcx, [rbp+pUsers]
0x18018b31e  call    ??1?$unique_storage@U?$resource_policy@PEAU_ENCRYPTION_PROTECTOR_LIST@@P6AXPEAU1@@Z$1?FreeIdentityProtectorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(void)
0x18018b323  jmp     loc_18018B279
0x18018b328  call    cs:__imp_FreeIdentityProtectorList
0x18018b32e  jmp     loc_18018B279
0x18018b333  mov     edx, 101Fh
0x18018b338  mov     r8, r14
0x18018b33b  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18018b33f  call    InitPropVariantFromStringEx
0x18018b344  mov     ebx, eax
0x18018b346  test    eax, eax
0x18018b348  js      loc_18064B1F5
0x18018b34e  lea     rcx, [rbp+pv]; void *
0x18018b352  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18018b357  lea     rcx, [rbp+pUsers]
0x18018b35b  call    ??1?$unique_storage@U?$resource_policy@PEAU_ENCRYPTION_PROTECTOR_LIST@@P6AXPEAU1@@Z$1?FreeIdentityProtectorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(void)
0x18018b360  jmp     loc_18018B0B2
0x18064b104  mov     rcx, [rbp+38h]; this
0x18064b108  mov     r9d, ebx; char *
0x18064b10b  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18064b112  mov     edx, 2330h; void *
0x18064b117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18064b11c  lea     rcx, [rbp+pv]; void *
0x18064b120  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18064b125  lea     rcx, [rbp+pUsers]
0x18064b129  call    ??1?$unique_storage@U?$resource_policy@PEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@P6AXPEAU1@@Z$1?FreeEncryptionCertificateHashList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(void)
0x18064b12e  nop
0x18064b12f  jmp     loc_18018B075
0x18064b134  mov     [rbp+pv], r12
0x18064b138  mov     [rbp+var_40], r12
0x18064b13c  mov     [rbp+var_38], r12
0x18064b140  mov     ebx, r12d
0x18064b143  mov     rax, [rbp+pUsers]
0x18064b147  cmp     ebx, [rax]
0x18064b149  jnb     short loc_18064B1C2
0x18064b14b  movsxd  rdx, ebx
0x18064b14e  mov     rcx, [rax+8]
0x18064b152  mov     rdx, [rcx+rdx*8]
0x18064b156  mov     rdx, [rdx+18h]
0x18064b15a  lea     rcx, [rbp+pv]
0x18064b15e  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18064b163  mov     esi, eax
0x18064b165  test    eax, eax
0x18064b167  js      short loc_18064B192
0x18064b169  mov     dword ptr [rbp+var_50], 3Bh ; ';'
0x18064b170  mov     r8, r13
0x18064b173  lea     rdx, [rbp+var_50]
0x18064b177  lea     rcx, [rbp+pv]
0x18064b17b  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18064b180  mov     esi, eax
0x18064b182  test    eax, eax
0x18064b184  js      short loc_18064B18B
0x18064b186  add     ebx, r13d
0x18064b189  jmp     short loc_18064B143
0x18064b18b  mov     edx, 232Eh
0x18064b190  jmp     short loc_18064B197
0x18064b192  mov     edx, 232Dh; void *
0x18064b197  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18064b19e  mov     r9d, esi; char *
0x18064b1a1  mov     rcx, [rbp+38h]; this
0x18064b1a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18064b1aa  lea     rcx, [rbp+pv]; void *
0x18064b1ae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18064b1b3  lea     rcx, [rbp+pUsers]
0x18064b1b7  call    ??1?$unique_storage@U?$resource_policy@PEAU_ENCRYPTION_CERTIFICATE_HASH_LIST@@P6AXPEAU1@@Z$1?FreeEncryptionCertificateHashList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(void)
0x18064b1bc  nop
0x18064b1bd  jmp     loc_18018B279
  ... truncated ...
```
