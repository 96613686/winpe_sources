# wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerGroupStatus(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,ushort *,_MI_Datetime *,uint *)

- ea: `0x18001e75c`
- end: `0x18001e8cf`
- name: `?SmapiQueryPartnerGroupStatus@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEAGPEAU_MI_Datetime@@PEAI@Z`
- size: `371`
- prototype: `__int64(__int64 *, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x1800126cc`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001e75c`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001e840`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerGroupStatus(__int64 *a1, _QWORD *a2, ...)
{
  __int64 *application; // rax
  __int64 v5; // rbx
  int v6; // eax
  mi::MiAsyncOperation::MiOperationArgs **v7; // rax
  enum _MI_CancellationReason v8; // edx
  __int64 v9; // rdx
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[40]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v14[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v15[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v16; // [rsp+F8h] [rbp-8h]
  std::_Ref_count_base *v17[7]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v18; // [rsp+180h] [rbp+80h] BYREF
  va_list va; // [rsp+180h] [rbp+80h]
  __int64 v20; // [rsp+188h] [rbp+88h] BYREF
  va_list va1; // [rsp+188h] [rbp+88h]
  va_list va2; // [rsp+190h] [rbp+90h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  v11 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v15);
  mi::MiApplication::CreateParameterSet(*application, v17);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v13, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v17, (int)v13, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v13);
  }
  v5 = *a1;
  v14[0] = &std::_Func_impl_no_alloc<_lambda_68ed07df59e8d3ffdd9f10aa7318e73a_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v14[1] = &v11;
  va_copy((va_list)&v14[2], va);
  va_copy((va_list)&v14[3], va1);
  va_copy((va_list)&v14[4], va2);
  v14[7] = v14;
  std::wstring::wstring((__int64)v13, (__int64)L"SmapiQueryPartnerGroupStatus");
  v6 = std::wstring::wstring((__int64)v15, (__int64)L"MSFT_WvrAdminTasks");
  v7 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                   v5,
                                                   (__int64)v12,
                                                   v6,
                                                   (int)v13,
                                                   (__int64)v17,
                                                   (__int64)v14);
  mi::MiAsyncOperation::Join(v7);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v12, v8);
  std::wstring::_Tidy_deallocate((__int64)v15);
  std::wstring::_Tidy_deallocate((__int64)v13);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v14, v9);
  LODWORD(v5) = v11;
  mi::MiInstance::~MiInstance(v17);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e75c  mov     [rsp-8+arg_18], r9
0x18001e761  mov     [rsp-8+arg_10], r8
0x18001e766  push    rbp
0x18001e767  push    rbx
0x18001e768  push    rdi
0x18001e769  lea     rbp, [rsp-50h]
0x18001e76e  sub     rsp, 150h
0x18001e775  mov     rax, cs:__security_cookie
0x18001e77c  xor     rax, rsp
0x18001e77f  mov     [rbp+60h+var_18], rax
0x18001e783  mov     rbx, rdx
0x18001e786  mov     rdi, rcx
0x18001e789  mov     [rsp+160h+var_130], 0
0x18001e791  lea     rdx, [rbp+60h+var_70]
0x18001e795  mov     rcx, [rcx]
0x18001e798  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e79d  nop
0x18001e79e  lea     rdx, [rbp+60h+var_50]
0x18001e7a2  mov     rcx, [rax]
0x18001e7a5  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e7aa  nop
0x18001e7ab  mov     rcx, [rbp+60h+var_68]; this
0x18001e7af  test    rcx, rcx
0x18001e7b2  jz      short loc_18001E7B9
0x18001e7b4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e7b9  test    rbx, rbx
0x18001e7bc  jz      short loc_18001E7EF
0x18001e7be  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001e7c5  lea     rcx, [rbp+60h+var_D8]
0x18001e7c9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e7ce  nop
0x18001e7cf  mov     r9d, 2000h
0x18001e7d5  mov     r8, rbx
0x18001e7d8  lea     rdx, [rbp+60h+var_D8]
0x18001e7dc  lea     rcx, [rbp+60h+var_50]
0x18001e7e0  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e7e5  nop
0x18001e7e6  lea     rcx, [rbp+60h+var_D8]
0x18001e7ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e7ef  mov     rbx, [rdi]
0x18001e7f2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_68ed07df59e8d3ffdd9f10aa7318e73a_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_68ed07df59e8d3ffdd9f10aa7318e73a_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e7f9  mov     [rbp+60h+var_B0], rax
0x18001e7fd  lea     rax, [rsp+160h+var_130]
0x18001e802  mov     [rbp+60h+var_A8], rax
0x18001e806  lea     rax, [rbp+60h+arg_10]
0x18001e80d  mov     [rbp+60h+var_A0], rax
0x18001e811  lea     rax, [rbp+60h+arg_18]
0x18001e818  mov     [rbp+60h+var_98], rax
0x18001e81c  lea     rax, [rbp+60h+arg_20]
0x18001e823  mov     [rbp+60h+var_90], rax
0x18001e827  lea     rax, [rbp+60h+var_B0]
0x18001e82b  mov     [rbp+60h+var_78], rax
0x18001e82f  lea     rdx, aSmapiquerypart_0; "SmapiQueryPartnerGroupStatus"
0x18001e836  lea     rcx, [rbp+60h+var_D8]
0x18001e83a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e83f  nop
0x18001e840  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e847  lea     rcx, [rbp+60h+var_70]
0x18001e84b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e850  nop
0x18001e851  lea     rcx, [rbp+60h+var_B0]
0x18001e855  mov     [rsp+160h+var_138], rcx
0x18001e85a  lea     rcx, [rbp+60h+var_50]
0x18001e85e  mov     [rsp+160h+var_140], rcx
0x18001e863  lea     r9, [rbp+60h+var_D8]
0x18001e867  mov     r8, rax
0x18001e86a  lea     rdx, [rsp+160h+var_128]
0x18001e86f  mov     rcx, rbx
0x18001e872  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e877  nop
0x18001e878  mov     rcx, rax; this
0x18001e87b  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e880  nop
0x18001e881  lea     rcx, [rsp+160h+var_128]; this
0x18001e886  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e88b  nop
0x18001e88c  lea     rcx, [rbp+60h+var_70]
0x18001e890  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e895  nop
0x18001e896  lea     rcx, [rbp+60h+var_D8]
0x18001e89a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e89f  nop
0x18001e8a0  lea     rcx, [rbp+60h+var_B0]
0x18001e8a4  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e8a9  mov     ebx, [rsp+160h+var_130]
0x18001e8ad  lea     rcx, [rbp+60h+var_50]; this
0x18001e8b1  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e8b6  mov     eax, ebx
0x18001e8b8  mov     rcx, [rbp+60h+var_18]
0x18001e8bc  xor     rcx, rsp; StackCookie
0x18001e8bf  call    __security_check_cookie
0x18001e8c4  add     rsp, 150h
0x18001e8cb  pop     rdi
0x18001e8cc  pop     rbx
0x18001e8cd  pop     rbp
0x18001e8ce  retn
```
