# CZoneIdentifier::Save(ushort const *,int)

- ea: `0x1800a0b60`
- end: `0x1800a1047`
- name: `?Save@CZoneIdentifier@@UEAAJPEBGH@Z`
- size: `1255`
- prototype: `int(CZoneIdentifier *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180012c50`
- `0x180032088`
- `0x18003bf28`
- `0x18008cf94`
- `0x1800912b4`
- `0x1800a0b60`
- `0x1800a11c0`
- `0x1800a5760`
- `0x180110f88`
- `0x180111030`
- `0x180111654`
- `0x180111f34`
- `0x1801122e8`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a0d75`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a0d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0f39`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0c5c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0e28`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0fde`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0c5c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0e28`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a0fde`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a0c17`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a0de7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a0c17`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a0de7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a0c80`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a0cbc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a0c80`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a0cbc`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800a0d46`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800a0d46`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1800a0f29`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1800a0f29`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0dd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0f67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0f9c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0fb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a100a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0dd3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0f67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0f9c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a0fb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a100a`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800a0efc`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800a0efc`

## string_xrefs

- `0x1800a0ce8`: `LastWriterPackageFamilyName`
- `0x1800a0d2d`: `LastWriterPackageFamilyName`

## pseudocode

```c
int __fastcall CZoneIdentifier::Save(CZoneIdentifier *this, const unsigned __int16 *a2)
{
  CZoneIdentifier *v4; // r12
  int v5; // r8d
  int updated; // eax
  signed int NameAt; // ebx
  __int64 v8; // rdx
  DWORD FileAttributesW; // eax
  DWORD v10; // edi
  signed int LastError; // eax
  int v12; // r14d
  const char *v13; // r9
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  signed int v16; // eax
  __int64 v17; // rcx
  const WCHAR *String; // rax
  __int64 v19; // rcx
  int v20; // eax
  DWORD v21; // eax
  signed int v22; // eax
  const char *v23; // r9
  unsigned int v24; // r12d
  const WCHAR *v25; // r8
  HRESULT v26; // eax
  bool v27; // sf
  DWORD nSize; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpKeyName; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT propvar[3]; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT pvar[3]; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v35[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReturnedString[72]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v4 = (CZoneIdentifier *)((char *)this - 40);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::GetImpl'::`2'::impl) )
  {
    LOWORD(v35[0]) = 0;
    updated = CZoneIdentifier::_UpdateFile(v4, a2);
    NameAt = updated;
    if ( updated < 0 )
    {
      v8 = 302;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)(unsigned int)updated,
        nSize);
LABEL_56:
      PropVariantClear(v35);
      return NameAt;
    }
    updated = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, PROPVARIANT *))(**((_QWORD **)this + 2) + 24LL))(
                *((_QWORD *)this + 2),
                L"ZoneId",
                v35);
    NameAt = updated;
    if ( updated < 0 )
    {
      v8 = 303;
      goto LABEL_6;
    }
    if ( !LOWORD(v35[0]) )
    {
      FileAttributesW = GetFileAttributesW(a2);
      v10 = FileAttributesW;
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_55;
      }
      v12 = FileAttributesW & 1;
      if ( (FileAttributesW & 1) != 0 && !SetFileAttributesW(a2, FileAttributesW & 0xFFFFFFFE) )
      {
        v14 = 317;
LABEL_54:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v14,
                      (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
                      v13);
LABEL_55:
        NameAt = LastError;
        goto LABEL_56;
      }
      v15 = (const WCHAR *)*((_QWORD *)this + 1);
      if ( *((_BYTE *)this + 24) )
      {
        if ( DeleteFileW(v15) )
        {
          NameAt = 0;
        }
        else
        {
          v16 = GetLastError();
          NameAt = v16;
          if ( v16 > 0 )
            NameAt = (unsigned __int16)v16 | 0x80070000;
        }
      }
      else
      {
        NameAt = !DeleteFileW(v15) ? 0x80004005 : 0;
      }
