# _lambda_edc2c2a86480002e8658e36f447725ab_::operator()(Windows::Internal::AsyncStage,long,IPickerInitializationInfo *,CStorageItemVectorViewResult &)

- ea: `0x18000f6d8`
- end: `0x18000fb23`
- name: `??R_lambda_edc2c2a86480002e8658e36f447725ab_@@QEAAJW4AsyncStage@Internal@Windows@@JPEAUIPickerInitializationInfo@@AEAVCStorageItemVectorViewResult@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(__int64 *, int, int, __int64, CPickerResultWithMarshaledCallbacks *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800570d0`

## callees

- `0x180003d24`
- `0x180008134`
- `0x18000f6d8`
- `0x18000fb2c`
- `0x18000fcc0`
- `0x1800181bc`
- `0x1800205d8`
- `0x180021670`
- `0x180024fbc`
- `0x180025de8`
- `0x18002b1b0`
- `0x1800462d4`
- `0x1800464d4`
- `0x18004b9b0`
- `0x18004e404`
- `0x18004f2c8`
- `0x180053a24`
- `0x180053a6c`
- `0x18005be74`
- `0x18005c1b4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f95d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f97b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f95d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f97b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f985`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18000f7da`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18000f7da`

## pseudocode

```c
__int64 __fastcall _lambda_edc2c2a86480002e8658e36f447725ab_::operator()(
        __int64 *a1,
        int a2,
        int a3,
        __int64 a4,
        CPickerResultWithMarshaledCallbacks *a5)
{
  int CallerOwnerWindow; // ebx
  __int64 *v9; // r15
  __int64 v10; // rcx
  bool v11; // zf
  HWND v12; // rsi
  __int64 v13; // rbx
  int v14; // r15d
  __int64 v15; // rax
  int v16; // r15d
  __int64 v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  CFilePickerInvoker *v23; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE *v24; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID *v25; // [rsp+38h] [rbp-C8h]
  __int64 v26; // [rsp+40h] [rbp-C0h]
  __int128 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  __int128 *v32; // [rsp+90h] [rbp-70h]
  char v33; // [rsp+98h] [rbp-68h]
  LPVOID pv[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v35[2]; // [rsp+B0h] [rbp-50h]
  LPVOID v36[2]; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  char v38; // [rsp+D8h] [rbp-28h]
  _BYTE v39[192]; // [rsp+E0h] [rbp-20h] BYREF

  CallerOwnerWindow = a3;
  if ( a2 == 1 )
  {
    if ( a3 < 0 )
      goto LABEL_48;
    v9 = a1 + 6;
    v10 = a1[40];
    v11 = *(_DWORD *)v10 == 1;
    BYTE8(v28) = 0;
    if ( v11 )
    {
      LODWORD(v27) = *(_DWORD *)(v10 + 40);
      *((_QWORD *)&v27 + 1) = *(_QWORD *)(v10 + 48);
      if ( *(_BYTE *)(v10 + 64) )
        wil::details::StoredCallContextInfo::AssignMessage(
          (wil::details::StoredCallContextInfo *)&v27,
          *(const unsigned __int16 **)(v10 + 56));
      else
        *(_QWORD *)&v28 = *(_QWORD *)(v10 + 56);
      *(_QWORD *)&v29 = 0;
      *((_QWORD *)&v29 + 1) = v9;
      v30 = 0;
      v31 = 0;
      v32 = &v27;
      v33 = 0;
      wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)&v29);
    }
    else
    {
      v27 = 0;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
    }
    v12 = (HWND)a1[1];
    if ( IsWindow(v12) || (CallerOwnerWindow = -2147023496, (a1[5] & 2) != 0) && v12 )
    {
      CPickerParameters::CPickerParameters((CPickerParameters *)v39);
      CallerOwnerWindow = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a4 + 24LL))(a4, v39);
      if ( CallerOwnerWindow >= 0 )
      {
        v38 = 0;
        *(_OWORD *)pv = 0;
        *(_OWORD *)v35 = 0;
        *(_OWORD *)v36 = 0;
        v37 = 0;
        CallerOwnerWindow = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a4 + 32LL))(a4, pv);
        if ( CallerOwnerWindow >= 0 )
        {
          v22 = 0;
          CallerOwnerWindow = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a4 + 40LL))(a4, &v22);
          if ( CallerOwnerWindow >= 0 )
          {
            v23 = 0;
            v13 = *a1;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
            v24 = v39;
            v25 = pv;
            LODWORD(v26) = v22;
            CallerOwnerWindow = CAsyncForwarder<CFilePickerInvoker>::BeginInvoke<_lambda_4089e3f97b351a4b7870fb7b10a59a5a_>(
                                  v13,
                                  &v24,
                                  &v23);
            if ( CallerOwnerWindow >= 0 )
            {
              v24 = 0;
              LODWORD(v25) = 0;
              v26 = 0;
              CallerOwnerWindow = CFilePickerInvoker::ShowFilePicker(v23, v12, (struct PICKER_RESULTS *)&v24);
              if ( CallerOwnerWindow >= 0 )
              {
                CallerOwnerWindow = 0;
                if ( v24 )
                {
                  CallerOwnerWindow = CMarshaledInterface::Marshal((char *)a5 + 48, &IID_IShellItemArray, v24, 1);
                  if ( CallerOwnerWindow >= 0 )
                    CallerOwnerWindow = CPickerResultWithMarshaledCallbacks::MarshalCallbacks(
                                          a5,
                                          (const struct PICKER_RESULTS *)&v24);
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(*a1 + 40);
              CPickerResults::~CPickerResults((CPickerResults *)&v24);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
          }
        }
        CoTaskMemFree(pv[0]);
        CoTaskMemFree(pv[1]);
        CoTaskMemFree(v35[0]);
        CoTaskMemFree(v35[1]);
        CoTaskMemFree(v36[0]);
        CoTaskMemFree(v36[1]);
      }
      CPickerParameters::Clear((CPickerParameters *)v39);
      if ( CallerOwnerWindow >= 0 )
      {
        v22 = 0;
        if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)a5 + 56LL))(*(_QWORD *)a5, &v22) >= 0 && v22 == 2 )
          CallerOwnerWindow = -2147023673;
      }
    }
    wil::ActivityBase<PickerTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v9,
      (unsigned int)CallerOwnerWindow);
    if ( v31 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v29);
    wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)&v27);
  }
  else if ( a2 == 2 )
  {
    CallerOwnerWindow = CAsyncForwarder<CFilePickerInvoker>::Cancel(*a1);
  }
  if ( CallerOwnerWindow >= 0 && !a2 )
  {
    v14 = *((_DWORD *)a1 + 4);
    v23 = (CFilePickerInvoker *)(a1 + 4);
    v15 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v23);
    CallerOwnerWindow = Microsoft::WRL::AsWeak<Windows::ApplicationModel::Core::ICoreApplicationViewInternal>(
                          *(_QWORD *)a5,
                          v15);
    if ( CallerOwnerWindow >= 0 )
    {
      v16 = v14 & 2;
      v17 = a1[3];
      if ( v17 )
      {
        v18 = a1[4];
        if ( *(_QWORD *)(v17 + 88) != v18 )
        {
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
          v19 = *(_QWORD *)(v17 + 88);
          *(_QWORD *)(v17 + 88) = v18;
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
      }
      if ( a1[1]
        || (CallerOwnerWindow = Windows::Internal::AsyncWindowOperation::s_GetCallerOwnerWindow(
                                  (a1[2] & 8) != 0,
                                  (HWND *)a1 + 1),
            CallerOwnerWindow >= 0) )
      {
        if ( !v16 )
        {
          CallerOwnerWindow = Windows::Internal::AsyncWindowOperation::EnsureWindowData((Windows::Internal::AsyncWindowOperation *)(a1 + 1));
          if ( CallerOwnerWindow >= 0 )
            CallerOwnerWindow = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1[3] + 8) + 24LL))(a1[3] + 8);
        }
      }
      else if ( v16 )
      {
        CallerOwnerWindow = 0;
      }
    }
  }
LABEL_48:
  v20 = a1[3];
  if ( v20 && (CallerOwnerWindow < 0 || a2 == 1) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v20 + 8) + 32LL))(v20 + 8);
  return (unsigned int)CallerOwnerWindow;
}

```

