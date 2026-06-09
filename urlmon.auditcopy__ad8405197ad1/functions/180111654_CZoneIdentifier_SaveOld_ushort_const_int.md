# CZoneIdentifier::SaveOld(ushort const *,int)

- ea: `0x180111654`
- end: `0x180111ac7`
- name: `?SaveOld@CZoneIdentifier@@AEAAJPEBGH@Z`
- size: `1139`
- prototype: `__int64 __fastcall(LPCWSTR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a0b60`

## callees

- `0x180012c50`
- `0x180032088`
- `0x18003bf28`
- `0x18008cf94`
- `0x1800912b4`
- `0x1800a11c0`
- `0x1800a5760`
- `0x180110f88`
- `0x180111030`
- `0x180111654`
- `0x180111f34`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801117f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801117f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011187a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801119b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011187a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801119b9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801118a8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180111a4d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801118a8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180111a4d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180111867`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180111867`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801116f3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180111723`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801116f3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180111723`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801117c6`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1801117c6`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1801119a9`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1801119a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111853`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801119e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111a1c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111a7d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111a91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111853`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801119e7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111a1c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111a7d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180111a91`
- `PROPSYS!PropVariantToStringAlloc` at `0x18011197c`
- `PROPSYS!PropVariantToStringAlloc` at `0x18011197c`

## string_xrefs

- `0x180111768`: `LastWriterPackageFamilyName`
- `0x1801117ad`: `LastWriterPackageFamilyName`

## pseudocode

