# CActivationErrorPopup::CreateAndShowStoreSACDialog(ushort const *)

- ea: `0x1801647a4`
- end: `0x180164b44`
- name: `?CreateAndShowStoreSACDialog@CActivationErrorPopup@@AEAAJPEBG@Z`
- size: `928`
- prototype: `int(CActivationErrorPopup *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180163ad0`

## callees

- `0x180008acc`
- `0x180027ee4`
- `0x18004719c`
- `0x18013d330`
- `0x18013f785`
- `0x1801612c4`
- `0x180161350`
- `0x180161404`
- `0x180162d8c`
- `0x180162e3c`
- `0x180163090`
- `0x1801647a4`
- `0x180165d3c`
- `0x180166214`
- `0x1801676cc`
- `0x180168c14`
- `0x180169168`
- `0x18016af54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801649c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801649c5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1801649cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1801649cb`
- `SHDOCVW!__imp_ShowStoreAppRecommendation` at `0x1801649f5`
- `SHDOCVW!__imp_ShowStoreAppRecommendation` at `0x1801649f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180164851`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180164a13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180164a90`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180164851`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180164a13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x180164a90`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016485e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164a20`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164a9d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18016485e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164a20`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180164a9d`

## string_xrefs

- `0x180164ad1`: `SHOW_STORE_APP_RECOMMENDATION_FAILURE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CActivationErrorPopup::CreateAndShowStoreSACDialog(CActivationErrorPopup *this, WCHAR *a2)
{
  _QWORD *v4; // rax
  const WCHAR *v5; // r14
  __int64 v6; // rbx
  LPWSTR v7; // rax
  __int64 v8; // rax
  const char *v9; // r9
  __int64 result; // rax
  const wchar_t *v11; // r15
  int v12; // eax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rbx
  const unsigned __int16 *SACErrorCodeAsString; // rbx
  HWND ForegroundWindow; // rax
  int v17; // ebx
  __int64 v18; // r8
  __int64 v19; // rsi
  LPWSTR v20; // rax
  LPWSTR FileNameW; // rax
  __int64 v22; // r8
  __int64 v23; // rdi
  const WCHAR *v24; // rax
  const WCHAR *v25; // rbx
  __int64 v26; // [rsp+40h] [rbp-158h] BYREF
  int v27; // [rsp+48h] [rbp-150h] BYREF
  unsigned __int128 Buf1; // [rsp+50h] [rbp-148h] BYREF
  __int64 v29; // [rsp+60h] [rbp-138h]
  LPVOID ppv; // [rsp+70h] [rbp-128h] BYREF
  LPCWSTR v31; // [rsp+78h] [rbp-120h] BYREF
  unsigned __int16 *v32; // [rsp+80h] [rbp-118h] BYREF
  CActivationErrorPopup *v33; // [rsp+88h] [rbp-110h]
  unsigned __int16 v34[112]; // [rsp+90h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v33 = this;
  v31 = a2;
  v26 = 0;
  v4 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::ensure_data(&v26);
  tip2::details::shared_data<1,0,0>::start(*v4 + 8LL, &Buf1);
  try
  {
    v5 = &pszDefault;
    v32 = (unsigned __int16 *)&pszDefault;
    Buf1 = *(_OWORD *)(*((_QWORD *)this + 3) + 100LL);
    if ( ShouldShowStoreSACDialog((struct _GUID *)&Buf1, (const unsigned __int16 **)&v32) )
    {
      v11 = L"feedback-hub:?contextid=1271&newfeedback=true&feedbacktype=2";
      if ( a2 && **((_DWORD **)this + 3) != -2147020340 )
      {
        Buf1 = 0u;
        v29 = 0;
        if ( (int)MakeFileTokenFromPath(a2, &Buf1) >= 0 )
        {
          v12 = StringCchPrintfW(
                  v34,
                  0x6Bu,
                  L"%ws%ws",
                  L"feedback-hub:?contextid=1271&newfeedback=true&feedbacktype=2&files=",
                  (_QWORD)Buf1);
          v13 = v34;
          if ( v12 < 0 )
            v13 = L"feedback-hub:?contextid=1271&newfeedback=true&feedbacktype=2";
          v11 = v13;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&Buf1);
      }
      v14 = *((_QWORD *)this + 3);
      Buf1 = *(_OWORD *)(v14 + 100);
      if ( memcmp_0(&Buf1, qword_1803FFD50, 0x10u) )
        v5 = *(const WCHAR **)(v14 + 56);
      SACErrorCodeAsString = GetSACErrorCodeAsString(*(_DWORD *)v14);
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      CoCreateInstance(
        &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
        0,
        0x404u,
        &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
        &ppv);
      ForegroundWindow = GetForegroundWindow();
      v17 = ShowStoreAppRecommendation(ForegroundWindow, a2, L"SmartAppControl", SACErrorCodeAsString, v11, v5, ppv);
      v27 = v17;
      v19 = *((_QWORD *)this + 3);
      if ( v17 < 0 )
      {
        FileNameW = 0;
        if ( a2 )
        {
          if ( PathIsFileSpecW(a2) )
            FileNameW = a2;
          else
            FileNameW = PathFindFileNameW(a2);
        }
        *(_QWORD *)&Buf1 = FileNameW;
        ActivationErrorTelemetry::StoreSACDialogFailed<unsigned short const *,long const &,unsigned short const (&)[38],long &>(
          &Buf1,
          v19,
          v18,
          &v27);
        *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
                                 &v26,
                                 &Buf1)
                  + 280LL) = L"SHOW_STORE_APP_RECOMMENDATION_FAILURE";
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&Buf1);
        tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
        result = (unsigned int)v17;
      }
      else
      {
        v20 = 0;
        if ( a2 )
        {
          if ( PathIsFileSpecW(a2) )
            v20 = a2;
          else
            v20 = PathFindFileNameW(a2);
        }
        *(_QWORD *)&Buf1 = v20;
        ActivationErrorTelemetry::StoreSACDialogDisplayed<unsigned short const *,long const &>(&Buf1, v19);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
                                &v26,
                                &Buf1)
                 + 272LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&Buf1);
        tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
        result = 0;
      }
    }
    else
    {
      v27 = -2147467259;
      v6 = *((_QWORD *)this + 3);
      v7 = 0;
      if ( a2 )
      {
        if ( PathIsFileSpecW(a2) )
          v7 = a2;
        else
          v7 = PathFindFileNameW(a2);
      }
      *(_QWORD *)&Buf1 = v7;
      ActivationErrorTelemetry::StoreSACDialogFailed<unsigned short const *,long const &,unsigned short const * &,long>(
        &Buf1,
        v6,
        &v32,
        &v27);
      v8 = tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
             &v26,
             &Buf1);
      *(_QWORD *)(*(_QWORD *)v8 + 280LL) = v32;
      tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&Buf1);
      tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
      wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
      result = 2147500037LL;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1583,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\activationerrorpopup.cpp",
      v9);
    v27 = -2147467259;
    v23 = *((_QWORD *)v33 + 3);
    v24 = 0;
    v25 = v31;
    if ( v31 )
    {
      if ( PathIsFileSpecW(v31) )
        v24 = v25;
      else
        v24 = PathFindFileNameW(v25);
    }
    v31 = v24;
    ActivationErrorTelemetry::StoreSACDialogFailed<unsigned short const *,long const &,unsigned short const (&)[14],long>(
      &v31,
      v23,
      v22,
      &v27);
    *(_QWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(
                             &v26,
                             &v31)
              + 280LL) = L"UNKNOWN_ERROR";
    tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(&v31);
    tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(&v26);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(&v26);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x1801647a4  mov     [rsp+arg_10], rbx
0x1801647a9  mov     [rsp+arg_18], rsi
0x1801647ae  push    rdi
0x1801647af  push    r14
0x1801647b1  push    r15
0x1801647b3  sub     rsp, 180h
0x1801647ba  mov     rax, cs:__security_cookie
0x1801647c1  xor     rax, rsp
0x1801647c4  mov     [rsp+198h+var_28], rax
0x1801647cc  mov     rdi, rdx
0x1801647cf  mov     rsi, rcx
0x1801647d2  mov     [rsp+198h+var_110], rcx
0x1801647da  mov     [rsp+198h+var_120], rdx
0x1801647df  mov     [rsp+198h+var_158], 0
0x1801647e8  lea     rcx, [rsp+198h+var_158]
0x1801647ed  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::ensure_data(void)
0x1801647f2  mov     rcx, [rax]
0x1801647f5  add     rcx, 8
0x1801647f9  lea     rdx, [rsp+198h+Buf1]
0x1801647fe  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180164803  nop
0x180164804  lea     r14, pszDefault
0x18016480b  mov     [rsp+198h+var_118], r14
0x180164813  mov     rax, [rsi+18h]
0x180164817  movups  xmm0, xmmword ptr [rax+64h]
0x18016481b  movdqu  [rsp+198h+Buf1], xmm0
0x180164821  lea     rdx, [rsp+198h+var_118]; unsigned __int16 **
0x180164829  lea     rcx, [rsp+198h+Buf1]; struct _GUID
0x18016482e  call    ?ShouldShowStoreSACDialog@@YA_NU_GUID@@PEAPEBG@Z; ShouldShowStoreSACDialog(_GUID,ushort const * *)
0x180164833  test    al, al
0x180164835  jnz     loc_1801648D2
0x18016483b  mov     [rsp+198h+var_150], 80004005h
0x180164843  mov     rbx, [rsi+18h]
0x180164847  xor     eax, eax
0x180164849  test    rdi, rdi
0x18016484c  jz      short loc_180164869
0x18016484e  mov     rcx, rdi; pszPath
0x180164851  call    cs:__imp_PathIsFileSpecW
0x180164857  test    eax, eax
0x180164859  jnz     short loc_180164866
0x18016485b  mov     rcx, rdi; pszPath
0x18016485e  call    cs:__imp_PathFindFileNameW
0x180164864  jmp     short loc_180164869
0x180164866  mov     rax, rdi
0x180164869  mov     qword ptr [rsp+198h+Buf1], rax
0x18016486e  lea     r9, [rsp+198h+var_150]
0x180164873  lea     r8, [rsp+198h+var_118]
0x18016487b  mov     rdx, rbx
0x18016487e  lea     rcx, [rsp+198h+Buf1]
0x180164883  call    ??$StoreSACDialogFailed@PEBGAEBJAEAPEBGJ@ActivationErrorTelemetry@@SAX$$QEAPEBGAEBJAEAPEBG$$QEAJ@Z; ActivationErrorTelemetry::StoreSACDialogFailed<ushort const *,long const &,ushort const * &,long>(ushort const * &&,long const &,ushort const * &,long &&)
0x180164888  lea     rdx, [rsp+198h+Buf1]
0x18016488d  lea     rcx, [rsp+198h+var_158]
0x180164892  call    ??C?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(void)
0x180164897  mov     rdx, [rax]
0x18016489a  mov     rcx, [rsp+198h+var_118]
0x1801648a2  mov     [rdx+118h], rcx
0x1801648a9  lea     rcx, [rsp+198h+Buf1]
0x1801648ae  call    ??1?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(void)
0x1801648b3  lea     rcx, [rsp+198h+var_158]
0x1801648b8  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x1801648bd  nop
0x1801648be  lea     rcx, [rsp+198h+var_158]
0x1801648c3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x1801648c8  mov     eax, 80004005h
0x1801648cd  jmp     loc_180164B1B
0x1801648d2  lea     r15, aFeedbackHubCon; "feedback-hub:?contextid=1271&newfeedbac"...
0x1801648d9  test    rdi, rdi
0x1801648dc  jz      short loc_18016495B
0x1801648de  mov     rax, [rsi+18h]
0x1801648e2  cmp     dword ptr [rax], 800711CCh
0x1801648e8  jz      short loc_18016495B
0x1801648ea  mov     qword ptr [rsp+198h+Buf1], 0
0x1801648f3  mov     qword ptr [rsp+198h+Buf1+8], 0
0x1801648fc  mov     [rsp+198h+var_138], 0
0x180164905  lea     rdx, [rsp+198h+Buf1]
0x18016490a  mov     rcx, rdi
0x18016490d  call    ?MakeFileTokenFromPath@@YAJPEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; MakeFileTokenFromPath(ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180164912  test    eax, eax
0x180164914  js      short loc_180164951
0x180164916  mov     rax, qword ptr [rsp+198h+Buf1]
0x18016491b  mov     [rsp+198h+ppv], rax
0x180164920  lea     r9, aFeedbackHubCon_0; "feedback-hub:?contextid=1271&newfeedbac"...
0x180164927  lea     r8, aWsWs; "%ws%ws"
0x18016492e  mov     edx, 6Bh ; 'k'; unsigned __int64
0x180164933  lea     rcx, [rsp+198h+var_108]; unsigned __int16 *
0x18016493b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180164940  lea     rcx, [rsp+198h+var_108]
0x180164948  test    eax, eax
0x18016494a  cmovs   rcx, r15
0x18016494e  mov     r15, rcx
0x180164951  lea     rcx, [rsp+198h+Buf1]
0x180164956  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18016495b  mov     rbx, [rsi+18h]
0x18016495f  movups  xmm0, xmmword ptr [rbx+64h]
0x180164963  movdqu  [rsp+198h+Buf1], xmm0
0x180164969  mov     r8d, 10h; Size
0x18016496f  lea     rdx, qword_1803FFD50; Buf2
0x180164976  lea     rcx, [rsp+198h+Buf1]; Buf1
0x18016497b  call    memcmp_0
0x180164980  test    eax, eax
0x180164982  jz      short loc_180164988
0x180164984  mov     r14, [rbx+38h]
0x180164988  mov     ecx, [rbx]; int
0x18016498a  call    ?GetSACErrorCodeAsString@@YAPEBGJ@Z; GetSACErrorCodeAsString(long)
0x18016498f  mov     rbx, rax
0x180164992  mov     [rsp+198h+var_128], 0
0x18016499b  lea     rcx, [rsp+198h+var_128]
0x1801649a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801649a5  lea     rax, [rsp+198h+var_128]
0x1801649aa  mov     [rsp+198h+ppv], rax; ppv
0x1801649af  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x1801649b6  xor     edx, edx; pUnkOuter
0x1801649b8  mov     r8d, 404h; dwClsContext
0x1801649be  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x1801649c5  call    cs:__imp_CoCreateInstance
0x1801649cb  call    cs:__imp_GetForegroundWindow
0x1801649d1  mov     rcx, [rsp+198h+var_128]
0x1801649d6  mov     [rsp+198h+var_168], rcx
0x1801649db  mov     [rsp+198h+var_170], r14
0x1801649e0  mov     [rsp+198h+ppv], r15
0x1801649e5  mov     r9, rbx
0x1801649e8  lea     r8, aSmartappcontro; "SmartAppControl"
0x1801649ef  mov     rdx, rdi
0x1801649f2  mov     rcx, rax
0x1801649f5  call    cs:__imp_ShowStoreAppRecommendation
0x1801649fb  mov     ebx, eax
0x1801649fd  mov     [rsp+198h+var_150], eax
0x180164a01  mov     rsi, [rsi+18h]
0x180164a05  test    eax, eax
0x180164a07  js      short loc_180164A86
0x180164a09  xor     eax, eax
0x180164a0b  test    rdi, rdi
0x180164a0e  jz      short loc_180164A2B
0x180164a10  mov     rcx, rdi; pszPath
0x180164a13  call    cs:__imp_PathIsFileSpecW
0x180164a19  test    eax, eax
0x180164a1b  jnz     short loc_180164A28
0x180164a1d  mov     rcx, rdi; pszPath
0x180164a20  call    cs:__imp_PathFindFileNameW
0x180164a26  jmp     short loc_180164A2B
0x180164a28  mov     rax, rdi
0x180164a2b  mov     qword ptr [rsp+198h+Buf1], rax
0x180164a30  mov     rdx, rsi
0x180164a33  lea     rcx, [rsp+198h+Buf1]
0x180164a38  call    ??$StoreSACDialogDisplayed@PEBGAEBJ@ActivationErrorTelemetry@@SAX$$QEAPEBGAEBJ@Z; ActivationErrorTelemetry::StoreSACDialogDisplayed<ushort const *,long const &>(ushort const * &&,long const &)
0x180164a3d  lea     rdx, [rsp+198h+Buf1]
0x180164a42  lea     rcx, [rsp+198h+var_158]
0x180164a47  call    ??C?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(void)
0x180164a4c  mov     rcx, [rax]
0x180164a4f  mov     byte ptr [rcx+110h], 1
0x180164a56  lea     rcx, [rsp+198h+Buf1]
0x180164a5b  call    ??1?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(void)
0x180164a60  lea     rcx, [rsp+198h+var_158]
0x180164a65  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x180164a6a  lea     rcx, [rsp+198h+var_128]
0x180164a6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180164a74  nop
0x180164a75  lea     rcx, [rsp+198h+var_158]
0x180164a7a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x180164a7f  xor     eax, eax
0x180164a81  jmp     loc_180164B1B
0x180164a86  xor     eax, eax
0x180164a88  test    rdi, rdi
0x180164a8b  jz      short loc_180164AA8
0x180164a8d  mov     rcx, rdi; pszPath
0x180164a90  call    cs:__imp_PathIsFileSpecW
0x180164a96  test    eax, eax
0x180164a98  jnz     short loc_180164AA5
0x180164a9a  mov     rcx, rdi; pszPath
0x180164a9d  call    cs:__imp_PathFindFileNameW
0x180164aa3  jmp     short loc_180164AA8
0x180164aa5  mov     rax, rdi
0x180164aa8  mov     qword ptr [rsp+198h+Buf1], rax
0x180164aad  lea     r9, [rsp+198h+var_150]
0x180164ab2  mov     rdx, rsi
0x180164ab5  lea     rcx, [rsp+198h+Buf1]
0x180164aba  call    ??$StoreSACDialogFailed@PEBGAEBJAEAY0CG@$$CBGAEAJ@ActivationErrorTelemetry@@SAX$$QEAPEBGAEBJAEAY0CG@$$CBGAEAJ@Z; ActivationErrorTelemetry::StoreSACDialogFailed<ushort const *,long const &,ushort const (&)[38],long &>(ushort const * &&,long const &,ushort const (&)[38],long &)
0x180164abf  lea     rdx, [rsp+198h+Buf1]
0x180164ac4  lea     rcx, [rsp+198h+var_158]
0x180164ac9  call    ??C?$tip_test@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::operator->(void)
0x180164ace  mov     rcx, [rax]
0x180164ad1  lea     rax, aShowStoreAppRe; "SHOW_STORE_APP_RECOMMENDATION_FAILURE"
0x180164ad8  mov     [rcx+118h], rax
0x180164adf  lea     rcx, [rsp+198h+Buf1]
0x180164ae4  call    ??1?$test_data_control@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>>(void)
0x180164ae9  lea     rcx, [rsp+198h+var_158]
0x180164aee  call    ?complete@?$tip_test@V?$merged_data@U_tip_ShareSheetResizeTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_ShareSheetResizeTest,_tip_ShareSheetResizeTest>>::complete(void)
0x180164af3  lea     rcx, [rsp+198h+var_128]
0x180164af8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180164afd  nop
0x180164afe  lea     rcx, [rsp+198h+var_158]
0x180164b03  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x180164b08  mov     eax, ebx
0x180164b0a  jmp     short loc_180164B1B
0x180164b0c  lea     rcx, [rsp+198h+var_158]
0x180164b11  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ShowStoreSACDialogTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_ShowStoreSACDialogTest,TipTests::_tip_ShowStoreSACDialogTest>,wil::err_returncode_policy>(void)
0x180164b16  mov     eax, 80004005h
0x180164b1b  mov     rcx, [rsp+198h+var_28]
0x180164b23  xor     rcx, rsp; StackCookie
0x180164b26  call    __security_check_cookie
0x180164b2b  lea     r11, [rsp+198h+var_18]
0x180164b33  mov     rbx, [r11+30h]
0x180164b37  mov     rsi, [r11+38h]
0x180164b3b  mov     rsp, r11
0x180164b3e  pop     r15
0x180164b40  pop     r14
0x180164b42  pop     rdi
0x180164b43  retn
```
