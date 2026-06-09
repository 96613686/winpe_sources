# CWinRTActivationStoreCatalog::GetRuntimeClassInfo(ulong,IUserToken *,ushort const *,ushort const *,int,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x180059060`
- end: `0x180059757`
- name: `?GetRuntimeClassInfo@CWinRTActivationStoreCatalog@@UEAAJKPEAUIUserToken@@PEBG1HAEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `1783`
- prototype: `int(CWinRTActivationStoreCatalog *__hidden this, unsigned int, struct IUserToken *, const unsigned __int16 *, const unsigned __int16 *, int, const struct _GUID *, void **, struct IComCatalogSCM *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000875c`
- `0x180024610`
- `0x180025088`
- `0x18002750c`
- `0x180034260`
- `0x18003ca38`
- `0x18004bf70`
- `0x180059060`
- `0x18005c430`
- `0x180061e18`
- `0x1800a660c`
- `0x1800d68b4`
- `0x1800d69a0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059583`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180059583`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800592fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800592fc`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x180059690`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x180059690`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800596a1`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x1800596a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005913a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005972d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005913a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005972d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180059157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800591ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180059157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800591ae`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x180059250`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x180059250`

## string_xrefs

- `0x18005939e`: `onecore\com\combase\catalog\storecat.cxx`
- `0x180059537`: `onecore\com\combase\catalog\storecat.cxx`
- `0x1800593b4`: `Look up ActivatableClassId entry %ws for package %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`
- `0x180059544`: `Look up ActivatableClassId entry %ws in scope %!Windows::Foundation::RegistrationScope!: %!HRESULT!`

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
          if ( !dword_1801574B8 && (gfEnableTracing == v16 || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
          if ( !dword_1801574B8 && (gfEnableTracing == v16 || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
    else if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x180059060  mov     [rsp-38h+arg_10], rbx
0x180059065  mov     [rsp-38h+arg_8], edx
0x180059069  push    rbp
0x18005906a  push    rsi
0x18005906b  push    rdi
0x18005906c  push    r12
0x18005906e  push    r13
0x180059070  push    r14
0x180059072  push    r15
0x180059074  mov     rbp, rsp
0x180059077  sub     rsp, 80h
0x18005907e  mov     r13, [rbp+arg_38]
0x180059082  xor     ebx, ebx
0x180059084  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18005908a  mov     rdi, r9
0x18005908d  mov     r15, r8
0x180059090  mov     rsi, rcx
0x180059093  mov     [r13+0], rbx
0x180059097  jz      short loc_1800590D4
0x180059099  mov     rax, cs:WPP_GLOBAL_Control
0x1800590a0  test    byte ptr [rax+1Ch], 8
0x1800590a4  jz      short loc_1800590D4
0x1800590a6  mov     eax, [rcx+14h]
0x1800590a9  lea     rdx, aCwinrtactivati_1; "CWinRTActivationStoreCatalog::GetRuntim"...
0x1800590b0  mov     dword ptr [rsp+80h+var_50], eax
0x1800590b4  mov     r8d, 120h
0x1800590ba  mov     [rsp+80h+var_58], r9
0x1800590bf  lea     rax, aGetruntimeclas; "GetRuntimeClassInfo for %ws in scope %!"...
0x1800590c6  lea     r9d, [rbx+3]
0x1800590ca  mov     [rsp+80h+var_60], rax
0x1800590cf  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope)
0x1800590d4  mov     rcx, [rbp+StringSid]
0x1800590db  lea     r8, [rbp+var_18]
0x1800590df  lea     rdx, _GUID_22de7513_3849_4767_847d_c66aebc88040
0x1800590e6  mov     [rbp+var_18], rbx
0x1800590ea  mov     rax, [rcx]
0x1800590ed  mov     rax, [rax]
0x1800590f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800590f5  mov     r12, [rbp+sourceString]
0x1800590f9  lea     r14, Class
0x180059100  xor     r9d, r9d
0x180059103  mov     eax, 0FFFFFFFFh
0x180059108  mov     [rbp+string], r9
0x18005910c  mov     [rbp+var_30], r9
0x180059110  mov     [rbp+arg_0], r9
0x180059114  mov     [rbp+var_20], r9
0x180059118  mov     [rbp+var_10], r9
0x18005911c  test    r12, r12
0x18005911f  jz      short loc_180059175
0x180059121  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180059125  inc     rbx
0x180059128  cmp     [r12+rbx*2], r9w
0x18005912d  jnz     short loc_180059125
0x18005912f  cmp     rbx, rax
0x180059132  ja      loc_1800591BC
0x180059138  xor     ecx, ecx; string
0x18005913a  call    cs:__imp_WindowsDeleteString
0x180059141  nop     dword ptr [rax+rax+00h]
0x180059146  mov     edx, ebx; length
0x180059148  mov     [rbp+string], 0
0x180059150  lea     r8, [rbp+string]; string
0x180059154  mov     rcx, r12; sourceString
0x180059157  call    cs:__imp_WindowsCreateString
0x18005915e  nop     dword ptr [rax+rax+00h]
0x180059163  xor     r9d, r9d
0x180059166  mov     ebx, eax
0x180059168  test    eax, eax
0x18005916a  js      loc_180059261
0x180059170  mov     eax, 0FFFFFFFFh
0x180059175  test    rdi, rdi
0x180059178  jz      short loc_1800591CD
0x18005917a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005917e  inc     rbx
0x180059181  cmp     [rdi+rbx*2], r9w
0x180059186  jnz     short loc_18005917E
0x180059188  cmp     rbx, rax
0x18005918b  ja      short loc_1800591C6
0x18005918d  mov     rcx, [rbp+var_30]; string
0x180059191  call    cs:__imp_WindowsDeleteString
0x180059198  nop     dword ptr [rax+rax+00h]
0x18005919d  mov     edx, ebx; length
0x18005919f  mov     [rbp+var_30], 0
0x1800591a7  lea     r8, [rbp+var_30]; string
0x1800591ab  mov     rcx, rdi; sourceString
0x1800591ae  call    cs:__imp_WindowsCreateString
0x1800591b5  nop     dword ptr [rax+rax+00h]
0x1800591ba  jmp     short loc_1800591DC
0x1800591bc  mov     ebx, 80070216h
0x1800591c1  jmp     loc_180059261
0x1800591c6  mov     ebx, 80070216h
0x1800591cb  jmp     short loc_1800591E1
0x1800591cd  xor     r8d, r8d; unsigned int
0x1800591d0  lea     rcx, [rbp+var_30]; this
0x1800591d4  mov     rdx, r14; unsigned __int16 *
0x1800591d7  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800591dc  xor     r9d, r9d
0x1800591df  mov     ebx, eax
0x1800591e1  test    ebx, ebx
0x1800591e3  js      short loc_180059261
0x1800591e5  cmp     dword ptr [rsi+14h], 1
0x1800591e9  mov     [rbp+sourceString], 0FFFFFFFFFFFFFFFFh
0x1800591f1  jnz     short loc_180059223
0x1800591f3  test    r15, r15
0x1800591f6  jz      short loc_180059223
0x1800591f8  mov     rax, [r15]
0x1800591fb  lea     rdx, [rbp+sourceString]
0x1800591ff  mov     rcx, r15
0x180059202  mov     rax, [rax+30h]
0x180059206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005920b  xor     r9d, r9d
0x18005920e  mov     ebx, eax
0x180059210  test    eax, eax
0x180059212  js      short loc_180059261
0x180059214  lea     rcx, [rbp+arg_0]
0x180059218  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005921d  mov     rdx, [rbp+sourceString]
0x180059221  jmp     short loc_18005922E
0x180059223  lea     rcx, [rbp+arg_0]
0x180059227  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005922c  xor     edx, edx
0x18005922e  mov     r8d, [rbp+arg_8]
0x180059232  lea     rax, [rbp+arg_0]
0x180059236  mov     ecx, [rsi+14h]
0x180059239  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x180059240  shr     r8d, 13h
0x180059244  not     r8d
0x180059247  mov     [rsp+80h+var_60], rax
0x18005924c  and     r8d, 10h
0x180059250  call    cs:__imp_RoGetRegistrationStoreContext
0x180059257  nop     dword ptr [rax+rax+00h]
0x18005925c  mov     ebx, eax
0x18005925e  xor     r9d, r9d
0x180059261  cmp     dword ptr [rsi+14h], 1
0x180059265  jnz     loc_1800593D1
0x18005926b  test    ebx, ebx
0x18005926d  js      short loc_180059290
0x18005926f  mov     rcx, [rbp+arg_0]
0x180059273  lea     r9, [rbp+var_20]
0x180059277  mov     r8, [rbp+var_30]
0x18005927b  mov     rdx, [rbp+string]
0x18005927f  mov     rax, [rcx]
0x180059282  mov     rax, [rax+48h]
0x180059286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005928b  mov     ebx, eax
0x18005928d  xor     r9d, r9d
0x180059290  test    r15, r15
0x180059293  jz      loc_180059346
0x180059299  mov     rax, [r15]
0x18005929c  lea     r8, [rbp+arg_38]
0x1800592a0  lea     rdx, [rbp+Sid]
0x1800592a4  mov     [rbp+Sid], r9
0x1800592a8  mov     rcx, r15
0x1800592ab  mov     word ptr [rbp+arg_38], r9w
0x1800592b0  mov     rax, [rax+28h]
0x1800592b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800592b9  xor     r9d, r9d
0x1800592bc  test    ebx, ebx
0x1800592be  jns     loc_180059574
0x1800592c4  mov     eax, cs:dword_1801574B8
0x1800592ca  test    eax, eax
0x1800592cc  jnz     short loc_1800592EA
0x1800592ce  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x1800592d5  jz      loc_18005955E
0x1800592db  xor     ecx, ecx
0x1800592dd  call    IsWppLevelEnabled
0x1800592e2  test    al, al
0x1800592e4  jz      loc_18005955E
0x1800592ea  mov     rcx, [rbp+Sid]; Sid
0x1800592ee  lea     rdx, [rbp+StringSid]; StringSid
0x1800592f5  mov     [rbp+StringSid], r9
0x1800592fc  call    cs:__imp_ConvertSidToStringSidW
0x180059303  nop     dword ptr [rax+rax+00h]
0x180059308  mov     rax, [rbp+StringSid]
0x18005930f  mov     dword ptr [rsp+80h+var_38], ebx
0x180059313  test    rax, rax
0x180059316  cmovnz  r14, rax
0x18005931a  mov     eax, [rsi+14h]
0x18005931d  mov     [rsp+80h+var_40], r14
0x180059322  mov     dword ptr [rsp+80h+var_48], eax
0x180059326  mov     [rsp+80h+var_50], r12
0x18005932b  mov     [rsp+80h+var_58], rdi
0x180059330  call    ??$ComTraceMessageT@PEBGPEBGW4RegistrationScope@Foundation@Windows@@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBG22W4RegistrationScope@Foundation@Windows@@PEAGJ@Z; ComTraceMessageT<ushort const *,ushort const *,Windows::Foundation::RegistrationScope,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort const *,Windows::Foundation::RegistrationScope,ushort *,long)
0x180059335  lea     rcx, [rbp+StringSid]
0x18005933c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180059341  jmp     loc_18005955E
0x180059346  test    ebx, ebx
0x180059348  jns     short loc_180059371
0x18005934a  mov     eax, cs:dword_1801574B8
0x180059350  test    eax, eax
0x180059352  jnz     short loc_180059390
0x180059354  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005935b  jz      loc_18005955E
0x180059361  xor     ecx, ecx
0x180059363  call    IsWppLevelEnabled
0x180059368  test    al, al
0x18005936a  jnz     short loc_180059390
0x18005936c  jmp     loc_18005955E
0x180059371  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x180059378  jz      loc_180059574
0x18005937e  mov     ecx, 3
0x180059383  call    IsWppLevelEnabled
0x180059388  test    al, al
0x18005938a  jz      loc_180059574
0x180059390  mov     eax, [rsi+14h]
0x180059393  lea     r8, aCwinrtactivati_1; "CWinRTActivationStoreCatalog::GetRuntim"...
0x18005939a  mov     dword ptr [rsp+80h+var_40], ebx
0x18005939e  lea     rdx, aOnecoreComComb_118; "onecore\\com\\combase\\catalog\\storeca"...
0x1800593a5  mov     dword ptr [rsp+80h+var_48], eax
0x1800593a9  mov     r9d, 175h; int
0x1800593af  mov     [rsp+80h+var_50], r12
0x1800593b4  lea     rax, aLookUpActivata_1; "Look up ActivatableClassId entry %ws fo"...
0x1800593bb  mov     [rsp+80h+var_58], rdi
0x1800593c0  mov     ecx, ebx; int
0x1800593c2  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800593c7  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800593cc  jmp     loc_18005955A
0x1800593d1  mov     r14d, 2
0x1800593d7  cmp     [rsi+14h], r14d
0x1800593db  jnz     loc_180059494
0x1800593e1  test    ebx, ebx
0x1800593e3  js      short loc_180059406
0x1800593e5  mov     rcx, [rbp+arg_0]
0x1800593e9  lea     r9, [rbp+var_20]
0x1800593ed  mov     r8, [rbp+var_30]
0x1800593f1  mov     rdx, [rbp+string]
0x1800593f5  mov     rax, [rcx]
0x1800593f8  mov     rax, [rax+48h]
0x1800593fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059401  mov     ebx, eax
0x180059403  xor     r9d, r9d
0x180059406  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18005940d  cmp     ebx, 80070002h
0x180059413  jnz     short loc_18005942A
0x180059415  test    r8d, r8d
0x180059418  jz      loc_18005956A
0x18005941e  mov     ecx, r14d
0x180059421  call    IsWppLevelEnabled
0x180059426  test    al, al
0x180059428  jnz     short loc_180059489
0x18005942a  test    ebx, ebx
0x18005942c  jns     short loc_18005946E
0x18005942e  cmp     ebx, 80070002h
0x180059434  jz      loc_18005956A
0x18005943a  mov     eax, cs:dword_1801574B8
0x180059440  test    eax, eax
0x180059442  jnz     short loc_180059489
0x180059444  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005944b  jz      short loc_180059458
0x18005944d  xor     ecx, ecx
0x18005944f  call    IsWppLevelEnabled
0x180059454  test    al, al
0x180059456  jnz     short loc_180059489
0x180059458  cmp     ebx, 8007000Dh
0x18005945e  jnz     loc_1800596B9
0x180059464  mov     ebx, 80040153h
0x180059469  jmp     loc_1800596B9
0x18005946e  test    r8d, r8d
0x180059471  jz      loc_180059574
0x180059477  mov     ecx, 3
0x18005947c  call    IsWppLevelEnabled
0x180059481  test    al, al
0x180059483  jz      loc_180059574
0x180059489  mov     r9d, 189h
0x18005948f  jmp     loc_180059529
0x180059494  test    ebx, ebx
0x180059496  js      short loc_1800594B5
0x180059498  mov     rcx, [rbp+arg_0]
0x18005949c  lea     r8, [rbp+var_10]
0x1800594a0  mov     rdx, [rbp+var_30]
0x1800594a4  mov     rax, [rcx]
0x1800594a7  mov     rax, [rax+50h]
0x1800594ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594b0  mov     ebx, eax
0x1800594b2  xor     r9d, r9d
0x1800594b5  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x1800594bc  cmp     ebx, 80070002h
0x1800594c2  jnz     short loc_1800594D9
0x1800594c4  test    r8d, r8d
0x1800594c7  jz      loc_18005956A
0x1800594cd  mov     ecx, r14d
0x1800594d0  call    IsWppLevelEnabled
0x1800594d5  test    al, al
0x1800594d7  jnz     short loc_180059523
0x1800594d9  test    ebx, ebx
0x1800594db  jns     short loc_180059510
0x1800594dd  cmp     ebx, 80070002h
0x1800594e3  jz      loc_18005956A
0x1800594e9  mov     eax, cs:dword_1801574B8
0x1800594ef  test    eax, eax
0x1800594f1  jnz     short loc_180059523
0x1800594f3  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x1800594fa  jz      loc_180059458
0x180059500  xor     ecx, ecx
0x180059502  call    IsWppLevelEnabled
0x180059507  test    al, al
0x180059509  jnz     short loc_180059523
0x18005950b  jmp     loc_180059458
0x180059510  test    r8d, r8d
0x180059513  jz      short loc_180059574
0x180059515  mov     ecx, 3
  ... truncated ...
```
