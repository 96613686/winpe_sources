# wvr::MSFT_WvrAdminTasks::WvrSuspendReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001fa48`
- end: `0x18001fba3`
- name: `?WvrSuspendReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000b494`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001fa48`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001fb09`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrSuspendReplicationGroup(_QWORD *a1, __int64 a2)
{
  _QWORD *application; // rax
  __int64 v5; // rbx
  int v6; // eax
  mi::MiAsyncOperation *v7; // rax
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v12[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v13; // [rsp+B0h] [rbp-50h]
  _QWORD v14[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v15[56]; // [rsp+110h] [rbp+10h] BYREF

  v9 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v12);
  mi::MiApplication::CreateParameterSet(*application, v15);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  if ( a2 )
  {
    std::wstring::wstring(v11, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v15, v11, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v11);
  }
  v5 = *a1;
  v14[0] = &std::_Func_impl_no_alloc<_lambda_49067a5c4bd8eefca2466640b7c1351d_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v14[1] = &v9;
  v14[7] = v14;
  std::wstring::wstring(v11, L"WvrSuspendReplicationGroup");
  v6 = std::wstring::wstring(v12, L"MSFT_WvrAdminTasks");
  v7 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                 v5,
                                 (unsigned int)v10,
                                 v6,
                                 (unsigned int)v11,
                                 (__int64)v15,
                                 (__int64)v14);
  mi::MiAsyncOperation::Join(v7);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v10);
  std::wstring::_Tidy_deallocate(v12);
  std::wstring::_Tidy_deallocate(v11);
  std::_Func_class<void,>::~_Func_class<void,>(v14);
  LODWORD(v5) = v9;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001fa48  mov     [rsp-8+arg_10], rbx
0x18001fa4d  mov     [rsp-8+arg_18], rdi
0x18001fa52  push    rbp
0x18001fa53  lea     rbp, [rsp-50h]
0x18001fa58  sub     rsp, 150h
0x18001fa5f  mov     rax, cs:__security_cookie
0x18001fa66  xor     rax, rsp
0x18001fa69  mov     [rbp+50h+var_8], rax
0x18001fa6d  mov     rbx, rdx
0x18001fa70  mov     rdi, rcx
0x18001fa73  mov     [rsp+150h+var_120], 0
0x18001fa7b  lea     rdx, [rbp+50h+var_A8]
0x18001fa7f  mov     rcx, [rcx]
0x18001fa82  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001fa87  nop
0x18001fa88  lea     rdx, [rbp+50h+var_40]
0x18001fa8c  mov     rcx, [rax]
0x18001fa8f  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001fa94  nop
0x18001fa95  mov     rcx, [rbp+50h+var_A0]; this
0x18001fa99  test    rcx, rcx
0x18001fa9c  jz      short loc_18001FAA3
0x18001fa9e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001faa3  test    rbx, rbx
0x18001faa6  jz      short loc_18001FAD9
0x18001faa8  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001faaf  lea     rcx, [rbp+50h+var_C8]
0x18001fab3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001fab8  nop
0x18001fab9  mov     r9d, 2000h
0x18001fabf  mov     r8, rbx
0x18001fac2  lea     rdx, [rbp+50h+var_C8]
0x18001fac6  lea     rcx, [rbp+50h+var_40]
0x18001faca  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001facf  nop
0x18001fad0  lea     rcx, [rbp+50h+var_C8]
0x18001fad4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fad9  mov     rbx, [rdi]
0x18001fadc  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_49067a5c4bd8eefca2466640b7c1351d_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_49067a5c4bd8eefca2466640b7c1351d_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001fae3  mov     [rbp+50h+var_80], rax
0x18001fae7  lea     rax, [rsp+150h+var_120]
0x18001faec  mov     [rbp+50h+var_78], rax
0x18001faf0  lea     rax, [rbp+50h+var_80]
0x18001faf4  mov     [rbp+50h+var_48], rax
0x18001faf8  lea     rdx, aWvrsuspendrepl; "WvrSuspendReplicationGroup"
0x18001faff  lea     rcx, [rbp+50h+var_C8]
0x18001fb03  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001fb08  nop
0x18001fb09  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001fb10  lea     rcx, [rbp+50h+var_A8]
0x18001fb14  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001fb19  nop
0x18001fb1a  lea     rcx, [rbp+50h+var_80]
0x18001fb1e  mov     [rsp+150h+var_128], rcx
0x18001fb23  lea     rcx, [rbp+50h+var_40]
0x18001fb27  mov     [rsp+150h+var_130], rcx
0x18001fb2c  lea     r9, [rbp+50h+var_C8]
0x18001fb30  mov     r8, rax
0x18001fb33  lea     rdx, [rsp+150h+var_118]
0x18001fb38  mov     rcx, rbx
0x18001fb3b  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001fb40  nop
0x18001fb41  mov     rcx, rax; this
0x18001fb44  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001fb49  nop
0x18001fb4a  lea     rcx, [rsp+150h+var_118]; this
0x18001fb4f  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001fb54  nop
0x18001fb55  lea     rcx, [rbp+50h+var_A8]
0x18001fb59  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fb5e  nop
0x18001fb5f  lea     rcx, [rbp+50h+var_C8]
0x18001fb63  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fb68  nop
0x18001fb69  lea     rcx, [rbp+50h+var_80]
0x18001fb6d  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001fb72  mov     ebx, [rsp+150h+var_120]
0x18001fb76  lea     rcx, [rbp+50h+var_40]; this
0x18001fb7a  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001fb7f  mov     eax, ebx
0x18001fb81  mov     rcx, [rbp+50h+var_8]
0x18001fb85  xor     rcx, rsp; StackCookie
0x18001fb88  call    __security_check_cookie
0x18001fb8d  lea     r11, [rsp+150h+var_s0]
0x18001fb95  mov     rbx, [r11+20h]
0x18001fb99  mov     rdi, [r11+28h]
0x18001fb9d  mov     rsp, r11
0x18001fba0  pop     rbp
0x18001fba1  retn
```
