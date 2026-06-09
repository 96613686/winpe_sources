# CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,ComRegistrationVisibility,CPackagedComCatalog::TypeLibVersion,bool,CPackagedComCatalog::TypeLibVersion *)

- ea: `0x1800e69ac`
- end: `0x1800e6d90`
- name: `?TryReadHighestTypeLibVersionEntryForPackage@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@W4ComRegistrationVisibility@@VTypeLibVersion@1@_NPEAV71@@Z`
- size: `996`
- prototype: `static int __high(struct ComTypeLibVersionRegistrationEntryProperties *, struct IPackagedComCatalogContext *, const struct OpaqueString *, const struct _GUID *, enum ComRegistrationVisibility, struct CPackagedComCatalog::TypeLibVersion, bool, struct CPackagedComCatalog::TypeLibVersion *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800a8ad4`
- `0x1800e50c8`

## callees

- `0x180016160`
- `0x18002ba28`
- `0x180034540`
- `0x1800414d0`
- `0x1800a9ec0`
- `0x1800b27e0`
- `0x1800d4290`
- `0x1800d9338`
- `0x1800e12b0`
- `0x1800e4548`
- `0x1800e69ac`
- `0x1800e6fa4`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6c56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6c56`

## string_xrefs

- `0x1800e6a4b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e6cc3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e6d30`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e6c6c`: `CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage(
        __int64 a1,
        __int64 *a2,
        HSTRING *a3,
        const struct _GUID *a4,
        __int64 a5,
        __int64 *a6,
        char a7,
        __int64 a8)
{
  unsigned int v8; // r14d
  __int64 v12; // xmm6_8
  int v13; // esi
  int v14; // eax
  unsigned int v15; // ebx
  HSTRING v16; // rcx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64 *, __int64, _QWORD, char *); // rbx
  int v19; // eax
  int SupportedAndVisibleTypeLibVersionEntry; // eax
  __int64 v21; // r8
  PCWSTR StringRawBuffer; // rdi
  CGuidStr *v23; // rbx
  PCWSTR v24; // rax
  __int64 v25; // r9
  HSTRING v27; // rbx
  int v28; // [rsp+28h] [rbp-E0h]
  char v29; // [rsp+58h] [rbp-B0h] BYREF
  __int16 v30; // [rsp+59h] [rbp-AFh]
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING v32; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+70h] [rbp-98h] BYREF
  int v34; // [rsp+78h] [rbp-90h]
  __int64 v35; // [rsp+88h] [rbp-80h] BYREF
  int v36; // [rsp+90h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v38[4]; // [rsp+A8h] [rbp-60h] BYREF
  int v39; // [rsp+ACh] [rbp-5Ch]
  char v40; // [rsp+B0h] [rbp-58h]
  int v41; // [rsp+B4h] [rbp-54h]
  char v42; // [rsp+B8h] [rbp-50h]
  __int64 v43; // [rsp+C0h] [rbp-48h]
  char v44; // [rsp+C8h] [rbp-40h]
  __int64 v45; // [rsp+D0h] [rbp-38h]
  char v46; // [rsp+D8h] [rbp-30h]
  __int64 v47; // [rsp+E0h] [rbp-28h]
  char v48; // [rsp+E8h] [rbp-20h]
  __int64 v49; // [rsp+F0h] [rbp-18h]
  __int16 v50; // [rsp+F8h] [rbp-10h]
  char v51; // [rsp+FCh] [rbp-Ch]
  int v52; // [rsp+100h] [rbp-8h]
  char v53; // [rsp+104h] [rbp-4h]
  int v54; // [rsp+108h] [rbp+0h]
  char v55; // [rsp+10Ch] [rbp+4h]
  int v56; // [rsp+110h] [rbp+8h]
  _BYTE v57[4]; // [rsp+118h] [rbp+10h] BYREF
  int v58; // [rsp+11Ch] [rbp+14h]
  char v59; // [rsp+120h] [rbp+18h]
  int v60; // [rsp+124h] [rbp+1Ch]
  char v61; // [rsp+128h] [rbp+20h]
  __int64 v62; // [rsp+130h] [rbp+28h]
  char v63; // [rsp+138h] [rbp+30h]
  __int64 v64; // [rsp+140h] [rbp+38h]
  char v65; // [rsp+148h] [rbp+40h]
  __int64 v66; // [rsp+150h] [rbp+48h]
  char v67; // [rsp+158h] [rbp+50h]
  __int64 v68; // [rsp+160h] [rbp+58h]
  __int16 v69; // [rsp+168h] [rbp+60h]
  char v70; // [rsp+16Ch] [rbp+64h]
  int v71; // [rsp+170h] [rbp+68h]
  char v72; // [rsp+174h] [rbp+6Ch]
  int v73; // [rsp+178h] [rbp+70h]
  char v74; // [rsp+17Ch] [rbp+74h]
  int v75; // [rsp+180h] [rbp+78h]
  __int64 v76; // [rsp+188h] [rbp+80h]
  _BYTE v77[80]; // [rsp+198h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+250h] [rbp+148h]

  v8 = 0;
  v76 = a1;
  if ( a8 )
  {
    *(_WORD *)(a8 + 9) = *(_WORD *)((char *)&v36 + 1);
    *(_BYTE *)(a8 + 11) = HIBYTE(v36);
    *(_QWORD *)a8 = 0;
    *(_BYTE *)(a8 + 8) = 0;
  }
  v37 = 0;
  v12 = *a6;
  v13 = *((_DWORD *)a6 + 2);
  v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, const struct _GUID *, __int64 *))(*a2 + 112))(a2, *a3, a4, &v37);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v16 = 0;
    string = 0;
    v32 = 0;
    v38[0] = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
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
    while ( 1 )
    {
      v17 = *a2;
      v29 = 0;
      v18 = *(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, char *))(v17 + 120);
      WindowsDeleteString(v16);
      string = 0;
      v19 = v18(a2, v37, v8, &v29);
      v15 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2029,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v19,
          (int)&string);
        goto LABEL_25;
      }
      if ( !v29 )
        break;
      v57[0] = 0;
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
      v74 = 0;
      v75 = 0;
      v30 = 0;
      SupportedAndVisibleTypeLibVersionEntry = CPackagedComCatalog::TryReadSupportedAndVisibleTypeLibVersionEntry(
                                                 v57,
                                                 a2,
                                                 a3,
                                                 a4);
      v15 = SupportedAndVisibleTypeLibVersionEntry;
      if ( SupportedAndVisibleTypeLibVersionEntry < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x204B,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)SupportedAndVisibleTypeLibVersionEntry,
          (int)&string);
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v57);
LABEL_25:
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v38);
        WindowsDeleteString(v32);
        WindowsDeleteString(string);
        return v15;
      }
      if ( (_BYTE)v30 )
      {
        v33 = 0;
        LOBYTE(v34) = 0;
        if ( (int)CPackagedComCatalog::ParseTypeLibVersionString(
                    string,
                    (struct CPackagedComCatalog::TypeLibVersion *)&v33) < 0 )
        {
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(*a3, 0);
            v23 = CGuidStr::CGuidStr((CGuidStr *)v77, a4);
            v24 = WindowsGetStringRawBuffer(string, 0);
            ComTraceMessageT<unsigned short const *,unsigned short *,unsigned short const *,long>(
              (__int64)L"Incorrectly-formatted typelib version number. VersionNumber:%S TypeLibId:%ws PackageName=%S hr=%!HRESULT!",
              (__int64)"CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage",
              0x205Eu,
              v25,
              (__int64)L"Incorrectly-formatted typelib version number. VersionNumber:%S TypeLibId:%ws PackageName=%S hr=%!HRESULT!",
              (__int64)v24,
              (__int64)v23,
              (__int64)StringRawBuffer,
              0x8007000D);
          }
          ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v57);
          ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v38);
          WindowsDeleteString(v32);
          WindowsDeleteString(string);
          return 2147942413LL;
        }
        LOBYTE(v21) = a7;
        v35 = v12;
        v36 = v13;
        if ( (unsigned __int8)CPackagedComCatalog::TypeLibVersion::IsGreaterThan(&v33, &v35, v21) )
        {
          OpaqueString::operator=(&v32, &string);
          v12 = v33;
          v13 = v34;
          ComTypeLibVersionRegistrationEntryProperties::operator=(v38, v57);
        }
      }
      ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v57);
      v16 = string;
      ++v8;
    }
    v27 = v32;
    if ( v32 )
    {
      ComTypeLibVersionRegistrationEntryProperties::operator=(v76, v38);
      if ( a8 )
      {
        *(_QWORD *)a8 = v12;
        *(_DWORD *)(a8 + 8) = v13;
      }
    }
    ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v38);
    WindowsDeleteString(v27);
    WindowsDeleteString(string);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x201E,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v14,
      v28);
    return v15;
  }
}

```

