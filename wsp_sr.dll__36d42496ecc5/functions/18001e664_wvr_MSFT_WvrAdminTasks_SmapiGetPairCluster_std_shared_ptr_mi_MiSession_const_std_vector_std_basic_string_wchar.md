# wvr::MSFT_WvrAdminTasks::SmapiGetPairCluster(std::shared_ptr<mi::MiSession> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x18001e664`
- end: `0x18001e756`
- name: `?SmapiGetPairCluster@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@1@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180005db8`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x180008704`
- `0x180024c98`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001e6d5`: `MSFT_WvrAdminTasks`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SmapiGetPairCluster(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  int v4; // eax
  mi::MiAsyncOperation::MiOperationArgs **v5; // rax
  enum _MI_CancellationReason v6; // edx
  __int64 v7; // rdx
  unsigned int v9; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v10[88]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v11[8]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v12[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v13[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v14; // [rsp+140h] [rbp+38h] BYREF
  __int64 v15; // [rsp+148h] [rbp+40h] BYREF

  v15 = a3;
  v14 = a2;
  v9 = 0;
  v3 = *a1;
  v11[0] = &std::_Func_impl_no_alloc<_lambda_359ec5393a421c698912e77a43a92501_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v11[1] = &v9;
  v11[2] = &v14;
  v11[3] = &v15;
  v11[7] = v11;
  std::wstring::wstring((__int64)v12, (__int64)L"SmapiGetPairCluster");
  v4 = std::wstring::wstring((__int64)v13, (__int64)L"MSFT_WvrAdminTasks");
  v5 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                   v3,
                                                   (unsigned int)v10,
                                                   v4,
                                                   (unsigned int)v12,
                                                   (__int64)v11);
  mi::MiAsyncOperation::Join(v5);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v10, v6);
  std::wstring::_Tidy_deallocate((__int64)v13);
  std::wstring::_Tidy_deallocate((__int64)v12);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v11, v7);
  return v9;
}

```

## disassembly

```asm
0x18001e664  mov     rax, rsp
0x18001e667  mov     [rax+20h], rbx
0x18001e66b  mov     [rax+18h], r8
0x18001e66f  mov     [rax+10h], rdx
0x18001e673  push    rbp
0x18001e674  lea     rbp, [rax-28h]
0x18001e678  sub     rsp, 120h
0x18001e67f  mov     rax, cs:__security_cookie
0x18001e686  xor     rax, rsp
0x18001e689  mov     [rbp+20h+var_10], rax
0x18001e68d  mov     [rsp+120h+var_F0], 0
0x18001e695  mov     rbx, [rcx]
0x18001e698  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_359ec5393a421c698912e77a43a92501_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_359ec5393a421c698912e77a43a92501_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e69f  mov     [rbp+20h+var_90], rax
0x18001e6a3  lea     rax, [rsp+120h+var_F0]
0x18001e6a8  mov     [rbp+20h+var_88], rax
0x18001e6ac  lea     rax, [rbp+20h+arg_8]
0x18001e6b0  mov     [rbp+20h+var_80], rax
0x18001e6b4  lea     rax, [rbp+20h+arg_10]
0x18001e6b8  mov     [rbp+20h+var_78], rax
0x18001e6bc  lea     rax, [rbp+20h+var_90]
0x18001e6c0  mov     [rbp+20h+var_58], rax
0x18001e6c4  lea     rdx, aSmapigetpaircl; "SmapiGetPairCluster"
0x18001e6cb  lea     rcx, [rbp+20h+var_50]
0x18001e6cf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e6d4  nop
0x18001e6d5  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e6dc  lea     rcx, [rbp+20h+var_30]
0x18001e6e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e6e5  nop
0x18001e6e6  lea     rcx, [rbp+20h+var_90]
0x18001e6ea  mov     [rsp+20h], rcx
0x18001e6ef  lea     r9, [rbp+20h+var_50]
0x18001e6f3  mov     r8, rax
0x18001e6f6  lea     rdx, [rsp+120h+var_E8]
0x18001e6fb  mov     rcx, rbx
0x18001e6fe  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e703  nop
0x18001e704  mov     rcx, rax; this
0x18001e707  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e70c  nop
0x18001e70d  lea     rcx, [rsp+120h+var_E8]; this
0x18001e712  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e717  nop
0x18001e718  lea     rcx, [rbp+20h+var_30]
0x18001e71c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e721  nop
0x18001e722  lea     rcx, [rbp+20h+var_50]
0x18001e726  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e72b  nop
0x18001e72c  lea     rcx, [rbp+20h+var_90]
0x18001e730  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e735  mov     eax, [rsp+120h+var_F0]
0x18001e739  mov     rcx, [rbp+20h+var_10]
0x18001e73d  xor     rcx, rsp; StackCookie
0x18001e740  call    __security_check_cookie
0x18001e745  mov     rbx, [rsp+120h+arg_18]
0x18001e74d  add     rsp, 120h
0x18001e754  pop     rbp
0x18001e755  retn
```
