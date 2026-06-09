# CPackagedComCatalog::ResolveAndReadTypeLibVersionEntryOld(ComTypeLibVersionRegistrationEntryProperties &,HSTRING__ * *,_GUID const &,CPackagedComCatalog::TypeLibVersion,ulong,bool,bool,CPackagedComCatalog::TypeLibVersion *)

- ea: `0x1800a97ac`
- end: `0x1800a9eb7`
- name: `?ResolveAndReadTypeLibVersionEntryOld@CPackagedComCatalog@@AEAAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAPEAUHSTRING__@@AEBU_GUID@@VTypeLibVersion@1@K_N4PEAV51@@Z`
- size: `1803`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800dd5f0`
- `0x1800dffa0`
- `0x1800e1680`

## callees

- `0x18000bbe8`
- `0x18000d4c4`
- `0x18002ba28`
- `0x1800414d0`
- `0x180047990`
- `0x180048090`
- `0x1800483bc`
- `0x18007b510`
- `0x180080b44`
- `0x1800a97ac`
- `0x1800a9ec0`
- `0x1800b27e0`
- `0x1800d539c`
- `0x1800d6d5c`
- `0x1800d9338`
- `0x1800e1654`
- `0x1800e4d14`
- `0x1800e51e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9b65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9e4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9e62`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800a9833`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800a9833`

## string_xrefs

- `0x1800a9846`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a98a7`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a9978`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::ResolveAndReadTypeLibVersionEntryOld(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        GUID *a4,
        unsigned int *a5,
        unsigned int a6,
        char a7,
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
  unsigned int v23; // esi
  struct OpaqueString *v24; // r10
  struct OpaqueString *v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  char v29; // al
  struct OpaqueString *v30; // rdx
  __int64 v31; // rax
  unsigned int v32; // eax
  struct _GUID *v33; // xmm6_8
  unsigned int v34; // esi
  unsigned int v35; // edi
  struct _GUID *v36; // r14
  struct OpaqueString *v37; // rbx
  struct OpaqueString *v38; // r10
  __int64 v39; // rdx
  __int64 v40; // rcx
  char v41; // al
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
  v52 = a4;
  v94 = a3;
  *a3 = 0;
  v51 = 0;
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
    goto LABEL_63;
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
    goto LABEL_63;
  }
  if ( !(_DWORD)v118 )
  {
LABEL_62:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v116);
    v13 = -2147319779;
    goto LABEL_63;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v117,
    (char *)v117 + 32 * (unsigned int)v118,
    (unsigned int)v118,
    MoreRecentlyInstalledByUser);
  v19 = 0;
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
    v22 = 0;
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
        v55[0] = v22;
        v67 = 0;
        v56 = v22;
        v57 = v22;
        v58 = v22;
        v59 = v22;
        v60 = v22;
        v61 = v22;
        v62 = v22;
        v63 = v22;
        v64 = v22;
        v65 = v22;
        v66 = v22;
        v68 = v22;
        v69 = v22;
        v70 = v22;
        v71 = v22;
        v72 = v22;
        v73 = v22;
        if ( (int)CPackagedComCatalog::ReadTypeLibVersionEntry(
                    (struct ComTypeLibVersionRegistrationEntryProperties *)v55,
                    v51,
                    v25,
                    v52,
                    (const struct OpaqueString *)&string) >= 0 )
        {
          if ( (_BYTE)v67 )
          {
            LOBYTE(v27) = HIBYTE(v67);
            v29 = HIBYTE(v67);
          }
          else
          {
            v29 = 0;
            LOBYTE(v27) = 0;
          }
          LOBYTE(v28) = v29 == 0;
          if ( (unsigned __int8)RegistrationScopeMatchesInstallScope(v28, v27, v23) )
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
              goto LABEL_32;
            }
          }
        }
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v55);
        v24 = v117;
        v22 = 0;
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
          v22 = 0;
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
          v22 = 0;
          v23 = 0;
          goto LABEL_14;
        }
      }
    }
    if ( a7 != (_BYTE)v22 )
    {
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_62;
    }
    std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
      v24,
      (char *)v24 + v26,
      (unsigned int)v118,
      MoreRecentlyInstalledByUser);
    WindowsDeleteString(string);
    v19 = 0;
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
LABEL_61:
    WindowsDeleteString(0);
    ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v97);
    goto LABEL_62;
  }
  v35 = 1;
  v36 = v52;
  v37 = v117;
  do
  {
    if ( (unsigned __int8)PackageInstalledForScope(v37, v35, v18, v19) )
    {
      LOBYTE(v53) = v19;
      v86 = 0;
      v74[0] = v19;
      v75 = v19;
      v76 = v19;
      v77 = v19;
      v78 = v19;
      v79 = v19;
      v80 = v19;
      v81 = v19;
      v82 = v19;
      v83 = v19;
      v84 = v19;
      v85 = v19;
      v87 = v19;
      v88 = v19;
      v89 = v19;
      v90 = v19;
      v91 = v19;
      v92 = v19;
      v52 = 0;
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
        if ( (_BYTE)v86 )
        {
          LOBYTE(v39) = HIBYTE(v86);
          v41 = HIBYTE(v86);
        }
        else
        {
          v41 = 0;
          LOBYTE(v39) = 0;
        }
        LOBYTE(v40) = v41 == 0;
        if ( (unsigned __int8)RegistrationScopeMatchesInstallScope(v40, v39, v35) )
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
      v19 = 0;
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
        v19 = 0;
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
        v19 = 0;
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
    goto LABEL_61;
  ComTypeLibVersionRegistrationEntryProperties::operator=(a2, v97);
  *v46 = v44;
  if ( v45 )
  {
    *(_QWORD *)v45 = v33;
    *(_DWORD *)(v45 + 8) = v34;
  }
  WindowsDeleteString(0);
  ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v97);
LABEL_32:
  PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v116);
  v13 = 0;
LABEL_63:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  return v13;
}

```

