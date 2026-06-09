# SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(ulong,wchar_t const *,_GUID,ulong,void const *,IUnknown *)

- ea: `0x140017f58`
- end: `0x1400182d1`
- name: `?Initialize@WUDeploymentSessionInfoWrapper@SessionDataUtil@@AEAAJKPEB_WU_GUID@@KPEBXPEAUIUnknown@@@Z`
- size: `889`
- prototype: `int(SessionDataUtil::WUDeploymentSessionInfoWrapper *__hidden this, unsigned int, const wchar_t *, struct _GUID *__struct_ptr, unsigned int, const void *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140017db0`

## callees

- `0x140002ac0`
- `0x14000ce5c`
- `0x14000d4cc`
- `0x140013a74`
- `0x1400178a0`
- `0x140017f58`
- `0x1400183a0`
- `0x1400186e8`
- `0x1400188c8`
- `0x14001aa60`
- `0x14001acf4`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018289`
- `RPCRT4!UuidToStringW` at `0x14001811f`
- `RPCRT4!UuidToStringW` at `0x14001811f`
- `RPCRT4!UuidFromStringW` at `0x14001818b`
- `RPCRT4!UuidFromStringW` at `0x14001818b`

## string_xrefs

- `0x1400180e0`: `SandboxPath`
- `0x140018163`: `InformationFactoryCLSID`

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
    SusFree(v12);
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
      SusFree(*v11);
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
      SusFree(v24);
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
0x140017f58  mov     [rsp-38h+arg_8], rbx
0x140017f5d  push    rbp
0x140017f5e  push    rsi
0x140017f5f  push    rdi
0x140017f60  push    r12
0x140017f62  push    r13
0x140017f64  push    r14
0x140017f66  push    r15
0x140017f68  mov     rbp, rsp
0x140017f6b  sub     rsp, 60h
0x140017f6f  movaps  [rsp+60h+var_10], xmm6
0x140017f74  mov     rax, cs:__security_cookie
0x140017f7b  xor     rax, rsp
0x140017f7e  mov     [rbp+var_20], rax
0x140017f82  mov     [rbp+Uuid], r9
0x140017f86  mov     r13, r8
0x140017f89  mov     r14, rcx
0x140017f8c  mov     r15, [rbp+arg_28]
0x140017f90  mov     r12, [rbp+arg_30]
0x140017f94  movaps  xmm6, xmmword ptr [r9]
0x140017f98  mov     dword ptr [rcx], 1
0x140017f9e  lea     rdi, [rcx+8]
0x140017fa2  mov     rcx, [rdi]; lpMem
0x140017fa5  test    rcx, rcx
0x140017fa8  jz      short loc_140017FB6
0x140017faa  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140017faf  mov     qword ptr [rdi], 0
0x140017fb6  mov     rdx, rdi
0x140017fb9  mov     rcx, r13
0x140017fbc  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x140017fc1  mov     ebx, eax
0x140017fc3  test    eax, eax
0x140017fc5  jns     short loc_140017FD1
0x140017fc7  mov     edx, 3F2h
0x140017fcc  mov     r9d, eax
0x140017fcf  jmp     short loc_140018023
0x140017fd1  movdqu  xmmword ptr [r14+10h], xmm6
0x140017fd7  test    r15, r15
0x140017fda  jz      short loc_140018052
0x140017fdc  lea     rsi, [r14+20h]
0x140017fe0  mov     rbx, [rsi]
0x140017fe3  test    rbx, rbx
0x140017fe6  jz      short loc_140018004
0x140017fe8  mov     rcx, rbx; this
0x140017feb  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x140017ff0  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140017ff5  mov     rcx, rbx; void *
0x140017ff8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017ffd  mov     qword ptr [rsi], 0
0x140018004  mov     r9, rsi; struct SessionDataUtil::WUOptionalSessionInfoWrapper **
0x140018007  xor     r8d, r8d; struct IUnknown *
0x14001800a  mov     rdx, r15; void *
0x14001800d  mov     ecx, [rbp+arg_20]; unsigned int
0x140018010  call    ?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)
0x140018015  mov     ebx, eax
0x140018017  mov     r9d, eax; char *
0x14001801a  test    eax, eax
0x14001801c  jns     short loc_140018052
0x14001801e  mov     edx, 3FBh; void *
0x140018023  mov     rcx, [rbp+38h]; this
0x140018027  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14001802e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018033  mov     rcx, [rbp+38h]; this
0x140018037  mov     r9d, ebx; char *
0x14001803a  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140018041  mov     edx, 40Ch; void *
0x140018046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001804b  mov     eax, ebx
0x14001804d  jmp     loc_1400182A8
0x140018052  test    r12, r12
0x140018055  jnz     short loc_14001805E
0x140018057  xor     eax, eax
0x140018059  jmp     loc_1400182A8
0x14001805e  mov     rax, [r12]
0x140018062  mov     [rbp+var_30], 0
0x14001806a  lea     r8, [rbp+var_30]
0x14001806e  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x140018075  mov     rcx, r12
0x140018078  mov     rax, [rax]
0x14001807b  call    _guard_dispatch_icall
0x140018080  mov     esi, eax
0x140018082  xor     r12d, r12d
0x140018085  test    eax, eax
0x140018087  jns     short loc_140018090
0x140018089  mov     edx, 411h
0x14001808e  jmp     short loc_1400180FB
0x140018090  xorps   xmm0, xmm0
0x140018093  movsd   [rbp+var_40], xmm0
0x140018098  lea     r9, [rbp+var_40]
0x14001809c  movsd   xmm2, cs:__real@3ff0000000000000
0x1400180a4  lea     rdx, aDeploymentsess_0; "DeploymentSessionInfoVersion"
0x1400180ab  mov     rcx, [rbp+var_30]; this
0x1400180af  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x1400180b4  mov     esi, eax
0x1400180b6  test    eax, eax
0x1400180b8  jns     short loc_1400180C1
0x1400180ba  mov     edx, 417h
0x1400180bf  jmp     short loc_1400180FB
0x1400180c1  cvttsd2si rax, [rbp+var_40]
0x1400180c7  mov     [r14], eax
0x1400180ca  mov     rcx, [rdi]; lpMem
0x1400180cd  test    rcx, rcx
0x1400180d0  jz      short loc_1400180DA
0x1400180d2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400180d7  mov     [rdi], r12
0x1400180da  mov     r9, rdi; wchar_t *
0x1400180dd  mov     r8, r13; wchar_t *
0x1400180e0  lea     rdx, aSandboxpath; "SandboxPath"
0x1400180e7  mov     rcx, [rbp+var_30]; this
0x1400180eb  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1400180f0  mov     esi, eax
0x1400180f2  test    eax, eax
0x1400180f4  jns     short loc_140018113
0x1400180f6  mov     edx, 41Eh; void *
0x1400180fb  mov     rcx, [rbp+38h]; this
0x1400180ff  mov     r9d, esi; char *
0x140018102  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140018109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001810e  jmp     loc_140018290
0x140018113  mov     [rbp+StringUuid], r12
0x140018117  lea     rdx, [rbp+StringUuid]; StringUuid
0x14001811b  mov     rcx, [rbp+Uuid]; Uuid
0x14001811f  call    cs:__imp_UuidToStringW
0x140018125  mov     esi, eax
0x140018127  mov     ebx, 80010000h
0x14001812c  cmp     eax, 1
0x14001812f  jl      short loc_140018136
0x140018131  movzx   esi, ax
0x140018134  or      esi, ebx
0x140018136  test    esi, esi
0x140018138  jns     short loc_140018157
0x14001813a  mov     rcx, [rbp+38h]; this
0x14001813e  mov     r9d, esi; char *
0x140018141  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140018148  mov     edx, 423h; void *
0x14001814d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018152  jmp     loc_140018280
0x140018157  mov     [rbp+var_40], r12
0x14001815b  lea     r9, [rbp+var_40]; wchar_t *
0x14001815f  mov     r8, [rbp+StringUuid]; wchar_t *
0x140018163  lea     rdx, aInformationfac; "InformationFactoryCLSID"
0x14001816a  mov     rcx, [rbp+var_30]; this
0x14001816e  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x140018173  mov     esi, eax
0x140018175  mov     rdi, [rbp+var_40]
0x140018179  test    eax, eax
0x14001817b  jns     short loc_140018184
0x14001817d  mov     edx, 429h
0x140018182  jmp     short loc_1400181A6
0x140018184  lea     rdx, [r14+10h]; Uuid
0x140018188  mov     rcx, rdi; StringUuid
0x14001818b  call    cs:__imp_UuidFromStringW
0x140018191  mov     esi, eax
0x140018193  cmp     eax, 1
0x140018196  jl      short loc_14001819D
0x140018198  movzx   esi, ax
0x14001819b  or      esi, ebx
0x14001819d  test    esi, esi
0x14001819f  jns     short loc_1400181BE
0x1400181a1  mov     edx, 42Dh; void *
0x1400181a6  mov     rcx, [rbp+38h]; this
0x1400181aa  mov     r9d, esi; char *
0x1400181ad  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400181b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400181b9  jmp     loc_140018272
0x1400181be  test    r15, r15
0x1400181c1  jz      loc_14001826F
0x1400181c7  mov     [rbp+Uuid], r12
0x1400181cb  lea     r8, [rbp+Uuid]; wchar_t *
0x1400181cf  lea     rdx, aOptionalsessio; "OptionalSessionInfo"
0x1400181d6  mov     rcx, [rbp+var_30]; this
0x1400181da  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x1400181df  mov     esi, eax
0x1400181e1  mov     rbx, [rbp+Uuid]
0x1400181e5  test    eax, eax
0x1400181e7  jns     short loc_1400181F0
0x1400181e9  mov     edx, 435h
0x1400181ee  jmp     short loc_14001822F
0x1400181f0  mov     rsi, [r14+20h]
0x1400181f4  test    rsi, rsi
0x1400181f7  jz      short loc_140018212
0x1400181f9  mov     rcx, rsi; this
0x1400181fc  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x140018201  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140018206  mov     rcx, rsi; void *
0x140018209  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001820e  mov     [r14+20h], r12
0x140018212  lea     r9, [r14+20h]; struct SessionDataUtil::WUOptionalSessionInfoWrapper **
0x140018216  mov     r8, rbx; struct IUnknown *
0x140018219  mov     rdx, r15; void *
0x14001821c  mov     ecx, [rbp+arg_20]; unsigned int
0x14001821f  call    ?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)
0x140018224  mov     esi, eax
0x140018226  test    eax, eax
0x140018228  jns     short loc_14001825A
0x14001822a  mov     edx, 43Bh; void *
0x14001822f  mov     r9d, eax; char *
0x140018232  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140018239  mov     rcx, [rbp+38h]; this
0x14001823d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018242  nop
0x140018243  test    rbx, rbx
0x140018246  jz      short loc_140018258
0x140018248  mov     rax, [rbx]
0x14001824b  mov     rcx, rbx
0x14001824e  mov     rax, [rax+10h]
0x140018252  call    _guard_dispatch_icall
0x140018257  nop
0x140018258  jmp     short loc_140018272
0x14001825a  test    rbx, rbx
0x14001825d  jz      short loc_14001826F
0x14001825f  mov     rax, [rbx]
0x140018262  mov     rcx, rbx
0x140018265  mov     rax, [rax+10h]
0x140018269  call    _guard_dispatch_icall
0x14001826e  nop
0x14001826f  mov     esi, r12d
0x140018272  test    rdi, rdi
0x140018275  jz      short loc_140018280
0x140018277  mov     rcx, rdi; lpMem
0x14001827a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001827f  nop
0x140018280  mov     rcx, [rbp+StringUuid]; pv
0x140018284  test    rcx, rcx
0x140018287  jz      short loc_140018290
0x140018289  call    cs:__imp_CoTaskMemFree
0x14001828f  nop
0x140018290  mov     rcx, [rbp+var_30]
0x140018294  test    rcx, rcx
0x140018297  jz      short loc_1400182A6
0x140018299  mov     rdx, [rcx]
0x14001829c  mov     rax, [rdx+10h]
0x1400182a0  call    _guard_dispatch_icall
0x1400182a5  nop
0x1400182a6  mov     eax, esi
0x1400182a8  mov     rcx, [rbp+var_20]
0x1400182ac  xor     rcx, rsp; StackCookie
0x1400182af  call    __security_check_cookie
0x1400182b4  mov     rbx, [rsp+60h+arg_8]
0x1400182bc  movaps  xmm6, [rsp+60h+var_10]
0x1400182c1  add     rsp, 60h
0x1400182c5  pop     r15
0x1400182c7  pop     r14
0x1400182c9  pop     r13
0x1400182cb  pop     r12
0x1400182cd  pop     rdi
0x1400182ce  pop     rsi
0x1400182cf  pop     rbp
0x1400182d0  retn
```
