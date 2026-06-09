# wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerPartitions(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,ushort *,_MI_Datetime *,uint *)

- ea: `0x18001ea08`
- end: `0x18001ebc8`
- name: `?SmapiQueryPartnerPartitions@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEAV54@2PEAGPEAU_MI_Datetime@@PEAI@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180014450`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001ea08`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001eb37`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 wvr::MSFT_WvrAdminTasks::SmapiQueryPartnerPartitions(_QWORD *a1, __int64 a2, __int64 a3, ...)
{
  _QWORD *application; // rax
  __int64 v7; // rbx
  int v8; // eax
  mi::MiAsyncOperation *v9; // rax
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[40]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v14[8]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v15[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v16; // [rsp+F8h] [rbp-8h]
  _BYTE v17[56]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v18; // [rsp+198h] [rbp+98h] BYREF
  va_list va; // [rsp+198h] [rbp+98h]
  __int64 v20; // [rsp+1A0h] [rbp+A0h] BYREF
  va_list va1; // [rsp+1A0h] [rbp+A0h]
  __int64 v22; // [rsp+1A8h] [rbp+A8h] BYREF
  va_list va2; // [rsp+1A8h] [rbp+A8h]
  __int64 v24; // [rsp+1B0h] [rbp+B0h] BYREF
  va_list va3; // [rsp+1B0h] [rbp+B0h]
  va_list va4; // [rsp+1B8h] [rbp+B8h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v22 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v24 = va_arg(va4, _QWORD);
  v11 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v15);
  mi::MiApplication::CreateParameterSet(*application, v17);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( a2 )
  {
    std::wstring::wstring(v13, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v17, v13, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v13);
  }
  if ( a3 )
  {
    std::wstring::wstring(v13, L"PartitionId");
    mi::MiInstance::AddElement<std::wstring>(v17, v13, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v13);
  }
  v7 = *a1;
  v14[0] = &std::_Func_impl_no_alloc<_lambda_dde23385866a357cf8fa76a26c5b3433_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v14[1] = &v11;
  va_copy((va_list)&v14[2], va);
  va_copy((va_list)&v14[3], va1);
  va_copy((va_list)&v14[4], va2);
  va_copy((va_list)&v14[5], va3);
  va_copy((va_list)&v14[6], va4);
  v14[7] = v14;
  std::wstring::wstring(v13, L"SmapiQueryPartnerPartitions");
  v8 = std::wstring::wstring(v15, L"MSFT_WvrAdminTasks");
  v9 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                 v7,
                                 (unsigned int)v12,
                                 v8,
                                 (unsigned int)v13,
                                 (__int64)v17,
                                 (__int64)v14);
  mi::MiAsyncOperation::Join(v9);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v12);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v13);
  std::_Func_class<void,>::~_Func_class<void,>(v14);
  LODWORD(v7) = v11;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ea08  mov     [rsp-8+arg_18], r9
