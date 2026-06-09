# wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,bool const *)

- ea: `0x18001f354`
- end: `0x18001f4dd`
- name: `?WvrDeleteReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEB_N@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000a4b0`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001ccf4`
- `0x18001f354`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001f445`: `MSFT_WvrAdminTasks`
- `0x18001f434`: `WvrDeleteReplicationGroup`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *application; // rax
  __int64 v7; // rbx
  int v8; // eax
  mi::MiAsyncOperation *v9; // rax
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v14[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v15; // [rsp+B0h] [rbp-50h]
  _QWORD v16[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v17[56]; // [rsp+110h] [rbp+10h] BYREF

  v11 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v14);
  mi::MiApplication::CreateParameterSet(*application, v17);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( a2 )
  {
    std::wstring::wstring(v13, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v17, v13, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v13);
  }
  if ( a3 )
  {
    std::wstring::wstring(v13, L"FullCleanup");
    mi::MiInstance::AddElement<bool>(v17, v13, a3);
    std::wstring::_Tidy_deallocate(v13);
  }
  v7 = *a1;
  v16[0] = &std::_Func_impl_no_alloc<_lambda_47582d3328fd0554403824d9fc60f740_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v16[1] = &v11;
  v16[7] = v16;
  std::wstring::wstring(v13, L"WvrDeleteReplicationGroup");
  v8 = std::wstring::wstring(v14, L"MSFT_WvrAdminTasks");
  v9 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                 v7,
                                 (unsigned int)v12,
                                 v8,
                                 (unsigned int)v13,
                                 (__int64)v17,
                                 (__int64)v16);
  mi::MiAsyncOperation::Join(v9);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v12);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v13);
  std::_Func_class<void,>::~_Func_class<void,>(v16);
  LODWORD(v7) = v11;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001f354  mov     [rsp-8+arg_18], rbx
0x18001f359  push    rbp
0x18001f35a  push    rsi
0x18001f35b  push    rdi
0x18001f35c  lea     rbp, [rsp-50h]
0x18001f361  sub     rsp, 150h
0x18001f368  mov     rax, cs:__security_cookie
0x18001f36f  xor     rax, rsp
0x18001f372  mov     [rbp+60h+var_18], rax
0x18001f376  mov     rbx, r8
0x18001f379  mov     rdi, rdx
0x18001f37c  mov     rsi, rcx
0x18001f37f  mov     [rsp+160h+var_130], 0
0x18001f387  lea     rdx, [rbp+60h+var_B8]
0x18001f38b  mov     rcx, [rcx]
0x18001f38e  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f393  nop
0x18001f394  lea     rdx, [rbp+60h+var_50]
0x18001f398  mov     rcx, [rax]
0x18001f39b  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f3a0  nop
0x18001f3a1  mov     rcx, [rbp+60h+var_B0]; this
0x18001f3a5  test    rcx, rcx
0x18001f3a8  jz      short loc_18001F3AF
0x18001f3aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f3af  test    rdi, rdi
0x18001f3b2  jz      short loc_18001F3E5
0x18001f3b4  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f3bb  lea     rcx, [rbp+60h+var_D8]
0x18001f3bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f3c4  nop
0x18001f3c5  mov     r9d, 2000h
0x18001f3cb  mov     r8, rdi
0x18001f3ce  lea     rdx, [rbp+60h+var_D8]
0x18001f3d2  lea     rcx, [rbp+60h+var_50]
0x18001f3d6  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f3db  nop
0x18001f3dc  lea     rcx, [rbp+60h+var_D8]
0x18001f3e0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f3e5  test    rbx, rbx
0x18001f3e8  jz      short loc_18001F415
0x18001f3ea  lea     rdx, aFullcleanup; "FullCleanup"
0x18001f3f1  lea     rcx, [rbp+60h+var_D8]
0x18001f3f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f3fa  nop
0x18001f3fb  mov     r8, rbx
0x18001f3fe  lea     rdx, [rbp+60h+var_D8]
0x18001f402  lea     rcx, [rbp+60h+var_50]
0x18001f406  call    ??$AddElement@_N@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NI@Z; mi::MiInstance::AddElement<bool>(std::wstring const &,bool const &,uint)
0x18001f40b  nop
0x18001f40c  lea     rcx, [rbp+60h+var_D8]
0x18001f410  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f415  mov     rbx, [rsi]
0x18001f418  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_47582d3328fd0554403824d9fc60f740_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_47582d3328fd0554403824d9fc60f740_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f41f  mov     [rbp+60h+var_90], rax
0x18001f423  lea     rax, [rsp+160h+var_130]
0x18001f428  mov     [rbp+60h+var_88], rax
0x18001f42c  lea     rax, [rbp+60h+var_90]
0x18001f430  mov     [rbp+60h+var_58], rax
0x18001f434  lea     rdx, aWvrdeleterepli; "WvrDeleteReplicationGroup"
0x18001f43b  lea     rcx, [rbp+60h+var_D8]
0x18001f43f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f444  nop
0x18001f445  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f44c  lea     rcx, [rbp+60h+var_B8]
0x18001f450  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f455  nop
0x18001f456  lea     rcx, [rbp+60h+var_90]
0x18001f45a  mov     [rsp+160h+var_138], rcx
0x18001f45f  lea     rcx, [rbp+60h+var_50]
0x18001f463  mov     [rsp+160h+var_140], rcx
0x18001f468  lea     r9, [rbp+60h+var_D8]
0x18001f46c  mov     r8, rax
0x18001f46f  lea     rdx, [rsp+160h+var_128]
0x18001f474  mov     rcx, rbx
0x18001f477  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f47c  nop
0x18001f47d  mov     rcx, rax; this
0x18001f480  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f485  nop
0x18001f486  lea     rcx, [rsp+160h+var_128]; this
0x18001f48b  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f490  nop
0x18001f491  lea     rcx, [rbp+60h+var_B8]
0x18001f495  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f49a  nop
0x18001f49b  lea     rcx, [rbp+60h+var_D8]
0x18001f49f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f4a4  nop
0x18001f4a5  lea     rcx, [rbp+60h+var_90]
0x18001f4a9  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f4ae  mov     ebx, [rsp+160h+var_130]
0x18001f4b2  lea     rcx, [rbp+60h+var_50]; this
0x18001f4b6  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f4bb  mov     eax, ebx
0x18001f4bd  mov     rcx, [rbp+60h+var_18]
0x18001f4c1  xor     rcx, rsp; StackCookie
0x18001f4c4  call    __security_check_cookie
0x18001f4c9  mov     rbx, [rsp+160h+arg_18]
0x18001f4d1  add     rsp, 150h
0x18001f4d8  pop     rdi
0x18001f4d9  pop     rsi
0x18001f4da  pop     rbp
0x18001f4db  retn
```
