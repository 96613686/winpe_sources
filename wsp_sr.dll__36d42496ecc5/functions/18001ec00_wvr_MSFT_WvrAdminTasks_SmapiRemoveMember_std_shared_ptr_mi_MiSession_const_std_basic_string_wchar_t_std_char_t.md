# wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *)

- ea: `0x18001ec00`
- end: `0x18001ed88`
- name: `?SmapiRemoveMember@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000aa28`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001ec00`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001ecf1`: `MSFT_WvrAdminTasks`
- `0x18001ece0`: `SmapiRemoveMember`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(__int64 *a1, _QWORD *a2, __int64 a3)
{
  __int64 *application; // rax
  __int64 v7; // rbx
  int v8; // eax
  mi::MiAsyncOperation::MiOperationArgs **v9; // rax
  enum _MI_CancellationReason v10; // edx
  __int64 v11; // rdx
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v16[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v17; // [rsp+B0h] [rbp-50h]
  _QWORD v18[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v19[7]; // [rsp+110h] [rbp+10h] BYREF

  v13 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v16);
  mi::MiApplication::CreateParameterSet(*application, v19);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v15, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v19, (int)v15, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v15);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v15, (__int64)L"PartitionObjectIds");
    mi::MiInstance::AddElement(v19, v15, a3);
    std::wstring::_Tidy_deallocate((__int64)v15);
  }
  v7 = *a1;
  v18[0] = &std::_Func_impl_no_alloc<_lambda_016ea3eef90b7c7afe4ce333cad6ddec_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v18[1] = &v13;
  v18[7] = v18;
  std::wstring::wstring((__int64)v15, (__int64)L"SmapiRemoveMember");
  v8 = std::wstring::wstring((__int64)v16, (__int64)L"MSFT_WvrAdminTasks");
  v9 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                   v7,
                                                   (__int64)v14,
                                                   v8,
                                                   (int)v15,
                                                   (__int64)v19,
                                                   (__int64)v18);
  mi::MiAsyncOperation::Join(v9);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v14, v10);
  std::wstring::_Tidy_deallocate((__int64)v16);
  std::wstring::_Tidy_deallocate((__int64)v15);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v18, v11);
  LODWORD(v7) = v13;
  mi::MiInstance::~MiInstance(v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ec00  mov     [rsp-8+arg_18], rbx
0x18001ec05  push    rbp
0x18001ec06  push    rsi
0x18001ec07  push    rdi
0x18001ec08  lea     rbp, [rsp-50h]
0x18001ec0d  sub     rsp, 150h
0x18001ec14  mov     rax, cs:__security_cookie
0x18001ec1b  xor     rax, rsp
0x18001ec1e  mov     [rbp+60h+var_18], rax
0x18001ec22  mov     rbx, r8
0x18001ec25  mov     rdi, rdx
0x18001ec28  mov     rsi, rcx
0x18001ec2b  mov     [rsp+160h+var_130], 0
0x18001ec33  lea     rdx, [rbp+60h+var_B8]
0x18001ec37  mov     rcx, [rcx]
0x18001ec3a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001ec3f  nop
0x18001ec40  lea     rdx, [rbp+60h+var_50]
0x18001ec44  mov     rcx, [rax]
0x18001ec47  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001ec4c  nop
0x18001ec4d  mov     rcx, [rbp+60h+var_B0]; this
0x18001ec51  test    rcx, rcx
0x18001ec54  jz      short loc_18001EC5B
0x18001ec56  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ec5b  test    rdi, rdi
0x18001ec5e  jz      short loc_18001EC91
0x18001ec60  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001ec67  lea     rcx, [rbp+60h+var_D8]
0x18001ec6b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ec70  nop
0x18001ec71  mov     r9d, 2000h
0x18001ec77  mov     r8, rdi
0x18001ec7a  lea     rdx, [rbp+60h+var_D8]
0x18001ec7e  lea     rcx, [rbp+60h+var_50]
0x18001ec82  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ec87  nop
0x18001ec88  lea     rcx, [rbp+60h+var_D8]
0x18001ec8c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ec91  test    rbx, rbx
0x18001ec94  jz      short loc_18001ECC1
0x18001ec96  lea     rdx, aPartitionobjec; "PartitionObjectIds"
0x18001ec9d  lea     rcx, [rbp+60h+var_D8]
0x18001eca1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eca6  nop
0x18001eca7  mov     r8, rbx
0x18001ecaa  lea     rdx, [rbp+60h+var_D8]
0x18001ecae  lea     rcx, [rbp+60h+var_50]
0x18001ecb2  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001ecb7  nop
0x18001ecb8  lea     rcx, [rbp+60h+var_D8]
0x18001ecbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ecc1  mov     rbx, [rsi]
0x18001ecc4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_016ea3eef90b7c7afe4ce333cad6ddec_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_016ea3eef90b7c7afe4ce333cad6ddec_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001eccb  mov     [rbp+60h+var_90], rax
0x18001eccf  lea     rax, [rsp+160h+var_130]
0x18001ecd4  mov     [rbp+60h+var_88], rax
0x18001ecd8  lea     rax, [rbp+60h+var_90]
0x18001ecdc  mov     [rbp+60h+var_58], rax
0x18001ece0  lea     rdx, aSmapiremovemem; "SmapiRemoveMember"
0x18001ece7  lea     rcx, [rbp+60h+var_D8]
0x18001eceb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ecf0  nop
0x18001ecf1  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001ecf8  lea     rcx, [rbp+60h+var_B8]
0x18001ecfc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ed01  nop
0x18001ed02  lea     rcx, [rbp+60h+var_90]
0x18001ed06  mov     [rsp+160h+var_138], rcx
0x18001ed0b  lea     rcx, [rbp+60h+var_50]
0x18001ed0f  mov     [rsp+160h+var_140], rcx
0x18001ed14  lea     r9, [rbp+60h+var_D8]
0x18001ed18  mov     r8, rax
0x18001ed1b  lea     rdx, [rsp+160h+var_128]
0x18001ed20  mov     rcx, rbx
0x18001ed23  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001ed28  nop
0x18001ed29  mov     rcx, rax; this
0x18001ed2c  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001ed31  nop
0x18001ed32  lea     rcx, [rsp+160h+var_128]; this
0x18001ed37  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001ed3c  nop
0x18001ed3d  lea     rcx, [rbp+60h+var_B8]
0x18001ed41  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ed46  nop
0x18001ed47  lea     rcx, [rbp+60h+var_D8]
0x18001ed4b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ed50  nop
0x18001ed51  lea     rcx, [rbp+60h+var_90]
0x18001ed55  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001ed5a  mov     ebx, [rsp+160h+var_130]
0x18001ed5e  lea     rcx, [rbp+60h+var_50]; this
0x18001ed62  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001ed67  mov     eax, ebx
0x18001ed69  mov     rcx, [rbp+60h+var_18]
0x18001ed6d  xor     rcx, rsp; StackCookie
0x18001ed70  call    __security_check_cookie
0x18001ed75  mov     rbx, [rsp+160h+arg_18]
0x18001ed7d  add     rsp, 150h
0x18001ed84  pop     rdi
0x18001ed85  pop     rsi
0x18001ed86  pop     rbp
0x18001ed87  retn
```
