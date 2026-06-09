# CPackagedComCatalog::ResolveAndReadTypeLibVersionEntryOld(ComTypeLibVersionRegistrationEntryProperties &,HSTRING__ * *,_GUID const &,CPackagedComCatalog::TypeLibVersion,ulong,bool,bool,CPackagedComCatalog::TypeLibVersion *)

- ea: `0x1800ae8d4`
- end: `0x1800aefbd`
- name: `?ResolveAndReadTypeLibVersionEntryOld@CPackagedComCatalog@@AEAAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAPEAUHSTRING__@@AEBU_GUID@@VTypeLibVersion@1@K_N4PEAV51@@Z`
- size: `1769`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e4590`
- `0x1800e7160`
- `0x1800e8900`

## callees

- `0x18001037c`
- `0x1800210f8`
- `0x18002750c`
- `0x18003b8d0`
- `0x18003c024`
- `0x18003c360`
- `0x18004b0f0`
- `0x18007fbd0`
- `0x1800854fc`
- `0x1800ae8d4`
- `0x1800aefc4`
- `0x1800b7ac0`
- `0x1800dbe44`
- `0x1800dd784`
- `0x1800dd988`
- `0x1800e0100`
- `0x1800e88c4`
- `0x1800ec210`
- `0x1800ec720`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aeab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aecc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aef34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aef5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aeab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aec9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aecc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aef34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aef5b`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800ae95b`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800ae95b`

## string_xrefs

