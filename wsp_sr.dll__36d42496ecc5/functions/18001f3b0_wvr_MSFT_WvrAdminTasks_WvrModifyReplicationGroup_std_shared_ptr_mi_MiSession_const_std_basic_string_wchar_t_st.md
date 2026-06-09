# wvr::MSFT_WvrAdminTasks::WvrModifyReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,uint const *,unsigned __int64 const *,bool const *,bool const *,bool const *,bool const *,uint const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f3b0`
- end: `0x18001f538`
- name: `?WvrModifyReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBIPEB_KPEB_N44421@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000b174`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001caec`
- `0x18001f3b0`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001f4a1`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrModifyReplicationGroup(__int64 *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 *application; // rax
  __int64 v8; // rbx
  int v9; // eax
  mi::MiAsyncOperation::MiOperationArgs **v10; // rax
  enum _MI_CancellationReason v11; // edx
  __int64 v12; // rdx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v17[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v18; // [rsp+B0h] [rbp-50h]
  _QWORD v19[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v20[7]; // [rsp+110h] [rbp+10h] BYREF

  v14 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v17);
  mi::MiApplication::CreateParameterSet(*application, v20);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v16, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v16, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v16);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v16, (__int64)L"ReplicationMode");
    mi::MiInstance::AddElement<unsigned int>(v20, v16, a4);
    std::wstring::_Tidy_deallocate((__int64)v16);
  }
  v8 = *a1;
  v19[0] = &std::_Func_impl_no_alloc<_lambda_d4bed6ea89c78a0f5f1f16ebba582772_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v19[1] = &v14;
  v19[7] = v19;
  std::wstring::wstring((__int64)v16, (__int64)L"WvrModifyReplicationGroup");
  v9 = std::wstring::wstring((__int64)v17, (__int64)L"MSFT_WvrAdminTasks");
  v10 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v8,
                                                    (__int64)v15,
                                                    v9,
                                                    (int)v16,
                                                    (__int64)v20,
                                                    (__int64)v19);
  mi::MiAsyncOperation::Join(v10);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v15, v11);
  std::wstring::_Tidy_deallocate((__int64)v17);
  std::wstring::_Tidy_deallocate((__int64)v16);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v19, v12);
  LODWORD(v8) = v14;
  mi::MiInstance::~MiInstance(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f3b0  mov     [rsp-8+arg_10], rbx
0x18001f3b5  push    rbp
0x18001f3b6  push    rsi
0x18001f3b7  push    rdi
0x18001f3b8  lea     rbp, [rsp-50h]
0x18001f3bd  sub     rsp, 150h
0x18001f3c4  mov     rax, cs:__security_cookie
0x18001f3cb  xor     rax, rsp
0x18001f3ce  mov     [rbp+60h+var_18], rax
0x18001f3d2  mov     rbx, r9
0x18001f3d5  mov     rdi, rdx
0x18001f3d8  mov     rsi, rcx
0x18001f3db  mov     [rsp+160h+var_130], 0
0x18001f3e3  lea     rdx, [rbp+60h+var_B8]
0x18001f3e7  mov     rcx, [rcx]
0x18001f3ea  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f3ef  nop
0x18001f3f0  lea     rdx, [rbp+60h+var_50]
0x18001f3f4  mov     rcx, [rax]
0x18001f3f7  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f3fc  nop
0x18001f3fd  mov     rcx, [rbp+60h+var_B0]; this
0x18001f401  test    rcx, rcx
0x18001f404  jz      short loc_18001F40B
0x18001f406  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f40b  test    rdi, rdi
0x18001f40e  jz      short loc_18001F441
0x18001f410  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f417  lea     rcx, [rbp+60h+var_D8]
0x18001f41b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f420  nop
0x18001f421  mov     r9d, 2000h
0x18001f427  mov     r8, rdi
0x18001f42a  lea     rdx, [rbp+60h+var_D8]
0x18001f42e  lea     rcx, [rbp+60h+var_50]
0x18001f432  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f437  nop
0x18001f438  lea     rcx, [rbp+60h+var_D8]
0x18001f43c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f441  test    rbx, rbx
0x18001f444  jz      short loc_18001F471
0x18001f446  lea     rdx, aReplicationmod; "ReplicationMode"
0x18001f44d  lea     rcx, [rbp+60h+var_D8]
0x18001f451  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f456  nop
0x18001f457  mov     r8, rbx
0x18001f45a  lea     rdx, [rbp+60h+var_D8]
0x18001f45e  lea     rcx, [rbp+60h+var_50]
0x18001f462  call    ??$AddElement@I@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBII@Z; mi::MiInstance::AddElement<uint>(std::wstring const &,uint const &,uint)
0x18001f467  nop
0x18001f468  lea     rcx, [rbp+60h+var_D8]
0x18001f46c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f471  mov     rbx, [rsi]
0x18001f474  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d4bed6ea89c78a0f5f1f16ebba582772_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d4bed6ea89c78a0f5f1f16ebba582772_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f47b  mov     [rbp+60h+var_90], rax
0x18001f47f  lea     rax, [rsp+160h+var_130]
0x18001f484  mov     [rbp+60h+var_88], rax
0x18001f488  lea     rax, [rbp+60h+var_90]
0x18001f48c  mov     [rbp+60h+var_58], rax
0x18001f490  lea     rdx, aWvrmodifyrepli; "WvrModifyReplicationGroup"
0x18001f497  lea     rcx, [rbp+60h+var_D8]
0x18001f49b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f4a0  nop
0x18001f4a1  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f4a8  lea     rcx, [rbp+60h+var_B8]
0x18001f4ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f4b1  nop
0x18001f4b2  lea     rcx, [rbp+60h+var_90]
0x18001f4b6  mov     [rsp+160h+var_138], rcx
0x18001f4bb  lea     rcx, [rbp+60h+var_50]
0x18001f4bf  mov     [rsp+160h+var_140], rcx
0x18001f4c4  lea     r9, [rbp+60h+var_D8]
0x18001f4c8  mov     r8, rax
0x18001f4cb  lea     rdx, [rsp+160h+var_128]
0x18001f4d0  mov     rcx, rbx
0x18001f4d3  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f4d8  nop
0x18001f4d9  mov     rcx, rax; this
0x18001f4dc  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f4e1  nop
0x18001f4e2  lea     rcx, [rsp+160h+var_128]; this
0x18001f4e7  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f4ec  nop
0x18001f4ed  lea     rcx, [rbp+60h+var_B8]
0x18001f4f1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f4f6  nop
0x18001f4f7  lea     rcx, [rbp+60h+var_D8]
0x18001f4fb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f500  nop
0x18001f501  lea     rcx, [rbp+60h+var_90]
0x18001f505  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f50a  mov     ebx, [rsp+160h+var_130]
0x18001f50e  lea     rcx, [rbp+60h+var_50]; this
0x18001f512  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f517  mov     eax, ebx
0x18001f519  mov     rcx, [rbp+60h+var_18]
0x18001f51d  xor     rcx, rsp; StackCookie
0x18001f520  call    __security_check_cookie
0x18001f525  mov     rbx, [rsp+160h+arg_10]
0x18001f52d  add     rsp, 150h
0x18001f534  pop     rdi
0x18001f535  pop     rsi
0x18001f536  pop     rbp
0x18001f537  retn
```
