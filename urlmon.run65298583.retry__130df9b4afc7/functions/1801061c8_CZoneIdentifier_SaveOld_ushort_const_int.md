# CZoneIdentifier::SaveOld(ushort const *,int)

- ea: `0x1801061c8`
- end: `0x1801065d3`
- name: `?SaveOld@CZoneIdentifier@@AEAAJPEBGH@Z`
- size: `1035`
- prototype: `__int64 __fastcall(LPCWSTR *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009a230`

## callees

- `0x180034300`
- `0x18006cfa4`
- `0x1800864e0`
- `0x1800877ec`
- `0x18008b74c`
- `0x18009a6a0`
- `0x18009e92c`
- `0x180105b2c`
- `0x180105bc0`
- `0x1801061c8`
- `0x180106a24`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180106353`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180106353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801063c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801064ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801063c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801064ea`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801063ee`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18010656c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801063ee`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18010656c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801063b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801063b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180106267`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180106291`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180106267`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180106291`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18010632a`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x18010632a`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1801064e0`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x1801064e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801063ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180106512`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180106541`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180106596`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801065a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801063ab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180106512`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180106541`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180106596`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801065a4`
- `PROPSYS!PropVariantToStringAlloc` at `0x1801064b9`
- `PROPSYS!PropVariantToStringAlloc` at `0x1801064b9`

## string_xrefs

- `0x1801062d0`: `LastWriterPackageFamilyName`
- `0x180106311`: `LastWriterPackageFamilyName`

## pseudocode