- `0x1800ae974`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ae9d1`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800aea98`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::ResolveAndReadTypeLibVersionEntryOld(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        GUID *a4,
        unsigned int *a5,
        unsigned int a6,
        bool a7,
        char a8,
        __int64 a9)
{
  int RegistrationStoreContext; // eax
  unsigned int v13; // ebx
  HSTRING v14; // rdx
  int InstalledPackagesContaining; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r9
  unsigned int v23; // r15d
  struct OpaqueString *v24; // r10
  struct OpaqueString *v25; // rdi
  __int64 v26; // rcx
  char v27; // bl
  __int64 v28; // rcx
  __int64 v29; // rdx
  struct OpaqueString *v30; // rdx
  __int64 v31; // rax
  unsigned int v32; // eax
  struct _GUID *v33; // xmm6_8
  unsigned int v34; // r15d
  unsigned int v35; // esi
  struct _GUID *v36; // r14
  struct OpaqueString *v37; // rdi
  struct OpaqueString *v38; // r10
  char v39; // bl
  __int64 v40; // rcx
  __int64 v41; // rdx
  unsigned int v42; // ecx
  struct OpaqueString *v43; // rdx
  __int64 v44; // rbx
  __int64 v45; // r14
  _QWORD *v46; // r12
  int v48; // [rsp+28h] [rbp-E0h]
  char v49; // [rsp+48h] [rbp-C0h]
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  struct IPackagedComCatalogContext *v51; // [rsp+58h] [rbp-B0h] BYREF
  struct _GUID *v52; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+68h] [rbp-A0h]
  __int64 v54; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v55[4]; // [rsp+78h] [rbp-90h] BYREF
  int v56; // [rsp+7Ch] [rbp-8Ch]
  char v57; // [rsp+80h] [rbp-88h]
  int v58; // [rsp+84h] [rbp-84h]
  char v59; // [rsp+88h] [rbp-80h]
  __int64 v60; // [rsp+90h] [rbp-78h]
  char v61; // [rsp+98h] [rbp-70h]
  __int64 v62; // [rsp+A0h] [rbp-68h]
  char v63; // [rsp+A8h] [rbp-60h]
  __int64 v64; // [rsp+B0h] [rbp-58h]
  char v65; // [rsp+B8h] [rbp-50h]
  __int64 v66; // [rsp+C0h] [rbp-48h]
  __int16 v67; // [rsp+C8h] [rbp-40h]
  char v68; // [rsp+CCh] [rbp-3Ch]
  int v69; // [rsp+D0h] [rbp-38h]
  char v70; // [rsp+D4h] [rbp-34h]
  int v71; // [rsp+D8h] [rbp-30h]
  char v72; // [rsp+DCh] [rbp-2Ch]
  int v73; // [rsp+E0h] [rbp-28h]
  _BYTE v74[4]; // [rsp+E8h] [rbp-20h] BYREF
  int v75; // [rsp+ECh] [rbp-1Ch]
  char v76; // [rsp+F0h] [rbp-18h]
  int v77; // [rsp+F4h] [rbp-14h]
  char v78; // [rsp+F8h] [rbp-10h]
  __int64 v79; // [rsp+100h] [rbp-8h]
  char v80; // [rsp+108h] [rbp+0h]
  __int64 v81; // [rsp+110h] [rbp+8h]
  char v82; // [rsp+118h] [rbp+10h]
  __int64 v83; // [rsp+120h] [rbp+18h]
  char v84; // [rsp+128h] [rbp+20h]
  __int64 v85; // [rsp+130h] [rbp+28h]
  __int16 v86; // [rsp+138h] [rbp+30h]
  char v87; // [rsp+13Ch] [rbp+34h]
  int v88; // [rsp+140h] [rbp+38h]
  char v89; // [rsp+144h] [rbp+3Ch]
  int v90; // [rsp+148h] [rbp+40h]
  char v91; // [rsp+14Ch] [rbp+44h]
  int v92; // [rsp+150h] [rbp+48h]
  __int64 v93; // [rsp+158h] [rbp+50h]
  _QWORD *v94; // [rsp+160h] [rbp+58h]
  struct _GUID *v95; // [rsp+168h] [rbp+60h] BYREF
  unsigned int v96; // [rsp+170h] [rbp+68h]
  _BYTE v97[4]; // [rsp+178h] [rbp+70h] BYREF
  int v98; // [rsp+17Ch] [rbp+74h]
  char v99; // [rsp+180h] [rbp+78h]
  int v100; // [rsp+184h] [rbp+7Ch]
  char v101; // [rsp+188h] [rbp+80h]
  __int64 v102; // [rsp+190h] [rbp+88h]
  char v103; // [rsp+198h] [rbp+90h]
  __int64 v104; // [rsp+1A0h] [rbp+98h]
  char v105; // [rsp+1A8h] [rbp+A0h]
  __int64 v106; // [rsp+1B0h] [rbp+A8h]
  char v107; // [rsp+1B8h] [rbp+B0h]
  __int64 v108; // [rsp+1C0h] [rbp+B8h]
  __int16 v109; // [rsp+1C8h] [rbp+C0h]
  char v110; // [rsp+1CCh] [rbp+C4h]
  int v111; // [rsp+1D0h] [rbp+C8h]
  char v112; // [rsp+1D4h] [rbp+CCh]
  int v113; // [rsp+1D8h] [rbp+D0h]
  char v114; // [rsp+1DCh] [rbp+D4h]
  int v115; // [rsp+1E0h] [rbp+D8h]
  _BYTE v116[128]; // [rsp+1E8h] [rbp+E0h] BYREF
  struct OpaqueString *v117; // [rsp+268h] [rbp+160h]
  __int64 v118; // [rsp+270h] [rbp+168h]
  unsigned __int16 v119[8]; // [rsp+288h] [rbp+180h] BYREF
  int v120; // [rsp+298h] [rbp+190h]
  wil::details::in1diag3 *retaddr; // [rsp+2F0h] [rbp+1E8h]

  v93 = a9;
  *a3 = 0;
  v51 = 0;
  v52 = a4;
  v94 = a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  v13 = RegistrationStoreContext;
  if ( RegistrationStoreContext < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x209F,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)RegistrationStoreContext,
      (int)&v51);
    goto LABEL_56;
  }
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v116);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(
                                  (PackageListBuffer *)v116,
                                  v14,
                                  (__int64)v51,
                                  a4,
                                  a8,
                                  0);
  v13 = InstalledPackagesContaining;
  if ( InstalledPackagesContaining < 0 )
  {
    v16 = (unsigned int)InstalledPackagesContaining;
    v17 = 8360;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)v16,
      v48);
