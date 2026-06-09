# CWindowsLiveProvider::GetProviderPropertyStore(IPropertyStore * *)

- ea: `0x180016800`
- end: `0x180016b71`
- name: `?GetProviderPropertyStore@CWindowsLiveProvider@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `881`
- prototype: `__int64 __fastcall(CWindowsLiveProvider *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003054`
- `0x1800039c8`
- `0x180003cf0`
- `0x180004b00`
- `0x180006aa4`
- `0x1800090c0`
- `0x180009630`
- `0x18000bcc4`
- `0x18000fd70`
- `0x180010b80`
- `0x180016800`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016930`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016a73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016b2a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016a73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016b2a`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800168e3`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800168e3`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180016942`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180016942`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWindowsLiveProvider::GetProviderPropertyStore(
        CWindowsLiveProvider *this,
        struct IPropertyStore **a2)
{
  __int64 v3; // rdx
  unsigned __int16 *v4; // rbx
  int *v5; // rdi
  __int64 v6; // rbx
  struct IPropertyStore *v7; // rax
  unsigned int v8; // ebx
  void *ppv; // [rsp+20h] [rbp-78h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-70h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v13[4]; // [rsp+48h] [rbp-50h] BYREF
  int v14; // [rsp+68h] [rbp-30h] BYREF
  __int64 v15; // [rsp+70h] [rbp-28h] BYREF
  CPassportException *v16; // [rsp+78h] [rbp-20h] BYREF
  ATL::CAtlException *v17; // [rsp+80h] [rbp-18h] BYREF
  int inited; // [rsp+B0h] [rbp+18h] BYREF
  unsigned __int16 *Src; // [rsp+B8h] [rbp+20h] BYREF

  inited = 0;
  memset(&pvar, 0, sizeof(pvar));
  v13[0] = "CWindowsLiveProvider::GetProviderPropertyStore";
  v13[1] = &inited;
  v13[2] = 0;
  v13[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::GetProviderPropertyStore",
    (const char *)0x397,
    0,
    0);
  Src = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  memset(&pvar, 0, sizeof(pvar));
  if ( !a2 )
  {
    inited = -2147024809;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Src);
    CTraceFuncW<long>::~CTraceFuncW<long>(v13);
    goto LABEL_32;
  }
  ppszPath = 0;
  inited = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
  if ( inited < 0 )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Src);
    CTraceFuncW<long>::~CTraceFuncW<long>(v13);
    goto LABEL_32;
  }
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &Src,
      L"%s\\IdentityCRL\\",
      ppszPath);
    CoTaskMemFree(ppszPath);
    inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
    if ( inited >= 0 )
    {
      v3 = *(_QWORD *)ATL::operator+(&v15, &Src, L"WLive48x48.png");
      v4 = Src;
      v5 = (int *)(Src - 12);
      if ( (unsigned __int16 *)(v3 - 24) != Src - 12 )
      {
        if ( v5[4] >= 0 && *(_QWORD *)(v3 - 24) == *(_QWORD *)v5 )
        {
          v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v5);
          v4 = (unsigned __int16 *)(v6 + 24);
          Src = v4;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&Src, v3, *(unsigned int *)(v3 - 16));
          v4 = Src;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
      inited = InitPropVariantFromString(v4, &pvar);
      if ( inited < 0 )
      {
        ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
        CTraceFuncW<long>::~CTraceFuncW<long>(v13);
        goto LABEL_32;
      }
      inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                 ppv,
                 &PKEY_IdentityProvider_Picture,
                 &pvar);
      if ( inited >= 0 )
      {
        PropVariantClear((PROPVARIANT *)&pvar);
        inited = InitPropVariantFromString(L"MicrosoftAccount", &pvar);
        if ( inited >= 0 )
        {
          inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                     ppv,
                     &PKEY_IdentityProvider_Name,
                     &pvar);
          if ( inited >= 0 )
          {
            v7 = (struct IPropertyStore *)ppv;
            ppv = 0;
            *a2 = v7;
          }
        }
      }
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Src);
    CTraceFuncW<long>::~CTraceFuncW<long>(v13);
  }
  catch ( CPassportException *v16 )
  {
    inited = *((_DWORD *)v16 + 2);
    if ( inited >= 0 )
      inited = -2147418113;
  }
  catch ( ATL::CAtlException *v17 )
  {
    inited = *(_DWORD *)v17;
    if ( inited >= 0 )
      inited = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    inited = -2147024882;
  }
  catch ( long v14 )
  {
    inited = v14;
    if ( v14 >= 0 )
      inited = -2147418113;
  }
LABEL_32:
  PropVariantClear((PROPVARIANT *)&pvar);
  v8 = ErrorHandlingUtilities::MapInternalErrorToExternal(inited, 0, 0);
  if ( ppv )
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppv + 16LL))(ppv, *(_QWORD *)ppv);
  return v8;
}

```

## disassembly

```asm
0x180016800  mov     r11, rsp
0x180016803  mov     [r11+8], rbx
0x180016807  mov     [r11+10h], rsi
0x18001680b  push    rdi
0x18001680c  sub     rsp, 90h
0x180016813  mov     rsi, rdx
0x180016816  mov     dword ptr [r11+18h], 0
0x18001681e  mov     qword ptr [r11-78h], 0
0x180016826  xorps   xmm0, xmm0
0x180016829  xor     eax, eax
0x18001682b  movups  xmmword ptr [rsp+98h+pvar], xmm0
0x180016830  mov     [r11-58h], rax
0x180016834  lea     rdx, aCwindowslivepr_11; "CWindowsLiveProvider::GetProviderProper"...
0x18001683b  mov     [r11-50h], rdx
0x18001683f  lea     rax, [r11+18h]
0x180016843  mov     [r11-48h], rax
0x180016847  mov     qword ptr [r11-40h], 0
0x18001684f  mov     qword ptr [r11-38h], 0
0x180016857  xor     r9d, r9d; unsigned int
0x18001685a  mov     r8d, 397h; char *
0x180016860  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180016867  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001686c  nop
0x18001686d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016874  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001687b  mov     rax, [rax+18h]
0x18001687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016884  add     rax, 18h
0x180016888  mov     [rsp+98h+Src], rax
0x180016890  xorps   xmm0, xmm0
0x180016893  xor     eax, eax
0x180016895  movups  xmmword ptr [rsp+98h+pvar], xmm0
0x18001689a  mov     [rsp+98h+var_58], rax
0x18001689f  test    rsi, rsi
0x1800168a2  jnz     short loc_1800168CD
0x1800168a4  mov     [rsp+98h+arg_10], 80070057h
0x1800168af  lea     rcx, [rsp+98h+Src]; void *
0x1800168b7  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800168bc  nop
0x1800168bd  lea     rcx, [rsp+98h+var_50]
0x1800168c2  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800168c7  nop
0x1800168c8  jmp     loc_180016B25
0x1800168cd  mov     [rsp+98h+ppszPath], rax
0x1800168d2  lea     r9, [rsp+98h+ppszPath]; ppszPath
0x1800168d7  xor     r8d, r8d; hToken
0x1800168da  xor     edx, edx; dwFlags
0x1800168dc  lea     rcx, FOLDERID_Windows; rfid
0x1800168e3  call    cs:__imp_SHGetKnownFolderPath
0x1800168e9  mov     [rsp+98h+arg_10], eax
0x1800168f0  test    eax, eax
0x1800168f2  jns     short loc_180016912
0x1800168f4  lea     rcx, [rsp+98h+Src]; void *
0x1800168fc  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180016901  nop
0x180016902  lea     rcx, [rsp+98h+var_50]
0x180016907  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001690c  nop
0x18001690d  jmp     loc_180016B25
0x180016912  mov     r8, [rsp+98h+ppszPath]
0x180016917  lea     rdx, aSIdentitycrl; "%s\\IdentityCRL\\"
0x18001691e  lea     rcx, [rsp+98h+Src]
0x180016926  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001692b  mov     rcx, [rsp+98h+ppszPath]; pv
0x180016930  call    cs:__imp_CoTaskMemFree
0x180016936  lea     rdx, [rsp+98h+ppv]; ppv
0x18001693b  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180016942  call    cs:__imp_PSCreateMemoryPropertyStore
0x180016948  mov     [rsp+98h+arg_10], eax
0x18001694f  test    eax, eax
0x180016951  jns     short loc_180016971
0x180016953  lea     rcx, [rsp+98h+Src]; void *
0x18001695b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180016960  nop
0x180016961  lea     rcx, [rsp+98h+var_50]
0x180016966  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001696b  nop
0x18001696c  jmp     loc_180016B25
0x180016971  lea     r8, aWlive48x48Png; "WLive48x48.png"
0x180016978  lea     rdx, [rsp+98h+Src]
0x180016980  lea     rcx, [rsp+98h+var_28]
0x180016985  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18001698a  nop
0x18001698b  mov     rdx, [rax]
0x18001698e  lea     rcx, [rdx-18h]
0x180016992  mov     rbx, [rsp+98h+Src]
0x18001699a  lea     rdi, [rbx-18h]
0x18001699e  cmp     rcx, rdi
0x1800169a1  jz      short loc_1800169E8
0x1800169a3  cmp     dword ptr [rdi+10h], 0
0x1800169a7  jl      short loc_1800169CF
0x1800169a9  mov     rax, [rdi]
0x1800169ac  cmp     [rcx], rax
0x1800169af  jnz     short loc_1800169CF
0x1800169b1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800169b6  mov     rbx, rax
0x1800169b9  mov     rcx, rdi; this
0x1800169bc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800169c1  add     rbx, 18h
0x1800169c5  mov     [rsp+98h+Src], rbx
0x1800169cd  jmp     short loc_1800169E8
0x1800169cf  mov     r8d, [rdx-10h]
0x1800169d3  lea     rcx, [rsp+98h+Src]
0x1800169db  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800169e0  mov     rbx, [rsp+98h+Src]
0x1800169e8  mov     rcx, [rsp+98h+var_28]
0x1800169ed  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800169f1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800169f6  lea     rdx, [rsp+98h+pvar]; struct tagPROPVARIANT *
0x1800169fb  mov     rcx, rbx; Src
0x1800169fe  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180016a03  mov     [rsp+98h+arg_10], eax
0x180016a0a  test    eax, eax
0x180016a0c  jns     short loc_180016A28
0x180016a0e  lea     rcx, [rbx-18h]; this
0x180016a12  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180016a17  nop
0x180016a18  lea     rcx, [rsp+98h+var_50]
0x180016a1d  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180016a22  nop
0x180016a23  jmp     loc_180016B25
0x180016a28  mov     rcx, [rsp+98h+ppv]
0x180016a2d  mov     rax, [rcx]
0x180016a30  lea     r8, [rsp+98h+pvar]
0x180016a35  lea     rdx, PKEY_IdentityProvider_Picture
0x180016a3c  mov     rax, [rax+30h]
0x180016a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a45  mov     [rsp+98h+arg_10], eax
0x180016a4c  test    eax, eax
0x180016a4e  jns     short loc_180016A6E
0x180016a50  lea     rcx, [rsp+98h+Src]; void *
0x180016a58  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180016a5d  nop
0x180016a5e  lea     rcx, [rsp+98h+var_50]
0x180016a63  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180016a68  nop
0x180016a69  jmp     loc_180016B25
0x180016a6e  lea     rcx, [rsp+98h+pvar]; pvar
0x180016a73  call    cs:__imp_PropVariantClear
0x180016a79  lea     rdx, [rsp+98h+pvar]; struct tagPROPVARIANT *
0x180016a7e  lea     rcx, Src; "MicrosoftAccount"
0x180016a85  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180016a8a  mov     [rsp+98h+arg_10], eax
0x180016a91  test    eax, eax
0x180016a93  jns     short loc_180016AB0
0x180016a95  lea     rcx, [rsp+98h+Src]; void *
0x180016a9d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180016aa2  nop
0x180016aa3  lea     rcx, [rsp+98h+var_50]
0x180016aa8  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180016aad  nop
0x180016aae  jmp     short loc_180016B25
0x180016ab0  mov     rcx, [rsp+98h+ppv]
0x180016ab5  mov     rax, [rcx]
0x180016ab8  lea     r8, [rsp+98h+pvar]
0x180016abd  lea     rdx, PKEY_IdentityProvider_Name
0x180016ac4  mov     rax, [rax+30h]
0x180016ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016acd  mov     [rsp+98h+arg_10], eax
0x180016ad4  test    eax, eax
0x180016ad6  jns     short loc_180016AF3
0x180016ad8  lea     rcx, [rsp+98h+Src]; void *
0x180016ae0  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180016ae5  nop
0x180016ae6  lea     rcx, [rsp+98h+var_50]
0x180016aeb  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180016af0  nop
0x180016af1  jmp     short loc_180016B25
0x180016af3  mov     rax, [rsp+98h+ppv]
0x180016af8  mov     [rsp+98h+ppv], 0
0x180016b01  mov     [rsi], rax
0x180016b04  lea     rcx, [rsp+98h+Src]; void *
0x180016b0c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180016b11  nop
0x180016b12  lea     rcx, [rsp+98h+var_50]
0x180016b17  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180016b1c  nop
0x180016b1d  jmp     short loc_180016B25
0x180016b1f  jmp     short loc_180016B25
0x180016b21  jmp     short loc_180016B25
0x180016b23  jmp     short $+2
0x180016b25  lea     rcx, [rsp+98h+pvar]; pvar
0x180016b2a  call    cs:__imp_PropVariantClear
0x180016b30  xor     r8d, r8d; bool *
0x180016b33  xor     edx, edx; bool
0x180016b35  mov     ecx, [rsp+98h+arg_10]; int
0x180016b3c  call    ?MapInternalErrorToExternal@ErrorHandlingUtilities@@SAJJ_NPEA_N@Z; ErrorHandlingUtilities::MapInternalErrorToExternal(long,bool,bool *)
0x180016b41  mov     ebx, eax
0x180016b43  mov     rcx, [rsp+98h+ppv]
0x180016b48  test    rcx, rcx
0x180016b4b  jz      short loc_180016B5A
0x180016b4d  mov     rdx, [rcx]
0x180016b50  mov     rax, [rdx+10h]
0x180016b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b59  nop
0x180016b5a  mov     eax, ebx
0x180016b5c  lea     r11, [rsp+98h+var_8]
0x180016b64  mov     rbx, [r11+10h]
0x180016b68  mov     rsi, [r11+18h]
0x180016b6c  mov     rsp, r11
0x180016b6f  pop     rdi
0x180016b70  retn
```
