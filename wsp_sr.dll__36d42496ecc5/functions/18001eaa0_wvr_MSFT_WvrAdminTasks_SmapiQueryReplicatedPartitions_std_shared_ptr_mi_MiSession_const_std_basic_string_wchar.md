# wvr::MSFT_WvrAdminTasks::SmapiQueryReplicatedPartitions(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x18001eaa0`
- end: `0x18001ebf8`
- name: `?SmapiQueryReplicatedPartitions@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z`
- size: `344`
- prototype: `__int64(__int64 *, __int64, _QWORD *, ...)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180019cb8`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001eaa0`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001eb69`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 wvr::MSFT_WvrAdminTasks::SmapiQueryReplicatedPartitions(__int64 *a1, __int64 a2, _QWORD *a3, ...)
{
  __int64 *application; // rax
  __int64 v6; // rbx
  int v7; // eax
  mi::MiAsyncOperation::MiOperationArgs **v8; // rax
  enum _MI_CancellationReason v9; // edx
  __int64 v10; // rdx
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v15[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v16; // [rsp+B0h] [rbp-50h]
  _QWORD v17[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v18[7]; // [rsp+110h] [rbp+10h] BYREF
  va_list va; // [rsp+188h] [rbp+88h] BYREF

  va_start(va, a3);
  v12 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v15);
  mi::MiApplication::CreateParameterSet(*application, v18);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( a3 )
  {
    std::wstring::wstring((__int64)v14, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v18, (int)v14, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v14);
  }
  v6 = *a1;
  v17[0] = &std::_Func_impl_no_alloc<_lambda_6a324b9e58aef0cf78e4fe8fbf279365_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v17[1] = &v12;
  va_copy((va_list)&v17[2], va);
  v17[7] = v17;
  std::wstring::wstring((__int64)v14, (__int64)L"SmapiQueryReplicatedPartitions");
  v7 = std::wstring::wstring((__int64)v15, (__int64)L"MSFT_WvrAdminTasks");
  v8 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                   v6,
                                                   (__int64)v13,
                                                   v7,
                                                   (int)v14,
                                                   (__int64)v18,
                                                   (__int64)v17);
  mi::MiAsyncOperation::Join(v8);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v13, v9);
  std::wstring::_Tidy_deallocate((__int64)v15);
  std::wstring::_Tidy_deallocate((__int64)v14);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v17, v10);
  LODWORD(v6) = v12;
  mi::MiInstance::~MiInstance(v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001eaa0  mov     [rsp-8+arg_18], r9
0x18001eaa5  push    rbp
0x18001eaa6  push    rbx
0x18001eaa7  push    rdi
0x18001eaa8  lea     rbp, [rsp-50h]
0x18001eaad  sub     rsp, 150h
0x18001eab4  mov     rax, cs:__security_cookie
0x18001eabb  xor     rax, rsp
0x18001eabe  mov     [rbp+60h+var_18], rax
0x18001eac2  mov     rbx, r8
0x18001eac5  mov     rdi, rcx
0x18001eac8  mov     [rsp+160h+var_130], 0
0x18001ead0  lea     rdx, [rbp+60h+var_B8]
0x18001ead4  mov     rcx, [rcx]
0x18001ead7  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001eadc  nop
0x18001eadd  lea     rdx, [rbp+60h+var_50]
0x18001eae1  mov     rcx, [rax]
0x18001eae4  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001eae9  nop
0x18001eaea  mov     rcx, [rbp+60h+var_B0]; this
0x18001eaee  test    rcx, rcx
0x18001eaf1  jz      short loc_18001EAF8
0x18001eaf3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001eaf8  test    rbx, rbx
0x18001eafb  jz      short loc_18001EB2E
0x18001eafd  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001eb04  lea     rcx, [rbp+60h+var_D8]
0x18001eb08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eb0d  nop
0x18001eb0e  mov     r9d, 2000h
0x18001eb14  mov     r8, rbx
0x18001eb17  lea     rdx, [rbp+60h+var_D8]
0x18001eb1b  lea     rcx, [rbp+60h+var_50]
0x18001eb1f  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001eb24  nop
0x18001eb25  lea     rcx, [rbp+60h+var_D8]
0x18001eb29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eb2e  mov     rbx, [rdi]
0x18001eb31  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6a324b9e58aef0cf78e4fe8fbf279365_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6a324b9e58aef0cf78e4fe8fbf279365_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001eb38  mov     [rbp+60h+var_90], rax
0x18001eb3c  lea     rax, [rsp+160h+var_130]
0x18001eb41  mov     [rbp+60h+var_88], rax
0x18001eb45  lea     rax, [rbp+60h+arg_18]
0x18001eb4c  mov     [rbp+60h+var_80], rax
0x18001eb50  lea     rax, [rbp+60h+var_90]
0x18001eb54  mov     [rbp+60h+var_58], rax
0x18001eb58  lea     rdx, aSmapiqueryrepl; "SmapiQueryReplicatedPartitions"
0x18001eb5f  lea     rcx, [rbp+60h+var_D8]
0x18001eb63  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eb68  nop
0x18001eb69  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001eb70  lea     rcx, [rbp+60h+var_B8]
0x18001eb74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eb79  nop
0x18001eb7a  lea     rcx, [rbp+60h+var_90]
0x18001eb7e  mov     [rsp+160h+var_138], rcx
0x18001eb83  lea     rcx, [rbp+60h+var_50]
0x18001eb87  mov     [rsp+160h+var_140], rcx
0x18001eb8c  lea     r9, [rbp+60h+var_D8]
0x18001eb90  mov     r8, rax
0x18001eb93  lea     rdx, [rsp+160h+var_128]
0x18001eb98  mov     rcx, rbx
0x18001eb9b  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001eba0  nop
0x18001eba1  mov     rcx, rax; this
0x18001eba4  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001eba9  nop
0x18001ebaa  lea     rcx, [rsp+160h+var_128]; this
0x18001ebaf  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001ebb4  nop
0x18001ebb5  lea     rcx, [rbp+60h+var_B8]
0x18001ebb9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ebbe  nop
0x18001ebbf  lea     rcx, [rbp+60h+var_D8]
0x18001ebc3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ebc8  nop
0x18001ebc9  lea     rcx, [rbp+60h+var_90]
0x18001ebcd  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001ebd2  mov     ebx, [rsp+160h+var_130]
0x18001ebd6  lea     rcx, [rbp+60h+var_50]; this
0x18001ebda  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001ebdf  mov     eax, ebx
0x18001ebe1  mov     rcx, [rbp+60h+var_18]
0x18001ebe5  xor     rcx, rsp; StackCookie
0x18001ebe8  call    __security_check_cookie
0x18001ebed  add     rsp, 150h
0x18001ebf4  pop     rdi
0x18001ebf5  pop     rbx
0x18001ebf6  pop     rbp
0x18001ebf7  retn
```