LABEL_6:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v116);
    goto LABEL_56;
  }
  if ( !(_DWORD)v118 )
  {
LABEL_55:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v116);
    v13 = -2147319779;
    goto LABEL_56;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v117,
    (char *)v117 + 32 * (unsigned int)v118,
    (unsigned int)v118,
    MoreRecentlyInstalledByUser);
  v49 = *((_BYTE *)a5 + 8);
  if ( v49 )
  {
    v20 = *a5;
    v120 = 0;
    v48 = a5[1];
    *(_OWORD *)v119 = 0;
    if ( (int)StringCchPrintfW(v119, 0xAu, L"%x.%x", v20) < 0 )
    {
      v13 = -2147024809;
      v17 = 8381;
      v16 = 2147942487LL;
      goto LABEL_5;
    }
    string = 0;
    v21 = Microsoft::WRL::Wrappers::HString::Set<10>(&string, v119);
    v13 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20C0,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v21,
        v48);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_6;
    }
    v23 = 1;
LABEL_14:
    v24 = v117;
    v25 = v117;
    while ( 1 )
    {
      v26 = 32LL * (unsigned int)v118;
      if ( v25 == (struct OpaqueString *)((char *)v24 + v26) )
        break;
      if ( (unsigned __int8)PackageInstalledForScope(v25, v23, (unsigned int)v118, v22) )
      {
        v55[0] = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v61 = 0;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v66 = 0;
        v67 = 0;
        v68 = 0;
        v69 = 0;
        v70 = 0;
        v71 = 0;
        v72 = 0;
        v73 = 0;
        if ( (int)CPackagedComCatalog::ReadTypeLibVersionEntry(
                    (struct ComTypeLibVersionRegistrationEntryProperties *)v55,
                    v51,
                    v25,
                    v52,
                    (const struct OpaqueString *)&string) >= 0 )
        {
          v27 = (_BYTE)v67 != 0 ? HIBYTE(v67) : 0;
          LOBYTE(v28) = RegistrationHasUserScope<ComTypeLibVersionRegistrationEntryProperties>(v55);
          LOBYTE(v29) = v27;
          v13 = 0;
          if ( (unsigned __int8)RegistrationScopeMatchesInstallScope(v28, v29, v23) )
          {
            if ( CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(v55[0] != 0 ? v56 : 0, a6, a7) )
            {
              ComTypeLibVersionRegistrationEntryProperties::operator=(a2, v55);
              v31 = *(_QWORD *)v25;
              *(_QWORD *)v25 = 0;
              *a3 = v31;
              if ( a9 )
              {
                v32 = a5[2];
                *(_QWORD *)a9 = *(_QWORD *)a5;
                *(_DWORD *)(a9 + 8) = v32;
              }
              ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v55);
              WindowsDeleteString(string);
              string = 0;
              goto LABEL_6;
            }
          }
        }
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v55);
        v24 = v117;
      }
      v25 = (struct OpaqueString *)((char *)v25 + 32);
      v30 = (struct OpaqueString *)((char *)v24 + 32 * (unsigned int)v118);
      if ( v25 == v30 )
      {
        if ( v23 == 1 )
        {
          std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
            v24,
            v30,
            (32LL * (unsigned int)v118) >> 5,
            MoreRecentlyInstalledByOneTime);
          v23 = 2;
          goto LABEL_14;
        }
        if ( v23 == 2 )
        {
          std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
            v24,
            v30,
            (32LL * (unsigned int)v118) >> 5,
            MoreRecentlyInstalledByMachine);
          v23 = 0;
          goto LABEL_14;
        }
      }
    }
    if ( a7 )
    {
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_55;
    }
    std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
      v24,
      (char *)v24 + v26,
      (unsigned int)v118,
      MoreRecentlyInstalledByUser);
    WindowsDeleteString(string);
  }
  v33 = *(struct _GUID **)a5;
  v34 = a5[2];
  v97[0] = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v54 = 0;
  if ( !(_DWORD)v118 )
  {
LABEL_54:
    WindowsDeleteString(0);
    ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v97);
    goto LABEL_55;
  }
  v35 = 1;
  v36 = v52;
  v37 = v117;
  do
  {
    if ( (unsigned __int8)PackageInstalledForScope(v37, v35, v18, v19) )
    {
      v52 = 0;
      v86 = 0;
      LOBYTE(v53) = 0;
      v74[0] = 0;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      v81 = 0;
      v82 = 0;
      v83 = 0;
      v84 = 0;
      v85 = 0;
      v87 = 0;
      v88 = 0;
      v89 = 0;
      v90 = 0;
      v91 = 0;
      v92 = 0;
      v95 = v33;
      v96 = v34;
      if ( (int)CPackagedComCatalog::ReadHighestTypeLibVersionEntry(
                  (struct ComTypeLibVersionRegistrationEntryProperties *)v74,
                  v51,
                  v37,
                  v36,
                  (__int64 *)&v95,
                  v49,
                  (__int64)&v52) >= 0 )
      {
        v39 = (_BYTE)v86 != 0 ? HIBYTE(v86) : 0;
        LOBYTE(v40) = RegistrationHasUserScope<ComTypeLibVersionRegistrationEntryProperties>(v74);
        LOBYTE(v41) = v39;
        if ( (unsigned __int8)RegistrationScopeMatchesInstallScope(v40, v41, v35) )
        {
          v42 = *(_BYTE *)a2 ? *(_DWORD *)(a2 + 4) : 0;
          if ( CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(v42, a6, a7) )
          {
            v33 = v52;
            v34 = v53;
            ComTypeLibVersionRegistrationEntryProperties::operator=(v97, v74);
            OpaqueString::operator=(&v54, v37);
          }
        }
      }
      ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v74);
      v38 = v117;
    }
    v37 = (struct OpaqueString *)((char *)v37 + 32);
    v43 = (struct OpaqueString *)((char *)v38 + 32 * (unsigned int)v118);
    if ( v37 == v43 )
    {
      if ( v35 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v38,
          v43,
          (32LL * (unsigned int)v118) >> 5,
          MoreRecentlyInstalledByOneTime);
        v35 = 2;
      }
      else
      {
        if ( v35 != 2 )
          continue;
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v38,
          v43,
          (32LL * (unsigned int)v118) >> 5,
          MoreRecentlyInstalledByMachine);
        v35 = 0;
      }
      v38 = v117;
      v37 = v117;
    }
  }
  while ( v37 != (struct OpaqueString *)((char *)v38 + 32 * (unsigned int)v118) );
  v44 = v54;
  v45 = v93;
  v46 = v94;
  if ( !v54 )
    goto LABEL_54;
  ComTypeLibVersionRegistrationEntryProperties::operator=(a2, v97);
  *v46 = v44;
  if ( v45 )
  {
    *(_QWORD *)v45 = v33;
    *(_DWORD *)(v45 + 8) = v34;
  }
  WindowsDeleteString(0);
  ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v97);
  PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v116);
  v13 = 0;
