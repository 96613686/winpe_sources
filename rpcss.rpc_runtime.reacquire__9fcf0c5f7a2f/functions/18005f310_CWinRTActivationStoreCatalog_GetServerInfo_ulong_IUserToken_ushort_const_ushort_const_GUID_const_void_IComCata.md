# CWinRTActivationStoreCatalog::GetServerInfo(ulong,IUserToken *,ushort const *,ushort const *,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x18005f310`
- end: `0x18005f992`
- name: `?GetServerInfo@CWinRTActivationStoreCatalog@@UEAAJKPEAUIUserToken@@PEBG1AEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `1666`
- prototype: `int(CWinRTActivationStoreCatalog *__hidden this, unsigned int, struct IUserToken *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, struct IComCatalogSCM *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009d78`
- `0x1800241f0`
- `0x180025088`
- `0x18002750c`
- `0x180034260`
- `0x18003ca38`
- `0x180052390`
- `0x18005f310`
- `0x180061e18`
- `0x18007b310`
- `0x1800a660c`
- `0x1800d69a0`
- `0x1800d6a4c`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f89a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f89a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005f5bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005f5bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x18005f961`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x18005f961`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18005f972`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18005f972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f3c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f3c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005f3e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005f43b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005f3e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005f43b`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005f4e0`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005f4e0`

## string_xrefs

- `0x18005f852`: `onecore\com\combase\catalog\storecat.cxx`

## pseudocode

```c
__int64 __fastcall CWinRTActivationStoreCatalog::GetServerInfo(
        CWinRTActivationStoreCatalog *this,
        unsigned int a2,
        struct IUserToken *a3,
        const unsigned __int16 *a4,
        PCNZWCH sourceString,
        const struct _GUID *a6,
        void **a7,
        struct IComCatalogSCM *a8)
{
  int v10; // r9d
  WCHAR *v13; // r13
  LPWSTR v14; // r15
  unsigned __int64 v15; // rbx
  HRESULT v16; // eax
  int Interface; // ebx
  unsigned __int64 v18; // rbx
  HRESULT v19; // eax
  bool v20; // zf
  int v21; // eax
  __int64 v22; // rdx
  int RegistrationStoreContext; // eax
  struct IActivationCatalogContext *v24; // rbx
  __int64 (__fastcall *v25)(struct IActivationCatalogContext *, GUID *, __int64 *); // rdi
  __int64 v26; // rax
  WCHAR *v27; // r9
  int v28; // edx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r9d
  CWinRTActivationStoreCatalog::CServerInfo *v34; // rax
  CWinRTActivationStoreCatalog::CServerInfo *v35; // rax
  CWinRTActivationStoreCatalog::CServerInfo *v36; // rdi
  __int64 v37; // rdx
  struct IActivationCatalogContext **v38; // [rsp+20h] [rbp-71h]
  HSTRING v39; // [rsp+50h] [rbp-41h] BYREF
  HSTRING string; // [rsp+58h] [rbp-39h] BYREF
  struct RegistrationStoreContext::ServerHandleDetail *v41; // [rsp+60h] [rbp-31h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-29h] BYREF
  struct RegistrationStoreContext::ServerForMachineHandleDetail *v43; // [rsp+70h] [rbp-21h] BYREF
  __int64 v44; // [rsp+78h] [rbp-19h] BYREF
  __int64 v45; // [rsp+80h] [rbp-11h] BYREF
  PSID Sid[9]; // [rsp+88h] [rbp-9h] BYREF
  struct IActivationCatalogContext *v47; // [rsp+E0h] [rbp+4Fh] BYREF

  v10 = 0;
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
      (_DWORD)this,
      (unsigned int)"CWinRTActivationStoreCatalog::GetServerInfo",
      491,
      3,
      (__int64)L"GetServerInfo for %ws in scope %!Windows::Foundation::RegistrationScope!");
    v10 = 0;
  }
  v13 = (WCHAR *)sourceString;
  v14 = (LPWSTR)&Class;
  v39 = 0;
  string = 0;
  v47 = 0;
  v44 = 0;
  v41 = 0;
  v43 = 0;
  if ( sourceString )
  {
    v15 = -1;
    do
      ++v15;
    while ( sourceString[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      Interface = -2147024362;
      goto LABEL_26;
    }
    WindowsDeleteString(0);
    string = 0;
    v16 = WindowsCreateString(v13, v15, &string);
    v10 = 0;
    Interface = v16;
    if ( v16 < 0 )
      goto LABEL_26;
  }
  if ( a4 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a4[v18] );
    if ( v18 > 0xFFFFFFFF )
    {
      Interface = -2147024362;
      goto LABEL_18;
    }
    WindowsDeleteString(v39);
    v39 = 0;
    v19 = WindowsCreateString(a4, v18, &v39);
  }
  else
  {
    v19 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v39, &Class, 0);
  }
  v10 = 0;
  Interface = v19;
