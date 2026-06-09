# wvr::MSFT_WvrAdminTasks::SetPartnershipAddVolumes(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,bool const *)

- ea: `0x18001e264`
- end: `0x18001e4a0`
- name: `?SetPartnershipAddVolumes@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@112PEB_N@Z`
- size: `572`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64, __int64, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009f9c`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001e264`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001e40a`: `MSFT_WvrAdminTasks`
- `0x18001e378`: `DestinationComputerName`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SetPartnershipAddVolumes(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7)
{
  __int64 *application; // rax
  __int64 v11; // rbx
  int v12; // eax
  mi::MiAsyncOperation::MiOperationArgs **v13; // rax
  enum _MI_CancellationReason v14; // edx
  __int64 v15; // rdx
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v20[7]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v21[8]; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base *v22; // [rsp+E8h] [rbp-18h]
  _QWORD v23[8]; // [rsp+100h] [rbp+0h] BYREF

  v17 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v21);
  mi::MiApplication::CreateParameterSet(*application, v20);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v19, (__int64)L"SourceRGName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v19, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v19);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v19, (__int64)L"SourceAddVolumePartnership");
    mi::MiInstance::AddElement(v20, v19, a4);
    std::wstring::_Tidy_deallocate((__int64)v19);
  }
  if ( a5 )
  {
    std::wstring::wstring((__int64)v19, (__int64)L"DestinationRGName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v19, a5, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v19);
  }
  if ( a6 )
  {
    std::wstring::wstring((__int64)v19, (__int64)L"DestinationComputerName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v19, a6, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v19);
  }
  if ( a7 )
  {
    std::wstring::wstring((__int64)v19, (__int64)L"DestinationAddVolumePartnership");
    mi::MiInstance::AddElement(v20, v19, a7);
    std::wstring::_Tidy_deallocate((__int64)v19);
  }
  v11 = *a1;
  v23[0] = &std::_Func_impl_no_alloc<_lambda_d7254051dd6b986771d7090cf60c7bfc_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v23[1] = &v17;
  v23[7] = v23;
  std::wstring::wstring((__int64)v19, (__int64)L"SetPartnershipAddVolumes");
  v12 = std::wstring::wstring((__int64)v21, (__int64)L"MSFT_WvrAdminTasks");
  v13 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v11,
                                                    (__int64)v18,
                                                    v12,
                                                    (int)v19,
                                                    (__int64)v20,
                                                    (__int64)v23);
  mi::MiAsyncOperation::Join(v13);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v18, v14);
  std::wstring::_Tidy_deallocate((__int64)v21);
  std::wstring::_Tidy_deallocate((__int64)v19);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v23, v15);
  LODWORD(v11) = v17;
  mi::MiInstance::~MiInstance(v20);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001e264  push    rbp
0x18001e266  push    rbx
0x18001e267  push    rsi
0x18001e268  push    rdi
0x18001e269  push    r12
0x18001e26b  push    r14
0x18001e26d  push    r15
0x18001e26f  lea     rbp, [rsp-50h]
0x18001e274  sub     rsp, 150h
0x18001e27b  mov     rax, cs:__security_cookie
0x18001e282  xor     rax, rsp
0x18001e285  mov     [rbp+80h+var_40], rax
0x18001e289  mov     rdi, r9
0x18001e28c  mov     rsi, rdx
0x18001e28f  mov     r12, rcx
0x18001e292  mov     r14, [rbp+80h+arg_20]
0x18001e299  mov     r15, [rbp+80h+arg_28]
0x18001e2a0  mov     rbx, [rbp+80h+arg_30]
0x18001e2a7  mov     [rsp+180h+var_150], 0
0x18001e2af  lea     rdx, [rbp+80h+var_A0]
0x18001e2b3  mov     rcx, [rcx]
0x18001e2b6  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e2bb  nop
0x18001e2bc  lea     rdx, [rbp+80h+var_D8]
0x18001e2c0  mov     rcx, [rax]
0x18001e2c3  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e2c8  nop
0x18001e2c9  mov     rcx, [rbp+80h+var_98]; this
0x18001e2cd  test    rcx, rcx
0x18001e2d0  jz      short loc_18001E2D7
0x18001e2d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e2d7  test    rsi, rsi
0x18001e2da  jz      short loc_18001E30D
0x18001e2dc  lea     rdx, aSourcergname; "SourceRGName"
0x18001e2e3  lea     rcx, [rbp+80h+var_F8]
0x18001e2e7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e2ec  nop
0x18001e2ed  mov     r9d, 2000h
0x18001e2f3  mov     r8, rsi
0x18001e2f6  lea     rdx, [rbp+80h+var_F8]
0x18001e2fa  lea     rcx, [rbp+80h+var_D8]
0x18001e2fe  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e303  nop
0x18001e304  lea     rcx, [rbp+80h+var_F8]
0x18001e308  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e30d  test    rdi, rdi
0x18001e310  jz      short loc_18001E33D
0x18001e312  lea     rdx, aSourceaddvolum; "SourceAddVolumePartnership"
0x18001e319  lea     rcx, [rbp+80h+var_F8]
0x18001e31d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e322  nop
0x18001e323  mov     r8, rdi
0x18001e326  lea     rdx, [rbp+80h+var_F8]
0x18001e32a  lea     rcx, [rbp+80h+var_D8]
0x18001e32e  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e333  nop
0x18001e334  lea     rcx, [rbp+80h+var_F8]
0x18001e338  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e33d  test    r14, r14
0x18001e340  jz      short loc_18001E373
0x18001e342  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18001e349  lea     rcx, [rbp+80h+var_F8]
0x18001e34d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e352  nop
0x18001e353  mov     r9d, 2000h
0x18001e359  mov     r8, r14
0x18001e35c  lea     rdx, [rbp+80h+var_F8]
0x18001e360  lea     rcx, [rbp+80h+var_D8]
0x18001e364  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e369  nop
0x18001e36a  lea     rcx, [rbp+80h+var_F8]
0x18001e36e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e373  test    r15, r15
0x18001e376  jz      short loc_18001E3A9
0x18001e378  lea     rdx, aDestinationcom; "DestinationComputerName"
0x18001e37f  lea     rcx, [rbp+80h+var_F8]
0x18001e383  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e388  nop
0x18001e389  mov     r9d, 2000h
0x18001e38f  mov     r8, r15
0x18001e392  lea     rdx, [rbp+80h+var_F8]
0x18001e396  lea     rcx, [rbp+80h+var_D8]
0x18001e39a  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e39f  nop
0x18001e3a0  lea     rcx, [rbp+80h+var_F8]
0x18001e3a4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e3a9  test    rbx, rbx
0x18001e3ac  jz      short loc_18001E3D9
0x18001e3ae  lea     rdx, aDestinationadd; "DestinationAddVolumePartnership"
0x18001e3b5  lea     rcx, [rbp+80h+var_F8]
0x18001e3b9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e3be  nop
0x18001e3bf  mov     r8, rbx
0x18001e3c2  lea     rdx, [rbp+80h+var_F8]
0x18001e3c6  lea     rcx, [rbp+80h+var_D8]
0x18001e3ca  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e3cf  nop
0x18001e3d0  lea     rcx, [rbp+80h+var_F8]
0x18001e3d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e3d9  mov     rbx, [r12]
0x18001e3dd  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d7254051dd6b986771d7090cf60c7bfc_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d7254051dd6b986771d7090cf60c7bfc_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e3e4  mov     [rbp+80h+var_80], rax
0x18001e3e8  lea     rax, [rsp+180h+var_150]
0x18001e3ed  mov     [rbp+80h+var_78], rax
0x18001e3f1  lea     rax, [rbp+80h+var_80]
0x18001e3f5  mov     [rbp+80h+var_48], rax
0x18001e3f9  lea     rdx, aSetpartnership; "SetPartnershipAddVolumes"
0x18001e400  lea     rcx, [rbp+80h+var_F8]
0x18001e404  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e409  nop
0x18001e40a  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e411  lea     rcx, [rbp+80h+var_A0]
0x18001e415  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e41a  nop
0x18001e41b  lea     rcx, [rbp+80h+var_80]
0x18001e41f  mov     [rsp+180h+var_158], rcx
0x18001e424  lea     rcx, [rbp+80h+var_D8]
0x18001e428  mov     [rsp+180h+var_160], rcx
0x18001e42d  lea     r9, [rbp+80h+var_F8]
0x18001e431  mov     r8, rax
0x18001e434  lea     rdx, [rsp+180h+var_148]
0x18001e439  mov     rcx, rbx
0x18001e43c  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e441  nop
0x18001e442  mov     rcx, rax; this
0x18001e445  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e44a  nop
0x18001e44b  lea     rcx, [rsp+180h+var_148]; this
0x18001e450  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e455  nop
0x18001e456  lea     rcx, [rbp+80h+var_A0]
0x18001e45a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e45f  nop
0x18001e460  lea     rcx, [rbp+80h+var_F8]
0x18001e464  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e469  nop
0x18001e46a  lea     rcx, [rbp+80h+var_80]
0x18001e46e  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e473  mov     ebx, [rsp+180h+var_150]
0x18001e477  lea     rcx, [rbp+80h+var_D8]; this
0x18001e47b  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e480  mov     eax, ebx
0x18001e482  mov     rcx, [rbp+80h+var_40]
0x18001e486  xor     rcx, rsp; StackCookie
0x18001e489  call    __security_check_cookie
0x18001e48e  add     rsp, 150h
0x18001e495  pop     r15
0x18001e497  pop     r14
0x18001e499  pop     r12
0x18001e49b  pop     rdi
0x18001e49c  pop     rsi
0x18001e49d  pop     rbx
0x18001e49e  pop     rbp
0x18001e49f  retn
```
