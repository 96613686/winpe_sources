# wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,bool const *)

- ea: `0x18001f220`
- end: `0x18001f3a8`
- name: `?WvrDeleteReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEB_N@Z`
- size: `392`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18000a354`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001cbec`
- `0x18001f220`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001f311`: `MSFT_WvrAdminTasks`
- `0x18001f300`: `WvrDeleteReplicationGroup`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(__int64 *a1, _QWORD *a2, __int64 a3)
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
    std::wstring::wstring((__int64)v15, (__int64)L"FullCleanup");
    mi::MiInstance::AddElement<bool>(v19, v15, a3);
    std::wstring::_Tidy_deallocate((__int64)v15);
  }
  v7 = *a1;
  v18[0] = &std::_Func_impl_no_alloc<_lambda_47582d3328fd0554403824d9fc60f740_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v18[1] = &v13;
  v18[7] = v18;
  std::wstring::wstring((__int64)v15, (__int64)L"WvrDeleteReplicationGroup");
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
0x18001f220  mov     [rsp-8+arg_18], rbx
0x18001f225  push    rbp
0x18001f226  push    rsi
0x18001f227  push    rdi
0x18001f228  lea     rbp, [rsp-50h]
0x18001f22d  sub     rsp, 150h
0x18001f234  mov     rax, cs:__security_cookie
0x18001f23b  xor     rax, rsp
0x18001f23e  mov     [rbp+60h+var_18], rax
0x18001f242  mov     rbx, r8
0x18001f245  mov     rdi, rdx
0x18001f248  mov     rsi, rcx
0x18001f24b  mov     [rsp+160h+var_130], 0
0x18001f253  lea     rdx, [rbp+60h+var_B8]
0x18001f257  mov     rcx, [rcx]
0x18001f25a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f25f  nop
0x18001f260  lea     rdx, [rbp+60h+var_50]
0x18001f264  mov     rcx, [rax]
0x18001f267  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f26c  nop
0x18001f26d  mov     rcx, [rbp+60h+var_B0]; this
0x18001f271  test    rcx, rcx
0x18001f274  jz      short loc_18001F27B
0x18001f276  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f27b  test    rdi, rdi
0x18001f27e  jz      short loc_18001F2B1
0x18001f280  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001f287  lea     rcx, [rbp+60h+var_D8]
0x18001f28b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f290  nop
0x18001f291  mov     r9d, 2000h
0x18001f297  mov     r8, rdi
0x18001f29a  lea     rdx, [rbp+60h+var_D8]
0x18001f29e  lea     rcx, [rbp+60h+var_50]
0x18001f2a2  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f2a7  nop
0x18001f2a8  lea     rcx, [rbp+60h+var_D8]
0x18001f2ac  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f2b1  test    rbx, rbx
0x18001f2b4  jz      short loc_18001F2E1
0x18001f2b6  lea     rdx, aFullcleanup; "FullCleanup"
0x18001f2bd  lea     rcx, [rbp+60h+var_D8]
0x18001f2c1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f2c6  nop
0x18001f2c7  mov     r8, rbx
0x18001f2ca  lea     rdx, [rbp+60h+var_D8]
0x18001f2ce  lea     rcx, [rbp+60h+var_50]
0x18001f2d2  call    ??$AddElement@_N@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_NI@Z; mi::MiInstance::AddElement<bool>(std::wstring const &,bool const &,uint)
0x18001f2d7  nop
0x18001f2d8  lea     rcx, [rbp+60h+var_D8]
0x18001f2dc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f2e1  mov     rbx, [rsi]
0x18001f2e4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_47582d3328fd0554403824d9fc60f740_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_47582d3328fd0554403824d9fc60f740_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f2eb  mov     [rbp+60h+var_90], rax
0x18001f2ef  lea     rax, [rsp+160h+var_130]
0x18001f2f4  mov     [rbp+60h+var_88], rax
0x18001f2f8  lea     rax, [rbp+60h+var_90]
0x18001f2fc  mov     [rbp+60h+var_58], rax
0x18001f300  lea     rdx, aWvrdeleterepli; "WvrDeleteReplicationGroup"
0x18001f307  lea     rcx, [rbp+60h+var_D8]
0x18001f30b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f310  nop
0x18001f311  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f318  lea     rcx, [rbp+60h+var_B8]
0x18001f31c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f321  nop
0x18001f322  lea     rcx, [rbp+60h+var_90]
0x18001f326  mov     [rsp+160h+var_138], rcx
0x18001f32b  lea     rcx, [rbp+60h+var_50]
0x18001f32f  mov     [rsp+160h+var_140], rcx
0x18001f334  lea     r9, [rbp+60h+var_D8]
0x18001f338  mov     r8, rax
0x18001f33b  lea     rdx, [rsp+160h+var_128]
0x18001f340  mov     rcx, rbx
0x18001f343  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f348  nop
0x18001f349  mov     rcx, rax; this
0x18001f34c  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f351  nop
0x18001f352  lea     rcx, [rsp+160h+var_128]; this
0x18001f357  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f35c  nop
0x18001f35d  lea     rcx, [rbp+60h+var_B8]
0x18001f361  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f366  nop
0x18001f367  lea     rcx, [rbp+60h+var_D8]
0x18001f36b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f370  nop
0x18001f371  lea     rcx, [rbp+60h+var_90]
0x18001f375  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f37a  mov     ebx, [rsp+160h+var_130]
0x18001f37e  lea     rcx, [rbp+60h+var_50]; this
0x18001f382  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f387  mov     eax, ebx
0x18001f389  mov     rcx, [rbp+60h+var_18]
0x18001f38d  xor     rcx, rsp; StackCookie
0x18001f390  call    __security_check_cookie
0x18001f395  mov     rbx, [rsp+160h+arg_18]
0x18001f39d  add     rsp, 150h
0x18001f3a4  pop     rdi
0x18001f3a5  pop     rsi
0x18001f3a6  pop     rbp
0x18001f3a7  retn
```
