# CUserTileBroker::FixCorruptedStore(ushort const *)

- ea: `0x18004bf90`
- end: `0x18004c308`
- name: `?FixCorruptedStore@CUserTileBroker@@UEAAJPEBG@Z`
- size: `888`
- prototype: `__int64 __fastcall(CUserTileBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800093f0`
- `0x18000a46c`
- `0x18000c1b8`
- `0x18000c410`
- `0x180014b00`
- `0x18001b760`
- `0x18001c020`
- `0x180027888`
- `0x18003039c`
- `0x18004bf90`
- `0x18004c310`
- `0x18004c358`
- `0x180054130`
- `0x180054ad4`
- `0x1800b1214`
- `0x1800d134c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c11f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c11f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18004bfe2`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18004bfe2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004c0a5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004c0a5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004c2aa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004c2aa`

## string_xrefs

- `0x18004bffd`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c031`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c078`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c0fe`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c1a4`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c1df`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c224`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18004c258`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
__int64 __fastcall CUserTileBroker::FixCorruptedStore(CUserTileBroker *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // r14
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  char *FirstFileW; // rbx
  const char *v8; // r9
  int StringForUserTileType; // eax
  wchar_t *v10; // r13
  unsigned __int64 v11; // r12
  __int64 v12; // rsi
  int v13; // eax
  int CallerSIDString; // eax
  int UserTileRegKey; // eax
  int v16; // eax
  struct HWND__ *i; // rsi
  PWSTR pszPath; // [rsp+20h] [rbp-2D8h] BYREF
  wchar_t *SubStr; // [rsp+28h] [rbp-2D0h] BYREF
  HKEY phkResult; // [rsp+30h] [rbp-2C8h] BYREF
  LPCWSTR psz; // [rsp+38h] [rbp-2C0h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-2B8h] BYREF
  char v24[8]; // [rsp+48h] [rbp-2B0h] BYREF
  char *v25; // [rsp+50h] [rbp-2A8h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-2A0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pszPath,
    a2,
    -1);
  v2 = -1;
  do
    ++v2;
  while ( pszPath[v2] );
  v3 = v2 + 1;
  v26 = v2 + 1;
  v4 = PathCchRemoveFileSpec(pszPath, v2 + 1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v4,
      (int)pszPath);
  v5 = StringCchCatW(pszPath, v3, L"\\");
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v5,
      (int)pszPath);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpFileName,
    pszPath,
    v3);
  v6 = StringCchCatW((unsigned __int16 *)lpFileName, v3, L"*");
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v6,
      (int)pszPath);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
  v25 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      try
      {
        for ( i = &c_optimizedTileSizes; i != (struct HWND__ *)&dword_180135BA4; i += 3 )
        {
          SubStr = 0;
          StringForUserTileType = GetStringForUserTileType(*((unsigned int *)i + 1), &SubStr);
          if ( StringForUserTileType < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1BE,
              (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
              (const char *)(unsigned int)StringForUserTileType,
              (int)pszPath);
          v10 = SubStr;
          if ( wcsstr(FindFileData.cFileName, SubStr) )
          {
            SubStr = 0;
            v11 = v3;
            v12 = -1;
            do
              ++v12;
            while ( v10[v12] );
            do
            {
              wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v24,
                pszPath,
                v11);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                &SubStr,
                v24);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v24);
              v13 = StringCchCatW(SubStr, v11, FindFileData.cFileName);
              v11 += v12;
            }
            while ( v13 == -2147024774 );
            if ( v13 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1CE,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)v13,
                (int)pszPath);
            psz = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &psz,
              0);
            CallerSIDString = CImpersonateCaller::GetCallerSIDString((unsigned __int16 **)&psz);
            if ( CallerSIDString < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1D2,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)CallerSIDString,
                (int)pszPath);
            phkResult = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &phkResult,
              0);
            UserTileRegKey = GetUserTileRegKey(psz, 0x20006u, &phkResult);
            if ( UserTileRegKey < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1D4,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)UserTileRegKey,
                (int)pszPath);
            v16 = SHRegSetString(phkResult, 0, v10, SubStr);
            if ( v16 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x1D6,
                (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
                (const char *)(unsigned int)v16,
                (int)pszPath);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&psz);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SubStr);
            goto LABEL_35;
          }
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1DB,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
          v8);
        v3 = v26;
        FirstFileW = v25;
      }