```c
__int64 __fastcall CZoneIdentifier::SaveOld(LPCWSTR *this, const unsigned __int16 *a2)
{
  int updated; // eax
  int LastError; // ebx
  LPCWSTR v6; // rcx
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  const WCHAR *v10; // rcx
  const char *v11; // r9
  LPCWSTR v12; // rcx
  const WCHAR *String; // rax
  LPCWSTR v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  DWORD FileAttributesW; // eax
  DWORD v19; // esi
  signed int v20; // eax
  const char *v21; // r9
  __int64 v22; // rdx
  unsigned int v23; // r15d
  const WCHAR *v24; // r8
  HRESULT v25; // eax
  bool v26; // sf
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpKeyName; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[3]; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT propvar[3]; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v33[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReturnedString[72]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  updated = CZoneIdentifier::_UpdateFile((CZoneIdentifier *)this, a2);
  LastError = updated;
  if ( updated >= 0 )
  {
    v6 = this[7];
    LOWORD(v33[0]) = 0;
    v7 = (*(__int64 (__fastcall **)(LPCWSTR, const WCHAR *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(v6, L"ZoneId", v33);
    LastError = v7;
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      v9 = 196;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)v8);
      goto LABEL_51;
    }
    if ( !LOWORD(v33[0]) )
    {
      v10 = this[6];
      if ( *((_BYTE *)this + 64) )
      {
        if ( !DeleteFileW(v10) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xCB,
                        (__int64)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
                        v11);
LABEL_51:
          PropVariantClear(v33);
          return (unsigned int)LastError;
        }
      }
      else if ( !DeleteFileW(v10) )
      {
        LastError = -2147467259;
        v9 = 207;
        v8 = 2147500037LL;
        goto LABEL_11;
      }
LABEL_50:
      LastError = 0;
      goto LABEL_51;
    }
    v12 = this[7];
    LOWORD(pvar[0]) = 0;
    if ( (*(int (__fastcall **)(LPCWSTR, const WCHAR *, PROPVARIANT *))(*(_QWORD *)v12 + 24LL))(
           v12,
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
                this[6])
          || (String = CPropVariant::GetString((CPropVariant *)pvar),
              CompareStringOrdinal(ReturnedString, -1, String, -1, 1) != 2) )
        {
          CZoneIdentifier::RemoveNamedValue((CZoneIdentifier *)(this + 4), L"AppZoneId");
        }
      }
    }
    v14 = this[7];
    v28 = 0;
    v15 = (*(__int64 (__fastcall **)(LPCWSTR, unsigned int *))(*(_QWORD *)v14 + 40LL))(v14, &v28);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 225;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)v16);
LABEL_20:
      PropVariantClear(pvar);
      goto LABEL_51;
    }
    FileAttributesW = GetFileAttributesW(a2);
    v19 = FileAttributesW;
    if ( FileAttributesW == -1 )
    {
      v20 = GetLastError();
      LastError = v20;
      if ( v20 > 0 )
        LastError = (unsigned __int16)v20 | 0x80070000;
      goto LABEL_20;
    }
    if ( (FileAttributesW & 1) == 0 || SetFileAttributesW(a2, FileAttributesW & 0xFFFFFFFE) )
    {
      LastError = 0;
      if ( (int)CZoneIdentifier::_SaveBatchedHelper(this, v28) < 0 )
      {
        v23 = 0;
        if ( v28 )
        {
          while ( 1 )
          {
            lpKeyName = 0;
            LOWORD(propvar[0]) = 0;
            ppszOut = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              (void **)&lpKeyName,
              0);
            LastError = CZoneIdentifier::GetNameAt((CZoneIdentifier *)(this + 4), v23, (unsigned __int16 **)&lpKeyName);
            if ( LastError < 0 )
              break;
            LastError = (*(__int64 (__fastcall **)(LPCWSTR, LPCWSTR, PROPVARIANT *))(*(_QWORD *)this[7] + 24LL))(
                          this[7],
                          lpKeyName,
                          propvar);
            if ( LastError < 0 )
              break;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              (void **)&ppszOut,
              0);
            LastError = 0;
            v24 = 0;
            ppszOut = 0;
            if ( LOWORD(propvar[0]) )
            {
              v25 = PropVariantToStringAlloc(propvar, &ppszOut);
              if ( v25 != -2147023728 )
                LastError = v25;
              if ( LastError < 0 )
                break;
              v24 = ppszOut;
            }
            if ( !WritePrivateProfileStringW(L"ZoneTransfer", lpKeyName, v24, this[6]) )
            {
              LastError = GetLastError();
              v26 = LastError < 0;
              if ( LastError > 0 )
              {
                LastError = (unsigned __int16)LastError | 0x80070000;
                v26 = LastError < 0;
              }
              if ( v26 )
                break;
            }
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>((void **)&ppszOut);
            PropVariantClear(propvar);
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>((void **)&lpKeyName);
            if ( ++v23 >= v28 )
              goto LABEL_44;
          }
          wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>((void **)&ppszOut);
          PropVariantClear(propvar);
          wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>((void **)&lpKeyName);
        }
      }
LABEL_44:
      CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u);
      if ( (v19 & 1) == 0 || SetFileAttributesW(a2, v19) )
      {
        if ( LastError >= 0 )
        {
          PropVariantClear(pvar);
          goto LABEL_50;
        }
        v16 = (unsigned int)LastError;
        v17 = 284;
        goto LABEL_19;
      }
      v22 = 281;
    }
    else
    {
      v22 = 238;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v22,
                  (__int64)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
                  v21);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC1,
    (int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
    (const char *)(unsigned int)updated);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180111654  mov     [rsp-8+arg_10], rbx
0x180111659  push    rbp
0x18011165a  push    rsi
0x18011165b  push    rdi
0x18011165c  push    r12
0x18011165e  push    r13
0x180111660  push    r14
0x180111662  push    r15
0x180111664  lea     rbp, [rsp-30h]
0x180111669  sub     rsp, 130h
0x180111670  mov     rax, cs:__security_cookie
0x180111677  xor     rax, rsp
0x18011167a  mov     [rbp+60h+var_40], rax
0x18011167e  mov     r12, rdx
0x180111681  mov     rdi, rcx
0x180111684  call    ?_UpdateFile@CZoneIdentifier@@AEAAJPEBG@Z; CZoneIdentifier::_UpdateFile(ushort const *)
0x180111689  xor     r13d, r13d
0x18011168c  mov     ebx, eax
0x18011168e  test    eax, eax
0x180111690  jns     short loc_1801116AF
0x180111692  mov     rcx, [rbp+68h]; this
0x180111696  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18011169d  mov     r9d, eax; char *
0x1801116a0  mov     edx, 0C1h; void *
0x1801116a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801116aa  jmp     loc_180111A9D
0x1801116af  mov     rcx, [rdi+38h]
0x1801116b3  lea     r8, [rsp+160h+var_E8]
0x1801116b8  mov     word ptr [rsp+160h+var_E8], r13w
0x1801116be  lea     rdx, KeyName; "ZoneId"
0x1801116c5  mov     rax, [rcx]
0x1801116c8  mov     rax, [rax+18h]
0x1801116cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801116d1  mov     ebx, eax
0x1801116d3  test    eax, eax
0x1801116d5  jns     short loc_1801116E1
0x1801116d7  mov     r9d, eax
0x1801116da  mov     edx, 0C4h
0x1801116df  jmp     short loc_180111744
0x1801116e1  cmp     word ptr [rsp+160h+var_E8], r13w
0x1801116e7  jnz     short loc_180111759
0x1801116e9  mov     rcx, [rdi+30h]; lpFileName
0x1801116ed  cmp     [rdi+40h], r13b
0x1801116f1  jz      short loc_180111723
0x1801116f3  call    cs:__imp_DeleteFileW
0x1801116fa  nop     dword ptr [rax+rax+00h]
0x1801116ff  test    eax, eax
0x180111701  jnz     loc_180111A89
0x180111707  mov     rcx, [rbp+68h]; this
0x18011170b  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180111712  mov     edx, 0CBh; void *
0x180111717  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011171c  mov     ebx, eax
0x18011171e  jmp     loc_180111A8C
0x180111723  call    cs:__imp_DeleteFileW
0x18011172a  nop     dword ptr [rax+rax+00h]
0x18011172f  test    eax, eax
0x180111731  jnz     loc_180111A89
0x180111737  mov     ebx, 80004005h
0x18011173c  mov     edx, 0CFh; void *
0x180111741  mov     r9d, ebx; char *
0x180111744  mov     rcx, [rbp+68h]; this
0x180111748  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x18011174f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180111754  jmp     loc_180111A8C
0x180111759  mov     rcx, [rdi+38h]
0x18011175d  lea     r8, [rsp+160h+pvar]
0x180111762  mov     word ptr [rsp+160h+pvar], r13w
0x180111768  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x18011176f  mov     rax, [rcx]
0x180111772  mov     rax, [rax+18h]
0x180111776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011177b  test    eax, eax
0x18011177d  js      loc_180111816
0x180111783  cmp     word ptr [rsp+160h+pvar], r13w
0x180111789  jz      loc_180111816
0x18011178f  xor     edx, edx; Val
0x180111791  lea     rcx, [rbp+60h+ReturnedString]; void *
0x180111795  mov     r8d, 82h; Size
0x18011179b  call    memset_0
0x1801117a0  mov     rax, [rdi+30h]
0x1801117a4  lea     r9, [rbp+60h+ReturnedString]; lpReturnedString
0x1801117a8  mov     [rsp+160h+lpFileName], rax; lpFileName
0x1801117ad  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x1801117b4  xor     r8d, r8d; lpDefault
0x1801117b7  mov     [rsp+160h+nSize], 41h ; 'A'; nSize
0x1801117bf  lea     rcx, AppName; "ZoneTransfer"
0x1801117c6  call    cs:__imp_GetPrivateProfileStringW
0x1801117cd  nop     dword ptr [rax+rax+00h]
0x1801117d2  test    eax, eax
0x1801117d4  jz      short loc_180111806
0x1801117d6  lea     rcx, [rsp+160h+pvar]; this
0x1801117db  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x1801117e0  or      edx, 0FFFFFFFFh; cchCount1
0x1801117e3  mov     [rsp+160h+nSize], 1; int
0x1801117eb  mov     r9d, edx; cchCount2
0x1801117ee  lea     rcx, [rbp+60h+ReturnedString]; lpString1
0x1801117f2  mov     r8, rax; lpString2
0x1801117f5  call    cs:__imp_CompareStringOrdinal
0x1801117fc  nop     dword ptr [rax+rax+00h]
0x180111801  cmp     eax, 2
0x180111804  jz      short loc_180111816
0x180111806  lea     rcx, [rdi+20h]; this
0x18011180a  lea     rdx, aAppzoneid; "AppZoneId"
0x180111811  call    ?RemoveNamedValue@CZoneIdentifier@@UEAAJPEBG@Z; CZoneIdentifier::RemoveNamedValue(ushort const *)
0x180111816  mov     rcx, [rdi+38h]
0x18011181a  lea     rdx, [rsp+160h+var_130]
0x18011181f  mov     [rsp+160h+var_130], r13d
0x180111824  mov     rax, [rcx]
0x180111827  mov     rax, [rax+28h]
0x18011182b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180111830  mov     ebx, eax
0x180111832  test    eax, eax
0x180111834  jns     short loc_180111864
0x180111836  mov     r9d, eax; char *
0x180111839  mov     edx, 0E1h; void *
0x18011183e  mov     rcx, [rbp+68h]; this
0x180111842  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180111849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011184e  lea     rcx, [rsp+160h+pvar]; pvar
0x180111853  call    cs:__imp_PropVariantClear
0x18011185a  nop     dword ptr [rax+rax+00h]
0x18011185f  jmp     loc_180111A8C
0x180111864  mov     rcx, r12; lpFileName
0x180111867  call    cs:__imp_GetFileAttributesW
0x18011186e  nop     dword ptr [rax+rax+00h]
0x180111873  mov     esi, eax
0x180111875  cmp     eax, 0FFFFFFFFh
0x180111878  jnz     short loc_180111897
0x18011187a  call    cs:__imp_GetLastError
0x180111881  nop     dword ptr [rax+rax+00h]
0x180111886  mov     ebx, eax
0x180111888  test    eax, eax
0x18011188a  jle     short loc_18011184E
0x18011188c  movzx   ebx, ax
0x18011188f  or      ebx, 80070000h
0x180111895  jmp     short loc_18011184E
0x180111897  mov     r14d, esi
0x18011189a  and     r14d, 1
0x18011189e  jz      short loc_1801118D4
0x1801118a0  mov     edx, esi
0x1801118a2  mov     rcx, r12; lpFileName
0x1801118a5  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1801118a8  call    cs:__imp_SetFileAttributesW
0x1801118af  nop     dword ptr [rax+rax+00h]
0x1801118b4  test    eax, eax
0x1801118b6  jnz     short loc_1801118D4
0x1801118b8  mov     edx, 0EEh; void *
0x1801118bd  mov     rcx, [rbp+68h]; this
0x1801118c1  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1801118c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801118cd  mov     ebx, eax
0x1801118cf  jmp     loc_18011184E
0x1801118d4  mov     edx, [rsp+160h+var_130]; unsigned int
0x1801118d8  mov     rcx, rdi; this
0x1801118db  mov     ebx, r13d
0x1801118de  call    ?_SaveBatchedHelper@CZoneIdentifier@@AEAAJK@Z; CZoneIdentifier::_SaveBatchedHelper(ulong)
0x1801118e3  test    eax, eax
0x1801118e5  jns     loc_180111A32
0x1801118eb  mov     r15d, r13d
0x1801118ee  cmp     [rsp+160h+var_130], r13d
0x1801118f3  jbe     loc_180111A32
0x1801118f9  xor     ecx, ecx
0x1801118fb  xor     edx, edx
0x1801118fd  mov     [rsp+160h+lpKeyName], rcx
0x180111902  mov     word ptr [rsp+160h+propvar], cx
0x180111907  mov     [rsp+160h+ppszOut], rcx
0x18011190c  lea     rcx, [rsp+160h+lpKeyName]
0x180111911  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180111916  lea     r8, [rsp+160h+lpKeyName]; unsigned __int16 **
0x18011191b  mov     edx, r15d; unsigned int
0x18011191e  lea     rcx, [rdi+20h]; this
0x180111922  call    ?GetNameAt@CZoneIdentifier@@UEAAJKPEAPEAG@Z; CZoneIdentifier::GetNameAt(ulong,ushort * *)
0x180111927  mov     ebx, eax
0x180111929  test    eax, eax
0x18011192b  js      loc_180111A0D
0x180111931  mov     rcx, [rdi+38h]
0x180111935  lea     r8, [rsp+160h+propvar]
0x18011193a  mov     rdx, [rsp+160h+lpKeyName]
0x18011193f  mov     rax, [rcx]
0x180111942  mov     rax, [rax+18h]
0x180111946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011194b  lea     rcx, [rsp+160h+ppszOut]
0x180111950  mov     ebx, eax
0x180111952  test    eax, eax
0x180111954  js      loc_180111A12
0x18011195a  xor     edx, edx
0x18011195c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180111961  xor     ebx, ebx
0x180111963  mov     r8d, ebx
0x180111966  mov     [rsp+160h+ppszOut], rbx
0x18011196b  cmp     word ptr [rsp+160h+propvar], bx
0x180111970  jz      short loc_180111999
0x180111972  lea     rdx, [rsp+160h+ppszOut]; ppszOut
0x180111977  lea     rcx, [rsp+160h+propvar]; propvar
0x18011197c  call    cs:__imp_PropVariantToStringAlloc
0x180111983  nop     dword ptr [rax+rax+00h]
0x180111988  cmp     eax, 80070490h
0x18011198d  cmovnz  ebx, eax
0x180111990  test    ebx, ebx
0x180111992  js      short loc_180111A0D
0x180111994  mov     r8, [rsp+160h+ppszOut]; lpString
0x180111999  mov     r9, [rdi+30h]; lpFileName
0x18011199d  lea     rcx, AppName; "ZoneTransfer"
0x1801119a4  mov     rdx, [rsp+160h+lpKeyName]; lpKeyName
0x1801119a9  call    cs:__imp_WritePrivateProfileStringW
0x1801119b0  nop     dword ptr [rax+rax+00h]
0x1801119b5  test    eax, eax
0x1801119b7  jnz     short loc_1801119D8
0x1801119b9  call    cs:__imp_GetLastError
0x1801119c0  nop     dword ptr [rax+rax+00h]
0x1801119c5  mov     ebx, eax
0x1801119c7  test    eax, eax
0x1801119c9  jle     short loc_1801119D6
0x1801119cb  movzx   ebx, bx
0x1801119ce  or      ebx, 80070000h
0x1801119d4  test    ebx, ebx
0x1801119d6  js      short loc_180111A0D
0x1801119d8  lea     rcx, [rsp+160h+ppszOut]
0x1801119dd  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1801119e2  lea     rcx, [rsp+160h+propvar]; pvar
0x1801119e7  call    cs:__imp_PropVariantClear
0x1801119ee  nop     dword ptr [rax+rax+00h]
0x1801119f3  lea     rcx, [rsp+160h+lpKeyName]
0x1801119f8  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x1801119fd  inc     r15d
0x180111a00  cmp     r15d, [rsp+160h+var_130]
0x180111a05  jb      loc_1801118F9
0x180111a0b  jmp     short loc_180111A32
0x180111a0d  lea     rcx, [rsp+160h+ppszOut]
0x180111a12  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180111a17  lea     rcx, [rsp+160h+propvar]; pvar
0x180111a1c  call    cs:__imp_PropVariantClear
0x180111a23  nop     dword ptr [rax+rax+00h]
0x180111a28  lea     rcx, [rsp+160h+lpKeyName]
0x180111a2d  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180111a32  mov     edx, 4; unsigned int
0x180111a37  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x180111a3e  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x180111a43  test    r14d, r14d
0x180111a46  jz      short loc_180111A67
0x180111a48  mov     edx, esi; dwFileAttributes
0x180111a4a  mov     rcx, r12; lpFileName
0x180111a4d  call    cs:__imp_SetFileAttributesW
0x180111a54  nop     dword ptr [rax+rax+00h]
0x180111a59  test    eax, eax
0x180111a5b  jnz     short loc_180111A67
0x180111a5d  mov     edx, 119h
0x180111a62  jmp     loc_1801118BD
0x180111a67  test    ebx, ebx
0x180111a69  jns     short loc_180111A78
0x180111a6b  mov     r9d, ebx
0x180111a6e  mov     edx, 11Ch
0x180111a73  jmp     loc_18011183E
0x180111a78  lea     rcx, [rsp+160h+pvar]; pvar
0x180111a7d  call    cs:__imp_PropVariantClear
0x180111a84  nop     dword ptr [rax+rax+00h]
0x180111a89  mov     ebx, r13d
0x180111a8c  lea     rcx, [rsp+160h+var_E8]; pvar
0x180111a91  call    cs:__imp_PropVariantClear
0x180111a98  nop     dword ptr [rax+rax+00h]
0x180111a9d  mov     eax, ebx
0x180111a9f  mov     rcx, [rbp+60h+var_40]
0x180111aa3  xor     rcx, rsp; StackCookie
0x180111aa6  call    __security_check_cookie
0x180111aab  mov     rbx, [rsp+160h+arg_10]
0x180111ab3  add     rsp, 130h
0x180111aba  pop     r15
0x180111abc  pop     r14
0x180111abe  pop     r13
0x180111ac0  pop     r12
0x180111ac2  pop     rdi
0x180111ac3  pop     rsi
0x180111ac4  pop     rbp
0x180111ac5  retn
```
