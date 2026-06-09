# wvr::MSFT_WvrAdminTasks::WvrSetPrimaryReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,bool const *)

- ea: `0x18001f7d8`
- end: `0x18001fa40`
- name: `?WvrSetPrimaryReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@222PEB_N@Z`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b030`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001ccf4`
- `0x18001f7d8`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001f9a7`: `MSFT_WvrAdminTasks`
- `0x18001f8eb`: `SecondaryComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrSetPrimaryReplicationGroup(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *application; // rax
  __int64 v12; // rbx
  int v13; // eax
  mi::MiAsyncOperation *v14; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v19[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v20[8]; // [rsp+E0h] [rbp-20h] BYREF
  std::_Ref_count_base *v21; // [rsp+E8h] [rbp-18h]
  _QWORD v22[8]; // [rsp+100h] [rbp+0h] BYREF

  v16 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v20);
  mi::MiApplication::CreateParameterSet(*application, v19);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  if ( a2 )
  {
    std::wstring::wstring(v18, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v19, v18, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v18);
  }
  if ( a3 )
  {
    std::wstring::wstring(v18, L"SecondaryReplicationGroupName");
    mi::MiInstance::AddElement(v19, v18, a3);
    std::wstring::_Tidy_deallocate(v18);
  }
  if ( a4 )
  {
    std::wstring::wstring(v18, L"SecondaryReplicationGroupId");
    mi::MiInstance::AddElement(v19, v18, a4);
    std::wstring::_Tidy_deallocate(v18);
  }
  if ( a5 )
  {
    std::wstring::wstring(v18, L"SecondaryComputerName");
    mi::MiInstance::AddElement(v19, v18, a5);
    std::wstring::_Tidy_deallocate(v18);
  }
  if ( a6 )
  {
    std::wstring::wstring(v18, L"PartnershipId");
    mi::MiInstance::AddElement(v19, v18, a6);
    std::wstring::_Tidy_deallocate(v18);
  }
  if ( a7 )
  {
    std::wstring::wstring(v18, L"Force");
    mi::MiInstance::AddElement<bool>(v19, v18, a7);
    std::wstring::_Tidy_deallocate(v18);
  }
  v12 = *a1;
  v22[0] = &std::_Func_impl_no_alloc<_lambda_7e5ba9f4ea2dfa71161ca5221569fea1_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v22[1] = &v16;
  v22[7] = v22;
  std::wstring::wstring(v18, L"WvrSetPrimaryReplicationGroup");
  v13 = std::wstring::wstring(v20, L"MSFT_WvrAdminTasks");
  v14 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v12,
                                  (unsigned int)v17,
                                  v13,
                                  (unsigned int)v18,
                                  (__int64)v19,
                                  (__int64)v22);
  mi::MiAsyncOperation::Join(v14);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v17);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(v18);
  std::_Func_class<void,>::~_Func_class<void,>(v22);
  LODWORD(v12) = v16;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001f7d8  push    rbp
