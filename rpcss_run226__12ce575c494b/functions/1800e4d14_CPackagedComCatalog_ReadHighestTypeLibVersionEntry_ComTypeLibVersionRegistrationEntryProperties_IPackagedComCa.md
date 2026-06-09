# CPackagedComCatalog::ReadHighestTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,CPackagedComCatalog::TypeLibVersion,bool,CPackagedComCatalog::TypeLibVersion *)

- ea: `0x1800e4d14`
- end: `0x1800e50bf`
- name: `?ReadHighestTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@VTypeLibVersion@1@_NPEAV61@@Z`
- size: `939`
- prototype: `static int __high(struct ComTypeLibVersionRegistrationEntryProperties *, struct IPackagedComCatalogContext *, const struct OpaqueString *, const struct _GUID *, struct CPackagedComCatalog::TypeLibVersion, bool, struct CPackagedComCatalog::TypeLibVersion *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800a97ac`
- `0x1800e022c`

## callees

- `0x180005c40`
- `0x180016160`
- `0x18002ba28`
- `0x180034540`
- `0x1800414d0`
- `0x18008e98c`
- `0x18009ffc0`
- `0x1800a9ec0`
- `0x1800b27e0`
- `0x1800d4290`
- `0x1800e12b0`
- `0x1800e4548`
- `0x1800e4d14`
- `0x1800e51e0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4f60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e504e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e508f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4f55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4f60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e504e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e508f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4f10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4fe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4ef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4f10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4fe6`

## string_xrefs

