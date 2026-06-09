# ShowStoreAppRecommendation

- ea: `0x18001d900`
- end: `0x18001da31`
- name: `ShowStoreAppRecommendation`
- size: `305`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *, unsigned __int16 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005ab8`
- `0x1800060a8`
- `0x180014554`
- `0x180014bf4`
- `0x180014cf0`
- `0x180014d94`
- `0x180016c34`
- `0x18001a704`
- `0x18001a950`
- `0x18001b048`
- `0x18001cbfc`
- `0x18001d900`

## import_xrefs

- `USER32!EnableWindow` at `0x18001d9a8`
- `USER32!EnableWindow` at `0x18001d9a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ShowStoreAppRecommendation(
        HWND a1,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        struct IUnknown *a7)
{
  void **v10; // rax
  HWND Owner; // rbx
  const unsigned __int16 *v12; // r8
  char v13; // di
  volatile signed __int32 *v14; // rbx
  const char *v15; // r9
  __int64 result; // rax
  void *v17; // [rsp+30h] [rbp-68h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v20[48]; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v17 = 0;
  v10 = tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::ensure_data(&v17);
  tip2::details::shared_data<1,0,0>::start((__int64)*v10 + 8, &v18);
  try
  {
    MonitorAwareUIPositioner::MonitorAwareUIPositioner((MonitorAwareUIPositioner *)v19, a1, 0, a7);
    Owner = MonitorAwareUIPositioner::GetOwner((MonitorAwareUIPositioner *)v19);
    OwnerWindowDisabler::OwnerWindowDisabler((OwnerWindowDisabler *)&v18, a1);
    v13 = ShowSACAppRecommendation(Owner, a2, v12, a4, a5, a6);
    if ( (_BYTE)v18 )
      EnableWindow(*((HWND *)&v18 + 1), 1);
    wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&int DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&int DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>(v20);
    v14 = (volatile signed __int32 *)*tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::ensure_data(&v17);
    *(_QWORD *)&v18 = v14;
    if ( v14 )
      _InterlockedIncrement(v14 + 70);
    tip2::details::shared_data<1,0,0>::begin_update((__int64)(v14 + 2));
    *((_BYTE *)v14 + 272) = v13;
    tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>(&v18);
    tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::complete(&v17);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>(&v17);
    result = v13 == 0 ? 0x80004005 : 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x946,
      (unsigned int)"shell\\shdocvw\\download.cpp",
      v15);
    tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::complete(&v17);
    wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>(&v17);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001d900  push    rbx
0x18001d902  push    rsi
0x18001d903  push    rdi
0x18001d904  push    r14
0x18001d906  sub     rsp, 78h
0x18001d90a  mov     rsi, r9
0x18001d90d  mov     r14, rdx
0x18001d910  mov     rdi, rcx
0x18001d913  mov     [rsp+98h+var_68], 0
0x18001d91c  lea     rcx, [rsp+98h+var_68]
0x18001d921  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::ensure_data(void)
0x18001d926  mov     rcx, [rax]
0x18001d929  add     rcx, 8
0x18001d92d  lea     rdx, [rsp+98h+var_60]
0x18001d932  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18001d937  nop
0x18001d938  mov     r9, [rsp+98h+arg_30]; struct IUnknown *
0x18001d940  xor     r8d, r8d; int
0x18001d943  mov     rdx, rdi; HWND
0x18001d946  lea     rcx, [rsp+98h+var_50]; this
0x18001d94b  call    ??0MonitorAwareUIPositioner@@QEAA@PEAUHWND__@@HPEAUIUnknown@@@Z; MonitorAwareUIPositioner::MonitorAwareUIPositioner(HWND__ *,int,IUnknown *)
0x18001d950  nop
0x18001d951  lea     rcx, [rsp+98h+var_50]; this
0x18001d956  call    ?GetOwner@MonitorAwareUIPositioner@@QEAAPEAUHWND__@@XZ; MonitorAwareUIPositioner::GetOwner(void)
0x18001d95b  mov     rbx, rax
0x18001d95e  mov     rdx, rdi; HWND
0x18001d961  lea     rcx, [rsp+98h+var_60]; this
0x18001d966  call    ??0OwnerWindowDisabler@@QEAA@PEAUHWND__@@@Z; OwnerWindowDisabler::OwnerWindowDisabler(HWND__ *)
0x18001d96b  nop
0x18001d96c  mov     rcx, [rsp+98h+arg_28]
0x18001d974  mov     [rsp+98h+var_70], rcx; unsigned __int16 *
0x18001d979  mov     rcx, [rsp+98h+arg_20]
0x18001d981  mov     [rsp+98h+var_78], rcx; unsigned __int16 *
0x18001d986  mov     r9, rsi; unsigned __int16 *
0x18001d989  mov     rdx, r14; unsigned __int16 *
0x18001d98c  mov     rcx, rbx; HWND
0x18001d98f  call    ?ShowSACAppRecommendation@@YA_NPEAUHWND__@@PEBG1111@Z; ShowSACAppRecommendation(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001d994  mov     dil, al
0x18001d997  cmp     byte ptr [rsp+98h+var_60], 0
0x18001d99c  jz      short loc_18001D9AF
0x18001d99e  mov     edx, 1; bEnable
0x18001d9a3  mov     rcx, [rsp+98h+hWnd]; hWnd
0x18001d9a8  call    cs:__imp_EnableWindow
0x18001d9ae  nop
0x18001d9af  lea     rcx, [rsp+98h+var_30]
0x18001d9b4  call    ??1?$unique_storage@U?$resource_policy@PEAUHWND__@@P6AHPEAU1@@Z$1?DestroyWindow@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HWND__ *,int (*)(HWND__ *),&DestroyWindow(HWND__ *),wistd::integral_constant<unsigned __int64,0>,HWND__ *,HWND__ *,0,std::nullptr_t>>(void)
0x18001d9b9  nop
0x18001d9ba  lea     rcx, [rsp+98h+var_68]
0x18001d9bf  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::ensure_data(void)
0x18001d9c4  mov     rbx, [rax]
0x18001d9c7  mov     [rsp+98h+var_60], rbx
0x18001d9cc  test    rbx, rbx
0x18001d9cf  jz      short loc_18001D9D8
0x18001d9d1  lock inc dword ptr [rbx+118h]
0x18001d9d8  lea     rcx, [rbx+8]
0x18001d9dc  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x18001d9e1  mov     [rbx+110h], dil
0x18001d9e8  lea     rcx, [rsp+98h+var_60]
0x18001d9ed  call    ??1?$test_data_control@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::~test_data_control<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>(void)
0x18001d9f2  lea     rcx, [rsp+98h+var_68]
0x18001d9f7  call    ?complete@?$tip_test@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>>::complete(void)
0x18001d9fc  nop
0x18001d9fd  neg     dil
0x18001da00  sbb     ebx, ebx
0x18001da02  not     ebx
0x18001da04  and     ebx, 80004005h
0x18001da0a  lea     rcx, [rsp+98h+var_68]
0x18001da0f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>(void)
0x18001da14  mov     eax, ebx
0x18001da16  jmp     short loc_18001DA27
0x18001da18  lea     rcx, [rsp+98h+var_68]
0x18001da1d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>,wil::err_returncode_policy>(void)
0x18001da22  mov     eax, 80004005h
0x18001da27  add     rsp, 78h
0x18001da2b  pop     r14
0x18001da2d  pop     rdi
0x18001da2e  pop     rsi
0x18001da2f  pop     rbx
0x18001da30  retn
```
