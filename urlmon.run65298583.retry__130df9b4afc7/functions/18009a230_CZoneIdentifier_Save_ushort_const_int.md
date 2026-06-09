# CZoneIdentifier::Save(ushort const *,int)

- ea: `0x18009a230`
- end: `0x18009a697`
- name: `?Save@CZoneIdentifier@@UEAAJPEBGH@Z`
- size: `1127`
- prototype: `int __fastcall(CZoneIdentifier *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180034300`
- `0x18006cfa4`
- `0x1800864e0`
- `0x1800877ec`
- `0x18008b74c`
- `0x18009a230`
- `0x18009a6a0`
- `0x18009e92c`
- `0x180105b2c`
- `0x180105bc0`
- `0x1801061c8`
- `0x180106a24`
- `0x180106d98`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009a417`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009a417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a48a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a48a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a5ae`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a320`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a4b2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a63b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a320`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a4b2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18009a63b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009a2e7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009a47d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009a2e7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18009a47d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009a33e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009a36e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009a33e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18009a36e`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18009a3ee`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18009a3ee`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18009a5a4`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18009a5a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a46f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a5d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a605`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a61a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a661`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a46f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a5d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a605`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a61a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009a661`
- `PROPSYS!PropVariantToStringAlloc` at `0x18009a57d`
- `PROPSYS!PropVariantToStringAlloc` at `0x18009a57d`

## string_xrefs

