# wvr::MSFT_WvrAdminTasks::WvrResumeReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f674`
- end: `0x18001f7cf`
- name: `?WvrResumeReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18000aecc`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001f674`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001f735`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrResumeReplicationGroup(_QWORD *a1, __int64 a2)
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
  v14[0] = &std::_Func_impl_no_alloc<_lambda_89fe832ff5635dabd41c7c166c209cb3_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v14[1] = &v9;
  v14[7] = v14;
  std::wstring::wstring(v11, L"WvrResumeReplicationGroup");
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
0x18001f674  mov     [rsp-8+arg_10], rbx
0x18001f679  mov     [rsp-8+arg_18], rdi
0x18001f67e  push    rbp
0x18001f67f  lea     rbp, [rsp-50h]
0x18001f684  sub     rsp, 150h
0x18001f68b  mov     rax, cs:__security_cookie
0x18001f692  xor     rax, rsp
0x18001f695  mov     [rbp+50h+var_8], rax
0x18001f699  mov     rbx, rdx
0x18001f69c  mov     rdi, rcx
0x18001f69f  mov     [rsp+150h+var_120], 0
0x18001f6a7  lea     rdx, [rbp+50h+var_A8]
0x18001f6ab  mov     rcx, [rcx]
0x18001f6ae  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f6b3  nop
0x18001f6b4  lea     rdx, [rbp+50h+var_40]
0x18001f6b8  mov     rcx, [rax]
0x18001f6bb  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f6c0  nop
0x18001f6c1  mov     rcx, [rbp+50h+var_A0]; this
0x18001f6c5  test    rcx, rcx
0x18001f6c8  jz      short loc_18001F6CF
0x18001f6ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f6cf  test    rbx, rbx
0x18001f6d2  jz      short loc_18001F705
0x18001f6d4  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f6db  lea     rcx, [rbp+50h+var_C8]
0x18001f6df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f6e4  nop
0x18001f6e5  mov     r9d, 2000h
0x18001f6eb  mov     r8, rbx
0x18001f6ee  lea     rdx, [rbp+50h+var_C8]
0x18001f6f2  lea     rcx, [rbp+50h+var_40]
0x18001f6f6  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f6fb  nop
0x18001f6fc  lea     rcx, [rbp+50h+var_C8]
0x18001f700  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f705  mov     rbx, [rdi]
0x18001f708  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_89fe832ff5635dabd41c7c166c209cb3_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_89fe832ff5635dabd41c7c166c209cb3_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f70f  mov     [rbp+50h+var_80], rax
0x18001f713  lea     rax, [rsp+150h+var_120]
0x18001f718  mov     [rbp+50h+var_78], rax
0x18001f71c  lea     rax, [rbp+50h+var_80]
0x18001f720  mov     [rbp+50h+var_48], rax
0x18001f724  lea     rdx, aWvrresumerepli; "WvrResumeReplicationGroup"
0x18001f72b  lea     rcx, [rbp+50h+var_C8]
0x18001f72f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f734  nop
0x18001f735  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f73c  lea     rcx, [rbp+50h+var_A8]
0x18001f740  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f745  nop
0x18001f746  lea     rcx, [rbp+50h+var_80]
0x18001f74a  mov     [rsp+150h+var_128], rcx
0x18001f74f  lea     rcx, [rbp+50h+var_40]
0x18001f753  mov     [rsp+150h+var_130], rcx
0x18001f758  lea     r9, [rbp+50h+var_C8]
0x18001f75c  mov     r8, rax
0x18001f75f  lea     rdx, [rsp+150h+var_118]
0x18001f764  mov     rcx, rbx
0x18001f767  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f76c  nop
0x18001f76d  mov     rcx, rax; this
0x18001f770  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f775  nop
0x18001f776  lea     rcx, [rsp+150h+var_118]; this
0x18001f77b  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f780  nop
0x18001f781  lea     rcx, [rbp+50h+var_A8]
0x18001f785  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f78a  nop
0x18001f78b  lea     rcx, [rbp+50h+var_C8]
0x18001f78f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f794  nop
0x18001f795  lea     rcx, [rbp+50h+var_80]
0x18001f799  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f79e  mov     ebx, [rsp+150h+var_120]
0x18001f7a2  lea     rcx, [rbp+50h+var_40]; this
0x18001f7a6  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f7ab  mov     eax, ebx
0x18001f7ad  mov     rcx, [rbp+50h+var_8]
0x18001f7b1  xor     rcx, rsp; StackCookie
0x18001f7b4  call    __security_check_cookie
0x18001f7b9  lea     r11, [rsp+150h+var_s0]
0x18001f7c1  mov     rbx, [r11+20h]
0x18001f7c5  mov     rdi, [r11+28h]
0x18001f7c9  mov     rsp, r11
0x18001f7cc  pop     rbp
0x18001f7cd  retn
```
