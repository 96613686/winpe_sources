# wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerPartitions(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,ushort *,_MI_Datetime *,uint *)

- ea: `0x18001e8d8`
- end: `0x18001ea97`
- name: `?SmapiQueryPartnerPartitions@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEAV54@2PEAGPEAU_MI_Datetime@@PEAI@Z`
- size: `447`
- prototype: `__int64(__int64 *, _QWORD *, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180014540`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001e8d8`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001ea07`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerPartitions(__int64 *a1, _QWORD *a2, _QWORD *a3, ...)
{
  __int64 *application; // rax
  __int64 v7; // rbx
  int v8; // eax
  mi::MiAsyncOperation::MiOperationArgs **v9; // rax
  enum _MI_CancellationReason v10; // edx
  __int64 v11; // rdx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[40]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v16[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v17[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v18; // [rsp+F8h] [rbp-8h]
  std::_Ref_count_base *v19[7]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v20; // [rsp+198h] [rbp+98h] BYREF
  va_list va; // [rsp+198h] [rbp+98h]
  __int64 v22; // [rsp+1A0h] [rbp+A0h] BYREF
  va_list va1; // [rsp+1A0h] [rbp+A0h]
  __int64 v24; // [rsp+1A8h] [rbp+A8h] BYREF
  va_list va2; // [rsp+1A8h] [rbp+A8h]
  __int64 v26; // [rsp+1B0h] [rbp+B0h] BYREF
  va_list va3; // [rsp+1B0h] [rbp+B0h]
  va_list va4; // [rsp+1B8h] [rbp+B8h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v20 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v22 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v24 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v26 = va_arg(va4, _QWORD);
  v13 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v17);
  mi::MiApplication::CreateParameterSet(*application, v19);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v15, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v19, (int)v15, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v15);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v15, (__int64)L"PartitionId");
    mi::MiInstance::AddElement<std::wstring>((int)v19, (int)v15, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v15);
  }
  v7 = *a1;
  v16[0] = &std::_Func_impl_no_alloc<_lambda_dde23385866a357cf8fa76a26c5b3433_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v16[1] = &v13;
  va_copy((va_list)&v16[2], va);
  va_copy((va_list)&v16[3], va1);
  va_copy((va_list)&v16[4], va2);
  va_copy((va_list)&v16[5], va3);
  va_copy((va_list)&v16[6], va4);
  v16[7] = v16;
  std::wstring::wstring((__int64)v15, (__int64)L"SmapiQueryPartnerPartitions");
  v8 = std::wstring::wstring((__int64)v17, (__int64)L"MSFT_WvrAdminTasks");
  v9 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                   v7,
                                                   (__int64)v14,
                                                   v8,
                                                   (int)v15,
                                                   (__int64)v19,
                                                   (__int64)v16);
  mi::MiAsyncOperation::Join(v9);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v14, v10);
  std::wstring::_Tidy_deallocate((__int64)v17);
  std::wstring::_Tidy_deallocate((__int64)v15);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v16, v11);
  LODWORD(v7) = v13;
  mi::MiInstance::~MiInstance(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e8d8  mov     [rsp-8+arg_18], r9
0x18001e8dd  push    rbp
0x18001e8de  push    rbx
0x18001e8df  push    rsi
0x18001e8e0  push    rdi
0x18001e8e1  lea     rbp, [rsp-58h]
0x18001e8e6  sub     rsp, 158h
0x18001e8ed  mov     rax, cs:__security_cookie
0x18001e8f4  xor     rax, rsp
0x18001e8f7  mov     [rbp+70h+var_28], rax
0x18001e8fb  mov     rbx, r8
0x18001e8fe  mov     rdi, rdx
0x18001e901  mov     rsi, rcx
0x18001e904  mov     [rsp+170h+var_140], 0
0x18001e90c  lea     rdx, [rbp+70h+var_80]
0x18001e910  mov     rcx, [rcx]
0x18001e913  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e918  nop
0x18001e919  lea     rdx, [rbp+70h+var_60]
0x18001e91d  mov     rcx, [rax]
0x18001e920  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e925  nop
0x18001e926  mov     rcx, [rbp+70h+var_78]; this
0x18001e92a  test    rcx, rcx
0x18001e92d  jz      short loc_18001E934
0x18001e92f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e934  test    rdi, rdi
0x18001e937  jz      short loc_18001E96A
0x18001e939  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001e940  lea     rcx, [rbp+70h+var_E8]
0x18001e944  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e949  nop
0x18001e94a  mov     r9d, 2000h
0x18001e950  mov     r8, rdi
0x18001e953  lea     rdx, [rbp+70h+var_E8]
0x18001e957  lea     rcx, [rbp+70h+var_60]
0x18001e95b  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e960  nop
0x18001e961  lea     rcx, [rbp+70h+var_E8]
0x18001e965  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e96a  test    rbx, rbx
0x18001e96d  jz      short loc_18001E9A0
0x18001e96f  lea     rdx, aPartitionid; "PartitionId"
0x18001e976  lea     rcx, [rbp+70h+var_E8]
0x18001e97a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e97f  nop
0x18001e980  mov     r9d, 2000h
0x18001e986  mov     r8, rbx
0x18001e989  lea     rdx, [rbp+70h+var_E8]
0x18001e98d  lea     rcx, [rbp+70h+var_60]
0x18001e991  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e996  nop
0x18001e997  lea     rcx, [rbp+70h+var_E8]
0x18001e99b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e9a0  mov     rbx, [rsi]
0x18001e9a3  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_dde23385866a357cf8fa76a26c5b3433_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_dde23385866a357cf8fa76a26c5b3433_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e9aa  mov     [rbp+70h+var_C0], rax
0x18001e9ae  lea     rax, [rsp+170h+var_140]
0x18001e9b3  mov     [rbp+70h+var_B8], rax
0x18001e9b7  lea     rax, [rbp+70h+arg_18]
0x18001e9be  mov     [rbp+70h+var_B0], rax
0x18001e9c2  lea     rax, [rbp+70h+arg_20]
0x18001e9c9  mov     [rbp+70h+var_A8], rax
0x18001e9cd  lea     rax, [rbp+70h+arg_28]
0x18001e9d4  mov     [rbp+70h+var_A0], rax
0x18001e9d8  lea     rax, [rbp+70h+arg_30]
0x18001e9df  mov     [rbp+70h+var_98], rax
0x18001e9e3  lea     rax, [rbp+70h+arg_38]
0x18001e9ea  mov     [rbp+70h+var_90], rax
0x18001e9ee  lea     rax, [rbp+70h+var_C0]
0x18001e9f2  mov     [rbp+70h+var_88], rax
0x18001e9f6  lea     rdx, aSmapiquerypart; "SmapiQueryPartnerPartitions"
0x18001e9fd  lea     rcx, [rbp+70h+var_E8]
0x18001ea01  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ea06  nop
0x18001ea07  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001ea0e  lea     rcx, [rbp+70h+var_80]
0x18001ea12  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ea17  nop
0x18001ea18  lea     rcx, [rbp+70h+var_C0]
0x18001ea1c  mov     [rsp+170h+var_148], rcx
0x18001ea21  lea     rcx, [rbp+70h+var_60]
0x18001ea25  mov     [rsp+170h+var_150], rcx
0x18001ea2a  lea     r9, [rbp+70h+var_E8]
0x18001ea2e  mov     r8, rax
0x18001ea31  lea     rdx, [rsp+170h+var_138]
0x18001ea36  mov     rcx, rbx
0x18001ea39  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001ea3e  nop
0x18001ea3f  mov     rcx, rax; this
0x18001ea42  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001ea47  nop
0x18001ea48  lea     rcx, [rsp+170h+var_138]; this
0x18001ea4d  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001ea52  nop
0x18001ea53  lea     rcx, [rbp+70h+var_80]
0x18001ea57  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea5c  nop
0x18001ea5d  lea     rcx, [rbp+70h+var_E8]
0x18001ea61  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea66  nop
0x18001ea67  lea     rcx, [rbp+70h+var_C0]
0x18001ea6b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001ea70  mov     ebx, [rsp+170h+var_140]
0x18001ea74  lea     rcx, [rbp+70h+var_60]; this
0x18001ea78  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001ea7d  mov     eax, ebx
0x18001ea7f  mov     rcx, [rbp+70h+var_28]
0x18001ea83  xor     rcx, rsp; StackCookie
0x18001ea86  call    __security_check_cookie
0x18001ea8b  add     rsp, 158h
0x18001ea92  pop     rdi
0x18001ea93  pop     rsi
0x18001ea94  pop     rbx
0x18001ea95  pop     rbp
0x18001ea96  retn
```
