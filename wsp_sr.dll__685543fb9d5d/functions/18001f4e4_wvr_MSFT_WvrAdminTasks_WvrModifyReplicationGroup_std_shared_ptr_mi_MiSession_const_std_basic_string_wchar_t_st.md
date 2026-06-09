# wvr::MSFT_WvrAdminTasks::WvrModifyReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,uint const *,unsigned __int64 const *,bool const *,bool const *,bool const *,bool const *,uint const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f4e4`
- end: `0x18001f66d`
- name: `?WvrModifyReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBIPEB_KPEB_N44421@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000b2dc`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001cbf0`
- `0x18001f4e4`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001f5d5`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrModifyReplicationGroup(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *application; // rax
  __int64 v8; // rbx
  int v9; // eax
  mi::MiAsyncOperation *v10; // rax
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v15[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v16; // [rsp+B0h] [rbp-50h]
  _QWORD v17[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v18[56]; // [rsp+110h] [rbp+10h] BYREF

  v12 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v15);
  mi::MiApplication::CreateParameterSet(*application, v18);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( a2 )
  {
    std::wstring::wstring(v14, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v18, v14, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v14);
  }
  if ( a4 )
  {
    std::wstring::wstring(v14, L"ReplicationMode");
    mi::MiInstance::AddElement<unsigned int>(v18, v14, a4);
    std::wstring::_Tidy_deallocate(v14);
  }
  v8 = *a1;
  v17[0] = &std::_Func_impl_no_alloc<_lambda_d4bed6ea89c78a0f5f1f16ebba582772_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v17[1] = &v12;
  v17[7] = v17;
  std::wstring::wstring(v14, L"WvrModifyReplicationGroup");
  v9 = std::wstring::wstring(v15, L"MSFT_WvrAdminTasks");
  v10 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v8,
                                  (unsigned int)v13,
                                  v9,
                                  (unsigned int)v14,
                                  (__int64)v18,
                                  (__int64)v17);
  mi::MiAsyncOperation::Join(v10);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v13);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v14);
  std::_Func_class<void,>::~_Func_class<void,>(v17);
  LODWORD(v8) = v12;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f4e4  mov     [rsp-8+arg_10], rbx
0x18001f4e9  push    rbp
0x18001f4ea  push    rsi
0x18001f4eb  push    rdi
0x18001f4ec  lea     rbp, [rsp-50h]
0x18001f4f1  sub     rsp, 150h
0x18001f4f8  mov     rax, cs:__security_cookie
0x18001f4ff  xor     rax, rsp
0x18001f502  mov     [rbp+60h+var_18], rax
0x18001f506  mov     rbx, r9
0x18001f509  mov     rdi, rdx
0x18001f50c  mov     rsi, rcx
0x18001f50f  mov     [rsp+160h+var_130], 0
0x18001f517  lea     rdx, [rbp+60h+var_B8]
0x18001f51b  mov     rcx, [rcx]
0x18001f51e  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f523  nop
0x18001f524  lea     rdx, [rbp+60h+var_50]
0x18001f528  mov     rcx, [rax]
0x18001f52b  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f530  nop
0x18001f531  mov     rcx, [rbp+60h+var_B0]; this
0x18001f535  test    rcx, rcx
0x18001f538  jz      short loc_18001F53F
0x18001f53a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f53f  test    rdi, rdi
0x18001f542  jz      short loc_18001F575
0x18001f544  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f54b  lea     rcx, [rbp+60h+var_D8]
0x18001f54f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f554  nop
0x18001f555  mov     r9d, 2000h
0x18001f55b  mov     r8, rdi
0x18001f55e  lea     rdx, [rbp+60h+var_D8]
0x18001f562  lea     rcx, [rbp+60h+var_50]
0x18001f566  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f56b  nop
0x18001f56c  lea     rcx, [rbp+60h+var_D8]
0x18001f570  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f575  test    rbx, rbx
0x18001f578  jz      short loc_18001F5A5
0x18001f57a  lea     rdx, aReplicationmod; "ReplicationMode"
0x18001f581  lea     rcx, [rbp+60h+var_D8]
0x18001f585  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f58a  nop
0x18001f58b  mov     r8, rbx
0x18001f58e  lea     rdx, [rbp+60h+var_D8]
0x18001f592  lea     rcx, [rbp+60h+var_50]
0x18001f596  call    ??$AddElement@I@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBII@Z; mi::MiInstance::AddElement<uint>(std::wstring const &,uint const &,uint)
0x18001f59b  nop
0x18001f59c  lea     rcx, [rbp+60h+var_D8]
0x18001f5a0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f5a5  mov     rbx, [rsi]
0x18001f5a8  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d4bed6ea89c78a0f5f1f16ebba582772_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d4bed6ea89c78a0f5f1f16ebba582772_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f5af  mov     [rbp+60h+var_90], rax
0x18001f5b3  lea     rax, [rsp+160h+var_130]
0x18001f5b8  mov     [rbp+60h+var_88], rax
0x18001f5bc  lea     rax, [rbp+60h+var_90]
0x18001f5c0  mov     [rbp+60h+var_58], rax
0x18001f5c4  lea     rdx, aWvrmodifyrepli; "WvrModifyReplicationGroup"
0x18001f5cb  lea     rcx, [rbp+60h+var_D8]
0x18001f5cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f5d4  nop
0x18001f5d5  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f5dc  lea     rcx, [rbp+60h+var_B8]
0x18001f5e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f5e5  nop
0x18001f5e6  lea     rcx, [rbp+60h+var_90]
0x18001f5ea  mov     [rsp+160h+var_138], rcx
0x18001f5ef  lea     rcx, [rbp+60h+var_50]
0x18001f5f3  mov     [rsp+160h+var_140], rcx
0x18001f5f8  lea     r9, [rbp+60h+var_D8]
0x18001f5fc  mov     r8, rax
0x18001f5ff  lea     rdx, [rsp+160h+var_128]
0x18001f604  mov     rcx, rbx
0x18001f607  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f60c  nop
0x18001f60d  mov     rcx, rax; this
0x18001f610  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f615  nop
0x18001f616  lea     rcx, [rsp+160h+var_128]; this
0x18001f61b  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f620  nop
0x18001f621  lea     rcx, [rbp+60h+var_B8]
0x18001f625  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f62a  nop
0x18001f62b  lea     rcx, [rbp+60h+var_D8]
0x18001f62f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f634  nop
0x18001f635  lea     rcx, [rbp+60h+var_90]
0x18001f639  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f63e  mov     ebx, [rsp+160h+var_130]
0x18001f642  lea     rcx, [rbp+60h+var_50]; this
0x18001f646  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f64b  mov     eax, ebx
0x18001f64d  mov     rcx, [rbp+60h+var_18]
0x18001f651  xor     rcx, rsp; StackCookie
0x18001f654  call    __security_check_cookie
0x18001f659  mov     rbx, [rsp+160h+arg_10]
0x18001f661  add     rsp, 150h
0x18001f668  pop     rdi
0x18001f669  pop     rsi
0x18001f66a  pop     rbp
0x18001f66b  retn
```