## disassembly

```asm
0x18000f6d8  mov     [rsp-8+arg_8], rbx
0x18000f6dd  push    rbp
0x18000f6de  push    rsi
0x18000f6df  push    rdi
0x18000f6e0  push    r12
0x18000f6e2  push    r13
0x18000f6e4  push    r14
0x18000f6e6  push    r15
0x18000f6e8  lea     rbp, [rsp-0B0h]
0x18000f6f0  sub     rsp, 1B0h
0x18000f6f7  mov     rax, cs:__security_cookie
0x18000f6fe  xor     rax, rsp
0x18000f701  mov     [rbp+0E0h+var_40], rax
0x18000f708  mov     r14, r9
0x18000f70b  mov     ebx, r8d
0x18000f70e  mov     r13d, edx
0x18000f711  mov     rdi, rcx
0x18000f714  mov     r12, [rbp+0E0h+arg_20]
0x18000f71b  cmp     edx, 1
0x18000f71e  jnz     loc_18000F9EF
0x18000f724  test    ebx, ebx
0x18000f726  js      loc_18000FAD4
0x18000f72c  lea     r15, [rcx+30h]
0x18000f730  mov     rcx, [r15+110h]
0x18000f737  cmp     [rcx], edx
0x18000f739  mov     byte ptr [rsp+1E0h+var_180+8], 0
0x18000f73e  jnz     short loc_18000F7A5
0x18000f740  mov     eax, [rcx+28h]
0x18000f743  mov     dword ptr [rsp+1E0h+var_190], eax
0x18000f747  mov     rax, [rcx+30h]
0x18000f74b  mov     qword ptr [rsp+1E0h+var_190+8], rax
0x18000f750  mov     rax, [rcx+38h]
0x18000f754  cmp     byte ptr [rcx+40h], 0
0x18000f758  jz      short loc_18000F769
0x18000f75a  mov     rdx, rax; unsigned __int16 *
0x18000f75d  lea     rcx, [rsp+1E0h+var_190]; this
0x18000f762  call    ?AssignMessage@StoredCallContextInfo@details@wil@@AEAAXPEBG@Z; wil::details::StoredCallContextInfo::AssignMessage(ushort const *)
0x18000f767  jmp     short loc_18000F76E
0x18000f769  mov     qword ptr [rsp+1E0h+var_180], rax
0x18000f76e  mov     qword ptr [rsp+1E0h+var_170], 0
0x18000f777  mov     qword ptr [rsp+1E0h+var_170+8], r15
0x18000f77c  mov     [rbp+0E0h+var_160], 0
0x18000f784  mov     [rbp+0E0h+var_158], 0
0x18000f78b  lea     rax, [rsp+1E0h+var_190]
0x18000f790  mov     [rbp+0E0h+var_150], rax
0x18000f794  mov     [rbp+0E0h+var_148], 0
0x18000f798  lea     rcx, [rsp+1E0h+var_170]; this
0x18000f79d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000f7a2  nop
0x18000f7a3  jmp     short loc_18000F7D3
0x18000f7a5  xorps   xmm0, xmm0
0x18000f7a8  movups  [rsp+1E0h+var_190], xmm0
0x18000f7ad  movups  [rsp+1E0h+var_180], xmm0
0x18000f7b2  movdqa  [rsp+1E0h+var_170], xmm0
0x18000f7b8  mov     [rbp+0E0h+var_160], 0
0x18000f7c0  mov     [rbp+0E0h+var_158], 0
0x18000f7c7  mov     [rbp+0E0h+var_150], 0
0x18000f7cf  mov     [rbp+0E0h+var_148], 0
0x18000f7d3  mov     rsi, [rdi+8]
0x18000f7d7  mov     rcx, rsi; hWnd
0x18000f7da  call    cs:__imp_IsWindow
0x18000f7e0  test    eax, eax
0x18000f7e2  jnz     short loc_18000F7FC
0x18000f7e4  mov     ebx, 80070578h
0x18000f7e9  test    byte ptr [rdi+28h], 2
0x18000f7ed  jz      loc_18000F9C7
0x18000f7f3  test    rsi, rsi
0x18000f7f6  jz      loc_18000F9C7
0x18000f7fc  lea     rcx, [rbp+0E0h+var_100]; this
0x18000f800  call    ??0CPickerParameters@@QEAA@XZ; CPickerParameters::CPickerParameters(void)
0x18000f805  nop
0x18000f806  mov     rax, [r14]
0x18000f809  lea     rdx, [rbp+0E0h+var_100]
0x18000f80d  mov     rcx, r14
0x18000f810  mov     rax, [rax+18h]
0x18000f814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f819  mov     ebx, eax
0x18000f81b  test    eax, eax
0x18000f81d  js      loc_18000F98C
0x18000f823  mov     [rbp+0E0h+var_108], 0
0x18000f827  xorps   xmm0, xmm0
0x18000f82a  movdqa  xmmword ptr [rbp+0E0h+pv], xmm0
0x18000f82f  xorps   xmm1, xmm1
0x18000f832  movdqa  xmmword ptr [rbp+0E0h+var_130], xmm1
0x18000f837  movdqa  xmmword ptr [rbp+0E0h+var_120], xmm0
0x18000f83c  mov     [rbp+0E0h+var_110], 0
0x18000f844  mov     rax, [r14]
0x18000f847  lea     rdx, [rbp+0E0h+pv]
0x18000f84b  mov     rcx, r14
0x18000f84e  mov     rax, [rax+20h]
0x18000f852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f857  mov     ebx, eax
0x18000f859  test    eax, eax
0x18000f85b  js      loc_18000F94F
0x18000f861  mov     [rsp+1E0h+var_1C0], 0
0x18000f869  mov     rax, [r14]
0x18000f86c  lea     rdx, [rsp+1E0h+var_1C0]
0x18000f871  mov     rcx, r14
0x18000f874  mov     rax, [rax+28h]
0x18000f878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87d  mov     ebx, eax
0x18000f87f  xor     r14d, r14d
0x18000f882  test    eax, eax
0x18000f884  js      loc_18000F94F
0x18000f88a  mov     [rsp+1E0h+var_1B8], r14
0x18000f88f  mov     rbx, [rdi]
0x18000f892  lea     rcx, [rsp+1E0h+var_1B8]
0x18000f897  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f89c  lea     rax, [rbp+0E0h+var_100]
0x18000f8a0  mov     [rsp+1E0h+var_1B0], rax
0x18000f8a5  lea     rax, [rbp+0E0h+pv]
0x18000f8a9  mov     [rsp+1E0h+var_1A8], rax
0x18000f8ae  mov     eax, [rsp+1E0h+var_1C0]
0x18000f8b2  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x18000f8b6  lea     r8, [rsp+1E0h+var_1B8]
0x18000f8bb  lea     rdx, [rsp+1E0h+var_1B0]
0x18000f8c0  mov     rcx, rbx
0x18000f8c3  call    ??$BeginInvoke@V_lambda_4089e3f97b351a4b7870fb7b10a59a5a_@@@?$CAsyncForwarder@VCFilePickerInvoker@@@@QEAAJ$$QEAV_lambda_4089e3f97b351a4b7870fb7b10a59a5a_@@PEAPEAVCFilePickerInvoker@@@Z; CAsyncForwarder<CFilePickerInvoker>::BeginInvoke<_lambda_4089e3f97b351a4b7870fb7b10a59a5a_>(_lambda_4089e3f97b351a4b7870fb7b10a59a5a_ &&,CFilePickerInvoker * *)
0x18000f8c8  mov     ebx, eax
0x18000f8ca  test    eax, eax
0x18000f8cc  js      short loc_18000F944
0x18000f8ce  mov     [rsp+1E0h+var_1B0], r14
0x18000f8d3  mov     dword ptr [rsp+1E0h+var_1A8], r14d
0x18000f8d8  mov     [rsp+1E0h+var_1A0], r14
0x18000f8dd  lea     r8, [rsp+1E0h+var_1B0]; struct PICKER_RESULTS *
0x18000f8e2  mov     rdx, rsi; HWND
0x18000f8e5  mov     rcx, [rsp+1E0h+var_1B8]; this
0x18000f8ea  call    ?ShowFilePicker@CFilePickerInvoker@@QEAAJPEAUHWND__@@PEAUPICKER_RESULTS@@@Z; CFilePickerInvoker::ShowFilePicker(HWND__ *,PICKER_RESULTS *)
0x18000f8ef  mov     ebx, eax
0x18000f8f1  test    eax, eax
0x18000f8f3  js      short loc_18000F92C
0x18000f8f5  mov     ebx, r14d
0x18000f8f8  mov     r8, [rsp+1E0h+var_1B0]
0x18000f8fd  test    r8, r8
0x18000f900  jz      short loc_18000F92C
0x18000f902  lea     rcx, [r12+30h]
0x18000f907  lea     r9d, [r14+1]
0x18000f90b  lea     rdx, IID_IShellItemArray
0x18000f912  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x18000f917  mov     ebx, eax
0x18000f919  test    eax, eax
0x18000f91b  js      short loc_18000F92C
0x18000f91d  lea     rdx, [rsp+1E0h+var_1B0]; struct PICKER_RESULTS *
0x18000f922  mov     rcx, r12; this
0x18000f925  call    ?MarshalCallbacks@CPickerResultWithMarshaledCallbacks@@IEAAJAEBUPICKER_RESULTS@@@Z; CPickerResultWithMarshaledCallbacks::MarshalCallbacks(PICKER_RESULTS const &)
0x18000f92a  mov     ebx, eax
0x18000f92c  mov     rcx, [rdi]
0x18000f92f  add     rcx, 28h ; '('
0x18000f933  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f938  nop
0x18000f939  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18000f93e  call    ??1CPickerResults@@QEAA@XZ; CPickerResults::~CPickerResults(void)
0x18000f943  nop
0x18000f944  lea     rcx, [rsp+1E0h+var_1B8]
0x18000f949  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000f94e  nop
0x18000f94f  mov     rcx, [rbp+0E0h+pv]; pv
0x18000f953  call    cs:__imp_CoTaskMemFree
0x18000f959  mov     rcx, [rbp+0E0h+pv+8]; pv
0x18000f95d  call    cs:__imp_CoTaskMemFree
0x18000f963  mov     rcx, [rbp+0E0h+var_130]; pv
0x18000f967  call    cs:__imp_CoTaskMemFree
0x18000f96d  mov     rcx, [rbp+0E0h+var_130+8]; pv
0x18000f971  call    cs:__imp_CoTaskMemFree
0x18000f977  mov     rcx, [rbp+0E0h+var_120]; pv
0x18000f97b  call    cs:__imp_CoTaskMemFree
0x18000f981  mov     rcx, [rbp+0E0h+var_120+8]; pv
0x18000f985  call    cs:__imp_CoTaskMemFree
0x18000f98b  nop
0x18000f98c  lea     rcx, [rbp+0E0h+var_100]; this
0x18000f990  call    ?Clear@CPickerParameters@@QEAAXXZ; CPickerParameters::Clear(void)
0x18000f995  nop
0x18000f996  test    ebx, ebx
0x18000f998  js      short loc_18000F9C7
0x18000f99a  mov     [rsp+1E0h+var_1C0], 0
0x18000f9a2  mov     rcx, [r12]
0x18000f9a6  mov     rax, [rcx]
0x18000f9a9  lea     rdx, [rsp+1E0h+var_1C0]
0x18000f9ae  mov     rax, [rax+38h]
0x18000f9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b7  test    eax, eax
0x18000f9b9  js      short loc_18000F9C7
0x18000f9bb  cmp     [rsp+1E0h+var_1C0], 2
0x18000f9c0  jnz     short loc_18000F9C7
0x18000f9c2  mov     ebx, 800704C7h
0x18000f9c7  mov     edx, ebx
0x18000f9c9  mov     rcx, r15
0x18000f9cc  call    ?Stop@?$ActivityBase@VPickerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PickerTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000f9d1  nop
0x18000f9d2  cmp     [rbp+0E0h+var_158], 0
0x18000f9d6  jz      short loc_18000F9E3
0x18000f9d8  lea     rcx, [rsp+1E0h+var_170]; this
0x18000f9dd  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000f9e2  nop
0x18000f9e3  lea     rcx, [rsp+1E0h+var_190]; this
0x18000f9e8  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x18000f9ed  jmp     short loc_18000F9FF
0x18000f9ef  cmp     r13d, 2
0x18000f9f3  jnz     short loc_18000F9FF
0x18000f9f5  mov     rcx, [rcx]
0x18000f9f8  call    ?Cancel@?$CAsyncForwarder@VCFilePickerInvoker@@@@QEAAJXZ; CAsyncForwarder<CFilePickerInvoker>::Cancel(void)
0x18000f9fd  mov     ebx, eax
0x18000f9ff  test    ebx, ebx
0x18000fa01  js      loc_18000FAD4
0x18000fa07  test    r13d, r13d
0x18000fa0a  jnz     loc_18000FAD4
0x18000fa10  mov     r15d, [rdi+10h]
0x18000fa14  lea     rsi, [rdi+20h]
0x18000fa18  mov     [rsp+1E0h+var_1B8], rsi
0x18000fa1d  lea     rcx, [rsp+1E0h+var_1B8]
0x18000fa22  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18000fa27  mov     rdx, rax
0x18000fa2a  mov     rcx, [r12]
0x18000fa2e  call    ??$AsWeak@UICoreApplicationViewInternal@Core@ApplicationModel@Windows@@@WRL@Microsoft@@YAJPEAUICoreApplicationViewInternal@Core@ApplicationModel@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::ApplicationModel::Core::ICoreApplicationViewInternal>(Windows::ApplicationModel::Core::ICoreApplicationViewInternal *,Microsoft::WRL::WeakRef *)
0x18000fa33  mov     ebx, eax
0x18000fa35  test    eax, eax
0x18000fa37  js      loc_18000FAD4
0x18000fa3d  and     r15d, 2
0x18000fa41  mov     r14, [rdi+18h]
0x18000fa45  test    r14, r14
0x18000fa48  jz      short loc_18000FA82
0x18000fa4a  mov     rsi, [rsi]
0x18000fa4d  cmp     [r14+58h], rsi
0x18000fa51  jz      short loc_18000FA82
0x18000fa53  test    rsi, rsi
0x18000fa56  jz      short loc_18000FA68
0x18000fa58  mov     rax, [rsi]
0x18000fa5b  mov     rcx, rsi
0x18000fa5e  mov     rax, [rax+8]
0x18000fa62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa67  nop
0x18000fa68  mov     rcx, [r14+58h]
0x18000fa6c  mov     [r14+58h], rsi
0x18000fa70  test    rcx, rcx
0x18000fa73  jz      short loc_18000FA82
0x18000fa75  mov     rax, [rcx]
0x18000fa78  mov     rax, [rax+10h]
0x18000fa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa81  nop
0x18000fa82  cmp     qword ptr [rdi+8], 0
0x18000fa87  jnz     short loc_18000FAAA
0x18000fa89  mov     ecx, [rdi+10h]
0x18000fa8c  shr     ecx, 3
0x18000fa8f  and     cl, 1; bool
0x18000fa92  lea     rdx, [rdi+8]; HWND *
0x18000fa96  call    ?s_GetCallerOwnerWindow@AsyncWindowOperation@Internal@Windows@@CAJ_NPEAPEAUHWND__@@@Z; Windows::Internal::AsyncWindowOperation::s_GetCallerOwnerWindow(bool,HWND__ * *)
0x18000fa9b  mov     ebx, eax
0x18000fa9d  test    eax, eax
0x18000fa9f  jns     short loc_18000FAAA
0x18000faa1  test    r15d, r15d
0x18000faa4  jz      short loc_18000FAD4
0x18000faa6  xor     ebx, ebx
0x18000faa8  jmp     short loc_18000FAD4
0x18000faaa  test    r15d, r15d
0x18000faad  jnz     short loc_18000FAD4
0x18000faaf  lea     rcx, [rdi+8]; this
0x18000fab3  call    ?EnsureWindowData@AsyncWindowOperation@Internal@Windows@@AEAAJXZ; Windows::Internal::AsyncWindowOperation::EnsureWindowData(void)
0x18000fab8  mov     ebx, eax
0x18000faba  test    eax, eax
0x18000fabc  js      short loc_18000FAD4
0x18000fabe  mov     rcx, [rdi+18h]
0x18000fac2  add     rcx, 8
0x18000fac6  mov     rax, [rcx]
0x18000fac9  mov     rax, [rax+18h]
0x18000facd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad2  mov     ebx, eax
0x18000fad4  mov     rcx, [rdi+18h]
0x18000fad8  test    rcx, rcx
0x18000fadb  jz      short loc_18000FAF7
0x18000fadd  test    ebx, ebx
0x18000fadf  js      short loc_18000FAE7
0x18000fae1  cmp     r13d, 1
0x18000fae5  jnz     short loc_18000FAF7
0x18000fae7  add     rcx, 8
0x18000faeb  mov     rax, [rcx]
0x18000faee  mov     rax, [rax+20h]
0x18000faf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faf7  mov     eax, ebx
0x18000faf9  mov     rcx, [rbp+0E0h+var_40]
0x18000fb00  xor     rcx, rsp; StackCookie
0x18000fb03  call    __security_check_cookie
0x18000fb08  mov     rbx, [rsp+1E0h+arg_8]
0x18000fb10  add     rsp, 1B0h
0x18000fb17  pop     r15
0x18000fb19  pop     r14
0x18000fb1b  pop     r13
0x18000fb1d  pop     r12
0x18000fb1f  pop     rdi
0x18000fb20  pop     rsi
0x18000fb21  pop     rbp
0x18000fb22  retn
```
