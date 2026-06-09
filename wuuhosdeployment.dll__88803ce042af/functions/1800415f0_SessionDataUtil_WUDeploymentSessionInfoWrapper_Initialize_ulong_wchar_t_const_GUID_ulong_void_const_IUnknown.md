# SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(ulong,wchar_t const *,_GUID,ulong,void const *,IUnknown *)

- ea: `0x1800415f0`
- end: `0x180041969`
- name: `?Initialize@WUDeploymentSessionInfoWrapper@SessionDataUtil@@AEAAJKPEB_WU_GUID@@KPEBXPEAUIUnknown@@@Z`
- size: `889`
- prototype: `int(SessionDataUtil::WUDeploymentSessionInfoWrapper *__hidden this, unsigned int, const wchar_t *, struct _GUID *__struct_ptr, unsigned int, const void *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041448`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000b334`
- `0x18003d494`
- `0x180040f38`
- `0x1800415f0`
- `0x180041970`
- `0x180041cb8`
- `0x180041e98`
- `0x180042630`
- `0x180042a24`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041921`
- `RPCRT4!UuidFromStringW` at `0x180041823`
- `RPCRT4!UuidFromStringW` at `0x180041823`
- `RPCRT4!UuidToStringW` at `0x1800417b7`
- `RPCRT4!UuidToStringW` at `0x1800417b7`

## string_xrefs

