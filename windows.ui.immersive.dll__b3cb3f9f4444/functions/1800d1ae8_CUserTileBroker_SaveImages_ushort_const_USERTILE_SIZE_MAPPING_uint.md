# CUserTileBroker::_SaveImages(ushort const *,USERTILE_SIZE_MAPPING *,uint)

- ea: `0x1800d1ae8`
- end: `0x1800d1dc1`
- name: `?_SaveImages@CUserTileBroker@@AEAAJPEBGPEAUUSERTILE_SIZE_MAPPING@@I@Z`
- size: `729`
- prototype: `__int64 __fastcall(CUserTileBroker *this, unsigned __int16 *, struct USERTILE_SIZE_MAPPING *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016c80`

## callees

- `0x18000a46c`
- `0x180014b00`
- `0x18001c020`
- `0x18002e93c`
- `0x18003039c`
- `0x1800343ec`
- `0x18003729c`
- `0x18003ff34`
- `0x18004c358`
- `0x180051f80`
- `0x180054130`
- `0x1800d0d10`
- `0x1800d195c`
- `0x1800d1a40`
- `0x1800d1ae8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1b53`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1b53`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800d1d20`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800d1d41`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800d1d5a`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800d1d20`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800d1d41`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1800d1d5a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d1c04`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d1c04`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800d1bdd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800d1bdd`

## string_xrefs

- `0x1800d1b7a`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800d1bba`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800d1c70`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800d1cb7`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x1800d1d05`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
__int64 __fastcall CUserTileBroker::_SaveImages(
        CUserTileBroker *this,
        unsigned __int16 *a2,
        struct USERTILE_SIZE_MAPPING *a3)
{
  int CallerSIDString; // eax
  int v6; // ebx
  __int64 v7; // rdx
  CUserTileBroker *v8; // rcx
  HRESULT TileFolder; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  struct IStream *v12; // r8
  CUserTileBroker *v13; // rcx
  int UserTileRegKey; // eax
  __int64 v15; // rdi
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // rsi
  int v18; // eax
  int v20; // [rsp+20h] [rbp-79h]
  HKEY hkey; // [rsp+40h] [rbp-59h] BYREF
  struct IShellItem *v22; // [rsp+48h] [rbp-51h] BYREF
  LPCWSTR psz; // [rsp+50h] [rbp-49h] BYREF
  GUID pguid; // [rsp+58h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  psz = 0;
  CallerSIDString = CImpersonateCaller::GetCallerSIDString((unsigned __int16 **)&psz);
  v6 = CallerSIDString;
  if ( a2 )
  {
    if ( CallerSIDString >= 0 )
      _o__wcsicmp(psz, a2);
  }
  else
  {
    if ( CallerSIDString < 0 )
    {
      v7 = 647;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
        (const char *)(unsigned int)CallerSIDString,
        v20);
      goto LABEL_35;
    }
    a2 = (unsigned __int16 *)psz;
  }
  CallerSIDString = EnsurePublicFolderandRegKey(a2);
  v6 = CallerSIDString;
  if ( CallerSIDString < 0 )
  {
    v7 = 661;
    goto LABEL_9;
  }
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  TileFolder = CUserTileBroker::_GetTileFolder(v8, a2, &v22);
  v6 = TileFolder;
  if ( TileFolder < 0 )
  {
    v10 = 664;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)TileFolder,
      v20);
    goto LABEL_34;
  }
  pguid = 0;
  TileFolder = CoCreateGuid(&pguid);
  v6 = TileFolder;
  if ( TileFolder < 0 )
  {
    v10 = 667;
    goto LABEL_12;
  }
  StringFromGUID2(&pguid, sz, 39);
  v6 = 0;
  v11 = 0;
  do
  {
    if ( v6 < 0 )
      break;
    v12 = (struct IStream *)*((_QWORD *)a3 + 12 * v11 + 2);
    if ( v12 )
      v6 = CUserTileBroker::_SaveImage(
             (struct USERTILE_SIZE_MAPPING *)((char *)a3 + 96 * v11 + 24),
             v22,
             v12,
             sz,
             (const unsigned __int16 *)a3 + 48 * v11 + 22,
             (const unsigned __int16 *)a3 + 48 * v11 + 12,
             (LPWSTR *)a3 + 12 * v11 + 11);
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (unsigned int)v11 < 0xE );
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v6,
      v20);
    goto LABEL_33;
  }
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  UserTileRegKey = GetUserTileRegKey(a2, 0x2011Fu, &hkey);
  v6 = UserTileRegKey;
  if ( UserTileRegKey < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)UserTileRegKey,
      v20);
    goto LABEL_32;
  }
  v15 = 0;
  while ( v6 >= 0 )
  {
    v16 = (const unsigned __int16 *)*((_QWORD *)a3 + 12 * v15 + 11);
    v17 = (const unsigned __int16 *)((char *)a3 + 96 * v15);
    if ( !v16 )
      goto LABEL_29;
    v18 = SHRegSetString(hkey, 0, v17 + 22, v16);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2B7,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
        (const char *)(unsigned int)v18,
        v20);
LABEL_29:
      SHDeleteValueW(hkey, 0, v17 + 22);
    }
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= 0xE )
      break;
  }
  SHDeleteValueW(hkey, 0, L"Image200");
  SHDeleteValueW(hkey, 0, L"Video200");
LABEL_32:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
LABEL_33:
  CUserTileBroker::_CleanUpFiles(v13, v22, v6 >= 0, sz);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
LABEL_35:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&psz);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d1ae8  mov     [rsp-8+arg_0], rbx
0x1800d1aed  push    rbp
0x1800d1aee  push    rsi
0x1800d1aef  push    rdi
0x1800d1af0  push    r12
0x1800d1af2  push    r14
0x1800d1af4  lea     rbp, [rsp-37h]
0x1800d1af9  sub     rsp, 0D0h
0x1800d1b00  mov     rax, cs:__security_cookie
0x1800d1b07  xor     rax, rsp
0x1800d1b0a  mov     [rbp+57h+var_30], rax
0x1800d1b0e  mov     r14, r8
0x1800d1b11  mov     rsi, rdx
0x1800d1b14  mov     [rbp+57h+psz], 0
0x1800d1b1c  lea     rcx, [rbp+57h+psz]; unsigned __int16 **
0x1800d1b20  call    ?GetCallerSIDString@CImpersonateCaller@@SAJPEAPEAG@Z; CImpersonateCaller::GetCallerSIDString(ushort * *)
0x1800d1b25  mov     ebx, eax
0x1800d1b27  mov     r12d, 1
0x1800d1b2d  test    rsi, rsi
0x1800d1b30  jnz     short loc_1800D1B46
0x1800d1b32  test    eax, eax
0x1800d1b34  jns     short loc_1800D1B3D
0x1800d1b36  mov     edx, 287h
0x1800d1b3b  jmp     short loc_1800D1B7A
0x1800d1b3d  mov     edi, r12d
0x1800d1b40  mov     rsi, [rbp+57h+psz]
0x1800d1b44  jmp     short loc_1800D1B65
0x1800d1b46  xor     edi, edi
0x1800d1b48  test    eax, eax
0x1800d1b4a  js      short loc_1800D1B65
0x1800d1b4c  mov     rdx, rsi
0x1800d1b4f  mov     rcx, [rbp+57h+psz]
0x1800d1b53  call    cs:__imp__o__wcsicmp
0x1800d1b5a  nop     dword ptr [rax+rax+00h]
0x1800d1b5f  test    eax, eax
0x1800d1b61  cmovz   edi, r12d
0x1800d1b65  mov     edx, edi
0x1800d1b67  mov     rcx, rsi; unsigned __int16 *
0x1800d1b6a  call    EnsurePublicFolderandRegKey
0x1800d1b6f  mov     ebx, eax
0x1800d1b71  test    eax, eax
0x1800d1b73  jns     short loc_1800D1B92
0x1800d1b75  mov     edx, 295h; void *
0x1800d1b7a  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800d1b81  mov     r9d, eax; char *
0x1800d1b84  mov     rcx, [rbp+5Fh]; this
0x1800d1b88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1b8d  jmp     loc_1800D1D92
0x1800d1b92  mov     [rbp+57h+var_A8], 0
0x1800d1b9a  lea     rcx, [rbp+57h+var_A8]
0x1800d1b9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1ba3  lea     r8, [rbp+57h+var_A8]; struct IShellItem **
0x1800d1ba7  mov     rdx, rsi; unsigned __int16 *
0x1800d1baa  call    ?_GetTileFolder@CUserTileBroker@@AEAAJPEBGPEAPEAUIShellItem@@@Z; CUserTileBroker::_GetTileFolder(ushort const *,IShellItem * *)
0x1800d1baf  mov     ebx, eax
0x1800d1bb1  test    eax, eax
0x1800d1bb3  jns     short loc_1800D1BD2
0x1800d1bb5  mov     edx, 298h; void *
0x1800d1bba  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800d1bc1  mov     r9d, eax; char *
0x1800d1bc4  mov     rcx, [rbp+5Fh]; this
0x1800d1bc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1bcd  jmp     loc_1800D1D88
0x1800d1bd2  xorps   xmm0, xmm0
0x1800d1bd5  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800d1bd9  lea     rcx, [rbp+57h+pguid]; pguid
0x1800d1bdd  call    cs:__imp_CoCreateGuid
0x1800d1be4  nop     dword ptr [rax+rax+00h]
0x1800d1be9  mov     ebx, eax
0x1800d1beb  test    eax, eax
0x1800d1bed  jns     short loc_1800D1BF6
0x1800d1bef  mov     edx, 29Bh
0x1800d1bf4  jmp     short loc_1800D1BBA
0x1800d1bf6  mov     r8d, 27h ; '''; cchMax
0x1800d1bfc  lea     rdx, [rbp+57h+sz]; lpsz
0x1800d1c00  lea     rcx, [rbp+57h+pguid]; rguid
0x1800d1c04  call    cs:__imp_StringFromGUID2
0x1800d1c0b  nop     dword ptr [rax+rax+00h]
0x1800d1c10  xor     ebx, ebx
0x1800d1c12  xor     edi, edi
0x1800d1c14  test    ebx, ebx
0x1800d1c16  js      short loc_1800D1C65
0x1800d1c18  lea     rdx, [rdi+rdi*2]
0x1800d1c1c  shl     rdx, 5
0x1800d1c20  mov     r8, [rdx+r14+10h]; struct IStream *
0x1800d1c25  test    r8, r8
0x1800d1c28  jz      short loc_1800D1C5D
0x1800d1c2a  lea     rax, [r14+58h]
0x1800d1c2e  add     rax, rdx
0x1800d1c31  lea     rcx, [r14+18h]
0x1800d1c35  add     rcx, rdx; this
0x1800d1c38  lea     r9, [r14+2Ch]
0x1800d1c3c  add     r9, rdx
0x1800d1c3f  mov     [rsp+0F0h+ppwsz], rax; ppwsz
0x1800d1c44  mov     [rsp+0F0h+var_C8], rcx; unsigned __int16 *
0x1800d1c49  mov     [rsp+0F0h+var_D0], r9; int
0x1800d1c4e  lea     r9, [rbp+57h+sz]; unsigned __int16 *
0x1800d1c52  mov     rdx, [rbp+57h+var_A8]; struct IShellItem *
0x1800d1c56  call    ?_SaveImage@CUserTileBroker@@AEAAJPEAUIShellItem@@PEAUIStream@@PEBG22PEAPEAG@Z; CUserTileBroker::_SaveImage(IShellItem *,IStream *,ushort const *,ushort const *,ushort const *,ushort * *)
0x1800d1c5b  mov     ebx, eax
0x1800d1c5d  add     edi, r12d
0x1800d1c60  cmp     edi, 0Eh
0x1800d1c63  jb      short loc_1800D1C14
0x1800d1c65  mov     rcx, [rbp+5Fh]; this
0x1800d1c69  test    ebx, ebx
0x1800d1c6b  jns     short loc_1800D1C86
0x1800d1c6d  mov     r9d, ebx; char *
0x1800d1c70  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800d1c77  mov     edx, 2ABh; void *
0x1800d1c7c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d1c81  jmp     loc_1800D1D70
0x1800d1c86  mov     [rbp+57h+hkey], 0
0x1800d1c8e  xor     edx, edx
0x1800d1c90  lea     rcx, [rbp+57h+hkey]
0x1800d1c94  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d1c99  lea     r8, [rbp+57h+hkey]; phkResult
0x1800d1c9d  mov     edx, 2011Fh; samDesired
0x1800d1ca2  mov     rcx, rsi; psz
0x1800d1ca5  call    GetUserTileRegKey
0x1800d1caa  mov     ebx, eax
0x1800d1cac  mov     rcx, [rbp+5Fh]; this
0x1800d1cb0  test    eax, eax
0x1800d1cb2  jns     short loc_1800D1CCD
0x1800d1cb4  mov     r9d, eax; char *
0x1800d1cb7  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800d1cbe  mov     edx, 2AFh; void *
0x1800d1cc3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d1cc8  jmp     loc_1800D1D67
0x1800d1ccd  xor     edi, edi
0x1800d1ccf  test    ebx, ebx
0x1800d1cd1  js      short loc_1800D1D34
0x1800d1cd3  lea     rcx, [rdi+rdi*2]
0x1800d1cd7  shl     rcx, 5
0x1800d1cdb  mov     r9, [rcx+r14+58h]; unsigned __int16 *
0x1800d1ce0  lea     rsi, [rcx+r14]
0x1800d1ce4  test    r9, r9
0x1800d1ce7  jz      short loc_1800D1D16
0x1800d1ce9  lea     r8, [rsi+2Ch]; unsigned __int16 *
0x1800d1ced  xor     edx, edx; unsigned __int16 *
0x1800d1cef  mov     rcx, [rbp+57h+hkey]; HKEY
0x1800d1cf3  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800d1cf8  mov     ebx, eax
0x1800d1cfa  mov     rcx, [rbp+5Fh]; this
0x1800d1cfe  test    eax, eax
0x1800d1d00  jns     short loc_1800D1D2C
0x1800d1d02  mov     r9d, eax; char *
0x1800d1d05  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800d1d0c  mov     edx, 2B7h; void *
0x1800d1d11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d1d16  lea     r8, [rsi+2Ch]; pszValue
0x1800d1d1a  xor     edx, edx; pszSubKey
0x1800d1d1c  mov     rcx, [rbp+57h+hkey]; hkey
0x1800d1d20  call    cs:__imp_SHDeleteValueW
0x1800d1d27  nop     dword ptr [rax+rax+00h]
0x1800d1d2c  add     edi, r12d
0x1800d1d2f  cmp     edi, 0Eh
0x1800d1d32  jb      short loc_1800D1CCF
0x1800d1d34  lea     r8, aImage200; "Image200"
0x1800d1d3b  xor     edx, edx; pszSubKey
0x1800d1d3d  mov     rcx, [rbp+57h+hkey]; hkey
0x1800d1d41  call    cs:__imp_SHDeleteValueW
0x1800d1d48  nop     dword ptr [rax+rax+00h]
0x1800d1d4d  lea     r8, aVideo200; "Video200"
0x1800d1d54  xor     edx, edx; pszSubKey
0x1800d1d56  mov     rcx, [rbp+57h+hkey]; hkey
0x1800d1d5a  call    cs:__imp_SHDeleteValueW
0x1800d1d61  nop     dword ptr [rax+rax+00h]
0x1800d1d66  nop
0x1800d1d67  lea     rcx, [rbp+57h+hkey]
0x1800d1d6b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d1d70  mov     r8d, ebx
0x1800d1d73  shr     r8d, 1Fh
0x1800d1d77  xor     r8b, r12b; bool
0x1800d1d7a  lea     r9, [rbp+57h+sz]; unsigned __int16 *
0x1800d1d7e  mov     rdx, [rbp+57h+var_A8]; struct IShellItem *
0x1800d1d82  call    ?_CleanUpFiles@CUserTileBroker@@AEAAXPEAUIShellItem@@_NPEBG@Z; CUserTileBroker::_CleanUpFiles(IShellItem *,bool,ushort const *)
0x1800d1d87  nop
0x1800d1d88  lea     rcx, [rbp+57h+var_A8]
0x1800d1d8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1d91  nop
0x1800d1d92  lea     rcx, [rbp+57h+psz]
0x1800d1d96  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800d1d9b  mov     eax, ebx
0x1800d1d9d  mov     rcx, [rbp+57h+var_30]
0x1800d1da1  xor     rcx, rsp; StackCookie
0x1800d1da4  call    __security_check_cookie
0x1800d1da9  mov     rbx, [rsp+0F0h+arg_0]
0x1800d1db1  add     rsp, 0D0h
0x1800d1db8  pop     r14
0x1800d1dba  pop     r12
0x1800d1dbc  pop     rdi
0x1800d1dbd  pop     rsi
0x1800d1dbe  pop     rbp
0x1800d1dbf  retn
```