```c
__int64 __fastcall CZoneIdentifier::SaveOld(LPCWSTR *this, const unsigned __int16 *a2)
{
  int updated; // eax
  signed int LastError; // ebx
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
  DWORD nSize; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszOut; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpKeyName; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[3]; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT propvar[3]; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v34[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReturnedString[72]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  updated = CZoneIdentifier::_UpdateFile((CZoneIdentifier *)this, a2);
  LastError = updated;
  if ( updated >= 0 )
  {
    v6 = this[7];
    LOWORD(v34[0]) = 0;
    v7 = (*(__int64 (__fastcall **)(LPCWSTR, const WCHAR *, PROPVARIANT *))(*(_QWORD *)v6 + 24LL))(v6, L"ZoneId", v34);
    LastError = v7;
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      v9 = 196;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)v8,
        nSize);
      goto LABEL_51;
    }
    if ( !LOWORD(v34[0]) )
    {
      v10 = this[6];
      if ( *((_BYTE *)this + 64) )
      {
        if ( !DeleteFileW(v10) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xCB,
                        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
                        v11);
LABEL_51:
          PropVariantClear(v34);
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
    v29 = 0;
    v15 = (*(__int64 (__fastcall **)(LPCWSTR, unsigned int *))(*(_QWORD *)v14 + 40LL))(v14, &v29);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 225;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
        (const char *)v16,
        nSize);
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
      if ( (int)CZoneIdentifier::_SaveBatchedHelper((CZoneIdentifier *)this, v29) < 0 )
      {
        v23 = 0;
        if ( v29 )
        {
          while ( 1 )
          {
            lpKeyName = 0;
            LOWORD(propvar[0]) = 0;
            ppszOut = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &lpKeyName,
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
              &ppszOut,
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
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&ppszOut);
            PropVariantClear(propvar);
            wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpKeyName);
            if ( ++v23 >= v29 )
              goto LABEL_44;
          }
          wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&ppszOut);
          PropVariantClear(propvar);
          wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&lpKeyName);
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
                  (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
                  v21);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC1,
    (unsigned int)"onecoreuap\\inetcore\\urlmon\\zones\\zoneidentifier.cxx",
    (const char *)(unsigned int)updated,
    nSize);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1801061c8  mov     [rsp-8+arg_10], rbx
0x1801061cd  push    rbp
0x1801061ce  push    rsi
0x1801061cf  push    rdi
0x1801061d0  push    r12
0x1801061d2  push    r13
0x1801061d4  push    r14
0x1801061d6  push    r15
0x1801061d8  lea     rbp, [rsp-30h]
0x1801061dd  sub     rsp, 130h
0x1801061e4  mov     rax, cs:__security_cookie
0x1801061eb  xor     rax, rsp
0x1801061ee  mov     [rbp+60h+var_40], rax
0x1801061f2  mov     r12, rdx
0x1801061f5  mov     rdi, rcx
0x1801061f8  call    ?_UpdateFile@CZoneIdentifier@@AEAAJPEBG@Z; CZoneIdentifier::_UpdateFile(ushort const *)
0x1801061fd  xor     r13d, r13d
0x180106200  mov     ebx, eax
0x180106202  test    eax, eax
0x180106204  jns     short loc_180106223
0x180106206  mov     rcx, [rbp+68h]; this
0x18010620a  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180106211  mov     r9d, eax; char *
0x180106214  mov     edx, 0C1h; void *
0x180106219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010621e  jmp     loc_1801065AA
0x180106223  mov     rcx, [rdi+38h]
0x180106227  lea     r8, [rsp+160h+var_E8]
0x18010622c  mov     word ptr [rsp+160h+var_E8], r13w
0x180106232  lea     rdx, KeyName; "ZoneId"
0x180106239  mov     rax, [rcx]
0x18010623c  mov     rax, [rax+18h]
0x180106240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106245  mov     ebx, eax
0x180106247  test    eax, eax
0x180106249  jns     short loc_180106255
0x18010624b  mov     r9d, eax
0x18010624e  mov     edx, 0C4h
0x180106253  jmp     short loc_1801062AC
0x180106255  cmp     word ptr [rsp+160h+var_E8], r13w
0x18010625b  jnz     short loc_1801062C1
0x18010625d  mov     rcx, [rdi+30h]; lpFileName
0x180106261  cmp     [rdi+40h], r13b
0x180106265  jz      short loc_180106291
0x180106267  call    cs:__imp_DeleteFileW
0x18010626d  test    eax, eax
0x18010626f  jnz     loc_18010659C
0x180106275  mov     rcx, [rbp+68h]; this
0x180106279  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180106280  mov     edx, 0CBh; void *
0x180106285  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010628a  mov     ebx, eax
0x18010628c  jmp     loc_18010659F
0x180106291  call    cs:__imp_DeleteFileW
0x180106297  test    eax, eax
0x180106299  jnz     loc_18010659C
0x18010629f  mov     ebx, 80004005h
0x1801062a4  mov     edx, 0CFh; void *
0x1801062a9  mov     r9d, ebx; char *
0x1801062ac  mov     rcx, [rbp+68h]; this
0x1801062b0  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1801062b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801062bc  jmp     loc_18010659F
0x1801062c1  mov     rcx, [rdi+38h]
0x1801062c5  lea     r8, [rsp+160h+pvar]
0x1801062ca  mov     word ptr [rsp+160h+pvar], r13w
0x1801062d0  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x1801062d7  mov     rax, [rcx]
0x1801062da  mov     rax, [rax+18h]
0x1801062de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801062e3  test    eax, eax
0x1801062e5  js      loc_18010636E
0x1801062eb  cmp     word ptr [rsp+160h+pvar], r13w
0x1801062f1  jz      short loc_18010636E
0x1801062f3  xor     edx, edx; Val
0x1801062f5  lea     rcx, [rbp+60h+ReturnedString]; void *
0x1801062f9  mov     r8d, 82h; Size
0x1801062ff  call    memset_0
0x180106304  mov     rax, [rdi+30h]
0x180106308  lea     r9, [rbp+60h+ReturnedString]; lpReturnedString
0x18010630c  mov     [rsp+160h+lpFileName], rax; lpFileName
0x180106311  lea     rdx, aLastwriterpack; "LastWriterPackageFamilyName"
0x180106318  xor     r8d, r8d; lpDefault
0x18010631b  mov     [rsp+160h+nSize], 41h ; 'A'; nSize
0x180106323  lea     rcx, AppName; "ZoneTransfer"
0x18010632a  call    cs:__imp_GetPrivateProfileStringW
0x180106330  test    eax, eax
0x180106332  jz      short loc_18010635E
0x180106334  lea     rcx, [rsp+160h+pvar]; this
0x180106339  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18010633e  or      edx, 0FFFFFFFFh; cchCount1
0x180106341  mov     [rsp+160h+nSize], 1; int
0x180106349  mov     r9d, edx; cchCount2
0x18010634c  lea     rcx, [rbp+60h+ReturnedString]; lpString1
0x180106350  mov     r8, rax; lpString2
0x180106353  call    cs:__imp_CompareStringOrdinal
0x180106359  cmp     eax, 2
0x18010635c  jz      short loc_18010636E
0x18010635e  lea     rcx, [rdi+20h]; this
0x180106362  lea     rdx, aAppzoneid; "AppZoneId"
0x180106369  call    ?RemoveNamedValue@CZoneIdentifier@@UEAAJPEBG@Z; CZoneIdentifier::RemoveNamedValue(ushort const *)
0x18010636e  mov     rcx, [rdi+38h]
0x180106372  lea     rdx, [rsp+160h+var_130]
0x180106377  mov     [rsp+160h+var_130], r13d
0x18010637c  mov     rax, [rcx]
0x18010637f  mov     rax, [rax+28h]
0x180106383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106388  mov     ebx, eax
0x18010638a  test    eax, eax
0x18010638c  jns     short loc_1801063B6
0x18010638e  mov     r9d, eax; char *
0x180106391  mov     edx, 0E1h; void *
0x180106396  mov     rcx, [rbp+68h]; this
0x18010639a  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x1801063a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801063a6  lea     rcx, [rsp+160h+pvar]; pvar
0x1801063ab  call    cs:__imp_PropVariantClear
0x1801063b1  jmp     loc_18010659F
0x1801063b6  mov     rcx, r12; lpFileName
0x1801063b9  call    cs:__imp_GetFileAttributesW
0x1801063bf  mov     esi, eax
0x1801063c1  cmp     eax, 0FFFFFFFFh
0x1801063c4  jnz     short loc_1801063DD
0x1801063c6  call    cs:__imp_GetLastError
0x1801063cc  mov     ebx, eax
0x1801063ce  test    eax, eax
0x1801063d0  jle     short loc_1801063A6
0x1801063d2  movzx   ebx, ax
0x1801063d5  or      ebx, 80070000h
0x1801063db  jmp     short loc_1801063A6
0x1801063dd  mov     r14d, esi
0x1801063e0  and     r14d, 1
0x1801063e4  jz      short loc_180106411
0x1801063e6  mov     edx, esi
0x1801063e8  mov     rcx, r12; lpFileName
0x1801063eb  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1801063ee  call    cs:__imp_SetFileAttributesW
0x1801063f4  test    eax, eax
0x1801063f6  jnz     short loc_180106411
0x1801063f8  mov     edx, 0EEh; void *
0x1801063fd  mov     rcx, [rbp+68h]; this
0x180106401  lea     r8, aOnecoreuapInet_23; "onecoreuap\\inetcore\\urlmon\\zones\\zo"...
0x180106408  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010640d  mov     ebx, eax
0x18010640f  jmp     short loc_1801063A6
0x180106411  mov     edx, [rsp+160h+var_130]; unsigned int
0x180106415  mov     rcx, rdi; this
0x180106418  mov     ebx, r13d
0x18010641b  call    ?_SaveBatchedHelper@CZoneIdentifier@@AEAAJK@Z; CZoneIdentifier::_SaveBatchedHelper(ulong)
0x180106420  test    eax, eax
0x180106422  jns     loc_180106551
0x180106428  mov     r15d, r13d
0x18010642b  cmp     [rsp+160h+var_130], r13d
0x180106430  jbe     loc_180106551
0x180106436  xor     ecx, ecx
0x180106438  xor     edx, edx
0x18010643a  mov     [rsp+160h+lpKeyName], rcx
0x18010643f  mov     word ptr [rsp+160h+propvar], cx
0x180106444  mov     [rsp+160h+ppszOut], rcx
0x180106449  lea     rcx, [rsp+160h+lpKeyName]
0x18010644e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180106453  lea     r8, [rsp+160h+lpKeyName]; unsigned __int16 **
0x180106458  mov     edx, r15d; unsigned int
0x18010645b  lea     rcx, [rdi+20h]; this
0x18010645f  call    ?GetNameAt@CZoneIdentifier@@UEAAJKPEAPEAG@Z; CZoneIdentifier::GetNameAt(ulong,ushort * *)
0x180106464  mov     ebx, eax
0x180106466  test    eax, eax
0x180106468  js      loc_180106532
0x18010646e  mov     rcx, [rdi+38h]
0x180106472  lea     r8, [rsp+160h+propvar]
0x180106477  mov     rdx, [rsp+160h+lpKeyName]
0x18010647c  mov     rax, [rcx]
0x18010647f  mov     rax, [rax+18h]
0x180106483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106488  lea     rcx, [rsp+160h+ppszOut]
0x18010648d  mov     ebx, eax
0x18010648f  test    eax, eax
0x180106491  js      loc_180106537
0x180106497  xor     edx, edx
0x180106499  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010649e  xor     ebx, ebx
0x1801064a0  mov     r8d, ebx
0x1801064a3  mov     [rsp+160h+ppszOut], rbx
0x1801064a8  cmp     word ptr [rsp+160h+propvar], bx
0x1801064ad  jz      short loc_1801064D0
0x1801064af  lea     rdx, [rsp+160h+ppszOut]; ppszOut
0x1801064b4  lea     rcx, [rsp+160h+propvar]; propvar
0x1801064b9  call    cs:__imp_PropVariantToStringAlloc
0x1801064bf  cmp     eax, 80070490h
0x1801064c4  cmovnz  ebx, eax
0x1801064c7  test    ebx, ebx
0x1801064c9  js      short loc_180106532
0x1801064cb  mov     r8, [rsp+160h+ppszOut]; lpString
0x1801064d0  mov     r9, [rdi+30h]; lpFileName
0x1801064d4  lea     rcx, AppName; "ZoneTransfer"
0x1801064db  mov     rdx, [rsp+160h+lpKeyName]; lpKeyName
0x1801064e0  call    cs:__imp_WritePrivateProfileStringW
0x1801064e6  test    eax, eax
0x1801064e8  jnz     short loc_180106503
0x1801064ea  call    cs:__imp_GetLastError
0x1801064f0  mov     ebx, eax
0x1801064f2  test    eax, eax
0x1801064f4  jle     short loc_180106501
0x1801064f6  movzx   ebx, bx
0x1801064f9  or      ebx, 80070000h
0x1801064ff  test    ebx, ebx
0x180106501  js      short loc_180106532
0x180106503  lea     rcx, [rsp+160h+ppszOut]
0x180106508  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18010650d  lea     rcx, [rsp+160h+propvar]; pvar
0x180106512  call    cs:__imp_PropVariantClear
0x180106518  lea     rcx, [rsp+160h+lpKeyName]
0x18010651d  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180106522  inc     r15d
0x180106525  cmp     r15d, [rsp+160h+var_130]
0x18010652a  jb      loc_180106436
0x180106530  jmp     short loc_180106551
0x180106532  lea     rcx, [rsp+160h+ppszOut]
0x180106537  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18010653c  lea     rcx, [rsp+160h+propvar]; pvar
0x180106541  call    cs:__imp_PropVariantClear
0x180106547  lea     rcx, [rsp+160h+lpKeyName]
0x18010654c  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180106551  mov     edx, 4; unsigned int
0x180106556  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18010655d  call    ?IncrementCounter@CSharedMem@@QEAAHK@Z; CSharedMem::IncrementCounter(ulong)
0x180106562  test    r14d, r14d
0x180106565  jz      short loc_180106580
0x180106567  mov     edx, esi; dwFileAttributes
0x180106569  mov     rcx, r12; lpFileName
0x18010656c  call    cs:__imp_SetFileAttributesW
0x180106572  test    eax, eax
0x180106574  jnz     short loc_180106580
0x180106576  mov     edx, 119h
0x18010657b  jmp     loc_1801063FD
0x180106580  test    ebx, ebx
0x180106582  jns     short loc_180106591
0x180106584  mov     r9d, ebx
0x180106587  mov     edx, 11Ch
0x18010658c  jmp     loc_180106396
0x180106591  lea     rcx, [rsp+160h+pvar]; pvar
0x180106596  call    cs:__imp_PropVariantClear
0x18010659c  mov     ebx, r13d
0x18010659f  lea     rcx, [rsp+160h+var_E8]; pvar
0x1801065a4  call    cs:__imp_PropVariantClear
0x1801065aa  mov     eax, ebx
0x1801065ac  mov     rcx, [rbp+60h+var_40]
0x1801065b0  xor     rcx, rsp; StackCookie
0x1801065b3  call    __security_check_cookie
0x1801065b8  mov     rbx, [rsp+160h+arg_10]
0x1801065c0  add     rsp, 130h
0x1801065c7  pop     r15
0x1801065c9  pop     r14
0x1801065cb  pop     r13
0x1801065cd  pop     r12
0x1801065cf  pop     rdi
0x1801065d0  pop     rsi
0x1801065d1  pop     rbp
0x1801065d2  retn
```