LABEL_18:
  if ( Interface < 0 )
    goto LABEL_26;
  v20 = *((_DWORD *)this + 5) == 1;
  v45 = -1;
  if ( v20 && a3 )
  {
    v21 = (*(__int64 (__fastcall **)(struct IUserToken *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v45);
    v10 = 0;
    Interface = v21;
    if ( v21 < 0 )
      goto LABEL_26;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v22 = v45;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v22 = 0;
  }
  v38 = &v47;
  RegistrationStoreContext = RoGetRegistrationStoreContext(
                               *((unsigned int *)this + 5),
                               v22,
                               ~(unsigned __int8)(a2 >> 19) & 0x10,
                               &GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2);
  v10 = 0;
  Interface = RegistrationStoreContext;
  if ( RegistrationStoreContext >= 0 )
  {
    v24 = v47;
    v25 = **(__int64 (__fastcall ***)(struct IActivationCatalogContext *, GUID *, __int64 *))v47;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    Interface = v25(v24, &GUID_6859c7ea_a8f8_47e3_84eb_92c2d56d3ec6, &v44);
    v10 = 0;
  }
LABEL_26:
  if ( *((_DWORD *)this + 5) != 1 )
  {
    if ( *((_DWORD *)this + 5) != 2 )
    {
      if ( Interface >= 0 )
      {
        Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, struct RegistrationStoreContext::ServerForMachineHandleDetail **, _QWORD, struct IActivationCatalogContext **))(*(_QWORD *)v47 + 96LL))(
                      v47,
                      v39,
                      &v43,
                      0,
                      v38);
        v10 = 0;
      }
      if ( Interface != -2147024894 )
        goto LABEL_70;
      if ( !gfEnableTracing )
        goto LABEL_82;
      if ( !(unsigned __int8)IsWppLevelEnabled(2) )
      {
LABEL_70:
        if ( Interface >= 0 )
        {
          if ( gfEnableTracing == v10 || !(unsigned __int8)IsWppLevelEnabled(3) )
            goto LABEL_83;
        }
        else
        {
          if ( Interface == -2147024894 )
            goto LABEL_82;
          if ( !dword_1801574B8 && (gfEnableTracing == v10 || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_57;
        }
      }
      v32 = 618;
      goto LABEL_79;
    }
    if ( Interface >= 0 )
    {
      Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ServerHandleDetail **, struct IActivationCatalogContext **))(*(_QWORD *)v47 + 88LL))(
                    v47,
                    string,
                    v39,
                    &v41,
                    v38);
      v10 = 0;
    }
    if ( Interface != -2147024894 )
      goto LABEL_52;
    if ( !gfEnableTracing )
      goto LABEL_82;
    if ( !(unsigned __int8)IsWppLevelEnabled(2) )
    {
LABEL_52:
      if ( Interface < 0 )
      {
        if ( Interface != -2147024894 )
        {
          if ( !dword_1801574B8 && (gfEnableTracing == v10 || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_57;
          goto LABEL_64;
        }
LABEL_82:
        Interface = -2147221164;
        goto LABEL_57;
      }
      if ( gfEnableTracing == v10 || !(unsigned __int8)IsWppLevelEnabled(3) )
        goto LABEL_83;
    }
LABEL_64:
    v32 = 600;
    goto LABEL_79;
  }
  if ( a3 )
  {
    if ( Interface >= 0 )
      Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ServerHandleDetail **, struct IActivationCatalogContext **))(*(_QWORD *)v47 + 88LL))(
                    v47,
                    string,
                    v39,
                    &v41,
                    v38);
    v26 = *(_QWORD *)a3;
    Sid[0] = 0;
    LOWORD(sourceString) = 0;
    (*(void (__fastcall **)(struct IUserToken *, PSID *, PCNZWCH *))(v26 + 40))(a3, Sid, &sourceString);
    v27 = 0;
    if ( Interface < 0 )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        StringSid = v27;
        ConvertSidToStringSidW(Sid[0], &StringSid);
        if ( StringSid )
          v14 = StringSid;
        ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope,unsigned short *,long>(
          v29,
          v28,
          v30,
          v31,
          (_DWORD)v38,
          (__int64)a4,
          *((_DWORD *)this + 5),
          (__int64)v14,
          Interface);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      }
