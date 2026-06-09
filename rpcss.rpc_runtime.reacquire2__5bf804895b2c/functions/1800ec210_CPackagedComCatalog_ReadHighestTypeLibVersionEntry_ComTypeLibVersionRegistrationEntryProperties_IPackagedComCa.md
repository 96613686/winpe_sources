# CPackagedComCatalog::ReadHighestTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,CPackagedComCatalog::TypeLibVersion,bool,CPackagedComCatalog::TypeLibVersion *)

- ea: `0x1800ec210`
- end: `0x1800ec5f8`
- name: `?ReadHighestTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@VTypeLibVersion@1@_NPEAV61@@Z`
- size: `1000`
- prototype: `static int __high(struct ComTypeLibVersionRegistrationEntryProperties *, struct IPackagedComCatalogContext *, const struct OpaqueString *, const struct _GUID *, struct CPackagedComCatalog::TypeLibVersion, bool, struct CPackagedComCatalog::TypeLibVersion *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800ae8d4`
- `0x1800e7404`

## callees

- `0x1800065a4`
- `0x18001a374`
- `0x1800210f8`
- `0x180034260`
- `0x18004b0f0`
- `0x180095c0c`
- `0x1800a543c`
- `0x1800aefc4`
- `0x1800b7ac0`
- `0x1800dac84`
- `0x1800e8504`
- `0x1800eba28`
- `0x1800ec210`
- `0x1800ec720`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec574`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec5c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec31b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec574`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec5b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ec5c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec500`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ec500`

## string_xrefs