LABEL_51:
      CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u);
      if ( !v12 || SetFileAttributesW(a2, v10) )
        goto LABEL_56;
      v14 = 399;
      goto LABEL_54;
    }
    v17 = *((_QWORD *)this + 2);
    LOWORD(pvar[0]) = 0;
    if ( (*(int (__fastcall **)(__int64, const WCHAR *, PROPVARIANT *))(*(_QWORD *)v17 + 24LL))(
           v17,
           L"LastWriterPackageFamilyName",
           pvar) >= 0 )
    {
      if ( LOWORD(pvar[0]) )
      {
        memset_0(ReturnedString, 0, 0x82u);
        if ( !GetPrivateProfileStringW(
                L"ZoneTransfer",
                L"LastWriterPackageFamilyName",
                0,
                ReturnedString,
                0x41u,
                *((LPCWSTR *)this + 1))
          || (String = CPropVariant::GetString((CPropVariant *)pvar),
              CompareStringOrdinal(ReturnedString, -1, String, -1, 1) != 2) )
        {
          CZoneIdentifier::RemoveNamedValue((CZoneIdentifier *)((char *)this - 8), L"AppZoneId");
        }
      }
    }
    v19 = *((_QWORD *)this + 2);
    v30 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 40LL))(v19, &v30);
    NameAt = v20;
    if ( v20 >= 0 )
    {
      v21 = GetFileAttributesW(a2);
      v10 = v21;
      if ( v21 == -1 )
      {
        v22 = GetLastError();
        NameAt = v22;
        if ( v22 > 0 )
          NameAt = (unsigned __int16)v22 | 0x80070000;
      }
      else
      {
        v12 = v21 & 1;
        if ( (v21 & 1) == 0 || SetFileAttributesW(a2, v21 & 0xFFFFFFFE) )
        {
          NameAt = 0;
          if ( (int)CZoneIdentifier::_SaveBatchedHelper(v4, v30) < 0 )
          {
            v24 = 0;
            if ( v30 )
            {
              while ( 1 )
              {
                lpKeyName = 0;
                LOWORD(propvar[0]) = 0;
                ppszOut = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &lpKeyName,
                  0);
                NameAt = CZoneIdentifier::GetNameAt(
                           (CZoneIdentifier *)((char *)this - 8),
                           v24,
                           (unsigned __int16 **)&lpKeyName);
                if ( NameAt < 0 )
                  break;
                NameAt = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, PROPVARIANT *))(**((_QWORD **)this + 2) + 24LL))(
                           *((_QWORD *)this + 2),
                           lpKeyName,
                           propvar);
                if ( NameAt < 0 )
                  break;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &ppszOut,
                  0);
                NameAt = 0;
                v25 = 0;
                ppszOut = 0;
                if ( LOWORD(propvar[0]) )
                {
                  v26 = PropVariantToStringAlloc(propvar, &ppszOut);
                  if ( v26 != -2147023728 )
                    NameAt = v26;
                  if ( NameAt < 0 )
                    break;
                  v25 = ppszOut;
                }
                if ( !WritePrivateProfileStringW(L"ZoneTransfer", lpKeyName, v25, *((LPCWSTR *)this + 1)) )
                {
                  NameAt = GetLastError();
                  v27 = NameAt < 0;
                  if ( NameAt > 0 )
                  {
                    NameAt = (unsigned __int16)NameAt | 0x80070000;
                    v27 = NameAt < 0;
                  }
                  if ( v27 )
                    break;
                }
                wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&ppszOut);
                PropVariantClear(propvar);
                wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpKeyName);
                if ( ++v24 >= v30 )
                  goto LABEL_50;
              }
              wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&ppszOut);
              PropVariantClear(propvar);
              wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpKeyName);
            }
          }
LABEL_50:
          PropVariantClear(pvar);
          goto LABEL_51;
        }
        NameAt = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x165,
                   (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
                   v23);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x158,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)(unsigned int)v20,
        nSize);
    }
    PropVariantClear(pvar);
    goto LABEL_56;
  }
  return CZoneIdentifier::SaveOld(v4, a2, v5);
}

