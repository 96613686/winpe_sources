# SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool)

- ea: `0x14005b34c`
- end: `0x14005b726`
- name: `?TryClaimSingletonOrRedirectLaunch@SingletonHelper@SingletonHelpers@@QEAA?AW4SingletonClaimResult@2@AEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_N@Z`
- size: `986`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005b72c`

## callees

- `0x14000bca8`
- `0x14000c0c8`
- `0x140046a30`
- `0x14004afcc`
- `0x140052d90`
- `0x140052eec`
- `0x140053000`
- `0x140053a4c`
- `0x140057044`
- `0x14005ad28`
- `0x14005b34c`
- `0x14005bd30`
- `0x14005d6a8`
- `0x14005db48`
- `0x14005f760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14005b42b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14005b42b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005b659`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005b659`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005b51e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005b51e`
- `faultrep!ReportCoreHang` at `0x14005b5f8`
- `faultrep!ReportCoreHang` at `0x14005b5f8`

## string_xrefs

- `0x14005b714`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14005b6fe`: `shellcommon\internal\shell\inc\SingletonHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  void **v5; // r15
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  DWORD v8; // r13d
  unsigned int v9; // ecx
  char v10; // r14
  __int64 v11; // rsi
  void *v12; // rbx
  DWORD v13; // eax
  const char *v14; // r9
  void *v15; // rbx
  _QWORD *v16; // rbx
  HKEY v17; // rcx
  __int64 v18; // rax
  __int64 *v19; // r14
  __int64 v20; // rax
  __int64 v21; // rcx
  int unused; // r12d
  int v23; // edx
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // ebx
  const char *v29; // r9
  _QWORD *v30; // rax
  __int64 v31; // rcx
  _QWORD *v32; // rdi
  DWORD pdwType; // [rsp+28h] [rbp-89h]
  HWND pvData; // [rsp+30h] [rbp-81h]
  DWORD v35; // [rsp+38h] [rbp-79h]
  HKEY v36; // [rsp+40h] [rbp-71h]
  __int64 v37; // [rsp+48h] [rbp-69h] BYREF
  int v38; // [rsp+50h] [rbp-61h]
  unsigned int v39; // [rsp+54h] [rbp-5Dh]
  DWORD pcbData; // [rsp+58h] [rbp-59h] BYREF
  void *v41; // [rsp+60h] [rbp-51h] BYREF
  int v42[2]; // [rsp+68h] [rbp-49h] BYREF
  __int64 v43; // [rsp+70h] [rbp-41h]
  HKEY hkey; // [rsp+78h] [rbp-39h] BYREF
  int v45[2]; // [rsp+80h] [rbp-31h] BYREF
  __int64 v46; // [rsp+88h] [rbp-29h]
  char v47[8]; // [rsp+90h] [rbp-21h] BYREF
  char v48[8]; // [rsp+98h] [rbp-19h] BYREF
  HKEY v49[2]; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v50[11]; // [rsp+B0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]
  struct HWND__ hWnd; // [rsp+118h] [rbp+67h] BYREF
  __int64 v53; // [rsp+120h] [rbp+6Fh]
  unsigned int v54; // [rsp+128h] [rbp+77h]
  int v55; // [rsp+130h] [rbp+7Fh] BYREF

  LOBYTE(v55) = (_BYTE)a4;
  v54 = a3;
  v53 = a2;
  v5 = (void **)(a1 + 112);
  if ( *(_QWORD *)(a1 + 112) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15C,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\SingletonHelpers.h",
      a4);
  v37 = 0;
  v6 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::ensure_data(&v37);
  tip2::details::shared_data<0,0,0>::start(*v6 + 8LL, v42);
  v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                   &v37,
                   &hWnd);
  std::wstring::operator=(*v7 + 272LL, a1 + 72);
  tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(&hWnd);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                          &v37,
                          &hWnd)
           + 304LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(&hWnd);
  v8 = 0;
  v9 = 0;
  v38 = 0;
  v54 = 0;
  v10 = 0;
  LOBYTE(v55) = 0;
  v11 = -1;
  while ( 1 )
  {
    v39 = v9;
    if ( v9 >= 0x2710 && !v10 )
    {
LABEL_38:
      tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::complete(&v37);
      wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v37);
      return 2;
    }
    v12 = *(void **)(a1 + 104);
    v13 = WaitForSingleObjectEx(v12, v8, 0);
    if ( v13 == 258 )
    {
      v12 = 0;
    }
    else if ( (v13 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    }
    v41 = v12;
    if ( v5 != &v41 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v5,
        v12);
      v41 = 0;
    }
    v15 = *v5;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
    if ( v15 )
      break;
    if ( v10 )
      goto LABEL_38;
    v16 = (_QWORD *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 64) <= 7u )
      v17 = (HKEY)(a1 + 40);
    else
      v17 = (HKEY)*v16;
    v49[0] = v17;
    v18 = -1;
    do
      ++v18;
    while ( *((_WORD *)v17 + v18) );
    v49[1] = (HKEY)v18;
    v19 = (__int64 *)(a1 + 8);
    if ( *(_QWORD *)(a1 + 32) <= 7u )
      v20 = a1 + 8;
    else
      v20 = *v19;
    v50[0] = v20;
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(v20 + 2 * v21) );
    v50[1] = v21;
    SingletonHelpers::details::GetSingletonSessionSubKey(&hkey, v50, v49, 0x20019u);
    hWnd.unused = 0;
    pcbData = 4;
    RegGetValueW(hkey, 0, L"ProcessId", 0x18u, 0, &hWnd, &pcbData);
    unused = hWnd.unused;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    v23 = v38;
    if ( unused == v38 )
    {
      v24 = v54;
    }
    else
    {
      v23 = unused;
      v38 = unused;
      v24 = 0;
    }
    v54 = v8 + v24;
    if ( !v23 )
      goto LABEL_35;
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                            &v37,
                            v47)
             + 306LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(v47);
    v25 = *(_QWORD *)(a1 + 56);
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v16 = (_QWORD *)*v16;
    *(_QWORD *)v45 = v16;
    v46 = v25;
    v26 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(a1 + 32) > 7u )
      v19 = (__int64 *)*v19;
    *(_QWORD *)v42 = v19;
    v43 = v26;
    v27 = SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(
            (int)v42,
            (int)v45,
            unused,
            v53,
            pdwType,
            pvData,
            v35,
            v36);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                             &v37,
                             v48)
              + 308LL) = v27;
    tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(v48);
    if ( !v27 )
    {
      tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::complete(&v37);
      wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v37);
      return 1;
    }
    if ( v27 == 1 && v54 >= 0x2710 )
    {
      v55 = unused;
      ReportCoreHang(&v55, 1, 0, 32);
      v10 = 1;
      LOBYTE(v55) = 1;
    }
    else
    {
LABEL_35:
      v10 = v55;
    }
    v9 = v8 + v39;
    v8 += 200;
  }
  *(_DWORD *)(a1 + 120) = GetCurrentThreadId();
  v30 = (_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(a1 + 64) > 7u )
    v30 = (_QWORD *)*v30;
  *(_QWORD *)v42 = v30;
  v31 = -1;
  do
    ++v31;
  while ( *((_WORD *)v30 + v31) );
  v43 = v31;
  v32 = (_QWORD *)(a1 + 8);
  if ( v32[3] > 7u )
    v32 = (_QWORD *)*v32;
  *(_QWORD *)v45 = v32;
  do
    ++v11;
  while ( *((_WORD *)v32 + v11) );
  v46 = v11;
  SingletonHelpers::details::SetPIDAndClearCommunicationHWNDForSingletonInstance(v5, (__int64)v45, (__int64)v42, v29);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                          &v37,
                          &hWnd)
           + 305LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(&hWnd);
  tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::complete(&v37);
  wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v37);
  return 0;
}

```