- `0x1800ec2a8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ec52b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ec596`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ec428`: `CPackagedComCatalog::ReadHighestTypeLibVersionEntry`
- `0x1800ec51f`: `CPackagedComCatalog::ReadHighestTypeLibVersionEntry`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::ReadHighestTypeLibVersionEntry(
        struct ComTypeLibVersionRegistrationEntryProperties *a1,
        struct IPackagedComCatalogContext *a2,
        const struct OpaqueString *a3,
        const struct _GUID *a4,
        __int64 *a5,
        char a6,
        __int64 a7)
{
  __int64 v10; // rcx
  HSTRING v11; // rdx
  __int64 v12; // xmm6_8
  int v13; // r14d
  int v14; // eax
  unsigned int v15; // ebx
  HSTRING v16; // rcx
  unsigned int v17; // edi
  __int64 v18; // rax
  __int64 (__fastcall *v19)(struct IPackagedComCatalogContext *, __int64, _QWORD, __int64 *); // rbx
  __int64 v20; // r8
  PCWSTR StringRawBuffer; // rdi
  CGuidStr *v22; // rbx
  PCWSTR v23; // rax
  int v24; // ecx
  int v25; // r9d
  int TypeLibVersionEntry; // eax
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  CGuidStr *v30; // rax
  int v31; // r9d
  __int64 v32; // r11
  int v33; // [rsp+28h] [rbp-E0h]
  HSTRING *p_string; // [rsp+28h] [rbp-E0h]
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING v37; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+70h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-90h]
  __int64 v40; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v41[4]; // [rsp+88h] [rbp-80h] BYREF
  int v42; // [rsp+8Ch] [rbp-7Ch]
  char v43; // [rsp+90h] [rbp-78h]
  int v44; // [rsp+94h] [rbp-74h]
  char v45; // [rsp+98h] [rbp-70h]
  __int64 v46; // [rsp+A0h] [rbp-68h]
  char v47; // [rsp+A8h] [rbp-60h]
  __int64 v48; // [rsp+B0h] [rbp-58h]
  char v49; // [rsp+B8h] [rbp-50h]
  __int64 v50; // [rsp+C0h] [rbp-48h]
  char v51; // [rsp+C8h] [rbp-40h]
  __int64 v52; // [rsp+D0h] [rbp-38h]
  __int16 v53; // [rsp+D8h] [rbp-30h]
  char v54; // [rsp+DCh] [rbp-2Ch]
  int v55; // [rsp+E0h] [rbp-28h]
  char v56; // [rsp+E4h] [rbp-24h]
  int v57; // [rsp+E8h] [rbp-20h]
  char v58; // [rsp+ECh] [rbp-1Ch]
  int v59; // [rsp+F0h] [rbp-18h]
  struct ComTypeLibVersionRegistrationEntryProperties *v60; // [rsp+F8h] [rbp-10h]
  __int64 v61; // [rsp+108h] [rbp+0h] BYREF
  int v62; // [rsp+110h] [rbp+8h]
  _BYTE v63[80]; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v60 = a1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  v11 = *(HSTRING *)a3;
  v40 = 0;
  v12 = *a5;
  v13 = *((_DWORD *)a5 + 2);
  v14 = (*(__int64 (__fastcall **)(struct IPackagedComCatalogContext *, HSTRING, const struct _GUID *, __int64 *))(*(_QWORD *)a2 + 112LL))(
          a2,
          v11,
          a4,
          &v40);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v16 = 0;
    string = 0;
    v37 = 0;
    v17 = 0;
    v41[0] = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    while ( 1 )
    {
      v18 = *(_QWORD *)a2;
      LOBYTE(v35) = 0;
      v19 = *(__int64 (__fastcall **)(struct IPackagedComCatalogContext *, __int64, _QWORD, __int64 *))(v18 + 120);
      WindowsDeleteString(v16);
      p_string = &string;
      string = 0;
      v15 = v19(a2, v40, v17, &v35);
      if ( (v15 & 0x80000000) != 0 )
        break;
      if ( !(_BYTE)v35 )
      {
        if ( v37 )
        {
          TypeLibVersionEntry = CPackagedComCatalog::ReadTypeLibVersionEntry(
                                  v60,
                                  a2,
                                  a3,
                                  a4,
                                  (const struct OpaqueString *)&v37);
          v15 = TypeLibVersionEntry;
          if ( TypeLibVersionEntry < 0 )
          {
            v28 = (unsigned int)TypeLibVersionEntry;
            v29 = 8180;
            goto LABEL_31;
          }
          if ( a7 )
          {
            *(_QWORD *)a7 = v12;
            *(_DWORD *)(a7 + 8) = v13;
          }
          v15 = 0;
LABEL_32:
          ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v41);
          WindowsDeleteString(v37);
        }
        else if ( v17 )
        {
          ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v41);
          WindowsDeleteString(0);
          v15 = -2147319779;
        }
        else
        {
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            WindowsGetStringRawBuffer(*(HSTRING *)a3, 0);
            v30 = CGuidStr::CGuidStr((CGuidStr *)v63, a4);
            ComTraceMessageT<unsigned short *,unsigned short const *,long>(
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              (unsigned int)"CPackagedComCatalog::ReadHighestTypeLibVersionEntry",
              0x2000,
              v31,
              (__int64)L"No versions found for typelib registration. TypeLibId:%ws PackageName=%S hr=%!HRESULT!",
              v30,
              v32,
              -2147024883);
          }
          ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v41);
          WindowsDeleteString(0);
          v15 = -2147024883;
        }
        WindowsDeleteString(string);
        return v15;
      }
      v38 = 0;
      LOBYTE(v39) = 0;
      if ( (int)CPackagedComCatalog::ParseTypeLibVersionString(
                  string,
                  (struct CPackagedComCatalog::TypeLibVersion *)&v38) < 0 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a3, 0);
          v22 = CGuidStr::CGuidStr((CGuidStr *)v63, a4);
          v23 = WindowsGetStringRawBuffer(string, 0);
          ComTraceMessageT<unsigned short const *,unsigned short *,unsigned short const *,long>(
            v24,
            (unsigned int)"CPackagedComCatalog::ReadHighestTypeLibVersionEntry",
            8163,
            v25,
            (__int64)L"Incorrectly-formatted typelib version number. VersionNumber:%S TypeLibId:%ws PackageName=%S hr=%!HRESULT!",
            v23,
            v22,
            StringRawBuffer,
            -2147024883);
        }
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v41);
        WindowsDeleteString(v37);
        WindowsDeleteString(string);
        return 2147942413LL;
      }
      LOBYTE(v20) = a6;
      v61 = v12;
      v62 = v13;
      if ( (unsigned __int8)CPackagedComCatalog::TypeLibVersion::IsGreaterThan(&v38, &v61, v20) )
      {
        OpaqueString::operator=(&v37, &string);
        v12 = v38;
        v13 = v39;
      }
      v16 = string;
      ++v17;
    }
    v28 = v15;
    v29 = 8147;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)v28,
      (int)p_string);
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1FC8,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)v14,
    v33);
  return v15;
}

```

