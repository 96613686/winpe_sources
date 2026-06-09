# wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f18c`
- end: `0x18001f34e`
- name: `?WvrCreateReplicationPartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111@Z`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a2c4`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001f18c`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001f2bb`: `MSFT_WvrAdminTasks`
- `0x18001f25a`: `TargetComputerName`
- `0x18001f2aa`: `WvrCreateReplicationPartnership`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *application; // rax
  __int64 v9; // rbx
  int v10; // eax
  mi::MiAsyncOperation *v11; // rax
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v16[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v17; // [rsp+B0h] [rbp-50h]
  _BYTE v18[56]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v19[8]; // [rsp+100h] [rbp+0h] BYREF

  v13 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v16);
  mi::MiApplication::CreateParameterSet(*application, v18);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( a2 )
  {
    std::wstring::wstring(v15, L"SourceReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v18, v15, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v15);
  }
  if ( a3 )
  {
    std::wstring::wstring(v15, L"TargetReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v18, v15, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v15);
  }
  if ( a4 )
  {
    std::wstring::wstring(v15, L"TargetComputerName");
    mi::MiInstance::AddElement<std::wstring>(v18, v15, a4, 0x2000);
    std::wstring::_Tidy_deallocate(v15);
  }
  v9 = *a1;
  v19[0] = &std::_Func_impl_no_alloc<_lambda_384ead2774eecb21d450a830335cc63e_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v19[1] = &v13;
  v19[7] = v19;
  std::wstring::wstring(v15, L"WvrCreateReplicationPartnership");
  v10 = std::wstring::wstring(v16, L"MSFT_WvrAdminTasks");
  v11 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v9,
                                  (unsigned int)v14,
                                  v10,
                                  (unsigned int)v15,
                                  (__int64)v18,
                                  (__int64)v19);
  mi::MiAsyncOperation::Join(v11);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v14);
  std::wstring::_Tidy_deallocate(v16);
  std::wstring::_Tidy_deallocate(v15);
  std::_Func_class<void,>::~_Func_class<void,>(v19);
  LODWORD(v9) = v13;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f18c  push    rbp
0x18001f18e  push    rbx
0x18001f18f  push    rsi
0x18001f190  push    rdi
0x18001f191  push    r14
0x18001f193  lea     rbp, [rsp-50h]
0x18001f198  sub     rsp, 150h
0x18001f19f  mov     rax, cs:__security_cookie
0x18001f1a6  xor     rax, rsp
0x18001f1a9  mov     [rbp+70h+var_30], rax
0x18001f1ad  mov     rbx, r9
0x18001f1b0  mov     rsi, r8
0x18001f1b3  mov     rdi, rdx
0x18001f1b6  mov     r14, rcx
0x18001f1b9  mov     [rsp+170h+var_140], 0
0x18001f1c1  lea     rdx, [rbp+70h+var_C8]
0x18001f1c5  mov     rcx, [rcx]
0x18001f1c8  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f1cd  nop
0x18001f1ce  lea     rdx, [rbp+70h+var_A8]
0x18001f1d2  mov     rcx, [rax]
0x18001f1d5  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f1da  nop
0x18001f1db  mov     rcx, [rbp+70h+var_C0]; this
0x18001f1df  test    rcx, rcx
0x18001f1e2  jz      short loc_18001F1E9
0x18001f1e4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f1e9  test    rdi, rdi
0x18001f1ec  jz      short loc_18001F21F
0x18001f1ee  lea     rdx, aSourcereplicat; "SourceReplicationGroupName"
0x18001f1f5  lea     rcx, [rbp+70h+var_E8]
0x18001f1f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f1fe  nop
0x18001f1ff  mov     r9d, 2000h
0x18001f205  mov     r8, rdi
0x18001f208  lea     rdx, [rbp+70h+var_E8]
0x18001f20c  lea     rcx, [rbp+70h+var_A8]
0x18001f210  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f215  nop
0x18001f216  lea     rcx, [rbp+70h+var_E8]
0x18001f21a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f21f  test    rsi, rsi
0x18001f222  jz      short loc_18001F255
0x18001f224  lea     rdx, aTargetreplicat_1; "TargetReplicationGroupName"
0x18001f22b  lea     rcx, [rbp+70h+var_E8]
0x18001f22f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f234  nop
0x18001f235  mov     r9d, 2000h
0x18001f23b  mov     r8, rsi
0x18001f23e  lea     rdx, [rbp+70h+var_E8]
0x18001f242  lea     rcx, [rbp+70h+var_A8]
0x18001f246  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f24b  nop
0x18001f24c  lea     rcx, [rbp+70h+var_E8]
0x18001f250  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f255  test    rbx, rbx
0x18001f258  jz      short loc_18001F28B
0x18001f25a  lea     rdx, aTargetcomputer; "TargetComputerName"
0x18001f261  lea     rcx, [rbp+70h+var_E8]
0x18001f265  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f26a  nop
0x18001f26b  mov     r9d, 2000h
0x18001f271  mov     r8, rbx
0x18001f274  lea     rdx, [rbp+70h+var_E8]
0x18001f278  lea     rcx, [rbp+70h+var_A8]
0x18001f27c  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f281  nop
0x18001f282  lea     rcx, [rbp+70h+var_E8]
0x18001f286  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f28b  mov     rbx, [r14]
0x18001f28e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_384ead2774eecb21d450a830335cc63e_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_384ead2774eecb21d450a830335cc63e_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f295  mov     [rbp+70h+var_70], rax
0x18001f299  lea     rax, [rsp+170h+var_140]
0x18001f29e  mov     [rbp+70h+var_68], rax
0x18001f2a2  lea     rax, [rbp+70h+var_70]
0x18001f2a6  mov     [rbp+70h+var_38], rax
0x18001f2aa  lea     rdx, aWvrcreaterepli; "WvrCreateReplicationPartnership"
0x18001f2b1  lea     rcx, [rbp+70h+var_E8]
0x18001f2b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f2ba  nop
0x18001f2bb  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f2c2  lea     rcx, [rbp+70h+var_C8]
0x18001f2c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f2cb  nop
0x18001f2cc  lea     rcx, [rbp+70h+var_70]
0x18001f2d0  mov     [rsp+170h+var_148], rcx
0x18001f2d5  lea     rcx, [rbp+70h+var_A8]
0x18001f2d9  mov     [rsp+170h+var_150], rcx
0x18001f2de  lea     r9, [rbp+70h+var_E8]
0x18001f2e2  mov     r8, rax
0x18001f2e5  lea     rdx, [rsp+170h+var_138]
0x18001f2ea  mov     rcx, rbx
0x18001f2ed  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f2f2  nop
0x18001f2f3  mov     rcx, rax; this
0x18001f2f6  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f2fb  nop
0x18001f2fc  lea     rcx, [rsp+170h+var_138]; this
0x18001f301  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f306  nop
0x18001f307  lea     rcx, [rbp+70h+var_C8]
0x18001f30b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f310  nop
0x18001f311  lea     rcx, [rbp+70h+var_E8]
0x18001f315  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f31a  nop
0x18001f31b  lea     rcx, [rbp+70h+var_70]
0x18001f31f  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f324  mov     ebx, [rsp+170h+var_140]
0x18001f328  lea     rcx, [rbp+70h+var_A8]; this
0x18001f32c  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f331  mov     eax, ebx
0x18001f333  mov     rcx, [rbp+70h+var_30]
0x18001f337  xor     rcx, rsp; StackCookie
0x18001f33a  call    __security_check_cookie
0x18001f33f  add     rsp, 150h
0x18001f346  pop     r14
0x18001f348  pop     rdi
0x18001f349  pop     rsi
0x18001f34a  pop     rbx
0x18001f34b  pop     rbp
0x18001f34c  retn
```
