# UnifiedSession::Initialize(CRecoInstCtxt *,std::vector<CRecoInstCtxt *,std::allocator<CRecoInstCtxt *>> const &)

- ea: `0x180032b5c`
- end: `0x1800333f5`
- name: `?Initialize@UnifiedSession@@QEAAJPEAVCRecoInstCtxt@@AEBV?$vector@PEAVCRecoInstCtxt@@V?$allocator@PEAVCRecoInstCtxt@@@std@@@std@@@Z`
- size: `2201`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180031a70`
- `0x180038fcc`

## callees

- `0x180013ec0`
- `0x180021944`
- `0x1800243e8`
- `0x180026508`
- `0x18002895c`
- `0x180029860`
- `0x180030738`
- `0x18003151c`
- `0x1800315fc`
- `0x180032b5c`
- `0x1800335d4`
- `0x180033efc`
- `0x180034084`
- `0x1800341dc`
- `0x1800345e0`
- `0x18003b7d0`
- `0x180056934`
- `0x1800586a8`
- `0x180069478`
- `0x180079e30`
- `0x18007d7a5`
- `0x1800b6dc8`
- `0x18012c0c4`
- `0x18025c624`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033201`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033266`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033201`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180033266`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032ce7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032e2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003329e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003337e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800333ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032e2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003329e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003337e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800333ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall UnifiedSession::Initialize(bool *a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, GUID *, GUID *, GUID *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  int v17; // ebx
  void *v18; // rcx
  OneSettingsPolicyWrapper **v19; // rax
  const unsigned __int16 *v20; // rdx
  int BoolValue; // eax
  _OWORD *v22; // rbx
  int v23; // eax
  unsigned int v24; // edi
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  const WCHAR *v29; // rcx
  int v30; // eax
  void *v31; // rcx
  unsigned __int16 **v32; // r8
  __int64 String; // rdx
  __int64 v34; // rdx
  std::_Ref_count_base *v35; // rcx
  std::_Ref_count_base *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  unsigned __int16 **v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rdx
  std::_Ref_count_base *v42; // rcx
  std::_Ref_count_base *v43; // rax
  HKEY v44; // rcx
  const unsigned __int16 *v45; // rdx
  HKEY v46; // rcx
  const unsigned __int16 *v47; // rdx
  __int64 v48; // rdx
  const wchar_t *v49; // rax
  const wchar_t *v50; // r9
  HRESULT Guid; // eax
  void *v52; // rcx
  HRESULT v53; // eax
  void *v54; // rcx
  __int64 v55; // rcx
  int ActiveApplicationMonikerString; // eax
  int inited; // eax
  void *v58; // rcx
  void *v59; // rcx
  int ppv; // [rsp+20h] [rbp-E8h]
  int ppva; // [rsp+20h] [rbp-E8h]
  int ppvb; // [rsp+20h] [rbp-E8h]
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID v64; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v65; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-B0h] BYREF
  std::_Ref_count_base *v67; // [rsp+60h] [rbp-A8h] BYREF
  char v68; // [rsp+68h] [rbp-A0h]
  unsigned __int16 *v69[3]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v70; // [rsp+88h] [rbp-80h]
  __int128 v71; // [rsp+90h] [rbp-78h] BYREF
  int v72[8]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  if ( *a3 == a3[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  if ( memcmp_0(a1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
    return 2147549183LL;
  }
  v7 = std::make_shared<UnifiedSessionResultWrapper,>(&p_pv);
  std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(a1 + 48, v7);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  v8 = std::make_shared<UnifiedSessionResultWrapper,>(&p_pv);
  std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(a1 + 64, v8);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  v9 = std::make_shared<UnifiedSessionResultWrapper,>(&p_pv);
  std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(a1 + 80, v9);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  DoTraceMessage(
    16,
    "UnifiedSession: Instantiating with %u contexts (owner is 0x%08p)",
    (__int64)(a3[1] - *a3) >> 3,
    a2);
  *((_QWORD *)a1 + 3) = a2;
  v64 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  v10 = CoCreateInstance(&CLSID_SpResourceManager, 0, 1u, &GUID_93384e18_5014_43d5_adbb_a78e055926bd, &v64);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)v10,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    return v11;
  }
  v65 = 0;
  v12 = v64;
  v13 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, GUID *))(*(_QWORD *)v64 + 40LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  ppvb = 0;
  v14 = v13(v12, &CLSID_SpAudioOrchestrator, &GUID_00000000_0000_0000_0000_000000000000, &IID_ISpAudioOrchestratorInput);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)v14,
      0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    return v15;
  }
  v71 = 0;
  pv = 0;
  v16 = *v65;
  p_pv = &pv;
  v67 = 0;
  v68 = 1;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int128 *, std::_Ref_count_base **))(v16 + 32))(
          v65,
          1,
          &v71,
          &v67);
  wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)v17,
      0);
    v18 = pv;
    pv = 0;
    if ( v18 )
      CoTaskMemFree(v18);
LABEL_20:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    return (unsigned int)v17;
  }
  *((_DWORD *)a1 + 57) = *((_DWORD *)pv + 2) / 0x3E8u;
  v19 = (OneSettingsPolicyWrapper **)SRCloudPolicy::Instance(&p_pv);
  BoolValue = OneSettingsPolicyWrapper::GetBoolValue(*v19, v20, a1 + 232);
  if ( BoolValue < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)BoolValue,
      0);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  v22 = a1 + 32;
  v23 = Halsey::ActionObjectBase<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal,Halsey::CuInputBase>::Clone<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal>(
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 80LL),
          a1 + 32);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)v23,
      ppvb);
    v25 = pv;
    pv = 0;
    if ( v25 )
      CoTaskMemFree(v25);
LABEL_73:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    return v24;
  }
  v26 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 80LL);
  if ( !v26 || *(_DWORD *)(v26 + 396) == 0x4000 )
  {
    DoTraceMessage(16, "CloudCoordinator: New session is implicit for instCtxt handle=%u", a2[6]);
    a1[16] = 1;
    Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternalCreator::AddPropertiesToCuInput(
      *((_QWORD *)a1 + 3) + 104LL,
      *((_QWORD *)a1 + 3) + 80LL,
      *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    Guid = CoCreateGuid((GUID *)(*(_QWORD *)v22 + 200LL));
    v24 = Guid;
    if ( Guid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
        (const char *)(unsigned int)Guid,
        ppvb);
      v52 = pv;
      pv = 0;
      if ( v52 )
        CoTaskMemFree(v52);
      goto LABEL_73;
    }
    v53 = CoCreateGuid((GUID *)(*(_QWORD *)v22 + 216LL));
    v24 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
        (const char *)(unsigned int)v53,
        ppvb);
      v54 = pv;
      pv = 0;
      if ( v54 )
        CoTaskMemFree(v54);
      goto LABEL_73;
    }
    *(_DWORD *)(*(_QWORD *)v22 + 360LL) = 2;
  }
  else
  {
    std::wstring::wstring(v69);
    v27 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL);
    if ( v27 )
    {
      v28 = *(unsigned int *)(v27 + 152);
      v29 = (const WCHAR *)(v27 + 56);
      if ( *((_QWORD *)v29 + 3) > 7u )
        v29 = *(const WCHAR **)v29;
    }
    else
    {
      v29 = &cchOriginalDestLength;
      v28 = 0;
    }
    v30 = CRecoInstCtxt::BuildRegistryOverrideKey(v29, v28, v69);
    v24 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
        (const char *)(unsigned int)v30,
        ppvb);
      std::wstring::_Tidy_deallocate(v69);
      v31 = pv;
      pv = 0;
      if ( v31 )
        CoTaskMemFree(v31);
      goto LABEL_73;
    }
    v32 = v69;
    if ( v70 > 7 )
      LODWORD(v32) = v69[0];
    String = SpRegUtil::GetString(
               (int)v72,
               -2147483647,
               (int)v32,
               (int)L"MockInputFile",
               (unsigned __int16 *)&cchOriginalDestLength);
    Halsey::swstring::swstring(&p_pv, String);
    v34 = *(_QWORD *)v22;
    v35 = v67;
    if ( v67 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v67 + 2);
      v35 = v67;
    }
    *(_QWORD *)(v34 + 560) = p_pv;
    v36 = *(std::_Ref_count_base **)(v34 + 568);
    *(_QWORD *)(v34 + 568) = v35;
    if ( v36 )
      std::_Ref_count_base::_Decref(v36);
    if ( v67 )
      std::_Ref_count_base::_Decref(v67);
    std::wstring::_Tidy_deallocate(v72);
    v37 = *(_QWORD *)(*(_QWORD *)v22 + 560LL);
    if ( v37 )
      v38 = *(_QWORD *)(v37 + 16);
    else
      v38 = 0;
    if ( v38 )
    {
      v39 = v69;
      if ( v70 > 7 )
        LODWORD(v39) = v69[0];
      v40 = SpRegUtil::GetString(
              (int)v72,
              -2147483647,
              (int)v39,
              (int)L"MockConversationName",
              (unsigned __int16 *)&cchOriginalDestLength);
      Halsey::swstring::swstring(&p_pv, v40);
      v41 = *(_QWORD *)v22;
      v42 = v67;
      if ( v67 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v67 + 2);
        v42 = v67;
      }
      *(_QWORD *)(v41 + 576) = p_pv;
      v43 = *(std::_Ref_count_base **)(v41 + 584);
      *(_QWORD *)(v41 + 584) = v42;
      if ( v43 )
        std::_Ref_count_base::_Decref(v43);
      if ( v67 )
        std::_Ref_count_base::_Decref(v67);
      std::wstring::_Tidy_deallocate(v72);
      v45 = (const unsigned __int16 *)v69;
      if ( v70 > 7 )
        v45 = v69[0];
      SpRegUtil::Delete(v44, v45, L"MockInputFile");
      v47 = (const unsigned __int16 *)v69;
      if ( v70 > 7 )
        v47 = v69[0];
      SpRegUtil::Delete(v46, v47, L"MockConversationName");
      Halsey::swstring::c_str((Halsey::swstring *)(*(_QWORD *)v22 + 576LL));
      v49 = Halsey::swstring::c_str((Halsey::swstring *)(v48 + 560));
      DoTraceMessage(16, "CloudCoordinator: using mocks %S %S for instCtxt handle=%u", v49, v50, a2[6]);
    }
    std::wstring::_Tidy_deallocate(v69);
  }
  v55 = *(_QWORD *)(*(_QWORD *)v22 + 328LL);
  if ( v55 && !*(_DWORD *)(v55 + 216) )
  {
    DoTraceMessage(
      16,
      "CloudCoordinator: New session is cloud-continuous and will deliver local results asynchronously for instCtxt handle=%u",
      a2[6]);
    a1[18] = 1;
    *((_DWORD *)a1 + 5) = 1;
  }
  *(_OWORD *)a1 = *(_OWORD *)(*((_QWORD *)a1 + 4) + 216LL);
  ActiveApplicationMonikerString = GetActiveApplicationMonikerString(a3, a1 + 96);
  if ( ActiveApplicationMonikerString < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)ActiveApplicationMonikerString,
      ppvb);
  inited = UnifiedSession::DoSessionInitTelemetry(a1, a3);
  v17 = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\unifiedsession.cpp",
      (const char *)(unsigned int)inited,
      ppvb);
    v58 = pv;
    pv = 0;
    if ( v58 )
      CoTaskMemFree(v58);
    goto LABEL_20;
  }
  v59 = pv;
  pv = 0;
  if ( v59 )
    CoTaskMemFree(v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  return 0;
}

```

