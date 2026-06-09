# CRegFolder::_GetRegistryDisplayName(IDLREGITEM const *,ushort * *)

- ea: `0x1800c6e20`
- end: `0x1800c71da`
- name: `?_GetRegistryDisplayName@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEAPEAG@Z`
- size: `954`
- prototype: `__int64 __fastcall(CRegFolder *__hidden this, const struct IDLREGITEM *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180091620`

## callees

- `0x180012d30`
- `0x180013140`
- `0x180044320`
- `0x180045bd0`
- `0x18004e434`
- `0x180062710`
- `0x180063050`
- `0x1800b5630`
- `0x1800b5de0`
- `0x1800c6e20`
- `0x1800c72b0`
- `0x1800c8920`
- `0x1800c89e4`
- `0x1801720d0`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180664749`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180664749`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c71af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c71af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c70b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c70fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c71a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c70b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c70fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c71a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c6fe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c6fe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c702a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c70c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c702a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c70c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7110`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c6ea5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c7064`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c6ea5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800c7064`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800c6efc`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800c6efc`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800c6f6e`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800c6f96`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800c6f6e`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x1800c6f96`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_ModifyWowDisplayName` at `0x1800c71c9`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_ModifyWowDisplayName` at `0x1800c71c9`

## string_xrefs

- `0x1800c7088`: `Bad reg folder display name config, clsid: %ls`

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
            memcpy_s(v13, v12 + 2, Source, v12);
            *(_WORD *)&v14[v12] = 0;
          }
          pv = v14;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
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
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
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
0x1800c6e20  mov     [rsp-8+arg_18], rbx
0x1800c6e25  push    rbp
0x1800c6e26  push    rsi
0x1800c6e27  push    rdi
0x1800c6e28  push    r12
0x1800c6e2a  push    r13
0x1800c6e2c  push    r14
0x1800c6e2e  push    r15
0x1800c6e30  lea     rbp, [rsp-1D0h]
0x1800c6e38  sub     rsp, 2D0h
0x1800c6e3f  mov     rax, cs:__security_cookie
0x1800c6e46  xor     rax, rsp
0x1800c6e49  mov     [rbp+200h+var_40], rax
0x1800c6e50  xor     r13d, r13d
0x1800c6e53  mov     r12, r8
0x1800c6e56  mov     [r8], r13
0x1800c6e59  mov     r15, rdx
0x1800c6e5c  mov     [rsp+300h+var_2C8], r13
0x1800c6e61  mov     r14, rcx
0x1800c6e64  call    ?_GetPIDLRCLSID@CRegFolder@@AEAAAEFBU_GUID@@PEFBUIDLREGITEM@@@Z; CRegFolder::_GetPIDLRCLSID(IDLREGITEM const *)
0x1800c6e69  mov     r9, [r14+138h]
0x1800c6e70  movups  xmm0, xmmword ptr [rax]
0x1800c6e73  movdqu  xmmword ptr [rsp+300h+rguid.Data1], xmm0
0x1800c6e79  test    r9, r9
0x1800c6e7c  jz      short loc_1800C6ECC
0x1800c6e7e  lea     r8, aSNamecustomiza; "%s\\NameCustomizations"
0x1800c6e85  mov     edx, 104h; unsigned __int64
0x1800c6e8a  lea     rcx, [rbp+200h+Source]; unsigned __int16 *
0x1800c6e8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c6e93  test    eax, eax
0x1800c6e95  js      short loc_1800C6ECC
0x1800c6e97  lea     r8d, [r13+27h]; cchMax
0x1800c6e9b  lea     rdx, [rsp+300h+sz]; lpsz
0x1800c6ea0  lea     rcx, [rsp+300h+rguid]; rguid
0x1800c6ea5  call    cs:__imp_StringFromGUID2
0x1800c6eac  nop     dword ptr [rax+rax+00h]
0x1800c6eb1  lea     rcx, [rsp+300h+var_2C8]
0x1800c6eb6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800c6ebb  mov     r8, rax
0x1800c6ebe  lea     rdx, [rsp+300h+sz]; lpValue
0x1800c6ec3  lea     rcx, [rbp+200h+Source]; lpSubKey
0x1800c6ec7  call    GetSessionKeyStringAlloc
0x1800c6ecc  mov     [rsp+300h+hKey], r13
0x1800c6ed1  cmp     [rsp+300h+var_2C8], r13
0x1800c6ed6  jnz     loc_1800C70D6
0x1800c6edc  xor     r9d, r9d
0x1800c6edf  lea     rax, [rsp+300h+hKey]
0x1800c6ee4  mov     [rsp+300h+var_2D8], rax; unsigned int *
0x1800c6ee9  lea     rcx, [rsp+300h+rguid]
0x1800c6eee  xor     edx, edx
0x1800c6ef0  mov     dword ptr [rsp+300h+var_2E0], 1
0x1800c6ef8  lea     r8d, [r9+1]
0x1800c6efc  call    cs:__imp_SHRegGetCLSIDKey
0x1800c6f03  nop     dword ptr [rax+rax+00h]
0x1800c6f08  test    eax, eax
0x1800c6f0a  jns     loc_1800C7159
0x1800c6f10  cmp     [rsp+300h+var_2C8], r13
0x1800c6f15  jnz     loc_1800C70D6
0x1800c6f1b  mov     rdi, [rsp+300h+hKey]
0x1800c6f20  mov     [rsp+300h+var_2D0], r13b
0x1800c6f25  test    rdi, rdi
0x1800c6f28  jnz     loc_1800C7190
0x1800c6f2e  lea     r9, [rsp+300h+hKey]; HKEY *
0x1800c6f33  mov     [rsp+300h+hKey], r13
0x1800c6f38  lea     r8, [rsp+300h+var_2D0]; bool *
0x1800c6f3d  mov     rdx, r15; struct IDLREGITEM *
0x1800c6f40  mov     rcx, r14; this
0x1800c6f43  call    ?_OpenItemKey@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEA_NPEAPEAUHKEY__@@@Z; CRegFolder::_OpenItemKey(IDLREGITEM const *,bool *,HKEY__ * *)
0x1800c6f48  test    eax, eax
0x1800c6f4a  js      loc_1800C7036
0x1800c6f50  mov     rbx, [rsp+300h+hKey]
0x1800c6f55  lea     r8, [rbp+200h+Source]
0x1800c6f59  mov     rcx, rbx
0x1800c6f5c  mov     [rbp+200h+Source], r13w
0x1800c6f61  mov     r9d, 104h
0x1800c6f67  lea     rdx, aLocalizedstrin; "LocalizedString"
0x1800c6f6e  call    cs:__imp_SHLoadRegUIStringW
0x1800c6f75  nop     dword ptr [rax+rax+00h]
0x1800c6f7a  test    eax, eax
0x1800c6f7c  jns     loc_1800C7149
0x1800c6f82  mov     r9d, 104h
0x1800c6f88  lea     r8, [rbp+200h+Source]
0x1800c6f8c  lea     rdx, WindowName
0x1800c6f93  mov     rcx, rbx
0x1800c6f96  call    cs:__imp_SHLoadRegUIStringW
0x1800c6f9d  nop     dword ptr [rax+rax+00h]
0x1800c6fa2  test    eax, eax
0x1800c6fa4  js      loc_1800C7036
0x1800c6faa  cmp     [rsp+300h+var_2D0], r13b
0x1800c6faf  jnz     loc_1800C71C0
0x1800c6fb5  mov     ecx, 7FFFFFFFh
0x1800c6fba  lea     rax, [rbp+200h+Source]
0x1800c6fbe  cmp     [rax], r13w
0x1800c6fc2  jz      short loc_1800C6FCE
0x1800c6fc4  add     rax, 2
0x1800c6fc8  sub     rcx, 1
0x1800c6fcc  jnz     short loc_1800C6FBE
0x1800c6fce  lea     rcx, [rbp+200h+Source]
0x1800c6fd2  sub     rax, rcx
0x1800c6fd5  sar     rax, 1
0x1800c6fd8  lea     rdi, [rax+rax]
0x1800c6fdc  lea     rcx, [rdi+2]; cb
0x1800c6fe0  call    cs:__imp_CoTaskMemAlloc
0x1800c6fe7  nop     dword ptr [rax+rax+00h]
0x1800c6fec  mov     rbx, rax
0x1800c6fef  test    rax, rax
0x1800c6ff2  jz      short loc_1800C700C
0x1800c6ff4  mov     r9, rdi; SourceSize
0x1800c6ff7  lea     r8, [rbp+200h+Source]; Source
0x1800c6ffb  lea     rdx, [rdi+2]; DestinationSize
0x1800c6fff  mov     rcx, rax; Destination
0x1800c7002  call    memcpy_s
0x1800c7007  mov     [rdi+rbx], r13w
0x1800c700c  lea     rdx, [rsp+300h+pv]
0x1800c7011  mov     [rsp+300h+pv], rbx
0x1800c7016  lea     rcx, [rsp+300h+var_2C8]
0x1800c701b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800c7020  mov     rcx, [rsp+300h+pv]; pv
0x1800c7025  test    rcx, rcx
0x1800c7028  jz      short loc_1800C7036
0x1800c702a  call    cs:__imp_CoTaskMemFree
0x1800c7031  nop     dword ptr [rax+rax+00h]
0x1800c7036  cmp     [rsp+300h+var_2C8], r13
0x1800c703b  jnz     loc_1800C70D6
0x1800c7041  mov     rdx, r15; struct IDLREGITEM *
0x1800c7044  mov     rcx, r14; this
0x1800c7047  call    ?_ReqItemIndex@CRegFolder@@AEAAHPEFBUIDLREGITEM@@@Z; CRegFolder::_ReqItemIndex(IDLREGITEM const *)
0x1800c704c  test    eax, eax
0x1800c704e  jns     loc_180664724
0x1800c7054  mov     r8d, 27h ; '''; cchMax
0x1800c705a  lea     rdx, [rsp+300h+sz]; lpsz
0x1800c705f  lea     rcx, [rsp+300h+rguid]; rguid
0x1800c7064  call    cs:__imp_StringFromGUID2
0x1800c706b  nop     dword ptr [rax+rax+00h]
0x1800c7070  mov     rcx, [rbp+208h]; this
0x1800c7077  lea     rax, [rsp+300h+sz]
0x1800c707c  mov     [rsp+300h+var_2D8], rax; char *
0x1800c7081  lea     r8, aOnecoreuapShel_141; "onecoreuap\\shell\\windows.storage\\reg"...
0x1800c7088  lea     rax, aBadRegFolderDi; "Bad reg folder display name config, cls"...
0x1800c708f  mov     ebx, 80004005h
0x1800c7094  mov     r9d, ebx; char *
0x1800c7097  mov     [rsp+300h+var_2E0], rax; int
0x1800c709c  mov     edx, 6ADh; void *
0x1800c70a1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800c70a6  mov     rcx, [rsp+300h+hKey]; hKey
0x1800c70ab  test    rcx, rcx
0x1800c70ae  jz      short loc_1800C70BC
0x1800c70b0  call    cs:__imp_RegCloseKey
0x1800c70b7  nop     dword ptr [rax+rax+00h]
0x1800c70bc  mov     rcx, [rsp+300h+var_2C8]; pv
0x1800c70c1  test    rcx, rcx
0x1800c70c4  jz      short loc_1800C70D2
0x1800c70c6  call    cs:__imp_CoTaskMemFree
0x1800c70cd  nop     dword ptr [rax+rax+00h]
0x1800c70d2  mov     eax, ebx
0x1800c70d4  jmp     short loc_1800C711E
0x1800c70d6  mov     rax, [rsp+300h+var_2C8]
0x1800c70db  test    rax, rax
0x1800c70de  jz      loc_1800C7054
0x1800c70e4  mov     rdi, [rsp+300h+hKey]
0x1800c70e9  mov     [rsp+300h+var_2C8], r13
0x1800c70ee  mov     [r12], rax
0x1800c70f2  test    rdi, rdi
0x1800c70f5  jz      short loc_1800C711C
0x1800c70f7  mov     rcx, rdi; hKey
0x1800c70fa  call    cs:__imp_RegCloseKey
0x1800c7101  nop     dword ptr [rax+rax+00h]
0x1800c7106  mov     rcx, [rsp+300h+var_2C8]; pv
0x1800c710b  test    rcx, rcx
0x1800c710e  jz      short loc_1800C711C
0x1800c7110  call    cs:__imp_CoTaskMemFree
0x1800c7117  nop     dword ptr [rax+rax+00h]
0x1800c711c  xor     eax, eax
0x1800c711e  mov     rcx, [rbp+200h+var_40]
0x1800c7125  xor     rcx, rsp; StackCookie
0x1800c7128  call    __security_check_cookie
0x1800c712d  mov     rbx, [rsp+300h+arg_18]
0x1800c7135  add     rsp, 2D0h
0x1800c713c  pop     r15
0x1800c713e  pop     r14
0x1800c7140  pop     r13
0x1800c7142  pop     r12
0x1800c7144  pop     rdi
0x1800c7145  pop     rsi
0x1800c7146  pop     rbp
0x1800c7147  retn
0x1800c7149  cmp     [rbp+200h+Source], r13w
0x1800c714e  jz      loc_1800C6F82
0x1800c7154  jmp     loc_1800C6FAA
0x1800c7159  lea     rcx, [rsp+300h+var_2C8]
0x1800c715e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800c7163  mov     rcx, [rsp+300h+hKey]; HKEY
0x1800c7168  xor     r8d, r8d; unsigned __int16 *
0x1800c716b  xor     edx, edx; unsigned __int16 *
0x1800c716d  mov     [rsp+300h+var_2E0], rax; void **
0x1800c7172  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800c7177  test    eax, eax
0x1800c7179  jns     loc_1800C6F10
0x1800c717f  xor     edx, edx
0x1800c7181  lea     rcx, [rsp+300h+var_2C8]
0x1800c7186  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c718b  jmp     loc_1800C6F10
0x1800c7190  call    cs:__imp_GetLastError
0x1800c7197  nop     dword ptr [rax+rax+00h]
0x1800c719c  mov     rcx, rdi; hKey
0x1800c719f  mov     ebx, eax
0x1800c71a1  call    cs:__imp_RegCloseKey
0x1800c71a8  nop     dword ptr [rax+rax+00h]
0x1800c71ad  mov     ecx, ebx; dwErrCode
0x1800c71af  call    cs:__imp_SetLastError
0x1800c71b6  nop     dword ptr [rax+rax+00h]
0x1800c71bb  jmp     loc_1800C6F2E
0x1800c71c0  mov     edx, 104h
0x1800c71c5  lea     rcx, [rbp+200h+Source]
0x1800c71c9  call    cs:__imp_SHELL32_CPL_ModifyWowDisplayName
0x1800c71d0  nop     dword ptr [rax+rax+00h]
0x1800c71d5  jmp     loc_1800C6FB5
0x180664724  mov     rdx, [r14+158h]
0x18066472b  lea     r8, [rbp+200h+Source]; lpBuffer
0x18066472f  cdqe
0x180664731  mov     r9d, 104h; cchBufferMax
0x180664737  lea     rcx, [rax+rax*2]
0x18066473b  add     rcx, rcx
0x18066473e  mov     edx, [rdx+rcx*8+8]; uID
0x180664742  mov     rcx, cs:g_hinst; hInstance
0x180664749  call    cs:__imp_LoadStringW
0x180664750  nop     dword ptr [rax+rax+00h]
0x180664755  test    eax, eax
0x180664757  jz      loc_1800C70D6
0x18066475d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180664761  lea     rdx, [rbp+200h+Source]
0x180664765  lea     rcx, [rsp+300h+pv]
0x18066476a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18066476f  lea     rdx, [rsp+300h+pv]
0x180664774  lea     rcx, [rsp+300h+var_2C8]
0x180664779  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18066477e  lea     rcx, [rsp+300h+pv]; void *
0x180664783  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180664788  nop
0x180664789  jmp     loc_1800C70D6
```
