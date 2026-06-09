# wvr::MSFT_WvrAdminTasks::SetPartnershipAddVolumes(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,bool const *)

- ea: `0x18001e390`
- end: `0x18001e5cd`
- name: `?SetPartnershipAddVolumes@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@112PEB_N@Z`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a0f4`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001e390`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001e536`: `MSFT_WvrAdminTasks`
- `0x18001e4a4`: `DestinationComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SetPartnershipAddVolumes(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *application; // rax
  __int64 v11; // rbx
  int v12; // eax
  mi::MiAsyncOperation *v13; // rax
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v18[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v19[8]; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base *v20; // [rsp+E8h] [rbp-18h]
  _QWORD v21[8]; // [rsp+100h] [rbp+0h] BYREF

  v15 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v19);
  mi::MiApplication::CreateParameterSet(*application, v18);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( a2 )
  {
    std::wstring::wstring(v17, L"SourceRGName");
    mi::MiInstance::AddElement<std::wstring>(v18, v17, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v17);
  }
  if ( a4 )
  {
    std::wstring::wstring(v17, L"SourceAddVolumePartnership");
    mi::MiInstance::AddElement(v18, v17, a4);
    std::wstring::_Tidy_deallocate(v17);
  }
  if ( a5 )
  {
    std::wstring::wstring(v17, L"DestinationRGName");
    mi::MiInstance::AddElement<std::wstring>(v18, v17, a5, 0x2000);
    std::wstring::_Tidy_deallocate(v17);
  }
  if ( a6 )
  {
    std::wstring::wstring(v17, L"DestinationComputerName");
    mi::MiInstance::AddElement<std::wstring>(v18, v17, a6, 0x2000);
    std::wstring::_Tidy_deallocate(v17);
  }
  if ( a7 )
  {
    std::wstring::wstring(v17, L"DestinationAddVolumePartnership");
    mi::MiInstance::AddElement(v18, v17, a7);
    std::wstring::_Tidy_deallocate(v17);
  }
  v11 = *a1;
  v21[0] = &std::_Func_impl_no_alloc<_lambda_d7254051dd6b986771d7090cf60c7bfc_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v21[1] = &v15;
  v21[7] = v21;
  std::wstring::wstring(v17, L"SetPartnershipAddVolumes");
  v12 = std::wstring::wstring(v19, L"MSFT_WvrAdminTasks");
  v13 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v11,
                                  (unsigned int)v16,
                                  v12,
                                  (unsigned int)v17,
                                  (__int64)v18,
                                  (__int64)v21);
  mi::MiAsyncOperation::Join(v13);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v16);
  std::wstring::_Tidy_deallocate(v19);
  std::wstring::_Tidy_deallocate(v17);
  std::_Func_class<void,>::~_Func_class<void,>(v21);
  LODWORD(v11) = v15;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001e390  push    rbp