- `0x18009a394`: `LastWriterPackageFamilyName`
- `0x18009a3d5`: `LastWriterPackageFamilyName`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::GetImpl'::`2'::impl) )
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
0x18009a230  mov     [rsp-8+arg_10], rbx
0x18009a235  push    rbp
0x18009a236  push    rsi
0x18009a237  push    rdi
0x18009a238  push    r12
0x18009a23a  push    r13
0x18009a23c  push    r14
0x18009a23e  push    r15
0x18009a240  lea     rbp, [rsp-30h]
0x18009a245  sub     rsp, 130h
0x18009a24c  mov     rax, cs:__security_cookie
0x18009a253  xor     rax, rsp
0x18009a256  mov     [rbp+60h+var_40], rax
0x18009a25a  mov     r15, rdx
0x18009a25d  mov     rsi, rcx
0x18009a260  lea     r12, [rcx-28h]
0x18009a264  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::GetImpl(void)'::`2'::impl
0x18009a26b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FlushCacheOnMotWDeletion>::__private_IsEnabled(void)
0x18009a270  xor     r13d, r13d
0x18009a273  mov     rdx, r15; unsigned __int16 *
0x18009a276  mov     rcx, r12; this
0x18009a279  test    al, al
0x18009a27b  jz      loc_18009A66B
0x18009a281  mov     word ptr [rsp+160h+var_E8], r13w
0x18009a287  call    ?_UpdateFile@CZoneIdentifier@@AEAAJPEBG@Z; CZoneIdentifier::_UpdateFile(ushort const *)
0x18009a28c  mov     ebx, eax
0x18009a28e  test    eax, eax
0x18009a290  jns     short loc_18009A299
0x18009a292  mov     edx, 12Eh
0x18009a297  jmp     short loc_18009A2C0
0x18009a299  mov     rcx, [rsi+10h]
0x18009a29d  lea     r8, [rsp+160h+var_E8]
0x18009a2a2  lea     rdx, KeyName; "ZoneId"
0x18009a2a9  mov     rax, [rcx]
0x18009a2ac  mov     rax, [rax+18h]
0x18009a2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a2b5  mov     ebx, eax
0x18009a2b7  test    eax, eax
0x18009a2b9  jns     short loc_18009A2D8
0x18009a2bb  mov     edx, 12Fh; void *
0x18009a2c0  mov     rcx, [rbp+68h]; this
0x18009a2c4  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18009a2cb  mov     r9d, eax; char *
0x18009a2ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a2d3  jmp     loc_18009A65C
0x18009a2d8  cmp     word ptr [rsp+160h+var_E8], r13w
0x18009a2de  jnz     loc_18009A385
0x18009a2e4  mov     rcx, r15; lpFileName
0x18009a2e7  call    cs:__imp_GetFileAttributesW
0x18009a2ed  mov     edi, eax
0x18009a2ef  cmp     eax, 0FFFFFFFFh
0x18009a2f2  jnz     short loc_18009A30F
0x18009a2f4  call    cs:__imp_GetLastError
0x18009a2fa  test    eax, eax
0x18009a2fc  jle     loc_18009A65A
0x18009a302  movzx   eax, ax
0x18009a305  or      eax, 80070000h
0x18009a30a  jmp     loc_18009A65A
0x18009a30f  mov     r14d, eax
0x18009a312  and     r14d, 1
0x18009a316  jz      short loc_18009A334
0x18009a318  mov     edx, eax
0x18009a31a  mov     rcx, r15; lpFileName
0x18009a31d  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18009a320  call    cs:__imp_SetFileAttributesW
0x18009a326  test    eax, eax
0x18009a328  jnz     short loc_18009A334
0x18009a32a  mov     edx, 13Dh
0x18009a32f  jmp     loc_18009A64A
0x18009a334  mov     rcx, [rsi+8]; lpFileName
0x18009a338  cmp     [rsi+18h], r13b
0x18009a33c  jz      short loc_18009A36E
0x18009a33e  call    cs:__imp_DeleteFileW
0x18009a344  test    eax, eax
0x18009a346  jz      short loc_18009A350
0x18009a348  mov     ebx, r13d
0x18009a34b  jmp     loc_18009A620
0x18009a350  call    cs:__imp_GetLastError
0x18009a356  mov     ebx, eax
0x18009a358  test    eax, eax
0x18009a35a  jle     loc_18009A620
0x18009a360  movzx   ebx, ax
0x18009a363  or      ebx, 80070000h
0x18009a369  jmp     loc_18009A620
0x18009a36e  call    cs:__imp_DeleteFileW
0x18009a374  neg     eax
0x18009a376  sbb     ebx, ebx
0x18009a378  not     ebx
0x18009a37a  and     ebx, 80004005h
0x18009a380  jmp     loc_18009A620
0x18009a385  mov     rcx, [rsi+10h]
0x18009a389  lea     r8, [rsp+160h+pvar]
0x18009a38e  mov     word ptr [rsp+160h+pvar], r13w
0x18009a394  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x18009a39b  mov     rax, [rcx]
0x18009a39e  mov     rax, [rax+18h]
0x18009a3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a3a7  test    eax, eax
0x18009a3a9  js      loc_18009A432
0x18009a3af  cmp     word ptr [rsp+160h+pvar], r13w
0x18009a3b5  jz      short loc_18009A432
0x18009a3b7  xor     edx, edx; Val
0x18009a3b9  lea     rcx, [rbp+60h+ReturnedString]; void *
0x18009a3bd  mov     r8d, 82h; Size
0x18009a3c3  call    memset_0
0x18009a3c8  mov     rax, [rsi+8]
0x18009a3cc  lea     r9, [rbp+60h+ReturnedString]; lpReturnedString
0x18009a3d0  mov     [rsp+160h+lpFileName], rax; lpFileName
0x18009a3d5  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x18009a3dc  xor     r8d, r8d; lpDefault
0x18009a3df  mov     [rsp+160h+nSize], 41h ; 'A'; nSize
0x18009a3e7  lea     rcx, AppName; "ZoneTransfer"
0x18009a3ee  call    cs:__imp_GetPrivateProfileStringW
0x18009a3f4  test    eax, eax
0x18009a3f6  jz      short loc_18009A422
0x18009a3f8  lea     rcx, [rsp+160h+pvar]; this
0x18009a3fd  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18009a402  or      edx, 0FFFFFFFFh; cchCount1
0x18009a405  mov     [rsp+160h+nSize], 1; int
0x18009a40d  mov     r9d, edx; cchCount2
0x18009a410  lea     rcx, [rbp+60h+ReturnedString]; lpString1
0x18009a414  mov     r8, rax; lpString2
0x18009a417  call    cs:__imp_CompareStringOrdinal
0x18009a41d  cmp     eax, 2
0x18009a420  jz      short loc_18009A432
0x18009a422  lea     rcx, [rsi-8]; this
0x18009a426  lea     rdx, aAppzoneid; "AppZoneId"
0x18009a42d  call    ?RemoveNamedValue@CZoneIdentifier@@UEAAJPEBG@Z; CZoneIdentifier::RemoveNamedValue(ushort const *)
0x18009a432  mov     rcx, [rsi+10h]
0x18009a436  lea     rdx, [rsp+160h+var_130]
0x18009a43b  mov     [rsp+160h+var_130], r13d
0x18009a440  mov     rax, [rcx]
0x18009a443  mov     rax, [rax+28h]
0x18009a447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a44c  mov     ebx, eax
0x18009a44e  test    eax, eax
0x18009a450  jns     short loc_18009A47A
0x18009a452  mov     rcx, [rbp+68h]; this
0x18009a456  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18009a45d  mov     r9d, eax; char *
0x18009a460  mov     edx, 158h; void *
0x18009a465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a46a  lea     rcx, [rsp+160h+pvar]; pvar
0x18009a46f  call    cs:__imp_PropVariantClear
0x18009a475  jmp     loc_18009A65C
0x18009a47a  mov     rcx, r15; lpFileName
0x18009a47d  call    cs:__imp_GetFileAttributesW
0x18009a483  mov     edi, eax
0x18009a485  cmp     eax, 0FFFFFFFFh
0x18009a488  jnz     short loc_18009A4A1
0x18009a48a  call    cs:__imp_GetLastError
0x18009a490  mov     ebx, eax
0x18009a492  test    eax, eax
0x18009a494  jle     short loc_18009A46A
0x18009a496  movzx   ebx, ax
0x18009a499  or      ebx, 80070000h
0x18009a49f  jmp     short loc_18009A46A
0x18009a4a1  mov     r14d, eax
0x18009a4a4  and     r14d, 1
0x18009a4a8  jz      short loc_18009A4D5
0x18009a4aa  mov     edx, eax
0x18009a4ac  mov     rcx, r15; lpFileName
0x18009a4af  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18009a4b2  call    cs:__imp_SetFileAttributesW
0x18009a4b8  test    eax, eax
0x18009a4ba  jnz     short loc_18009A4D5
0x18009a4bc  mov     rcx, [rbp+68h]; this
0x18009a4c0  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18009a4c7  mov     edx, 165h; void *
0x18009a4cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009a4d1  mov     ebx, eax
0x18009a4d3  jmp     short loc_18009A46A
0x18009a4d5  mov     edx, [rsp+160h+var_130]; unsigned int
0x18009a4d9  mov     rcx, r12; this
0x18009a4dc  mov     ebx, r13d
0x18009a4df  call    ?_SaveBatchedHelper@CZoneIdentifier@@AEAAJK@Z; CZoneIdentifier::_SaveBatchedHelper(ulong)
0x18009a4e4  test    eax, eax
0x18009a4e6  jns     loc_18009A615
0x18009a4ec  mov     r12d, r13d
0x18009a4ef  cmp     [rsp+160h+var_130], r13d
0x18009a4f4  jbe     loc_18009A615
0x18009a4fa  xor     ecx, ecx
0x18009a4fc  xor     edx, edx
0x18009a4fe  mov     [rsp+160h+lpKeyName], rcx
0x18009a503  mov     word ptr [rsp+160h+propvar], cx
0x18009a508  mov     [rsp+160h+ppszOut], rcx
0x18009a50d  lea     rcx, [rsp+160h+lpKeyName]
0x18009a512  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009a517  lea     r8, [rsp+160h+lpKeyName]; unsigned __int16 **
0x18009a51c  mov     edx, r12d; unsigned int
0x18009a51f  lea     rcx, [rsi-8]; this
0x18009a523  call    ?GetNameAt@CZoneIdentifier@@UEAAJKPEAPEAG@Z; CZoneIdentifier::GetNameAt(ulong,ushort * *)
0x18009a528  mov     ebx, eax
0x18009a52a  test    eax, eax
0x18009a52c  js      loc_18009A5F6
0x18009a532  mov     rcx, [rsi+10h]
0x18009a536  lea     r8, [rsp+160h+propvar]
0x18009a53b  mov     rdx, [rsp+160h+lpKeyName]
0x18009a540  mov     rax, [rcx]
0x18009a543  mov     rax, [rax+18h]
0x18009a547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a54c  lea     rcx, [rsp+160h+ppszOut]
0x18009a551  mov     ebx, eax
0x18009a553  test    eax, eax
0x18009a555  js      loc_18009A5FB
0x18009a55b  xor     edx, edx
0x18009a55d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009a562  xor     ebx, ebx
0x18009a564  mov     r8d, ebx
0x18009a567  mov     [rsp+160h+ppszOut], rbx
0x18009a56c  cmp     word ptr [rsp+160h+propvar], bx
0x18009a571  jz      short loc_18009A594
0x18009a573  lea     rdx, [rsp+160h+ppszOut]; ppszOut
0x18009a578  lea     rcx, [rsp+160h+propvar]; propvar
0x18009a57d  call    cs:__imp_PropVariantToStringAlloc
0x18009a583  cmp     eax, 80070490h
0x18009a588  cmovnz  ebx, eax
0x18009a58b  test    ebx, ebx
0x18009a58d  js      short loc_18009A5F6
0x18009a58f  mov     r8, [rsp+160h+ppszOut]; lpString
0x18009a594  mov     r9, [rsi+8]; lpFileName
0x18009a598  lea     rcx, AppName; "ZoneTransfer"
0x18009a59f  mov     rdx, [rsp+160h+lpKeyName]; lpKeyName
0x18009a5a4  call    cs:__imp_WritePrivateProfileStringW
0x18009a5aa  test    eax, eax
0x18009a5ac  jnz     short loc_18009A5C7
0x18009a5ae  call    cs:__imp_GetLastError
0x18009a5b4  mov     ebx, eax
0x18009a5b6  test    eax, eax
0x18009a5b8  jle     short loc_18009A5C5
0x18009a5ba  movzx   ebx, bx
0x18009a5bd  or      ebx, 80070000h
0x18009a5c3  test    ebx, ebx
0x18009a5c5  js      short loc_18009A5F6
0x18009a5c7  lea     rcx, [rsp+160h+ppszOut]
0x18009a5cc  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18009a5d1  lea     rcx, [rsp+160h+propvar]; pvar
0x18009a5d6  call    cs:__imp_PropVariantClear
0x18009a5dc  lea     rcx, [rsp+160h+lpKeyName]
0x18009a5e1  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18009a5e6  inc     r12d
0x18009a5e9  cmp     r12d, [rsp+160h+var_130]
0x18009a5ee  jb      loc_18009A4FA
0x18009a5f4  jmp     short loc_18009A615
0x18009a5f6  lea     rcx, [rsp+160h+ppszOut]
0x18009a5fb  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18009a600  lea     rcx, [rsp+160h+propvar]; pvar
0x18009a605  call    cs:__imp_PropVariantClear
0x18009a60b  lea     rcx, [rsp+160h+lpKeyName]
0x18009a610  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18009a615  lea     rcx, [rsp+160h+pvar]; pvar
0x18009a61a  call    cs:__imp_PropVariantClear
0x18009a620  mov     edx, 4; unsigned int
0x18009a625  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18009a62c  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x18009a631  test    r14d, r14d
0x18009a634  jz      short loc_18009A65C
0x18009a636  mov     edx, edi; dwFileAttributes
0x18009a638  mov     rcx, r15; lpFileName
0x18009a63b  call    cs:__imp_SetFileAttributesW
0x18009a641  test    eax, eax
0x18009a643  jnz     short loc_18009A65C
0x18009a645  mov     edx, 18Fh; void *
0x18009a64a  mov     rcx, [rbp+68h]; this
0x18009a64e  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18009a655  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009a65a  mov     ebx, eax
0x18009a65c  lea     rcx, [rsp+160h+var_E8]; pvar
0x18009a661  call    cs:__imp_PropVariantClear
0x18009a667  mov     eax, ebx
0x18009a669  jmp     short loc_18009A670
0x18009a66b  call    ?SaveOld@CZoneIdentifier@@AEAAJPEBGH@Z; CZoneIdentifier::SaveOld(ushort const *,int)
0x18009a670  mov     rcx, [rbp+60h+var_40]
0x18009a674  xor     rcx, rsp; StackCookie
0x18009a677  call    __security_check_cookie
0x18009a67c  mov     rbx, [rsp+160h+arg_10]
0x18009a684  add     rsp, 130h
0x18009a68b  pop     r15
0x18009a68d  pop     r14
0x18009a68f  pop     r13
0x18009a691  pop     r12
0x18009a693  pop     rdi
0x18009a694  pop     rsi
0x18009a695  pop     rbp
0x18009a696  retn
```