## disassembly

```asm
0x14005b34c  mov     rax, rsp
0x14005b34f  mov     [rax+20h], r9b
0x14005b353  mov     [rax+18h], r8d
0x14005b357  mov     [rax+10h], rdx
0x14005b35b  push    rbp
0x14005b35c  push    rbx
0x14005b35d  push    rsi
0x14005b35e  push    rdi
0x14005b35f  push    r12
0x14005b361  push    r13
0x14005b363  push    r14
0x14005b365  push    r15
0x14005b367  lea     rbp, [rax-5Fh]
0x14005b36b  sub     rsp, 0C8h
0x14005b372  mov     rdi, rcx
0x14005b375  lea     r15, [rcx+70h]
0x14005b379  mov     rcx, [rbp+5Fh]; this
0x14005b37d  xor     r12d, r12d
0x14005b380  cmp     [r15], r12
0x14005b383  jnz     loc_14005B6FE
0x14005b389  mov     [rbp+57h+var_C0], r12
0x14005b38d  lea     rcx, [rbp+57h+var_C0]
0x14005b391  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::ensure_data(void)
0x14005b396  mov     rcx, [rax]
0x14005b399  add     rcx, 8
0x14005b39d  lea     rdx, [rbp+57h+var_A0]
0x14005b3a1  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x14005b3a6  lea     rdx, [rbp+57h+hWnd]
0x14005b3aa  lea     rcx, [rbp+57h+var_C0]
0x14005b3ae  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x14005b3b3  nop
0x14005b3b4  lea     rdx, [rdi+48h]
0x14005b3b8  mov     rcx, [rax]
0x14005b3bb  add     rcx, 110h
0x14005b3c2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14005b3c7  nop
0x14005b3c8  lea     rcx, [rbp+57h+hWnd]
0x14005b3cc  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x14005b3d1  lea     rdx, [rbp+57h+hWnd]
0x14005b3d5  lea     rcx, [rbp+57h+var_C0]
0x14005b3d9  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x14005b3de  mov     rcx, [rax]
0x14005b3e1  mov     byte ptr [rcx+130h], 1
0x14005b3e8  lea     rcx, [rbp+57h+hWnd]
0x14005b3ec  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x14005b3f1  mov     r13d, r12d
0x14005b3f4  mov     ecx, r12d
0x14005b3f7  mov     [rbp+57h+var_B8], r12d
0x14005b3fb  mov     [rbp+57h+arg_10], r12d
0x14005b3ff  mov     r14b, r12b
0x14005b402  mov     byte ptr [rbp+57h+arg_18], r12b
0x14005b406  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005b40a  mov     [rbp+57h+var_B4], ecx
0x14005b40d  cmp     ecx, 2710h
0x14005b413  jb      short loc_14005B41E
0x14005b415  test    r14b, r14b
0x14005b418  jz      loc_14005B63C
0x14005b41e  mov     rbx, [rdi+68h]
0x14005b422  xor     r8d, r8d; bAlertable
0x14005b425  mov     edx, r13d; dwMilliseconds
0x14005b428  mov     rcx, rbx; hHandle
0x14005b42b  call    cs:__imp_WaitForSingleObjectEx
0x14005b431  cmp     eax, 102h
0x14005b436  jz      short loc_14005B445
0x14005b438  test    eax, 0FFFFFF7Fh
0x14005b43d  jnz     loc_14005B710
0x14005b443  jmp     short loc_14005B448
0x14005b445  mov     rbx, r12
0x14005b448  mov     [rbp+57h+var_A8], rbx
0x14005b44c  lea     rax, [rbp+57h+var_A8]
0x14005b450  cmp     r15, rax
0x14005b453  jz      short loc_14005B464
0x14005b455  mov     rdx, rbx
0x14005b458  mov     rcx, r15
0x14005b45b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14005b460  mov     [rbp+57h+var_A8], r12
0x14005b464  mov     rbx, [r15]
0x14005b467  lea     rcx, [rbp+57h+var_A8]
0x14005b46b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14005b470  test    rbx, rbx
0x14005b473  jnz     loc_14005B659
0x14005b479  test    r14b, r14b
0x14005b47c  jnz     loc_14005B63C
0x14005b482  lea     rbx, [rdi+28h]
0x14005b486  cmp     qword ptr [rdi+40h], 7
0x14005b48b  jbe     short loc_14005B492
0x14005b48d  mov     rcx, [rbx]
0x14005b490  jmp     short loc_14005B495
0x14005b492  mov     rcx, rbx
0x14005b495  mov     [rbp+57h+var_68], rcx
0x14005b499  mov     rax, rsi
0x14005b49c  inc     rax
0x14005b49f  cmp     [rcx+rax*2], r12w
0x14005b4a4  jnz     short loc_14005B49C
0x14005b4a6  mov     [rbp+57h+var_60], rax
0x14005b4aa  lea     r14, [rdi+8]
0x14005b4ae  cmp     qword ptr [rdi+20h], 7
0x14005b4b3  jbe     short loc_14005B4BA
0x14005b4b5  mov     rax, [r14]
0x14005b4b8  jmp     short loc_14005B4BD
0x14005b4ba  mov     rax, r14
0x14005b4bd  mov     [rbp+57h+var_58], rax
0x14005b4c1  mov     rcx, rsi
0x14005b4c4  inc     rcx
0x14005b4c7  cmp     [rax+rcx*2], r12w
0x14005b4cc  jnz     short loc_14005B4C4
0x14005b4ce  mov     [rbp+57h+var_50], rcx
0x14005b4d2  mov     r9d, 20019h
0x14005b4d8  lea     r8, [rbp+57h+var_68]
0x14005b4dc  lea     rdx, [rbp+57h+var_58]
0x14005b4e0  lea     rcx, [rbp+57h+hkey]
0x14005b4e4  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong)
0x14005b4e9  mov     [rbp+57h+hWnd.unused], r12d
0x14005b4ed  mov     [rbp+57h+pcbData], 4
0x14005b4f4  lea     rax, [rbp+57h+pcbData]
0x14005b4f8  mov     [rsp+30h], rax; DWORD
0x14005b4fd  lea     rax, [rbp+57h+hWnd]
0x14005b501  mov     [rsp+100h+pvData], rax; hWnd
0x14005b506  mov     [rsp+100h+pdwType], r12; dwProcessId
0x14005b50b  mov     r9d, 18h; dwFlags
0x14005b511  mov     r8, cs:lpValue; lpValue
0x14005b518  xor     edx, edx; lpSubKey
0x14005b51a  mov     rcx, [rbp+57h+hkey]; hkey
0x14005b51e  call    cs:__imp_RegGetValueW
0x14005b524  mov     r12d, [rbp+57h+hWnd.unused]
0x14005b528  lea     rcx, [rbp+57h+hkey]
0x14005b52c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14005b531  mov     edx, [rbp+57h+var_B8]
0x14005b534  cmp     r12d, edx
0x14005b537  jz      short loc_14005B543
0x14005b539  mov     edx, r12d
0x14005b53c  mov     [rbp+57h+var_B8], edx
0x14005b53f  xor     eax, eax
0x14005b541  jmp     short loc_14005B546
0x14005b543  mov     eax, [rbp+57h+arg_10]
0x14005b546  add     eax, r13d
0x14005b549  mov     [rbp+57h+arg_10], eax
0x14005b54c  test    edx, edx
0x14005b54e  jz      loc_14005B606
0x14005b554  lea     rdx, [rbp+57h+var_78]
0x14005b558  lea     rcx, [rbp+57h+var_C0]
0x14005b55c  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x14005b561  mov     rcx, [rax]
0x14005b564  mov     byte ptr [rcx+132h], 1
0x14005b56b  lea     rcx, [rbp+57h+var_78]
0x14005b56f  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x14005b574  mov     rax, [rdi+38h]
0x14005b578  cmp     qword ptr [rdi+40h], 7
0x14005b57d  jbe     short loc_14005B582
0x14005b57f  mov     rbx, [rbx]
0x14005b582  mov     qword ptr [rbp+57h+var_88], rbx
0x14005b586  mov     [rbp+57h+var_80], rax
0x14005b58a  mov     rax, [rdi+18h]
0x14005b58e  cmp     qword ptr [rdi+20h], 7
0x14005b593  jbe     short loc_14005B598
0x14005b595  mov     r14, [r14]
0x14005b598  mov     qword ptr [rbp+57h+var_A0], r14
0x14005b59c  mov     [rbp+57h+var_98], rax
0x14005b5a0  mov     r9, [rbp+57h+arg_8]; int
0x14005b5a4  mov     r8d, r12d; int
0x14005b5a7  lea     rdx, [rbp+57h+var_88]; int
0x14005b5ab  lea     rcx, [rbp+57h+var_A0]; int
0x14005b5af  call    ?TryRedirectLaunchToProcess@SingletonHelper@SingletonHelpers@@KA?AW4RedirectionResult@details@2@AEBV?$basic_zstring_view@G@wil@@0KAEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_NW4StandardMessage@@PEAVFlowEndpointBase@@@Z; SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool,StandardMessage,FlowEndpointBase *)
0x14005b5b4  mov     ebx, eax
0x14005b5b6  lea     rdx, [rbp+57h+var_70]
0x14005b5ba  lea     rcx, [rbp+57h+var_C0]
0x14005b5be  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x14005b5c3  mov     rcx, [rax]
0x14005b5c6  mov     [rcx+134h], ebx
0x14005b5cc  lea     rcx, [rbp+57h+var_70]
0x14005b5d0  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x14005b5d5  test    ebx, ebx
0x14005b5d7  jz      short loc_14005B61F
0x14005b5d9  cmp     ebx, 1
0x14005b5dc  jnz     short loc_14005B606
0x14005b5de  cmp     [rbp+57h+arg_10], 2710h
0x14005b5e5  jb      short loc_14005B606
0x14005b5e7  mov     [rbp+57h+arg_18], r12d
0x14005b5eb  lea     r9d, [rbx+1Fh]
0x14005b5ef  xor     r8d, r8d
0x14005b5f2  mov     edx, ebx
0x14005b5f4  lea     rcx, [rbp+57h+arg_18]
0x14005b5f8  call    cs:__imp_ReportCoreHang
0x14005b5fe  mov     r14b, bl
0x14005b601  mov     byte ptr [rbp+57h+arg_18], bl
0x14005b604  jmp     short loc_14005B60A
0x14005b606  mov     r14b, byte ptr [rbp+57h+arg_18]
0x14005b60a  mov     ecx, [rbp+57h+var_B4]
0x14005b60d  add     ecx, r13d
0x14005b610  add     r13d, 0C8h
0x14005b617  xor     r12d, r12d
0x14005b61a  jmp     loc_14005B40A
0x14005b61f  lea     rcx, [rbp+57h+var_C0]
0x14005b623  call    ?complete@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::complete(void)
0x14005b628  nop
0x14005b629  lea     rcx, [rbp+57h+var_C0]
0x14005b62d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x14005b632  mov     eax, 1
0x14005b637  jmp     loc_14005B6EA
0x14005b63c  lea     rcx, [rbp+57h+var_C0]
0x14005b640  call    ?complete@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::complete(void)
0x14005b645  nop
0x14005b646  lea     rcx, [rbp+57h+var_C0]
0x14005b64a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x14005b64f  mov     eax, 2
0x14005b654  jmp     loc_14005B6EA
0x14005b659  call    cs:__imp_GetCurrentThreadId
0x14005b65f  mov     [rdi+78h], eax
0x14005b662  lea     rax, [rdi+28h]
0x14005b666  cmp     qword ptr [rax+18h], 7
0x14005b66b  jbe     short loc_14005B670
0x14005b66d  mov     rax, [rax]
0x14005b670  mov     qword ptr [rbp+57h+var_A0], rax
0x14005b674  mov     rcx, rsi
0x14005b677  inc     rcx
0x14005b67a  cmp     [rax+rcx*2], r12w
0x14005b67f  jnz     short loc_14005B677
0x14005b681  mov     [rbp+57h+var_98], rcx
0x14005b685  add     rdi, 8
0x14005b689  cmp     qword ptr [rdi+18h], 7
0x14005b68e  jbe     short loc_14005B693
0x14005b690  mov     rdi, [rdi]
0x14005b693  mov     qword ptr [rbp+57h+var_88], rdi
0x14005b697  inc     rsi
0x14005b69a  cmp     [rdi+rsi*2], r12w
0x14005b69f  jnz     short loc_14005B697
0x14005b6a1  mov     [rbp+57h+var_80], rsi
0x14005b6a5  lea     r8, [rbp+57h+var_A0]
0x14005b6a9  lea     rdx, [rbp+57h+var_88]
0x14005b6ad  mov     rcx, r15
0x14005b6b0  call    ?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@1@Z
0x14005b6b5  lea     rdx, [rbp+57h+hWnd]
0x14005b6b9  lea     rcx, [rbp+57h+var_C0]
0x14005b6bd  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x14005b6c2  mov     rcx, [rax]
0x14005b6c5  mov     byte ptr [rcx+131h], 1
0x14005b6cc  lea     rcx, [rbp+57h+hWnd]
0x14005b6d0  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x14005b6d5  lea     rcx, [rbp+57h+var_C0]
0x14005b6d9  call    ?complete@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::complete(void)
0x14005b6de  nop
0x14005b6df  lea     rcx, [rbp+57h+var_C0]
0x14005b6e3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x14005b6e8  xor     eax, eax
0x14005b6ea  add     rsp, 0C8h
0x14005b6f1  pop     r15
0x14005b6f3  pop     r14
0x14005b6f5  pop     r13
0x14005b6f7  pop     r12
0x14005b6f9  pop     rdi
0x14005b6fa  pop     rsi
0x14005b6fb  pop     rbx
0x14005b6fc  pop     rbp
0x14005b6fd  retn
0x14005b6fe  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Sing"...
0x14005b705  mov     edx, 15Ch; void *
0x14005b70a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14005b710  mov     rcx, [rbp+5Fh]; this
0x14005b714  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14005b71b  mov     edx, 0E01h; void *
0x14005b720  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
