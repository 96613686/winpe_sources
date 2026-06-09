# CPackagedComCatalog::GetClassInfoFromProgIdWorker(IPackagedComCatalogContext *,OpaqueString const &,bool,ushort const *,bool,_GUID const &,void * *)

- ea: `0x1800dc590`
- end: `0x1800dc8c3`
- name: `?GetClassInfoFromProgIdWorker@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NPEBG2AEBU_GUID@@PEAPEAX@Z`
- size: `819`
- prototype: `__int64 __fastcall(struct IPackagedComCatalogContext *, const struct OpaqueString *, bool, const unsigned __int16 *, bool, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800dc440`

## callees

- `0x18000f874`
- `0x180016160`
- `0x18002ba28`
- `0x180034540`
- `0x1800414d0`
- `0x18004c4e0`
- `0x18008d028`
- `0x1800a12c4`
- `0x1800b27e0`
- `0x1800d46e0`
- `0x1800dc590`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc660`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc73d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc7df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc83f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc660`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc73d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc7df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc83f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc6de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc6ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc78c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc6de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc6ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dc78c`

## string_xrefs

- `0x1800dc704`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc7a3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc872`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dc7aa`: `While resolving ProgId %S, found ProgId %S with CLSID=%ws`
- `0x1800dc6f8`: `CPackagedComCatalog::GetClassInfoFromProgIdWorker`
- `0x1800dc797`: `CPackagedComCatalog::GetClassInfoFromProgIdWorker`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetClassInfoFromProgIdWorker(
        struct IPackagedComCatalogContext *a1,
        const struct OpaqueString *a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        char a5,
        const struct _GUID *a6,
        void **a7)
{
  int v8; // r14d
  int v9; // eax
  int ClassInfoWorker; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  char v13; // si
  int v14; // edi
  HSTRING v15; // rbx
  void **v17; // [rsp+20h] [rbp-F0h]
  int v18; // [rsp+58h] [rbp-B8h]
  int v19; // [rsp+60h] [rbp-B0h]
  int v20; // [rsp+68h] [rbp-A8h]
  char v21[8]; // [rsp+90h] [rbp-80h] BYREF
  HSTRING v22; // [rsp+98h] [rbp-78h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-70h] BYREF
  const unsigned __int16 *v24; // [rsp+A8h] [rbp-68h] BYREF
  const struct _GUID *v25; // [rsp+B0h] [rbp-60h]
  _BYTE v26[4]; // [rsp+C0h] [rbp-50h] BYREF
  struct _GUID v27; // [rsp+C4h] [rbp-4Ch] BYREF
  char v28; // [rsp+D8h] [rbp-38h]
  HSTRING v29; // [rsp+E0h] [rbp-30h] BYREF
  __int16 v30; // [rsp+E8h] [rbp-28h]
  char v31; // [rsp+ECh] [rbp-24h]
  int v32; // [rsp+F0h] [rbp-20h]
  char v33; // [rsp+F4h] [rbp-1Ch]
  int v34; // [rsp+F8h] [rbp-18h]
  char v35; // [rsp+FCh] [rbp-14h]
  int v36; // [rsp+100h] [rbp-10h]
  struct _GUID v37; // [rsp+110h] [rbp+0h] BYREF
  _BYTE v38[80]; // [rsp+120h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+A8h]

  v8 = a3;
  v24 = a4;
  v25 = a6;
  *a7 = 0;
  OpaqueString::OpaqueString(&string, a2);
  v22 = 0;
  v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v22);
  ClassInfoWorker = v9;
  if ( v9 >= 0 )
  {
    v13 = a5;
    v14 = 2 * v8;
    v21[0] = a5;
    LODWORD(v24) = 2 * v8;
    v37 = 0;
    while ( 1 )
    {
      v26[0] = 0;
      v28 = 0;
      v29 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v15 = v22;
      v27 = 0;
      v30 = 0;
      WindowsDeleteString(string);
      string = 0;
      ClassInfoWorker = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(
                          (__int64)v26,
                          (__int64)&string,
                          (__int64)v21,
                          (__int64)&v24,
                          v17,
                          (__int64)a1,
                          (__int64)v15,
                          (__int64)&string,
                          v8,
                          v13,
                          v14,
                          v18,
                          v19,
                          v20);
      if ( ClassInfoWorker < 0 )
        break;
      if ( v26[0] )
      {
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        {
          CGuidStr::CGuidStr((CGuidStr *)v38, &v27);
          WindowsGetStringRawBuffer(v22, 0);
          ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(
            (__int64)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (__int64)"CPackagedComCatalog::GetClassInfoFromProgIdWorker",
            0x1DFAu);
        }
        v37 = v27;
        WindowsDeleteString(v29);
        ClassInfoWorker = CPackagedComCatalog::GetClassInfoWorker(
                            6,
                            0,
                            (__int64)a1,
                            (const struct OpaqueString *)&string,
                            v8,
                            &v37,
                            v21[0],
                            (__int64)v25,
                            a7,
                            (int)v24,
                            0,
                            0,
                            0,
                            0,
                            0);
        goto LABEL_22;
      }
      if ( !v28 )
      {
        WindowsDeleteString(v29);
LABEL_17:
        ClassInfoWorker = -2147221164;
        goto LABEL_22;
      }
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      {
        WindowsGetStringRawBuffer(v29, 0);
        WindowsGetStringRawBuffer(v22, 0);
        v17 = (void **)L"While resolving ProgId %S, found ProgId %S with CurrentVersion=%S";
        ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(
          (__int64)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (__int64)"CPackagedComCatalog::GetClassInfoFromProgIdWorker",
          0x1E03u);
      }
      OpaqueString::operator=(&v22, &v29);
      WindowsDeleteString(v29);
      v13 = v21[0];
      v14 = (int)v24;
    }
    WindowsDeleteString(v29);
    if ( ClassInfoWorker == -2147024894 )
      goto LABEL_17;
    if ( ClassInfoWorker == -2147024883 )
    {
      ClassInfoWorker = -2147221165;
      goto LABEL_22;
    }
    v11 = (unsigned int)ClassInfoWorker;
    v12 = 7704;
  }
  else
  {
    v11 = (unsigned int)v9;
    v12 = 7646;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)v11,
    (int)v17);
LABEL_22:
  WindowsDeleteString(v22);
  v22 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ClassInfoWorker;
}

```