## disassembly

```asm
0x1800e69ac  mov     rax, rsp
0x1800e69af  push    rbp
0x1800e69b0  push    rbx
0x1800e69b1  push    rsi
0x1800e69b2  push    rdi
0x1800e69b3  push    r12
0x1800e69b5  push    r13
0x1800e69b7  push    r14
0x1800e69b9  push    r15
0x1800e69bb  lea     rbp, [rax-148h]
0x1800e69c2  sub     rsp, 208h
0x1800e69c9  movaps  xmmword ptr [rax-58h], xmm6
0x1800e69cd  mov     rax, cs:__security_cookie
0x1800e69d4  xor     rax, rsp
0x1800e69d7  mov     [rbp+140h+var_60], rax
0x1800e69de  mov     rdi, [rbp+140h+arg_38]
0x1800e69e5  xor     r14d, r14d
0x1800e69e8  mov     [rbp+140h+var_C0], rcx
0x1800e69ef  mov     r13, r9
0x1800e69f2  mov     r12, r8
0x1800e69f5  mov     r15, rdx
0x1800e69f8  test    rdi, rdi
0x1800e69fb  jz      short loc_1800E6A12
0x1800e69fd  movzx   eax, [rbp+140h+var_1B7]
0x1800e6a01  mov     [rdi+9], ax
0x1800e6a05  mov     al, [rbp+140h+var_1B5]
0x1800e6a08  mov     [rdi+0Bh], al
0x1800e6a0b  mov     [rdi], r14
0x1800e6a0e  mov     [rdi+8], r14b
0x1800e6a12  mov     rax, [rbp+140h+arg_28]
0x1800e6a19  lea     r9, [rbp+140h+var_1B0]
0x1800e6a1d  mov     r8, r13
0x1800e6a20  mov     [rbp+140h+var_1B0], r14
0x1800e6a24  mov     rcx, r15
0x1800e6a27  movsd   xmm6, qword ptr [rax]
0x1800e6a2b  mov     esi, [rax+8]
0x1800e6a2e  mov     rax, [rdx]
0x1800e6a31  mov     rdx, [r12]
0x1800e6a35  mov     rax, [rax+70h]
0x1800e6a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6a3e  mov     ebx, eax
0x1800e6a40  test    eax, eax
0x1800e6a42  jns     short loc_1800E6A64
0x1800e6a44  mov     rcx, [rbp+148h]; this
0x1800e6a4b  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e6a52  mov     r9d, eax; char *
0x1800e6a55  mov     edx, 201Eh; void *
0x1800e6a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6a5f  jmp     loc_1800E6D63
0x1800e6a64  xor     ebx, ebx
0x1800e6a66  mov     ecx, ebx; string
0x1800e6a68  mov     [rsp+240h+string], rbx
0x1800e6a6d  mov     [rsp+240h+var_1E0], rbx
0x1800e6a72  mov     [rbp+140h+var_1A0], bl
0x1800e6a75  mov     [rbp+140h+var_19C], ebx
0x1800e6a78  mov     [rbp+140h+var_198], bl
0x1800e6a7b  mov     [rbp+140h+var_194], ebx
0x1800e6a7e  mov     [rbp+140h+var_190], bl
0x1800e6a81  mov     [rbp+140h+var_188], rbx
0x1800e6a85  mov     [rbp+140h+var_180], bl
0x1800e6a88  mov     [rbp+140h+var_178], rbx
0x1800e6a8c  mov     [rbp+140h+var_170], bl
0x1800e6a8f  mov     [rbp+140h+var_168], rbx
0x1800e6a93  mov     [rbp+140h+var_160], bl
0x1800e6a96  mov     [rbp+140h+var_158], rbx
0x1800e6a9a  mov     [rbp+140h+var_150], bx
0x1800e6a9e  mov     [rbp+140h+var_14C], bl
0x1800e6aa1  mov     [rbp+140h+var_148], ebx
0x1800e6aa4  mov     [rbp+140h+var_144], bl
0x1800e6aa7  mov     [rbp+140h+var_140], ebx
0x1800e6aaa  mov     [rbp+140h+var_13C], bl
0x1800e6aad  mov     [rbp+140h+var_138], ebx
0x1800e6ab0  mov     rax, [r15]
0x1800e6ab3  mov     byte ptr [rsp+240h+var_1F0], bl
0x1800e6ab7  mov     rbx, [rax+78h]
0x1800e6abb  call    cs:__imp_WindowsDeleteString
0x1800e6ac1  mov     rdx, [rbp+140h+var_1B0]
0x1800e6ac5  lea     rax, [rsp+240h+string]
0x1800e6aca  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800e6acf  lea     r9, [rsp+240h+var_1F0]
0x1800e6ad4  mov     rax, rbx
0x1800e6ad7  mov     [rsp+240h+string], 0
0x1800e6ae0  mov     r8d, r14d
0x1800e6ae3  mov     rcx, r15
0x1800e6ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6aeb  xor     ecx, ecx
0x1800e6aed  mov     ebx, eax
0x1800e6aef  test    eax, eax
0x1800e6af1  js      loc_1800E6D29
0x1800e6af7  cmp     byte ptr [rsp+240h+var_1F0], cl
0x1800e6afb  jz      loc_1800E6CE2
0x1800e6b01  lea     rax, [rsp+240h+var_1F0+1]
0x1800e6b06  mov     [rbp+140h+var_130], cl
0x1800e6b09  mov     qword ptr [rsp+240h+var_208], rax
0x1800e6b0e  mov     r9, r13
0x1800e6b11  lea     rax, [rsp+240h+var_1F0+2]
0x1800e6b16  mov     [rbp+140h+var_12C], ecx
0x1800e6b19  mov     [rsp+240h+var_210], rax
0x1800e6b1e  mov     r8, r12
0x1800e6b21  mov     eax, [rbp+140h+arg_20]
0x1800e6b27  mov     rdx, r15
0x1800e6b2a  mov     dword ptr [rsp+240h+var_218], eax
0x1800e6b2e  lea     rax, [rsp+240h+string]
0x1800e6b33  mov     [rbp+140h+var_128], cl
0x1800e6b36  mov     [rbp+140h+var_124], ecx
0x1800e6b39  mov     [rbp+140h+var_120], cl
0x1800e6b3c  mov     [rbp+140h+var_118], rcx
0x1800e6b40  mov     [rbp+140h+var_110], cl
0x1800e6b43  mov     [rbp+140h+var_108], rcx
0x1800e6b47  mov     [rbp+140h+var_100], cl
0x1800e6b4a  mov     [rbp+140h+var_F8], rcx
0x1800e6b4e  mov     [rbp+140h+var_F0], cl
0x1800e6b51  mov     [rbp+140h+var_E8], rcx
0x1800e6b55  mov     [rbp+140h+var_E0], cx
0x1800e6b59  mov     [rbp+140h+var_DC], cl
0x1800e6b5c  mov     [rbp+140h+var_D8], ecx
0x1800e6b5f  mov     [rbp+140h+var_D4], cl
0x1800e6b62  mov     [rbp+140h+var_D0], ecx
0x1800e6b65  mov     [rbp+140h+var_CC], cl
0x1800e6b68  mov     [rbp+140h+var_C8], ecx
0x1800e6b6b  mov     byte ptr [rsp+240h+var_1F0+2], cl
0x1800e6b6f  mov     byte ptr [rsp+240h+var_1F0+1], cl
0x1800e6b73  lea     rcx, [rbp+140h+var_130]
0x1800e6b77  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800e6b7c  call    ?TryReadSupportedAndVisibleTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2W4ComRegistrationVisibility@@AEA_N5@Z; CPackagedComCatalog::TryReadSupportedAndVisibleTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &,ComRegistrationVisibility,bool &,bool &)
0x1800e6b81  mov     ebx, eax
0x1800e6b83  test    eax, eax
0x1800e6b85  js      loc_1800E6CBC
0x1800e6b8b  xor     ebx, ebx
0x1800e6b8d  cmp     byte ptr [rsp+240h+var_1F0+1], bl
0x1800e6b91  jz      short loc_1800E6BF6
0x1800e6b93  mov     rcx, [rsp+240h+string]; HSTRING
0x1800e6b98  lea     rdx, [rsp+240h+var_1D8]; struct CPackagedComCatalog::TypeLibVersion *
0x1800e6b9d  mov     [rsp+240h+var_1D8], rbx
0x1800e6ba2  mov     byte ptr [rsp+240h+var_1D0], bl
0x1800e6ba6  call    ?ParseTypeLibVersionString@CPackagedComCatalog@@CAJPEAUHSTRING__@@PEAVTypeLibVersion@1@@Z; CPackagedComCatalog::ParseTypeLibVersionString(HSTRING__ *,CPackagedComCatalog::TypeLibVersion *)
0x1800e6bab  test    eax, eax
0x1800e6bad  js      short loc_1800E6C0C
0x1800e6baf  mov     r8b, [rbp+140h+arg_30]
0x1800e6bb6  lea     rdx, [rbp+140h+var_1C0]
0x1800e6bba  lea     rcx, [rsp+240h+var_1D8]
0x1800e6bbf  movsd   [rbp+140h+var_1C0], xmm6
0x1800e6bc4  mov     [rbp-78h], esi
0x1800e6bc7  call    ?IsGreaterThan@TypeLibVersion@CPackagedComCatalog@@QEAA_NV12@_N@Z; CPackagedComCatalog::TypeLibVersion::IsGreaterThan(CPackagedComCatalog::TypeLibVersion,bool)
0x1800e6bcc  test    al, al
0x1800e6bce  jz      short loc_1800E6BF6
0x1800e6bd0  lea     rdx, [rsp+240h+string]
0x1800e6bd5  lea     rcx, [rsp+240h+var_1E0]
0x1800e6bda  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800e6bdf  movsd   xmm6, [rsp+240h+var_1D8]
0x1800e6be5  lea     rdx, [rbp+140h+var_130]
0x1800e6be9  mov     esi, [rsp+240h+var_1D0]
0x1800e6bed  lea     rcx, [rbp+140h+var_1A0]
0x1800e6bf1  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@AEBU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800e6bf6  lea     rcx, [rbp+140h+var_130]; this
0x1800e6bfa  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e6bff  mov     rcx, [rsp+240h+string]
0x1800e6c04  inc     r14d
0x1800e6c07  jmp     loc_1800E6AB0
0x1800e6c0c  mov     eax, cs:dword_18014E4B8
0x1800e6c12  mov     esi, 8007000Dh
0x1800e6c17  test    eax, eax
0x1800e6c19  jnz     short loc_1800E6C2E
0x1800e6c1b  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800e6c21  jz      short loc_1800E6C8D
0x1800e6c23  xor     ecx, ecx
0x1800e6c25  call    IsWppLevelEnabled
0x1800e6c2a  test    al, al
0x1800e6c2c  jz      short loc_1800E6C8D
0x1800e6c2e  mov     rcx, [r12]; string
0x1800e6c32  xor     edx, edx; length
0x1800e6c34  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e6c3a  mov     rdx, r13; struct _GUID *
0x1800e6c3d  lea     rcx, [rbp+140h+var_B0]; this
0x1800e6c44  mov     rdi, rax
0x1800e6c47  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e6c4c  mov     rcx, [rsp+240h+string]; string
0x1800e6c51  xor     edx, edx; length
0x1800e6c53  mov     rbx, rax
0x1800e6c56  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e6c5c  mov     [rsp+40h], esi
0x1800e6c60  lea     rcx, aIncorrectlyFor; "Incorrectly-formatted typelib version n"...
0x1800e6c67  mov     qword ptr [rsp+240h+var_208], rdi
0x1800e6c6c  lea     rdx, aCpackagedcomca_9; "CPackagedComCatalog::TryReadHighestType"...
0x1800e6c73  mov     [rsp+240h+var_210], rbx
0x1800e6c78  mov     r8d, 205Eh
0x1800e6c7e  mov     [rsp+240h+var_218], rax
0x1800e6c83  mov     qword ptr [rsp+240h+var_220], rcx
0x1800e6c88  call    ??$ComTraceMessageT@PEBGPEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG2J@Z; ComTraceMessageT<ushort const *,ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,ushort const *,long)
0x1800e6c8d  lea     rcx, [rbp+140h+var_130]; this
0x1800e6c91  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e6c96  lea     rcx, [rbp+140h+var_1A0]; this
0x1800e6c9a  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e6c9f  mov     rcx, [rsp+240h+var_1E0]; string
0x1800e6ca4  call    cs:__imp_WindowsDeleteString
0x1800e6caa  mov     rcx, [rsp+240h+string]; string
0x1800e6caf  call    cs:__imp_WindowsDeleteString
0x1800e6cb5  mov     eax, esi
0x1800e6cb7  jmp     loc_1800E6D65
0x1800e6cbc  mov     rcx, [rbp+148h]; this
0x1800e6cc3  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e6cca  mov     r9d, ebx; char *
0x1800e6ccd  mov     edx, 204Bh; void *
0x1800e6cd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6cd7  lea     rcx, [rbp+140h+var_130]; this
0x1800e6cdb  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e6ce0  jmp     short loc_1800E6D44
0x1800e6ce2  mov     rbx, [rsp+240h+var_1E0]
0x1800e6ce7  test    rbx, rbx
0x1800e6cea  jz      short loc_1800E6D08
0x1800e6cec  mov     rcx, [rbp+140h+var_C0]
0x1800e6cf3  lea     rdx, [rbp+140h+var_1A0]
0x1800e6cf7  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@AEBU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800e6cfc  test    rdi, rdi
0x1800e6cff  jz      short loc_1800E6D08
0x1800e6d01  movsd   qword ptr [rdi], xmm6
0x1800e6d05  mov     [rdi+8], esi
0x1800e6d08  lea     rcx, [rbp+140h+var_1A0]; this
0x1800e6d0c  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e6d11  mov     rcx, rbx; string
0x1800e6d14  call    cs:__imp_WindowsDeleteString
0x1800e6d1a  mov     rcx, [rsp+240h+string]; string
0x1800e6d1f  call    cs:__imp_WindowsDeleteString
0x1800e6d25  xor     eax, eax
0x1800e6d27  jmp     short loc_1800E6D65
0x1800e6d29  mov     rcx, [rbp+148h]; this
0x1800e6d30  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e6d37  mov     r9d, ebx; char *
0x1800e6d3a  mov     edx, 2029h; void *
0x1800e6d3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e6d44  lea     rcx, [rbp+140h+var_1A0]; this
0x1800e6d48  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800e6d4d  mov     rcx, [rsp+240h+var_1E0]; string
0x1800e6d52  call    cs:__imp_WindowsDeleteString
0x1800e6d58  mov     rcx, [rsp+240h+string]; string
0x1800e6d5d  call    cs:__imp_WindowsDeleteString
0x1800e6d63  mov     eax, ebx
0x1800e6d65  mov     rcx, [rbp+140h+var_60]
0x1800e6d6c  xor     rcx, rsp; StackCookie
0x1800e6d6f  call    __security_check_cookie
0x1800e6d74  movaps  xmm6, [rsp+240h+var_58+8]
0x1800e6d7c  add     rsp, 208h
0x1800e6d83  pop     r15
0x1800e6d85  pop     r14
0x1800e6d87  pop     r13
0x1800e6d89  pop     r12
0x1800e6d8b  pop     rdi
0x1800e6d8c  pop     rsi
0x1800e6d8d  pop     rbx
0x1800e6d8e  pop     rbp
0x1800e6d8f  retn
```