LABEL_35:
      ;
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v25);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpFileName);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
  return 0;
}

```

## disassembly

```asm
0x18004bf90  push    rbx
0x18004bf92  push    rsi
0x18004bf93  push    rdi
0x18004bf94  push    r12
0x18004bf96  push    r13
0x18004bf98  push    r14
0x18004bf9a  sub     rsp, 2C8h
0x18004bfa1  mov     rax, cs:__security_cookie
0x18004bfa8  xor     rax, rsp
0x18004bfab  mov     [rsp+2F8h+var_48], rax
0x18004bfb3  xor     edi, edi
0x18004bfb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004bfb9  lea     rcx, [rsp+2F8h+pszPath]
0x18004bfbe  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004bfc3  nop
0x18004bfc4  mov     rcx, [rsp+2F8h+pszPath]; pszPath
0x18004bfc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bfcd  inc     rax
0x18004bfd0  cmp     [rcx+rax*2], di
0x18004bfd4  jnz     short loc_18004BFCD
0x18004bfd6  lea     r14, [rax+1]
0x18004bfda  mov     [rsp+2F8h+var_2A0], r14
0x18004bfdf  mov     rdx, r14; cchPath
0x18004bfe2  call    cs:__imp_PathCchRemoveFileSpec
0x18004bfe9  nop     dword ptr [rax+rax+00h]
0x18004bfee  mov     rcx, [rsp+2F8h]; this
0x18004bff6  test    eax, eax
0x18004bff8  jns     short loc_18004C00E
0x18004bffa  mov     r9d, eax; char *
0x18004bffd  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c004  mov     edx, 1AEh; void *
0x18004c009  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c00e  lea     r8, pszSrc; "\\"
0x18004c015  mov     rdx, r14; unsigned __int64
0x18004c018  mov     rcx, [rsp+2F8h+pszPath]; unsigned __int16 *
0x18004c01d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004c022  mov     rcx, [rsp+2F8h]; this
0x18004c02a  test    eax, eax
0x18004c02c  jns     short loc_18004C042
0x18004c02e  mov     r9d, eax; char *
0x18004c031  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c038  mov     edx, 1AFh; void *
0x18004c03d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c042  mov     r8, r14
0x18004c045  mov     rdx, [rsp+2F8h+pszPath]
0x18004c04a  lea     rcx, [rsp+2F8h+lpFileName]
0x18004c04f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004c054  nop
0x18004c055  lea     r8, asc_1801080BC; "*"
0x18004c05c  mov     rdx, r14; unsigned __int64
0x18004c05f  mov     rcx, [rsp+2F8h+lpFileName]; unsigned __int16 *
0x18004c064  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004c069  mov     rcx, [rsp+2F8h]; this
0x18004c071  test    eax, eax
0x18004c073  jns     short loc_18004C089
0x18004c075  mov     r9d, eax; char *
0x18004c078  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c07f  mov     edx, 1B1h; void *
0x18004c084  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c089  xor     edx, edx; Val
0x18004c08b  mov     r8d, 250h; Size
0x18004c091  lea     rcx, [rsp+2F8h+FindFileData]; void *
0x18004c096  call    memset_0
0x18004c09b  lea     rdx, [rsp+2F8h+FindFileData]; lpFindFileData
0x18004c0a0  mov     rcx, [rsp+2F8h+lpFileName]; lpFileName
0x18004c0a5  call    cs:__imp_FindFirstFileW
0x18004c0ac  nop     dword ptr [rax+rax+00h]
0x18004c0b1  mov     rbx, rax
0x18004c0b4  mov     [rsp+2F8h+var_2A8], rax
0x18004c0b9  dec     rax
0x18004c0bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004c0c0  ja      loc_18004C2BE
0x18004c0c6  lea     rsi, ?c_optimizedTileSizes@@3PAUUSERTILE_OPTIMIZED_SIZES@@A; USERTILE_OPTIMIZED_SIZES near * c_optimizedTileSizes
0x18004c0cd  lea     r12, dword_180135BA4
0x18004c0d4  cmp     rsi, r12
0x18004c0d7  jz      loc_18004C28B
0x18004c0dd  mov     [rsp+2F8h+SubStr], rdi
0x18004c0e2  lea     rdx, [rsp+2F8h+SubStr]
0x18004c0e7  mov     ecx, [rsi+4]
0x18004c0ea  call    ?GetStringForUserTileType@@YAJW4USER_TILE_TYPE@@PEAPEBG@Z; GetStringForUserTileType(USER_TILE_TYPE,ushort const * *)
0x18004c0ef  mov     rcx, [rsp+2F8h]; this
0x18004c0f7  test    eax, eax
0x18004c0f9  jns     short loc_18004C10F
0x18004c0fb  mov     r9d, eax; char *
0x18004c0fe  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c105  mov     edx, 1BEh; void *
0x18004c10a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c10f  mov     r13, [rsp+2F8h+SubStr]
0x18004c114  mov     rdx, r13; SubStr
0x18004c117  lea     rcx, [rsp+2F8h+FindFileData.cFileName]; Str
0x18004c11f  call    cs:__imp_wcsstr
0x18004c126  nop     dword ptr [rax+rax+00h]
0x18004c12b  test    rax, rax
0x18004c12e  jz      loc_18004C28D
0x18004c134  mov     [rsp+2F8h+SubStr], rdi
0x18004c139  mov     r12, r14
0x18004c13c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004c140  inc     rsi
0x18004c143  cmp     [r13+rsi*2+0], di
0x18004c149  jnz     short loc_18004C140
0x18004c14b  mov     r8, r12
0x18004c14e  mov     rdx, [rsp+2F8h+pszPath]
0x18004c153  lea     rcx, [rsp+2F8h+var_2B0]
0x18004c158  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004c15d  lea     rdx, [rsp+2F8h+var_2B0]
0x18004c162  lea     rcx, [rsp+2F8h+SubStr]
0x18004c167  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004c16c  lea     rcx, [rsp+2F8h+var_2B0]
0x18004c171  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004c176  lea     r8, [rsp+2F8h+FindFileData.cFileName]; unsigned __int16 *
0x18004c17e  mov     rdx, r12; unsigned __int64
0x18004c181  mov     rcx, [rsp+2F8h+SubStr]; unsigned __int16 *
0x18004c186  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004c18b  add     r12, rsi
0x18004c18e  cmp     eax, 8007007Ah
0x18004c193  jz      short loc_18004C14B
0x18004c195  mov     rcx, [rsp+2F8h]; this
0x18004c19d  test    eax, eax
0x18004c19f  jns     short loc_18004C1B5
0x18004c1a1  mov     r9d, eax; char *
0x18004c1a4  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c1ab  mov     edx, 1CEh; void *
0x18004c1b0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c1b5  mov     [rsp+2F8h+psz], rdi
0x18004c1ba  xor     edx, edx
0x18004c1bc  lea     rcx, [rsp+2F8h+psz]
0x18004c1c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004c1c6  lea     rcx, [rsp+2F8h+psz]; unsigned __int16 **
0x18004c1cb  call    ?GetCallerSIDString@CImpersonateCaller@@SAJPEAPEAG@Z; CImpersonateCaller::GetCallerSIDString(ushort * *)
0x18004c1d0  mov     rcx, [rsp+2F8h]; this
0x18004c1d8  test    eax, eax
0x18004c1da  jns     short loc_18004C1F0
0x18004c1dc  mov     r9d, eax; char *
0x18004c1df  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c1e6  mov     edx, 1D2h; void *
0x18004c1eb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c1f0  mov     [rsp+2F8h+phkResult], rdi
0x18004c1f5  xor     edx, edx
0x18004c1f7  lea     rcx, [rsp+2F8h+phkResult]
0x18004c1fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004c201  lea     r8, [rsp+2F8h+phkResult]; phkResult
0x18004c206  mov     edx, 20006h; samDesired
0x18004c20b  mov     rcx, [rsp+2F8h+psz]; psz
0x18004c210  call    GetUserTileRegKey
0x18004c215  mov     rcx, [rsp+2F8h]; this
0x18004c21d  test    eax, eax
0x18004c21f  jns     short loc_18004C235
0x18004c221  mov     r9d, eax; char *
0x18004c224  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c22b  mov     edx, 1D4h; void *
0x18004c230  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c235  mov     r9, [rsp+2F8h+SubStr]; unsigned __int16 *
0x18004c23a  mov     r8, r13; unsigned __int16 *
0x18004c23d  xor     edx, edx; unsigned __int16 *
0x18004c23f  mov     rcx, [rsp+2F8h+phkResult]; HKEY
0x18004c244  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004c249  mov     rcx, [rsp+2F8h]; this
0x18004c251  test    eax, eax
0x18004c253  jns     short loc_18004C26A
0x18004c255  mov     r9d, eax; char *
0x18004c258  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18004c25f  mov     edx, 1D6h; void *
0x18004c264  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004c26a  lea     rcx, [rsp+2F8h+phkResult]
0x18004c26f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004c274  nop
0x18004c275  lea     rcx, [rsp+2F8h+psz]
0x18004c27a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004c27f  nop
0x18004c280  lea     rcx, [rsp+2F8h+SubStr]
0x18004c285  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004c28a  nop
0x18004c28b  jmp     short loc_18004C2A2
0x18004c28d  add     rsi, 0Ch
0x18004c291  jmp     loc_18004C0D4
0x18004c296  xor     edi, edi
0x18004c298  mov     r14, [rsp+2F8h+var_2A0]
0x18004c29d  mov     rbx, [rsp+2F8h+var_2A8]
0x18004c2a2  lea     rdx, [rsp+2F8h+FindFileData]; lpFindFileData
0x18004c2a7  mov     rcx, rbx; hFindFile
0x18004c2aa  call    cs:__imp_FindNextFileW
0x18004c2b1  nop     dword ptr [rax+rax+00h]
0x18004c2b6  test    eax, eax
0x18004c2b8  jnz     loc_18004C0C6
0x18004c2be  lea     rcx, [rsp+2F8h+var_2A8]
0x18004c2c3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18004c2c8  nop
0x18004c2c9  lea     rcx, [rsp+2F8h+lpFileName]
0x18004c2ce  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004c2d3  nop
0x18004c2d4  lea     rcx, [rsp+2F8h+pszPath]
0x18004c2d9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004c2de  xor     eax, eax
0x18004c2e0  jmp     short loc_18004C2E6
0x18004c2e2  mov     eax, dword ptr [rsp+2F8h+pszPath]
0x18004c2e6  mov     rcx, [rsp+2F8h+var_48]
0x18004c2ee  xor     rcx, rsp; StackCookie
0x18004c2f1  call    __security_check_cookie
0x18004c2f6  add     rsp, 2C8h
0x18004c2fd  pop     r14
0x18004c2ff  pop     r13
0x18004c301  pop     r12
0x18004c303  pop     rdi
0x18004c304  pop     rsi
0x18004c305  pop     rbx
0x18004c306  retn
```
