# wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *)

- ea: `0x18001ed30`
- end: `0x18001eeb9`
- name: `?SmapiRemoveMember@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000ab90`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001ed30`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001ee21`: `MSFT_WvrAdminTasks`
- `0x18001ee10`: `SmapiRemoveMember`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *application; // rax
  __int64 v7; // rbx
  int v8; // eax
  mi::MiAsyncOperation *v9; // rax
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v14[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v15; // [rsp+B0h] [rbp-50h]
  _QWORD v16[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v17[56]; // [rsp+110h] [rbp+10h] BYREF

  v11 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v14);
  mi::MiApplication::CreateParameterSet(*application, v17);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( a2 )
  {
    std::wstring::wstring(v13, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v17, v13, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v13);
  }
  if ( a3 )
  {
    std::wstring::wstring(v13, L"PartitionObjectIds");
    mi::MiInstance::AddElement(v17, v13, a3);
    std::wstring::_Tidy_deallocate(v13);
  }
  v7 = *a1;
  v16[0] = &std::_Func_impl_no_alloc<_lambda_016ea3eef90b7c7afe4ce333cad6ddec_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v16[1] = &v11;
  v16[7] = v16;
  std::wstring::wstring(v13, L"SmapiRemoveMember");
  v8 = std::wstring::wstring(v14, L"MSFT_WvrAdminTasks");
  v9 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                 v7,
                                 (unsigned int)v12,
                                 v8,
                                 (unsigned int)v13,
                                 (__int64)v17,
                                 (__int64)v16);
  mi::MiAsyncOperation::Join(v9);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v12);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v13);
  std::_Func_class<void,>::~_Func_class<void,>(v16);
  LODWORD(v7) = v11;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ed30  mov     [rsp-8+arg_18], rbx
0x18001ed35  push    rbp
0x18001ed36  push    rsi
0x18001ed37  push    rdi
0x18001ed38  lea     rbp, [rsp-50h]
0x18001ed3d  sub     rsp, 150h
0x18001ed44  mov     rax, cs:__security_cookie
0x18001ed4b  xor     rax, rsp
0x18001ed4e  mov     [rbp+60h+var_18], rax
0x18001ed52  mov     rbx, r8
0x18001ed55  mov     rdi, rdx
0x18001ed58  mov     rsi, rcx
0x18001ed5b  mov     [rsp+160h+var_130], 0
0x18001ed63  lea     rdx, [rbp+60h+var_B8]
0x18001ed67  mov     rcx, [rcx]
0x18001ed6a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001ed6f  nop
0x18001ed70  lea     rdx, [rbp+60h+var_50]
0x18001ed74  mov     rcx, [rax]
0x18001ed77  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001ed7c  nop
0x18001ed7d  mov     rcx, [rbp+60h+var_B0]; this
0x18001ed81  test    rcx, rcx
0x18001ed84  jz      short loc_18001ED8B
0x18001ed86  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ed8b  test    rdi, rdi
0x18001ed8e  jz      short loc_18001EDC1
0x18001ed90  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001ed97  lea     rcx, [rbp+60h+var_D8]
0x18001ed9b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eda0  nop
0x18001eda1  mov     r9d, 2000h
0x18001eda7  mov     r8, rdi
0x18001edaa  lea     rdx, [rbp+60h+var_D8]
0x18001edae  lea     rcx, [rbp+60h+var_50]
0x18001edb2  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001edb7  nop
0x18001edb8  lea     rcx, [rbp+60h+var_D8]
0x18001edbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001edc1  test    rbx, rbx
0x18001edc4  jz      short loc_18001EDF1
0x18001edc6  lea     rdx, aPartitionobjec; "PartitionObjectIds"
0x18001edcd  lea     rcx, [rbp+60h+var_D8]
0x18001edd1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001edd6  nop
0x18001edd7  mov     r8, rbx
0x18001edda  lea     rdx, [rbp+60h+var_D8]
0x18001edde  lea     rcx, [rbp+60h+var_50]
0x18001ede2  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001ede7  nop
0x18001ede8  lea     rcx, [rbp+60h+var_D8]
0x18001edec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001edf1  mov     rbx, [rsi]
0x18001edf4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_016ea3eef90b7c7afe4ce333cad6ddec_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_016ea3eef90b7c7afe4ce333cad6ddec_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001edfb  mov     [rbp+60h+var_90], rax
0x18001edff  lea     rax, [rsp+160h+var_130]
0x18001ee04  mov     [rbp+60h+var_88], rax
0x18001ee08  lea     rax, [rbp+60h+var_90]
0x18001ee0c  mov     [rbp+60h+var_58], rax
0x18001ee10  lea     rdx, aSmapiremovemem; "SmapiRemoveMember"
0x18001ee17  lea     rcx, [rbp+60h+var_D8]
0x18001ee1b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ee20  nop
0x18001ee21  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001ee28  lea     rcx, [rbp+60h+var_B8]
0x18001ee2c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ee31  nop
0x18001ee32  lea     rcx, [rbp+60h+var_90]
0x18001ee36  mov     [rsp+160h+var_138], rcx
0x18001ee3b  lea     rcx, [rbp+60h+var_50]
0x18001ee3f  mov     [rsp+160h+var_140], rcx
0x18001ee44  lea     r9, [rbp+60h+var_D8]
0x18001ee48  mov     r8, rax
0x18001ee4b  lea     rdx, [rsp+160h+var_128]
0x18001ee50  mov     rcx, rbx
0x18001ee53  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001ee58  nop
0x18001ee59  mov     rcx, rax; this
0x18001ee5c  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001ee61  nop
0x18001ee62  lea     rcx, [rsp+160h+var_128]; this
0x18001ee67  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001ee6c  nop
0x18001ee6d  lea     rcx, [rbp+60h+var_B8]
0x18001ee71  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee76  nop
0x18001ee77  lea     rcx, [rbp+60h+var_D8]
0x18001ee7b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee80  nop
0x18001ee81  lea     rcx, [rbp+60h+var_90]
0x18001ee85  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001ee8a  mov     ebx, [rsp+160h+var_130]
0x18001ee8e  lea     rcx, [rbp+60h+var_50]; this
0x18001ee92  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001ee97  mov     eax, ebx
0x18001ee99  mov     rcx, [rbp+60h+var_18]
0x18001ee9d  xor     rcx, rsp; StackCookie
0x18001eea0  call    __security_check_cookie
0x18001eea5  mov     rbx, [rsp+160h+arg_18]
0x18001eead  add     rsp, 150h
0x18001eeb4  pop     rdi
0x18001eeb5  pop     rsi
0x18001eeb6  pop     rbp
0x18001eeb7  retn
```