## disassembly

```asm
0x180032b5c  push    rbx
0x180032b5e  push    rsi
0x180032b5f  push    rdi
0x180032b60  push    r12
0x180032b62  push    r13
0x180032b64  push    r14
0x180032b66  push    r15
0x180032b68  sub     rsp, 0D0h
0x180032b6f  mov     rax, cs:__security_cookie
0x180032b76  xor     rax, rsp
0x180032b79  mov     [rsp+108h+var_48], rax
0x180032b81  mov     r15, r8
0x180032b84  mov     r13, rdx
0x180032b87  mov     rsi, rcx
0x180032b8a  xor     r12d, r12d
0x180032b8d  test    rdx, rdx
0x180032b90  jnz     short loc_180032BB9
0x180032b92  mov     rcx, [rsp+108h]; this
0x180032b9a  mov     ebx, 80070057h
0x180032b9f  mov     r9d, ebx; char *
0x180032ba2  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032ba9  lea     edx, [r13+7Dh]; void *
0x180032bad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032bb2  mov     eax, ebx
0x180032bb4  jmp     loc_1800333D1
0x180032bb9  mov     rax, [r8+8]
0x180032bbd  cmp     [r8], rax
0x180032bc0  jnz     short loc_180032BEA
0x180032bc2  mov     rcx, [rsp+108h]; this
0x180032bca  mov     ebx, 80070057h
0x180032bcf  mov     r9d, ebx; char *
0x180032bd2  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032bd9  mov     edx, 7Eh ; '~'; void *
0x180032bde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032be3  mov     eax, ebx
0x180032be5  jmp     loc_1800333D1
0x180032bea  mov     r8d, 10h; Size
0x180032bf0  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180032bf7  call    memcmp_0
0x180032bfc  test    eax, eax
0x180032bfe  jz      short loc_180032C28
0x180032c00  mov     rcx, [rsp+108h]; this
0x180032c08  mov     ebx, 8000FFFFh
0x180032c0d  mov     r9d, ebx; char *
0x180032c10  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032c17  mov     edx, 7Fh; void *
0x180032c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032c21  mov     eax, ebx
0x180032c23  jmp     loc_1800333D1
0x180032c28  lea     rcx, [rsp+108h+var_B0]
0x180032c2d  call    ??$make_shared@VUnifiedSessionResultWrapper@@$$V@std@@YA?AV?$shared_ptr@VUnifiedSessionResultWrapper@@@0@XZ; std::make_shared<UnifiedSessionResultWrapper,>(void)
0x180032c32  lea     rcx, [rsi+30h]
0x180032c36  mov     rdx, rax
0x180032c39  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x180032c3e  mov     rcx, [rsp+108h+var_A8]; this
0x180032c43  test    rcx, rcx
0x180032c46  jz      short loc_180032C4D
0x180032c48  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c4d  lea     rcx, [rsp+108h+var_B0]
0x180032c52  call    ??$make_shared@VUnifiedSessionResultWrapper@@$$V@std@@YA?AV?$shared_ptr@VUnifiedSessionResultWrapper@@@0@XZ; std::make_shared<UnifiedSessionResultWrapper,>(void)
0x180032c57  lea     rcx, [rsi+40h]
0x180032c5b  mov     rdx, rax
0x180032c5e  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x180032c63  mov     rcx, [rsp+108h+var_A8]; this
0x180032c68  test    rcx, rcx
0x180032c6b  jz      short loc_180032C72
0x180032c6d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c72  lea     rcx, [rsp+108h+var_B0]
0x180032c77  call    ??$make_shared@VUnifiedSessionResultWrapper@@$$V@std@@YA?AV?$shared_ptr@VUnifiedSessionResultWrapper@@@0@XZ; std::make_shared<UnifiedSessionResultWrapper,>(void)
0x180032c7c  lea     rcx, [rsi+50h]
0x180032c80  mov     rdx, rax
0x180032c83  call    ??4?$shared_ptr@VCloudConnectionCookie@Halsey@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Halsey::CloudConnectionCookie>::operator=(std::shared_ptr<Halsey::CloudConnectionCookie> &&)
0x180032c88  mov     rcx, [rsp+108h+var_A8]; this
0x180032c8d  test    rcx, rcx
0x180032c90  jz      short loc_180032C97
0x180032c92  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c97  mov     r8, [r15+8]
0x180032c9b  sub     r8, [r15]
0x180032c9e  sar     r8, 3
0x180032ca2  mov     r9, r13
0x180032ca5  lea     rdx, aUnifiedsession_0; "UnifiedSession: Instantiating with %u c"...
0x180032cac  mov     ecx, 10h; int
0x180032cb1  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180032cb6  mov     [rsi+18h], r13
0x180032cba  mov     [rsp+108h+var_C0], r12
0x180032cbf  lea     rcx, [rsp+108h+var_C0]
0x180032cc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032cc9  lea     rax, [rsp+108h+var_C0]
0x180032cce  mov     [rsp+108h+ppv], rax; int
0x180032cd3  lea     r9, _GUID_93384e18_5014_43d5_adbb_a78e055926bd; riid
0x180032cda  xor     edx, edx; pUnkOuter
0x180032cdc  lea     r8d, [rdx+1]; dwClsContext
0x180032ce0  lea     rcx, CLSID_SpResourceManager; rclsid
0x180032ce7  call    cs:__imp_CoCreateInstance
0x180032ced  mov     ebx, eax
0x180032cef  test    eax, eax
0x180032cf1  jns     short loc_180032D21
0x180032cf3  mov     rcx, [rsp+108h]; this
0x180032cfb  mov     r9d, eax; char *
0x180032cfe  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032d05  mov     edx, 8Ah; void *
0x180032d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d0f  nop
0x180032d10  lea     rcx, [rsp+108h+var_C0]
0x180032d15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032d1a  mov     eax, ebx
0x180032d1c  jmp     loc_1800333D1
0x180032d21  mov     [rsp+108h+var_B8], r12
0x180032d26  mov     rdi, [rsp+108h+var_C0]
0x180032d2b  mov     rax, [rdi]
0x180032d2e  mov     rbx, [rax+28h]
0x180032d32  lea     rcx, [rsp+108h+var_B8]
0x180032d37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032d3c  lea     rax, [rsp+108h+var_B8]
0x180032d41  mov     [rsp+108h+var_E0], rax
0x180032d46  mov     dword ptr [rsp+108h+ppv], r12d; int
0x180032d4b  lea     r9, IID_ISpAudioOrchestratorInput
0x180032d52  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x180032d59  lea     rdx, CLSID_SpAudioOrchestrator
0x180032d60  mov     rcx, rdi
0x180032d63  mov     rax, rbx
0x180032d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d6b  mov     ebx, eax
0x180032d6d  test    eax, eax
0x180032d6f  jns     short loc_180032DAA
0x180032d71  mov     rcx, [rsp+108h]; this
0x180032d79  mov     r9d, eax; char *
0x180032d7c  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032d83  mov     edx, 8Dh; void *
0x180032d88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d8d  nop
0x180032d8e  lea     rcx, [rsp+108h+var_B8]
0x180032d93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032d98  nop
0x180032d99  lea     rcx, [rsp+108h+var_C0]
0x180032d9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032da3  mov     eax, ebx
0x180032da5  jmp     loc_1800333D1
0x180032daa  xorps   xmm0, xmm0
0x180032dad  movups  [rsp+108h+var_78], xmm0
0x180032db5  mov     [rsp+108h+pv], r12
0x180032dba  mov     rcx, [rsp+108h+var_B8]
0x180032dbf  mov     rax, [rcx]
0x180032dc2  lea     rdx, [rsp+108h+pv]
0x180032dc7  mov     [rsp+108h+var_B0], rdx
0x180032dcc  mov     [rsp+108h+var_A8], r12
0x180032dd1  mov     [rsp+108h+var_A0], 1
0x180032dd6  lea     r9, [rsp+108h+var_A8]
0x180032ddb  lea     r8, [rsp+108h+var_78]
0x180032de3  mov     edx, 1
0x180032de8  mov     rax, [rax+20h]
0x180032dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032df1  mov     ebx, eax
0x180032df3  lea     rcx, [rsp+108h+var_B0]
0x180032df8  call    ??1?$out_param_t@V?$unique_ptr@USPPHRASE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180032dfd  test    ebx, ebx
0x180032dff  jns     short loc_180032E50
0x180032e01  mov     rcx, [rsp+108h]; this
0x180032e09  mov     r9d, ebx; char *
0x180032e0c  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032e13  mov     edx, 91h; void *
0x180032e18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e1d  nop
0x180032e1e  mov     rcx, [rsp+108h+pv]; pv
0x180032e23  mov     [rsp+108h+pv], r12
0x180032e28  test    rcx, rcx
0x180032e2b  jz      short loc_180032E34
0x180032e2d  call    cs:__imp_CoTaskMemFree
0x180032e33  nop
0x180032e34  lea     rcx, [rsp+108h+var_B8]
0x180032e39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032e3e  nop
0x180032e3f  lea     rcx, [rsp+108h+var_C0]
0x180032e44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032e49  mov     eax, ebx
0x180032e4b  jmp     loc_1800333D1
0x180032e50  mov     eax, 10624DD3h
0x180032e55  mov     rcx, [rsp+108h+pv]
0x180032e5a  mul     dword ptr [rcx+8]
0x180032e5d  shr     edx, 6
0x180032e60  mov     [rsi+0E4h], edx
0x180032e66  lea     rcx, [rsp+108h+var_B0]
0x180032e6b  call    ?Instance@SRCloudPolicy@@SA?AV?$shared_ptr@VOneSettingsPolicyWrapper@@@std@@XZ; SRCloudPolicy::Instance(void)
0x180032e70  nop
0x180032e71  lea     r8, [rsi+0E8h]; bool *
0x180032e78  mov     rcx, [rax]; this
0x180032e7b  call    ?GetBoolValue@OneSettingsPolicyWrapper@@QEAAJPEBGPEA_N@Z; OneSettingsPolicyWrapper::GetBoolValue(ushort const *,bool *)
0x180032e80  mov     rcx, [rsp+108h]; this
0x180032e88  test    eax, eax
0x180032e8a  jns     short loc_180032EA1
0x180032e8c  mov     r9d, eax; char *
0x180032e8f  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032e96  mov     edx, 94h; void *
0x180032e9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032ea0  nop
0x180032ea1  mov     rcx, [rsp+108h+var_A8]; this
0x180032ea6  test    rcx, rcx
0x180032ea9  jz      short loc_180032EB0
0x180032eab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032eb0  lea     rbx, [rsi+20h]
0x180032eb4  mov     rcx, [rsi+18h]
0x180032eb8  mov     rdx, rbx
0x180032ebb  mov     rcx, [rcx+50h]
0x180032ebf  call    ??$Clone@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@?$ActionObjectBase@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@VCuInputBase@Halsey@@@Halsey@@QEAAJAEAV?$shared_ptr@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@@Z; Halsey::ActionObjectBase<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal,Halsey::CuInputBase>::Clone<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal>(std::shared_ptr<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal> &)
0x180032ec4  mov     edi, eax
0x180032ec6  test    eax, eax
0x180032ec8  jns     short loc_180032F19
0x180032eca  mov     rcx, [rsp+108h]; this
0x180032ed2  mov     r9d, eax; char *
0x180032ed5  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032edc  mov     edx, 96h; void *
0x180032ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032ee6  nop
0x180032ee7  mov     rcx, [rsp+108h+pv]; pv
0x180032eec  mov     [rsp+108h+pv], r12
0x180032ef1  test    rcx, rcx
0x180032ef4  jz      short loc_180032EFD
0x180032ef6  call    cs:__imp_CoTaskMemFree
0x180032efc  nop
0x180032efd  lea     rcx, [rsp+108h+var_B8]
0x180032f02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032f07  nop
0x180032f08  lea     rcx, [rsp+108h+var_C0]
0x180032f0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032f12  mov     eax, edi
0x180032f14  jmp     loc_1800333D1
0x180032f19  mov     rax, [rsi+18h]
0x180032f1d  mov     rcx, [rax+50h]
0x180032f21  test    rcx, rcx
0x180032f24  jz      loc_1800331C9
0x180032f2a  cmp     dword ptr [rcx+18Ch], 4000h
0x180032f34  jz      loc_1800331C9
0x180032f3a  lea     rcx, [rsp+108h+var_98]
0x180032f3f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180032f44  nop
0x180032f45  mov     rax, [rsi+18h]
0x180032f49  mov     rcx, [rax+8]
0x180032f4d  test    rcx, rcx
0x180032f50  jz      short loc_180032F6F
0x180032f52  mov     edx, [rcx+98h]
0x180032f58  add     rcx, 38h ; '8'
0x180032f5c  cmp     qword ptr [rcx+18h], 7
0x180032f61  jbe     short loc_180032F66
0x180032f63  mov     rcx, [rcx]
0x180032f66  lea     r14, cchOriginalDestLength
0x180032f6d  jmp     short loc_180032F7C
0x180032f6f  lea     r14, cchOriginalDestLength
0x180032f76  mov     rcx, r14
0x180032f79  mov     edx, r12d
0x180032f7c  lea     r8, [rsp+108h+var_98]
0x180032f81  call    ?BuildRegistryOverrideKey@CRecoInstCtxt@@SAJPEBGKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRecoInstCtxt::BuildRegistryOverrideKey(ushort const *,ulong,std::wstring &)
0x180032f86  mov     edi, eax
0x180032f88  test    eax, eax
0x180032f8a  jns     short loc_180032FE6
0x180032f8c  mov     rcx, [rsp+108h]; this
0x180032f94  mov     r9d, eax; char *
0x180032f97  lea     r8, aOnecoreuapEndu_170; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180032f9e  mov     edx, 0A6h; void *
0x180032fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032fa8  nop
0x180032fa9  lea     rcx, [rsp+108h+var_98]
0x180032fae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032fb3  nop
0x180032fb4  mov     rcx, [rsp+108h+pv]; pv
0x180032fb9  mov     [rsp+108h+pv], r12
0x180032fbe  test    rcx, rcx
0x180032fc1  jz      short loc_180032FCA
0x180032fc3  call    cs:__imp_CoTaskMemFree
0x180032fc9  nop
0x180032fca  lea     rcx, [rsp+108h+var_B8]
0x180032fcf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fd4  nop
0x180032fd5  lea     rcx, [rsp+108h+var_C0]
0x180032fda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032fdf  mov     eax, edi
0x180032fe1  jmp     loc_1800333D1
0x180032fe6  lea     r8, [rsp+108h+var_98]
0x180032feb  cmp     [rsp+108h+var_80], 7
0x180032ff4  cmova   r8, [rsp+108h+var_98]; int
0x180032ffa  mov     [rsp+108h+ppv], r14; unsigned __int16 *
0x180032fff  lea     r9, aMockinputfile; "MockInputFile"
0x180033006  mov     rdi, 0FFFFFFFF80000001h
0x18003300d  mov     rdx, rdi; int
0x180033010  lea     rcx, [rsp+108h+var_68]; int
0x180033018  call    ?GetString@SpRegUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG11@Z; SpRegUtil::GetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18003301d  nop
0x18003301e  mov     rdx, rax
0x180033021  lea     rcx, [rsp+108h+var_B0]
0x180033026  call    ??0swstring@Halsey@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Halsey::swstring::swstring(std::wstring const &)
0x18003302b  mov     rdx, [rbx]
0x18003302e  mov     rcx, [rsp+108h+var_A8]
0x180033033  test    rcx, rcx
0x180033036  jz      short loc_180033041
0x180033038  lock inc dword ptr [rcx+8]
0x18003303c  mov     rcx, [rsp+108h+var_A8]
0x180033041  mov     rax, [rsp+108h+var_B0]
0x180033046  mov     [rdx+230h], rax
0x18003304d  mov     rax, [rdx+238h]
0x180033054  mov     [rdx+238h], rcx
0x18003305b  test    rax, rax
  ... truncated ...
```
