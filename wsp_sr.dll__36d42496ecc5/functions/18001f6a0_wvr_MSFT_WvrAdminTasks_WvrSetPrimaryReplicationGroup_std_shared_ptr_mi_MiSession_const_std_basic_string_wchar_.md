# wvr::MSFT_WvrAdminTasks::WvrSetPrimaryReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,bool const *)

- ea: `0x18001f6a0`
- end: `0x18001f907`
- name: `?WvrSetPrimaryReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@222PEB_N@Z`
- size: `615`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aec8`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001cbec`
- `0x18001f6a0`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001f86f`: `MSFT_WvrAdminTasks`
- `0x18001f7b3`: `SecondaryComputerName`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrSetPrimaryReplicationGroup(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 *application; // rax
  __int64 v12; // rbx
  int v13; // eax
  mi::MiAsyncOperation::MiOperationArgs **v14; // rax
  enum _MI_CancellationReason v15; // edx
  __int64 v16; // rdx
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[32]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v21[7]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v22[8]; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base *v23; // [rsp+E8h] [rbp-18h]
  _QWORD v24[8]; // [rsp+100h] [rbp+0h] BYREF

  v18 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v22);
  mi::MiApplication::CreateParameterSet(*application, v21);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v21, (int)v20, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v20);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"SecondaryReplicationGroupName");
    mi::MiInstance::AddElement(v21, v20, a3);
    std::wstring::_Tidy_deallocate((__int64)v20);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"SecondaryReplicationGroupId");
    mi::MiInstance::AddElement(v21, v20, a4);
    std::wstring::_Tidy_deallocate((__int64)v20);
  }
  if ( a5 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"SecondaryComputerName");
    mi::MiInstance::AddElement(v21, v20, a5);
    std::wstring::_Tidy_deallocate((__int64)v20);
  }
  if ( a6 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"PartnershipId");
    mi::MiInstance::AddElement(v21, v20, a6);
    std::wstring::_Tidy_deallocate((__int64)v20);
  }
  if ( a7 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"Force");
    mi::MiInstance::AddElement<bool>(v21, v20, a7);
    std::wstring::_Tidy_deallocate((__int64)v20);
  }
  v12 = *a1;
  v24[0] = &std::_Func_impl_no_alloc<_lambda_7e5ba9f4ea2dfa71161ca5221569fea1_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v24[1] = &v18;
  v24[7] = v24;
  std::wstring::wstring((__int64)v20, (__int64)L"WvrSetPrimaryReplicationGroup");
  v13 = std::wstring::wstring((__int64)v22, (__int64)L"MSFT_WvrAdminTasks");
  v14 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v12,
                                                    (__int64)v19,
                                                    v13,
                                                    (int)v20,
                                                    (__int64)v21,
                                                    (__int64)v24);
  mi::MiAsyncOperation::Join(v14);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v19, v15);
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::wstring::_Tidy_deallocate((__int64)v20);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v24, v16);
  LODWORD(v12) = v18;
  mi::MiInstance::~MiInstance(v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001f6a0  push    rbp
0x18001f6a2  push    rbx
0x18001f6a3  push    rsi
0x18001f6a4  push    rdi
0x18001f6a5  push    r12
0x18001f6a7  push    r13
0x18001f6a9  push    r14
0x18001f6ab  push    r15
0x18001f6ad  lea     rbp, [rsp-58h]
0x18001f6b2  sub     rsp, 158h
0x18001f6b9  mov     rax, cs:__security_cookie
0x18001f6c0  xor     rax, rsp
0x18001f6c3  mov     [rbp+90h+var_50], rax
0x18001f6c7  mov     r14, r9
0x18001f6ca  mov     rdi, r8
0x18001f6cd  mov     rsi, rdx
0x18001f6d0  mov     r13, rcx
0x18001f6d3  mov     r15, [rbp+90h+arg_20]
0x18001f6da  mov     r12, [rbp+90h+arg_28]
0x18001f6e1  mov     rbx, [rbp+90h+arg_30]
0x18001f6e8  mov     [rsp+190h+var_160], 0
0x18001f6f0  lea     rdx, [rbp+90h+var_B0]
0x18001f6f4  mov     rcx, [rcx]
0x18001f6f7  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f6fc  nop
0x18001f6fd  lea     rdx, [rbp+90h+var_E8]
0x18001f701  mov     rcx, [rax]
0x18001f704  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f709  nop
0x18001f70a  mov     rcx, [rbp+90h+var_A8]; this
0x18001f70e  test    rcx, rcx
0x18001f711  jz      short loc_18001F718
0x18001f713  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f718  test    rsi, rsi
0x18001f71b  jz      short loc_18001F74E
0x18001f71d  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f724  lea     rcx, [rbp+90h+var_108]
0x18001f728  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f72d  nop
0x18001f72e  mov     r9d, 2000h
0x18001f734  mov     r8, rsi
0x18001f737  lea     rdx, [rbp+90h+var_108]
0x18001f73b  lea     rcx, [rbp+90h+var_E8]
0x18001f73f  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f744  nop
0x18001f745  lea     rcx, [rbp+90h+var_108]
0x18001f749  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f74e  test    rdi, rdi
0x18001f751  jz      short loc_18001F77E
0x18001f753  lea     rdx, aSecondaryrepli; "SecondaryReplicationGroupName"
0x18001f75a  lea     rcx, [rbp+90h+var_108]
0x18001f75e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f763  nop
0x18001f764  mov     r8, rdi
0x18001f767  lea     rdx, [rbp+90h+var_108]
0x18001f76b  lea     rcx, [rbp+90h+var_E8]
0x18001f76f  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f774  nop
0x18001f775  lea     rcx, [rbp+90h+var_108]
0x18001f779  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f77e  test    r14, r14
0x18001f781  jz      short loc_18001F7AE
0x18001f783  lea     rdx, aSecondaryrepli_0; "SecondaryReplicationGroupId"
0x18001f78a  lea     rcx, [rbp+90h+var_108]
0x18001f78e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f793  nop
0x18001f794  mov     r8, r14
0x18001f797  lea     rdx, [rbp+90h+var_108]
0x18001f79b  lea     rcx, [rbp+90h+var_E8]
0x18001f79f  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f7a4  nop
0x18001f7a5  lea     rcx, [rbp+90h+var_108]
0x18001f7a9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f7ae  test    r15, r15
0x18001f7b1  jz      short loc_18001F7DE
0x18001f7b3  lea     rdx, aSecondarycompu; "SecondaryComputerName"
0x18001f7ba  lea     rcx, [rbp+90h+var_108]
0x18001f7be  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f7c3  nop
0x18001f7c4  mov     r8, r15
0x18001f7c7  lea     rdx, [rbp+90h+var_108]
0x18001f7cb  lea     rcx, [rbp+90h+var_E8]
0x18001f7cf  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f7d4  nop
0x18001f7d5  lea     rcx, [rbp+90h+var_108]
0x18001f7d9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f7de  test    r12, r12
0x18001f7e1  jz      short loc_18001F80E
0x18001f7e3  lea     rdx, aPartnershipid; "PartnershipId"
0x18001f7ea  lea     rcx, [rbp+90h+var_108]
0x18001f7ee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f7f3  nop
0x18001f7f4  mov     r8, r12
0x18001f7f7  lea     rdx, [rbp+90h+var_108]
0x18001f7fb  lea     rcx, [rbp+90h+var_E8]
0x18001f7ff  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f804  nop
0x18001f805  lea     rcx, [rbp+90h+var_108]
0x18001f809  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f80e  test    rbx, rbx
0x18001f811  jz      short loc_18001F83E
0x18001f813  lea     rdx, aForce; "Force"
0x18001f81a  lea     rcx, [rbp+90h+var_108]
0x18001f81e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f823  nop
0x18001f824  mov     r8, rbx
0x18001f827  lea     rdx, [rbp+90h+var_108]
0x18001f82b  lea     rcx, [rbp+90h+var_E8]
0x18001f82f  call    ??$AddElement@_N@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NI@Z; mi::MiInstance::AddElement<bool>(std::wstring const &,bool const &,uint)
0x18001f834  nop
0x18001f835  lea     rcx, [rbp+90h+var_108]
0x18001f839  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f83e  mov     rbx, [r13+0]
0x18001f842  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_7e5ba9f4ea2dfa71161ca5221569fea1_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_7e5ba9f4ea2dfa71161ca5221569fea1_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f849  mov     [rbp+90h+var_90], rax
0x18001f84d  lea     rax, [rsp+190h+var_160]
0x18001f852  mov     [rbp+90h+var_88], rax
0x18001f856  lea     rax, [rbp+90h+var_90]
0x18001f85a  mov     [rbp+90h+var_58], rax
0x18001f85e  lea     rdx, aWvrsetprimaryr; "WvrSetPrimaryReplicationGroup"
0x18001f865  lea     rcx, [rbp+90h+var_108]
0x18001f869  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f86e  nop
0x18001f86f  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f876  lea     rcx, [rbp+90h+var_B0]
0x18001f87a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f87f  nop
0x18001f880  lea     rcx, [rbp+90h+var_90]
0x18001f884  mov     [rsp+190h+var_168], rcx
0x18001f889  lea     rcx, [rbp+90h+var_E8]
0x18001f88d  mov     [rsp+190h+var_170], rcx
0x18001f892  lea     r9, [rbp+90h+var_108]
0x18001f896  mov     r8, rax
0x18001f899  lea     rdx, [rsp+190h+var_158]
0x18001f89e  mov     rcx, rbx
0x18001f8a1  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f8a6  nop
0x18001f8a7  mov     rcx, rax; this
0x18001f8aa  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f8af  nop
0x18001f8b0  lea     rcx, [rsp+190h+var_158]; this
0x18001f8b5  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f8ba  nop
0x18001f8bb  lea     rcx, [rbp+90h+var_B0]
0x18001f8bf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f8c4  nop
0x18001f8c5  lea     rcx, [rbp+90h+var_108]
0x18001f8c9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f8ce  nop
0x18001f8cf  lea     rcx, [rbp+90h+var_90]
0x18001f8d3  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f8d8  mov     ebx, [rsp+190h+var_160]
0x18001f8dc  lea     rcx, [rbp+90h+var_E8]; this
0x18001f8e0  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f8e5  mov     eax, ebx
0x18001f8e7  mov     rcx, [rbp+90h+var_50]
0x18001f8eb  xor     rcx, rsp; StackCookie
0x18001f8ee  call    __security_check_cookie
0x18001f8f3  add     rsp, 158h
0x18001f8fa  pop     r15
0x18001f8fc  pop     r14
0x18001f8fe  pop     r13
0x18001f900  pop     r12
0x18001f902  pop     rdi
0x18001f903  pop     rsi
0x18001f904  pop     rbx
0x18001f905  pop     rbp
0x18001f906  retn
```
