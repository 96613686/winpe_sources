# CFSFolder::GetEncryptionOwnersHelper(CFSFolder *,_ITEMID_CHILD const *,IDFOLDER const *,bool,tagPROPVARIANT *)

- ea: `0x1800ea090`
- end: `0x1800ea4aa`
- name: `?GetEncryptionOwnersHelper@CFSFolder@@KAJPEAV1@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@_NPEAUtagPROPVARIANT@@@Z`
- size: `1050`
- prototype: `__int64 __fastcall(struct CFSFolder *, const struct _ITEMID_CHILD *, const struct IDFOLDER *, bool, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ea050`
- `0x1800ea070`

## callees

- `0x180038f50`
- `0x180042ac0`
- `0x180063050`
- `0x18007b9d0`
- `0x18007bf50`
- `0x18007dcf0`
- `0x1800e94bc`
- `0x1800ea090`
- `0x1800ea4b0`
- `0x1800f8f68`
- `0x1801720d0`
- `0x18027c010`
- `0x180311c10`
- `0x180370e34`
- `0x180374a30`
- `0x1803b1f60`
- `0x1805244c0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea1bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea397`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea3b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea1bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea27f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea397`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ea3b9`
- `efswrt!EnterpriseDataGetStatus` at `0x1800ea304`
- `efswrt!EnterpriseDataGetStatus` at `0x1800ea304`
- `efswrt!QueryIdentityProtectors` at `0x1800ea1e5`
- `efswrt!QueryIdentityProtectors` at `0x1800ea1e5`
- `efswrt!FreeIdentityProtectorList` at `0x1800ea220`
- `efswrt!FreeIdentityProtectorList` at `0x1800ea466`
- `efswrt!FreeIdentityProtectorList` at `0x1800ea220`
- `efswrt!FreeIdentityProtectorList` at `0x1800ea466`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800ea119`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800ea119`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!QueryUsersOnEncryptedFile` at `0x1800ea3f8`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!QueryUsersOnEncryptedFile` at `0x1800ea3f8`

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
  int v10; // ebx
  __int64 v11; // rdx
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  int v15; // eax
  struct tagPROPVARIANT *v16; // r8
  void *v17; // rbx
  int EncryptionIdentitiesForNetworkPath; // edi
  int Status; // eax
  unsigned __int16 v20; // r8
  unsigned int j; // ebx
  int v22; // eax
  unsigned int v23; // esi
  int v24; // eax
  int v25; // esi
  DWORD v26; // eax
  __int64 v27; // rdx
  DWORD i; // ebx
  int v29; // esi
  __int64 v30; // rdx
  int inited; // eax
  unsigned __int64 v32; // r9
  unsigned int v33; // [rsp+20h] [rbp-60h]
  unsigned __int16 v34[4]; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  __int64 v36; // [rsp+40h] [rbp-40h]
  __int64 v37; // [rsp+48h] [rbp-38h]
  const struct _ITEMID_CHILD *v38; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR pszPath; // [rsp+58h] [rbp-28h] BYREF
  __int64 v40; // [rsp+60h] [rbp-20h] BYREF
  PENCRYPTION_CERTIFICATE_HASH_LIST pUsers; // [rsp+68h] [rbp-18h] BYREF
  int v42; // [rsp+70h] [rbp-10h] BYREF
  int v43; // [rsp+74h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v38 = a2;
  *(_OWORD *)&a5->vt = 0;
  a5->bstrblobVal.pData = 0;
  pszPath = 0;
  v7 = (char *)a1 + 312;
  v8 = *(__int64 (__fastcall **)(char *, const struct _ITEMID_CHILD *, __int64, __int64))(*((_QWORD *)a1 + 39) + 112LL);
  v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
  v10 = v8(v7, v38, 1, v9);
  if ( v10 < 0 )
  {
    v11 = 8963;
    goto LABEL_5;
  }
  if ( !PathIsNetworkPathW(pszPath) )
  {
    v42 = 0x2000;
    v10 = (*(__int64 (__fastcall **)(char *, __int64, const struct _ITEMID_CHILD **, int *))(*((_QWORD *)a1 + 6) + 72LL))(
            (char *)a1 + 48,
            1,
            &v38,
            &v42);
    if ( v10 < 0 )
    {
      v11 = 8982;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v10,
        v33);
LABEL_6:
      if ( pszPath )
        CoTaskMemFree((LPVOID)pszPath);
      return (unsigned int)v10;
    }
    if ( (v42 & 0x2000) == 0 )
    {
      if ( pszPath )
        CoTaskMemFree((LPVOID)pszPath);
      return 0;
    }
    if ( IsDesktopPresent() && EdpHelpers::IsLegacyEfsFile((EdpHelpers *)pszPath, v13) )
    {
      pUsers = 0;
      v26 = QueryUsersOnEncryptedFile(pszPath, &pUsers);
      if ( v26 )
      {
        v10 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x2328,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
                (const char *)v26,
                v33);
LABEL_61:
        wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(&pUsers);
LABEL_64:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
        return (unsigned int)v10;
      }
      pv = 0;
      v36 = 0;
      v37 = 0;
      for ( i = 0; i < pUsers->nCert_Hash; ++i )
      {
        v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                &pv,
                pUsers->pUsers[i]->lpDisplayInformation);
        if ( v29 < 0 )
        {
          v30 = 9005;
          goto LABEL_58;
        }
        *(_DWORD *)v34 = 59;
        v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, v34, 1);
        if ( v29 < 0 )
        {
          v30 = 9006;
LABEL_58:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)(unsigned int)v29,
            v33);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          v10 = v29;
          goto LABEL_61;
        }
      }
      inited = InitPropVariantFromStringEx((unsigned __int16 *)pv);
      v10 = inited;
      if ( inited < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2330,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)inited,
          v33);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        goto LABEL_61;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_CERTIFICATE_HASH_LIST *,void (*)(_ENCRYPTION_CERTIFICATE_HASH_LIST *),&void FreeEncryptionCertificateHashList(_ENCRYPTION_CERTIFICATE_HASH_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_CERTIFICATE_HASH_LIST *,_ENCRYPTION_CERTIFICATE_HASH_LIST *,0,std::nullptr_t>>(&pUsers);
LABEL_63:
      v10 = 0;
      goto LABEL_64;
    }
    v40 = 0;
    v14 = QueryIdentityProtectors(pszPath, &v40);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2335,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v14,
        v33);
      if ( v40 )
        FreeIdentityProtectorList();
      goto LABEL_6;
    }
    if ( !*(_DWORD *)v40 )
    {
LABEL_50:
      wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(&v40);
      goto LABEL_63;
    }
    pv = 0;
    v36 = 0;
    v37 = 0;
    v43 = 0;
    Status = EnterpriseDataGetStatus(pszPath, &v43);
    v10 = Status;
    if ( Status < 0 )
    {
      v27 = 9026;
    }
    else
    {
      if ( !a4 || v43 != 2 )
        goto LABEL_30;
      v10 = -2147023728;
      pUsers = 0;
      v34[0] = 0;
      if ( !Windows::Internal::ResourceString::FindAndSize(
              g_hinst,
              0xC911u,
              v20,
              (const unsigned __int16 **)&pUsers,
              v34)
        || (v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                    &pv,
                    pUsers,
                    v34[0]),
            v10 < 0) )
      {
        v32 = (unsigned int)v10;
        v27 = 9030;
        goto LABEL_68;
      }
      *(_DWORD *)v34 = 59;
      Status = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, v34, 1);
      v10 = Status;
      if ( Status < 0 )
      {
        v27 = 9031;
      }
      else
      {
LABEL_30:
        for ( j = 0; j < *(_DWORD *)v40; ++j )
        {
          v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                  &pv,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v40 + 8) + 8LL * (int)j) + 16LL));
          v23 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x234C,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
              (const char *)(unsigned int)v22,
              v33);
            if ( pv )
              CoTaskMemFree(pv);
            if ( v40 )
              FreeIdentityProtectorList();
            if ( pszPath )
              CoTaskMemFree((LPVOID)pszPath);
            return v23;
          }
          *(_DWORD *)v34 = 59;
          v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
                  &pv,
                  v34,
                  1);
          v25 = v24;
          if ( v24 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x234D,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
              (const char *)(unsigned int)v24,
              v33);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
            wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(&v40);
            v10 = v25;
            goto LABEL_64;
          }
        }
        Status = InitPropVariantFromStringEx((unsigned __int16 *)pv);
        v10 = Status;
        if ( Status >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          goto LABEL_50;
        }
        v27 = 9039;
      }
    }
    v32 = (unsigned int)Status;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)v32,
      v33);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&void FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(&v40);
    goto LABEL_64;
  }
  pv = 0;
  v36 = -1;
  v37 = -1;
  v15 = PathConvertToUNC(pszPath, (unsigned __int16 **)&pv);
  v10 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v15,
      v33);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_6;
  }
  v17 = pv;
  EncryptionIdentitiesForNetworkPath = EdpHelpers::GetEncryptionIdentitiesForNetworkPath((EdpHelpers *)pv, &a5->vt, v16);
  if ( EncryptionIdentitiesForNetworkPath >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    goto LABEL_63;
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
0x1800ea090  mov     [rsp-38h+arg_10], rbx
0x1800ea095  push    rbp
0x1800ea096  push    rsi
0x1800ea097  push    rdi
0x1800ea098  push    r12
0x1800ea09a  push    r13
0x1800ea09c  push    r14
0x1800ea09e  push    r15
0x1800ea0a0  mov     rbp, rsp
0x1800ea0a3  sub     rsp, 80h
0x1800ea0aa  mov     rax, cs:__security_cookie
0x1800ea0b1  xor     rax, rsp
0x1800ea0b4  mov     [rbp+var_8], rax
0x1800ea0b8  mov     sil, r9b
0x1800ea0bb  mov     r15, rcx
0x1800ea0be  mov     [rbp+var_30], rdx
0x1800ea0c2  mov     r14, [rbp+arg_20]
0x1800ea0c6  xorps   xmm0, xmm0
0x1800ea0c9  xor     eax, eax
0x1800ea0cb  movups  xmmword ptr [r14], xmm0
0x1800ea0cf  mov     [r14+10h], rax
0x1800ea0d3  xor     r12d, r12d
0x1800ea0d6  mov     [rbp+pszPath], r12
0x1800ea0da  lea     rdi, [rcx+138h]
0x1800ea0e1  mov     rax, [rdi]
0x1800ea0e4  mov     rbx, [rax+70h]
0x1800ea0e8  lea     rcx, [rbp+pszPath]
0x1800ea0ec  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800ea0f1  mov     r9, rax
0x1800ea0f4  lea     r13d, [r12+1]
0x1800ea0f9  mov     r8d, r13d
0x1800ea0fc  mov     rdx, [rbp+var_30]
0x1800ea100  mov     rcx, rdi
0x1800ea103  mov     rax, rbx
0x1800ea106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea10b  mov     ebx, eax
0x1800ea10d  test    eax, eax
0x1800ea10f  js      loc_1800EA231
0x1800ea115  mov     rcx, [rbp+pszPath]; pszPath
0x1800ea119  call    cs:__imp_PathIsNetworkPathW
0x1800ea120  nop     dword ptr [rax+rax+00h]
0x1800ea125  test    eax, eax
0x1800ea127  jnz     loc_1800EA23B
0x1800ea12d  mov     edi, 2000h
0x1800ea132  mov     [rbp+var_10], edi
0x1800ea135  lea     rcx, [r15+30h]
0x1800ea139  mov     rax, [rcx]
0x1800ea13c  lea     r9, [rbp+var_10]
0x1800ea140  lea     r8, [rbp+var_30]
0x1800ea144  mov     edx, r13d
0x1800ea147  mov     rax, [rax+48h]
0x1800ea14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea150  mov     ebx, eax
0x1800ea152  test    eax, eax
0x1800ea154  jns     short loc_1800EA1AE
0x1800ea156  mov     edx, 2316h; void *
0x1800ea15b  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800ea162  mov     r9d, ebx; char *
0x1800ea165  mov     rcx, [rbp+38h]; this
0x1800ea169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea16e  nop
0x1800ea16f  mov     rcx, [rbp+pszPath]; pv
0x1800ea173  test    rcx, rcx
0x1800ea176  jz      short loc_1800EA184
0x1800ea178  call    cs:__imp_CoTaskMemFree
0x1800ea17f  nop     dword ptr [rax+rax+00h]
0x1800ea184  mov     eax, ebx
0x1800ea186  mov     rcx, [rbp+var_8]
0x1800ea18a  xor     rcx, rsp; StackCookie
0x1800ea18d  call    __security_check_cookie
0x1800ea192  mov     rbx, [rsp+80h+arg_10]
0x1800ea19a  add     rsp, 80h
0x1800ea1a1  pop     r15
0x1800ea1a3  pop     r14
0x1800ea1a5  pop     r13
0x1800ea1a7  pop     r12
0x1800ea1a9  pop     rdi
0x1800ea1aa  pop     rsi
0x1800ea1ab  pop     rbp
0x1800ea1ac  retn
0x1800ea1ae  test    [rbp+var_10], edi
0x1800ea1b1  jnz     short loc_1800EA1CC
0x1800ea1b3  mov     rcx, [rbp+pszPath]; pv
0x1800ea1b7  test    rcx, rcx
0x1800ea1ba  jz      short loc_1800EA1C8
0x1800ea1bc  call    cs:__imp_CoTaskMemFree
0x1800ea1c3  nop     dword ptr [rax+rax+00h]
0x1800ea1c8  xor     eax, eax
0x1800ea1ca  jmp     short loc_1800EA186
0x1800ea1cc  call    ?IsDesktopPresent@@YA_NXZ; IsDesktopPresent(void)
0x1800ea1d1  test    al, al
0x1800ea1d3  jnz     loc_1800EA3DB
0x1800ea1d9  mov     [rbp+var_20], r12
0x1800ea1dd  lea     rdx, [rbp+var_20]
0x1800ea1e1  mov     rcx, [rbp+pszPath]
0x1800ea1e5  call    cs:__imp_QueryIdentityProtectors
0x1800ea1ec  nop     dword ptr [rax+rax+00h]
0x1800ea1f1  mov     ebx, eax
0x1800ea1f3  test    eax, eax
0x1800ea1f5  jns     loc_1800EA2DF
0x1800ea1fb  mov     rcx, [rbp+38h]; this
0x1800ea1ff  mov     r9d, eax; char *
0x1800ea202  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800ea209  mov     edx, 2335h; void *
0x1800ea20e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea213  mov     rcx, [rbp+var_20]
0x1800ea217  test    rcx, rcx
0x1800ea21a  jz      loc_1800EA16F
0x1800ea220  call    cs:__imp_FreeIdentityProtectorList
0x1800ea227  nop     dword ptr [rax+rax+00h]
0x1800ea22c  jmp     loc_1800EA16F
0x1800ea231  mov     edx, 2303h
0x1800ea236  jmp     loc_1800EA15B
0x1800ea23b  mov     [rbp+pv], r12
0x1800ea23f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ea243  mov     [rbp+var_40], rax
0x1800ea247  mov     [rbp+var_38], rax
0x1800ea24b  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800ea24f  mov     rcx, [rbp+pszPath]; unsigned __int16 *
0x1800ea253  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x1800ea258  mov     ebx, eax
0x1800ea25a  test    eax, eax
0x1800ea25c  js      short loc_1800EA2A8
0x1800ea25e  mov     rdx, r14; unsigned __int16 *
0x1800ea261  mov     rbx, [rbp+pv]
0x1800ea265  mov     rcx, rbx; this
0x1800ea268  call    ?GetEncryptionIdentitiesForNetworkPath@EdpHelpers@@YAJPEBGPEAUtagPROPVARIANT@@@Z; EdpHelpers::GetEncryptionIdentitiesForNetworkPath(ushort const *,tagPROPVARIANT *)
0x1800ea26d  mov     edi, eax
0x1800ea26f  test    eax, eax
0x1800ea271  jns     loc_1800EA3CC
0x1800ea277  test    rbx, rbx
0x1800ea27a  jz      short loc_1800EA28C
0x1800ea27c  mov     rcx, rbx; pv
0x1800ea27f  call    cs:__imp_CoTaskMemFree
0x1800ea286  nop     dword ptr [rax+rax+00h]
0x1800ea28b  nop
0x1800ea28c  mov     rcx, [rbp+pszPath]; pv
0x1800ea290  test    rcx, rcx
0x1800ea293  jz      short loc_1800EA2A1
0x1800ea295  call    cs:__imp_CoTaskMemFree
0x1800ea29c  nop     dword ptr [rax+rax+00h]
0x1800ea2a1  mov     eax, edi
0x1800ea2a3  jmp     loc_1800EA186
0x1800ea2a8  mov     rcx, [rbp+38h]; this
0x1800ea2ac  mov     r9d, ebx; char *
0x1800ea2af  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800ea2b6  mov     edx, 230Eh; void *
0x1800ea2bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea2c0  nop
0x1800ea2c1  mov     rcx, [rbp+pv]; pv
0x1800ea2c5  test    rcx, rcx
0x1800ea2c8  jz      loc_1800EA16F
0x1800ea2ce  call    cs:__imp_CoTaskMemFree
0x1800ea2d5  nop     dword ptr [rax+rax+00h]
0x1800ea2da  jmp     loc_1800EA16F
0x1800ea2df  mov     rax, [rbp+var_20]
0x1800ea2e3  cmp     [rax], r12d
0x1800ea2e6  jz      loc_1800EA49B
0x1800ea2ec  mov     [rbp+pv], r12
0x1800ea2f0  mov     [rbp+var_40], r12
0x1800ea2f4  mov     [rbp+var_38], r12
0x1800ea2f8  mov     [rbp+var_C], r12d
0x1800ea2fc  lea     rdx, [rbp+var_C]
0x1800ea300  mov     rcx, [rbp+pszPath]
0x1800ea304  call    cs:__imp_EnterpriseDataGetStatus
0x1800ea30b  nop     dword ptr [rax+rax+00h]
0x1800ea310  mov     ebx, eax
0x1800ea312  test    eax, eax
0x1800ea314  js      loc_1800EA42B
0x1800ea31a  test    sil, sil
0x1800ea31d  jnz     loc_180665C20
0x1800ea323  mov     ebx, r12d
0x1800ea326  mov     rax, [rbp+var_20]
0x1800ea32a  cmp     ebx, [rax]
0x1800ea32c  jnb     loc_1800EA477
0x1800ea332  movsxd  rdx, ebx
0x1800ea335  mov     rcx, [rax+8]
0x1800ea339  mov     rdx, [rcx+rdx*8]
0x1800ea33d  mov     rdx, [rdx+10h]
0x1800ea341  lea     rcx, [rbp+pv]
0x1800ea345  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x1800ea34a  mov     esi, eax
0x1800ea34c  test    eax, eax
0x1800ea34e  js      short loc_1800EA376
0x1800ea350  mov     dword ptr [rbp+var_50], 3Bh ; ';'
0x1800ea357  mov     r8, r13
0x1800ea35a  lea     rdx, [rbp+var_50]
0x1800ea35e  lea     rcx, [rbp+pv]
0x1800ea362  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800ea367  mov     esi, eax
0x1800ea369  test    eax, eax
0x1800ea36b  js      loc_1800EA435
0x1800ea371  add     ebx, r13d
0x1800ea374  jmp     short loc_1800EA326
0x1800ea376  mov     rcx, [rbp+38h]; this
0x1800ea37a  mov     r9d, esi; char *
0x1800ea37d  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800ea384  mov     edx, 234Ch; void *
0x1800ea389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea38e  mov     rcx, [rbp+pv]; pv
0x1800ea392  test    rcx, rcx
0x1800ea395  jz      short loc_1800EA3A3
0x1800ea397  call    cs:__imp_CoTaskMemFree
0x1800ea39e  nop     dword ptr [rax+rax+00h]
0x1800ea3a3  mov     rcx, [rbp+var_20]
0x1800ea3a7  test    rcx, rcx
0x1800ea3aa  jnz     loc_1800EA466
0x1800ea3b0  mov     rcx, [rbp+pszPath]; pv
0x1800ea3b4  test    rcx, rcx
0x1800ea3b7  jz      short loc_1800EA3C5
0x1800ea3b9  call    cs:__imp_CoTaskMemFree
0x1800ea3c0  nop     dword ptr [rax+rax+00h]
0x1800ea3c5  mov     eax, esi
0x1800ea3c7  jmp     loc_1800EA186
0x1800ea3cc  lea     rcx, [rbp+pv]; void *
0x1800ea3d0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ea3d5  nop
0x1800ea3d6  jmp     loc_180665BD8
0x1800ea3db  mov     rcx, [rbp+pszPath]; this
0x1800ea3df  call    ?IsLegacyEfsFile@EdpHelpers@@YA_NPEBG@Z; EdpHelpers::IsLegacyEfsFile(ushort const *)
0x1800ea3e4  test    al, al
0x1800ea3e6  jz      loc_1800EA1D9
0x1800ea3ec  mov     [rbp+pUsers], r12
0x1800ea3f0  lea     rdx, [rbp+pUsers]; pUsers
0x1800ea3f4  mov     rcx, [rbp+pszPath]; lpFileName
0x1800ea3f8  call    cs:__imp_QueryUsersOnEncryptedFile
0x1800ea3ff  nop     dword ptr [rax+rax+00h]
0x1800ea404  test    eax, eax
0x1800ea406  jz      loc_180665B00
0x1800ea40c  mov     rcx, [rbp+38h]; this
0x1800ea410  mov     r9d, eax; char *
0x1800ea413  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800ea41a  mov     edx, 2328h; void *
0x1800ea41f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ea424  mov     ebx, eax
0x1800ea426  jmp     loc_180665BBB
0x1800ea42b  mov     edx, 2342h
0x1800ea430  jmp     loc_180665BEF
0x1800ea435  mov     rcx, [rbp+38h]; this
0x1800ea439  mov     r9d, esi; char *
0x1800ea43c  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800ea443  mov     edx, 234Dh; void *
0x1800ea448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ea44d  lea     rcx, [rbp+pv]; void *
0x1800ea451  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ea456  lea     rcx, [rbp+var_20]
0x1800ea45a  call    ??1?$unique_storage@U?$resource_policy@PEAU_ENCRYPTION_PROTECTOR_LIST@@P6AXPEAU1@@Z$1?FreeIdentityProtectorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(void)
0x1800ea45f  mov     ebx, esi
0x1800ea461  jmp     loc_180665BDB
0x1800ea466  call    cs:__imp_FreeIdentityProtectorList
0x1800ea46d  nop     dword ptr [rax+rax+00h]
0x1800ea472  jmp     loc_1800EA3B0
0x1800ea477  mov     edx, 101Fh
0x1800ea47c  mov     r8, r14
0x1800ea47f  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1800ea483  call    InitPropVariantFromStringEx
0x1800ea488  mov     ebx, eax
0x1800ea48a  test    eax, eax
0x1800ea48c  js      loc_180665BEA
0x1800ea492  lea     rcx, [rbp+pv]; void *
0x1800ea496  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ea49b  lea     rcx, [rbp+var_20]
0x1800ea49f  call    ??1?$unique_storage@U?$resource_policy@PEAU_ENCRYPTION_PROTECTOR_LIST@@P6AXPEAU1@@Z$1?FreeIdentityProtectorList@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ENCRYPTION_PROTECTOR_LIST *,void (*)(_ENCRYPTION_PROTECTOR_LIST *),&FreeIdentityProtectorList(_ENCRYPTION_PROTECTOR_LIST *),wistd::integral_constant<unsigned __int64,0>,_ENCRYPTION_PROTECTOR_LIST *,_ENCRYPTION_PROTECTOR_LIST *,0,std::nullptr_t>>(void)
0x1800ea4a4  nop
0x1800ea4a5  jmp     loc_180665BD8
0x180665b00  mov     [rbp+pv], r12
0x180665b04  mov     [rbp+var_40], r12
0x180665b08  mov     [rbp+var_38], r12
0x180665b0c  mov     ebx, r12d
0x180665b0f  mov     rax, [rbp+pUsers]
0x180665b13  cmp     ebx, [rax]
0x180665b15  jnb     short loc_180665B83
0x180665b17  movsxd  rdx, ebx
0x180665b1a  mov     rcx, [rax+8]
0x180665b1e  mov     rdx, [rcx+rdx*8]
0x180665b22  mov     rdx, [rdx+18h]
0x180665b26  lea     rcx, [rbp+pv]
0x180665b2a  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x180665b2f  mov     esi, eax
0x180665b31  test    eax, eax
0x180665b33  js      short loc_180665B5E
0x180665b35  mov     dword ptr [rbp+var_50], 3Bh ; ';'
0x180665b3c  mov     r8, r13
0x180665b3f  lea     rdx, [rbp+var_50]
0x180665b43  lea     rcx, [rbp+pv]
0x180665b47  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x180665b4c  mov     esi, eax
0x180665b4e  test    eax, eax
0x180665b50  js      short loc_180665B57
0x180665b52  add     ebx, r13d
0x180665b55  jmp     short loc_180665B0F
0x180665b57  mov     edx, 232Eh
0x180665b5c  jmp     short loc_180665B63
0x180665b5e  mov     edx, 232Dh; void *
0x180665b63  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180665b6a  mov     r9d, esi; char *
0x180665b6d  mov     rcx, [rbp+38h]; this
0x180665b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180665b76  lea     rcx, [rbp+pv]; void *
0x180665b7a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
  ... truncated ...
```