## disassembly

```asm
0x1800ec210  mov     rax, rsp
0x1800ec213  push    rbp
0x1800ec214  push    rbx
0x1800ec215  push    rsi
0x1800ec216  push    rdi
0x1800ec217  push    r12
0x1800ec219  push    r13
0x1800ec21b  push    r14
0x1800ec21d  push    r15
0x1800ec21f  lea     rbp, [rax-0C8h]
0x1800ec226  sub     rsp, 188h
0x1800ec22d  movaps  xmmword ptr [rax-58h], xmm6
0x1800ec231  mov     rax, cs:__security_cookie
0x1800ec238  xor     rax, rsp
0x1800ec23b  mov     [rbp+0C0h+var_60], rax
0x1800ec23f  mov     rsi, [rbp+0C0h+arg_30]
0x1800ec246  mov     r12, r9
0x1800ec249  mov     r15, r8
0x1800ec24c  mov     [rbp+0C0h+var_D0], rcx
0x1800ec250  mov     r13, rdx
0x1800ec253  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ec25a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ec25f  test    al, al
0x1800ec261  jz      short loc_1800EC268
0x1800ec263  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ec268  mov     rax, [rbp+0C0h+arg_20]
0x1800ec26f  lea     r9, [rsp+1C0h+var_148]
0x1800ec274  mov     rdx, [r15]
0x1800ec277  mov     r8, r12
0x1800ec27a  mov     rcx, r13
0x1800ec27d  mov     [rsp+1C0h+var_148], 0
0x1800ec286  movsd   xmm6, qword ptr [rax]
0x1800ec28a  mov     r14d, [rax+8]
0x1800ec28e  mov     rax, [r13+0]
0x1800ec292  mov     rax, [rax+70h]
0x1800ec296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec29b  mov     ebx, eax
0x1800ec29d  test    eax, eax
0x1800ec29f  jns     short loc_1800EC2C1
0x1800ec2a1  mov     rcx, [rbp+0C8h]; this
0x1800ec2a8  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ec2af  mov     r9d, eax; char *
0x1800ec2b2  mov     edx, 1FC8h; void *
0x1800ec2b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec2bc  jmp     loc_1800EC5CD
0x1800ec2c1  xor     ebx, ebx
0x1800ec2c3  mov     ecx, ebx; string
0x1800ec2c5  mov     [rsp+1C0h+string], rbx
0x1800ec2ca  mov     [rsp+1C0h+var_160], rbx
0x1800ec2cf  mov     edi, ebx
0x1800ec2d1  mov     [rbp+0C0h+var_140], bl
0x1800ec2d4  mov     [rbp+0C0h+var_13C], ebx
0x1800ec2d7  mov     [rbp+0C0h+var_138], bl
0x1800ec2da  mov     [rbp+0C0h+var_134], ebx
0x1800ec2dd  mov     [rbp+0C0h+var_130], bl
0x1800ec2e0  mov     [rbp+0C0h+var_128], rbx
0x1800ec2e4  mov     [rbp+0C0h+var_120], bl
0x1800ec2e7  mov     [rbp+0C0h+var_118], rbx
0x1800ec2eb  mov     [rbp+0C0h+var_110], bl
0x1800ec2ee  mov     [rbp+0C0h+var_108], rbx
0x1800ec2f2  mov     [rbp+0C0h+var_100], bl
0x1800ec2f5  mov     [rbp+0C0h+var_F8], rbx
0x1800ec2f9  mov     [rbp+0C0h+var_F0], bx
0x1800ec2fd  mov     [rbp+0C0h+var_EC], bl
0x1800ec300  mov     [rbp+0C0h+var_E8], ebx
0x1800ec303  mov     [rbp+0C0h+var_E4], bl
0x1800ec306  mov     [rbp+0C0h+var_E0], ebx
0x1800ec309  mov     [rbp+0C0h+var_DC], bl
0x1800ec30c  mov     [rbp+0C0h+var_D8], ebx
0x1800ec30f  mov     rax, [r13+0]
0x1800ec313  mov     byte ptr [rsp+1C0h+var_170], bl
0x1800ec317  mov     rbx, [rax+78h]
0x1800ec31b  call    cs:__imp_WindowsDeleteString
0x1800ec322  nop     dword ptr [rax+rax+00h]
0x1800ec327  mov     rdx, [rsp+1C0h+var_148]
0x1800ec32c  lea     rax, [rsp+1C0h+string]
0x1800ec331  mov     [rsp+1C0h+var_1A0], rax; int
0x1800ec336  lea     r9, [rsp+1C0h+var_170]
0x1800ec33b  mov     rax, rbx
0x1800ec33e  mov     [rsp+1C0h+string], 0
0x1800ec347  mov     r8d, edi
0x1800ec34a  mov     rcx, r13
0x1800ec34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec352  mov     ebx, eax
0x1800ec354  test    eax, eax
0x1800ec356  js      loc_1800EC587
0x1800ec35c  xor     ebx, ebx
0x1800ec35e  cmp     byte ptr [rsp+1C0h+var_170], bl
0x1800ec362  jz      loc_1800EC487
0x1800ec368  mov     rcx, [rsp+1C0h+string]; HSTRING
0x1800ec36d  lea     rdx, [rsp+1C0h+var_158]; struct CPackagedComCatalog::TypeLibVersion *
0x1800ec372  mov     [rsp+1C0h+var_158], rbx
0x1800ec377  mov     byte ptr [rsp+1C0h+var_150], bl
0x1800ec37b  call    ?ParseTypeLibVersionString@CPackagedComCatalog@@CAJPEAUHSTRING__@@PEAVTypeLibVersion@1@@Z; CPackagedComCatalog::ParseTypeLibVersionString(HSTRING__ *,CPackagedComCatalog::TypeLibVersion *)
0x1800ec380  test    eax, eax
0x1800ec382  js      short loc_1800EC3CC
0x1800ec384  mov     r8b, [rbp+0C0h+arg_28]
0x1800ec38b  lea     rdx, [rbp+0C0h+var_C0]
0x1800ec38f  lea     rcx, [rsp+1C0h+var_158]
0x1800ec394  movsd   [rbp+0C0h+var_C0], xmm6
0x1800ec399  mov     [rbp+0C0h+var_B8], r14d
0x1800ec39d  call    ?IsGreaterThan@TypeLibVersion@CPackagedComCatalog@@QEAA_NV12@_N@Z; CPackagedComCatalog::TypeLibVersion::IsGreaterThan(CPackagedComCatalog::TypeLibVersion,bool)
0x1800ec3a2  test    al, al
0x1800ec3a4  jz      short loc_1800EC3C0
0x1800ec3a6  lea     rdx, [rsp+1C0h+string]
0x1800ec3ab  lea     rcx, [rsp+1C0h+var_160]
0x1800ec3b0  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800ec3b5  movsd   xmm6, [rsp+1C0h+var_158]
0x1800ec3bb  mov     r14d, dword ptr [rsp+1C0h+var_150]
0x1800ec3c0  mov     rcx, [rsp+1C0h+string]
0x1800ec3c5  inc     edi
0x1800ec3c7  jmp     loc_1800EC30F
0x1800ec3cc  mov     eax, cs:dword_1801574B8
0x1800ec3d2  mov     esi, 8007000Dh
0x1800ec3d7  test    eax, eax
0x1800ec3d9  jnz     short loc_1800EC3EE
0x1800ec3db  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800ec3e1  jz      short loc_1800EC455
0x1800ec3e3  xor     ecx, ecx
0x1800ec3e5  call    IsWppLevelEnabled
0x1800ec3ea  test    al, al
0x1800ec3ec  jz      short loc_1800EC455
0x1800ec3ee  mov     rcx, [r15]; string
0x1800ec3f1  xor     edx, edx; length
0x1800ec3f3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec3fa  nop     dword ptr [rax+rax+00h]
0x1800ec3ff  mov     rdx, r12; struct _GUID *
0x1800ec402  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800ec406  mov     rdi, rax
0x1800ec409  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800ec40e  mov     rcx, [rsp+1C0h+string]; string
0x1800ec413  xor     edx, edx; length
0x1800ec415  mov     rbx, rax
0x1800ec418  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec41f  nop     dword ptr [rax+rax+00h]
0x1800ec424  mov     [rsp+40h], esi
0x1800ec428  lea     rdx, aCpackagedcomca_3; "CPackagedComCatalog::ReadHighestTypeLib"...
0x1800ec42f  mov     qword ptr [rsp+1C0h+var_188], rdi
0x1800ec434  mov     r8d, 1FE3h
0x1800ec43a  mov     [rsp+1C0h+var_190], rbx
0x1800ec43f  mov     [rsp+1C0h+var_198], rax
0x1800ec444  lea     rax, aIncorrectlyFor; "Incorrectly-formatted typelib version n"...
0x1800ec44b  mov     [rsp+1C0h+var_1A0], rax
0x1800ec450  call    ??$ComTraceMessageT@PEBGPEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG2J@Z; ComTraceMessageT<ushort const *,ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,ushort const *,long)
0x1800ec455  lea     rcx, [rbp+0C0h+var_140]; this
0x1800ec459  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ec45e  mov     rcx, [rsp+1C0h+var_160]; string
0x1800ec463  call    cs:__imp_WindowsDeleteString
0x1800ec46a  nop     dword ptr [rax+rax+00h]
0x1800ec46f  mov     rcx, [rsp+1C0h+string]; string
0x1800ec474  call    cs:__imp_WindowsDeleteString
0x1800ec47b  nop     dword ptr [rax+rax+00h]
0x1800ec480  mov     eax, esi
0x1800ec482  jmp     loc_1800EC5CF
0x1800ec487  cmp     [rsp+1C0h+var_160], rbx
0x1800ec48c  jz      short loc_1800EC4D1
0x1800ec48e  mov     rcx, [rbp+0C0h+var_D0]; struct ComTypeLibVersionRegistrationEntryProperties *
0x1800ec492  lea     rax, [rsp+1C0h+var_160]
0x1800ec497  mov     r9, r12; struct _GUID *
0x1800ec49a  mov     [rsp+1C0h+var_1A0], rax; struct OpaqueString *
0x1800ec49f  mov     r8, r15; struct OpaqueString *
0x1800ec4a2  mov     rdx, r13; struct IPackagedComCatalogContext *
0x1800ec4a5  call    ?ReadTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2@Z; CPackagedComCatalog::ReadTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &)
0x1800ec4aa  mov     ebx, eax
0x1800ec4ac  test    eax, eax
0x1800ec4ae  jns     short loc_1800EC4BD
0x1800ec4b0  mov     r9d, eax
0x1800ec4b3  mov     edx, 1FF4h
0x1800ec4b8  jmp     loc_1800EC58F
0x1800ec4bd  test    rsi, rsi
0x1800ec4c0  jz      short loc_1800EC4CA
0x1800ec4c2  movsd   qword ptr [rsi], xmm6
0x1800ec4c6  mov     [rsi+8], r14d
0x1800ec4ca  xor     ebx, ebx
0x1800ec4cc  jmp     loc_1800EC5A2
0x1800ec4d1  test    edi, edi
0x1800ec4d3  jnz     loc_1800EC569
0x1800ec4d9  mov     eax, cs:dword_1801574B8
0x1800ec4df  mov     esi, 8007000Dh
0x1800ec4e4  test    eax, eax
0x1800ec4e6  jnz     short loc_1800EC4FB
0x1800ec4e8  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800ec4ee  jz      short loc_1800EC54E
0x1800ec4f0  xor     ecx, ecx
0x1800ec4f2  call    IsWppLevelEnabled
0x1800ec4f7  test    al, al
0x1800ec4f9  jz      short loc_1800EC54E
0x1800ec4fb  mov     rcx, [r15]; string
0x1800ec4fe  xor     edx, edx; length
0x1800ec500  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ec507  nop     dword ptr [rax+rax+00h]
0x1800ec50c  mov     rdx, r12; struct _GUID *
0x1800ec50f  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800ec513  mov     r11, rax
0x1800ec516  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800ec51b  mov     [rsp+1C0h+var_188], esi
0x1800ec51f  lea     rdx, aCpackagedcomca_3; "CPackagedComCatalog::ReadHighestTypeLib"...
0x1800ec526  mov     [rsp+1C0h+var_190], r11
0x1800ec52b  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ec532  mov     [rsp+1C0h+var_198], rax
0x1800ec537  mov     r8d, 2000h
0x1800ec53d  lea     rax, aNoVersionsFoun_0; "No versions found for typelib registrat"...
0x1800ec544  mov     [rsp+1C0h+var_1A0], rax
0x1800ec549  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800ec54e  lea     rcx, [rbp+0C0h+var_140]; this
0x1800ec552  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ec557  xor     ecx, ecx; string
0x1800ec559  call    cs:__imp_WindowsDeleteString
0x1800ec560  nop     dword ptr [rax+rax+00h]
0x1800ec565  mov     ebx, esi
0x1800ec567  jmp     short loc_1800EC5BC
0x1800ec569  lea     rcx, [rbp+0C0h+var_140]; this
0x1800ec56d  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ec572  xor     ecx, ecx; string
0x1800ec574  call    cs:__imp_WindowsDeleteString
0x1800ec57b  nop     dword ptr [rax+rax+00h]
0x1800ec580  mov     ebx, 8002801Dh
0x1800ec585  jmp     short loc_1800EC5BC
0x1800ec587  mov     r9d, ebx; char *
0x1800ec58a  mov     edx, 1FD3h; void *
0x1800ec58f  mov     rcx, [rbp+0C8h]; this
0x1800ec596  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ec59d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec5a2  lea     rcx, [rbp+0C0h+var_140]; this
0x1800ec5a6  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ec5ab  mov     rcx, [rsp+1C0h+var_160]; string
0x1800ec5b0  call    cs:__imp_WindowsDeleteString
0x1800ec5b7  nop     dword ptr [rax+rax+00h]
0x1800ec5bc  mov     rcx, [rsp+1C0h+string]; string
0x1800ec5c1  call    cs:__imp_WindowsDeleteString
0x1800ec5c8  nop     dword ptr [rax+rax+00h]
0x1800ec5cd  mov     eax, ebx
0x1800ec5cf  mov     rcx, [rbp+0C0h+var_60]
0x1800ec5d3  xor     rcx, rsp; StackCookie
0x1800ec5d6  call    __security_check_cookie
0x1800ec5db  movaps  xmm6, [rsp+1C0h+var_58+8]
0x1800ec5e3  add     rsp, 188h
0x1800ec5ea  pop     r15
0x1800ec5ec  pop     r14
0x1800ec5ee  pop     r13
0x1800ec5f0  pop     r12
0x1800ec5f2  pop     rdi
0x1800ec5f3  pop     rsi
0x1800ec5f4  pop     rbx
0x1800ec5f5  pop     rbp
0x1800ec5f6  retn
```