```

## disassembly

```asm
0x1800a0b60  mov     [rsp-8+arg_10], rbx
0x1800a0b65  push    rbp
0x1800a0b66  push    rsi
0x1800a0b67  push    rdi
0x1800a0b68  push    r12
0x1800a0b6a  push    r13
0x1800a0b6c  push    r14
0x1800a0b6e  push    r15
0x1800a0b70  lea     rbp, [rsp-30h]
0x1800a0b75  sub     rsp, 130h
0x1800a0b7c  mov     rax, cs:__security_cookie
0x1800a0b83  xor     rax, rsp
0x1800a0b86  mov     [rbp+60h+var_40], rax
0x1800a0b8a  mov     r15, rdx
0x1800a0b8d  mov     rsi, rcx
0x1800a0b90  lea     r12, [rcx-28h]
0x1800a0b94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::GetImpl(void)'::`2'::impl
0x1800a0b9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::__private_IsEnabled(void)
0x1800a0ba0  xor     r13d, r13d
0x1800a0ba3  mov     rdx, r15; unsigned __int16 *
0x1800a0ba6  mov     rcx, r12; this
0x1800a0ba9  test    al, al
0x1800a0bab  jz      loc_1800A101A
0x1800a0bb1  mov     word ptr [rsp+160h+var_E8], r13w
0x1800a0bb7  call    ?_UpdateFile@CZoneIdentifier@@AEAAJPEBG@Z; CZoneIdentifier::_UpdateFile(ushort const *)
0x1800a0bbc  mov     ebx, eax
0x1800a0bbe  test    eax, eax
0x1800a0bc0  jns     short loc_1800A0BC9
0x1800a0bc2  mov     edx, 12Eh
0x1800a0bc7  jmp     short loc_1800A0BF0
0x1800a0bc9  mov     rcx, [rsi+10h]
0x1800a0bcd  lea     r8, [rsp+160h+var_E8]
0x1800a0bd2  lea     rdx, KeyName; "ZoneId"
0x1800a0bd9  mov     rax, [rcx]
0x1800a0bdc  mov     rax, [rax+18h]
0x1800a0be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0be5  mov     ebx, eax
0x1800a0be7  test    eax, eax
0x1800a0be9  jns     short loc_1800A0C08
0x1800a0beb  mov     edx, 12Fh; void *
0x1800a0bf0  mov     rcx, [rbp+68h]; this
0x1800a0bf4  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1800a0bfb  mov     r9d, eax; char *
0x1800a0bfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0c03  jmp     loc_1800A1005
0x1800a0c08  cmp     word ptr [rsp+160h+var_E8], r13w
0x1800a0c0e  jnz     loc_1800A0CD9
0x1800a0c14  mov     rcx, r15; lpFileName
0x1800a0c17  call    cs:__imp_GetFileAttributesW
0x1800a0c1e  nop     dword ptr [rax+rax+00h]
0x1800a0c23  mov     edi, eax
0x1800a0c25  cmp     eax, 0FFFFFFFFh
0x1800a0c28  jnz     short loc_1800A0C4B
0x1800a0c2a  call    cs:__imp_GetLastError
0x1800a0c31  nop     dword ptr [rax+rax+00h]
0x1800a0c36  test    eax, eax
0x1800a0c38  jle     loc_1800A1003
0x1800a0c3e  movzx   eax, ax
0x1800a0c41  or      eax, 80070000h
0x1800a0c46  jmp     loc_1800A1003
0x1800a0c4b  mov     r14d, eax
0x1800a0c4e  and     r14d, 1
0x1800a0c52  jz      short loc_1800A0C76
0x1800a0c54  mov     edx, eax
0x1800a0c56  mov     rcx, r15; lpFileName
0x1800a0c59  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800a0c5c  call    cs:__imp_SetFileAttributesW
0x1800a0c63  nop     dword ptr [rax+rax+00h]
0x1800a0c68  test    eax, eax
0x1800a0c6a  jnz     short loc_1800A0C76
0x1800a0c6c  mov     edx, 13Dh
0x1800a0c71  jmp     loc_1800A0FF3
0x1800a0c76  mov     rcx, [rsi+8]; lpFileName
0x1800a0c7a  cmp     [rsi+18h], r13b
0x1800a0c7e  jz      short loc_1800A0CBC
0x1800a0c80  call    cs:__imp_DeleteFileW
0x1800a0c87  nop     dword ptr [rax+rax+00h]
0x1800a0c8c  test    eax, eax
0x1800a0c8e  jz      short loc_1800A0C98
0x1800a0c90  mov     ebx, r13d
0x1800a0c93  jmp     loc_1800A0FC3
0x1800a0c98  call    cs:__imp_GetLastError
0x1800a0c9f  nop     dword ptr [rax+rax+00h]
0x1800a0ca4  mov     ebx, eax
0x1800a0ca6  test    eax, eax
0x1800a0ca8  jle     loc_1800A0FC3
0x1800a0cae  movzx   ebx, ax
0x1800a0cb1  or      ebx, 80070000h
0x1800a0cb7  jmp     loc_1800A0FC3
0x1800a0cbc  call    cs:__imp_DeleteFileW
0x1800a0cc3  nop     dword ptr [rax+rax+00h]
0x1800a0cc8  neg     eax
0x1800a0cca  sbb     ebx, ebx
0x1800a0ccc  not     ebx
0x1800a0cce  and     ebx, 80004005h
0x1800a0cd4  jmp     loc_1800A0FC3
0x1800a0cd9  mov     rcx, [rsi+10h]
0x1800a0cdd  lea     r8, [rsp+160h+pvar]
0x1800a0ce2  mov     word ptr [rsp+160h+pvar], r13w
0x1800a0ce8  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x1800a0cef  mov     rax, [rcx]
0x1800a0cf2  mov     rax, [rax+18h]
0x1800a0cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0cfb  test    eax, eax
0x1800a0cfd  js      loc_1800A0D96
0x1800a0d03  cmp     word ptr [rsp+160h+pvar], r13w
0x1800a0d09  jz      loc_1800A0D96
0x1800a0d0f  xor     edx, edx; Val
0x1800a0d11  lea     rcx, [rbp+60h+ReturnedString]; void *
0x1800a0d15  mov     r8d, 82h; Size
0x1800a0d1b  call    memset_0
0x1800a0d20  mov     rax, [rsi+8]
0x1800a0d24  lea     r9, [rbp+60h+ReturnedString]; lpReturnedString
0x1800a0d28  mov     [rsp+160h+lpFileName], rax; lpFileName
0x1800a0d2d  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x1800a0d34  xor     r8d, r8d; lpDefault
0x1800a0d37  mov     [rsp+160h+nSize], 41h ; 'A'; nSize
0x1800a0d3f  lea     rcx, AppName; "ZoneTransfer"
0x1800a0d46  call    cs:__imp_GetPrivateProfileStringW
0x1800a0d4d  nop     dword ptr [rax+rax+00h]
0x1800a0d52  test    eax, eax
0x1800a0d54  jz      short loc_1800A0D86
0x1800a0d56  lea     rcx, [rsp+160h+pvar]; this
0x1800a0d5b  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x1800a0d60  or      edx, 0FFFFFFFFh; cchCount1
0x1800a0d63  mov     [rsp+160h+nSize], 1; int
0x1800a0d6b  mov     r9d, edx; cchCount2
0x1800a0d6e  lea     rcx, [rbp+60h+ReturnedString]; lpString1
0x1800a0d72  mov     r8, rax; lpString2
0x1800a0d75  call    cs:__imp_CompareStringOrdinal
0x1800a0d7c  nop     dword ptr [rax+rax+00h]
0x1800a0d81  cmp     eax, 2
0x1800a0d84  jz      short loc_1800A0D96
0x1800a0d86  lea     rcx, [rsi-8]; this
0x1800a0d8a  lea     rdx, aAppzoneid; "AppZoneId"
0x1800a0d91  call    ?RemoveNamedValue@CZoneIdentifier@@UEAAJPEBG@Z; CZoneIdentifier::RemoveNamedValue(ushort const *)
0x1800a0d96  mov     rcx, [rsi+10h]
0x1800a0d9a  lea     rdx, [rsp+160h+var_130]
0x1800a0d9f  mov     [rsp+160h+var_130], r13d
0x1800a0da4  mov     rax, [rcx]
0x1800a0da7  mov     rax, [rax+28h]
0x1800a0dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0db0  mov     ebx, eax
0x1800a0db2  test    eax, eax
0x1800a0db4  jns     short loc_1800A0DE4
0x1800a0db6  mov     rcx, [rbp+68h]; this
0x1800a0dba  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1800a0dc1  mov     r9d, eax; char *
0x1800a0dc4  mov     edx, 158h; void *
0x1800a0dc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0dce  lea     rcx, [rsp+160h+pvar]; pvar
0x1800a0dd3  call    cs:__imp_PropVariantClear
0x1800a0dda  nop     dword ptr [rax+rax+00h]
0x1800a0ddf  jmp     loc_1800A1005
0x1800a0de4  mov     rcx, r15; lpFileName
0x1800a0de7  call    cs:__imp_GetFileAttributesW
0x1800a0dee  nop     dword ptr [rax+rax+00h]
0x1800a0df3  mov     edi, eax
0x1800a0df5  cmp     eax, 0FFFFFFFFh
0x1800a0df8  jnz     short loc_1800A0E17
0x1800a0dfa  call    cs:__imp_GetLastError
0x1800a0e01  nop     dword ptr [rax+rax+00h]
0x1800a0e06  mov     ebx, eax
0x1800a0e08  test    eax, eax
0x1800a0e0a  jle     short loc_1800A0DCE
0x1800a0e0c  movzx   ebx, ax
0x1800a0e0f  or      ebx, 80070000h
0x1800a0e15  jmp     short loc_1800A0DCE
0x1800a0e17  mov     r14d, eax
0x1800a0e1a  and     r14d, 1
0x1800a0e1e  jz      short loc_1800A0E54
0x1800a0e20  mov     edx, eax
0x1800a0e22  mov     rcx, r15; lpFileName
0x1800a0e25  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800a0e28  call    cs:__imp_SetFileAttributesW
0x1800a0e2f  nop     dword ptr [rax+rax+00h]
0x1800a0e34  test    eax, eax
0x1800a0e36  jnz     short loc_1800A0E54
0x1800a0e38  mov     rcx, [rbp+68h]; this
0x1800a0e3c  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1800a0e43  mov     edx, 165h; void *
0x1800a0e48  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a0e4d  mov     ebx, eax
0x1800a0e4f  jmp     loc_1800A0DCE
0x1800a0e54  mov     edx, [rsp+160h+var_130]; unsigned int
0x1800a0e58  mov     rcx, r12; this
0x1800a0e5b  mov     ebx, r13d
0x1800a0e5e  call    ?_SaveBatchedHelper@CZoneIdentifier@@AEAAJK@Z; CZoneIdentifier::_SaveBatchedHelper(ulong)
0x1800a0e63  test    eax, eax
0x1800a0e65  jns     loc_1800A0FB2
0x1800a0e6b  mov     r12d, r13d
0x1800a0e6e  cmp     [rsp+160h+var_130], r13d
0x1800a0e73  jbe     loc_1800A0FB2
0x1800a0e79  xor     ecx, ecx
0x1800a0e7b  xor     edx, edx
0x1800a0e7d  mov     [rsp+160h+lpKeyName], rcx
0x1800a0e82  mov     word ptr [rsp+160h+propvar], cx
0x1800a0e87  mov     [rsp+160h+ppszOut], rcx
0x1800a0e8c  lea     rcx, [rsp+160h+lpKeyName]
0x1800a0e91  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a0e96  lea     r8, [rsp+160h+lpKeyName]; unsigned __int16 **
0x1800a0e9b  mov     edx, r12d; unsigned int
0x1800a0e9e  lea     rcx, [rsi-8]; this
0x1800a0ea2  call    ?GetNameAt@CZoneIdentifier@@UEAAJKPEAPEAG@Z; CZoneIdentifier::GetNameAt(ulong,ushort * *)
0x1800a0ea7  mov     ebx, eax
0x1800a0ea9  test    eax, eax
0x1800a0eab  js      loc_1800A0F8D
0x1800a0eb1  mov     rcx, [rsi+10h]
0x1800a0eb5  lea     r8, [rsp+160h+propvar]
0x1800a0eba  mov     rdx, [rsp+160h+lpKeyName]
0x1800a0ebf  mov     rax, [rcx]
0x1800a0ec2  mov     rax, [rax+18h]
0x1800a0ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0ecb  lea     rcx, [rsp+160h+ppszOut]
0x1800a0ed0  mov     ebx, eax
0x1800a0ed2  test    eax, eax
0x1800a0ed4  js      loc_1800A0F92
0x1800a0eda  xor     edx, edx
0x1800a0edc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a0ee1  xor     ebx, ebx
0x1800a0ee3  mov     r8d, ebx
0x1800a0ee6  mov     [rsp+160h+ppszOut], rbx
0x1800a0eeb  cmp     word ptr [rsp+160h+propvar], bx
0x1800a0ef0  jz      short loc_1800A0F19
0x1800a0ef2  lea     rdx, [rsp+160h+ppszOut]; ppszOut
0x1800a0ef7  lea     rcx, [rsp+160h+propvar]; propvar
0x1800a0efc  call    cs:__imp_PropVariantToStringAlloc
0x1800a0f03  nop     dword ptr [rax+rax+00h]
0x1800a0f08  cmp     eax, 80070490h
0x1800a0f0d  cmovnz  ebx, eax
0x1800a0f10  test    ebx, ebx
0x1800a0f12  js      short loc_1800A0F8D
0x1800a0f14  mov     r8, [rsp+160h+ppszOut]; lpString
0x1800a0f19  mov     r9, [rsi+8]; lpFileName
0x1800a0f1d  lea     rcx, AppName; "ZoneTransfer"
0x1800a0f24  mov     rdx, [rsp+160h+lpKeyName]; lpKeyName
0x1800a0f29  call    cs:__imp_WritePrivateProfileStringW
0x1800a0f30  nop     dword ptr [rax+rax+00h]
0x1800a0f35  test    eax, eax
0x1800a0f37  jnz     short loc_1800A0F58
0x1800a0f39  call    cs:__imp_GetLastError
0x1800a0f40  nop     dword ptr [rax+rax+00h]
0x1800a0f45  mov     ebx, eax
0x1800a0f47  test    eax, eax
0x1800a0f49  jle     short loc_1800A0F56
0x1800a0f4b  movzx   ebx, bx
0x1800a0f4e  or      ebx, 80070000h
0x1800a0f54  test    ebx, ebx
0x1800a0f56  js      short loc_1800A0F8D
0x1800a0f58  lea     rcx, [rsp+160h+ppszOut]
0x1800a0f5d  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1800a0f62  lea     rcx, [rsp+160h+propvar]; pvar
0x1800a0f67  call    cs:__imp_PropVariantClear
0x1800a0f6e  nop     dword ptr [rax+rax+00h]
0x1800a0f73  lea     rcx, [rsp+160h+lpKeyName]
0x1800a0f78  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1800a0f7d  inc     r12d
0x1800a0f80  cmp     r12d, [rsp+160h+var_130]
0x1800a0f85  jb      loc_1800A0E79
0x1800a0f8b  jmp     short loc_1800A0FB2
0x1800a0f8d  lea     rcx, [rsp+160h+ppszOut]
0x1800a0f92  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1800a0f97  lea     rcx, [rsp+160h+propvar]; pvar
0x1800a0f9c  call    cs:__imp_PropVariantClear
0x1800a0fa3  nop     dword ptr [rax+rax+00h]
0x1800a0fa8  lea     rcx, [rsp+160h+lpKeyName]
0x1800a0fad  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1800a0fb2  lea     rcx, [rsp+160h+pvar]; pvar
0x1800a0fb7  call    cs:__imp_PropVariantClear
0x1800a0fbe  nop     dword ptr [rax+rax+00h]
0x1800a0fc3  mov     edx, 4; unsigned int
0x1800a0fc8  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x1800a0fcf  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x1800a0fd4  test    r14d, r14d
0x1800a0fd7  jz      short loc_1800A1005
0x1800a0fd9  mov     edx, edi; dwFileAttributes
0x1800a0fdb  mov     rcx, r15; lpFileName
0x1800a0fde  call    cs:__imp_SetFileAttributesW
0x1800a0fe5  nop     dword ptr [rax+rax+00h]
0x1800a0fea  test    eax, eax
0x1800a0fec  jnz     short loc_1800A1005
0x1800a0fee  mov     edx, 18Fh; void *
0x1800a0ff3  mov     rcx, [rbp+68h]; this
0x1800a0ff7  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1800a0ffe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a1003  mov     ebx, eax
0x1800a1005  lea     rcx, [rsp+160h+var_E8]; pvar
0x1800a100a  call    cs:__imp_PropVariantClear
0x1800a1011  nop     dword ptr [rax+rax+00h]
0x1800a1016  mov     eax, ebx
0x1800a1018  jmp     short loc_1800A101F
0x1800a101a  call    ?SaveOld@CZoneIdentifier@@AEAAJPEBGH@Z; CZoneIdentifier::SaveOld(ushort const *,int)
0x1800a101f  mov     rcx, [rbp+60h+var_40]
0x1800a1023  xor     rcx, rsp; StackCookie
0x1800a1026  call    __security_check_cookie
0x1800a102b  mov     rbx, [rsp+160h+arg_10]
0x1800a1033  add     rsp, 130h
0x1800a103a  pop     r15
0x1800a103c  pop     r14
0x1800a103e  pop     r13
  ... truncated ...
```
