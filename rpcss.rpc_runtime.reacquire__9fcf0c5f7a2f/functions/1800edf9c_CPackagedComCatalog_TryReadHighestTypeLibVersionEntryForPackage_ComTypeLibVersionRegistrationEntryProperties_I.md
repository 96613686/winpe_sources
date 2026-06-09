# CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,ComRegistrationVisibility,CPackagedComCatalog::TypeLibVersion,bool,CPackagedComCatalog::TypeLibVersion *)

- ea: `0x1800edf9c`
- end: `0x1800ee3b7`
- name: `?TryReadHighestTypeLibVersionEntryForPackage@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@W4ComRegistrationVisibility@@VTypeLibVersion@1@_NPEAV71@@Z`
- size: `1051`
- prototype: `static int __high(struct ComTypeLibVersionRegistrationEntryProperties *, struct IPackagedComCatalogContext *, const struct OpaqueString *, const struct _GUID *, enum ComRegistrationVisibility, struct CPackagedComCatalog::TypeLibVersion, bool, struct CPackagedComCatalog::TypeLibVersion *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800adba8`
- `0x1800ec600`

## callees

- `0x18001a374`
- `0x1800210f8`
- `0x180034260`
- `0x18004b0f0`
- `0x1800aefc4`
- `0x1800b7ac0`
- `0x1800dac84`
- `0x1800e0100`
- `0x1800e8504`
- `0x1800eba28`
- `0x1800edf9c`
- `0x1800ee5c8`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee36c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee37d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee2a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee36c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ee37d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ee22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ee252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ee22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ee252`

## string_xrefs

- `0x1800ee03b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ee2d1`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ee34a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ee26e`: `CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage`

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
  int v25; // r9d
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
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(*a3, 0);
            v23 = CGuidStr::CGuidStr((CGuidStr *)v77, a4);
            v24 = WindowsGetStringRawBuffer(string, 0);
            ComTraceMessageT<unsigned short const *,unsigned short *,unsigned short const *,long>(
              (unsigned int)L"Incorrectly-formatted typelib version number. VersionNumber:%S TypeLibId:%ws PackageName=%S hr=%!HRESULT!",
              (unsigned int)"CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage",
              8286,
              v25,
              (__int64)L"Incorrectly-formatted typelib version number. VersionNumber:%S TypeLibId:%ws PackageName=%S hr=%!HRESULT!",
              v24,
              v23,
              StringRawBuffer,
              -2147024883);
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
0x1800edf9c  mov     rax, rsp
0x1800edf9f  push    rbp
0x1800edfa0  push    rbx
0x1800edfa1  push    rsi
0x1800edfa2  push    rdi
0x1800edfa3  push    r12
0x1800edfa5  push    r13
0x1800edfa7  push    r14
0x1800edfa9  push    r15
0x1800edfab  lea     rbp, [rax-148h]
0x1800edfb2  sub     rsp, 208h
0x1800edfb9  movaps  xmmword ptr [rax-58h], xmm6
0x1800edfbd  mov     rax, cs:__security_cookie
0x1800edfc4  xor     rax, rsp
0x1800edfc7  mov     [rbp+140h+var_60], rax
0x1800edfce  mov     rdi, [rbp+140h+arg_38]
0x1800edfd5  xor     r14d, r14d
0x1800edfd8  mov     [rbp+140h+var_C0], rcx
0x1800edfdf  mov     r13, r9
0x1800edfe2  mov     r12, r8
0x1800edfe5  mov     r15, rdx
0x1800edfe8  test    rdi, rdi
0x1800edfeb  jz      short loc_1800EE002
0x1800edfed  movzx   eax, [rbp+140h+var_1B7]
0x1800edff1  mov     [rdi+9], ax
0x1800edff5  mov     al, [rbp+140h+var_1B5]
0x1800edff8  mov     [rdi+0Bh], al
0x1800edffb  mov     [rdi], r14
0x1800edffe  mov     [rdi+8], r14b
0x1800ee002  mov     rax, [rbp+140h+arg_28]
0x1800ee009  lea     r9, [rbp+140h+var_1B0]
0x1800ee00d  mov     r8, r13
0x1800ee010  mov     [rbp+140h+var_1B0], r14
0x1800ee014  mov     rcx, r15
0x1800ee017  movsd   xmm6, qword ptr [rax]
0x1800ee01b  mov     esi, [rax+8]
0x1800ee01e  mov     rax, [rdx]
0x1800ee021  mov     rdx, [r12]
0x1800ee025  mov     rax, [rax+70h]
0x1800ee029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee02e  mov     ebx, eax
0x1800ee030  test    eax, eax
0x1800ee032  jns     short loc_1800EE054
0x1800ee034  mov     rcx, [rbp+148h]; this
0x1800ee03b  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ee042  mov     r9d, eax; char *
0x1800ee045  mov     edx, 201Eh; void *
0x1800ee04a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee04f  jmp     loc_1800EE389
0x1800ee054  xor     ebx, ebx
0x1800ee056  mov     ecx, ebx; string
0x1800ee058  mov     [rsp+240h+string], rbx
0x1800ee05d  mov     [rsp+240h+var_1E0], rbx
0x1800ee062  mov     [rbp+140h+var_1A0], bl
0x1800ee065  mov     [rbp+140h+var_19C], ebx
0x1800ee068  mov     [rbp+140h+var_198], bl
0x1800ee06b  mov     [rbp+140h+var_194], ebx
0x1800ee06e  mov     [rbp+140h+var_190], bl
0x1800ee071  mov     [rbp+140h+var_188], rbx
0x1800ee075  mov     [rbp+140h+var_180], bl
0x1800ee078  mov     [rbp+140h+var_178], rbx
0x1800ee07c  mov     [rbp+140h+var_170], bl
0x1800ee07f  mov     [rbp+140h+var_168], rbx
0x1800ee083  mov     [rbp+140h+var_160], bl
0x1800ee086  mov     [rbp+140h+var_158], rbx
0x1800ee08a  mov     [rbp+140h+var_150], bx
0x1800ee08e  mov     [rbp+140h+var_14C], bl
0x1800ee091  mov     [rbp+140h+var_148], ebx
0x1800ee094  mov     [rbp+140h+var_144], bl
0x1800ee097  mov     [rbp+140h+var_140], ebx
0x1800ee09a  mov     [rbp+140h+var_13C], bl
0x1800ee09d  mov     [rbp+140h+var_138], ebx
0x1800ee0a0  mov     rax, [r15]
0x1800ee0a3  mov     byte ptr [rsp+240h+var_1F0], bl
0x1800ee0a7  mov     rbx, [rax+78h]
0x1800ee0ab  call    cs:__imp_WindowsDeleteString
0x1800ee0b2  nop     dword ptr [rax+rax+00h]
0x1800ee0b7  mov     rdx, [rbp+140h+var_1B0]
0x1800ee0bb  lea     rax, [rsp+240h+string]
0x1800ee0c0  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800ee0c5  lea     r9, [rsp+240h+var_1F0]
0x1800ee0ca  mov     rax, rbx
0x1800ee0cd  mov     [rsp+240h+string], 0
0x1800ee0d6  mov     r8d, r14d
0x1800ee0d9  mov     rcx, r15
0x1800ee0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee0e1  xor     ecx, ecx
0x1800ee0e3  mov     ebx, eax
0x1800ee0e5  test    eax, eax
0x1800ee0e7  js      loc_1800EE343
0x1800ee0ed  cmp     byte ptr [rsp+240h+var_1F0], cl
0x1800ee0f1  jz      loc_1800EE2F0
0x1800ee0f7  lea     rax, [rsp+240h+var_1F0+1]
0x1800ee0fc  mov     [rbp+140h+var_130], cl
0x1800ee0ff  mov     qword ptr [rsp+240h+var_208], rax
0x1800ee104  mov     r9, r13
0x1800ee107  lea     rax, [rsp+240h+var_1F0+2]
0x1800ee10c  mov     [rbp+140h+var_12C], ecx
0x1800ee10f  mov     [rsp+240h+var_210], rax
0x1800ee114  mov     r8, r12
0x1800ee117  mov     eax, [rbp+140h+arg_20]
0x1800ee11d  mov     rdx, r15
0x1800ee120  mov     dword ptr [rsp+240h+var_218], eax
0x1800ee124  lea     rax, [rsp+240h+string]
0x1800ee129  mov     [rbp+140h+var_128], cl
0x1800ee12c  mov     [rbp+140h+var_124], ecx
0x1800ee12f  mov     [rbp+140h+var_120], cl
0x1800ee132  mov     [rbp+140h+var_118], rcx
0x1800ee136  mov     [rbp+140h+var_110], cl
0x1800ee139  mov     [rbp+140h+var_108], rcx
0x1800ee13d  mov     [rbp+140h+var_100], cl
0x1800ee140  mov     [rbp+140h+var_F8], rcx
0x1800ee144  mov     [rbp+140h+var_F0], cl
0x1800ee147  mov     [rbp+140h+var_E8], rcx
0x1800ee14b  mov     [rbp+140h+var_E0], cx
0x1800ee14f  mov     [rbp+140h+var_DC], cl
0x1800ee152  mov     [rbp+140h+var_D8], ecx
0x1800ee155  mov     [rbp+140h+var_D4], cl
0x1800ee158  mov     [rbp+140h+var_D0], ecx
0x1800ee15b  mov     [rbp+140h+var_CC], cl
0x1800ee15e  mov     [rbp+140h+var_C8], ecx
0x1800ee161  mov     byte ptr [rsp+240h+var_1F0+2], cl
0x1800ee165  mov     byte ptr [rsp+240h+var_1F0+1], cl
0x1800ee169  lea     rcx, [rbp+140h+var_130]
0x1800ee16d  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800ee172  call    ?TryReadSupportedAndVisibleTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2W4ComRegistrationVisibility@@AEA_N5@Z; CPackagedComCatalog::TryReadSupportedAndVisibleTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &,ComRegistrationVisibility,bool &,bool &)
0x1800ee177  mov     ebx, eax
0x1800ee179  test    eax, eax
0x1800ee17b  js      loc_1800EE2CA
0x1800ee181  xor     ebx, ebx
0x1800ee183  cmp     byte ptr [rsp+240h+var_1F0+1], bl
0x1800ee187  jz      short loc_1800EE1EC
0x1800ee189  mov     rcx, [rsp+240h+string]; HSTRING
0x1800ee18e  lea     rdx, [rsp+240h+var_1D8]; struct CPackagedComCatalog::TypeLibVersion *
0x1800ee193  mov     [rsp+240h+var_1D8], rbx
0x1800ee198  mov     byte ptr [rsp+240h+var_1D0], bl
0x1800ee19c  call    ?ParseTypeLibVersionString@CPackagedComCatalog@@CAJPEAUHSTRING__@@PEAVTypeLibVersion@1@@Z; CPackagedComCatalog::ParseTypeLibVersionString(HSTRING__ *,CPackagedComCatalog::TypeLibVersion *)
0x1800ee1a1  test    eax, eax
0x1800ee1a3  js      short loc_1800EE202
0x1800ee1a5  mov     r8b, [rbp+140h+arg_30]
0x1800ee1ac  lea     rdx, [rbp+140h+var_1C0]
0x1800ee1b0  lea     rcx, [rsp+240h+var_1D8]
0x1800ee1b5  movsd   [rbp+140h+var_1C0], xmm6
0x1800ee1ba  mov     [rbp-78h], esi
0x1800ee1bd  call    ?IsGreaterThan@TypeLibVersion@CPackagedComCatalog@@QEAA_NV12@_N@Z; CPackagedComCatalog::TypeLibVersion::IsGreaterThan(CPackagedComCatalog::TypeLibVersion,bool)
0x1800ee1c2  test    al, al
0x1800ee1c4  jz      short loc_1800EE1EC
0x1800ee1c6  lea     rdx, [rsp+240h+string]
0x1800ee1cb  lea     rcx, [rsp+240h+var_1E0]
0x1800ee1d0  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800ee1d5  movsd   xmm6, [rsp+240h+var_1D8]
0x1800ee1db  lea     rdx, [rbp+140h+var_130]
0x1800ee1df  mov     esi, [rsp+240h+var_1D0]
0x1800ee1e3  lea     rcx, [rbp+140h+var_1A0]
0x1800ee1e7  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@AEBU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800ee1ec  lea     rcx, [rbp+140h+var_130]; this
0x1800ee1f0  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ee1f5  mov     rcx, [rsp+240h+string]
0x1800ee1fa  inc     r14d
0x1800ee1fd  jmp     loc_1800EE0A0
0x1800ee202  mov     eax, cs:dword_1801574B8
0x1800ee208  mov     esi, 8007000Dh
0x1800ee20d  test    eax, eax
0x1800ee20f  jnz     short loc_1800EE224
0x1800ee211  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800ee217  jz      short loc_1800EE28F
0x1800ee219  xor     ecx, ecx
0x1800ee21b  call    IsWppLevelEnabled
0x1800ee220  test    al, al
0x1800ee222  jz      short loc_1800EE28F
0x1800ee224  mov     rcx, [r12]; string
0x1800ee228  xor     edx, edx; length
0x1800ee22a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ee231  nop     dword ptr [rax+rax+00h]
0x1800ee236  mov     rdx, r13; struct _GUID *
0x1800ee239  lea     rcx, [rbp+140h+var_B0]; this
0x1800ee240  mov     rdi, rax
0x1800ee243  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800ee248  mov     rcx, [rsp+240h+string]; string
0x1800ee24d  xor     edx, edx; length
0x1800ee24f  mov     rbx, rax
0x1800ee252  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ee259  nop     dword ptr [rax+rax+00h]
0x1800ee25e  mov     [rsp+40h], esi
0x1800ee262  lea     rcx, aIncorrectlyFor; "Incorrectly-formatted typelib version n"...
0x1800ee269  mov     qword ptr [rsp+240h+var_208], rdi
0x1800ee26e  lea     rdx, aCpackagedcomca_9; "CPackagedComCatalog::TryReadHighestType"...
0x1800ee275  mov     [rsp+240h+var_210], rbx
0x1800ee27a  mov     r8d, 205Eh
0x1800ee280  mov     [rsp+240h+var_218], rax
0x1800ee285  mov     qword ptr [rsp+240h+var_220], rcx
0x1800ee28a  call    ??$ComTraceMessageT@PEBGPEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBG2PEAG2J@Z; ComTraceMessageT<ushort const *,ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort const *,ushort *,ushort const *,long)
0x1800ee28f  lea     rcx, [rbp+140h+var_130]; this
0x1800ee293  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ee298  lea     rcx, [rbp+140h+var_1A0]; this
0x1800ee29c  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ee2a1  mov     rcx, [rsp+240h+var_1E0]; string
0x1800ee2a6  call    cs:__imp_WindowsDeleteString
0x1800ee2ad  nop     dword ptr [rax+rax+00h]
0x1800ee2b2  mov     rcx, [rsp+240h+string]; string
0x1800ee2b7  call    cs:__imp_WindowsDeleteString
0x1800ee2be  nop     dword ptr [rax+rax+00h]
0x1800ee2c3  mov     eax, esi
0x1800ee2c5  jmp     loc_1800EE38B
0x1800ee2ca  mov     rcx, [rbp+148h]; this
0x1800ee2d1  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ee2d8  mov     r9d, ebx; char *
0x1800ee2db  mov     edx, 204Bh; void *
0x1800ee2e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee2e5  lea     rcx, [rbp+140h+var_130]; this
0x1800ee2e9  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ee2ee  jmp     short loc_1800EE35E
0x1800ee2f0  mov     rbx, [rsp+240h+var_1E0]
0x1800ee2f5  test    rbx, rbx
0x1800ee2f8  jz      short loc_1800EE316
0x1800ee2fa  mov     rcx, [rbp+140h+var_C0]
0x1800ee301  lea     rdx, [rbp+140h+var_1A0]
0x1800ee305  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@AEBU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties const &)
0x1800ee30a  test    rdi, rdi
0x1800ee30d  jz      short loc_1800EE316
0x1800ee30f  movsd   qword ptr [rdi], xmm6
0x1800ee313  mov     [rdi+8], esi
0x1800ee316  lea     rcx, [rbp+140h+var_1A0]; this
0x1800ee31a  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ee31f  mov     rcx, rbx; string
0x1800ee322  call    cs:__imp_WindowsDeleteString
0x1800ee329  nop     dword ptr [rax+rax+00h]
0x1800ee32e  mov     rcx, [rsp+240h+string]; string
0x1800ee333  call    cs:__imp_WindowsDeleteString
0x1800ee33a  nop     dword ptr [rax+rax+00h]
0x1800ee33f  xor     eax, eax
0x1800ee341  jmp     short loc_1800EE38B
0x1800ee343  mov     rcx, [rbp+148h]; this
0x1800ee34a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ee351  mov     r9d, ebx; char *
0x1800ee354  mov     edx, 2029h; void *
0x1800ee359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee35e  lea     rcx, [rbp+140h+var_1A0]; this
0x1800ee362  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800ee367  mov     rcx, [rsp+240h+var_1E0]; string
0x1800ee36c  call    cs:__imp_WindowsDeleteString
0x1800ee373  nop     dword ptr [rax+rax+00h]
0x1800ee378  mov     rcx, [rsp+240h+string]; string
0x1800ee37d  call    cs:__imp_WindowsDeleteString
0x1800ee384  nop     dword ptr [rax+rax+00h]
0x1800ee389  mov     eax, ebx
0x1800ee38b  mov     rcx, [rbp+140h+var_60]
0x1800ee392  xor     rcx, rsp; StackCookie
0x1800ee395  call    __security_check_cookie
0x1800ee39a  movaps  xmm6, [rsp+240h+var_58+8]
0x1800ee3a2  add     rsp, 208h
0x1800ee3a9  pop     r15
0x1800ee3ab  pop     r14
0x1800ee3ad  pop     r13
0x1800ee3af  pop     r12
0x1800ee3b1  pop     rdi
0x1800ee3b2  pop     rsi
0x1800ee3b3  pop     rbx
0x1800ee3b4  pop     rbp
0x1800ee3b5  retn
```
