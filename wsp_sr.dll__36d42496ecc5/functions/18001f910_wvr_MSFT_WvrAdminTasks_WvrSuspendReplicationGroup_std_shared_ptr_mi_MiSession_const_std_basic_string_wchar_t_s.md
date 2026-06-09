# wvr::MSFT_WvrAdminTasks::WvrSuspendReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f910`
- end: `0x18001fa6a`
- name: `?WvrSuspendReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `346`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000b328`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001f910`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001f9d1`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrSuspendReplicationGroup(__int64 *a1, _QWORD *a2)
{
  __int64 *application; // rax
  __int64 v5; // rbx
  int v6; // eax
  mi::MiAsyncOperation::MiOperationArgs **v7; // rax
  enum _MI_CancellationReason v8; // edx
  __int64 v9; // rdx
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v14[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v15; // [rsp+B0h] [rbp-50h]
  _QWORD v16[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v17[7]; // [rsp+110h] [rbp+10h] BYREF

  v11 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v14);
  mi::MiApplication::CreateParameterSet(*application, v17);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v13, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v17, (int)v13, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v13);
  }
  v5 = *a1;
  v16[0] = &std::_Func_impl_no_alloc<_lambda_49067a5c4bd8eefca2466640b7c1351d_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v16[1] = &v11;
  v16[7] = v16;
  std::wstring::wstring((__int64)v13, (__int64)L"WvrSuspendReplicationGroup");
  v6 = std::wstring::wstring((__int64)v14, (__int64)L"MSFT_WvrAdminTasks");
  v7 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                   v5,
                                                   (__int64)v12,
                                                   v6,
                                                   (int)v13,
                                                   (__int64)v17,
                                                   (__int64)v16);
  mi::MiAsyncOperation::Join(v7);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v12, v8);
  std::wstring::_Tidy_deallocate((__int64)v14);
  std::wstring::_Tidy_deallocate((__int64)v13);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v16, v9);
  LODWORD(v5) = v11;
  mi::MiInstance::~MiInstance(v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f910  mov     [rsp-8+arg_10], rbx
0x18001f915  mov     [rsp-8+arg_18], rdi
0x18001f91a  push    rbp
0x18001f91b  lea     rbp, [rsp-50h]
0x18001f920  sub     rsp, 150h
0x18001f927  mov     rax, cs:__security_cookie
0x18001f92e  xor     rax, rsp
0x18001f931  mov     [rbp+50h+var_8], rax
0x18001f935  mov     rbx, rdx
0x18001f938  mov     rdi, rcx
0x18001f93b  mov     [rsp+150h+var_120], 0
0x18001f943  lea     rdx, [rbp+50h+var_A8]
0x18001f947  mov     rcx, [rcx]
0x18001f94a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f94f  nop
0x18001f950  lea     rdx, [rbp+50h+var_40]
0x18001f954  mov     rcx, [rax]
0x18001f957  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f95c  nop
0x18001f95d  mov     rcx, [rbp+50h+var_A0]; this
0x18001f961  test    rcx, rcx
0x18001f964  jz      short loc_18001F96B
0x18001f966  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f96b  test    rbx, rbx
0x18001f96e  jz      short loc_18001F9A1
0x18001f970  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f977  lea     rcx, [rbp+50h+var_C8]
0x18001f97b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f980  nop
0x18001f981  mov     r9d, 2000h
0x18001f987  mov     r8, rbx
0x18001f98a  lea     rdx, [rbp+50h+var_C8]
0x18001f98e  lea     rcx, [rbp+50h+var_40]
0x18001f992  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f997  nop
0x18001f998  lea     rcx, [rbp+50h+var_C8]
0x18001f99c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f9a1  mov     rbx, [rdi]
0x18001f9a4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_49067a5c4bd8eefca2466640b7c1351d_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_49067a5c4bd8eefca2466640b7c1351d_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f9ab  mov     [rbp+50h+var_80], rax
0x18001f9af  lea     rax, [rsp+150h+var_120]
0x18001f9b4  mov     [rbp+50h+var_78], rax
0x18001f9b8  lea     rax, [rbp+50h+var_80]
0x18001f9bc  mov     [rbp+50h+var_48], rax
0x18001f9c0  lea     rdx, aWvrsuspendrepl; "WvrSuspendReplicationGroup"
0x18001f9c7  lea     rcx, [rbp+50h+var_C8]
0x18001f9cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9d0  nop
0x18001f9d1  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f9d8  lea     rcx, [rbp+50h+var_A8]
0x18001f9dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9e1  nop
0x18001f9e2  lea     rcx, [rbp+50h+var_80]
0x18001f9e6  mov     [rsp+150h+var_128], rcx
0x18001f9eb  lea     rcx, [rbp+50h+var_40]
0x18001f9ef  mov     [rsp+150h+var_130], rcx
0x18001f9f4  lea     r9, [rbp+50h+var_C8]
0x18001f9f8  mov     r8, rax
0x18001f9fb  lea     rdx, [rsp+150h+var_118]
0x18001fa00  mov     rcx, rbx
0x18001fa03  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001fa08  nop
0x18001fa09  mov     rcx, rax; this
0x18001fa0c  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001fa11  nop
0x18001fa12  lea     rcx, [rsp+150h+var_118]; this
0x18001fa17  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001fa1c  nop
0x18001fa1d  lea     rcx, [rbp+50h+var_A8]
0x18001fa21  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fa26  nop
0x18001fa27  lea     rcx, [rbp+50h+var_C8]
0x18001fa2b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fa30  nop
0x18001fa31  lea     rcx, [rbp+50h+var_80]
0x18001fa35  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001fa3a  mov     ebx, [rsp+150h+var_120]
0x18001fa3e  lea     rcx, [rbp+50h+var_40]; this
0x18001fa42  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001fa47  mov     eax, ebx
0x18001fa49  mov     rcx, [rbp+50h+var_8]
0x18001fa4d  xor     rcx, rsp; StackCookie
0x18001fa50  call    __security_check_cookie
0x18001fa55  lea     r11, [rsp+150h+var_s0]
0x18001fa5d  mov     rbx, [r11+20h]
0x18001fa61  mov     rdi, [r11+28h]
0x18001fa65  mov     rsp, r11
0x18001fa68  pop     rbp
0x18001fa69  retn
```
