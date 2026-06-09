# wvr::MSFT_WvrAdminTasks::SmapiQueryReplicatedPartitions(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x18001ebd0`
- end: `0x18001ed29`
- name: `?SmapiQueryReplicatedPartitions@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180019cf0`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001ebd0`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001ec99`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 wvr::MSFT_WvrAdminTasks::SmapiQueryReplicatedPartitions(_QWORD *a1, __int64 a2, __int64 a3, ...)
{
  _QWORD *application; // rax
  __int64 v6; // rbx
  int v7; // eax
  mi::MiAsyncOperation *v8; // rax
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v13[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v14; // [rsp+B0h] [rbp-50h]
  _QWORD v15[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v16[56]; // [rsp+110h] [rbp+10h] BYREF
  va_list va; // [rsp+188h] [rbp+88h] BYREF

  va_start(va, a3);
  v10 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v13);
  mi::MiApplication::CreateParameterSet(*application, v16);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  if ( a3 )
  {
    std::wstring::wstring(v12, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v16, v12, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v12);
  }
  v6 = *a1;
  v15[0] = &std::_Func_impl_no_alloc<_lambda_6a324b9e58aef0cf78e4fe8fbf279365_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v15[1] = &v10;
  va_copy((va_list)&v15[2], va);
  v15[7] = v15;
  std::wstring::wstring(v12, L"SmapiQueryReplicatedPartitions");
  v7 = std::wstring::wstring(v13, L"MSFT_WvrAdminTasks");
  v8 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                 v6,
                                 (unsigned int)v11,
                                 v7,
                                 (unsigned int)v12,
                                 (__int64)v16,
                                 (__int64)v15);
  mi::MiAsyncOperation::Join(v8);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v11);
  std::wstring::_Tidy_deallocate(v13);
  std::wstring::_Tidy_deallocate(v12);
  std::_Func_class<void,>::~_Func_class<void,>(v15);
  LODWORD(v6) = v10;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ebd0  mov     [rsp-8+arg_18], r9
0x18001ebd5  push    rbp
0x18001ebd6  push    rbx
0x18001ebd7  push    rdi
0x18001ebd8  lea     rbp, [rsp-50h]
0x18001ebdd  sub     rsp, 150h
0x18001ebe4  mov     rax, cs:__security_cookie
0x18001ebeb  xor     rax, rsp
0x18001ebee  mov     [rbp+60h+var_18], rax
0x18001ebf2  mov     rbx, r8
0x18001ebf5  mov     rdi, rcx
0x18001ebf8  mov     [rsp+160h+var_130], 0
0x18001ec00  lea     rdx, [rbp+60h+var_B8]
0x18001ec04  mov     rcx, [rcx]
0x18001ec07  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001ec0c  nop
0x18001ec0d  lea     rdx, [rbp+60h+var_50]
0x18001ec11  mov     rcx, [rax]
0x18001ec14  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001ec19  nop
0x18001ec1a  mov     rcx, [rbp+60h+var_B0]; this
0x18001ec1e  test    rcx, rcx
0x18001ec21  jz      short loc_18001EC28
0x18001ec23  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ec28  test    rbx, rbx
0x18001ec2b  jz      short loc_18001EC5E
0x18001ec2d  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001ec34  lea     rcx, [rbp+60h+var_D8]
0x18001ec38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ec3d  nop
0x18001ec3e  mov     r9d, 2000h
0x18001ec44  mov     r8, rbx
0x18001ec47  lea     rdx, [rbp+60h+var_D8]
0x18001ec4b  lea     rcx, [rbp+60h+var_50]
0x18001ec4f  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ec54  nop
0x18001ec55  lea     rcx, [rbp+60h+var_D8]
0x18001ec59  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec5e  mov     rbx, [rdi]
0x18001ec61  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6a324b9e58aef0cf78e4fe8fbf279365_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6a324b9e58aef0cf78e4fe8fbf279365_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001ec68  mov     [rbp+60h+var_90], rax
0x18001ec6c  lea     rax, [rsp+160h+var_130]
0x18001ec71  mov     [rbp+60h+var_88], rax
0x18001ec75  lea     rax, [rbp+60h+arg_18]
0x18001ec7c  mov     [rbp+60h+var_80], rax
0x18001ec80  lea     rax, [rbp+60h+var_90]
0x18001ec84  mov     [rbp+60h+var_58], rax
0x18001ec88  lea     rdx, aSmapiqueryrepl; "SmapiQueryReplicatedPartitions"
0x18001ec8f  lea     rcx, [rbp+60h+var_D8]
0x18001ec93  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ec98  nop
0x18001ec99  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001eca0  lea     rcx, [rbp+60h+var_B8]
0x18001eca4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eca9  nop
0x18001ecaa  lea     rcx, [rbp+60h+var_90]
0x18001ecae  mov     [rsp+160h+var_138], rcx
0x18001ecb3  lea     rcx, [rbp+60h+var_50]
0x18001ecb7  mov     [rsp+160h+var_140], rcx
0x18001ecbc  lea     r9, [rbp+60h+var_D8]
0x18001ecc0  mov     r8, rax
0x18001ecc3  lea     rdx, [rsp+160h+var_128]
0x18001ecc8  mov     rcx, rbx
0x18001eccb  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001ecd0  nop
0x18001ecd1  mov     rcx, rax; this
0x18001ecd4  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001ecd9  nop
0x18001ecda  lea     rcx, [rsp+160h+var_128]; this
0x18001ecdf  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001ece4  nop
0x18001ece5  lea     rcx, [rbp+60h+var_B8]
0x18001ece9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ecee  nop
0x18001ecef  lea     rcx, [rbp+60h+var_D8]
0x18001ecf3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ecf8  nop
0x18001ecf9  lea     rcx, [rbp+60h+var_90]
0x18001ecfd  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001ed02  mov     ebx, [rsp+160h+var_130]
0x18001ed06  lea     rcx, [rbp+60h+var_50]; this
0x18001ed0a  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001ed0f  mov     eax, ebx
0x18001ed11  mov     rcx, [rbp+60h+var_18]
0x18001ed15  xor     rcx, rsp; StackCookie
0x18001ed18  call    __security_check_cookie
0x18001ed1d  add     rsp, 150h
0x18001ed24  pop     rdi
0x18001ed25  pop     rbx
0x18001ed26  pop     rbp
0x18001ed27  retn
```
