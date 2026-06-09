# CPackagedComCatalog::GetClassInfoFromProgIdWorker(IPackagedComCatalogContext *,OpaqueString const &,bool,ushort const *,bool,_GUID const &,void * *)

- ea: `0x1800e33e0`
- end: `0x1800e3750`
- name: `?GetClassInfoFromProgIdWorker@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NPEBG2AEBU_GUID@@PEAPEAX@Z`
- size: `880`
- prototype: `__int64 __fastcall(struct IPackagedComCatalogContext *, const struct OpaqueString *, bool, const unsigned __int16 *, bool, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800e3280`

## callees

- `0x180012e10`
- `0x18001a374`
- `0x1800210f8`
- `0x180034260`
- `0x18004b0f0`
- `0x1800581c0`
- `0x1800941bc`
- `0x1800a6768`
- `0x1800b7ac0`
- `0x1800db0dc`
- `0x1800e33e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e34b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e359f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e35bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e36b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e371a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e34b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e359f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e35bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3653`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e36b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e371a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e35fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e35fa`

## string_xrefs

- `0x1800e3566`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e3617`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e36f2`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e361e`: `While resolving ProgId %S, found ProgId %S with CLSID=%ws`
- `0x1800e355a`: `CPackagedComCatalog::GetClassInfoFromProgIdWorker`
- `0x1800e360b`: `CPackagedComCatalog::GetClassInfoFromProgIdWorker`

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
  int v9; // r14d
  int v10; // eax
  int ClassInfoWorker; // ebx
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  char v14; // si
  int v15; // edi
  HSTRING v16; // rbx
  CGuidStr *v17; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // [rsp+20h] [rbp-F0h]
  int v21; // [rsp+58h] [rbp-B8h]
  int v22; // [rsp+60h] [rbp-B0h]
  int v23; // [rsp+68h] [rbp-A8h]
  char v24; // [rsp+90h] [rbp-80h] BYREF
  HSTRING v25; // [rsp+98h] [rbp-78h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-70h] BYREF
  const unsigned __int16 *v27; // [rsp+A8h] [rbp-68h] BYREF
  const struct _GUID *v28; // [rsp+B0h] [rbp-60h]
  char v29; // [rsp+C0h] [rbp-50h] BYREF
  struct _GUID v30; // [rsp+C4h] [rbp-4Ch] BYREF
  char v31; // [rsp+D8h] [rbp-38h]
  HSTRING v32; // [rsp+E0h] [rbp-30h] BYREF
  __int16 v33; // [rsp+E8h] [rbp-28h]
  char v34; // [rsp+ECh] [rbp-24h]
  int v35; // [rsp+F0h] [rbp-20h]
  char v36; // [rsp+F4h] [rbp-1Ch]
  int v37; // [rsp+F8h] [rbp-18h]
  char v38; // [rsp+FCh] [rbp-14h]
  int v39; // [rsp+100h] [rbp-10h]
  struct _GUID v40; // [rsp+110h] [rbp+0h] BYREF
  _BYTE v41[80]; // [rsp+120h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+A8h]

  v9 = a3;
  v27 = a4;
  v28 = a6;
  *a7 = 0;
  OpaqueString::OpaqueString(&string, a2);
  v25 = 0;
  v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v25);
  ClassInfoWorker = v10;
  if ( v10 >= 0 )
  {
    v14 = a5;
    v15 = 2 * v9;
    v24 = a5;
    LODWORD(v27) = 2 * v9;
    v40 = 0;
    while ( 1 )
    {
      v29 = 0;
      v31 = 0;
      v32 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v16 = v25;
      v30 = 0;
      v33 = 0;
      WindowsDeleteString(string);
      string = 0;
      ClassInfoWorker = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(
                          (unsigned int)&v29,
                          (unsigned int)&string,
                          (unsigned int)&v24,
                          (unsigned int)&v27,
                          v20,
                          (__int64)a1,
                          (__int64)v16,
                          (__int64)&string,
                          v9,
                          v14,
                          v15,
                          v21,
                          v22,
                          v23);
      if ( ClassInfoWorker < 0 )
        break;
      if ( v29 )
      {
        if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
        {
          v17 = CGuidStr::CGuidStr((CGuidStr *)v41, &v30);
          StringRawBuffer = WindowsGetStringRawBuffer(v25, 0);
          ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (unsigned int)"CPackagedComCatalog::GetClassInfoFromProgIdWorker",
            7674,
            3,
            (__int64)L"While resolving ProgId %S, found ProgId %S with CLSID=%ws",
            a4,
            StringRawBuffer,
            v17);
        }
        v40 = v30;
        WindowsDeleteString(v32);
        ClassInfoWorker = CPackagedComCatalog::GetClassInfoWorker(
                            6,
                            0,
                            (__int64)a1,
                            (const struct OpaqueString *)&string,
                            v9,
                            &v40,
                            v24,
                            (__int64)v28,
                            a7,
                            (int)v27,
                            0,
                            0,
                            0,
                            0,
                            0);
        goto LABEL_22;
      }
      if ( !v31 )
      {
        WindowsDeleteString(v32);
LABEL_17:
        ClassInfoWorker = -2147221164;
        goto LABEL_22;
      }
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      {
        WindowsGetStringRawBuffer(v32, 0);
        WindowsGetStringRawBuffer(v25, 0);
        ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (unsigned int)"CPackagedComCatalog::GetClassInfoFromProgIdWorker",
          7683,
          3,
          (__int64)L"While resolving ProgId %S, found ProgId %S with CurrentVersion=%S");
      }
      OpaqueString::operator=(&v25, &v32);
      WindowsDeleteString(v32);
      v14 = v24;
      v15 = (int)v27;
    }
    WindowsDeleteString(v32);
    if ( ClassInfoWorker == -2147024894 )
      goto LABEL_17;
    if ( ClassInfoWorker == -2147024883 )
    {
      ClassInfoWorker = -2147221165;
      goto LABEL_22;
    }
    v12 = (unsigned int)ClassInfoWorker;
    v13 = 7704;
  }
  else
  {
    v12 = (unsigned int)v10;
    v13 = 7646;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)v12,
    v20);