- `0x1800417fb`: `InformationFactoryCLSID`
- `0x180041778`: `SandboxPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(
        SessionDataUtil::WUDeploymentSessionInfoWrapper *this,
        __int64 a2,
        const wchar_t *a3,
        struct _GUID *a4,
        unsigned int a5,
        void *a6,
        struct IUnknown *a7)
{
  double v7; // xmm3_8
  UUID v10; // xmm6
  void **v11; // rdi
  void *v12; // rcx
  int v13; // eax
  const char *v14; // r9
  unsigned int Instance; // ebx
  __int64 v16; // rdx
  void *v17; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  int NumberPropertyWithDefault; // esi
  const wchar_t *v21; // r8
  __int64 v22; // rdx
  RPC_STATUS v23; // eax
  RPC_WSTR v24; // rdi
  __int64 v25; // rdx
  RPC_STATUS v26; // eax
  struct ABI::Windows::Data::Json::IJsonObject **v27; // r9
  int NamedObject; // eax
  struct IUnknown *v29; // rbx
  __int64 v30; // rdx
  void *v31; // rsi
  RPC_WSTR v32; // [rsp+20h] [rbp-40h] BYREF
  UUID *Uuid; // [rsp+28h] [rbp-38h] BYREF
  JsonUtil *v34; // [rsp+30h] [rbp-30h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  Uuid = a4;
  v10 = *a4;
  *(_DWORD *)this = 1;
  v11 = (void **)((char *)this + 8);
  v12 = (void *)*((_QWORD *)this + 1);
  if ( v12 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v12);
    *v11 = 0;
  }
  v13 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a3, v11);
  Instance = v13;
  if ( v13 < 0 )
  {
    v16 = 1010;
    v14 = (const char *)(unsigned int)v13;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      v14,
      (int)v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)Instance,
      (int)v32);
    return Instance;
  }
  *((UUID *)this + 1) = v10;
  if ( a6 )
  {
    v17 = (void *)*((_QWORD *)this + 4);
    if ( v17 )
    {
      SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(*((SessionDataUtil::WUOptionalSessionInfoWrapper **)this
                                                                                   + 4));
      operator delete(v17, (const struct std::nothrow_t *)0x38);
      *((_QWORD *)this + 4) = 0;
    }
    Instance = SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(
                 a5,
                 a6,
                 0,
                 (struct SessionDataUtil::WUOptionalSessionInfoWrapper **)this + 4);
    v14 = (const char *)Instance;
    if ( (Instance & 0x80000000) != 0 )
    {
      v16 = 1019;
      goto LABEL_10;
    }
  }
  if ( !a7 )
    return 0;
  lpVtbl = a7->lpVtbl;
  v34 = 0;
  NumberPropertyWithDefault = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, JsonUtil **, const char *))lpVtbl->QueryInterface)(
                                a7,
                                &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                                &v34,
                                v14);
  if ( NumberPropertyWithDefault >= 0 )
  {
    NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(
                                  v34,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"DeploymentSessionInfoVersion",
                                  v21,
                                  v7,
                                  0);
    if ( NumberPropertyWithDefault < 0 )
    {
      v22 = 1047;
      goto LABEL_21;
    }
    *(_DWORD *)this = (int)*(double *)&v32;
    if ( *v11 )
    {
      CSusBaseAllocTag<942762101>::operator delete(*v11);
      *v11 = 0;
    }
    NumberPropertyWithDefault = JsonUtil::GetStringPropertyWithDefault(
                                  v34,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"SandboxPath",
                                  a3,
                                  (wchar_t *)v11);
    if ( NumberPropertyWithDefault < 0 )
    {
      v22 = 1054;
      goto LABEL_21;
    }
    StringUuid = 0;
    v23 = UuidToStringW(Uuid, &StringUuid);
    NumberPropertyWithDefault = v23;
    if ( v23 >= 1 )
      NumberPropertyWithDefault = (unsigned __int16)v23 | 0x80010000;
    if ( NumberPropertyWithDefault < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x423,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NumberPropertyWithDefault,
        (int)v32);
LABEL_48:
      if ( StringUuid )
        CoTaskMemFree(StringUuid);
      goto LABEL_50;
    }
    *(double *)&v32 = 0.0;
    NumberPropertyWithDefault = JsonUtil::GetStringPropertyWithDefault(
                                  v34,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"InformationFactoryCLSID",
                                  StringUuid,
                                  (wchar_t *)&v32);
    v24 = v32;
    if ( NumberPropertyWithDefault < 0 )
    {
      v25 = 1065;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NumberPropertyWithDefault,
        (int)v32);
      goto LABEL_46;
    }
    v26 = UuidFromStringW(v32, (UUID *)this + 1);
    NumberPropertyWithDefault = v26;
    if ( v26 >= 1 )
      NumberPropertyWithDefault = (unsigned __int16)v26 | 0x80010000;
    if ( NumberPropertyWithDefault < 0 )
    {
      v25 = 1069;
      goto LABEL_32;
    }
    if ( a6 )
    {
      Uuid = 0;
      NamedObject = JsonUtil::GetNamedObject(
                      v34,
                      (struct ABI::Windows::Data::Json::IJsonObject *)L"OptionalSessionInfo",
                      (const wchar_t *)&Uuid,
                      v27);
      NumberPropertyWithDefault = NamedObject;
      v29 = (struct IUnknown *)Uuid;
      if ( NamedObject < 0 )
      {
        v30 = 1077;
        goto LABEL_40;
      }
      v31 = (void *)*((_QWORD *)this + 4);
      if ( v31 )
      {
        SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(*((SessionDataUtil::WUOptionalSessionInfoWrapper **)this
                                                                                     + 4));
        operator delete(v31, (const struct std::nothrow_t *)0x38);
        *((_QWORD *)this + 4) = 0;
      }
      NamedObject = SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(
                      a5,
                      a6,
                      v29,
                      (struct SessionDataUtil::WUOptionalSessionInfoWrapper **)this + 4);
      NumberPropertyWithDefault = NamedObject;
      if ( NamedObject < 0 )
      {
        v30 = 1083;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)NamedObject,
          (int)v32);
        if ( v29 )
          ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
        goto LABEL_46;
      }
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
    }
    NumberPropertyWithDefault = 0;
LABEL_46:
    if ( v24 )
      CSusBaseAllocTag<942762101>::operator delete(v24);
    goto LABEL_48;
  }
  v22 = 1041;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)NumberPropertyWithDefault,
    (int)v32);
LABEL_50:
  if ( v34 )
    (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v34 + 16LL))(v34);
  return (unsigned int)NumberPropertyWithDefault;
}

```

