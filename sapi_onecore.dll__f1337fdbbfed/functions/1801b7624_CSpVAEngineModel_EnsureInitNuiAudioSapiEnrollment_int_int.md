# CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment(int,int)

- ea: `0x1801b7624`
- end: `0x1801b7b3f`
- name: `?EnsureInitNuiAudioSapiEnrollment@CSpVAEngineModel@@AEAAJHH@Z`
- size: `1307`
- prototype: `__int64 __fastcall(CSpVAEngineModel *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b8050`

## callees

- `0x18000a590`
- `0x18000bec4`
- `0x180013ec0`
- `0x180068040`
- `0x18007d31c`
- `0x1800e4950`
- `0x1801b7624`
- `0x1801b7b9c`
- `0x1801b7f94`
- `0x1801b7ff0`
- `0x1801b80ec`
- `0x1801e204c`
- `0x1801e3308`
- `0x1801e343c`
- `0x1801e354c`
- `0x1801e3c88`
- `0x1801e3d24`
- `0x1801e3e14`
- `0x1801e4350`
- `0x1801e44f8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b766a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b766a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b7b1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b7b1c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b7729`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b7729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7ad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b7adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b76e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b76e7`

## string_xrefs

- `0x1801b79a2`: `Voice Activation User Model Update - Update Failed - Clearing Record - 0x%x`
- `0x1801b7968`: `VaMaster: Voice Activation User Model Update - Update Successful`
- `0x1801b797b`: `Voice Activation User Model Update - Update Successful.`
- `0x1801b789c`: `SidUbmFile`
- `0x1801b79af`: `Voice Activation User Model Update - Cannot Update Due To Old Training Data - Clearing Record - 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment(CSpVAEngineModel *this, int a2, int a3)
{
  unsigned int v6; // ebx
  void *v7; // r15
  CNuiAudioSapiEnrollment *v8; // rax
  CNuiAudioSapiEnrollment *v9; // rax
  void *v10; // r14
  HRESULT v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int LanguageFromToken; // eax
  int v17; // eax
  unsigned __int16 v18; // dx
  int v19; // eax
  unsigned __int16 v20; // dx
  int v21; // r12d
  int v22; // eax
  CSpVAEngineModel *v23; // rcx
  int UbmAsStream; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // ebx
  int v30; // eax
  int v31; // eax
  SIZE_T cb; // [rsp+30h] [rbp-50h] BYREF
  struct ISpObjectToken *v34; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v35; // [rsp+40h] [rbp-40h] BYREF
  __int64 v36; // [rsp+48h] [rbp-38h] BYREF
  void *v37; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v38; // [rsp+58h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int64 v40; // [rsp+68h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-10h]
  unsigned __int64 v42; // [rsp+78h] [rbp-8h]
  CNuiAudioSapiEnrollment *v43; // [rsp+C0h] [rbp+40h] BYREF
  int v44; // [rsp+C8h] [rbp+48h]
  unsigned __int16 v45; // [rsp+D8h] [rbp+58h] BYREF

  v44 = a2;
  v42 = ((unsigned __int64)this + 8) & -(__int64)(this != 0);
  lpCriticalSection = (LPCRITICAL_SECTION)(v42 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 8));
  if ( *((_QWORD *)this + 10) )
  {
    v6 = 0;
    goto LABEL_57;
  }
  v45 = 1033;
  ppv = 0;
  v36 = 0;
  v34 = 0;
  v35 = 0;
  v38 = 0;
  cb = 204800;
  v7 = 0;
  v37 = 0;
  v40 = 0;
  v8 = (CNuiAudioSapiEnrollment *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
  v43 = v8;
  if ( !v8 )
  {
    *((_QWORD *)this + 10) = 0;
LABEL_50:
    v10 = 0;
    v6 = -2147024882;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(321)",
      -2147024882);
    goto LABEL_52;
  }
  v9 = CNuiAudioSapiEnrollment::CNuiAudioSapiEnrollment(v8);
  *((_QWORD *)this + 10) = v9;
  if ( !v9 )
    goto LABEL_50;
  v10 = CoTaskMemAlloc(cb);
  if ( !v10 )
  {
    v6 = -2147024882;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(325)",
      -2147024882);
    goto LABEL_52;
  }
  v11 = CoCreateInstance(&CLSID_SpVAMaster, 0, 0x17u, &GUID_2d7b756d_3a40_4e0a_bee2_c74da3ccfbbc, &ppv);
  v6 = v11;
  if ( v11 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(328)",
      v11);
    goto LABEL_52;
  }
  v12 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
          ppv,
          &GUID_868e1937_6dc5_4537_aa0e_7de014c8076a,
          &v36);
  v6 = v12;
  if ( v12 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(329)",
      v12);
    goto LABEL_52;
  }
  if ( !v36 )
  {
    v6 = -2147418113;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(330)",
      -2147418113);
    goto LABEL_52;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
  v6 = v13;
  if ( v13 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(331)",
      v13);
    goto LABEL_52;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct ISpObjectToken **))(*(_QWORD *)v36 + 40LL))(
          v36,
          2,
          0,
          &v34);
  v6 = v14;
  if ( v14 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(332)",
      v14);
    goto LABEL_52;
  }
  v15 = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, unsigned __int16 **))v34->lpVtbl->GetStringValue)(
          v34,
          L"DataFile",
          &v35);
  v6 = v15;
  if ( v15 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(334)",
      v15);
    goto LABEL_52;
  }
  LanguageFromToken = SpGetLanguageFromToken(v34, &v45);
  v6 = LanguageFromToken;
  if ( LanguageFromToken < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(335)",
      LanguageFromToken);
    goto LABEL_52;
  }
  v17 = CNuiAudioSapiEnrollment::Initialize(*((CNuiAudioSapiEnrollment **)this + 10), v45, v35, a2);
  v6 = v17;
  if ( v17 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(337)",
      v17);
    goto LABEL_52;
  }
  v19 = CNuiAudioSapiEnrollment::RetrieveTrainedUserBlob(*((CNuiAudioSapiEnrollment **)this + 10), v18, v10, &cb);
  v21 = v19;
  if ( !a3 || v19 < 0 || !cb )
    goto LABEL_45;
  v22 = ((__int64 (__fastcall *)(struct ISpObjectToken *, const wchar_t *, unsigned __int16 **))v34->lpVtbl->GetStringValue)(
          v34,
          L"SidUbmFile",
          &v38);
  v6 = v22;
  if ( v22 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(345)",
      v22);
    goto LABEL_52;
  }
  LOBYTE(v43) = 1;
  UbmAsStream = CSpVAEngineModel::GetUbmAsStream(v23, v38, &v37, &v40);
  v7 = v37;
  if ( UbmAsStream < 0 )
    goto LABEL_45;
  v25 = NuiAudioApi::NuiAudioAreUBMAndUserModelMatched(v37, v40, v10, cb, (bool *)&v43);
  if ( v25 < 0 )
    DoTraceMessage(
      2,
      "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(350)",
      v25);
  if ( !(_BYTE)v43 )
  {
    v26 = CNuiAudioSapiEnrollment::RetrainUserModel(*((CNuiAudioSapiEnrollment **)this + 10));
    v27 = v26;
    if ( v26 < 0 )
    {
      if ( v26 == -2089418751 )
      {
        SpLogEvent(
          "CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
          2u,
          L"Voice Activation User Model Update - Cannot Update Due To Old Training Data - Clearing Record - 0x%x",
          2205548545LL);
      }
      else
      {
        SPTelemetry::SpeakerIDRetrainFailed(v26);
        SpLogEvent(
          "CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
          1u,
          L"Voice Activation User Model Update - Update Failed - Clearing Record - 0x%x",
          v27);
      }
      v29 = CNuiAudioSapiEnrollment::ClearUserModel(*((CNuiAudioSapiEnrollment **)this + 10));
      DoTraceMessage(8, "VaMaster: Clearing Voice Activation Record on training failure - 0x%x", v29);
      SPTelemetry::SpeakerIDRecordCleared(v29);
    }
    else
    {
      v28 = CNuiAudioSapiEnrollment::TrainAndCommitModel(*((CNuiAudioSapiEnrollment **)this + 10));
      v6 = v28;
      if ( v28 < 0 )
      {
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          (const wchar_t *)&NLInternal::s_tracingPrefix,
          L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(360)",
          v28);
        goto LABEL_52;
      }
      DoTraceMessage(8, "VaMaster: Voice Activation User Model Update - Update Successful");
      SpLogEvent(
        "CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
        0,
        L"Voice Activation User Model Update - Update Successful.");
    }
    v30 = CNuiAudioSapiEnrollment::Uninitialize(*((CNuiAudioSapiEnrollment **)this + 10));
    if ( v30 < 0 )
      DoTraceMessage(
        2,
        "%SIgnored Error: function=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(386)",
        v30);
    v31 = CNuiAudioSapiEnrollment::Initialize(*((CNuiAudioSapiEnrollment **)this + 10), v45, v35, v44);
    v6 = v31;
    if ( v31 < 0 )
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CSpVAEngineModel::EnsureInitNuiAudioSapiEnrollment",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\va\\vaenginemodel.cpp(387)",
        v31);
      goto LABEL_52;
    }
    cb = 204800;
  }
  else
  {
LABEL_45:
    cb = 204800;
    if ( v21 == -2146861025 )
      goto LABEL_47;
  }
  CNuiAudioSapiEnrollment::RetrieveTrainedUserModel(*((CNuiAudioSapiEnrollment **)this + 10), v20, v10, &cb);