0x18001ea0d  push    rbp
0x18001ea0e  push    rbx
0x18001ea0f  push    rsi
0x18001ea10  push    rdi
0x18001ea11  lea     rbp, [rsp-58h]
0x18001ea16  sub     rsp, 158h
0x18001ea1d  mov     rax, cs:__security_cookie
0x18001ea24  xor     rax, rsp
0x18001ea27  mov     [rbp+70h+var_28], rax
0x18001ea2b  mov     rbx, r8
0x18001ea2e  mov     rdi, rdx
0x18001ea31  mov     rsi, rcx
0x18001ea34  mov     [rsp+170h+var_140], 0
0x18001ea3c  lea     rdx, [rbp+70h+var_80]
0x18001ea40  mov     rcx, [rcx]
0x18001ea43  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001ea48  nop
0x18001ea49  lea     rdx, [rbp+70h+var_60]
0x18001ea4d  mov     rcx, [rax]
0x18001ea50  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001ea55  nop
0x18001ea56  mov     rcx, [rbp+70h+var_78]; this
0x18001ea5a  test    rcx, rcx
0x18001ea5d  jz      short loc_18001EA64
0x18001ea5f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ea64  test    rdi, rdi
0x18001ea67  jz      short loc_18001EA9A
0x18001ea69  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001ea70  lea     rcx, [rbp+70h+var_E8]
0x18001ea74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ea79  nop
0x18001ea7a  mov     r9d, 2000h
0x18001ea80  mov     r8, rdi
0x18001ea83  lea     rdx, [rbp+70h+var_E8]
0x18001ea87  lea     rcx, [rbp+70h+var_60]
0x18001ea8b  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ea90  nop
0x18001ea91  lea     rcx, [rbp+70h+var_E8]
0x18001ea95  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea9a  test    rbx, rbx
0x18001ea9d  jz      short loc_18001EAD0
0x18001ea9f  lea     rdx, aPartitionid; "PartitionId"
0x18001eaa6  lea     rcx, [rbp+70h+var_E8]
0x18001eaaa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eaaf  nop
0x18001eab0  mov     r9d, 2000h
0x18001eab6  mov     r8, rbx
0x18001eab9  lea     rdx, [rbp+70h+var_E8]
0x18001eabd  lea     rcx, [rbp+70h+var_60]
0x18001eac1  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001eac6  nop
0x18001eac7  lea     rcx, [rbp+70h+var_E8]
0x18001eacb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ead0  mov     rbx, [rsi]
0x18001ead3  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_dde23385866a357cf8fa76a26c5b3433_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_dde23385866a357cf8fa76a26c5b3433_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001eada  mov     [rbp+70h+var_C0], rax
0x18001eade  lea     rax, [rsp+170h+var_140]
0x18001eae3  mov     [rbp+70h+var_B8], rax
0x18001eae7  lea     rax, [rbp+70h+arg_18]
0x18001eaee  mov     [rbp+70h+var_B0], rax
0x18001eaf2  lea     rax, [rbp+70h+arg_20]
0x18001eaf9  mov     [rbp+70h+var_A8], rax
0x18001eafd  lea     rax, [rbp+70h+arg_28]
0x18001eb04  mov     [rbp+70h+var_A0], rax
0x18001eb08  lea     rax, [rbp+70h+arg_30]
0x18001eb0f  mov     [rbp+70h+var_98], rax
0x18001eb13  lea     rax, [rbp+70h+arg_38]
0x18001eb1a  mov     [rbp+70h+var_90], rax
0x18001eb1e  lea     rax, [rbp+70h+var_C0]
0x18001eb22  mov     [rbp+70h+var_88], rax
0x18001eb26  lea     rdx, aSmapiquerypart; "SmapiQueryPartnerPartitions"
0x18001eb2d  lea     rcx, [rbp+70h+var_E8]
0x18001eb31  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eb36  nop
0x18001eb37  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001eb3e  lea     rcx, [rbp+70h+var_80]
0x18001eb42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eb47  nop
0x18001eb48  lea     rcx, [rbp+70h+var_C0]
0x18001eb4c  mov     [rsp+170h+var_148], rcx
0x18001eb51  lea     rcx, [rbp+70h+var_60]
0x18001eb55  mov     [rsp+170h+var_150], rcx
0x18001eb5a  lea     r9, [rbp+70h+var_E8]
0x18001eb5e  mov     r8, rax
0x18001eb61  lea     rdx, [rsp+170h+var_138]
0x18001eb66  mov     rcx, rbx
0x18001eb69  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001eb6e  nop
0x18001eb6f  mov     rcx, rax; this
0x18001eb72  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001eb77  nop
0x18001eb78  lea     rcx, [rsp+170h+var_138]; this
0x18001eb7d  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001eb82  nop
0x18001eb83  lea     rcx, [rbp+70h+var_80]
0x18001eb87  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eb8c  nop
0x18001eb8d  lea     rcx, [rbp+70h+var_E8]
0x18001eb91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eb96  nop
0x18001eb97  lea     rcx, [rbp+70h+var_C0]
0x18001eb9b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001eba0  mov     ebx, [rsp+170h+var_140]
0x18001eba4  lea     rcx, [rbp+70h+var_60]; this
0x18001eba8  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001ebad  mov     eax, ebx
0x18001ebaf  mov     rcx, [rbp+70h+var_28]
0x18001ebb3  xor     rcx, rsp; StackCookie
0x18001ebb6  call    __security_check_cookie
0x18001ebbb  add     rsp, 158h
0x18001ebc2  pop     rdi
0x18001ebc3  pop     rsi
0x18001ebc4  pop     rbx
0x18001ebc5  pop     rbp
0x18001ebc6  retn
```