## disassembly

```asm
0x1800415f0  mov     [rsp-38h+arg_8], rbx
0x1800415f5  push    rbp
0x1800415f6  push    rsi
0x1800415f7  push    rdi
0x1800415f8  push    r12
0x1800415fa  push    r13
0x1800415fc  push    r14
0x1800415fe  push    r15
0x180041600  mov     rbp, rsp
0x180041603  sub     rsp, 60h
0x180041607  movaps  [rsp+60h+var_10], xmm6
0x18004160c  mov     rax, cs:__security_cookie
0x180041613  xor     rax, rsp
0x180041616  mov     [rbp+var_20], rax
0x18004161a  mov     [rbp+Uuid], r9
0x18004161e  mov     r13, r8
0x180041621  mov     r14, rcx
0x180041624  mov     r15, [rbp+arg_28]
0x180041628  mov     r12, [rbp+arg_30]
0x18004162c  movaps  xmm6, xmmword ptr [r9]
0x180041630  mov     dword ptr [rcx], 1
0x180041636  lea     rdi, [rcx+8]
0x18004163a  mov     rcx, [rdi]; lpMem
0x18004163d  test    rcx, rcx
0x180041640  jz      short loc_18004164E
0x180041642  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180041647  mov     qword ptr [rdi], 0
0x18004164e  mov     rdx, rdi
0x180041651  mov     rcx, r13
0x180041654  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180041659  mov     ebx, eax
0x18004165b  test    eax, eax
0x18004165d  jns     short loc_180041669
0x18004165f  mov     edx, 3F2h
0x180041664  mov     r9d, eax
0x180041667  jmp     short loc_1800416BB
0x180041669  movdqu  xmmword ptr [r14+10h], xmm6
0x18004166f  test    r15, r15
0x180041672  jz      short loc_1800416EA
0x180041674  lea     rsi, [r14+20h]
0x180041678  mov     rbx, [rsi]
0x18004167b  test    rbx, rbx
0x18004167e  jz      short loc_18004169C
0x180041680  mov     rcx, rbx; this
0x180041683  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x180041688  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18004168d  mov     rcx, rbx; void *
0x180041690  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180041695  mov     qword ptr [rsi], 0
0x18004169c  mov     r9, rsi; struct SessionDataUtil::WUOptionalSessionInfoWrapper **
0x18004169f  xor     r8d, r8d; struct IUnknown *
0x1800416a2  mov     rdx, r15; void *
0x1800416a5  mov     ecx, [rbp+arg_20]; unsigned int
0x1800416a8  call    ?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)
0x1800416ad  mov     ebx, eax
0x1800416af  mov     r9d, eax; char *
0x1800416b2  test    eax, eax
0x1800416b4  jns     short loc_1800416EA
0x1800416b6  mov     edx, 3FBh; void *
0x1800416bb  mov     rcx, [rbp+38h]; this
0x1800416bf  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800416c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416cb  mov     rcx, [rbp+38h]; this
0x1800416cf  mov     r9d, ebx; char *
0x1800416d2  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800416d9  mov     edx, 40Ch; void *
0x1800416de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416e3  mov     eax, ebx
0x1800416e5  jmp     loc_180041940
0x1800416ea  test    r12, r12
0x1800416ed  jnz     short loc_1800416F6
0x1800416ef  xor     eax, eax
0x1800416f1  jmp     loc_180041940
0x1800416f6  mov     rax, [r12]
0x1800416fa  mov     [rbp+var_30], 0
0x180041702  lea     r8, [rbp+var_30]
0x180041706  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18004170d  mov     rcx, r12
0x180041710  mov     rax, [rax]
0x180041713  call    _guard_dispatch_icall
0x180041718  mov     esi, eax
0x18004171a  xor     r12d, r12d
0x18004171d  test    eax, eax
0x18004171f  jns     short loc_180041728
0x180041721  mov     edx, 411h
0x180041726  jmp     short loc_180041793
0x180041728  xorps   xmm0, xmm0
0x18004172b  movsd   [rbp+var_40], xmm0
0x180041730  lea     r9, [rbp+var_40]
0x180041734  movsd   xmm2, cs:__real@3ff0000000000000
0x18004173c  lea     rdx, aDeploymentsess_0; "DeploymentSessionInfoVersion"
0x180041743  mov     rcx, [rbp+var_30]; this
0x180041747  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x18004174c  mov     esi, eax
0x18004174e  test    eax, eax
0x180041750  jns     short loc_180041759
0x180041752  mov     edx, 417h
0x180041757  jmp     short loc_180041793
0x180041759  cvttsd2si rax, [rbp+var_40]
0x18004175f  mov     [r14], eax
0x180041762  mov     rcx, [rdi]; lpMem
0x180041765  test    rcx, rcx
0x180041768  jz      short loc_180041772
0x18004176a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18004176f  mov     [rdi], r12
0x180041772  mov     r9, rdi; wchar_t *
0x180041775  mov     r8, r13; wchar_t *
0x180041778  lea     rdx, aSandboxpath; "SandboxPath"
0x18004177f  mov     rcx, [rbp+var_30]; this
0x180041783  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180041788  mov     esi, eax
0x18004178a  test    eax, eax
0x18004178c  jns     short loc_1800417AB
0x18004178e  mov     edx, 41Eh; void *
0x180041793  mov     rcx, [rbp+38h]; this
0x180041797  mov     r9d, esi; char *
0x18004179a  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800417a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417a6  jmp     loc_180041928
0x1800417ab  mov     [rbp+StringUuid], r12
0x1800417af  lea     rdx, [rbp+StringUuid]; StringUuid
0x1800417b3  mov     rcx, [rbp+Uuid]; Uuid
0x1800417b7  call    cs:__imp_UuidToStringW
0x1800417bd  mov     esi, eax
0x1800417bf  mov     ebx, 80010000h
0x1800417c4  cmp     eax, 1
0x1800417c7  jl      short loc_1800417CE
0x1800417c9  movzx   esi, ax
0x1800417cc  or      esi, ebx
0x1800417ce  test    esi, esi
0x1800417d0  jns     short loc_1800417EF
0x1800417d2  mov     rcx, [rbp+38h]; this
0x1800417d6  mov     r9d, esi; char *
0x1800417d9  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800417e0  mov     edx, 423h; void *
0x1800417e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800417ea  jmp     loc_180041918
0x1800417ef  mov     [rbp+var_40], r12
0x1800417f3  lea     r9, [rbp+var_40]; wchar_t *
0x1800417f7  mov     r8, [rbp+StringUuid]; wchar_t *
0x1800417fb  lea     rdx, aInformationfac; "InformationFactoryCLSID"
0x180041802  mov     rcx, [rbp+var_30]; this
0x180041806  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18004180b  mov     esi, eax
0x18004180d  mov     rdi, [rbp+var_40]
0x180041811  test    eax, eax
0x180041813  jns     short loc_18004181C
0x180041815  mov     edx, 429h
0x18004181a  jmp     short loc_18004183E
0x18004181c  lea     rdx, [r14+10h]; Uuid
0x180041820  mov     rcx, rdi; StringUuid
0x180041823  call    cs:__imp_UuidFromStringW
0x180041829  mov     esi, eax
0x18004182b  cmp     eax, 1
0x18004182e  jl      short loc_180041835
0x180041830  movzx   esi, ax
0x180041833  or      esi, ebx
0x180041835  test    esi, esi
0x180041837  jns     short loc_180041856
0x180041839  mov     edx, 42Dh; void *
0x18004183e  mov     rcx, [rbp+38h]; this
0x180041842  mov     r9d, esi; char *
0x180041845  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004184c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041851  jmp     loc_18004190A
0x180041856  test    r15, r15
0x180041859  jz      loc_180041907
0x18004185f  mov     [rbp+Uuid], r12
0x180041863  lea     r8, [rbp+Uuid]; wchar_t *
0x180041867  lea     rdx, aOptionalsessio_1; "OptionalSessionInfo"
0x18004186e  mov     rcx, [rbp+var_30]; this
0x180041872  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x180041877  mov     esi, eax
0x180041879  mov     rbx, [rbp+Uuid]
0x18004187d  test    eax, eax
0x18004187f  jns     short loc_180041888
0x180041881  mov     edx, 435h
0x180041886  jmp     short loc_1800418C7
0x180041888  mov     rsi, [r14+20h]
0x18004188c  test    rsi, rsi
0x18004188f  jz      short loc_1800418AA
0x180041891  mov     rcx, rsi; this
0x180041894  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x180041899  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18004189e  mov     rcx, rsi; void *
0x1800418a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800418a6  mov     [r14+20h], r12
0x1800418aa  lea     r9, [r14+20h]; struct SessionDataUtil::WUOptionalSessionInfoWrapper **
0x1800418ae  mov     r8, rbx; struct IUnknown *
0x1800418b1  mov     rdx, r15; void *
0x1800418b4  mov     ecx, [rbp+arg_20]; unsigned int
0x1800418b7  call    ?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)
0x1800418bc  mov     esi, eax
0x1800418be  test    eax, eax
0x1800418c0  jns     short loc_1800418F2
0x1800418c2  mov     edx, 43Bh; void *
0x1800418c7  mov     r9d, eax; char *
0x1800418ca  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800418d1  mov     rcx, [rbp+38h]; this
0x1800418d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800418da  nop
0x1800418db  test    rbx, rbx
0x1800418de  jz      short loc_1800418F0
0x1800418e0  mov     rax, [rbx]
0x1800418e3  mov     rcx, rbx
0x1800418e6  mov     rax, [rax+10h]
0x1800418ea  call    _guard_dispatch_icall
0x1800418ef  nop
0x1800418f0  jmp     short loc_18004190A
0x1800418f2  test    rbx, rbx
0x1800418f5  jz      short loc_180041907
0x1800418f7  mov     rax, [rbx]
0x1800418fa  mov     rcx, rbx
0x1800418fd  mov     rax, [rax+10h]
0x180041901  call    _guard_dispatch_icall
0x180041906  nop
0x180041907  mov     esi, r12d
0x18004190a  test    rdi, rdi
0x18004190d  jz      short loc_180041918
0x18004190f  mov     rcx, rdi; lpMem
0x180041912  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180041917  nop
0x180041918  mov     rcx, [rbp+StringUuid]; pv
0x18004191c  test    rcx, rcx
0x18004191f  jz      short loc_180041928
0x180041921  call    cs:__imp_CoTaskMemFree
0x180041927  nop
0x180041928  mov     rcx, [rbp+var_30]
0x18004192c  test    rcx, rcx
0x18004192f  jz      short loc_18004193E
0x180041931  mov     rdx, [rcx]
0x180041934  mov     rax, [rdx+10h]
0x180041938  call    _guard_dispatch_icall
0x18004193d  nop
0x18004193e  mov     eax, esi
0x180041940  mov     rcx, [rbp+var_20]
0x180041944  xor     rcx, rsp; StackCookie
0x180041947  call    __security_check_cookie
0x18004194c  mov     rbx, [rsp+60h+arg_8]
0x180041954  movaps  xmm6, [rsp+60h+var_10]
0x180041959  add     rsp, 60h
0x18004195d  pop     r15
0x18004195f  pop     r14
0x180041961  pop     r13
0x180041963  pop     r12
0x180041965  pop     rdi
0x180041966  pop     rsi
0x180041967  pop     rbp
0x180041968  retn
```
