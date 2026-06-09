# CWinRTActivationStoreCatalog::GetServerInfo(ulong,IUserToken *,ushort const *,ushort const *,_GUID const &,void * *,IComCatalogSCM *)

- ea: `0x18005a300`
- end: `0x18005a93b`
- name: `?GetServerInfo@CWinRTActivationStoreCatalog@@UEAAJKPEAUIUserToken@@PEBG1AEBU_GUID@@PEAPEAXPEAUIComCatalogSCM@@@Z`
- size: `1595`
- prototype: `int(CWinRTActivationStoreCatalog *__hidden this, unsigned int, struct IUserToken *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, struct IComCatalogSCM *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009350`
- `0x18000d4c4`
- `0x18002e9a0`
- `0x18002f058`
- `0x180034540`
- `0x180042490`
- `0x18005a300`
- `0x18005cf64`
- `0x18007658c`
- `0x1800814c8`
- `0x1800a1198`
- `0x1800d0190`
- `0x1800d0238`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a855`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005a855`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005a58d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005a58d`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x18005a916`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformErrorW` at `0x18005a916`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18005a921`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18005a921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a3b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a3fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a3b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a3fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005a3ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005a415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005a3ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005a415`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005a4b4`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x18005a4b4`

## string_xrefs

- `0x18005a80d`: `onecore\com\combase\catalog\storecat.cxx`

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
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // r9d
  CWinRTActivationStoreCatalog::CServerInfo *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  CWinRTActivationStoreCatalog::CServerInfo *v38; // rax
  CWinRTActivationStoreCatalog::CServerInfo *v39; // rdi
  __int64 v40; // rdx
  struct IActivationCatalogContext **v41; // [rsp+20h] [rbp-71h]
  HSTRING v42; // [rsp+50h] [rbp-41h] BYREF
  HSTRING string; // [rsp+58h] [rbp-39h] BYREF
  struct RegistrationStoreContext::ServerHandleDetail *v44; // [rsp+60h] [rbp-31h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-29h] BYREF
  struct RegistrationStoreContext::ServerForMachineHandleDetail *v46; // [rsp+70h] [rbp-21h] BYREF
  __int64 v47; // [rsp+78h] [rbp-19h] BYREF
  __int64 v48; // [rsp+80h] [rbp-11h] BYREF
  PSID Sid[9]; // [rsp+88h] [rbp-9h] BYREF
  struct IActivationCatalogContext *v50; // [rsp+E0h] [rbp+4Fh] BYREF

  v10 = 0;
  if ( gfEnableTracing && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    ComTraceMessageT<unsigned short const *,enum Windows::Foundation::RegistrationScope>(
      (_DWORD)this,
      (__int64)"CWinRTActivationStoreCatalog::GetServerInfo",
      0x1EBu,
      3,
      (__int64)L"GetServerInfo for %ws in scope %!Windows::Foundation::RegistrationScope!");
    v10 = 0;
  }
  v13 = (WCHAR *)sourceString;
  v14 = (LPWSTR)&Class;
  v42 = 0;
  string = 0;
  v50 = 0;
  v47 = 0;
  v44 = 0;
  v46 = 0;
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
    WindowsDeleteString(v42);
    v42 = 0;
    v19 = WindowsCreateString(a4, v18, &v42);
  }
  else
  {
    v19 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v42, &Class, 0);
  }
  v10 = 0;
  Interface = v19;
LABEL_18:
  if ( Interface < 0 )
    goto LABEL_26;
  v20 = *((_DWORD *)this + 5) == 1;
  v48 = -1;
  if ( v20 && a3 )
  {
    v21 = (*(__int64 (__fastcall **)(struct IUserToken *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v48);
    v10 = 0;
    Interface = v21;
    if ( v21 < 0 )
      goto LABEL_26;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    v22 = v48;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    v22 = 0;
  }
  v41 = &v50;
  RegistrationStoreContext = RoGetRegistrationStoreContext(
                               *((unsigned int *)this + 5),
                               v22,
                               ~(unsigned __int8)(a2 >> 19) & 0x10,
                               &GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2);
  v10 = 0;
  Interface = RegistrationStoreContext;
  if ( RegistrationStoreContext >= 0 )
  {
    v24 = v50;
    v25 = **(__int64 (__fastcall ***)(struct IActivationCatalogContext *, GUID *, __int64 *))v50;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    Interface = v25(v24, &GUID_6859c7ea_a8f8_47e3_84eb_92c2d56d3ec6, &v47);
    v10 = 0;
  }
LABEL_26:
  if ( *((_DWORD *)this + 5) != 1 )
  {
    if ( *((_DWORD *)this + 5) != 2 )
    {
      if ( Interface >= 0 )
      {
        Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, struct RegistrationStoreContext::ServerForMachineHandleDetail **, _QWORD, struct IActivationCatalogContext **))(*(_QWORD *)v50 + 96LL))(
                      v50,
                      v42,
                      &v46,
                      0,
                      v41);
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
          if ( !dword_18014E4B8 && (gfEnableTracing == v10 || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_57;
        }
      }
      v32 = 618;
      goto LABEL_79;
    }
    if ( Interface >= 0 )
    {
      Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ServerHandleDetail **, struct IActivationCatalogContext **))(*(_QWORD *)v50 + 88LL))(
                    v50,
                    string,
                    v42,
                    &v44,
                    v41);
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
          if ( !dword_18014E4B8 && (gfEnableTracing == v10 || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
      Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ServerHandleDetail **, struct IActivationCatalogContext **))(*(_QWORD *)v50 + 88LL))(
                    v50,
                    string,
                    v42,
                    &v44,
                    v41);
    v26 = *(_QWORD *)a3;
    Sid[0] = 0;
    LOWORD(sourceString) = 0;
    (*(void (__fastcall **)(struct IUserToken *, PSID *, PCNZWCH *))(v26 + 40))(a3, Sid, &sourceString);
    v27 = 0;
    if ( Interface < 0 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
          (int)v41,
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
    || (Interface = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, HSTRING, struct RegistrationStoreContext::ServerHandleDetail **, struct IActivationCatalogContext **))(*(_QWORD *)v50 + 88LL))(
                      v50,
                      string,
                      v42,
                      &v44,
                      v41),
        Interface < 0) )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
    && (v38 = (CWinRTActivationStoreCatalog::CServerInfo *)CWinRTActivationStoreCatalog::CServerInfo::CServerInfo(
                                                             v34,
                                                             v35,
                                                             v36,
                                                             v37),
        (v39 = v38) != 0) )
  {
    Interface = CWinRTActivationStoreCatalog::CServerInfo::FinalConstruct(
                  v38,
                  a3,
                  a4,
                  (struct IUserTokenInternal *)v13,
                  a8,
                  v50,
                  v44,
                  v46);
    if ( Interface >= 0 )
      Interface = CWinRTActivationStoreCatalog::CServerInfo::QueryInterface(v39, a6, a7);
    CWinRTActivationStoreCatalog::CServerInfo::Release(v39);
    if ( Interface == -2147024894 || Interface == -2147024883 )
    {
      Sid[0] = 0;
      LOWORD(sourceString) = 0;
      if ( (int)LoadStringResource(5239, v40, Sid, &sourceString) < 0 )
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
  if ( v44 )
    (*(void (__fastcall **)(struct IActivationCatalogContext *))(*(_QWORD *)v50 + 32LL))(v50);
  if ( v46 )
    (*(void (__fastcall **)(struct IActivationCatalogContext *))(*(_QWORD *)v50 + 32LL))(v50);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v42);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18005a300  push    rbp
0x18005a302  push    rbx
0x18005a303  push    rsi
0x18005a304  push    rdi
0x18005a305  push    r12
0x18005a307  push    r13
0x18005a309  push    r14
0x18005a30b  push    r15
0x18005a30d  lea     rbp, [rsp-7]
0x18005a312  sub     rsp, 98h
0x18005a319  mov     rsi, r9
0x18005a31c  mov     r12, r8
0x18005a31f  xor     r9d, r9d
0x18005a322  mov     edi, edx
0x18005a324  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005a32b  mov     r14, rcx
0x18005a32e  jz      short loc_18005A370
0x18005a330  mov     rax, cs:WPP_GLOBAL_Control
0x18005a337  test    byte ptr [rax+1Ch], 8
0x18005a33b  jz      short loc_18005A370
0x18005a33d  mov     eax, [rcx+14h]
0x18005a340  lea     rdx, aCwinrtactivati; "CWinRTActivationStoreCatalog::GetServer"...
0x18005a347  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18005a34b  mov     r9d, 3
0x18005a351  lea     rax, aGetserverinfoF; "GetServerInfo for %ws in scope %!Window"...
0x18005a358  mov     [rsp+0D0h+var_A8], rsi
0x18005a35d  mov     r8d, 1EBh
0x18005a363  mov     [rsp+0D0h+var_B0], rax
0x18005a368  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope)
0x18005a36d  xor     r9d, r9d
0x18005a370  mov     r13, [rbp+3Fh+sourceString]
0x18005a374  lea     r15, Class
0x18005a37b  mov     [rbp+3Fh+var_80], r9
0x18005a37f  mov     eax, 0FFFFFFFFh
0x18005a384  mov     [rbp+3Fh+string], r9
0x18005a388  mov     [rbp+3Fh+arg_0], r9
0x18005a38c  mov     [rbp+3Fh+var_58], r9
0x18005a390  mov     [rbp+3Fh+var_70], r9
0x18005a394  mov     [rbp+3Fh+var_60], r9
0x18005a398  test    r13, r13
0x18005a39b  jz      short loc_18005A3E2
0x18005a39d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005a3a1  inc     rbx
0x18005a3a4  cmp     [r13+rbx*2+0], r9w
0x18005a3aa  jnz     short loc_18005A3A1
0x18005a3ac  cmp     rbx, rax
0x18005a3af  ja      short loc_18005A41D
0x18005a3b1  xor     ecx, ecx; string
0x18005a3b3  call    cs:__imp_WindowsDeleteString
0x18005a3b9  mov     edx, ebx; length
0x18005a3bb  mov     [rbp+3Fh+string], 0
0x18005a3c3  lea     r8, [rbp+3Fh+string]; string
0x18005a3c7  mov     rcx, r13; sourceString
0x18005a3ca  call    cs:__imp_WindowsCreateString
0x18005a3d0  xor     r9d, r9d
0x18005a3d3  mov     ebx, eax
0x18005a3d5  test    eax, eax
0x18005a3d7  js      loc_18005A4F1
0x18005a3dd  mov     eax, 0FFFFFFFFh
0x18005a3e2  test    rsi, rsi
0x18005a3e5  jz      short loc_18005A42E
0x18005a3e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005a3eb  inc     rbx
0x18005a3ee  cmp     [rsi+rbx*2], r9w
0x18005a3f3  jnz     short loc_18005A3EB
0x18005a3f5  cmp     rbx, rax
0x18005a3f8  ja      short loc_18005A427
0x18005a3fa  mov     rcx, [rbp+3Fh+var_80]; string
0x18005a3fe  call    cs:__imp_WindowsDeleteString
0x18005a404  mov     edx, ebx; length
0x18005a406  mov     [rbp+3Fh+var_80], 0
0x18005a40e  lea     r8, [rbp+3Fh+var_80]; string
0x18005a412  mov     rcx, rsi; sourceString
0x18005a415  call    cs:__imp_WindowsCreateString
0x18005a41b  jmp     short loc_18005A43D
0x18005a41d  mov     ebx, 80070216h
0x18005a422  jmp     loc_18005A4F1
0x18005a427  mov     ebx, 80070216h
0x18005a42c  jmp     short loc_18005A442
0x18005a42e  xor     r8d, r8d; unsigned int
0x18005a431  lea     rcx, [rbp+3Fh+var_80]; this
0x18005a435  mov     rdx, r15; unsigned __int16 *
0x18005a438  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18005a43d  xor     r9d, r9d
0x18005a440  mov     ebx, eax
0x18005a442  test    ebx, ebx
0x18005a444  js      loc_18005A4F1
0x18005a44a  cmp     dword ptr [r14+14h], 1
0x18005a44f  mov     [rbp+3Fh+var_50], 0FFFFFFFFFFFFFFFFh
0x18005a457  jnz     short loc_18005A48A
0x18005a459  test    r12, r12
0x18005a45c  jz      short loc_18005A48A
0x18005a45e  mov     rax, [r12]
0x18005a462  lea     rdx, [rbp+3Fh+var_50]
0x18005a466  mov     rcx, r12
0x18005a469  mov     rax, [rax+30h]
0x18005a46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a472  xor     r9d, r9d
0x18005a475  mov     ebx, eax
0x18005a477  test    eax, eax
0x18005a479  js      short loc_18005A4F1
0x18005a47b  lea     rcx, [rbp+3Fh+arg_0]
0x18005a47f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005a484  mov     rdx, [rbp+3Fh+var_50]
0x18005a488  jmp     short loc_18005A495
0x18005a48a  lea     rcx, [rbp+3Fh+arg_0]
0x18005a48e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005a493  xor     edx, edx
0x18005a495  mov     ecx, [r14+14h]
0x18005a499  lea     rax, [rbp+3Fh+arg_0]
0x18005a49d  shr     edi, 13h
0x18005a4a0  lea     r9, _GUID_0fe5a50b_6ca2_47ed_8560_aa7920f978f2
0x18005a4a7  not     edi
0x18005a4a9  mov     [rsp+0D0h+var_B0], rax
0x18005a4ae  and     edi, 10h
0x18005a4b1  mov     r8d, edi
0x18005a4b4  call    cs:__imp_RoGetRegistrationStoreContext
0x18005a4ba  xor     r9d, r9d
0x18005a4bd  mov     ebx, eax
0x18005a4bf  test    eax, eax
0x18005a4c1  js      short loc_18005A4F1
0x18005a4c3  mov     rbx, [rbp+3Fh+arg_0]
0x18005a4c7  lea     rcx, [rbp+3Fh+var_58]
0x18005a4cb  mov     rax, [rbx]
0x18005a4ce  mov     rdi, [rax]
0x18005a4d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005a4d6  lea     r8, [rbp+3Fh+var_58]
0x18005a4da  mov     rcx, rbx
0x18005a4dd  lea     rdx, _GUID_6859c7ea_a8f8_47e3_84eb_92c2d56d3ec6
0x18005a4e4  mov     rax, rdi
0x18005a4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4ec  mov     ebx, eax
0x18005a4ee  xor     r9d, r9d
0x18005a4f1  cmp     dword ptr [r14+14h], 1
0x18005a4f6  mov     edi, 80070002h
0x18005a4fb  jnz     loc_18005A645
0x18005a501  test    r12, r12
0x18005a504  jz      loc_18005A5C7
0x18005a50a  test    ebx, ebx
0x18005a50c  js      short loc_18005A52F
0x18005a50e  mov     rcx, [rbp+3Fh+arg_0]
0x18005a512  lea     r9, [rbp+3Fh+var_70]
0x18005a516  mov     r8, [rbp+3Fh+var_80]
0x18005a51a  mov     rdx, [rbp+3Fh+string]
0x18005a51e  mov     rax, [rcx]
0x18005a521  mov     rax, [rax+58h]
0x18005a525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a52a  mov     ebx, eax
0x18005a52c  xor     r9d, r9d
0x18005a52f  mov     rax, [r12]
0x18005a533  lea     r8, [rbp+3Fh+sourceString]
0x18005a537  lea     rdx, [rbp+3Fh+Sid]
0x18005a53b  mov     [rbp+3Fh+Sid], r9
0x18005a53f  mov     rcx, r12
0x18005a542  mov     word ptr [rbp+3Fh+sourceString], r9w
0x18005a547  mov     rax, [rax+28h]
0x18005a54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a550  xor     r9d, r9d
0x18005a553  test    ebx, ebx
0x18005a555  jns     loc_18005A846
0x18005a55b  mov     eax, cs:dword_18014E4B8
0x18005a561  test    eax, eax
0x18005a563  jnz     short loc_18005A581
0x18005a565  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005a56c  jz      loc_18005A834
0x18005a572  xor     ecx, ecx
0x18005a574  call    IsWppLevelEnabled
0x18005a579  test    al, al
0x18005a57b  jz      loc_18005A834
0x18005a581  mov     rcx, [rbp+3Fh+Sid]; Sid
0x18005a585  lea     rdx, [rbp+3Fh+StringSid]; StringSid
0x18005a589  mov     [rbp+3Fh+StringSid], r9
0x18005a58d  call    cs:__imp_ConvertSidToStringSidW
0x18005a593  mov     rax, [rbp+3Fh+StringSid]
0x18005a597  test    rax, rax
0x18005a59a  mov     [rsp+0D0h+var_90], ebx
0x18005a59e  cmovnz  r15, rax
0x18005a5a2  mov     eax, [r14+14h]
0x18005a5a6  mov     [rsp+0D0h+var_98], r15
0x18005a5ab  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18005a5af  mov     [rsp+0D0h+var_A8], rsi
0x18005a5b4  call    ??$ComTraceMessageT@PEBGW4RegistrationScope@Foundation@Windows@@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBG2W4RegistrationScope@Foundation@Windows@@PEAGJ@Z; ComTraceMessageT<ushort const *,Windows::Foundation::RegistrationScope,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,Windows::Foundation::RegistrationScope,ushort *,long)
0x18005a5b9  lea     rcx, [rbp+3Fh+StringSid]
0x18005a5bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005a5c2  jmp     loc_18005A834
0x18005a5c7  test    ebx, ebx
0x18005a5c9  js      short loc_18005A5F6
0x18005a5cb  mov     rcx, [rbp+3Fh+arg_0]
0x18005a5cf  lea     r9, [rbp+3Fh+var_70]
0x18005a5d3  mov     r8, [rbp+3Fh+var_80]
0x18005a5d7  mov     rdx, [rbp+3Fh+string]
0x18005a5db  mov     rax, [rcx]
0x18005a5de  mov     rax, [rax+58h]
0x18005a5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5e7  mov     ebx, eax
0x18005a5e9  test    eax, eax
0x18005a5eb  js      short loc_18005A5F6
0x18005a5ed  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18005a5f4  jmp     short loc_18005A61F
0x18005a5f6  mov     eax, cs:dword_18014E4B8
0x18005a5fc  test    eax, eax
0x18005a5fe  jnz     short loc_18005A63A
0x18005a600  mov     r8d, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18005a607  test    r8d, r8d
0x18005a60a  jz      short loc_18005A617
0x18005a60c  xor     ecx, ecx
0x18005a60e  call    IsWppLevelEnabled
0x18005a613  test    al, al
0x18005a615  jnz     short loc_18005A63A
0x18005a617  test    ebx, ebx
0x18005a619  js      loc_18005A834
0x18005a61f  test    r8d, r8d
0x18005a622  jz      loc_18005A846
0x18005a628  mov     ecx, 3
0x18005a62d  call    IsWppLevelEnabled
0x18005a632  test    al, al
0x18005a634  jz      loc_18005A830
0x18005a63a  mov     r9d, 244h
0x18005a640  jmp     loc_18005A7FE
0x18005a645  mov     r15d, 2
0x18005a64b  cmp     [r14+14h], r15d
0x18005a64f  jnz     loc_18005A770
0x18005a655  test    ebx, ebx
0x18005a657  js      short loc_18005A67A
0x18005a659  mov     rcx, [rbp+3Fh+arg_0]
0x18005a65d  lea     r9, [rbp+3Fh+var_70]
0x18005a661  mov     r8, [rbp+3Fh+var_80]
0x18005a665  mov     rdx, [rbp+3Fh+string]
0x18005a669  mov     rax, [rcx]
0x18005a66c  mov     rax, [rax+58h]
0x18005a670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a675  mov     ebx, eax
0x18005a677  xor     r9d, r9d
0x18005a67a  cmp     ebx, edi
0x18005a67c  jnz     short loc_18005A69B
0x18005a67e  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005a685  jz      loc_18005A83C
0x18005a68b  mov     ecx, r15d
0x18005a68e  call    IsWppLevelEnabled
0x18005a693  test    al, al
0x18005a695  jnz     loc_18005A765
0x18005a69b  test    ebx, ebx
0x18005a69d  jns     loc_18005A746
0x18005a6a3  cmp     ebx, edi
0x18005a6a5  jz      loc_18005A83C
0x18005a6ab  mov     eax, cs:dword_18014E4B8
0x18005a6b1  test    eax, eax
0x18005a6b3  jnz     loc_18005A765
0x18005a6b9  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005a6c0  jz      short loc_18005A6D1
0x18005a6c2  xor     ecx, ecx
0x18005a6c4  call    IsWppLevelEnabled
0x18005a6c9  test    al, al
0x18005a6cb  jnz     loc_18005A765
0x18005a6d1  xor     r14d, r14d
0x18005a6d4  mov     rdx, [rbp+3Fh+var_70]
0x18005a6d8  test    rdx, rdx
0x18005a6db  jz      short loc_18005A6ED
0x18005a6dd  mov     rcx, [rbp+3Fh+arg_0]
0x18005a6e1  mov     rax, [rcx]
0x18005a6e4  mov     rax, [rax+20h]
0x18005a6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a6ed  mov     rdx, [rbp+3Fh+var_60]
0x18005a6f1  test    rdx, rdx
0x18005a6f4  jz      short loc_18005A706
0x18005a6f6  mov     rcx, [rbp+3Fh+arg_0]
0x18005a6fa  mov     rax, [rcx]
0x18005a6fd  mov     rax, [rax+20h]
0x18005a701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a706  lea     rcx, [rbp+3Fh+var_58]
0x18005a70a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005a70f  lea     rcx, [rbp+3Fh+arg_0]
0x18005a713  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005a718  mov     rcx, [rbp+3Fh+string]; string
0x18005a71c  call    cs:__imp_WindowsDeleteString
0x18005a722  mov     rcx, [rbp+3Fh+var_80]; string
0x18005a726  mov     [rbp+3Fh+string], r14
0x18005a72a  call    cs:__imp_WindowsDeleteString
0x18005a730  mov     eax, ebx
0x18005a732  add     rsp, 98h
0x18005a739  pop     r15
0x18005a73b  pop     r14
0x18005a73d  pop     r13
0x18005a73f  pop     r12
0x18005a741  pop     rdi
0x18005a742  pop     rsi
0x18005a743  pop     rbx
0x18005a744  pop     rbp
0x18005a745  retn
0x18005a746  cmp     cs:?gfEnableTracing@@3HA, r9d; int gfEnableTracing
0x18005a74d  jz      loc_18005A846
0x18005a753  mov     ecx, 3
0x18005a758  call    IsWppLevelEnabled
0x18005a75d  test    al, al
0x18005a75f  jz      loc_18005A846
0x18005a765  mov     r9d, 258h
0x18005a76b  jmp     loc_18005A7FE
0x18005a770  test    ebx, ebx
0x18005a772  js      short loc_18005A791
0x18005a774  mov     rcx, [rbp+3Fh+arg_0]
  ... truncated ...
```
