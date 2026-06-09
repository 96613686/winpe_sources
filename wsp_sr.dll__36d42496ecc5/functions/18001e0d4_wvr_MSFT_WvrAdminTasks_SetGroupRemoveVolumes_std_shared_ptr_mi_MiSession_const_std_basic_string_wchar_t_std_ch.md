# wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *)

- ea: `0x18001e0d4`
- end: `0x18001e25c`
- name: `?SetGroupRemoveVolumes@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000abc4`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001e0d4`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001e1c5`: `MSFT_WvrAdminTasks`
- `0x18001e16a`: `RemoveVolumeName`
- `0x18001e1b4`: `SetGroupRemoveVolumes`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(__int64 *a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 *application; // rax
  __int64 v8; // rbx
  int v9; // eax
  mi::MiAsyncOperation::MiOperationArgs **v10; // rax
  enum _MI_CancellationReason v11; // edx
  __int64 v12; // rdx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v17[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v18; // [rsp+B0h] [rbp-50h]
  _QWORD v19[8]; // [rsp+D0h] [rbp-30h] BYREF
  std::_Ref_count_base *v20[7]; // [rsp+110h] [rbp+10h] BYREF

  v14 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v17);
  mi::MiApplication::CreateParameterSet(*application, v20);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( a3 )
  {
    std::wstring::wstring((__int64)v16, (__int64)L"Name");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v16, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v16);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v16, (__int64)L"RemoveVolumeName");
    mi::MiInstance::AddElement(v20, v16, a4);
    std::wstring::_Tidy_deallocate((__int64)v16);
  }
  v8 = *a1;
  v19[0] = &std::_Func_impl_no_alloc<_lambda_9f280ffdb3525edee5f45e975bb2f18c_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v19[1] = &v14;
  v19[7] = v19;
  std::wstring::wstring((__int64)v16, (__int64)L"SetGroupRemoveVolumes");
  v9 = std::wstring::wstring((__int64)v17, (__int64)L"MSFT_WvrAdminTasks");
  v10 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v8,
                                                    (__int64)v15,
                                                    v9,
                                                    (int)v16,
                                                    (__int64)v20,
                                                    (__int64)v19);
  mi::MiAsyncOperation::Join(v10);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v15, v11);
  std::wstring::_Tidy_deallocate((__int64)v17);
  std::wstring::_Tidy_deallocate((__int64)v16);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v19, v12);
  LODWORD(v8) = v14;
  mi::MiInstance::~MiInstance(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e0d4  mov     [rsp-8+arg_8], rbx
0x18001e0d9  push    rbp
0x18001e0da  push    rsi
0x18001e0db  push    rdi
0x18001e0dc  lea     rbp, [rsp-50h]
0x18001e0e1  sub     rsp, 150h
0x18001e0e8  mov     rax, cs:__security_cookie
0x18001e0ef  xor     rax, rsp
0x18001e0f2  mov     [rbp+60h+var_18], rax
0x18001e0f6  mov     rbx, r9
0x18001e0f9  mov     rdi, r8
0x18001e0fc  mov     rsi, rcx
0x18001e0ff  mov     [rsp+160h+var_130], 0
0x18001e107  lea     rdx, [rbp+60h+var_B8]
0x18001e10b  mov     rcx, [rcx]
0x18001e10e  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e113  nop
0x18001e114  lea     rdx, [rbp+60h+var_50]
0x18001e118  mov     rcx, [rax]
0x18001e11b  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e120  nop
0x18001e121  mov     rcx, [rbp+60h+var_B0]; this
0x18001e125  test    rcx, rcx
0x18001e128  jz      short loc_18001E12F
0x18001e12a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e12f  test    rdi, rdi
0x18001e132  jz      short loc_18001E165
0x18001e134  lea     rdx, aName; "Name"
0x18001e13b  lea     rcx, [rbp+60h+var_D8]
0x18001e13f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e144  nop
0x18001e145  mov     r9d, 2000h
0x18001e14b  mov     r8, rdi
0x18001e14e  lea     rdx, [rbp+60h+var_D8]
0x18001e152  lea     rcx, [rbp+60h+var_50]
0x18001e156  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e15b  nop
0x18001e15c  lea     rcx, [rbp+60h+var_D8]
0x18001e160  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e165  test    rbx, rbx
0x18001e168  jz      short loc_18001E195
0x18001e16a  lea     rdx, aRemovevolumena; "RemoveVolumeName"
0x18001e171  lea     rcx, [rbp+60h+var_D8]
0x18001e175  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e17a  nop
0x18001e17b  mov     r8, rbx
0x18001e17e  lea     rdx, [rbp+60h+var_D8]
0x18001e182  lea     rcx, [rbp+60h+var_50]
0x18001e186  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001e18b  nop
0x18001e18c  lea     rcx, [rbp+60h+var_D8]
0x18001e190  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e195  mov     rbx, [rsi]
0x18001e198  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_9f280ffdb3525edee5f45e975bb2f18c_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_9f280ffdb3525edee5f45e975bb2f18c_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e19f  mov     [rbp+60h+var_90], rax
0x18001e1a3  lea     rax, [rsp+160h+var_130]
0x18001e1a8  mov     [rbp+60h+var_88], rax
0x18001e1ac  lea     rax, [rbp+60h+var_90]
0x18001e1b0  mov     [rbp+60h+var_58], rax
0x18001e1b4  lea     rdx, aSetgroupremove; "SetGroupRemoveVolumes"
0x18001e1bb  lea     rcx, [rbp+60h+var_D8]
0x18001e1bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e1c4  nop
0x18001e1c5  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e1cc  lea     rcx, [rbp+60h+var_B8]
0x18001e1d0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e1d5  nop
0x18001e1d6  lea     rcx, [rbp+60h+var_90]
0x18001e1da  mov     [rsp+160h+var_138], rcx
0x18001e1df  lea     rcx, [rbp+60h+var_50]
0x18001e1e3  mov     [rsp+160h+var_140], rcx
0x18001e1e8  lea     r9, [rbp+60h+var_D8]
0x18001e1ec  mov     r8, rax
0x18001e1ef  lea     rdx, [rsp+160h+var_128]
0x18001e1f4  mov     rcx, rbx
0x18001e1f7  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e1fc  nop
0x18001e1fd  mov     rcx, rax; this
0x18001e200  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e205  nop
0x18001e206  lea     rcx, [rsp+160h+var_128]; this
0x18001e20b  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e210  nop
0x18001e211  lea     rcx, [rbp+60h+var_B8]
0x18001e215  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e21a  nop
0x18001e21b  lea     rcx, [rbp+60h+var_D8]
0x18001e21f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e224  nop
0x18001e225  lea     rcx, [rbp+60h+var_90]
0x18001e229  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e22e  mov     ebx, [rsp+160h+var_130]
0x18001e232  lea     rcx, [rbp+60h+var_50]; this
0x18001e236  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e23b  mov     eax, ebx
0x18001e23d  mov     rcx, [rbp+60h+var_18]
0x18001e241  xor     rcx, rsp; StackCookie
0x18001e244  call    __security_check_cookie
0x18001e249  mov     rbx, [rsp+160h+arg_8]
0x18001e251  add     rsp, 150h
0x18001e258  pop     rdi
0x18001e259  pop     rsi
0x18001e25a  pop     rbp
0x18001e25b  retn
```
