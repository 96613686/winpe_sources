# wvr::MSFT_WvrAdminTasks::SmapiAddMember(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *)

- ea: `0x18001e5d4`
- end: `0x18001e78a`
- name: `?SmapiAddMember@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@2@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180009f4c`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001e5d4`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001e6f7`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SmapiAddMember(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
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
    std::wstring::wstring(v15, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v18, v15, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v15);
  }
  if ( a3 )
  {
    std::wstring::wstring(v15, L"VolumeNames");
    mi::MiInstance::AddElement(v18, v15, a3);
    std::wstring::_Tidy_deallocate(v15);
  }
  if ( a4 )
  {
    std::wstring::wstring(v15, L"PartitionObjectIds");
    mi::MiInstance::AddElement(v18, v15, a4);
    std::wstring::_Tidy_deallocate(v15);
  }
  v9 = *a1;
  v19[0] = &std::_Func_impl_no_alloc<_lambda_99a7bd846410e0b8fdde8106f358b986_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v19[1] = &v13;
  v19[7] = v19;
  std::wstring::wstring(v15, L"SmapiAddMember");
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
0x18001e5d4  push    rbp
0x18001e5d6  push    rbx
0x18001e5d7  push    rsi
0x18001e5d8  push    rdi
0x18001e5d9  push    r14
0x18001e5db  lea     rbp, [rsp-50h]
0x18001e5e0  sub     rsp, 150h
0x18001e5e7  mov     rax, cs:__security_cookie
0x18001e5ee  xor     rax, rsp
0x18001e5f1  mov     [rbp+70h+var_30], rax
0x18001e5f5  mov     rbx, r9
0x18001e5f8  mov     rdi, r8
0x18001e5fb  mov     rsi, rdx
0x18001e5fe  mov     r14, rcx
0x18001e601  mov     [rsp+170h+var_140], 0
0x18001e609  lea     rdx, [rbp+70h+var_C8]
0x18001e60d  mov     rcx, [rcx]
0x18001e610  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e615  nop
0x18001e616  lea     rdx, [rbp+70h+var_A8]
0x18001e61a  mov     rcx, [rax]
0x18001e61d  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e622  nop
0x18001e623  mov     rcx, [rbp+70h+var_C0]; this
0x18001e627  test    rcx, rcx
0x18001e62a  jz      short loc_18001E631
0x18001e62c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e631  test    rsi, rsi
0x18001e634  jz      short loc_18001E667
0x18001e636  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001e63d  lea     rcx, [rbp+70h+var_E8]
0x18001e641  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e646  nop
0x18001e647  mov     r9d, 2000h
0x18001e64d  mov     r8, rsi
0x18001e650  lea     rdx, [rbp+70h+var_E8]
0x18001e654  lea     rcx, [rbp+70h+var_A8]
0x18001e658  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e65d  nop
0x18001e65e  lea     rcx, [rbp+70h+var_E8]
0x18001e662  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e667  test    rdi, rdi
0x18001e66a  jz      short loc_18001E697
0x18001e66c  lea     rdx, aVolumenames; "VolumeNames"
0x18001e673  lea     rcx, [rbp+70h+var_E8]
0x18001e677  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e67c  nop
0x18001e67d  mov     r8, rdi
0x18001e680  lea     rdx, [rbp+70h+var_E8]
0x18001e684  lea     rcx, [rbp+70h+var_A8]
0x18001e688  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e68d  nop
0x18001e68e  lea     rcx, [rbp+70h+var_E8]
0x18001e692  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e697  test    rbx, rbx
0x18001e69a  jz      short loc_18001E6C7
0x18001e69c  lea     rdx, aPartitionobjec; "PartitionObjectIds"
0x18001e6a3  lea     rcx, [rbp+70h+var_E8]
0x18001e6a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e6ac  nop
0x18001e6ad  mov     r8, rbx
0x18001e6b0  lea     rdx, [rbp+70h+var_E8]
0x18001e6b4  lea     rcx, [rbp+70h+var_A8]
0x18001e6b8  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e6bd  nop
0x18001e6be  lea     rcx, [rbp+70h+var_E8]
0x18001e6c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e6c7  mov     rbx, [r14]
0x18001e6ca  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_99a7bd846410e0b8fdde8106f358b986_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_99a7bd846410e0b8fdde8106f358b986_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e6d1  mov     [rbp+70h+var_70], rax
0x18001e6d5  lea     rax, [rsp+170h+var_140]
0x18001e6da  mov     [rbp+70h+var_68], rax
0x18001e6de  lea     rax, [rbp+70h+var_70]
0x18001e6e2  mov     [rbp+70h+var_38], rax
0x18001e6e6  lea     rdx, aSmapiaddmember; "SmapiAddMember"
0x18001e6ed  lea     rcx, [rbp+70h+var_E8]
0x18001e6f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e6f6  nop
0x18001e6f7  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e6fe  lea     rcx, [rbp+70h+var_C8]
0x18001e702  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e707  nop
0x18001e708  lea     rcx, [rbp+70h+var_70]
0x18001e70c  mov     [rsp+170h+var_148], rcx
0x18001e711  lea     rcx, [rbp+70h+var_A8]
0x18001e715  mov     [rsp+170h+var_150], rcx
0x18001e71a  lea     r9, [rbp+70h+var_E8]
0x18001e71e  mov     r8, rax
0x18001e721  lea     rdx, [rsp+170h+var_138]
0x18001e726  mov     rcx, rbx
0x18001e729  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e72e  nop
0x18001e72f  mov     rcx, rax; this
0x18001e732  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e737  nop
0x18001e738  lea     rcx, [rsp+170h+var_138]; this
0x18001e73d  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e742  nop
0x18001e743  lea     rcx, [rbp+70h+var_C8]
0x18001e747  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e74c  nop
0x18001e74d  lea     rcx, [rbp+70h+var_E8]
0x18001e751  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e756  nop
0x18001e757  lea     rcx, [rbp+70h+var_70]
0x18001e75b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e760  mov     ebx, [rsp+170h+var_140]
0x18001e764  lea     rcx, [rbp+70h+var_A8]; this
0x18001e768  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e76d  mov     eax, ebx
0x18001e76f  mov     rcx, [rbp+70h+var_30]
0x18001e773  xor     rcx, rsp; StackCookie
0x18001e776  call    __security_check_cookie
0x18001e77b  add     rsp, 150h
0x18001e782  pop     r14
0x18001e784  pop     rdi
0x18001e785  pop     rsi
0x18001e786  pop     rbx
0x18001e787  pop     rbp
0x18001e788  retn
```