## disassembly

```asm
0x1800a97ac  mov     rax, rsp
0x1800a97af  push    rbp
0x1800a97b0  push    rbx
0x1800a97b1  push    rsi
0x1800a97b2  push    rdi
0x1800a97b3  push    r12
0x1800a97b5  push    r14
0x1800a97b7  push    r15
0x1800a97b9  lea     rbp, [rax-1E8h]
0x1800a97c0  sub     rsp, 2B0h
0x1800a97c7  movaps  xmmword ptr [rax-48h], xmm6
0x1800a97cb  mov     rax, cs:__security_cookie
0x1800a97d2  xor     rax, rsp
0x1800a97d5  mov     qword ptr [rbp+1E0h+var_48], rax
0x1800a97dc  mov     r14, [rbp+1E0h+arg_40]
0x1800a97e3  lea     rcx, [rsp+2E0h+var_290]
0x1800a97e8  mov     rdi, [rbp+1E0h+arg_20]
0x1800a97ef  mov     rsi, r9
0x1800a97f2  mov     [rbp+1E0h+var_190], r14
0x1800a97f6  mov     r12, r8
0x1800a97f9  mov     [rsp+2E0h+var_288], r9
0x1800a97fe  mov     r15, rdx
0x1800a9801  mov     [rbp+1E0h+var_188], r8
0x1800a9805  mov     qword ptr [r8], 0
0x1800a980c  mov     [rsp+2E0h+var_290], 0
0x1800a9815  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a981a  xor     edx, edx
0x1800a981c  lea     rax, [rsp+2E0h+var_290]
0x1800a9821  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800a9828  mov     [rsp+2E0h+var_2C0], rax; int
0x1800a982d  xor     r8d, r8d
0x1800a9830  lea     ecx, [rdx+1]
0x1800a9833  call    cs:__imp_RoGetRegistrationStoreContext
0x1800a9839  mov     ebx, eax
0x1800a983b  test    eax, eax
0x1800a983d  jns     short loc_1800A985F
0x1800a983f  mov     rcx, [rbp+1E8h]; this
0x1800a9846  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a984d  mov     r9d, eax; char *
0x1800a9850  mov     edx, 209Fh; void *
0x1800a9855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a985a  jmp     loc_1800A9E82
0x1800a985f  lea     rcx, [rbp+1E0h+var_100]; this
0x1800a9866  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x1800a986b  mov     al, [rbp+1E0h+arg_38]
0x1800a9871  lea     rcx, [rbp+1E0h+var_100]; this
0x1800a9878  mov     r8, [rsp+2E0h+var_290]
0x1800a987d  mov     r9, rsi
0x1800a9880  mov     [rsp+2E0h+var_2B8], 0; PackageFilter *
0x1800a9889  mov     byte ptr [rsp+2E0h+var_2C0], al; int
0x1800a988d  call    ??$GetInstalledPackagesContainingEntry@UComTypeLibVersionRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x1800a9892  mov     ebx, eax
0x1800a9894  test    eax, eax
0x1800a9896  jns     short loc_1800A98C4
0x1800a9898  mov     r9d, eax; char *
0x1800a989b  mov     edx, 20A8h; void *
0x1800a98a0  mov     rcx, [rbp+1E8h]; this
0x1800a98a7  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a98ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a98b3  lea     rcx, [rbp+1E0h+var_100]; this
0x1800a98ba  call    ??1PackageListBuffer@@QEAA@XZ; PackageListBuffer::~PackageListBuffer(void)
0x1800a98bf  jmp     loc_1800A9E82
0x1800a98c4  mov     rax, [rbp+1E0h+var_78]
0x1800a98cb  test    eax, eax
0x1800a98cd  jz      loc_1800A9E71
0x1800a98d3  mov     rcx, [rbp+1E0h+var_80]
0x1800a98da  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a98e1  mov     edx, eax
0x1800a98e3  shl     rdx, 5
0x1800a98e7  add     rdx, rcx
0x1800a98ea  mov     r8d, eax
0x1800a98ed  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a98f2  mov     al, [rdi+8]
0x1800a98f5  xor     r9d, r9d
0x1800a98f8  mov     byte ptr [rsp+2E0h+var_2A0], al
0x1800a98fc  test    al, al
0x1800a98fe  jz      loc_1800A9BCA
0x1800a9904  mov     r9d, [rdi]
0x1800a9907  lea     r8, aXX; "%x.%x"
0x1800a990e  xor     eax, eax
0x1800a9910  lea     rcx, [rbp+1E0h+var_60]; unsigned __int16 *
0x1800a9917  mov     [rbp+1E0h+var_50], eax
0x1800a991d  xorps   xmm0, xmm0
0x1800a9920  mov     eax, [rdi+4]
0x1800a9923  mov     edx, 0Ah; unsigned __int64
0x1800a9928  mov     dword ptr [rsp+2E0h+var_2C0], eax; int
0x1800a992c  movups  xmmword ptr [rbp+1E0h+var_60], xmm0
0x1800a9933  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a9938  test    eax, eax
0x1800a993a  jns     short loc_1800A994E
0x1800a993c  mov     ebx, 80070057h
0x1800a9941  mov     edx, 20BDh
0x1800a9946  mov     r9d, ebx
0x1800a9949  jmp     loc_1800A98A0
0x1800a994e  lea     rdx, [rbp+1E0h+var_60]
0x1800a9955  mov     [rsp+2E0h+string], 0
0x1800a995e  lea     rcx, [rsp+2E0h+string]
0x1800a9963  call    ??$Set@$09@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY09G@Z; Microsoft::WRL::Wrappers::HString::Set<10>(ushort (&)[10])
0x1800a9968  xor     r9d, r9d
0x1800a996b  mov     ebx, eax
0x1800a996d  test    eax, eax
0x1800a996f  jns     short loc_1800A99A5
0x1800a9971  mov     rcx, [rbp+1E8h]; this
0x1800a9978  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a997f  mov     r9d, eax; char *
0x1800a9982  mov     edx, 20C0h; void *
0x1800a9987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a998c  mov     rcx, [rsp+2E0h+string]; string
0x1800a9991  call    cs:__imp_WindowsDeleteString
0x1800a9997  mov     [rsp+2E0h+string], 0
0x1800a99a0  jmp     loc_1800A98B3
0x1800a99a5  mov     esi, 1
0x1800a99aa  mov     r10, [rbp+1E0h+var_80]
0x1800a99b1  mov     rbx, r10
0x1800a99b4  mov     r8d, dword ptr [rbp+1E0h+var_78]
0x1800a99bb  mov     ecx, r8d
0x1800a99be  shl     rcx, 5
0x1800a99c2  lea     rax, [r10+rcx]
0x1800a99c6  cmp     rbx, rax
0x1800a99c9  jz      loc_1800A9B87
0x1800a99cf  mov     edx, esi
0x1800a99d1  mov     rcx, rbx
0x1800a99d4  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800a99d9  test    al, al
0x1800a99db  jz      loc_1800A9AB4
0x1800a99e1  mov     rdx, [rsp+2E0h+var_290]; struct IPackagedComCatalogContext *
0x1800a99e6  lea     rcx, [rsp+2E0h+var_270]; struct ComTypeLibVersionRegistrationEntryProperties *
0x1800a99eb  xor     eax, eax
0x1800a99ed  mov     [rsp+2E0h+var_270], r9b
0x1800a99f2  mov     [rbp+1E0h+var_220], ax
0x1800a99f6  mov     r8, rbx; struct OpaqueString *
0x1800a99f9  lea     rax, [rsp+2E0h+string]
0x1800a99fe  mov     [rsp+2E0h+var_26C], r9d
0x1800a9a03  mov     [rsp+2E0h+var_268], r9b
0x1800a9a08  mov     [rsp+2E0h+var_264], r9d
0x1800a9a0d  mov     [rbp+1E0h+var_260], r9b
0x1800a9a11  mov     [rbp+1E0h+var_258], r9
0x1800a9a15  mov     [rbp+1E0h+var_250], r9b
0x1800a9a19  mov     [rbp+1E0h+var_248], r9
0x1800a9a1d  mov     [rbp+1E0h+var_240], r9b
0x1800a9a21  mov     [rbp+1E0h+var_238], r9
0x1800a9a25  mov     [rbp+1E0h+var_230], r9b
0x1800a9a29  mov     [rbp+1E0h+var_228], r9
0x1800a9a2d  mov     [rbp+1E0h+var_21C], r9b
0x1800a9a31  mov     [rbp+1E0h+var_218], r9d
0x1800a9a35  mov     [rbp+1E0h+var_214], r9b
0x1800a9a39  mov     [rbp+1E0h+var_210], r9d
0x1800a9a3d  mov     [rbp+1E0h+var_20C], r9b
0x1800a9a41  mov     [rbp+1E0h+var_208], r9d
0x1800a9a45  mov     r9, [rsp+2E0h+var_288]; struct _GUID *
0x1800a9a4a  mov     [rsp+2E0h+var_2C0], rax; struct OpaqueString *
0x1800a9a4f  call    ?ReadTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2@Z; CPackagedComCatalog::ReadTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &)
0x1800a9a54  test    eax, eax
0x1800a9a56  js      short loc_1800A9AA0
0x1800a9a58  cmp     byte ptr [rbp+1E0h+var_220], 0
0x1800a9a5c  jz      short loc_1800A9A65
0x1800a9a5e  mov     dl, byte ptr [rbp+1E0h+var_220+1]
0x1800a9a61  mov     al, dl
0x1800a9a63  jmp     short loc_1800A9A69
0x1800a9a65  xor     al, al
0x1800a9a67  xor     dl, dl
0x1800a9a69  test    al, al
0x1800a9a6b  mov     r8d, esi
0x1800a9a6e  setz    cl
0x1800a9a71  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x1800a9a76  test    al, al
0x1800a9a78  jz      short loc_1800A9AA0
0x1800a9a7a  mov     al, [rsp+2E0h+var_270]
0x1800a9a7e  mov     r8b, [rbp+1E0h+arg_30]; bool
0x1800a9a85  neg     al
0x1800a9a87  mov     edx, [rbp+1E0h+arg_28]; unsigned int
0x1800a9a8d  sbb     ecx, ecx
0x1800a9a8f  and     ecx, [rsp+2E0h+var_26C]; unsigned int
0x1800a9a93  call    ?IsTypeLibLocaleIdAcceptable@CPackagedComCatalog@@CA_NKK_N@Z; CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(ulong,ulong,bool)
0x1800a9a98  test    al, al
0x1800a9a9a  jnz     loc_1800A9B26
0x1800a9aa0  lea     rcx, [rsp+2E0h+var_270]; this
0x1800a9aa5  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a9aaa  mov     r10, [rbp+1E0h+var_80]
0x1800a9ab1  xor     r9d, r9d
0x1800a9ab4  mov     edx, dword ptr [rbp+1E0h+var_78]
0x1800a9aba  add     rbx, 20h ; ' '
0x1800a9abe  shl     rdx, 5
0x1800a9ac2  add     rdx, r10
0x1800a9ac5  cmp     rbx, rdx
0x1800a9ac8  jnz     loc_1800A99B4
0x1800a9ace  cmp     esi, 1
0x1800a9ad1  jnz     short loc_1800A9AF9
0x1800a9ad3  mov     r8, rdx
0x1800a9ad6  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a9add  sub     r8, r10
0x1800a9ae0  mov     rcx, r10
0x1800a9ae3  sar     r8, 5
0x1800a9ae7  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a9aec  xor     r9d, r9d
0x1800a9aef  mov     esi, 2
0x1800a9af4  jmp     loc_1800A99AA
0x1800a9af9  cmp     esi, 2
0x1800a9afc  jnz     loc_1800A99B4
0x1800a9b02  mov     r8, rdx
0x1800a9b05  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a9b0c  sub     r8, r10
0x1800a9b0f  mov     rcx, r10
0x1800a9b12  sar     r8, 5
0x1800a9b16  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a9b1b  xor     r9d, r9d
0x1800a9b1e  mov     esi, r9d
0x1800a9b21  jmp     loc_1800A99AA
0x1800a9b26  lea     rdx, [rsp+2E0h+var_270]
0x1800a9b2b  mov     rcx, r15
0x1800a9b2e  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@AEBU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800a9b33  mov     rax, [rbx]
0x1800a9b36  mov     qword ptr [rbx], 0
0x1800a9b3d  mov     [r12], rax
0x1800a9b41  test    r14, r14
0x1800a9b44  jz      short loc_1800A9B56
0x1800a9b46  movsd   xmm0, qword ptr [rdi]
0x1800a9b4a  mov     eax, [rdi+8]
0x1800a9b4d  movsd   qword ptr [r14], xmm0
0x1800a9b52  mov     [r14+8], eax
0x1800a9b56  lea     rcx, [rsp+2E0h+var_270]; this
0x1800a9b5b  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a9b60  mov     rcx, [rsp+2E0h+string]; string
0x1800a9b65  call    cs:__imp_WindowsDeleteString
0x1800a9b6b  mov     [rsp+2E0h+string], 0
0x1800a9b74  lea     rcx, [rbp+1E0h+var_100]; this
0x1800a9b7b  call    ??1PackageListBuffer@@QEAA@XZ; PackageListBuffer::~PackageListBuffer(void)
0x1800a9b80  xor     ebx, ebx
0x1800a9b82  jmp     loc_1800A9E82
0x1800a9b87  cmp     [rbp+1E0h+arg_30], r9b
0x1800a9b8e  jz      short loc_1800A9BA9
0x1800a9b90  mov     rcx, [rsp+2E0h+string]; string
0x1800a9b95  call    cs:__imp_WindowsDeleteString
0x1800a9b9b  mov     [rsp+2E0h+string], 0
0x1800a9ba4  jmp     loc_1800A9E71
0x1800a9ba9  lea     rdx, [r10+rcx]
0x1800a9bad  mov     rcx, r10
0x1800a9bb0  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a9bb7  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a9bbc  mov     rcx, [rsp+2E0h+string]; string
0x1800a9bc1  call    cs:__imp_WindowsDeleteString
0x1800a9bc7  xor     r9d, r9d
0x1800a9bca  movsd   xmm6, qword ptr [rdi]
0x1800a9bce  xor     eax, eax
0x1800a9bd0  mov     esi, [rdi+8]
0x1800a9bd3  mov     [rbp+1E0h+var_170], r9b
0x1800a9bd7  mov     [rbp+1E0h+var_16C], r9d
0x1800a9bdb  mov     [rbp+1E0h+var_168], r9b
0x1800a9bdf  mov     [rbp+1E0h+var_164], r9d
0x1800a9be3  mov     [rbp+1E0h+var_160], r9b
0x1800a9bea  mov     [rbp+1E0h+var_158], r9
0x1800a9bf1  mov     [rbp+1E0h+var_150], r9b
0x1800a9bf8  mov     [rbp+1E0h+var_148], r9
0x1800a9bff  mov     [rbp+1E0h+var_140], r9b
0x1800a9c06  mov     [rbp+1E0h+var_138], r9
0x1800a9c0d  mov     [rbp+1E0h+var_130], r9b
0x1800a9c14  mov     [rbp+1E0h+var_128], r9
0x1800a9c1b  mov     [rbp+1E0h+var_120], ax
0x1800a9c22  mov     [rbp+1E0h+var_11C], r9b
0x1800a9c29  mov     [rbp+1E0h+var_118], r9d
0x1800a9c30  mov     [rbp+1E0h+var_114], r9b
0x1800a9c37  mov     [rbp+1E0h+var_110], r9d
0x1800a9c3e  mov     [rbp+1E0h+var_10C], r9b
0x1800a9c45  mov     [rbp+1E0h+var_108], r9d
0x1800a9c4c  mov     qword ptr [rsp+2E0h+var_278], r9
0x1800a9c51  cmp     dword ptr [rbp+1E0h+var_78], r9d
0x1800a9c58  jz      loc_1800A9E60
0x1800a9c5e  mov     r10, [rbp+1E0h+var_80]
0x1800a9c65  lea     edi, [rax+1]
0x1800a9c68  mov     r14, [rsp+2E0h+var_288]
0x1800a9c6d  mov     rbx, r10
0x1800a9c70  mov     r12b, byte ptr [rsp+2E0h+var_2A0]
0x1800a9c75  mov     edx, edi
0x1800a9c77  mov     rcx, rbx
0x1800a9c7a  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800a9c7f  test    al, al
0x1800a9c81  jz      loc_1800A9D98
0x1800a9c87  mov     rdx, [rsp+2E0h+var_290]
0x1800a9c8c  lea     rcx, [rbp+1E0h+var_200]
0x1800a9c90  xor     eax, eax
0x1800a9c92  mov     byte ptr [rsp+2E0h+var_280], r9b
0x1800a9c97  mov     [rbp+1E0h+var_1B0], ax
0x1800a9c9b  mov     r8, rbx
0x1800a9c9e  lea     rax, [rsp+2E0h+var_288]
0x1800a9ca3  mov     [rbp+1E0h+var_200], r9b
0x1800a9ca7  mov     [rsp+30h], rax
0x1800a9cac  lea     rax, [rbp+1E0h+var_180]
0x1800a9cb0  mov     [rbp+1E0h+var_1FC], r9d
0x1800a9cb4  mov     [rbp+1E0h+var_1F8], r9b
0x1800a9cb8  mov     [rbp+1E0h+var_1F4], r9d
0x1800a9cbc  mov     [rbp+1E0h+var_1F0], r9b
0x1800a9cc0  mov     [rbp+1E0h+var_1E8], r9
0x1800a9cc4  mov     [rbp+1E0h+var_1E0], r9b
0x1800a9cc8  mov     [rbp+1E0h+var_1D8], r9
0x1800a9ccc  mov     [rbp+1E0h+var_1D0], r9b
0x1800a9cd0  mov     [rbp+1E0h+var_1C8], r9
0x1800a9cd4  mov     [rbp+1E0h+var_1C0], r9b
0x1800a9cd8  mov     [rbp+1E0h+var_1B8], r9
0x1800a9cdc  mov     [rbp+1E0h+var_1AC], r9b
0x1800a9ce0  mov     [rbp+1E0h+var_1A8], r9d
  ... truncated ...
```