## disassembly

```asm
0x1800dc590  mov     [rsp-8+arg_10], rbx
0x1800dc595  push    rbp
0x1800dc596  push    rsi
0x1800dc597  push    rdi
0x1800dc598  push    r12
0x1800dc59a  push    r13
0x1800dc59c  push    r14
0x1800dc59e  push    r15
0x1800dc5a0  lea     rbp, [rsp-70h]
0x1800dc5a5  sub     rsp, 180h
0x1800dc5ac  mov     rax, cs:__security_cookie
0x1800dc5b3  xor     rax, rsp
0x1800dc5b6  mov     [rbp+0A0h+var_40], rax
0x1800dc5ba  mov     rax, [rbp+0A0h+arg_28]
0x1800dc5c1  mov     r13, rcx
0x1800dc5c4  mov     r12, [rbp+0A0h+arg_30]
0x1800dc5cb  lea     rcx, [rbp+0A0h+string]; newString
0x1800dc5cf  mov     r15, r9
0x1800dc5d2  movzx   r14d, r8b
0x1800dc5d6  mov     [rbp+0A0h+var_108], r9
0x1800dc5da  mov     [rbp+0A0h+var_100], rax
0x1800dc5de  mov     qword ptr [r12], 0
0x1800dc5e6  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x1800dc5eb  lea     rdx, [rbp+0A0h+var_108]
0x1800dc5ef  mov     [rbp+0A0h+var_118], 0
0x1800dc5f7  lea     rcx, [rbp+0A0h+var_118]; string
0x1800dc5fb  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dc600  mov     ebx, eax
0x1800dc602  test    eax, eax
0x1800dc604  jns     short loc_1800DC613
0x1800dc606  mov     r9d, eax
0x1800dc609  mov     edx, 1DDEh
0x1800dc60e  jmp     loc_1800DC86B
0x1800dc613  mov     sil, [rbp+0A0h+arg_20]
0x1800dc61a  mov     edi, r14d
0x1800dc61d  add     edi, edi
0x1800dc61f  mov     [rbp+0A0h+var_120], sil
0x1800dc623  xorps   xmm0, xmm0
0x1800dc626  mov     dword ptr [rbp+0A0h+var_108], edi
0x1800dc629  xor     ebx, ebx
0x1800dc62b  movups  [rbp+0A0h+var_A0], xmm0
0x1800dc62f  mov     rcx, [rbp+0A0h+string]; string
0x1800dc633  xorps   xmm0, xmm0
0x1800dc636  xor     eax, eax
0x1800dc638  mov     [rbp+0A0h+var_F0], bl
0x1800dc63b  mov     [rbp+0A0h+var_D8], bl
0x1800dc63e  mov     [rbp+0A0h+var_D0], rbx
0x1800dc642  mov     [rbp+0A0h+var_C4], bl
0x1800dc645  mov     [rbp+0A0h+var_C0], ebx
0x1800dc648  mov     [rbp+0A0h+var_BC], bl
0x1800dc64b  mov     [rbp+0A0h+var_B8], ebx
0x1800dc64e  mov     [rbp+0A0h+var_B4], bl
0x1800dc651  mov     [rbp+0A0h+var_B0], ebx
0x1800dc654  mov     rbx, [rbp+0A0h+var_118]
0x1800dc658  movups  xmmword ptr [rbp+0A0h+var_EC.Data1], xmm0
0x1800dc65c  mov     [rbp+0A0h+var_C8], ax
0x1800dc660  call    cs:__imp_WindowsDeleteString
0x1800dc666  mov     dword ptr [rsp+1B0h+var_160], edi
0x1800dc66a  lea     rax, [rbp+0A0h+string]
0x1800dc66e  mov     byte ptr [rsp+1B0h+var_168], sil
0x1800dc673  lea     r9, [rbp+0A0h+var_108]
0x1800dc677  mov     byte ptr [rsp+1B0h+var_170], r14b
0x1800dc67c  lea     r8, [rbp+0A0h+var_120]
0x1800dc680  mov     [rsp+1B0h+var_178], rax
0x1800dc685  lea     rdx, [rbp+0A0h+string]
0x1800dc689  mov     [rsp+1B0h+var_180], rbx
0x1800dc68e  lea     rcx, [rbp+0A0h+var_F0]
0x1800dc692  mov     [rsp+1B0h+var_188], r13
0x1800dc697  mov     [rbp+0A0h+string], 0
0x1800dc69f  call    ??$DoPackageAwareLookup@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU3@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800dc6a4  mov     ebx, eax
0x1800dc6a6  test    eax, eax
0x1800dc6a8  js      loc_1800DC83B
0x1800dc6ae  xor     ebx, ebx
0x1800dc6b0  cmp     [rbp+0A0h+var_F0], bl
0x1800dc6b3  jnz     loc_1800DC75E
0x1800dc6b9  cmp     [rbp+0A0h+var_D8], bl
0x1800dc6bc  jz      loc_1800DC74F
0x1800dc6c2  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800dc6c8  jz      short loc_1800DC72C
0x1800dc6ca  lea     edi, [rbx+3]
0x1800dc6cd  mov     ecx, edi
0x1800dc6cf  call    IsWppLevelEnabled
0x1800dc6d4  test    al, al
0x1800dc6d6  jz      short loc_1800DC72C
0x1800dc6d8  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dc6dc  xor     edx, edx; length
0x1800dc6de  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc6e4  mov     rcx, [rbp+0A0h+var_118]; string
0x1800dc6e8  xor     edx, edx; length
0x1800dc6ea  mov     rbx, rax
0x1800dc6ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc6f3  mov     [rsp+1B0h+var_178], rbx
0x1800dc6f8  lea     rdx, aCpackagedcomca_2; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800dc6ff  mov     [rsp+1B0h+var_180], rax
0x1800dc704  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc70b  lea     rax, aWhileResolving; "While resolving ProgId %S, found ProgId"...
0x1800dc712  mov     [rsp+1B0h+var_188], r15
0x1800dc717  mov     r9d, edi
0x1800dc71a  mov     [rsp+1B0h+var_190], rax
0x1800dc71f  mov     r8d, 1E03h
0x1800dc725  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800dc72a  xor     ebx, ebx
0x1800dc72c  lea     rdx, [rbp+0A0h+var_D0]
0x1800dc730  lea     rcx, [rbp+0A0h+var_118]
0x1800dc734  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800dc739  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dc73d  call    cs:__imp_WindowsDeleteString
0x1800dc743  mov     sil, [rbp+0A0h+var_120]
0x1800dc747  mov     edi, dword ptr [rbp+0A0h+var_108]
0x1800dc74a  jmp     loc_1800DC62F
0x1800dc74f  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dc753  call    cs:__imp_WindowsDeleteString
0x1800dc759  jmp     loc_1800DC84D
0x1800dc75e  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800dc764  jz      short loc_1800DC7CB
0x1800dc766  mov     edi, 3
0x1800dc76b  mov     ecx, edi
0x1800dc76d  call    IsWppLevelEnabled
0x1800dc772  test    al, al
0x1800dc774  jz      short loc_1800DC7CB
0x1800dc776  lea     rdx, [rbp+0A0h+var_EC]; struct _GUID *
0x1800dc77a  lea     rcx, [rbp+0A0h+var_90]; this
0x1800dc77e  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800dc783  mov     rcx, [rbp+0A0h+var_118]; string
0x1800dc787  xor     edx, edx; length
0x1800dc789  mov     rbx, rax
0x1800dc78c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dc792  mov     [rsp+1B0h+var_178], rbx
0x1800dc797  lea     rdx, aCpackagedcomca_2; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800dc79e  mov     [rsp+1B0h+var_180], rax
0x1800dc7a3  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc7aa  lea     rax, aWhileResolving_0; "While resolving ProgId %S, found ProgId"...
0x1800dc7b1  mov     [rsp+1B0h+var_188], r15
0x1800dc7b6  mov     r9d, edi
0x1800dc7b9  mov     [rsp+1B0h+var_190], rax
0x1800dc7be  mov     r8d, 1DFAh
0x1800dc7c4  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800dc7c9  xor     ebx, ebx
0x1800dc7cb  mov     rax, qword ptr [rbp+0A0h+var_EC.Data1]
0x1800dc7cf  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dc7d3  mov     qword ptr [rbp+0A0h+var_A0], rax
0x1800dc7d7  mov     rax, qword ptr [rbp+0A0h+var_EC.Data4]
0x1800dc7db  mov     qword ptr [rbp+0A0h+var_A0+8], rax
0x1800dc7df  call    cs:__imp_WindowsDeleteString
0x1800dc7e5  mov     eax, dword ptr [rbp+0A0h+var_108]
0x1800dc7e8  lea     r9, [rbp+0A0h+string]
0x1800dc7ec  mov     [rsp+1B0h+var_140], rbx
0x1800dc7f1  xor     edx, edx
0x1800dc7f3  mov     [rsp+1B0h+var_148], ebx
0x1800dc7f7  mov     r8, r13
0x1800dc7fa  mov     [rsp+1B0h+var_150], rbx
0x1800dc7ff  mov     [rsp+1B0h+var_158], ebx
0x1800dc803  mov     [rsp+1B0h+var_160], rbx
0x1800dc808  lea     ecx, [rdx+6]
0x1800dc80b  mov     [rsp+1B0h+var_168], eax
0x1800dc80f  mov     rax, [rbp+0A0h+var_100]
0x1800dc813  mov     [rsp+1B0h+var_170], r12
0x1800dc818  mov     [rsp+1B0h+var_178], rax
0x1800dc81d  mov     al, [rbp+0A0h+var_120]
0x1800dc820  mov     byte ptr [rsp+1B0h+var_180], al
0x1800dc824  lea     rax, [rbp+0A0h+var_A0]
0x1800dc828  mov     [rsp+1B0h+var_188], rax
0x1800dc82d  mov     byte ptr [rsp+1B0h+var_190], r14b
0x1800dc832  call    ?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z; CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800dc837  mov     ebx, eax
0x1800dc839  jmp     short loc_1800DC87E
0x1800dc83b  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dc83f  call    cs:__imp_WindowsDeleteString
0x1800dc845  cmp     ebx, 80070002h
0x1800dc84b  jnz     short loc_1800DC854
0x1800dc84d  mov     ebx, 80040154h
0x1800dc852  jmp     short loc_1800DC87E
0x1800dc854  cmp     ebx, 8007000Dh
0x1800dc85a  jnz     short loc_1800DC863
0x1800dc85c  mov     ebx, 80040153h
0x1800dc861  jmp     short loc_1800DC87E
0x1800dc863  mov     r9d, ebx; char *
0x1800dc866  mov     edx, 1E18h; void *
0x1800dc86b  mov     rcx, [rbp+0A8h]; this
0x1800dc872  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dc879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dc87e  mov     rcx, [rbp+0A0h+var_118]; string
0x1800dc882  call    cs:__imp_WindowsDeleteString
0x1800dc888  mov     rcx, [rbp+0A0h+string]; string
0x1800dc88c  mov     [rbp+0A0h+var_118], 0
0x1800dc894  call    cs:__imp_WindowsDeleteString
0x1800dc89a  mov     eax, ebx
0x1800dc89c  mov     rcx, [rbp+0A0h+var_40]
0x1800dc8a0  xor     rcx, rsp; StackCookie
0x1800dc8a3  call    __security_check_cookie
0x1800dc8a8  mov     rbx, [rsp+1B0h+arg_10]
0x1800dc8b0  add     rsp, 180h
0x1800dc8b7  pop     r15
0x1800dc8b9  pop     r14
0x1800dc8bb  pop     r13
0x1800dc8bd  pop     r12
0x1800dc8bf  pop     rdi
0x1800dc8c0  pop     rsi
0x1800dc8c1  pop     rbp
0x1800dc8c2  retn
```
