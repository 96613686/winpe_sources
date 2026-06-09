# wvr::MSFT_WvrAdminTasks::SmapiGetPairCluster(std::shared_ptr<mi::MiSession> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x18001e790`
- end: `0x18001e883`
- name: `?SmapiGetPairCluster@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@1@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180005df8`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180008868`
- `0x180024f88`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001e801`: `MSFT_WvrAdminTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wvr::MSFT_WvrAdminTasks::SmapiGetPairCluster(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  int v4; // eax
  mi::MiAsyncOperation *v5; // rax
  unsigned int v7; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v8[88]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v9[8]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v10[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v11[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v12; // [rsp+140h] [rbp+38h] BYREF
  __int64 v13; // [rsp+148h] [rbp+40h] BYREF

  v13 = a3;
  v12 = a2;
  v7 = 0;
  v3 = *a1;
  v9[0] = &std::_Func_impl_no_alloc<_lambda_359ec5393a421c698912e77a43a92501_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v9[1] = &v7;
  v9[2] = &v12;
  v9[3] = &v13;
  v9[7] = v9;
  std::wstring::wstring(v10, L"SmapiGetPairCluster");
  v4 = std::wstring::wstring(v11, L"MSFT_WvrAdminTasks");
  v5 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(v3, (unsigned int)v8, v4, (unsigned int)v10, (__int64)v9);
  mi::MiAsyncOperation::Join(v5);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v8);
  std::wstring::_Tidy_deallocate(v11);
  std::wstring::_Tidy_deallocate(v10);
  std::_Func_class<void,>::~_Func_class<void,>(v9);
  return v7;
}

```

## disassembly

```asm
0x18001e790  mov     rax, rsp
0x18001e793  mov     [rax+20h], rbx
0x18001e797  mov     [rax+18h], r8
0x18001e79b  mov     [rax+10h], rdx
0x18001e79f  push    rbp
0x18001e7a0  lea     rbp, [rax-28h]
0x18001e7a4  sub     rsp, 120h
0x18001e7ab  mov     rax, cs:__security_cookie
0x18001e7b2  xor     rax, rsp
0x18001e7b5  mov     [rbp+20h+var_10], rax
0x18001e7b9  mov     [rsp+120h+var_F0], 0
0x18001e7c1  mov     rbx, [rcx]
0x18001e7c4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_359ec5393a421c698912e77a43a92501_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_359ec5393a421c698912e77a43a92501_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e7cb  mov     [rbp+20h+var_90], rax
0x18001e7cf  lea     rax, [rsp+120h+var_F0]
0x18001e7d4  mov     [rbp+20h+var_88], rax
0x18001e7d8  lea     rax, [rbp+20h+arg_8]
0x18001e7dc  mov     [rbp+20h+var_80], rax
0x18001e7e0  lea     rax, [rbp+20h+arg_10]
0x18001e7e4  mov     [rbp+20h+var_78], rax
0x18001e7e8  lea     rax, [rbp+20h+var_90]
0x18001e7ec  mov     [rbp+20h+var_58], rax
0x18001e7f0  lea     rdx, aSmapigetpaircl; "SmapiGetPairCluster"
0x18001e7f7  lea     rcx, [rbp+20h+var_50]
0x18001e7fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e800  nop
0x18001e801  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e808  lea     rcx, [rbp+20h+var_30]
0x18001e80c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e811  nop
0x18001e812  lea     rcx, [rbp+20h+var_90]
0x18001e816  mov     [rsp+20h], rcx
0x18001e81b  lea     r9, [rbp+20h+var_50]
0x18001e81f  mov     r8, rax
0x18001e822  lea     rdx, [rsp+120h+var_E8]
0x18001e827  mov     rcx, rbx
0x18001e82a  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e82f  nop
0x18001e830  mov     rcx, rax; this
0x18001e833  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e838  nop
0x18001e839  lea     rcx, [rsp+120h+var_E8]; this
0x18001e83e  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e843  nop
0x18001e844  lea     rcx, [rbp+20h+var_30]
0x18001e848  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e84d  nop
0x18001e84e  lea     rcx, [rbp+20h+var_50]
0x18001e852  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e857  nop
0x18001e858  lea     rcx, [rbp+20h+var_90]
0x18001e85c  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e861  mov     eax, [rsp+120h+var_F0]
0x18001e865  mov     rcx, [rbp+20h+var_10]
0x18001e869  xor     rcx, rsp; StackCookie
0x18001e86c  call    __security_check_cookie
0x18001e871  mov     rbx, [rsp+120h+arg_18]
0x18001e879  add     rsp, 120h
0x18001e880  pop     rbp
0x18001e881  retn
```
