# wvr::MSFT_WvrAdminTasks::SmapiAddMember(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *)

- ea: `0x18001e4a8`
- end: `0x18001e65d`
- name: `?SmapiAddMember@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@2@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180009df4`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001e4a8`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001e5cb`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SmapiAddMember(__int64 *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 *application; // rax
  __int64 v9; // rbx
  int v10; // eax
  mi::MiAsyncOperation::MiOperationArgs **v11; // rax
  enum _MI_CancellationReason v12; // edx
  __int64 v13; // rdx
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v18[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v19; // [rsp+B0h] [rbp-50h]
  std::_Ref_count_base *v20[7]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v21[8]; // [rsp+100h] [rbp+0h] BYREF

  v15 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v18);
  mi::MiApplication::CreateParameterSet(*application, v20);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v17, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v17, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v17);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v17, (__int64)L"VolumeNames");
    mi::MiInstance::AddElement(v20, v17, a3);
    std::wstring::_Tidy_deallocate((__int64)v17);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v17, (__int64)L"PartitionObjectIds");
    mi::MiInstance::AddElement(v20, v17, a4);
    std::wstring::_Tidy_deallocate((__int64)v17);
  }
  v9 = *a1;
  v21[0] = &std::_Func_impl_no_alloc<_lambda_99a7bd846410e0b8fdde8106f358b986_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v21[1] = &v15;
  v21[7] = v21;
  std::wstring::wstring((__int64)v17, (__int64)L"SmapiAddMember");
  v10 = std::wstring::wstring((__int64)v18, (__int64)L"MSFT_WvrAdminTasks");
  v11 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v9,
                                                    (__int64)v16,
                                                    v10,
                                                    (int)v17,
                                                    (__int64)v20,
                                                    (__int64)v21);
  mi::MiAsyncOperation::Join(v11);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v16, v12);
  std::wstring::_Tidy_deallocate((__int64)v18);
  std::wstring::_Tidy_deallocate((__int64)v17);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v21, v13);
  LODWORD(v9) = v15;
  mi::MiInstance::~MiInstance(v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e4a8  push    rbp
0x18001e4aa  push    rbx
0x18001e4ab  push    rsi
0x18001e4ac  push    rdi
0x18001e4ad  push    r14
0x18001e4af  lea     rbp, [rsp-50h]
0x18001e4b4  sub     rsp, 150h
0x18001e4bb  mov     rax, cs:__security_cookie
0x18001e4c2  xor     rax, rsp
0x18001e4c5  mov     [rbp+70h+var_30], rax
0x18001e4c9  mov     rbx, r9
0x18001e4cc  mov     rdi, r8
0x18001e4cf  mov     rsi, rdx
0x18001e4d2  mov     r14, rcx
0x18001e4d5  mov     [rsp+170h+var_140], 0
0x18001e4dd  lea     rdx, [rbp+70h+var_C8]
0x18001e4e1  mov     rcx, [rcx]
0x18001e4e4  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e4e9  nop
0x18001e4ea  lea     rdx, [rbp+70h+var_A8]
0x18001e4ee  mov     rcx, [rax]
0x18001e4f1  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e4f6  nop
0x18001e4f7  mov     rcx, [rbp+70h+var_C0]; this
0x18001e4fb  test    rcx, rcx
0x18001e4fe  jz      short loc_18001E505
0x18001e500  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e505  test    rsi, rsi
0x18001e508  jz      short loc_18001E53B
0x18001e50a  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001e511  lea     rcx, [rbp+70h+var_E8]
0x18001e515  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e51a  nop
0x18001e51b  mov     r9d, 2000h
0x18001e521  mov     r8, rsi
0x18001e524  lea     rdx, [rbp+70h+var_E8]
0x18001e528  lea     rcx, [rbp+70h+var_A8]
0x18001e52c  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e531  nop
0x18001e532  lea     rcx, [rbp+70h+var_E8]
0x18001e536  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e53b  test    rdi, rdi
0x18001e53e  jz      short loc_18001E56B
0x18001e540  lea     rdx, aVolumenames; "VolumeNames"
0x18001e547  lea     rcx, [rbp+70h+var_E8]
0x18001e54b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e550  nop
0x18001e551  mov     r8, rdi
0x18001e554  lea     rdx, [rbp+70h+var_E8]
0x18001e558  lea     rcx, [rbp+70h+var_A8]
0x18001e55c  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e561  nop
0x18001e562  lea     rcx, [rbp+70h+var_E8]
0x18001e566  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e56b  test    rbx, rbx
0x18001e56e  jz      short loc_18001E59B
0x18001e570  lea     rdx, aPartitionobjec; "PartitionObjectIds"
0x18001e577  lea     rcx, [rbp+70h+var_E8]
0x18001e57b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e580  nop
0x18001e581  mov     r8, rbx
0x18001e584  lea     rdx, [rbp+70h+var_E8]
0x18001e588  lea     rcx, [rbp+70h+var_A8]
0x18001e58c  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e591  nop
0x18001e592  lea     rcx, [rbp+70h+var_E8]
0x18001e596  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e59b  mov     rbx, [r14]
0x18001e59e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_99a7bd846410e0b8fdde8106f358b986_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_99a7bd846410e0b8fdde8106f358b986_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e5a5  mov     [rbp+70h+var_70], rax
0x18001e5a9  lea     rax, [rsp+170h+var_140]
0x18001e5ae  mov     [rbp+70h+var_68], rax
0x18001e5b2  lea     rax, [rbp+70h+var_70]
0x18001e5b6  mov     [rbp+70h+var_38], rax
0x18001e5ba  lea     rdx, aSmapiaddmember; "SmapiAddMember"
0x18001e5c1  lea     rcx, [rbp+70h+var_E8]
0x18001e5c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e5ca  nop
0x18001e5cb  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e5d2  lea     rcx, [rbp+70h+var_C8]
0x18001e5d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e5db  nop
0x18001e5dc  lea     rcx, [rbp+70h+var_70]
0x18001e5e0  mov     [rsp+170h+var_148], rcx
0x18001e5e5  lea     rcx, [rbp+70h+var_A8]
0x18001e5e9  mov     [rsp+170h+var_150], rcx
0x18001e5ee  lea     r9, [rbp+70h+var_E8]
0x18001e5f2  mov     r8, rax
0x18001e5f5  lea     rdx, [rsp+170h+var_138]
0x18001e5fa  mov     rcx, rbx
0x18001e5fd  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e602  nop
0x18001e603  mov     rcx, rax; this
0x18001e606  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e60b  nop
0x18001e60c  lea     rcx, [rsp+170h+var_138]; this
0x18001e611  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e616  nop
0x18001e617  lea     rcx, [rbp+70h+var_C8]
0x18001e61b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e620  nop
0x18001e621  lea     rcx, [rbp+70h+var_E8]
0x18001e625  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e62a  nop
0x18001e62b  lea     rcx, [rbp+70h+var_70]
0x18001e62f  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e634  mov     ebx, [rsp+170h+var_140]
0x18001e638  lea     rcx, [rbp+70h+var_A8]; this
0x18001e63c  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e641  mov     eax, ebx
0x18001e643  mov     rcx, [rbp+70h+var_30]
0x18001e647  xor     rcx, rsp; StackCookie
0x18001e64a  call    __security_check_cookie
0x18001e64f  add     rsp, 150h
0x18001e656  pop     r14
0x18001e658  pop     rdi
0x18001e659  pop     rsi
0x18001e65a  pop     rbx
0x18001e65b  pop     rbp
0x18001e65c  retn
```