LABEL_81:
      if ( Interface != -2147024894 )
        goto LABEL_57;
      goto LABEL_82;
    }
    goto LABEL_83;
  }
  if ( Interface < 0
    || (Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ServerHandleDetail **, struct IActivationCatalogContext **))(*(_QWORD *)v47 + 88LL))(
                      v47,
                      string,
                      v39,
                      &v41,
                      v38),
        Interface < 0) )
  {
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_81;
LABEL_45:
    v32 = 580;
LABEL_79:
    ComTraceHr(
      Interface,
      "onecore\\com\\combase\\catalog\\storecat.cxx",
      "CWinRTActivationStoreCatalog::GetServerInfo",
      v32,
      L"Look up Server entry %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!",
      a4,
      *((_DWORD *)this + 5),
      Interface);
LABEL_80:
    if ( Interface < 0 )
      goto LABEL_81;
    goto LABEL_83;
  }
  if ( gfEnableTracing )
  {
    if ( !(unsigned __int8)IsWppLevelEnabled(3) )
      goto LABEL_80;
    goto LABEL_45;
  }
LABEL_83:
  v34 = (CWinRTActivationStoreCatalog::CServerInfo *)HeapAlloc(g_hHeap, 0, 0x120u);
  if ( v34
    && (v35 = (CWinRTActivationStoreCatalog::CServerInfo *)CWinRTActivationStoreCatalog::CServerInfo::CServerInfo(v34),
        (v36 = v35) != 0) )
  {
    Interface = CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct(
                  v35,
                  a3,
                  a4,
                  (struct IUserTokenInternal *)v13,
                  a8,
                  v47,
                  v41,
                  v43);
    if ( Interface >= 0 )
      Interface = CWinRTActivationStoreCatalog::CServerInfo::QueryInterface(v36, a6, a7);
    CWinRTActivationStoreCatalog::CServerInfo::Release(v36);
    if ( Interface == -2147024894 || Interface == -2147024883 )
    {
      Sid[0] = 0;
      LOWORD(sourceString) = 0;
      if ( (int)LoadStringResource(5239, v37, Sid, &sourceString) < 0 )
        RoTransformError((unsigned int)Interface, 2147746131LL, 0);
      else
        RoTransformErrorW((unsigned int)Interface, 2147746131LL, (unsigned __int16)sourceString, Sid[0]);
      Interface = -2147221165;
    }
  }
  else
  {
    Interface = -2147024882;
  }
