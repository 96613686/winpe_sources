# CWinRTActivationStoreCatalog::GetRuntimeClassInfo(ulong,IUserToken *,ushort const *,ushort const *,int,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x1800532a0`
- end: `0x18005394a`
- name: `?GetRuntimeClassInfo@CWinRTActivationStoreCatalog@@UEAAJKPEAUIUserToken@@PEBG1HAEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `1706`
- prototype: `int(CWinRTActivationStoreCatalog *__hidden this, unsigned int, struct IUserToken *, const unsigned __int16 *, const unsigned __int16 *, int, const struct _GUID *, void **, struct IComCatalogSCM *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007dbc`
- `0x18000d4c4`
- `0x18002ed50`
- `0x18002f058`
- `0x180034540`
- `0x1800422c0`
- `0x1800532a0`
- `0x180056ed0`
- `0x18005cf64`
- `0x1800814c8`
- `0x1800a1198`
- `0x1800d00a8`
- `0x1800d0190`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005379b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005379b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005351a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005351a`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x1800538a2`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x1800538a2`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800538ad`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800538ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800533c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005390f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053919`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800533c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005390f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053919`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053927`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005338d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800533d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005338d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800533d8`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x180053474`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x180053474`

## string_xrefs

- `0x1800535b6`: `onecore\com\combase\catalog\storecat.cxx`
- `0x18005374f`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800535cc`: `Look up ActivatableClassId entry %ws for package %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`
- `0x18005375c`: `Look up ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`

## pseudocode

```c
__int64 __fastcall CWinRTActivationStoreCatalog::GetRuntimeClassInfo(
        CWinRTActivationStoreCatalog *this,
        unsigned int a2,
        struct IUserToken *a3,
        const unsigned __int16 *a4,
        __int64 sourceString,
        int a6,
        const struct _GUID *a7,
        void **a8,
        struct IComCatalogSCM *StringSid)
{
  void **v9; // r13
  bool v10; // zf
  WCHAR *v14; // r12
  const WCHAR *v15; // r14
  int v16; // r9d
  unsigned __int64 v17; // rbx
  HRESULT v18; // eax
  int RegistrationStoreContext; // ebx
  unsigned __int64 v20; // rbx
  HRESULT v21; // eax
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  struct IComCatalogSCM *v25; // r9
  int v26; // edx
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  CWinRTActivationStoreCatalog::CRuntimeClassInfo *v33; // rax
  CWinRTActivationStoreCatalog::CRuntimeClassInfo *v34; // rax
  int v35; // r8d
  CWinRTActivationStoreCatalog::CRuntimeClassInfo *v36; // rbx
  HRESULT Interface; // edi
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rcx
  unsigned __int16 *v42; // [rsp+20h] [rbp-60h]
  HSTRING v43; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  struct RegistrationStoreContext::ActivatableClassHandleDetail *v45; // [rsp+60h] [rbp-20h] BYREF
  struct IWinRTCatalogInternal *v46; // [rsp+68h] [rbp-18h] BYREF
  struct RegistrationStoreContext::ActivatableClassForMachineHandleDetail *v47; // [rsp+70h] [rbp-10h] BYREF
  PSID Sid; // [rsp+78h] [rbp-8h] BYREF
  struct IActivationCatalogContext *v49; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v50; // [rsp+C8h] [rbp+48h]

  v50 = a2;
  v9 = a8;
  v10 = gfEnableTracing == 0;
  *a8 = 0;
  if ( !v10 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
      (_DWORD)this,
      (unsigned int)"CWinRTActivationStoreCatalog::GetRuntimeClassInfo",
      288,
      3,
      (__int64)L"GetRuntimeClassInfo for %ws in scope %!Windows::Foundation::RegistrationScope!");
  v46 = 0;
  (**(void (__fastcall ***)(struct IComCatalogSCM *, GUID *, struct IWinRTCatalogInternal **))StringSid)(
    StringSid,
    &GUID_22de7513_3849_4767_847d_c66aebc88040,
    &v46);
  v14 = (WCHAR *)sourceString;
  v15 = &Class;
  v16 = 0;
  string = 0;
  v43 = 0;
  v49 = 0;
  v45 = 0;
  v47 = 0;
  if ( sourceString )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(sourceString + 2 * v17) );
    if ( v17 > 0xFFFFFFFF )
    {
      RegistrationStoreContext = -2147024362;
      goto LABEL_25;
    }
    WindowsDeleteString(0);
    string = 0;
    v18 = WindowsCreateString(v14, v17, &string);
    v16 = 0;
    RegistrationStoreContext = v18;
    if ( v18 < 0 )
      goto LABEL_25;
  }
  if ( a4 )
  {
    v20 = -1;
    do
      ++v20;
    while ( a4[v20] );
    if ( v20 > 0xFFFFFFFF )
    {
      RegistrationStoreContext = -2147024362;
      goto LABEL_18;
    }
    WindowsDeleteString(v43);
    v43 = 0;
    v21 = WindowsCreateString(a4, v20, &v43);
  }
  else
  {
    v21 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v43, &Class, 0);
  }
  v16 = 0;
  RegistrationStoreContext = v21;
LABEL_18:
  if ( RegistrationStoreContext < 0 )
    goto LABEL_25;
  v10 = *((_DWORD *)this + 5) == 1;
  sourceString = -1;
  if ( v10 && a3 )
  {
    v22 = (*(__int64 (__fastcall **)(struct IUserToken *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &sourceString);
    v16 = 0;
    RegistrationStoreContext = v22;
    if ( v22 < 0 )
      goto LABEL_25;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v23 = (const unsigned __int16 *)sourceString;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    v23 = 0;
  }
  v42 = (unsigned __int16 *)&v49;
  RegistrationStoreContext = RoGetRegistrationStoreContext(
                               *((unsigned int *)this + 5),
                               v23,
                               ~(unsigned __int8)(v50 >> 19) & 0x10,
                               &GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2);
  v16 = 0;
LABEL_25:
  if ( *((_DWORD *)this + 5) != 1 )
  {
    if ( *((_DWORD *)this + 5) != 2 )
    {
      if ( RegistrationStoreContext >= 0 )
      {
        RegistrationStoreContext = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, struct RegistrationStoreContext::ActivatableClassForMachineHandleDetail **, _QWORD, unsigned __int16 *))(*(_QWORD *)v49 + 80LL))(
                                     v49,
                                     v43,
                                     &v47,
                                     0,
                                     v42);
        v16 = 0;
      }
      v32 = gfEnableTracing;
      if ( RegistrationStoreContext != -2147024894 )
        goto LABEL_65;
      if ( !gfEnableTracing )
        goto LABEL_77;
      if ( !(unsigned __int8)IsWppLevelEnabled(2) )
      {
LABEL_65:
        if ( RegistrationStoreContext >= 0 )
        {
          if ( !v32 || !(unsigned __int8)IsWppLevelEnabled(3) )
            goto LABEL_78;
        }
        else
        {
          if ( RegistrationStoreContext == -2147024894 )
            goto LABEL_77;
          if ( !dword_18014E4B8 && (gfEnableTracing == v16 || !(unsigned __int8)IsWppLevelEnabled(0)) )
          {
LABEL_55:
            if ( RegistrationStoreContext == -2147024883 )
              RegistrationStoreContext = -2147221165;
            goto LABEL_93;
          }
        }
      }
      v31 = 411;
      goto LABEL_74;
    }
    if ( RegistrationStoreContext >= 0 )
    {
      RegistrationStoreContext = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ActivatableClassHandleDetail **, unsigned __int16 *))(*(_QWORD *)v49 + 72LL))(
                                   v49,
                                   string,
                                   v43,
                                   &v45,
                                   v42);
      v16 = 0;
    }
    v30 = gfEnableTracing;
    if ( RegistrationStoreContext != -2147024894 )
      goto LABEL_50;
    if ( !gfEnableTracing )
      goto LABEL_77;
    if ( !(unsigned __int8)IsWppLevelEnabled(2) )
    {
LABEL_50:
      if ( RegistrationStoreContext < 0 )
      {
        if ( RegistrationStoreContext != -2147024894 )
        {
          if ( !dword_18014E4B8 && (gfEnableTracing == v16 || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_55;
          goto LABEL_59;
        }
LABEL_77:
        RegistrationStoreContext = -2147221164;
        goto LABEL_93;
      }
      if ( !v30 || !(unsigned __int8)IsWppLevelEnabled(3) )
        goto LABEL_78;
    }
LABEL_59:
    v31 = 393;
LABEL_74:
    ComTraceHr(
      RegistrationStoreContext,
      "onecore\\com\\combase\\catalog\\storecat.cxx",
      "CWinRTActivationStoreCatalog::GetRuntimeClassInfo",
      v31,
      L"Look up ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!",
      a4,
      *((_DWORD *)this + 5),
      RegistrationStoreContext);
LABEL_75:
    if ( RegistrationStoreContext < 0 )
      goto LABEL_76;
    goto LABEL_78;
  }
  if ( RegistrationStoreContext >= 0 )
    RegistrationStoreContext = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ActivatableClassHandleDetail **, unsigned __int16 *))(*(_QWORD *)v49 + 72LL))(
                                 v49,
                                 string,
                                 v43,
                                 &v45,
                                 v42);
  if ( !a3 )
  {
    if ( RegistrationStoreContext >= 0 )
    {
      if ( !gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(3) )
        goto LABEL_78;
    }
    else if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
    {
      goto LABEL_76;
    }
    ComTraceHr(
      RegistrationStoreContext,
      "onecore\\com\\combase\\catalog\\storecat.cxx",
      "CWinRTActivationStoreCatalog::GetRuntimeClassInfo",
      373,
      L"Look up ActivatableClassId entry %ws for package %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!",
      a4,
      v14,
      *((_DWORD *)this + 5),
      RegistrationStoreContext);
    goto LABEL_75;
  }
  v24 = *(_QWORD *)a3;
  Sid = 0;
  LOWORD(a8) = 0;
  (*(void (__fastcall **)(struct IUserToken *, PSID *, void ***))(v24 + 40))(a3, &Sid, &a8);
  v25 = 0;
  if ( RegistrationStoreContext < 0 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      StringSid = v25;
      ConvertSidToStringSidW(Sid, (LPWSTR *)&StringSid);
      if ( StringSid )
        v15 = (const WCHAR *)StringSid;
      ComTraceMessageT<unsigned short const *,unsigned short const *,enum Windows::Foundation::RegistrationScope,unsigned short *,long>(
        v27,
        v26,
        v28,
        v29,
        (_DWORD)v42,
        (__int64)a4,
        (__int64)v14,
        *((_DWORD *)this + 5),
        (__int64)v15,
        RegistrationStoreContext);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
LABEL_76:
    if ( RegistrationStoreContext == -2147024894 )
      goto LABEL_77;
    goto LABEL_55;
  }
LABEL_78:
  v33 = (CWinRTActivationStoreCatalog::CRuntimeClassInfo *)HeapAlloc(g_hHeap, 0, 0xC0u);
  if ( v33
    && (v34 = (CWinRTActivationStoreCatalog::CRuntimeClassInfo *)CWinRTActivationStoreCatalog::CRuntimeClassInfo::CRuntimeClassInfo(v33),
        (v36 = v34) != 0) )
  {
    Interface = CWinRTActivationStoreCatalog::CRuntimeClassInfo::FinalConstruct(
                  v34,
                  v50,
                  a3,
                  a4,
                  v14,
                  v46,
                  v49,
                  v45,
                  v47,
                  a6 != v35);
    if ( Interface >= 0 )
      Interface = CWinRTActivationStoreCatalog::CRuntimeClassInfo::QueryInterface(v36, a7, v9);
    CWinRTActivationStoreCatalog::CRuntimeClassInfo::Release(v36);
    if ( Interface == -2147024894 || Interface == -2147024883 )
    {
      StringSid = 0;
      LOWORD(a8) = 0;
      v39 = LoadStringResource(5214, v38, &StringSid, &a8);
      v40 = (unsigned int)Interface;
    }
    else
    {
      if ( Interface != -2147221164 )
      {
        RegistrationStoreContext = Interface;
        goto LABEL_93;
      }
      StringSid = 0;
      LOWORD(a8) = 0;
      v39 = LoadStringResource(5215, v38, &StringSid, &a8);
      v40 = 2147746132LL;
    }
    if ( v39 < 0 )
      RoTransformError(v40, 2147746131LL, 0);
    else
      RoTransformErrorW(v40, 2147746131LL, (unsigned __int16)a8, StringSid);
    RegistrationStoreContext = -2147221165;
  }
  else
  {
    RegistrationStoreContext = -2147024882;
  }
LABEL_93:
  (*(void (__fastcall **)(struct IWinRTCatalogInternal *))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v45 )
    (*(void (__fastcall **)(struct IActivationCatalogContext *))(*(_QWORD *)v49 + 32LL))(v49);
  if ( v47 )
    (*(void (__fastcall **)(struct IActivationCatalogContext *))(*(_QWORD *)v49 + 32LL))(v49);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  WindowsDeleteString(0);
  WindowsDeleteString(v43);
  v43 = 0;
  WindowsDeleteString(string);
  return (unsigned int)RegistrationStoreContext;
}

```

## disassembly

```asm
0x1800532a0  mov     [rsp-38h+arg_10], rbx
0x1800532a5  mov     [rsp-38h+arg_8], edx
0x1800532a9  push    rbp
0x1800532aa  push    rsi
0x1800532ab  push    rdi
0x1800532ac  push    r12
0x1800532ae  push    r13
0x1800532b0  push    r14
0x1800532b2  push    r15
0x1800532b4  mov     rbp, rsp
0x1800532b7  sub     rsp, 80h
0x1800532be  mov     r13, [rbp+arg_38]
0x1800532c2  xor     ebx, ebx
0x1800532c4  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800532ca  mov     rdi, r9
0x1800532cd  mov     r15, r8
0x1800532d0  mov     rsi, rcx
0x1800532d3  mov     [r13+0], rbx
0x1800532d7  jz      short loc_180053314
0x1800532d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800532e0  test    byte ptr [rax+1Ch], 8
0x1800532e4  jz      short loc_180053314
0x1800532e6  mov     eax, [rcx+14h]
0x1800532e9  lea     rdx, aCwinrtactivati_1; "CWinRTActivationStoreCatalog::GetRuntim"...
0x1800532f0  mov     dword ptr [rsp+80h+var_50], eax
0x1800532f4  mov     r8d, 120h
0x1800532fa  mov     [rsp+80h+var_58], r9
0x1800532ff  lea     rax, aGetruntimeclas; "GetRuntimeClassInfo for %ws in scope %!"...
0x180053306  lea     r9d, [rbx+3]
0x18005330a  mov     [rsp+80h+var_60], rax
0x18005330f  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope)
0x180053314  mov     rcx, [rbp+StringSid]
0x18005331b  lea     r8, [rbp+var_18]
0x18005331f  lea     rdx, _GUID_22de7513_3849_4767_847d_c66aebc88040
0x180053326  mov     [rbp+var_18], rbx
0x18005332a  mov     rax, [rcx]
0x18005332d  mov     rax, [rax]
0x180053330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053335  mov     r12, [rbp+sourceString]
0x180053339  lea     r14, Class
0x180053340  xor     r9d, r9d
0x180053343  mov     eax, 0FFFFFFFFh
0x180053348  mov     [rbp+string], r9
0x18005334c  mov     [rbp+var_30], r9
0x180053350  mov     [rbp+arg_0], r9
0x180053354  mov     [rbp+var_20], r9
0x180053358  mov     [rbp+var_10], r9
0x18005335c  test    r12, r12
0x18005335f  jz      short loc_1800533A5
0x180053361  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180053365  inc     rbx
0x180053368  cmp     [r12+rbx*2], r9w
0x18005336d  jnz     short loc_180053365
0x18005336f  cmp     rbx, rax
0x180053372  ja      short loc_1800533E0
0x180053374  xor     ecx, ecx; string
0x180053376  call    cs:__imp_WindowsDeleteString
0x18005337c  mov     edx, ebx; length
0x18005337e  mov     [rbp+string], 0
0x180053386  lea     r8, [rbp+string]; string
0x18005338a  mov     rcx, r12; sourceString
0x18005338d  call    cs:__imp_WindowsCreateString
0x180053393  xor     r9d, r9d
0x180053396  mov     ebx, eax
0x180053398  test    eax, eax
0x18005339a  js      loc_18005347F
0x1800533a0  mov     eax, 0FFFFFFFFh
0x1800533a5  test    rdi, rdi
0x1800533a8  jz      short loc_1800533F1
0x1800533aa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800533ae  inc     rbx
0x1800533b1  cmp     [rdi+rbx*2], r9w
0x1800533b6  jnz     short loc_1800533AE
0x1800533b8  cmp     rbx, rax
0x1800533bb  ja      short loc_1800533EA
0x1800533bd  mov     rcx, [rbp+var_30]; string
0x1800533c1  call    cs:__imp_WindowsDeleteString
0x1800533c7  mov     edx, ebx; length
0x1800533c9  mov     [rbp+var_30], 0
0x1800533d1  lea     r8, [rbp+var_30]; string
0x1800533d5  mov     rcx, rdi; sourceString
0x1800533d8  call    cs:__imp_WindowsCreateString
0x1800533de  jmp     short loc_180053400
0x1800533e0  mov     ebx, 80070216h
0x1800533e5  jmp     loc_18005347F
0x1800533ea  mov     ebx, 80070216h
0x1800533ef  jmp     short loc_180053405
0x1800533f1  xor     r8d, r8d; unsigned int
0x1800533f4  lea     rcx, [rbp+var_30]; this
0x1800533f8  mov     rdx, r14; unsigned __int16 *
0x1800533fb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180053400  xor     r9d, r9d
0x180053403  mov     ebx, eax
0x180053405  test    ebx, ebx
0x180053407  js      short loc_18005347F
0x180053409  cmp     dword ptr [rsi+14h], 1
0x18005340d  mov     [rbp+sourceString], 0FFFFFFFFFFFFFFFFh
0x180053415  jnz     short loc_180053447
0x180053417  test    r15, r15
0x18005341a  jz      short loc_180053447
0x18005341c  mov     rax, [r15]
0x18005341f  lea     rdx, [rbp+sourceString]
0x180053423  mov     rcx, r15
0x180053426  mov     rax, [rax+30h]
0x18005342a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005342f  xor     r9d, r9d
0x180053432  mov     ebx, eax
0x180053434  test    eax, eax
0x180053436  js      short loc_18005347F
0x180053438  lea     rcx, [rbp+arg_0]
0x18005343c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053441  mov     rdx, [rbp+sourceString]
0x180053445  jmp     short loc_180053452
0x180053447  lea     rcx, [rbp+arg_0]
0x18005344b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053450  xor     edx, edx
0x180053452  mov     r8d, [rbp+arg_8]
0x180053456  lea     rax, [rbp+arg_0]
0x18005345a  mov     ecx, [rsi+14h]
0x18005345d  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x180053464  shr     r8d, 13h
0x180053468  not     r8d
0x18005346b  mov     [rsp+80h+var_60], rax
0x180053470  and     r8d, 10h
0x180053474  call    cs:__imp_RoGetRegistrationStoreContext
0x18005347a  mov     ebx, eax
0x18005347c  xor     r9d, r9d
0x18005347f  cmp     dword ptr [rsi+14h], 1
0x180053483  jnz     loc_1800535E9
0x180053489  test    ebx, ebx
0x18005348b  js      short loc_1800534AE
0x18005348d  mov     rcx, [rbp+arg_0]
0x180053491  lea     r9, [rbp+var_20]
0x180053495  mov     r8, [rbp+var_30]
0x180053499  mov     rdx, [rbp+string]
0x18005349d  mov     rax, [rcx]
0x1800534a0  mov     rax, [rax+48h]
0x1800534a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534a9  mov     ebx, eax
0x1800534ab  xor     r9d, r9d
0x1800534ae  test    r15, r15
0x1800534b1  jz      loc_18005355E
0x1800534b7  mov     rax, [r15]
0x1800534ba  lea     r8, [rbp+arg_38]
0x1800534be  lea     rdx, [rbp+Sid]
0x1800534c2  mov     [rbp+Sid], r9
0x1800534c6  mov     rcx, r15
0x1800534c9  mov     word ptr [rbp+arg_38], r9w
0x1800534ce  mov     rax, [rax+28h]
0x1800534d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534d7  xor     r9d, r9d
0x1800534da  test    ebx, ebx
0x1800534dc  jns     loc_18005378C
0x1800534e2  mov     eax, cs:dword_18014E4B8
0x1800534e8  test    eax, eax
0x1800534ea  jnz     short loc_180053508
0x1800534ec  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x1800534f3  jz      loc_180053776
0x1800534f9  xor     ecx, ecx
0x1800534fb  call    IsWppLevelEnabled
0x180053500  test    al, al
0x180053502  jz      loc_180053776
0x180053508  mov     rcx, [rbp+Sid]; Sid
0x18005350c  lea     rdx, [rbp+StringSid]; StringSid
0x180053513  mov     [rbp+StringSid], r9
0x18005351a  call    cs:__imp_ConvertSidToStringSidW
0x180053520  mov     rax, [rbp+StringSid]
0x180053527  mov     dword ptr [rsp+80h+var_38], ebx
0x18005352b  test    rax, rax
0x18005352e  cmovnz  r14, rax
0x180053532  mov     eax, [rsi+14h]
0x180053535  mov     [rsp+80h+var_40], r14
0x18005353a  mov     dword ptr [rsp+80h+var_48], eax
0x18005353e  mov     [rsp+80h+var_50], r12
0x180053543  mov     [rsp+80h+var_58], rdi
0x180053548  call    ??$ComTraceMessageT@PEBGPEBGW4RegistrationScope@Foundation@Windows@@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBG22W4RegistrationScope@Foundation@Windows@@PEAGJ@Z; ComTraceMessageT<ushort const *,ushort const *,Windows::Foundation::RegistrationScope,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort const *,Windows::Foundation::RegistrationScope,ushort *,long)
0x18005354d  lea     rcx, [rbp+StringSid]
0x180053554  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180053559  jmp     loc_180053776
0x18005355e  test    ebx, ebx
0x180053560  jns     short loc_180053589
0x180053562  mov     eax, cs:dword_18014E4B8
0x180053568  test    eax, eax
0x18005356a  jnz     short loc_1800535A8
0x18005356c  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180053573  jz      loc_180053776
0x180053579  xor     ecx, ecx
0x18005357b  call    IsWppLevelEnabled
0x180053580  test    al, al
0x180053582  jnz     short loc_1800535A8
0x180053584  jmp     loc_180053776
0x180053589  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180053590  jz      loc_18005378C
0x180053596  mov     ecx, 3
0x18005359b  call    IsWppLevelEnabled
0x1800535a0  test    al, al
0x1800535a2  jz      loc_18005378C
0x1800535a8  mov     eax, [rsi+14h]
0x1800535ab  lea     r8, aCwinrtactivati_1; "CWinRTActivationStoreCatalog::GetRuntim"...
0x1800535b2  mov     dword ptr [rsp+80h+var_40], ebx
0x1800535b6  lea     rdx, aOnecoreComComb_118; "onecore\\com\\combase\\catalog\\storeca"...
0x1800535bd  mov     dword ptr [rsp+80h+var_48], eax
0x1800535c1  mov     r9d, 175h; int
0x1800535c7  mov     [rsp+80h+var_50], r12
0x1800535cc  lea     rax, aLookUpActivata_1; "Look up ActivatableClassId entry %ws fo"...
0x1800535d3  mov     [rsp+80h+var_58], rdi
0x1800535d8  mov     ecx, ebx; int
0x1800535da  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800535df  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800535e4  jmp     loc_180053772
0x1800535e9  mov     r14d, 2
0x1800535ef  cmp     [rsi+14h], r14d
0x1800535f3  jnz     loc_1800536AC
0x1800535f9  test    ebx, ebx
0x1800535fb  js      short loc_18005361E
0x1800535fd  mov     rcx, [rbp+arg_0]
0x180053601  lea     r9, [rbp+var_20]
0x180053605  mov     r8, [rbp+var_30]
0x180053609  mov     rdx, [rbp+string]
0x18005360d  mov     rax, [rcx]
0x180053610  mov     rax, [rax+48h]
0x180053614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053619  mov     ebx, eax
0x18005361b  xor     r9d, r9d
0x18005361e  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x180053625  cmp     ebx, 80070002h
0x18005362b  jnz     short loc_180053642
0x18005362d  test    r8d, r8d
0x180053630  jz      loc_180053782
0x180053636  mov     ecx, r14d
0x180053639  call    IsWppLevelEnabled
0x18005363e  test    al, al
0x180053640  jnz     short loc_1800536A1
0x180053642  test    ebx, ebx
0x180053644  jns     short loc_180053686
0x180053646  cmp     ebx, 80070002h
0x18005364c  jz      loc_180053782
0x180053652  mov     eax, cs:dword_18014E4B8
0x180053658  test    eax, eax
0x18005365a  jnz     short loc_1800536A1
0x18005365c  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180053663  jz      short loc_180053670
0x180053665  xor     ecx, ecx
0x180053667  call    IsWppLevelEnabled
0x18005366c  test    al, al
0x18005366e  jnz     short loc_1800536A1
0x180053670  cmp     ebx, 8007000Dh
0x180053676  jnz     loc_1800538BF
0x18005367c  mov     ebx, 80040153h
0x180053681  jmp     loc_1800538BF
0x180053686  test    r8d, r8d
0x180053689  jz      loc_18005378C
0x18005368f  mov     ecx, 3
0x180053694  call    IsWppLevelEnabled
0x180053699  test    al, al
0x18005369b  jz      loc_18005378C
0x1800536a1  mov     r9d, 189h
0x1800536a7  jmp     loc_180053741
0x1800536ac  test    ebx, ebx
0x1800536ae  js      short loc_1800536CD
0x1800536b0  mov     rcx, [rbp+arg_0]
0x1800536b4  lea     r8, [rbp+var_10]
0x1800536b8  mov     rdx, [rbp+var_30]
0x1800536bc  mov     rax, [rcx]
0x1800536bf  mov     rax, [rax+50h]
0x1800536c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536c8  mov     ebx, eax
0x1800536ca  xor     r9d, r9d
0x1800536cd  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800536d4  cmp     ebx, 80070002h
0x1800536da  jnz     short loc_1800536F1
0x1800536dc  test    r8d, r8d
0x1800536df  jz      loc_180053782
0x1800536e5  mov     ecx, r14d
0x1800536e8  call    IsWppLevelEnabled
0x1800536ed  test    al, al
0x1800536ef  jnz     short loc_18005373B
0x1800536f1  test    ebx, ebx
0x1800536f3  jns     short loc_180053728
0x1800536f5  cmp     ebx, 80070002h
0x1800536fb  jz      loc_180053782
0x180053701  mov     eax, cs:dword_18014E4B8
0x180053707  test    eax, eax
0x180053709  jnz     short loc_18005373B
0x18005370b  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180053712  jz      loc_180053670
0x180053718  xor     ecx, ecx
0x18005371a  call    IsWppLevelEnabled
0x18005371f  test    al, al
0x180053721  jnz     short loc_18005373B
0x180053723  jmp     loc_180053670
0x180053728  test    r8d, r8d
0x18005372b  jz      short loc_18005378C
0x18005372d  mov     ecx, 3
0x180053732  call    IsWppLevelEnabled
0x180053737  test    al, al
0x180053739  jz      short loc_18005378C
0x18005373b  mov     r9d, 19Bh; int
0x180053741  mov     eax, [rsi+14h]
0x180053744  lea     r8, aCwinrtactivati_1; "CWinRTActivationStoreCatalog::GetRuntim"...
  ... truncated ...
```