0x18001e392  push    rbx
0x18001e393  push    rsi
0x18001e394  push    rdi
0x18001e395  push    r12
0x18001e397  push    r14
0x18001e399  push    r15
0x18001e39b  lea     rbp, [rsp-50h]
0x18001e3a0  sub     rsp, 150h
0x18001e3a7  mov     rax, cs:__security_cookie
0x18001e3ae  xor     rax, rsp
0x18001e3b1  mov     [rbp+80h+var_40], rax
0x18001e3b5  mov     rdi, r9
0x18001e3b8  mov     rsi, rdx
0x18001e3bb  mov     r12, rcx
0x18001e3be  mov     r14, [rbp+80h+arg_20]
0x18001e3c5  mov     r15, [rbp+80h+arg_28]
0x18001e3cc  mov     rbx, [rbp+80h+arg_30]
0x18001e3d3  mov     [rsp+180h+var_150], 0
0x18001e3db  lea     rdx, [rbp+80h+var_A0]
0x18001e3df  mov     rcx, [rcx]
0x18001e3e2  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e3e7  nop
0x18001e3e8  lea     rdx, [rbp+80h+var_D8]
0x18001e3ec  mov     rcx, [rax]
0x18001e3ef  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e3f4  nop
0x18001e3f5  mov     rcx, [rbp+80h+var_98]; this
0x18001e3f9  test    rcx, rcx
0x18001e3fc  jz      short loc_18001E403
0x18001e3fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e403  test    rsi, rsi
0x18001e406  jz      short loc_18001E439
0x18001e408  lea     rdx, aSourcergname; "SourceRGName"
0x18001e40f  lea     rcx, [rbp+80h+var_F8]
0x18001e413  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e418  nop
0x18001e419  mov     r9d, 2000h
0x18001e41f  mov     r8, rsi
0x18001e422  lea     rdx, [rbp+80h+var_F8]
0x18001e426  lea     rcx, [rbp+80h+var_D8]
0x18001e42a  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e42f  nop
0x18001e430  lea     rcx, [rbp+80h+var_F8]
0x18001e434  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e439  test    rdi, rdi
0x18001e43c  jz      short loc_18001E469
0x18001e43e  lea     rdx, aSourceaddvolum; "SourceAddVolumePartnership"
0x18001e445  lea     rcx, [rbp+80h+var_F8]
0x18001e449  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e44e  nop
0x18001e44f  mov     r8, rdi
0x18001e452  lea     rdx, [rbp+80h+var_F8]
0x18001e456  lea     rcx, [rbp+80h+var_D8]
0x18001e45a  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e45f  nop
0x18001e460  lea     rcx, [rbp+80h+var_F8]
0x18001e464  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e469  test    r14, r14
0x18001e46c  jz      short loc_18001E49F
0x18001e46e  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18001e475  lea     rcx, [rbp+80h+var_F8]
0x18001e479  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e47e  nop
0x18001e47f  mov     r9d, 2000h
0x18001e485  mov     r8, r14
0x18001e488  lea     rdx, [rbp+80h+var_F8]
0x18001e48c  lea     rcx, [rbp+80h+var_D8]
0x18001e490  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e495  nop
0x18001e496  lea     rcx, [rbp+80h+var_F8]
0x18001e49a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e49f  test    r15, r15
0x18001e4a2  jz      short loc_18001E4D5
0x18001e4a4  lea     rdx, aDestinationcom; "DestinationComputerName"
0x18001e4ab  lea     rcx, [rbp+80h+var_F8]
0x18001e4af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e4b4  nop
0x18001e4b5  mov     r9d, 2000h
0x18001e4bb  mov     r8, r15
0x18001e4be  lea     rdx, [rbp+80h+var_F8]
0x18001e4c2  lea     rcx, [rbp+80h+var_D8]
0x18001e4c6  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e4cb  nop
0x18001e4cc  lea     rcx, [rbp+80h+var_F8]
0x18001e4d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e4d5  test    rbx, rbx
0x18001e4d8  jz      short loc_18001E505
0x18001e4da  lea     rdx, aDestinationadd; "DestinationAddVolumePartnership"
0x18001e4e1  lea     rcx, [rbp+80h+var_F8]
0x18001e4e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e4ea  nop
0x18001e4eb  mov     r8, rbx
0x18001e4ee  lea     rdx, [rbp+80h+var_F8]
0x18001e4f2  lea     rcx, [rbp+80h+var_D8]
0x18001e4f6  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e4fb  nop
0x18001e4fc  lea     rcx, [rbp+80h+var_F8]
0x18001e500  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e505  mov     rbx, [r12]
0x18001e509  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d7254051dd6b986771d7090cf60c7bfc_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d7254051dd6b986771d7090cf60c7bfc_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e510  mov     [rbp+80h+var_80], rax
0x18001e514  lea     rax, [rsp+180h+var_150]
0x18001e519  mov     [rbp+80h+var_78], rax
0x18001e51d  lea     rax, [rbp+80h+var_80]
0x18001e521  mov     [rbp+80h+var_48], rax
0x18001e525  lea     rdx, aSetpartnership; "SetPartnershipAddVolumes"
0x18001e52c  lea     rcx, [rbp+80h+var_F8]
0x18001e530  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e535  nop
0x18001e536  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e53d  lea     rcx, [rbp+80h+var_A0]
0x18001e541  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e546  nop
0x18001e547  lea     rcx, [rbp+80h+var_80]
0x18001e54b  mov     [rsp+180h+var_158], rcx
0x18001e550  lea     rcx, [rbp+80h+var_D8]
0x18001e554  mov     [rsp+180h+var_160], rcx
0x18001e559  lea     r9, [rbp+80h+var_F8]
0x18001e55d  mov     r8, rax
0x18001e560  lea     rdx, [rsp+180h+var_148]
0x18001e565  mov     rcx, rbx
0x18001e568  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e56d  nop
0x18001e56e  mov     rcx, rax; this
0x18001e571  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e576  nop
0x18001e577  lea     rcx, [rsp+180h+var_148]; this
0x18001e57c  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e581  nop
0x18001e582  lea     rcx, [rbp+80h+var_A0]
0x18001e586  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e58b  nop
0x18001e58c  lea     rcx, [rbp+80h+var_F8]
0x18001e590  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e595  nop
0x18001e596  lea     rcx, [rbp+80h+var_80]
0x18001e59a  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e59f  mov     ebx, [rsp+180h+var_150]
0x18001e5a3  lea     rcx, [rbp+80h+var_D8]; this
0x18001e5a7  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e5ac  mov     eax, ebx
0x18001e5ae  mov     rcx, [rbp+80h+var_40]
0x18001e5b2  xor     rcx, rsp; StackCookie
0x18001e5b5  call    __security_check_cookie
0x18001e5ba  add     rsp, 150h
0x18001e5c1  pop     r15
0x18001e5c3  pop     r14
0x18001e5c5  pop     r12
0x18001e5c7  pop     rdi
0x18001e5c8  pop     rsi
0x18001e5c9  pop     rbx
0x18001e5ca  pop     rbp
0x18001e5cb  retn
```