LABEL_56:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  return v13;
}

```

## disassembly

```asm
0x1800ae8d4  mov     rax, rsp
0x1800ae8d7  mov     [rax+8], rbx
0x1800ae8db  push    rbp
0x1800ae8dc  push    rsi
0x1800ae8dd  push    rdi
0x1800ae8de  push    r12
0x1800ae8e0  push    r13
0x1800ae8e2  push    r14
0x1800ae8e4  push    r15
0x1800ae8e6  lea     rbp, [rax-1E8h]
0x1800ae8ed  sub     rsp, 2B0h
0x1800ae8f4  movaps  xmmword ptr [rax-48h], xmm6
0x1800ae8f8  mov     rax, cs:__security_cookie
0x1800ae8ff  xor     rax, rsp
0x1800ae902  mov     [rbp+1E0h+var_48], rax
0x1800ae909  mov     r14, [rbp+1E0h+arg_40]
0x1800ae910  lea     rcx, [rsp+2E0h+var_290]
0x1800ae915  mov     rsi, [rbp+1E0h+arg_20]
0x1800ae91c  xor     r15d, r15d
0x1800ae91f  mov     [rbp+1E0h+var_190], r14
0x1800ae923  mov     rdi, r9
0x1800ae926  mov     [r8], r15
0x1800ae929  mov     r12, r8
0x1800ae92c  mov     [rsp+2E0h+var_290], r15
0x1800ae931  mov     r13, rdx
0x1800ae934  mov     [rsp+2E0h+var_288], r9
0x1800ae939  mov     [rbp+1E0h+var_188], r8
0x1800ae93d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ae942  xor     edx, edx
0x1800ae944  lea     rax, [rsp+2E0h+var_290]
0x1800ae949  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800ae950  mov     [rsp+2E0h+var_2C0], rax; int
0x1800ae955  xor     r8d, r8d
0x1800ae958  lea     ecx, [rdx+1]
0x1800ae95b  call    cs:__imp_RoGetRegistrationStoreContext
0x1800ae962  nop     dword ptr [rax+rax+00h]
0x1800ae967  mov     ebx, eax
0x1800ae969  test    eax, eax
0x1800ae96b  jns     short loc_1800AE98D
0x1800ae96d  mov     rcx, [rbp+1E8h]; this
0x1800ae974  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ae97b  mov     r9d, eax; char *
0x1800ae97e  mov     edx, 209Fh; void *
0x1800ae983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae988  jmp     loc_1800AEF81
0x1800ae98d  lea     rcx, [rbp+1E0h+var_100]; this
0x1800ae994  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x1800ae999  mov     al, [rbp+1E0h+arg_38]
0x1800ae99f  lea     rcx, [rbp+1E0h+var_100]; this
0x1800ae9a6  mov     r8, [rsp+2E0h+var_290]
0x1800ae9ab  mov     r9, rdi
0x1800ae9ae  mov     [rsp+2E0h+var_2B8], r15; PackageFilter *
0x1800ae9b3  mov     byte ptr [rsp+2E0h+var_2C0], al; int
0x1800ae9b7  call    ??$GetInstalledPackagesContainingEntry@UComTypeLibVersionRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x1800ae9bc  mov     ebx, eax
0x1800ae9be  test    eax, eax
0x1800ae9c0  jns     short loc_1800AE9EE
0x1800ae9c2  mov     r9d, eax; char *
0x1800ae9c5  mov     edx, 20A8h; void *
0x1800ae9ca  mov     rcx, [rbp+1E8h]; this
0x1800ae9d1  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ae9d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae9dd  lea     rcx, [rbp+1E0h+var_100]; this
0x1800ae9e4  call    ??1PackageListBuffer@@QEAA@XZ; PackageListBuffer::~PackageListBuffer(void)
0x1800ae9e9  jmp     loc_1800AEF81
0x1800ae9ee  mov     rax, [rbp+1E0h+var_78]
0x1800ae9f5  xor     ebx, ebx
0x1800ae9f7  test    eax, eax
0x1800ae9f9  jz      loc_1800AEF70
0x1800ae9ff  mov     rcx, [rbp+1E0h+var_80]
0x1800aea06  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800aea0d  mov     edx, eax
0x1800aea0f  shl     rdx, 5
0x1800aea13  add     rdx, rcx
0x1800aea16  mov     r8d, eax
0x1800aea19  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800aea1e  mov     al, [rsi+8]
0x1800aea21  mov     byte ptr [rsp+2E0h+var_2A0], al
0x1800aea25  test    al, al
0x1800aea27  jz      loc_1800AECD4
0x1800aea2d  mov     r9d, [rsi]
0x1800aea30  lea     r8, aXX; "%x.%x"
0x1800aea37  xor     eax, eax
0x1800aea39  lea     edx, [rbx+0Ah]; unsigned __int64
0x1800aea3c  mov     [rbp+1E0h+var_50], eax
0x1800aea42  lea     rcx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800aea49  mov     eax, [rsi+4]
0x1800aea4c  xorps   xmm0, xmm0
0x1800aea4f  mov     dword ptr [rsp+2E0h+var_2C0], eax; int
0x1800aea53  movups  xmmword ptr [rbp+1E0h+var_60], xmm0
0x1800aea5a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aea5f  test    eax, eax
0x1800aea61  jns     short loc_1800AEA75
0x1800aea63  mov     ebx, 80070057h
0x1800aea68  mov     edx, 20BDh
0x1800aea6d  mov     r9d, ebx
0x1800aea70  jmp     loc_1800AE9CA
0x1800aea75  lea     rdx, [rbp+1E0h+var_60]
0x1800aea7c  mov     [rsp+2E0h+string], rbx
0x1800aea81  lea     rcx, [rsp+2E0h+string]
0x1800aea86  call    ??$Set@$09@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY09G@Z; Microsoft::WRL::Wrappers::HString::Set<10>(ushort (&)[10])
0x1800aea8b  mov     ebx, eax
0x1800aea8d  test    eax, eax
0x1800aea8f  jns     short loc_1800AEAC7
0x1800aea91  mov     rcx, [rbp+1E8h]; this
0x1800aea98  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800aea9f  mov     r9d, eax; char *
0x1800aeaa2  mov     edx, 20C0h; void *
0x1800aeaa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aeaac  mov     rcx, [rsp+2E0h+string]; string
0x1800aeab1  call    cs:__imp_WindowsDeleteString
0x1800aeab8  nop     dword ptr [rax+rax+00h]
0x1800aeabd  mov     [rsp+2E0h+string], r15
0x1800aeac2  jmp     loc_1800AE9DD
0x1800aeac7  mov     r15d, 1
0x1800aeacd  mov     r10, [rbp+1E0h+var_80]
0x1800aead4  mov     rdi, r10
0x1800aead7  mov     r8d, dword ptr [rbp+1E0h+var_78]
0x1800aeade  mov     ecx, r8d
0x1800aeae1  shl     rcx, 5
0x1800aeae5  lea     rax, [r10+rcx]
0x1800aeae9  cmp     rdi, rax
0x1800aeaec  jz      loc_1800AEC8B
0x1800aeaf2  mov     edx, r15d
0x1800aeaf5  mov     rcx, rdi
0x1800aeaf8  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800aeafd  xor     ebx, ebx
0x1800aeaff  test    al, al
0x1800aeb01  jz      loc_1800AEBCB
0x1800aeb07  mov     r9, [rsp+2E0h+var_288]; struct _GUID *
0x1800aeb0c  lea     rax, [rsp+2E0h+string]
0x1800aeb11  mov     rdx, [rsp+2E0h+var_290]; struct IPackagedComCatalogContext *
0x1800aeb16  lea     rcx, [rsp+2E0h+var_270]; struct ComTypeLibVersionRegistrationEntryProperties *
0x1800aeb1b  mov     r8, rdi; struct OpaqueString *
0x1800aeb1e  mov     [rsp+2E0h+var_2C0], rax; struct OpaqueString *
0x1800aeb23  mov     [rsp+2E0h+var_270], bl
0x1800aeb27  mov     [rsp+2E0h+var_26C], ebx
0x1800aeb2b  mov     [rsp+2E0h+var_268], bl
0x1800aeb2f  mov     [rsp+2E0h+var_264], ebx
0x1800aeb33  mov     [rbp+1E0h+var_260], bl
0x1800aeb36  mov     [rbp+1E0h+var_258], rbx
0x1800aeb3a  mov     [rbp+1E0h+var_250], bl
0x1800aeb3d  mov     [rbp+1E0h+var_248], rbx
0x1800aeb41  mov     [rbp+1E0h+var_240], bl
0x1800aeb44  mov     [rbp+1E0h+var_238], rbx
0x1800aeb48  mov     [rbp+1E0h+var_230], bl
0x1800aeb4b  mov     [rbp+1E0h+var_228], rbx
0x1800aeb4f  mov     [rbp+1E0h+var_220], bx
0x1800aeb53  mov     [rbp+1E0h+var_21C], bl
0x1800aeb56  mov     [rbp+1E0h+var_218], ebx
0x1800aeb59  mov     [rbp+1E0h+var_214], bl
0x1800aeb5c  mov     [rbp+1E0h+var_210], ebx
0x1800aeb5f  mov     [rbp+1E0h+var_20C], bl
0x1800aeb62  mov     [rbp+1E0h+var_208], ebx
0x1800aeb65  call    ?ReadTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2@Z; CPackagedComCatalog::ReadTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &)
0x1800aeb6a  test    eax, eax
0x1800aeb6c  js      short loc_1800AEBBA
0x1800aeb6e  mov     al, byte ptr [rbp+1E0h+var_220]
0x1800aeb71  lea     rcx, [rsp+2E0h+var_270]
0x1800aeb76  neg     al
0x1800aeb78  sbb     bl, bl
0x1800aeb7a  and     bl, byte ptr [rbp+1E0h+var_220+1]
0x1800aeb7d  call    ??$RegistrationHasUserScope@UComTypeLibVersionRegistrationEntryProperties@@@@YA_NAEBUComTypeLibVersionRegistrationEntryProperties@@@Z; RegistrationHasUserScope<ComTypeLibVersionRegistrationEntryProperties>(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800aeb82  mov     cl, al
0x1800aeb84  mov     r8d, r15d
0x1800aeb87  mov     dl, bl
0x1800aeb89  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x1800aeb8e  xor     ebx, ebx
0x1800aeb90  test    al, al
0x1800aeb92  jz      short loc_1800AEBBA
0x1800aeb94  mov     al, [rsp+2E0h+var_270]
0x1800aeb98  mov     r8b, [rbp+1E0h+arg_30]; bool
0x1800aeb9f  neg     al
0x1800aeba1  mov     edx, [rbp+1E0h+arg_28]; unsigned int
0x1800aeba7  sbb     ecx, ecx
0x1800aeba9  and     ecx, [rsp+2E0h+var_26C]; unsigned int
0x1800aebad  call    ?IsTypeLibLocaleIdAcceptable@CPackagedComCatalog@@CA_NKK_N@Z; CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(ulong,ulong,bool)
0x1800aebb2  test    al, al
0x1800aebb4  jnz     loc_1800AEC3A
0x1800aebba  lea     rcx, [rsp+2E0h+var_270]; this
0x1800aebbf  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800aebc4  mov     r10, [rbp+1E0h+var_80]
0x1800aebcb  mov     edx, dword ptr [rbp+1E0h+var_78]
0x1800aebd1  add     rdi, 20h ; ' '
0x1800aebd5  shl     rdx, 5
0x1800aebd9  add     rdx, r10
0x1800aebdc  cmp     rdi, rdx
0x1800aebdf  jnz     loc_1800AEAD7
0x1800aebe5  cmp     r15d, 1
0x1800aebe9  jnz     short loc_1800AEC0F
0x1800aebeb  mov     r8, rdx
0x1800aebee  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800aebf5  sub     r8, r10
0x1800aebf8  mov     rcx, r10
0x1800aebfb  sar     r8, 5
0x1800aebff  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800aec04  mov     r15d, 2
0x1800aec0a  jmp     loc_1800AEACD
0x1800aec0f  cmp     r15d, 2
0x1800aec13  jnz     loc_1800AEAD7
0x1800aec19  mov     r8, rdx
0x1800aec1c  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800aec23  sub     r8, r10
0x1800aec26  mov     rcx, r10
0x1800aec29  sar     r8, 5
0x1800aec2d  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800aec32  mov     r15d, ebx
0x1800aec35  jmp     loc_1800AEACD
0x1800aec3a  lea     rdx, [rsp+2E0h+var_270]
0x1800aec3f  mov     rcx, r13
0x1800aec42  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@AEBU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800aec47  mov     rax, [rdi]
0x1800aec4a  mov     [rdi], rbx
0x1800aec4d  mov     [r12], rax
0x1800aec51  test    r14, r14
0x1800aec54  jz      short loc_1800AEC66
0x1800aec56  movsd   xmm0, qword ptr [rsi]
0x1800aec5a  mov     eax, [rsi+8]
0x1800aec5d  movsd   qword ptr [r14], xmm0
0x1800aec62  mov     [r14+8], eax
0x1800aec66  lea     rcx, [rsp+2E0h+var_270]; this
0x1800aec6b  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800aec70  mov     rcx, [rsp+2E0h+string]; string
0x1800aec75  call    cs:__imp_WindowsDeleteString
0x1800aec7c  nop     dword ptr [rax+rax+00h]
0x1800aec81  mov     [rsp+2E0h+string], rbx
0x1800aec86  jmp     loc_1800AE9DD
0x1800aec8b  xor     ebx, ebx
0x1800aec8d  cmp     [rbp+1E0h+arg_30], bl
0x1800aec93  jz      short loc_1800AECB0
0x1800aec95  mov     rcx, [rsp+2E0h+string]; string
0x1800aec9a  call    cs:__imp_WindowsDeleteString
0x1800aeca1  nop     dword ptr [rax+rax+00h]
0x1800aeca6  mov     [rsp+2E0h+string], rbx
0x1800aecab  jmp     loc_1800AEF70
0x1800aecb0  lea     rdx, [r10+rcx]
0x1800aecb4  mov     rcx, r10
0x1800aecb7  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800aecbe  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800aecc3  mov     rcx, [rsp+2E0h+string]; string
0x1800aecc8  call    cs:__imp_WindowsDeleteString
0x1800aeccf  nop     dword ptr [rax+rax+00h]
0x1800aecd4  movsd   xmm6, qword ptr [rsi]
0x1800aecd8  xor     eax, eax
0x1800aecda  mov     r15d, [rsi+8]
0x1800aecde  mov     [rbp+1E0h+var_170], bl
0x1800aece1  mov     [rbp+1E0h+var_16C], ebx
0x1800aece4  mov     [rbp+1E0h+var_168], bl
0x1800aece7  mov     [rbp+1E0h+var_164], ebx
0x1800aecea  mov     [rbp+1E0h+var_160], bl
0x1800aecf0  mov     [rbp+1E0h+var_158], rbx
0x1800aecf7  mov     [rbp+1E0h+var_150], bl
0x1800aecfd  mov     [rbp+1E0h+var_148], rbx
0x1800aed04  mov     [rbp+1E0h+var_140], bl
0x1800aed0a  mov     [rbp+1E0h+var_138], rbx
0x1800aed11  mov     [rbp+1E0h+var_130], bl
0x1800aed17  mov     [rbp+1E0h+var_128], rbx
0x1800aed1e  mov     [rbp+1E0h+var_120], ax
0x1800aed25  mov     [rbp+1E0h+var_11C], bl
0x1800aed2b  mov     [rbp+1E0h+var_118], ebx
0x1800aed31  mov     [rbp+1E0h+var_114], bl
0x1800aed37  mov     [rbp+1E0h+var_110], ebx
0x1800aed3d  mov     [rbp+1E0h+var_10C], bl
0x1800aed43  mov     [rbp+1E0h+var_108], ebx
0x1800aed49  mov     [rsp+2E0h+var_278], rbx
0x1800aed4e  cmp     dword ptr [rbp+1E0h+var_78], ebx
0x1800aed54  jz      loc_1800AEF59
0x1800aed5a  mov     r10, [rbp+1E0h+var_80]
0x1800aed61  lea     esi, [rax+1]
0x1800aed64  mov     r14, [rsp+2E0h+var_288]
0x1800aed69  mov     rdi, r10
0x1800aed6c  mov     r12b, byte ptr [rsp+2E0h+var_2A0]
0x1800aed71  mov     edx, esi
0x1800aed73  mov     rcx, rdi
0x1800aed76  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800aed7b  test    al, al
0x1800aed7d  jz      loc_1800AEE87
0x1800aed83  mov     rdx, [rsp+2E0h+var_290]
0x1800aed88  lea     rcx, [rbp+1E0h+var_200]
0x1800aed8c  xor     eax, eax
0x1800aed8e  mov     [rsp+2E0h+var_288], 0
0x1800aed97  mov     [rbp+1E0h+var_1B0], ax
0x1800aed9b  mov     r9, r14
0x1800aed9e  lea     rax, [rsp+2E0h+var_288]
0x1800aeda3  mov     byte ptr [rsp+2E0h+var_280], bl
0x1800aeda7  mov     [rsp+2E0h+var_2B0], rax
0x1800aedac  mov     r8, rdi
0x1800aedaf  lea     rax, [rbp+1E0h+var_180]
0x1800aedb3  mov     byte ptr [rsp+2E0h+var_2B8], r12b
0x1800aedb8  mov     [rsp+2E0h+var_2C0], rax
0x1800aedbd  mov     [rbp+1E0h+var_200], bl
0x1800aedc0  mov     [rbp+1E0h+var_1FC], ebx
0x1800aedc3  mov     [rbp+1E0h+var_1F8], bl
0x1800aedc6  mov     [rbp+1E0h+var_1F4], ebx
0x1800aedc9  mov     [rbp+1E0h+var_1F0], bl
0x1800aedcc  mov     [rbp+1E0h+var_1E8], rbx
0x1800aedd0  mov     [rbp+1E0h+var_1E0], bl
0x1800aedd3  mov     [rbp+1E0h+var_1D8], rbx
0x1800aedd7  mov     [rbp+1E0h+var_1D0], bl
0x1800aedda  mov     [rbp+1E0h+var_1C8], rbx
  ... truncated ...
```
