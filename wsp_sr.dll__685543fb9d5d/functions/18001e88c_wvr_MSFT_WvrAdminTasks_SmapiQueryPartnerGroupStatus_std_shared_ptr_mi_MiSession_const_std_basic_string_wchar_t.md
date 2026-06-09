# wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerGroupStatus(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,ushort *,_MI_Datetime *,uint *)

- ea: `0x18001e88c`
- end: `0x18001ea00`
- name: `?SmapiQueryPartnerGroupStatus@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEAGPEAU_MI_Datetime@@PEAI@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180012594`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001e88c`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001e970`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerGroupStatus(_QWORD *a1, __int64 a2, ...)
{
  _QWORD *application; // rax
  __int64 v5; // rbx
  int v6; // eax
  mi::MiAsyncOperation *v7; // rax
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[40]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v12[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v13[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v14; // [rsp+F8h] [rbp-8h]
  _BYTE v15[56]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v16; // [rsp+180h] [rbp+80h] BYREF
  va_list va; // [rsp+180h] [rbp+80h]
  __int64 v18; // [rsp+188h] [rbp+88h] BYREF
  va_list va1; // [rsp+188h] [rbp+88h]
  va_list va2; // [rsp+190h] [rbp+90h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v16 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v18 = va_arg(va2, _QWORD);
  v9 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v13);
  mi::MiApplication::CreateParameterSet(*application, v15);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( a2 )
  {
    std::wstring::wstring(v11, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v15, v11, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v11);
  }
  v5 = *a1;
  v12[0] = &std::_Func_impl_no_alloc<_lambda_68ed07df59e8d3ffdd9f10aa7318e73a_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v12[1] = &v9;
  va_copy((va_list)&v12[2], va);
  va_copy((va_list)&v12[3], va1);
  va_copy((va_list)&v12[4], va2);
  v12[7] = v12;
  std::wstring::wstring(v11, L"SmapiQueryPartnerGroupStatus");
  v6 = std::wstring::wstring(v13, L"MSFT_WvrAdminTasks");
  v7 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                 v5,
                                 (unsigned int)v10,
                                 v6,
                                 (unsigned int)v11,
                                 (__int64)v15,
                                 (__int64)v12);
  mi::MiAsyncOperation::Join(v7);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v10);
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v11);
  std::_Func_class<void,>::~_Func_class<void,>(v12);
  LODWORD(v5) = v9;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e88c  mov     [rsp-8+arg_18], r9
0x18001e891  mov     [rsp-8+arg_10], r8
0x18001e896  push    rbp
0x18001e897  push    rbx
0x18001e898  push    rdi
0x18001e899  lea     rbp, [rsp-50h]
0x18001e89e  sub     rsp, 150h
0x18001e8a5  mov     rax, cs:__security_cookie
0x18001e8ac  xor     rax, rsp
0x18001e8af  mov     [rbp+60h+var_18], rax
0x18001e8b3  mov     rbx, rdx
0x18001e8b6  mov     rdi, rcx
0x18001e8b9  mov     [rsp+160h+var_130], 0
0x18001e8c1  lea     rdx, [rbp+60h+var_70]
0x18001e8c5  mov     rcx, [rcx]
0x18001e8c8  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e8cd  nop
0x18001e8ce  lea     rdx, [rbp+60h+var_50]
0x18001e8d2  mov     rcx, [rax]
0x18001e8d5  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e8da  nop
0x18001e8db  mov     rcx, [rbp+60h+var_68]; this
0x18001e8df  test    rcx, rcx
0x18001e8e2  jz      short loc_18001E8E9
0x18001e8e4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e8e9  test    rbx, rbx
0x18001e8ec  jz      short loc_18001E91F
0x18001e8ee  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001e8f5  lea     rcx, [rbp+60h+var_D8]
0x18001e8f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e8fe  nop
0x18001e8ff  mov     r9d, 2000h
0x18001e905  mov     r8, rbx
0x18001e908  lea     rdx, [rbp+60h+var_D8]
0x18001e90c  lea     rcx, [rbp+60h+var_50]
0x18001e910  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e915  nop
0x18001e916  lea     rcx, [rbp+60h+var_D8]
0x18001e91a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e91f  mov     rbx, [rdi]
0x18001e922  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_68ed07df59e8d3ffdd9f10aa7318e73a_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_68ed07df59e8d3ffdd9f10aa7318e73a_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e929  mov     [rbp+60h+var_B0], rax
0x18001e92d  lea     rax, [rsp+160h+var_130]
0x18001e932  mov     [rbp+60h+var_A8], rax
0x18001e936  lea     rax, [rbp+60h+arg_10]
0x18001e93d  mov     [rbp+60h+var_A0], rax
0x18001e941  lea     rax, [rbp+60h+arg_18]
0x18001e948  mov     [rbp+60h+var_98], rax
0x18001e94c  lea     rax, [rbp+60h+arg_20]
0x18001e953  mov     [rbp+60h+var_90], rax
0x18001e957  lea     rax, [rbp+60h+var_B0]
0x18001e95b  mov     [rbp+60h+var_78], rax
0x18001e95f  lea     rdx, aSmapiquerypart_0; "SmapiQueryPartnerGroupStatus"
0x18001e966  lea     rcx, [rbp+60h+var_D8]
0x18001e96a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e96f  nop
0x18001e970  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e977  lea     rcx, [rbp+60h+var_70]
0x18001e97b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e980  nop
0x18001e981  lea     rcx, [rbp+60h+var_B0]
0x18001e985  mov     [rsp+160h+var_138], rcx
0x18001e98a  lea     rcx, [rbp+60h+var_50]
0x18001e98e  mov     [rsp+160h+var_140], rcx
0x18001e993  lea     r9, [rbp+60h+var_D8]
0x18001e997  mov     r8, rax
0x18001e99a  lea     rdx, [rsp+160h+var_128]
0x18001e99f  mov     rcx, rbx
0x18001e9a2  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e9a7  nop
0x18001e9a8  mov     rcx, rax; this
0x18001e9ab  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e9b0  nop
0x18001e9b1  lea     rcx, [rsp+160h+var_128]; this
0x18001e9b6  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e9bb  nop
0x18001e9bc  lea     rcx, [rbp+60h+var_70]
0x18001e9c0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e9c5  nop
0x18001e9c6  lea     rcx, [rbp+60h+var_D8]
0x18001e9ca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e9cf  nop
0x18001e9d0  lea     rcx, [rbp+60h+var_B0]
0x18001e9d4  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e9d9  mov     ebx, [rsp+160h+var_130]
0x18001e9dd  lea     rcx, [rbp+60h+var_50]; this
0x18001e9e1  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e9e6  mov     eax, ebx
0x18001e9e8  mov     rcx, [rbp+60h+var_18]
0x18001e9ec  xor     rcx, rsp; StackCookie
0x18001e9ef  call    __security_check_cookie
0x18001e9f4  add     rsp, 150h
0x18001e9fb  pop     rdi
0x18001e9fc  pop     rbx
0x18001e9fd  pop     rbp
0x18001e9fe  retn
```
