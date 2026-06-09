# wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *)

- ea: `0x18001e200`
- end: `0x18001e389`
- name: `?SetGroupRemoveVolumes@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000ad2c`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001e200`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001e2f1`: `MSFT_WvrAdminTasks`
- `0x18001e296`: `RemoveVolumeName`
- `0x18001e2e0`: `SetGroupRemoveVolumes`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *application; // rax
  __int64 v8; // rbx
  int v9; // eax
  mi::MiAsyncOperation *v10; // rax
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v15[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v16; // [rsp+B0h] [rbp-50h]
  _QWORD v17[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v18[56]; // [rsp+110h] [rbp+10h] BYREF

  v12 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v15);
  mi::MiApplication::CreateParameterSet(*application, v18);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( a3 )
  {
    std::wstring::wstring(v14, L"Name");
    mi::MiInstance::AddElement<std::wstring>(v18, v14, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v14);
  }
  if ( a4 )
  {
    std::wstring::wstring(v14, L"RemoveVolumeName");
    mi::MiInstance::AddElement(v18, v14, a4);
    std::wstring::_Tidy_deallocate(v14);
  }
  v8 = *a1;
  v17[0] = &std::_Func_impl_no_alloc<_lambda_9f280ffdb3525edee5f45e975bb2f18c_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v17[1] = &v12;
  v17[7] = v17;
  std::wstring::wstring(v14, L"SetGroupRemoveVolumes");
  v9 = std::wstring::wstring(v15, L"MSFT_WvrAdminTasks");
  v10 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v8,
                                  (unsigned int)v13,
                                  v9,
                                  (unsigned int)v14,
                                  (__int64)v18,
                                  (__int64)v17);
  mi::MiAsyncOperation::Join(v10);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v13);
  std::wstring::_Tidy_deallocate(v15);
  std::wstring::_Tidy_deallocate(v14);
  std::_Func_class<void,>::~_Func_class<void,>(v17);
  LODWORD(v8) = v12;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e200  mov     [rsp-8+arg_8], rbx
0x18001e205  push    rbp
0x18001e206  push    rsi
0x18001e207  push    rdi
0x18001e208  lea     rbp, [rsp-50h]
0x18001e20d  sub     rsp, 150h
0x18001e214  mov     rax, cs:__security_cookie
0x18001e21b  xor     rax, rsp
0x18001e21e  mov     [rbp+60h+var_18], rax
0x18001e222  mov     rbx, r9
0x18001e225  mov     rdi, r8
0x18001e228  mov     rsi, rcx
0x18001e22b  mov     [rsp+160h+var_130], 0
0x18001e233  lea     rdx, [rbp+60h+var_B8]
0x18001e237  mov     rcx, [rcx]
0x18001e23a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e23f  nop
0x18001e240  lea     rdx, [rbp+60h+var_50]
0x18001e244  mov     rcx, [rax]
0x18001e247  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e24c  nop
0x18001e24d  mov     rcx, [rbp+60h+var_B0]; this
0x18001e251  test    rcx, rcx
0x18001e254  jz      short loc_18001E25B
0x18001e256  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e25b  test    rdi, rdi
0x18001e25e  jz      short loc_18001E291
0x18001e260  lea     rdx, aName; "Name"
0x18001e267  lea     rcx, [rbp+60h+var_D8]
0x18001e26b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e270  nop
0x18001e271  mov     r9d, 2000h
0x18001e277  mov     r8, rdi
0x18001e27a  lea     rdx, [rbp+60h+var_D8]
0x18001e27e  lea     rcx, [rbp+60h+var_50]
0x18001e282  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e287  nop
0x18001e288  lea     rcx, [rbp+60h+var_D8]
0x18001e28c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e291  test    rbx, rbx
0x18001e294  jz      short loc_18001E2C1
0x18001e296  lea     rdx, aRemovevolumena; "RemoveVolumeName"
0x18001e29d  lea     rcx, [rbp+60h+var_D8]
0x18001e2a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e2a6  nop
0x18001e2a7  mov     r8, rbx
0x18001e2aa  lea     rdx, [rbp+60h+var_D8]
0x18001e2ae  lea     rcx, [rbp+60h+var_50]
0x18001e2b2  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e2b7  nop
0x18001e2b8  lea     rcx, [rbp+60h+var_D8]
0x18001e2bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e2c1  mov     rbx, [rsi]
0x18001e2c4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_9f280ffdb3525edee5f45e975bb2f18c_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_9f280ffdb3525edee5f45e975bb2f18c_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e2cb  mov     [rbp+60h+var_90], rax
0x18001e2cf  lea     rax, [rsp+160h+var_130]
0x18001e2d4  mov     [rbp+60h+var_88], rax
0x18001e2d8  lea     rax, [rbp+60h+var_90]
0x18001e2dc  mov     [rbp+60h+var_58], rax
0x18001e2e0  lea     rdx, aSetgroupremove; "SetGroupRemoveVolumes"
0x18001e2e7  lea     rcx, [rbp+60h+var_D8]
0x18001e2eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e2f0  nop
0x18001e2f1  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e2f8  lea     rcx, [rbp+60h+var_B8]
0x18001e2fc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e301  nop
0x18001e302  lea     rcx, [rbp+60h+var_90]
0x18001e306  mov     [rsp+160h+var_138], rcx
0x18001e30b  lea     rcx, [rbp+60h+var_50]
0x18001e30f  mov     [rsp+160h+var_140], rcx
0x18001e314  lea     r9, [rbp+60h+var_D8]
0x18001e318  mov     r8, rax
0x18001e31b  lea     rdx, [rsp+160h+var_128]
0x18001e320  mov     rcx, rbx
0x18001e323  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e328  nop
0x18001e329  mov     rcx, rax; this
0x18001e32c  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e331  nop
0x18001e332  lea     rcx, [rsp+160h+var_128]; this
0x18001e337  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e33c  nop
0x18001e33d  lea     rcx, [rbp+60h+var_B8]
0x18001e341  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e346  nop
0x18001e347  lea     rcx, [rbp+60h+var_D8]
0x18001e34b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e350  nop
0x18001e351  lea     rcx, [rbp+60h+var_90]
0x18001e355  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e35a  mov     ebx, [rsp+160h+var_130]
0x18001e35e  lea     rcx, [rbp+60h+var_50]; this
0x18001e362  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e367  mov     eax, ebx
0x18001e369  mov     rcx, [rbp+60h+var_18]
0x18001e36d  xor     rcx, rsp; StackCookie
0x18001e370  call    __security_check_cookie
0x18001e375  mov     rbx, [rsp+160h+arg_8]
0x18001e37d  add     rsp, 150h
0x18001e384  pop     rdi
0x18001e385  pop     rsi
0x18001e386  pop     rbp
0x18001e387  retn
```
