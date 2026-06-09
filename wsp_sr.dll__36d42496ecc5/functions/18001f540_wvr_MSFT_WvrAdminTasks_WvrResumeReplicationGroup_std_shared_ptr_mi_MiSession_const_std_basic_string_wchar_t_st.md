# wvr::MSFT_WvrAdminTasks::WvrResumeReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f540`
- end: `0x18001f69a`
- name: `?WvrResumeReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `346`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000ad64`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001f540`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001f601`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrResumeReplicationGroup(__int64 *a1, _QWORD *a2)
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
  v16[0] = &std::_Func_impl_no_alloc<_lambda_89fe832ff5635dabd41c7c166c209cb3_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v16[1] = &v11;
  v16[7] = v16;
  std::wstring::wstring((__int64)v13, (__int64)L"WvrResumeReplicationGroup");
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
0x18001f540  mov     [rsp-8+arg_10], rbx
0x18001f545  mov     [rsp-8+arg_18], rdi
0x18001f54a  push    rbp
0x18001f54b  lea     rbp, [rsp-50h]
0x18001f550  sub     rsp, 150h
0x18001f557  mov     rax, cs:__security_cookie
0x18001f55e  xor     rax, rsp
0x18001f561  mov     [rbp+50h+var_8], rax
0x18001f565  mov     rbx, rdx
0x18001f568  mov     rdi, rcx
0x18001f56b  mov     [rsp+150h+var_120], 0
0x18001f573  lea     rdx, [rbp+50h+var_A8]
0x18001f577  mov     rcx, [rcx]
0x18001f57a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f57f  nop
0x18001f580  lea     rdx, [rbp+50h+var_40]
0x18001f584  mov     rcx, [rax]
0x18001f587  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f58c  nop
0x18001f58d  mov     rcx, [rbp+50h+var_A0]; this
0x18001f591  test    rcx, rcx
0x18001f594  jz      short loc_18001F59B
0x18001f596  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f59b  test    rbx, rbx
0x18001f59e  jz      short loc_18001F5D1
0x18001f5a0  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f5a7  lea     rcx, [rbp+50h+var_C8]
0x18001f5ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f5b0  nop
0x18001f5b1  mov     r9d, 2000h
0x18001f5b7  mov     r8, rbx
0x18001f5ba  lea     rdx, [rbp+50h+var_C8]
0x18001f5be  lea     rcx, [rbp+50h+var_40]
0x18001f5c2  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f5c7  nop
0x18001f5c8  lea     rcx, [rbp+50h+var_C8]
0x18001f5cc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f5d1  mov     rbx, [rdi]
0x18001f5d4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_89fe832ff5635dabd41c7c166c209cb3_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_89fe832ff5635dabd41c7c166c209cb3_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f5db  mov     [rbp+50h+var_80], rax
0x18001f5df  lea     rax, [rsp+150h+var_120]
0x18001f5e4  mov     [rbp+50h+var_78], rax
0x18001f5e8  lea     rax, [rbp+50h+var_80]
0x18001f5ec  mov     [rbp+50h+var_48], rax
0x18001f5f0  lea     rdx, aWvrresumerepli; "WvrResumeReplicationGroup"
0x18001f5f7  lea     rcx, [rbp+50h+var_C8]
0x18001f5fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f600  nop
0x18001f601  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f608  lea     rcx, [rbp+50h+var_A8]
0x18001f60c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f611  nop
0x18001f612  lea     rcx, [rbp+50h+var_80]
0x18001f616  mov     [rsp+150h+var_128], rcx
0x18001f61b  lea     rcx, [rbp+50h+var_40]
0x18001f61f  mov     [rsp+150h+var_130], rcx
0x18001f624  lea     r9, [rbp+50h+var_C8]
0x18001f628  mov     r8, rax
0x18001f62b  lea     rdx, [rsp+150h+var_118]
0x18001f630  mov     rcx, rbx
0x18001f633  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f638  nop
0x18001f639  mov     rcx, rax; this
0x18001f63c  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f641  nop
0x18001f642  lea     rcx, [rsp+150h+var_118]; this
0x18001f647  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f64c  nop
0x18001f64d  lea     rcx, [rbp+50h+var_A8]
0x18001f651  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f656  nop
0x18001f657  lea     rcx, [rbp+50h+var_C8]
0x18001f65b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f660  nop
0x18001f661  lea     rcx, [rbp+50h+var_80]
0x18001f665  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f66a  mov     ebx, [rsp+150h+var_120]
0x18001f66e  lea     rcx, [rbp+50h+var_40]; this
0x18001f672  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f677  mov     eax, ebx
0x18001f679  mov     rcx, [rbp+50h+var_8]
0x18001f67d  xor     rcx, rsp; StackCookie
0x18001f680  call    __security_check_cookie
0x18001f685  lea     r11, [rsp+150h+var_s0]
0x18001f68d  mov     rbx, [r11+20h]
0x18001f691  mov     rdi, [r11+28h]
0x18001f695  mov     rsp, r11
0x18001f698  pop     rbp
0x18001f699  retn
```