0x18001f7da  push    rbx
0x18001f7db  push    rsi
0x18001f7dc  push    rdi
0x18001f7dd  push    r12
0x18001f7df  push    r13
0x18001f7e1  push    r14
0x18001f7e3  push    r15
0x18001f7e5  lea     rbp, [rsp-58h]
0x18001f7ea  sub     rsp, 158h
0x18001f7f1  mov     rax, cs:__security_cookie
0x18001f7f8  xor     rax, rsp
0x18001f7fb  mov     [rbp+90h+var_50], rax
0x18001f7ff  mov     r14, r9
0x18001f802  mov     rdi, r8
0x18001f805  mov     rsi, rdx
0x18001f808  mov     r13, rcx
0x18001f80b  mov     r15, [rbp+90h+arg_20]
0x18001f812  mov     r12, [rbp+90h+arg_28]
0x18001f819  mov     rbx, [rbp+90h+arg_30]
0x18001f820  mov     [rsp+190h+var_160], 0
0x18001f828  lea     rdx, [rbp+90h+var_B0]
0x18001f82c  mov     rcx, [rcx]
0x18001f82f  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f834  nop
0x18001f835  lea     rdx, [rbp+90h+var_E8]
0x18001f839  mov     rcx, [rax]
0x18001f83c  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f841  nop
0x18001f842  mov     rcx, [rbp+90h+var_A8]; this
0x18001f846  test    rcx, rcx
0x18001f849  jz      short loc_18001F850
0x18001f84b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f850  test    rsi, rsi
0x18001f853  jz      short loc_18001F886
0x18001f855  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f85c  lea     rcx, [rbp+90h+var_108]
0x18001f860  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f865  nop
0x18001f866  mov     r9d, 2000h
0x18001f86c  mov     r8, rsi
0x18001f86f  lea     rdx, [rbp+90h+var_108]
0x18001f873  lea     rcx, [rbp+90h+var_E8]
0x18001f877  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f87c  nop
0x18001f87d  lea     rcx, [rbp+90h+var_108]
0x18001f881  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f886  test    rdi, rdi
0x18001f889  jz      short loc_18001F8B6
0x18001f88b  lea     rdx, aSecondaryrepli; "SecondaryReplicationGroupName"
0x18001f892  lea     rcx, [rbp+90h+var_108]
0x18001f896  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f89b  nop
0x18001f89c  mov     r8, rdi
0x18001f89f  lea     rdx, [rbp+90h+var_108]
0x18001f8a3  lea     rcx, [rbp+90h+var_E8]
0x18001f8a7  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f8ac  nop
0x18001f8ad  lea     rcx, [rbp+90h+var_108]
0x18001f8b1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f8b6  test    r14, r14
0x18001f8b9  jz      short loc_18001F8E6
0x18001f8bb  lea     rdx, aSecondaryrepli_0; "SecondaryReplicationGroupId"
0x18001f8c2  lea     rcx, [rbp+90h+var_108]
0x18001f8c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f8cb  nop
0x18001f8cc  mov     r8, r14
0x18001f8cf  lea     rdx, [rbp+90h+var_108]
0x18001f8d3  lea     rcx, [rbp+90h+var_E8]
0x18001f8d7  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f8dc  nop
0x18001f8dd  lea     rcx, [rbp+90h+var_108]
0x18001f8e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f8e6  test    r15, r15
0x18001f8e9  jz      short loc_18001F916
0x18001f8eb  lea     rdx, aSecondarycompu; "SecondaryComputerName"
0x18001f8f2  lea     rcx, [rbp+90h+var_108]
0x18001f8f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f8fb  nop
0x18001f8fc  mov     r8, r15
0x18001f8ff  lea     rdx, [rbp+90h+var_108]
0x18001f903  lea     rcx, [rbp+90h+var_E8]
0x18001f907  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f90c  nop
0x18001f90d  lea     rcx, [rbp+90h+var_108]
0x18001f911  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f916  test    r12, r12
0x18001f919  jz      short loc_18001F946
0x18001f91b  lea     rdx, aPartnershipid; "PartnershipId"
0x18001f922  lea     rcx, [rbp+90h+var_108]
0x18001f926  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f92b  nop
0x18001f92c  mov     r8, r12
0x18001f92f  lea     rdx, [rbp+90h+var_108]
0x18001f933  lea     rcx, [rbp+90h+var_E8]
0x18001f937  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001f93c  nop
0x18001f93d  lea     rcx, [rbp+90h+var_108]
0x18001f941  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f946  test    rbx, rbx
0x18001f949  jz      short loc_18001F976
0x18001f94b  lea     rdx, aForce; "Force"
0x18001f952  lea     rcx, [rbp+90h+var_108]
0x18001f956  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f95b  nop
0x18001f95c  mov     r8, rbx
0x18001f95f  lea     rdx, [rbp+90h+var_108]
0x18001f963  lea     rcx, [rbp+90h+var_E8]
0x18001f967  call    ??$AddElement@_N@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NI@Z; mi::MiInstance::AddElement<bool>(std::wstring const &,bool const &,uint)
0x18001f96c  nop
0x18001f96d  lea     rcx, [rbp+90h+var_108]
0x18001f971  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f976  mov     rbx, [r13+0]
0x18001f97a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_7e5ba9f4ea2dfa71161ca5221569fea1_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_7e5ba9f4ea2dfa71161ca5221569fea1_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f981  mov     [rbp+90h+var_90], rax
0x18001f985  lea     rax, [rsp+190h+var_160]
0x18001f98a  mov     [rbp+90h+var_88], rax
0x18001f98e  lea     rax, [rbp+90h+var_90]
0x18001f992  mov     [rbp+90h+var_58], rax
0x18001f996  lea     rdx, aWvrsetprimaryr; "WvrSetPrimaryReplicationGroup"
0x18001f99d  lea     rcx, [rbp+90h+var_108]
0x18001f9a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9a6  nop
0x18001f9a7  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f9ae  lea     rcx, [rbp+90h+var_B0]
0x18001f9b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9b7  nop
0x18001f9b8  lea     rcx, [rbp+90h+var_90]
0x18001f9bc  mov     [rsp+190h+var_168], rcx
0x18001f9c1  lea     rcx, [rbp+90h+var_E8]
0x18001f9c5  mov     [rsp+190h+var_170], rcx
0x18001f9ca  lea     r9, [rbp+90h+var_108]
0x18001f9ce  mov     r8, rax
0x18001f9d1  lea     rdx, [rsp+190h+var_158]
0x18001f9d6  mov     rcx, rbx
0x18001f9d9  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f9de  nop
0x18001f9df  mov     rcx, rax; this
0x18001f9e2  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f9e7  nop
0x18001f9e8  lea     rcx, [rsp+190h+var_158]; this
0x18001f9ed  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f9f2  nop
0x18001f9f3  lea     rcx, [rbp+90h+var_B0]
0x18001f9f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f9fc  nop
0x18001f9fd  lea     rcx, [rbp+90h+var_108]
0x18001fa01  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fa06  nop
0x18001fa07  lea     rcx, [rbp+90h+var_90]
0x18001fa0b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001fa10  mov     ebx, [rsp+190h+var_160]
0x18001fa14  lea     rcx, [rbp+90h+var_E8]; this
0x18001fa18  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001fa1d  mov     eax, ebx
0x18001fa1f  mov     rcx, [rbp+90h+var_50]
0x18001fa23  xor     rcx, rsp; StackCookie
0x18001fa26  call    __security_check_cookie
0x18001fa2b  add     rsp, 158h
0x18001fa32  pop     r15
0x18001fa34  pop     r14
0x18001fa36  pop     r13
0x18001fa38  pop     r12
0x18001fa3a  pop     rdi
0x18001fa3b  pop     rsi
0x18001fa3c  pop     rbx
0x18001fa3d  pop     rbp
0x18001fa3e  retn
```