LABEL_47:
  if ( !v6 )
  {
LABEL_53:
    CoTaskMemFree(v10);
    goto LABEL_54;
  }
LABEL_52:
  CSpVAEngineModel::UninitNuiAudioSapiEnrollment(this);
  if ( v10 )
    goto LABEL_53;
LABEL_54:
  if ( v7 )
    CoTaskMemFree(v7);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v38);
  SPPIPEINFO::~SPPIPEINFO((SPPIPEINFO *)&v35);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v34);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v36);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
LABEL_57:
  LeaveCriticalSection(lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x1801b7624  mov     [rsp-38h+arg_10], rbx
0x1801b7629  mov     [rsp-38h+arg_8], edx
0x1801b762d  push    rbp
0x1801b762e  push    rsi
0x1801b762f  push    rdi
0x1801b7630  push    r12
0x1801b7632  push    r13
0x1801b7634  push    r14
0x1801b7636  push    r15
0x1801b7638  mov     rbp, rsp
0x1801b763b  sub     rsp, 80h
0x1801b7642  mov     r13d, r8d
0x1801b7645  mov     r12d, edx
0x1801b7648  mov     rsi, rcx
0x1801b764b  mov     rax, rcx
0x1801b764e  lea     r9, [rcx+8]
0x1801b7652  neg     rax
0x1801b7655  sbb     r10, r10
0x1801b7658  and     r10, r9
0x1801b765b  mov     [rbp+var_8], r10
0x1801b765f  lea     rax, [r10+8]
0x1801b7663  mov     [rbp+lpCriticalSection], rax
0x1801b7667  mov     rcx, rax; lpCriticalSection
0x1801b766a  call    cs:__imp_EnterCriticalSection
0x1801b7670  nop
0x1801b7671  xor     edi, edi
0x1801b7673  cmp     [rsi+50h], rdi
0x1801b7677  jz      short loc_1801B7680
0x1801b7679  mov     ebx, edi
0x1801b767b  jmp     loc_1801B7B18
0x1801b7680  mov     eax, 409h
0x1801b7685  mov     [rbp+arg_18], ax
0x1801b7689  mov     [rbp+var_20], rdi
0x1801b768d  mov     [rbp+var_38], rdi
0x1801b7691  mov     [rbp+var_48], rdi
0x1801b7695  mov     [rbp+var_40], rdi
0x1801b7699  mov     [rbp+var_28], rdi
0x1801b769d  mov     [rbp+cb], 32000h
0x1801b76a5  mov     r15, rdi
0x1801b76a8  mov     [rbp+var_30], rdi
0x1801b76ac  mov     [rbp+var_18], rdi
0x1801b76b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801b76b7  mov     ecx, 98h; unsigned __int64
0x1801b76bc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801b76c1  mov     [rbp+arg_0], rax
0x1801b76c5  test    rax, rax
0x1801b76c8  jz      loc_1801B7A84
0x1801b76ce  mov     rcx, rax; this
0x1801b76d1  call    ??0CNuiAudioSapiEnrollment@@QEAA@XZ; CNuiAudioSapiEnrollment::CNuiAudioSapiEnrollment(void)
0x1801b76d6  mov     [rsi+50h], rax
0x1801b76da  test    rax, rax
0x1801b76dd  jz      loc_1801B7A88
0x1801b76e3  mov     rcx, [rbp+cb]; cb
0x1801b76e7  call    cs:__imp_CoTaskMemAlloc
0x1801b76ed  mov     r14, rax
0x1801b76f0  test    rax, rax
0x1801b76f3  jnz     short loc_1801B770C
0x1801b76f5  mov     eax, 8007000Eh
0x1801b76fa  mov     ebx, eax
0x1801b76fc  mov     [rsp+80h+var_58], eax
0x1801b7700  lea     rax, aOnecoreuapEndu_331; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7707  jmp     loc_1801B7A9D
0x1801b770c  lea     rax, [rbp+var_20]
0x1801b7710  mov     [rsp+80h+ppv], rax; ppv
0x1801b7715  lea     r9, _GUID_2d7b756d_3a40_4e0a_bee2_c74da3ccfbbc; riid
0x1801b771c  xor     edx, edx; pUnkOuter
0x1801b771e  lea     r8d, [rdx+17h]; dwClsContext
0x1801b7722  lea     rcx, CLSID_SpVAMaster; rclsid
0x1801b7729  call    cs:__imp_CoCreateInstance
0x1801b772f  mov     ebx, eax
0x1801b7731  test    eax, eax
0x1801b7733  jns     short loc_1801B7745
0x1801b7735  mov     [rsp+80h+var_58], eax
0x1801b7739  lea     rax, aOnecoreuapEndu_200; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7740  jmp     loc_1801B7A9D
0x1801b7745  mov     rcx, [rbp+var_20]
0x1801b7749  mov     rax, [rcx]
0x1801b774c  lea     r8, [rbp+var_38]
0x1801b7750  lea     rdx, _GUID_868e1937_6dc5_4537_aa0e_7de014c8076a
0x1801b7757  mov     rax, [rax]
0x1801b775a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b775f  mov     ebx, eax
0x1801b7761  test    eax, eax
0x1801b7763  jns     short loc_1801B7775
0x1801b7765  mov     [rsp+80h+var_58], eax
0x1801b7769  lea     rax, aOnecoreuapEndu_325; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7770  jmp     loc_1801B7A9D
0x1801b7775  mov     rcx, [rbp+var_38]
0x1801b7779  test    rcx, rcx
0x1801b777c  jnz     short loc_1801B7793
0x1801b777e  mov     ebx, 8000FFFFh
0x1801b7783  mov     [rsp+80h+var_58], ebx
0x1801b7787  lea     rax, aOnecoreuapEndu_184; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b778e  jmp     loc_1801B7A9D
0x1801b7793  mov     rax, [rcx]
0x1801b7796  mov     rax, [rax+18h]
0x1801b779a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b779f  mov     ebx, eax
0x1801b77a1  test    eax, eax
0x1801b77a3  jns     short loc_1801B77B5
0x1801b77a5  mov     [rsp+80h+var_58], eax
0x1801b77a9  lea     rax, aOnecoreuapEndu_149; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b77b0  jmp     loc_1801B7A9D
0x1801b77b5  mov     rcx, [rbp+var_38]
0x1801b77b9  mov     rax, [rcx]
0x1801b77bc  lea     r9, [rbp+var_48]
0x1801b77c0  xor     r8d, r8d
0x1801b77c3  lea     edi, [r8+2]
0x1801b77c7  mov     edx, edi
0x1801b77c9  mov     rax, [rax+28h]
0x1801b77cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b77d2  mov     ebx, eax
0x1801b77d4  test    eax, eax
0x1801b77d6  jns     short loc_1801B77EA
0x1801b77d8  mov     [rsp+80h+var_58], eax
0x1801b77dc  lea     rax, aOnecoreuapEndu_190; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b77e3  mov     ecx, edi
0x1801b77e5  jmp     loc_1801B7AA2
0x1801b77ea  mov     rcx, [rbp+var_48]
0x1801b77ee  mov     rax, [rcx]
0x1801b77f1  lea     r8, [rbp+var_40]
0x1801b77f5  lea     rdx, aDatafile; "DataFile"
0x1801b77fc  mov     rax, [rax+30h]
0x1801b7800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b7805  mov     ebx, eax
0x1801b7807  test    eax, eax
0x1801b7809  jns     short loc_1801B7818
0x1801b780b  mov     [rsp+80h+var_58], eax
0x1801b780f  lea     rax, aOnecoreuapEndu_279; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7816  jmp     short loc_1801B77E3
0x1801b7818  lea     rdx, [rbp+arg_18]; unsigned __int16 *
0x1801b781c  mov     rcx, [rbp+var_48]; struct ISpObjectToken *
0x1801b7820  call    ?SpGetLanguageFromToken@@YAJPEAUISpObjectToken@@PEAG@Z; SpGetLanguageFromToken(ISpObjectToken *,ushort *)
0x1801b7825  mov     ebx, eax
0x1801b7827  test    eax, eax
0x1801b7829  jns     short loc_1801B7838
0x1801b782b  mov     [rsp+80h+var_58], eax
0x1801b782f  lea     rax, aOnecoreuapEndu_183; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7836  jmp     short loc_1801B77E3
0x1801b7838  mov     r9d, r12d; int
0x1801b783b  mov     r8, [rbp+var_40]; unsigned __int16 *
0x1801b783f  movzx   edx, [rbp+arg_18]; unsigned __int16
0x1801b7843  mov     rcx, [rsi+50h]; this
0x1801b7847  call    ?Initialize@CNuiAudioSapiEnrollment@@QEAAJGPEBGH@Z; CNuiAudioSapiEnrollment::Initialize(ushort,ushort const *,int)
0x1801b784c  mov     ebx, eax
0x1801b784e  test    eax, eax
0x1801b7850  jns     short loc_1801B785F
0x1801b7852  mov     [rsp+80h+var_58], eax
0x1801b7856  lea     rax, aOnecoreuapEndu_176; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b785d  jmp     short loc_1801B77E3
0x1801b785f  lea     r9, [rbp+cb]; unsigned __int64 *
0x1801b7863  mov     r8, r14; void *
0x1801b7866  mov     rcx, [rsi+50h]; this
0x1801b786a  call    ?RetrieveTrainedUserBlob@CNuiAudioSapiEnrollment@@QEAAJGPEAXPEA_K@Z; CNuiAudioSapiEnrollment::RetrieveTrainedUserBlob(ushort,void *,unsigned __int64 *)
0x1801b786f  mov     r12d, eax
0x1801b7872  test    r13d, r13d
0x1801b7875  jz      loc_1801B7A5D
0x1801b787b  test    eax, eax
0x1801b787d  js      loc_1801B7A5D
0x1801b7883  cmp     [rbp+cb], r15
0x1801b7887  jbe     loc_1801B7A5D
0x1801b788d  mov     rcx, [rbp+var_48]
0x1801b7891  mov     rdx, [rcx]
0x1801b7894  mov     rax, [rdx+30h]
0x1801b7898  lea     r8, [rbp+var_28]
0x1801b789c  lea     rdx, aSidubmfile; "SidUbmFile"
0x1801b78a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b78a8  mov     ebx, eax
0x1801b78aa  test    eax, eax
0x1801b78ac  jns     short loc_1801B78BE
0x1801b78ae  mov     [rsp+80h+var_58], eax
0x1801b78b2  lea     rax, aOnecoreuapEndu_211; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b78b9  jmp     loc_1801B77E3
0x1801b78be  mov     r13d, 1
0x1801b78c4  mov     byte ptr [rbp+arg_0], r13b
0x1801b78c8  lea     r9, [rbp+var_18]; unsigned __int64 *
0x1801b78cc  lea     r8, [rbp+var_30]; void **
0x1801b78d0  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x1801b78d4  call    ?GetUbmAsStream@CSpVAEngineModel@@AEAAJPEBGPEAPEAXPEA_K@Z; CSpVAEngineModel::GetUbmAsStream(ushort const *,void * *,unsigned __int64 *)
0x1801b78d9  mov     r15, [rbp+var_30]
0x1801b78dd  test    eax, eax
0x1801b78df  js      loc_1801B7A5D
0x1801b78e5  lea     rax, [rbp+arg_0]
0x1801b78e9  mov     [rsp+80h+ppv], rax; bool *
0x1801b78ee  mov     r9d, dword ptr [rbp+cb]; int
0x1801b78f2  mov     r8, r14; void *
0x1801b78f5  mov     edx, dword ptr [rbp+var_18]; int
0x1801b78f8  mov     rcx, r15; void *
0x1801b78fb  call    ?NuiAudioAreUBMAndUserModelMatched@NuiAudioApi@@SAJPEBXH0HPEA_N@Z; NuiAudioApi::NuiAudioAreUBMAndUserModelMatched(void const *,int,void const *,int,bool *)
0x1801b7900  test    eax, eax
0x1801b7902  jns     short loc_1801B7930
0x1801b7904  mov     [rsp+80h+var_58], eax
0x1801b7908  lea     rax, aOnecoreuapEndu_198; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b790f  mov     [rsp+80h+ppv], rax
0x1801b7914  lea     r9, aCspvaenginemod_7; "CSpVAEngineModel::EnsureInitNuiAudioSap"...
0x1801b791b  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801b7922  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x1801b7929  mov     ecx, edi; int
0x1801b792b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801b7930  cmp     byte ptr [rbp+arg_0], 0
0x1801b7934  jnz     loc_1801B7A5D
0x1801b793a  mov     rcx, [rsi+50h]; this
0x1801b793e  call    ?RetrainUserModel@CNuiAudioSapiEnrollment@@QEAAJXZ; CNuiAudioSapiEnrollment::RetrainUserModel(void)
0x1801b7943  mov     ebx, eax
0x1801b7945  test    eax, eax
0x1801b7947  js      short loc_1801B7993
0x1801b7949  mov     rcx, [rsi+50h]; this
0x1801b794d  call    ?TrainAndCommitModel@CNuiAudioSapiEnrollment@@QEAAJXZ; CNuiAudioSapiEnrollment::TrainAndCommitModel(void)
0x1801b7952  mov     ebx, eax
0x1801b7954  test    eax, eax
0x1801b7956  jns     short loc_1801B7968
0x1801b7958  mov     [rsp+80h+var_58], eax
0x1801b795c  lea     rax, aOnecoreuapEndu_139; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7963  jmp     loc_1801B77E3
0x1801b7968  lea     rdx, aVamasterVoiceA; "VaMaster: Voice Activation User Model U"...
0x1801b796f  mov     ecx, 8; int
0x1801b7974  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801b7979  xor     eax, eax
0x1801b797b  lea     r8, aVoiceActivatio_0; "Voice Activation User Model Update - Up"...
0x1801b7982  movzx   edx, ax; unsigned __int16
0x1801b7985  lea     rcx, aCspvaenginemod_1; "CSpVAEngineModel::EnsureInitNuiAudioSap"...
0x1801b798c  call    ?SpLogEvent@@YAXPEBDGPEBGZZ; SpLogEvent(char const *,ushort,ushort const *,...)
0x1801b7991  jmp     short loc_1801B79EF
0x1801b7993  cmp     ebx, 83760001h
0x1801b7999  jz      short loc_1801B79AB
0x1801b799b  mov     ecx, ebx; int
0x1801b799d  call    ?SpeakerIDRetrainFailed@SPTelemetry@@SAXJ@Z; SPTelemetry::SpeakerIDRetrainFailed(long)
0x1801b79a2  lea     r8, aVoiceActivatio_5; "Voice Activation User Model Update - Up"...
0x1801b79a9  jmp     short loc_1801B79B6
0x1801b79ab  movzx   r13d, di
0x1801b79af  lea     r8, aVoiceActivatio_8; "Voice Activation User Model Update - Ca"...
0x1801b79b6  mov     r9d, ebx
0x1801b79b9  movzx   edx, r13w; unsigned __int16
0x1801b79bd  lea     rcx, aCspvaenginemod_1; "CSpVAEngineModel::EnsureInitNuiAudioSap"...
0x1801b79c4  call    ?SpLogEvent@@YAXPEBDGPEBGZZ; SpLogEvent(char const *,ushort,ushort const *,...)
0x1801b79c9  mov     rcx, [rsi+50h]; this
0x1801b79cd  call    ?ClearUserModel@CNuiAudioSapiEnrollment@@QEAAJXZ; CNuiAudioSapiEnrollment::ClearUserModel(void)
0x1801b79d2  mov     ebx, eax
0x1801b79d4  mov     r8d, eax
0x1801b79d7  lea     rdx, aVamasterCleari; "VaMaster: Clearing Voice Activation Rec"...
0x1801b79de  mov     ecx, 8; int
0x1801b79e3  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801b79e8  mov     ecx, ebx; int
0x1801b79ea  call    ?SpeakerIDRecordCleared@SPTelemetry@@SAXJ@Z; SPTelemetry::SpeakerIDRecordCleared(long)
0x1801b79ef  mov     rcx, [rsi+50h]; this
0x1801b79f3  call    ?Uninitialize@CNuiAudioSapiEnrollment@@QEAAJXZ; CNuiAudioSapiEnrollment::Uninitialize(void)
0x1801b79f8  test    eax, eax
0x1801b79fa  jns     short loc_1801B7A28
0x1801b79fc  mov     [rsp+80h+var_58], eax
0x1801b7a00  lea     rax, aOnecoreuapEndu_84; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7a07  mov     [rsp+80h+ppv], rax
0x1801b7a0c  lea     r9, aCspvaenginemod_7; "CSpVAEngineModel::EnsureInitNuiAudioSap"...
0x1801b7a13  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801b7a1a  lea     rdx, aSignoredErrorF; "%SIgnored Error: function=%S, fileline="...
0x1801b7a21  mov     ecx, edi; int
0x1801b7a23  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801b7a28  mov     r9d, [rbp+arg_8]; int
0x1801b7a2c  mov     r8, [rbp+var_40]; unsigned __int16 *
0x1801b7a30  movzx   edx, [rbp+arg_18]; unsigned __int16
0x1801b7a34  mov     rcx, [rsi+50h]; this
0x1801b7a38  call    ?Initialize@CNuiAudioSapiEnrollment@@QEAAJGPEBGH@Z; CNuiAudioSapiEnrollment::Initialize(ushort,ushort const *,int)
0x1801b7a3d  mov     ebx, eax
0x1801b7a3f  test    eax, eax
0x1801b7a41  jns     short loc_1801B7A53
0x1801b7a43  mov     [rsp+80h+var_58], eax
0x1801b7a47  lea     rax, aOnecoreuapEndu_163; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7a4e  jmp     loc_1801B77E3
0x1801b7a53  mov     [rbp+cb], 32000h
0x1801b7a5b  jmp     short loc_1801B7A6E
0x1801b7a5d  mov     [rbp+cb], 32000h
0x1801b7a65  cmp     r12d, 8009801Fh
0x1801b7a6c  jz      short loc_1801B7A7E
0x1801b7a6e  lea     r9, [rbp+cb]; unsigned __int64 *
0x1801b7a72  mov     r8, r14; void *
0x1801b7a75  mov     rcx, [rsi+50h]; this
0x1801b7a79  call    ?RetrieveTrainedUserModel@CNuiAudioSapiEnrollment@@QEAAJGPEAXPEA_K@Z; CNuiAudioSapiEnrollment::RetrieveTrainedUserModel(ushort,void *,unsigned __int64 *)
0x1801b7a7e  test    ebx, ebx
0x1801b7a80  jz      short loc_1801B7ACE
0x1801b7a82  jmp     short loc_1801B7AC1
0x1801b7a84  mov     [rsi+50h], rdi
0x1801b7a88  mov     r14, rdi
0x1801b7a8b  mov     eax, 8007000Eh
0x1801b7a90  mov     ebx, eax
0x1801b7a92  mov     [rsp+80h+var_58], eax
0x1801b7a96  lea     rax, aOnecoreuapEndu_330; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801b7a9d  mov     ecx, 2; int
0x1801b7aa2  mov     [rsp+80h+ppv], rax
0x1801b7aa7  lea     r9, aCspvaenginemod_7; "CSpVAEngineModel::EnsureInitNuiAudioSap"...
0x1801b7aae  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801b7ab5  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1801b7abc  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801b7ac1  mov     rcx, rsi; this
0x1801b7ac4  call    ?UninitNuiAudioSapiEnrollment@CSpVAEngineModel@@AEAAXXZ; CSpVAEngineModel::UninitNuiAudioSapiEnrollment(void)
0x1801b7ac9  test    r14, r14
0x1801b7acc  jz      short loc_1801B7AD7
0x1801b7ace  mov     rcx, r14; pv
0x1801b7ad1  call    cs:__imp_CoTaskMemFree
0x1801b7ad7  test    r15, r15
0x1801b7ada  jz      short loc_1801B7AE6
0x1801b7adc  mov     rcx, r15; pv
  ... truncated ...
```
