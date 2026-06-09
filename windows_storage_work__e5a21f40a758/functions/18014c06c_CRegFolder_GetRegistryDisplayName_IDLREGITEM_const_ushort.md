# CRegFolder::_GetRegistryDisplayName(IDLREGITEM const *,ushort * *)

- ea: `0x18014c06c`
- end: `0x18014c439`
- name: `?_GetRegistryDisplayName@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAPEAG@Z`
- size: `973`
- prototype: `__int64 __fastcall(CRegFolder *__hidden this, const struct IDLREGITEM *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800e2c40`

## callees

- `0x18001b390`
- `0x1800586b0`
- `0x1800945b0`
- `0x180094c70`
- `0x18009d680`
- `0x1800d0ac0`
- `0x1800d13a0`
- `0x1800e4368`
- `0x18014be50`
- `0x18014c06c`
- `0x18014c440`
- `0x18014c4e0`
- `0x18014c740`
- `0x18014d4e0`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18014c426`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18014c426`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18014c3a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18014c3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014c395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014c395`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c2d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c30c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c3a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c2d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c30c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014c3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014c214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18014c214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c31c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c3e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c31c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014c3e2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18014c0f1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18014c28c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18014c0f1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18014c28c`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18014c142`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x18014c142`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18014c1ae`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18014c1d0`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18014c1ae`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18014c1d0`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_ModifyWowDisplayName` at `0x18014c3f6`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_ModifyWowDisplayName` at `0x18014c3f6`

## string_xrefs

- `0x18014c2aa`: `Bad reg folder display name config, clsid: %ls`

## pseudocode