- `0x1800e4dac`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e500b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e506a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e4f1a`: `CPackagedComCatalog::ReadHighestTypeLibVersionEntry`
- `0x1800e4fff`: `CPackagedComCatalog::ReadHighestTypeLibVersionEntry`

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
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x1800e4d14  mov     rax, rsp
0x1800e4d17  push    rbp
0x1800e4d18  push    rbx
0x1800e4d19  push    rsi
0x1800e4d1a  push    rdi
0x1800e4d1b  push    r12
0x1800e4d1d  push    r13
0x1800e4d1f  push    r14
0x1800e4d21  push    r15
0x1800e4d23  lea     rbp, [rax-0C8h]
0x1800e4d2a  sub     rsp, 188h
0x1800e4d31  movaps  xmmword ptr [rax-58h], xmm6
0x1800e4d35  mov     rax, cs:__security_cookie
0x1800e4d3c  xor     rax, rsp
0x1800e4d3f  mov     [rbp+0C0h+var_60], rax
0x1800e4d43  mov     rsi, [rbp+0C0h+arg_30]
0x1800e4d4a  mov     r12, r9
0x1800e4d4d  mov     r15, r8
0x1800e4d50  mov     [rbp+0C0h+var_D0], rcx
0x1800e4d54  mov     r13, rdx
0x1800e4d57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800e4d5e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800e4d63  test    al, al
0x1800e4d65  jz      short loc_1800E4D6C
0x1800e4d67  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e4d6c  mov     rax, [rbp+0C0h+arg_20]
0x1800e4d73  lea     r9, [rsp+1C0h+var_148]
0x1800e4d78  mov     rdx, [r15]
0x1800e4d7b  mov     r8, r12
0x1800e4d7e  mov     rcx, r13
0x1800e4d81  mov     [rsp+1C0h+var_148], 0
0x1800e4d8a  movsd   xmm6, qword ptr [rax]
0x1800e4d8e  mov     r14d, [rax+8]
0x1800e4d92  mov     rax, [r13+0]
0x1800e4d96  mov     rax, [rax+70h]
0x1800e4d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4d9f  mov     ebx, eax
0x1800e4da1  test    eax, eax
0x1800e4da3  jns     short loc_1800E4DC5
0x1800e4da5  mov     rcx, [rbp+0C8h]; this
0x1800e4dac  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e4db3  mov     r9d, eax; char *
0x1800e4db6  mov     edx, 1FC8h; void *
0x1800e4dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4dc0  jmp     loc_1800E5095
0x1800e4dc5  xor     ebx, ebx
0x1800e4dc7  mov     ecx, ebx; string
0x1800e4dc9  mov     [rsp+1C0h+string], rbx
0x1800e4dce  mov     [rsp+1C0h+var_160], rbx
0x1800e4dd3  mov     edi, ebx
0x1800e4dd5  mov     [rbp+0C0h+var_140], bl
0x1800e4dd8  mov     [rbp+0C0h+var_13C], ebx
0x1800e4ddb  mov     [rbp+0C0h+var_138], bl
0x1800e4dde  mov     [rbp+0C0h+var_134], ebx
0x1800e4de1  mov     [rbp+0C0h+var_130], bl
0x1800e4de4  mov     [rbp+0C0h+var_128], rbx
0x1800e4de8  mov     [rbp+0C0h+var_120], bl
0x1800e4deb  mov     [rbp+0C0h+var_118], rbx
0x1800e4def  mov     [rbp+0C0h+var_110], bl
0x1800e4df2  mov     [rbp+0C0h+var_108], rbx
0x1800e4df6  mov     [rbp+0C0h+var_100], bl
0x1800e4df9  mov     [rbp+0C0h+var_F8], rbx
0x1800e4dfd  mov     [rbp+0C0h+var_F0], bx
0x1800e4e01  mov     [rbp+0C0h+var_EC], bl
0x1800e4e04  mov     [rbp+0C0h+var_E8], ebx
0x1800e4e07  mov     [rbp+0C0h+var_E4], bl
0x1800e4e0a  mov     [rbp+0C0h+var_E0], ebx
0x1800e4e0d  mov     [rbp+0C0h+var_DC], bl
0x1800e4e10  mov     [rbp+0C0h+var_D8], ebx
0x1800e4e13  mov     rax, [r13+0]
0x1800e4e17  mov     byte ptr [rsp+1C0h+var_170], bl
0x1800e4e1b  mov     rbx, [rax+78h]
0x1800e4e1f  call    cs:__imp_WindowsDeleteString
0x1800e4e25  mov     rdx, [rsp+1C0h+var_148]
0x1800e4e2a  lea     rax, [rsp+1C0h+string]
0x1800e4e2f  mov     [rsp+1C0h+var_1A0], rax; int
0x1800e4e34  lea     r9, [rsp+1C0h+var_170]
0x1800e4e39  mov     rax, rbx
0x1800e4e3c  mov     [rsp+1C0h+string], 0
0x1800e4e45  mov     r8d, edi
0x1800e4e48  mov     rcx, r13
0x1800e4e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4e50  mov     ebx, eax
0x1800e4e52  test    eax, eax
0x1800e4e54  js      loc_1800E505B
0x1800e4e5a  xor     ebx, ebx
0x1800e4e5c  cmp     byte ptr [rsp+1C0h+var_170], bl
0x1800e4e60  jz      loc_1800E4F6D
0x1800e4e66  mov     rcx, [rsp+1C0h+string]; HSTRING
0x1800e4e6b  lea     rdx, [rsp+1C0h+var_158]; struct CPackagedComCatalog::TypeLibVersion *
0x1800e4e70  mov     [rsp+1C0h+var_158], rbx
0x1800e4e75  mov     byte ptr [rsp+1C0h+var_150], bl
0x1800e4e79  call    ?ParseTypeLibVersionString@CPackagedComCatalog@@CAJPEAUHSTRING__@@PEAVTypeLibVersion@1@@Z; CPackagedComCatalog::ParseTypeLibVersionString(HSTRING__ *,CPackagedComCatalog::TypeLibVersion *)
0x1800e4e7e  test    eax, eax
0x1800e4e80  js      short loc_1800E4ECA
0x1800e4e82  mov     r8b, [rbp+0C0h+arg_28]
0x1800e4e89  lea     rdx, [rbp+0C0h+var_C0]
0x1800e4e8d  lea     rcx, [rsp+1C0h+var_158]
0x1800e4e92  movsd   [rbp+0C0h+var_C0], xmm6
0x1800e4e97  mov     [rbp+0C0h+var_B8], r14d
0x1800e4e9b  call    ?IsGreaterThan@TypeLibVersion@CPackagedComCatalog@@QEAA_NV12@_N@Z; CPackagedComCatalog::TypeLibVersion::IsGreaterThan(CPackagedComCatalog::TypeLibVersion,bool)
0x1800e4ea0  test    al, al
0x1800e4ea2  jz      short loc_1800E4EBE
0x1800e4ea4  lea     rdx, [rsp+1C0h+string]
0x1800e4ea9  lea     rcx, [rsp+1C0h+var_160]
0x1800e4eae  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800e4eb3  movsd   xmm6, [rsp+1C0h+var_158]
0x1800e4eb9  mov     r14d, dword ptr [rsp+1C0h+var_150]
0x1800e4ebe  mov     rcx, [rsp+1C0h+string]
0x1800e4ec3  inc     edi
0x1800e4ec5  jmp     loc_1800E4E13
0x1800e4eca  mov     eax, cs:dword_18014E4B8
0x1800e4ed0  mov     esi, 8007000Dh
0x1800e4ed5  test    eax, eax
0x1800e4ed7  jnz     short loc_1800E4EEC
0x1800e4ed9  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800e4edf  jz      short loc_1800E4F47
0x1800e4ee1  xor     ecx, ecx
0x1800e4ee3  call    IsWppLevelEnabled
0x1800e4ee8  test    al, al
0x1800e4eea  jz      short loc_1800E4F47
0x1800e4eec  mov     rcx, [r15]; string
0x1800e4eef  xor     edx, edx; length
0x1800e4ef1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4ef7  mov     rdx, r12; struct _GUID *
0x1800e4efa  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800e4efe  mov     rdi, rax
0x1800e4f01  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e4f06  mov     rcx, [rsp+1C0h+string]; string
0x1800e4f0b  xor     edx, edx; length
0x1800e4f0d  mov     rbx, rax
0x1800e4f10  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4f16  mov     [rsp+40h], esi
0x1800e4f1a  lea     rdx, aCpackagedcomca_3; "CPackagedComCatalog::ReadHighestTypeLib"...
0x1800e4f21  mov     qword ptr [rsp+1C0h+var_188], rdi
0x1800e4f26  mov     r8d, 1FE3h
0x1800e4f2c  mov     [rsp+1C0h+var_190], rbx
0x1800e4f31  mov     [rsp+1C0h+var_198], rax
0x1800e4f36  lea     rax, aIncorrectlyFor; "Incorrectly-formatted typelib version n"...
0x1800e4f3d  mov     [rsp+1C0h+var_1A0], rax
0x1800e4f42  call    ??$ComTraceMessageT@PEBGPEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG2J@Z; ComTraceMessageT<ushort const *,ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,ushort const *,long)
0x1800e4f47  lea     rcx, [rbp+0C0h+var_140]; this
0x1800e4f4b  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e4f50  mov     rcx, [rsp+1C0h+var_160]; string
0x1800e4f55  call    cs:__imp_WindowsDeleteString
0x1800e4f5b  mov     rcx, [rsp+1C0h+string]; string
0x1800e4f60  call    cs:__imp_WindowsDeleteString
0x1800e4f66  mov     eax, esi
0x1800e4f68  jmp     loc_1800E5097
0x1800e4f6d  cmp     [rsp+1C0h+var_160], rbx
0x1800e4f72  jz      short loc_1800E4FB7
0x1800e4f74  mov     rcx, [rbp+0C0h+var_D0]; struct ComTypeLibVersionRegistrationEntryProperties *
0x1800e4f78  lea     rax, [rsp+1C0h+var_160]
0x1800e4f7d  mov     r9, r12; struct _GUID *
0x1800e4f80  mov     [rsp+1C0h+var_1A0], rax; struct OpaqueString *
0x1800e4f85  mov     r8, r15; struct OpaqueString *
0x1800e4f88  mov     rdx, r13; struct IPackagedComCatalogContext *
0x1800e4f8b  call    ?ReadTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2@Z; CPackagedComCatalog::ReadTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &)
0x1800e4f90  mov     ebx, eax
0x1800e4f92  test    eax, eax
0x1800e4f94  jns     short loc_1800E4FA3
0x1800e4f96  mov     r9d, eax
0x1800e4f99  mov     edx, 1FF4h
0x1800e4f9e  jmp     loc_1800E5063
0x1800e4fa3  test    rsi, rsi
0x1800e4fa6  jz      short loc_1800E4FB0
0x1800e4fa8  movsd   qword ptr [rsi], xmm6
0x1800e4fac  mov     [rsi+8], r14d
0x1800e4fb0  xor     ebx, ebx
0x1800e4fb2  jmp     loc_1800E5076
0x1800e4fb7  test    edi, edi
0x1800e4fb9  jnz     loc_1800E5043
0x1800e4fbf  mov     eax, cs:dword_18014E4B8
0x1800e4fc5  mov     esi, 8007000Dh
0x1800e4fca  test    eax, eax
0x1800e4fcc  jnz     short loc_1800E4FE1
0x1800e4fce  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800e4fd4  jz      short loc_1800E502E
0x1800e4fd6  xor     ecx, ecx
0x1800e4fd8  call    IsWppLevelEnabled
0x1800e4fdd  test    al, al
0x1800e4fdf  jz      short loc_1800E502E
0x1800e4fe1  mov     rcx, [r15]; string
0x1800e4fe4  xor     edx, edx; length
0x1800e4fe6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4fec  mov     rdx, r12; struct _GUID *
0x1800e4fef  lea     rcx, [rbp+0C0h+var_B0]; this
0x1800e4ff3  mov     r11, rax
0x1800e4ff6  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e4ffb  mov     [rsp+1C0h+var_188], esi
0x1800e4fff  lea     rdx, aCpackagedcomca_3; "CPackagedComCatalog::ReadHighestTypeLib"...
0x1800e5006  mov     [rsp+1C0h+var_190], r11
0x1800e500b  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5012  mov     [rsp+1C0h+var_198], rax
0x1800e5017  mov     r8d, 2000h
0x1800e501d  lea     rax, aNoVersionsFoun_0; "No versions found for typelib registrat"...
0x1800e5024  mov     [rsp+1C0h+var_1A0], rax
0x1800e5029  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800e502e  lea     rcx, [rbp+0C0h+var_140]; this
0x1800e5032  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e5037  xor     ecx, ecx; string
0x1800e5039  call    cs:__imp_WindowsDeleteString
0x1800e503f  mov     ebx, esi
0x1800e5041  jmp     short loc_1800E508A
0x1800e5043  lea     rcx, [rbp+0C0h+var_140]; this
0x1800e5047  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e504c  xor     ecx, ecx; string
0x1800e504e  call    cs:__imp_WindowsDeleteString
0x1800e5054  mov     ebx, 8002801Dh
0x1800e5059  jmp     short loc_1800E508A
0x1800e505b  mov     r9d, ebx; char *
0x1800e505e  mov     edx, 1FD3h; void *
0x1800e5063  mov     rcx, [rbp+0C8h]; this
0x1800e506a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e5071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5076  lea     rcx, [rbp+0C0h+var_140]; this
0x1800e507a  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e507f  mov     rcx, [rsp+1C0h+var_160]; string
0x1800e5084  call    cs:__imp_WindowsDeleteString
0x1800e508a  mov     rcx, [rsp+1C0h+string]; string
0x1800e508f  call    cs:__imp_WindowsDeleteString
0x1800e5095  mov     eax, ebx
0x1800e5097  mov     rcx, [rbp+0C0h+var_60]
0x1800e509b  xor     rcx, rsp; StackCookie
0x1800e509e  call    __security_check_cookie
0x1800e50a3  movaps  xmm6, [rsp+1C0h+var_58+8]
0x1800e50ab  add     rsp, 188h
0x1800e50b2  pop     r15
0x1800e50b4  pop     r14
0x1800e50b6  pop     r13
0x1800e50b8  pop     r12
0x1800e50ba  pop     rdi
0x1800e50bb  pop     rsi
0x1800e50bc  pop     rbx
0x1800e50bd  pop     rbp
0x1800e50be  retn
```