LABEL_57:
  if ( v41 )
    (*(void (__fastcall **)(struct IActivationCatalogContext *))(*(_QWORD *)v47 + 32LL))(v47);
  if ( v43 )
    (*(void (__fastcall **)(struct IActivationCatalogContext *))(*(_QWORD *)v47 + 32LL))(v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v39);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18005f310  push    rbp
0x18005f312  push    rbx
0x18005f313  push    rsi
0x18005f314  push    rdi
0x18005f315  push    r12
0x18005f317  push    r13
0x18005f319  push    r14
0x18005f31b  push    r15
0x18005f31d  lea     rbp, [rsp-7]
0x18005f322  sub     rsp, 98h
0x18005f329  mov     rsi, r9
0x18005f32c  mov     r12, r8
0x18005f32f  xor     r9d, r9d
0x18005f332  mov     edi, edx
0x18005f334  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005f33b  mov     r14, rcx
0x18005f33e  jz      short loc_18005F380
0x18005f340  mov     rax, cs:WPP_GLOBAL_Control
0x18005f347  test    byte ptr [rax+1Ch], 8
0x18005f34b  jz      short loc_18005F380
0x18005f34d  mov     eax, [rcx+14h]
0x18005f350  lea     rdx, aCwinrtactivati; "CWinRTActivationStoreCatalog::GetServer"...
0x18005f357  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18005f35b  mov     r9d, 3
0x18005f361  lea     rax, aGetserverinfoF; "GetServerInfo for %ws in scope %!Window"...
0x18005f368  mov     [rsp+0D0h+var_A8], rsi
0x18005f36d  mov     r8d, 1EBh
0x18005f373  mov     [rsp+0D0h+var_B0], rax
0x18005f378  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope)
0x18005f37d  xor     r9d, r9d
0x18005f380  mov     r13, [rbp+3Fh+sourceString]
0x18005f384  lea     r15, Class
0x18005f38b  mov     [rbp+3Fh+var_80], r9
0x18005f38f  mov     eax, 0FFFFFFFFh
0x18005f394  mov     [rbp+3Fh+string], r9
0x18005f398  mov     [rbp+3Fh+arg_0], r9
0x18005f39c  mov     [rbp+3Fh+var_58], r9
0x18005f3a0  mov     [rbp+3Fh+var_70], r9
0x18005f3a4  mov     [rbp+3Fh+var_60], r9
0x18005f3a8  test    r13, r13
0x18005f3ab  jz      short loc_18005F402
0x18005f3ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005f3b1  inc     rbx
0x18005f3b4  cmp     [r13+rbx*2+0], r9w
0x18005f3ba  jnz     short loc_18005F3B1
0x18005f3bc  cmp     rbx, rax
0x18005f3bf  ja      loc_18005F449
0x18005f3c5  xor     ecx, ecx; string
0x18005f3c7  call    cs:__imp_WindowsDeleteString
0x18005f3ce  nop     dword ptr [rax+rax+00h]
0x18005f3d3  mov     edx, ebx; length
0x18005f3d5  mov     [rbp+3Fh+string], 0
0x18005f3dd  lea     r8, [rbp+3Fh+string]; string
0x18005f3e1  mov     rcx, r13; sourceString
0x18005f3e4  call    cs:__imp_WindowsCreateString
0x18005f3eb  nop     dword ptr [rax+rax+00h]
0x18005f3f0  xor     r9d, r9d
0x18005f3f3  mov     ebx, eax
0x18005f3f5  test    eax, eax
0x18005f3f7  js      loc_18005F523
0x18005f3fd  mov     eax, 0FFFFFFFFh
0x18005f402  test    rsi, rsi
0x18005f405  jz      short loc_18005F45A
0x18005f407  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005f40b  inc     rbx
0x18005f40e  cmp     [rsi+rbx*2], r9w
0x18005f413  jnz     short loc_18005F40B
0x18005f415  cmp     rbx, rax
0x18005f418  ja      short loc_18005F453
0x18005f41a  mov     rcx, [rbp+3Fh+var_80]; string
0x18005f41e  call    cs:__imp_WindowsDeleteString
0x18005f425  nop     dword ptr [rax+rax+00h]
0x18005f42a  mov     edx, ebx; length
0x18005f42c  mov     [rbp+3Fh+var_80], 0
0x18005f434  lea     r8, [rbp+3Fh+var_80]; string
0x18005f438  mov     rcx, rsi; sourceString
0x18005f43b  call    cs:__imp_WindowsCreateString
0x18005f442  nop     dword ptr [rax+rax+00h]
0x18005f447  jmp     short loc_18005F469
0x18005f449  mov     ebx, 80070216h
0x18005f44e  jmp     loc_18005F523
0x18005f453  mov     ebx, 80070216h
0x18005f458  jmp     short loc_18005F46E
0x18005f45a  xor     r8d, r8d; unsigned int
0x18005f45d  lea     rcx, [rbp+3Fh+var_80]; this
0x18005f461  mov     rdx, r15; unsigned __int16 *
0x18005f464  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18005f469  xor     r9d, r9d
0x18005f46c  mov     ebx, eax
0x18005f46e  test    ebx, ebx
0x18005f470  js      loc_18005F523
0x18005f476  cmp     dword ptr [r14+14h], 1
0x18005f47b  mov     [rbp+3Fh+var_50], 0FFFFFFFFFFFFFFFFh
0x18005f483  jnz     short loc_18005F4B6
0x18005f485  test    r12, r12
0x18005f488  jz      short loc_18005F4B6
0x18005f48a  mov     rax, [r12]
0x18005f48e  lea     rdx, [rbp+3Fh+var_50]
0x18005f492  mov     rcx, r12
0x18005f495  mov     rax, [rax+30h]
0x18005f499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f49e  xor     r9d, r9d
0x18005f4a1  mov     ebx, eax
0x18005f4a3  test    eax, eax
0x18005f4a5  js      short loc_18005F523
0x18005f4a7  lea     rcx, [rbp+3Fh+arg_0]
0x18005f4ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f4b0  mov     rdx, [rbp+3Fh+var_50]
0x18005f4b4  jmp     short loc_18005F4C1
0x18005f4b6  lea     rcx, [rbp+3Fh+arg_0]
0x18005f4ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f4bf  xor     edx, edx
0x18005f4c1  mov     ecx, [r14+14h]
0x18005f4c5  lea     rax, [rbp+3Fh+arg_0]
0x18005f4c9  shr     edi, 13h
0x18005f4cc  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x18005f4d3  not     edi
0x18005f4d5  mov     [rsp+0D0h+var_B0], rax
0x18005f4da  and     edi, 10h
0x18005f4dd  mov     r8d, edi
0x18005f4e0  call    cs:__imp_RoGetRegistrationStoreContext
0x18005f4e7  nop     dword ptr [rax+rax+00h]
0x18005f4ec  xor     r9d, r9d
0x18005f4ef  mov     ebx, eax
0x18005f4f1  test    eax, eax
0x18005f4f3  js      short loc_18005F523
0x18005f4f5  mov     rbx, [rbp+3Fh+arg_0]
0x18005f4f9  lea     rcx, [rbp+3Fh+var_58]
0x18005f4fd  mov     rax, [rbx]
0x18005f500  mov     rdi, [rax]
0x18005f503  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f508  lea     r8, [rbp+3Fh+var_58]
0x18005f50c  mov     rcx, rbx
0x18005f50f  lea     rdx, _GUID_6859c7ea_a8f8_47e3_84eb_92c2d56d3ec6
0x18005f516  mov     rax, rdi
0x18005f519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f51e  mov     ebx, eax
0x18005f520  xor     r9d, r9d
0x18005f523  cmp     dword ptr [r14+14h], 1
0x18005f528  mov     edi, 80070002h
0x18005f52d  jnz     loc_18005F67D
0x18005f533  test    r12, r12
0x18005f536  jz      loc_18005F5FF
0x18005f53c  test    ebx, ebx
0x18005f53e  js      short loc_18005F561
0x18005f540  mov     rcx, [rbp+3Fh+arg_0]
0x18005f544  lea     r9, [rbp+3Fh+var_70]
0x18005f548  mov     r8, [rbp+3Fh+var_80]
0x18005f54c  mov     rdx, [rbp+3Fh+string]
0x18005f550  mov     rax, [rcx]
0x18005f553  mov     rax, [rax+58h]
0x18005f557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f55c  mov     ebx, eax
0x18005f55e  xor     r9d, r9d
0x18005f561  mov     rax, [r12]
0x18005f565  lea     r8, [rbp+3Fh+sourceString]
0x18005f569  lea     rdx, [rbp+3Fh+Sid]
0x18005f56d  mov     [rbp+3Fh+Sid], r9
0x18005f571  mov     rcx, r12
0x18005f574  mov     word ptr [rbp+3Fh+sourceString], r9w
0x18005f579  mov     rax, [rax+28h]
0x18005f57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f582  xor     r9d, r9d
0x18005f585  test    ebx, ebx
0x18005f587  jns     loc_18005F88B
0x18005f58d  mov     eax, cs:dword_1801574B8
0x18005f593  test    eax, eax
0x18005f595  jnz     short loc_18005F5B3
0x18005f597  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005f59e  jz      loc_18005F879
0x18005f5a4  xor     ecx, ecx
0x18005f5a6  call    IsWppLevelEnabled
0x18005f5ab  test    al, al
0x18005f5ad  jz      loc_18005F879
0x18005f5b3  mov     rcx, [rbp+3Fh+Sid]; Sid
0x18005f5b7  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x18005f5bb  mov     [rbp+3Fh+StringSid], r9
0x18005f5bf  call    cs:__imp_ConvertSidToStringSidW
0x18005f5c6  nop     dword ptr [rax+rax+00h]
0x18005f5cb  mov     rax, [rbp+3Fh+StringSid]
0x18005f5cf  test    rax, rax
0x18005f5d2  mov     [rsp+0D0h+var_90], ebx
0x18005f5d6  cmovnz  r15, rax
0x18005f5da  mov     eax, [r14+14h]
0x18005f5de  mov     [rsp+0D0h+var_98], r15
0x18005f5e3  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18005f5e7  mov     [rsp+0D0h+var_A8], rsi
0x18005f5ec  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@PEAGJ@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope,ushort *,long)
0x18005f5f1  lea     rcx, [rbp+3Fh+StringSid]
0x18005f5f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005f5fa  jmp     loc_18005F879
0x18005f5ff  test    ebx, ebx
0x18005f601  js      short loc_18005F62E
0x18005f603  mov     rcx, [rbp+3Fh+arg_0]
0x18005f607  lea     r9, [rbp+3Fh+var_70]
0x18005f60b  mov     r8, [rbp+3Fh+var_80]
0x18005f60f  mov     rdx, [rbp+3Fh+string]
0x18005f613  mov     rax, [rcx]
0x18005f616  mov     rax, [rax+58h]
0x18005f61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f61f  mov     ebx, eax
0x18005f621  test    eax, eax
0x18005f623  js      short loc_18005F62E
0x18005f625  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18005f62c  jmp     short loc_18005F657
0x18005f62e  mov     eax, cs:dword_1801574B8
0x18005f634  test    eax, eax
0x18005f636  jnz     short loc_18005F672
0x18005f638  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18005f63f  test    r8d, r8d
0x18005f642  jz      short loc_18005F64F
0x18005f644  xor     ecx, ecx
0x18005f646  call    IsWppLevelEnabled
0x18005f64b  test    al, al
0x18005f64d  jnz     short loc_18005F672
0x18005f64f  test    ebx, ebx
0x18005f651  js      loc_18005F879
0x18005f657  test    r8d, r8d
0x18005f65a  jz      loc_18005F88B
0x18005f660  mov     ecx, 3
0x18005f665  call    IsWppLevelEnabled
0x18005f66a  test    al, al
0x18005f66c  jz      loc_18005F875
0x18005f672  mov     r9d, 244h
0x18005f678  jmp     loc_18005F843
0x18005f67d  mov     r15d, 2
0x18005f683  cmp     [r14+14h], r15d
0x18005f687  jnz     loc_18005F7B5
0x18005f68d  test    ebx, ebx
0x18005f68f  js      short loc_18005F6B2
0x18005f691  mov     rcx, [rbp+3Fh+arg_0]
0x18005f695  lea     r9, [rbp+3Fh+var_70]
0x18005f699  mov     r8, [rbp+3Fh+var_80]
0x18005f69d  mov     rdx, [rbp+3Fh+string]
0x18005f6a1  mov     rax, [rcx]
0x18005f6a4  mov     rax, [rax+58h]
0x18005f6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f6ad  mov     ebx, eax
0x18005f6af  xor     r9d, r9d
0x18005f6b2  cmp     ebx, edi
0x18005f6b4  jnz     short loc_18005F6D3
0x18005f6b6  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005f6bd  jz      loc_18005F881
0x18005f6c3  mov     ecx, r15d
0x18005f6c6  call    IsWppLevelEnabled
0x18005f6cb  test    al, al
0x18005f6cd  jnz     loc_18005F7AA
0x18005f6d3  test    ebx, ebx
0x18005f6d5  jns     loc_18005F78B
0x18005f6db  cmp     ebx, edi
0x18005f6dd  jz      loc_18005F881
0x18005f6e3  mov     eax, cs:dword_1801574B8
0x18005f6e9  test    eax, eax
0x18005f6eb  jnz     loc_18005F7AA
0x18005f6f1  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005f6f8  jz      short loc_18005F709
0x18005f6fa  xor     ecx, ecx
0x18005f6fc  call    IsWppLevelEnabled
0x18005f701  test    al, al
0x18005f703  jnz     loc_18005F7AA
0x18005f709  xor     r14d, r14d
0x18005f70c  mov     rdx, [rbp+3Fh+var_70]
0x18005f710  test    rdx, rdx
0x18005f713  jz      short loc_18005F725
0x18005f715  mov     rcx, [rbp+3Fh+arg_0]
0x18005f719  mov     rax, [rcx]
0x18005f71c  mov     rax, [rax+20h]
0x18005f720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f725  mov     rdx, [rbp+3Fh+var_60]
0x18005f729  test    rdx, rdx
0x18005f72c  jz      short loc_18005F73E
0x18005f72e  mov     rcx, [rbp+3Fh+arg_0]
0x18005f732  mov     rax, [rcx]
0x18005f735  mov     rax, [rax+20h]
0x18005f739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f73e  lea     rcx, [rbp+3Fh+var_58]
0x18005f742  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f747  lea     rcx, [rbp+3Fh+arg_0]
0x18005f74b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005f750  mov     rcx, [rbp+3Fh+string]; string
0x18005f754  call    cs:__imp_WindowsDeleteString
0x18005f75b  nop     dword ptr [rax+rax+00h]
0x18005f760  mov     rcx, [rbp+3Fh+var_80]; string
0x18005f764  mov     [rbp+3Fh+string], r14
0x18005f768  call    cs:__imp_WindowsDeleteString
0x18005f76f  nop     dword ptr [rax+rax+00h]
0x18005f774  mov     eax, ebx
0x18005f776  add     rsp, 98h
0x18005f77d  pop     r15
0x18005f77f  pop     r14
0x18005f781  pop     r13
0x18005f783  pop     r12
0x18005f785  pop     rdi
0x18005f786  pop     rsi
0x18005f787  pop     rbx
0x18005f788  pop     rbp
0x18005f789  retn
0x18005f78b  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005f792  jz      loc_18005F88B
0x18005f798  mov     ecx, 3
  ... truncated ...
```