```c
__int64 __fastcall CRegFolder::_GetRegistryDisplayName(
        CRegFolder *this,
        const struct IDLREGITEM *a2,
        unsigned __int16 **a3)
{
  GUID *PIDLRCLSID; // rax
  __int64 v7; // r9
  HKEY v8; // rdi
  HKEY v9; // rbx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  rsize_t v12; // rdi
  char *v13; // rax
  char *v14; // rbx
  int v15; // eax
  unsigned __int16 *v17; // rax
  HKEY v18; // rdi
  void **v19; // rax
  int v20; // r9d
  DWORD LastError; // ebx
  unsigned int *v22; // [rsp+28h] [rbp-D8h]
  bool v23; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v24; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 Source[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  *a3 = 0;
  v24 = 0;
  PIDLRCLSID = (GUID *)CRegFolder::_GetPIDLRCLSID(this, a2);
  v7 = *((_QWORD *)this + 39);
  rguid = *PIDLRCLSID;
  if ( v7 && (int)StringCchPrintfW(Source, 0x104u, L"%s\\NameCustomizations") >= 0 )
  {
    StringFromGUID2(&rguid, sz, 39);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v24);
    GetSessionKeyStringAlloc(Source, sz);
  }
  hKey = 0;
  if ( !v24 )
  {
    if ( (int)SHRegGetCLSIDKey(&rguid, 0, 1, 0, 1, &hKey) >= 0 )
    {
      v19 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v24);
      if ( SHRegAllocData(hKey, 0, 0, v20, v19, v22) < 0 )
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v24,
          0);
    }
    if ( !v24 )
    {
      v8 = hKey;
      v23 = 0;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v8);
        SetLastError(LastError);
      }
      hKey = 0;
      if ( CRegFolder::_OpenItemKey(this, a2, &v23, &hKey) >= 0 )
      {
        if ( (v9 = hKey, Source[0] = 0, (int)SHLoadRegUIStringW(hKey, L"LocalizedString", Source, 260) >= 0)
          && Source[0]
          || (int)SHLoadRegUIStringW(v9, &WindowName, Source, 260) >= 0 )
        {
          if ( v23 )
            SHELL32_CPL_ModifyWowDisplayName(Source, 260);
          v10 = 0x7FFFFFFF;
          v11 = Source;
          do
          {
            if ( !*v11 )
              break;
            ++v11;
            --v10;
          }
          while ( v10 );
          v12 = 2 * (v11 - Source);
          v13 = (char *)CoTaskMemAlloc(v12 + 2);
          v14 = v13;
          if ( v13 )
          {
            memcpy_s_0(v13, v12 + 2, Source, v12);
            *(_WORD *)&v14[v12] = 0;
          }
          pv = v14;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::replace(
            &v24,
            &pv);
          if ( pv )
            CoTaskMemFree(pv);
        }
      }
      if ( !v24 )
      {
        v15 = CRegFolder::_ReqItemIndex(this, a2);
        if ( v15 < 0 )
        {
LABEL_23:
          StringFromGUID2(&rguid, sz, 39);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x6AD,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\regfldr.cpp",
            (const char *)0x80004005LL,
            (int)"Bad reg folder display name config, clsid: %ls",
            (const char *)sz);
          if ( hKey )
            RegCloseKey(hKey);
          if ( v24 )
            CoTaskMemFree(v24);
          return 2147500037LL;
        }
        if ( LoadStringW(g_hinst, *(_DWORD *)(*((_QWORD *)this + 43) + 48LL * v15 + 8), Source, 260) )
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            Source,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v24,
            &pv);
          if ( pv )
            CoTaskMemFree(pv);
        }
      }
    }
  }
  v17 = (unsigned __int16 *)v24;
  if ( !v24 )
    goto LABEL_23;
  v18 = hKey;
  v24 = 0;
  *a3 = v17;
  if ( v18 )
  {
    RegCloseKey(v18);
    if ( v24 )
      CoTaskMemFree(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x18014c06c  mov     [rsp-8+arg_18], rbx
0x18014c071  push    rbp
0x18014c072  push    rsi
0x18014c073  push    rdi
0x18014c074  push    r12
0x18014c076  push    r13
0x18014c078  push    r14
0x18014c07a  push    r15
0x18014c07c  lea     rbp, [rsp-1D0h]
0x18014c084  sub     rsp, 2D0h
0x18014c08b  mov     rax, cs:__security_cookie
0x18014c092  xor     rax, rsp
0x18014c095  mov     [rbp+200h+var_40], rax
0x18014c09c  xor     r13d, r13d
0x18014c09f  mov     r12, r8
0x18014c0a2  mov     [r8], r13
0x18014c0a5  mov     r15, rdx
0x18014c0a8  mov     [rsp+300h+var_2C8], r13
0x18014c0ad  mov     r14, rcx
0x18014c0b0  call    ?_GetPIDLRCLSID@CRegFolder@@AEAAAEFBU_GUID@@PEFBUIDLREGITEM@@@Z; CRegFolder::_GetPIDLRCLSID(IDLREGITEM const *)
0x18014c0b5  mov     r9, [r14+138h]
0x18014c0bc  movups  xmm0, xmmword ptr [rax]
0x18014c0bf  movdqu  xmmword ptr [rsp+300h+rguid.Data1], xmm0
0x18014c0c5  test    r9, r9
0x18014c0c8  jz      short loc_18014C112
0x18014c0ca  lea     r8, aSNamecustomiza; "%s\\NameCustomizations"
0x18014c0d1  mov     edx, 104h; unsigned __int64
0x18014c0d6  lea     rcx, [rbp+200h+Source]; unsigned __int16 *
0x18014c0da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18014c0df  test    eax, eax
0x18014c0e1  js      short loc_18014C112
0x18014c0e3  lea     r8d, [r13+27h]; cchMax
0x18014c0e7  lea     rdx, [rsp+300h+sz]; lpsz
0x18014c0ec  lea     rcx, [rsp+300h+rguid]; rguid
0x18014c0f1  call    cs:__imp_StringFromGUID2
0x18014c0f7  lea     rcx, [rsp+300h+var_2C8]
0x18014c0fc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18014c101  mov     r8, rax
0x18014c104  lea     rdx, [rsp+300h+sz]; lpValue
0x18014c109  lea     rcx, [rbp+200h+Source]; lpSubKey
0x18014c10d  call    GetSessionKeyStringAlloc
0x18014c112  mov     [rsp+300h+hKey], r13
0x18014c117  cmp     [rsp+300h+var_2C8], r13
0x18014c11c  jnz     loc_18014C2EC
0x18014c122  xor     r9d, r9d
0x18014c125  lea     rax, [rsp+300h+hKey]
0x18014c12a  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x18014c12f  lea     rcx, [rsp+300h+rguid]
0x18014c134  xor     edx, edx
0x18014c136  mov     dword ptr [rsp+300h+var_2E0], 1
0x18014c13e  lea     r8d, [r9+1]
0x18014c142  call    cs:__imp_SHRegGetCLSIDKey
0x18014c148  test    eax, eax
0x18014c14a  jns     loc_18014C35E
0x18014c150  cmp     [rsp+300h+var_2C8], r13
0x18014c155  jnz     loc_18014C2EC
0x18014c15b  mov     rdi, [rsp+300h+hKey]
0x18014c160  mov     [rsp+300h+var_2D0], r13b
0x18014c165  test    rdi, rdi
0x18014c168  jnz     loc_18014C395
0x18014c16e  lea     r9, [rsp+300h+hKey]; HKEY *
0x18014c173  mov     [rsp+300h+hKey], r13
0x18014c178  lea     r8, [rsp+300h+var_2D0]; bool *
0x18014c17d  mov     rdx, r15; struct IDLREGITEM *
0x18014c180  mov     rcx, r14; this
0x18014c183  call    ?_OpenItemKey@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEA_NPEAPEAUHKEY__@@@Z; CRegFolder::_OpenItemKey(IDLREGITEM const *,bool *,HKEY__ * *)
0x18014c188  test    eax, eax
0x18014c18a  js      loc_18014C25E
0x18014c190  mov     rbx, [rsp+300h+hKey]
0x18014c195  lea     r8, [rbp+200h+Source]
0x18014c199  mov     rcx, rbx
0x18014c19c  mov     [rbp+200h+Source], r13w
0x18014c1a1  mov     r9d, 104h
0x18014c1a7  lea     rdx, aLocalizedstrin; "LocalizedString"
0x18014c1ae  call    cs:__imp_SHLoadRegUIStringW
0x18014c1b4  test    eax, eax
0x18014c1b6  jns     loc_18014C34E
0x18014c1bc  mov     r9d, 104h
0x18014c1c2  lea     r8, [rbp+200h+Source]
0x18014c1c6  lea     rdx, WindowName
0x18014c1cd  mov     rcx, rbx
0x18014c1d0  call    cs:__imp_SHLoadRegUIStringW
0x18014c1d6  test    eax, eax
0x18014c1d8  js      loc_18014C25E
0x18014c1de  cmp     [rsp+300h+var_2D0], r13b
0x18014c1e3  jnz     loc_18014C3ED
0x18014c1e9  mov     ecx, 7FFFFFFFh
0x18014c1ee  lea     rax, [rbp+200h+Source]
0x18014c1f2  cmp     [rax], r13w
0x18014c1f6  jz      short loc_18014C202
0x18014c1f8  add     rax, 2
0x18014c1fc  sub     rcx, 1
0x18014c200  jnz     short loc_18014C1F2
0x18014c202  lea     rcx, [rbp+200h+Source]
0x18014c206  sub     rax, rcx
0x18014c209  sar     rax, 1
0x18014c20c  lea     rdi, [rax+rax]
0x18014c210  lea     rcx, [rdi+2]; cb
0x18014c214  call    cs:__imp_CoTaskMemAlloc
0x18014c21a  mov     rbx, rax
0x18014c21d  test    rax, rax
0x18014c220  jz      short loc_18014C23A
0x18014c222  mov     r9, rdi; SourceSize
0x18014c225  lea     r8, [rbp+200h+Source]; Source
0x18014c229  lea     rdx, [rdi+2]; DestinationSize
0x18014c22d  mov     rcx, rax; Destination
0x18014c230  call    memcpy_s_0
0x18014c235  mov     [rdi+rbx], r13w
0x18014c23a  lea     rdx, [rsp+300h+pv]
0x18014c23f  mov     [rsp+300h+pv], rbx
0x18014c244  lea     rcx, [rsp+300h+var_2C8]
0x18014c249  call    ?replace@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@IEAAX$$QEAV123@@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::replace(wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>> &&)
0x18014c24e  mov     rcx, [rsp+300h+pv]; pv
0x18014c253  test    rcx, rcx
0x18014c256  jz      short loc_18014C25E
0x18014c258  call    cs:__imp_CoTaskMemFree
0x18014c25e  cmp     [rsp+300h+var_2C8], r13
0x18014c263  jnz     loc_18014C2EC
0x18014c269  mov     rdx, r15; struct IDLREGITEM *
0x18014c26c  mov     rcx, r14; this
0x18014c26f  call    ?_ReqItemIndex@CRegFolder@@AEAAHPEFBUIDLREGITEM@@@Z; CRegFolder::_ReqItemIndex(IDLREGITEM const *)
0x18014c274  test    eax, eax
0x18014c276  jns     loc_18014C401
0x18014c27c  mov     r8d, 27h ; '''; cchMax
0x18014c282  lea     rdx, [rsp+300h+sz]; lpsz
0x18014c287  lea     rcx, [rsp+300h+rguid]; rguid
0x18014c28c  call    cs:__imp_StringFromGUID2
0x18014c292  mov     rcx, [rbp+208h]; this
0x18014c299  lea     rax, [rsp+300h+sz]
0x18014c29e  mov     [rsp+300h+var_2D8], rax; char *
0x18014c2a3  lea     r8, aOnecoreuapShel_141; "onecoreuap\\shell\\windows.storage\\reg"...
0x18014c2aa  lea     rax, aBadRegFolderDi; "Bad reg folder display name config, cls"...
0x18014c2b1  mov     ebx, 80004005h
0x18014c2b6  mov     r9d, ebx; char *
0x18014c2b9  mov     [rsp+300h+var_2E0], rax; int
0x18014c2be  mov     edx, 6ADh; void *
0x18014c2c3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18014c2c8  mov     rcx, [rsp+300h+hKey]; hKey
0x18014c2cd  test    rcx, rcx
0x18014c2d0  jz      short loc_18014C2D8
0x18014c2d2  call    cs:__imp_RegCloseKey
0x18014c2d8  mov     rcx, [rsp+300h+var_2C8]; pv
0x18014c2dd  test    rcx, rcx
0x18014c2e0  jz      short loc_18014C2E8
0x18014c2e2  call    cs:__imp_CoTaskMemFree
0x18014c2e8  mov     eax, ebx
0x18014c2ea  jmp     short loc_18014C324
0x18014c2ec  mov     rax, [rsp+300h+var_2C8]
0x18014c2f1  test    rax, rax
0x18014c2f4  jz      short loc_18014C27C
0x18014c2f6  mov     rdi, [rsp+300h+hKey]
0x18014c2fb  mov     [rsp+300h+var_2C8], r13
0x18014c300  mov     [r12], rax
0x18014c304  test    rdi, rdi
0x18014c307  jz      short loc_18014C322
0x18014c309  mov     rcx, rdi; hKey
0x18014c30c  call    cs:__imp_RegCloseKey
0x18014c312  mov     rcx, [rsp+300h+var_2C8]; pv
0x18014c317  test    rcx, rcx
0x18014c31a  jz      short loc_18014C322
0x18014c31c  call    cs:__imp_CoTaskMemFree
0x18014c322  xor     eax, eax
0x18014c324  mov     rcx, [rbp+200h+var_40]
0x18014c32b  xor     rcx, rsp; StackCookie
0x18014c32e  call    __security_check_cookie
0x18014c333  mov     rbx, [rsp+300h+arg_18]
0x18014c33b  add     rsp, 2D0h
0x18014c342  pop     r15
0x18014c344  pop     r14
0x18014c346  pop     r13
0x18014c348  pop     r12
0x18014c34a  pop     rdi
0x18014c34b  pop     rsi
0x18014c34c  pop     rbp
0x18014c34d  retn
0x18014c34e  cmp     [rbp+200h+Source], r13w
0x18014c353  jz      loc_18014C1BC
0x18014c359  jmp     loc_18014C1DE
0x18014c35e  lea     rcx, [rsp+300h+var_2C8]
0x18014c363  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18014c368  mov     rcx, [rsp+300h+hKey]; HKEY
0x18014c36d  xor     r8d, r8d; unsigned __int16 *
0x18014c370  xor     edx, edx; unsigned __int16 *
0x18014c372  mov     [rsp+300h+var_2E0], rax; void **
0x18014c377  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18014c37c  test    eax, eax
0x18014c37e  jns     loc_18014C150
0x18014c384  xor     edx, edx
0x18014c386  lea     rcx, [rsp+300h+var_2C8]
0x18014c38b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18014c390  jmp     loc_18014C150
0x18014c395  call    cs:__imp_GetLastError
0x18014c39b  mov     rcx, rdi; hKey
0x18014c39e  mov     ebx, eax
0x18014c3a0  call    cs:__imp_RegCloseKey
0x18014c3a6  mov     ecx, ebx; dwErrCode
0x18014c3a8  call    cs:__imp_SetLastError
0x18014c3ae  jmp     loc_18014C16E
0x18014c3b3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18014c3b7  lea     rdx, [rbp+200h+Source]
0x18014c3bb  lea     rcx, [rsp+300h+pv]
0x18014c3c0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18014c3c5  lea     rdx, [rsp+300h+pv]
0x18014c3ca  lea     rcx, [rsp+300h+var_2C8]
0x18014c3cf  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18014c3d4  mov     rcx, [rsp+300h+pv]; pv
0x18014c3d9  test    rcx, rcx
0x18014c3dc  jz      loc_18014C2EC
0x18014c3e2  call    cs:__imp_CoTaskMemFree
0x18014c3e8  jmp     loc_18014C2EC
0x18014c3ed  mov     edx, 104h
0x18014c3f2  lea     rcx, [rbp+200h+Source]
0x18014c3f6  call    cs:__imp_SHELL32_CPL_ModifyWowDisplayName
0x18014c3fc  jmp     loc_18014C1E9
0x18014c401  mov     rdx, [r14+158h]
0x18014c408  lea     r8, [rbp+200h+Source]; lpBuffer
0x18014c40c  cdqe
0x18014c40e  mov     r9d, 104h; cchBufferMax
0x18014c414  lea     rcx, [rax+rax*2]
0x18014c418  add     rcx, rcx
0x18014c41b  mov     edx, [rdx+rcx*8+8]; uID
0x18014c41f  mov     rcx, cs:g_hinst; hInstance
0x18014c426  call    cs:__imp_LoadStringW
0x18014c42c  test    eax, eax
0x18014c42e  jz      loc_18014C2EC
0x18014c434  jmp     loc_18014C3B3
```