LABEL_22:
  WindowsDeleteString(v25);
  v25 = 0;
  WindowsDeleteString(string);
  return (unsigned int)ClassInfoWorker;
}

```

## disassembly

```asm
0x1800e33e0  mov     [rsp-8+arg_10], rbx
0x1800e33e5  push    rbp
0x1800e33e6  push    rsi
0x1800e33e7  push    rdi
0x1800e33e8  push    r12
0x1800e33ea  push    r13
0x1800e33ec  push    r14
0x1800e33ee  push    r15
0x1800e33f0  lea     rbp, [rsp-70h]
0x1800e33f5  sub     rsp, 180h
0x1800e33fc  mov     rax, cs:__security_cookie
0x1800e3403  xor     rax, rsp
0x1800e3406  mov     [rbp+0A0h+var_40], rax
0x1800e340a  mov     rax, [rbp+0A0h+arg_28]
0x1800e3411  mov     r13, rcx
0x1800e3414  mov     r12, [rbp+0A0h+arg_30]
0x1800e341b  lea     rcx, [rbp+0A0h+string]; newString
0x1800e341f  mov     r15, r9
0x1800e3422  movzx   r14d, r8b
0x1800e3426  mov     [rbp+0A0h+var_108], r9
0x1800e342a  mov     [rbp+0A0h+var_100], rax
0x1800e342e  mov     qword ptr [r12], 0
0x1800e3436  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x1800e343b  lea     rdx, [rbp+0A0h+var_108]
0x1800e343f  mov     [rbp+0A0h+var_118], 0
0x1800e3447  lea     rcx, [rbp+0A0h+var_118]; string
0x1800e344b  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e3450  mov     ebx, eax
0x1800e3452  test    eax, eax
0x1800e3454  jns     short loc_1800E3463
0x1800e3456  mov     r9d, eax
0x1800e3459  mov     edx, 1DDEh
0x1800e345e  jmp     loc_1800E36EB
0x1800e3463  mov     sil, [rbp+0A0h+arg_20]
0x1800e346a  mov     edi, r14d
0x1800e346d  add     edi, edi
0x1800e346f  mov     [rbp+0A0h+var_120], sil
0x1800e3473  xorps   xmm0, xmm0
0x1800e3476  mov     dword ptr [rbp+0A0h+var_108], edi
0x1800e3479  xor     ebx, ebx
0x1800e347b  movups  [rbp+0A0h+var_A0], xmm0
0x1800e347f  mov     rcx, [rbp+0A0h+string]; string
0x1800e3483  xorps   xmm0, xmm0
0x1800e3486  xor     eax, eax
0x1800e3488  mov     [rbp+0A0h+var_F0], bl
0x1800e348b  mov     [rbp+0A0h+var_D8], bl
0x1800e348e  mov     [rbp+0A0h+var_D0], rbx
0x1800e3492  mov     [rbp+0A0h+var_C4], bl
0x1800e3495  mov     [rbp+0A0h+var_C0], ebx
0x1800e3498  mov     [rbp+0A0h+var_BC], bl
0x1800e349b  mov     [rbp+0A0h+var_B8], ebx
0x1800e349e  mov     [rbp+0A0h+var_B4], bl
0x1800e34a1  mov     [rbp+0A0h+var_B0], ebx
0x1800e34a4  mov     rbx, [rbp+0A0h+var_118]
0x1800e34a8  movups  xmmword ptr [rbp+0A0h+var_EC.Data1], xmm0
0x1800e34ac  mov     [rbp+0A0h+var_C8], ax
0x1800e34b0  call    cs:__imp_WindowsDeleteString
0x1800e34b7  nop     dword ptr [rax+rax+00h]
0x1800e34bc  mov     dword ptr [rsp+1B0h+var_160], edi
0x1800e34c0  lea     rax, [rbp+0A0h+string]
0x1800e34c4  mov     byte ptr [rsp+1B0h+var_168], sil
0x1800e34c9  lea     r9, [rbp+0A0h+var_108]
0x1800e34cd  mov     byte ptr [rsp+1B0h+var_170], r14b
0x1800e34d2  lea     r8, [rbp+0A0h+var_120]
0x1800e34d6  mov     [rsp+1B0h+var_178], rax
0x1800e34db  lea     rdx, [rbp+0A0h+string]
0x1800e34df  mov     [rsp+1B0h+var_180], rbx
0x1800e34e4  lea     rcx, [rbp+0A0h+var_F0]
0x1800e34e8  mov     [rsp+1B0h+var_188], r13
0x1800e34ed  mov     [rbp+0A0h+string], 0
0x1800e34f5  call    ??$DoPackageAwareLookup@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU3@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800e34fa  mov     ebx, eax
0x1800e34fc  test    eax, eax
0x1800e34fe  js      loc_1800E36B5
0x1800e3504  xor     ebx, ebx
0x1800e3506  cmp     [rbp+0A0h+var_F0], bl
0x1800e3509  jnz     loc_1800E35CC
0x1800e350f  cmp     [rbp+0A0h+var_D8], bl
0x1800e3512  jz      loc_1800E35B7
0x1800e3518  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800e351e  jz      short loc_1800E358E
0x1800e3520  lea     edi, [rbx+3]
0x1800e3523  mov     ecx, edi
0x1800e3525  call    IsWppLevelEnabled
0x1800e352a  test    al, al
0x1800e352c  jz      short loc_1800E358E
0x1800e352e  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e3532  xor     edx, edx; length
0x1800e3534  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e353b  nop     dword ptr [rax+rax+00h]
0x1800e3540  mov     rcx, [rbp+0A0h+var_118]; string
0x1800e3544  xor     edx, edx; length
0x1800e3546  mov     rbx, rax
0x1800e3549  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3550  nop     dword ptr [rax+rax+00h]
0x1800e3555  mov     [rsp+1B0h+var_178], rbx
0x1800e355a  lea     rdx, aCpackagedcomca_2; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800e3561  mov     [rsp+1B0h+var_180], rax
0x1800e3566  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e356d  lea     rax, aWhileResolving; "While resolving ProgId %S, found ProgId"...
0x1800e3574  mov     [rsp+1B0h+var_188], r15
0x1800e3579  mov     r9d, edi
0x1800e357c  mov     [rsp+1B0h+var_190], rax
0x1800e3581  mov     r8d, 1E03h
0x1800e3587  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800e358c  xor     ebx, ebx
0x1800e358e  lea     rdx, [rbp+0A0h+var_D0]
0x1800e3592  lea     rcx, [rbp+0A0h+var_118]
0x1800e3596  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800e359b  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e359f  call    cs:__imp_WindowsDeleteString
0x1800e35a6  nop     dword ptr [rax+rax+00h]
0x1800e35ab  mov     sil, [rbp+0A0h+var_120]
0x1800e35af  mov     edi, dword ptr [rbp+0A0h+var_108]
0x1800e35b2  jmp     loc_1800E347F
0x1800e35b7  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e35bb  call    cs:__imp_WindowsDeleteString
0x1800e35c2  nop     dword ptr [rax+rax+00h]
0x1800e35c7  jmp     loc_1800E36CD
0x1800e35cc  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800e35d2  jz      short loc_1800E363F
0x1800e35d4  mov     edi, 3
0x1800e35d9  mov     ecx, edi
0x1800e35db  call    IsWppLevelEnabled
0x1800e35e0  test    al, al
0x1800e35e2  jz      short loc_1800E363F
0x1800e35e4  lea     rdx, [rbp+0A0h+var_EC]; struct _GUID *
0x1800e35e8  lea     rcx, [rbp+0A0h+var_90]; this
0x1800e35ec  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e35f1  mov     rcx, [rbp+0A0h+var_118]; string
0x1800e35f5  xor     edx, edx; length
0x1800e35f7  mov     rbx, rax
0x1800e35fa  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3601  nop     dword ptr [rax+rax+00h]
0x1800e3606  mov     [rsp+1B0h+var_178], rbx
0x1800e360b  lea     rdx, aCpackagedcomca_2; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800e3612  mov     [rsp+1B0h+var_180], rax
0x1800e3617  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e361e  lea     rax, aWhileResolving_0; "While resolving ProgId %S, found ProgId"...
0x1800e3625  mov     [rsp+1B0h+var_188], r15
0x1800e362a  mov     r9d, edi
0x1800e362d  mov     [rsp+1B0h+var_190], rax
0x1800e3632  mov     r8d, 1DFAh
0x1800e3638  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800e363d  xor     ebx, ebx
0x1800e363f  mov     rax, qword ptr [rbp+0A0h+var_EC.Data1]
0x1800e3643  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e3647  mov     qword ptr [rbp+0A0h+var_A0], rax
0x1800e364b  mov     rax, qword ptr [rbp+0A0h+var_EC.Data4]
0x1800e364f  mov     qword ptr [rbp+0A0h+var_A0+8], rax
0x1800e3653  call    cs:__imp_WindowsDeleteString
0x1800e365a  nop     dword ptr [rax+rax+00h]
0x1800e365f  mov     eax, dword ptr [rbp+0A0h+var_108]
0x1800e3662  lea     r9, [rbp+0A0h+string]
0x1800e3666  mov     [rsp+1B0h+var_140], rbx
0x1800e366b  xor     edx, edx
0x1800e366d  mov     [rsp+1B0h+var_148], ebx
0x1800e3671  mov     r8, r13
0x1800e3674  mov     [rsp+1B0h+var_150], rbx
0x1800e3679  mov     [rsp+1B0h+var_158], ebx
0x1800e367d  mov     [rsp+1B0h+var_160], rbx
0x1800e3682  lea     ecx, [rdx+6]
0x1800e3685  mov     [rsp+1B0h+var_168], eax
0x1800e3689  mov     rax, [rbp+0A0h+var_100]
0x1800e368d  mov     [rsp+1B0h+var_170], r12
0x1800e3692  mov     [rsp+1B0h+var_178], rax
0x1800e3697  mov     al, [rbp+0A0h+var_120]
0x1800e369a  mov     byte ptr [rsp+1B0h+var_180], al
0x1800e369e  lea     rax, [rbp+0A0h+var_A0]
0x1800e36a2  mov     [rsp+1B0h+var_188], rax
0x1800e36a7  mov     byte ptr [rsp+1B0h+var_190], r14b
0x1800e36ac  call    ?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z; CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800e36b1  mov     ebx, eax
0x1800e36b3  jmp     short loc_1800E36FE
0x1800e36b5  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e36b9  call    cs:__imp_WindowsDeleteString
0x1800e36c0  nop     dword ptr [rax+rax+00h]
0x1800e36c5  cmp     ebx, 80070002h
0x1800e36cb  jnz     short loc_1800E36D4
0x1800e36cd  mov     ebx, 80040154h
0x1800e36d2  jmp     short loc_1800E36FE
0x1800e36d4  cmp     ebx, 8007000Dh
0x1800e36da  jnz     short loc_1800E36E3
0x1800e36dc  mov     ebx, 80040153h
0x1800e36e1  jmp     short loc_1800E36FE
0x1800e36e3  mov     r9d, ebx; char *
0x1800e36e6  mov     edx, 1E18h; void *
0x1800e36eb  mov     rcx, [rbp+0A8h]; this
0x1800e36f2  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e36f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e36fe  mov     rcx, [rbp+0A0h+var_118]; string
0x1800e3702  call    cs:__imp_WindowsDeleteString
0x1800e3709  nop     dword ptr [rax+rax+00h]
0x1800e370e  mov     rcx, [rbp+0A0h+string]; string
0x1800e3712  mov     [rbp+0A0h+var_118], 0
0x1800e371a  call    cs:__imp_WindowsDeleteString
0x1800e3721  nop     dword ptr [rax+rax+00h]
0x1800e3726  mov     eax, ebx
0x1800e3728  mov     rcx, [rbp+0A0h+var_40]
0x1800e372c  xor     rcx, rsp; StackCookie
0x1800e372f  call    __security_check_cookie
0x1800e3734  mov     rbx, [rsp+1B0h+arg_10]
0x1800e373c  add     rsp, 180h
0x1800e3743  pop     r15
0x1800e3745  pop     r14
0x1800e3747  pop     r13
0x1800e3749  pop     r12
0x1800e374b  pop     rdi
0x1800e374c  pop     rsi
0x1800e374d  pop     rbp
0x1800e374e  retn
```
