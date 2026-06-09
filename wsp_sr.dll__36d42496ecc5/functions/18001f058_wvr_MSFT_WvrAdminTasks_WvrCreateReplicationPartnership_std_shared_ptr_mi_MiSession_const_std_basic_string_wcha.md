# wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *)

- ea: `0x18001f058`
- end: `0x18001f219`
- name: `?WvrCreateReplicationPartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111@Z`
- size: `449`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a16c`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001f058`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001f187`: `MSFT_WvrAdminTasks`
- `0x18001f126`: `TargetComputerName`
- `0x18001f176`: `WvrCreateReplicationPartnership`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
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
    std::wstring::wstring((__int64)v17, (__int64)L"SourceReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v17, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v17);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v17, (__int64)L"TargetReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v17, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v17);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v17, (__int64)L"TargetComputerName");
    mi::MiInstance::AddElement<std::wstring>((int)v20, (int)v17, a4, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v17);
  }
  v9 = *a1;
  v21[0] = &std::_Func_impl_no_alloc<_lambda_384ead2774eecb21d450a830335cc63e_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v21[1] = &v15;
  v21[7] = v21;
  std::wstring::wstring((__int64)v17, (__int64)L"WvrCreateReplicationPartnership");
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
0x18001f058  push    rbp
0x18001f05a  push    rbx
0x18001f05b  push    rsi
0x18001f05c  push    rdi
0x18001f05d  push    r14
0x18001f05f  lea     rbp, [rsp-50h]
0x18001f064  sub     rsp, 150h
0x18001f06b  mov     rax, cs:__security_cookie
0x18001f072  xor     rax, rsp
0x18001f075  mov     [rbp+70h+var_30], rax
0x18001f079  mov     rbx, r9
0x18001f07c  mov     rsi, r8
0x18001f07f  mov     rdi, rdx
0x18001f082  mov     r14, rcx
0x18001f085  mov     [rsp+170h+var_140], 0
0x18001f08d  lea     rdx, [rbp+70h+var_C8]
0x18001f091  mov     rcx, [rcx]
0x18001f094  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001f099  nop
0x18001f09a  lea     rdx, [rbp+70h+var_A8]
0x18001f09e  mov     rcx, [rax]
0x18001f0a1  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001f0a6  nop
0x18001f0a7  mov     rcx, [rbp+70h+var_C0]; this
0x18001f0ab  test    rcx, rcx
0x18001f0ae  jz      short loc_18001F0B5
0x18001f0b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f0b5  test    rdi, rdi
0x18001f0b8  jz      short loc_18001F0EB
0x18001f0ba  lea     rdx, aSourcereplicat; "SourceReplicationGroupName"
0x18001f0c1  lea     rcx, [rbp+70h+var_E8]
0x18001f0c5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f0ca  nop
0x18001f0cb  mov     r9d, 2000h
0x18001f0d1  mov     r8, rdi
0x18001f0d4  lea     rdx, [rbp+70h+var_E8]
0x18001f0d8  lea     rcx, [rbp+70h+var_A8]
0x18001f0dc  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f0e1  nop
0x18001f0e2  lea     rcx, [rbp+70h+var_E8]
0x18001f0e6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f0eb  test    rsi, rsi
0x18001f0ee  jz      short loc_18001F121
0x18001f0f0  lea     rdx, aTargetreplicat_1; "TargetReplicationGroupName"
0x18001f0f7  lea     rcx, [rbp+70h+var_E8]
0x18001f0fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f100  nop
0x18001f101  mov     r9d, 2000h
0x18001f107  mov     r8, rsi
0x18001f10a  lea     rdx, [rbp+70h+var_E8]
0x18001f10e  lea     rcx, [rbp+70h+var_A8]
0x18001f112  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f117  nop
0x18001f118  lea     rcx, [rbp+70h+var_E8]
0x18001f11c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f121  test    rbx, rbx
0x18001f124  jz      short loc_18001F157
0x18001f126  lea     rdx, aTargetcomputer; "TargetComputerName"
0x18001f12d  lea     rcx, [rbp+70h+var_E8]
0x18001f131  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f136  nop
0x18001f137  mov     r9d, 2000h
0x18001f13d  mov     r8, rbx
0x18001f140  lea     rdx, [rbp+70h+var_E8]
0x18001f144  lea     rcx, [rbp+70h+var_A8]
0x18001f148  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f14d  nop
0x18001f14e  lea     rcx, [rbp+70h+var_E8]
0x18001f152  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f157  mov     rbx, [r14]
0x18001f15a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_384ead2774eecb21d450a830335cc63e_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_384ead2774eecb21d450a830335cc63e_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f161  mov     [rbp+70h+var_70], rax
0x18001f165  lea     rax, [rsp+170h+var_140]
0x18001f16a  mov     [rbp+70h+var_68], rax
0x18001f16e  lea     rax, [rbp+70h+var_70]
0x18001f172  mov     [rbp+70h+var_38], rax
0x18001f176  lea     rdx, aWvrcreaterepli; "WvrCreateReplicationPartnership"
0x18001f17d  lea     rcx, [rbp+70h+var_E8]
0x18001f181  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f186  nop
0x18001f187  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f18e  lea     rcx, [rbp+70h+var_C8]
0x18001f192  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f197  nop
0x18001f198  lea     rcx, [rbp+70h+var_70]
0x18001f19c  mov     [rsp+170h+var_148], rcx
0x18001f1a1  lea     rcx, [rbp+70h+var_A8]
0x18001f1a5  mov     [rsp+170h+var_150], rcx
0x18001f1aa  lea     r9, [rbp+70h+var_E8]
0x18001f1ae  mov     r8, rax
0x18001f1b1  lea     rdx, [rsp+170h+var_138]
0x18001f1b6  mov     rcx, rbx
0x18001f1b9  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f1be  nop
0x18001f1bf  mov     rcx, rax; this
0x18001f1c2  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f1c7  nop
0x18001f1c8  lea     rcx, [rsp+170h+var_138]; this
0x18001f1cd  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f1d2  nop
0x18001f1d3  lea     rcx, [rbp+70h+var_C8]
0x18001f1d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f1dc  nop
0x18001f1dd  lea     rcx, [rbp+70h+var_E8]
0x18001f1e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f1e6  nop
0x18001f1e7  lea     rcx, [rbp+70h+var_70]
0x18001f1eb  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f1f0  mov     ebx, [rsp+170h+var_140]
0x18001f1f4  lea     rcx, [rbp+70h+var_A8]; this
0x18001f1f8  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f1fd  mov     eax, ebx
0x18001f1ff  mov     rcx, [rbp+70h+var_30]
0x18001f203  xor     rcx, rsp; StackCookie
0x18001f206  call    __security_check_cookie
0x18001f20b  add     rsp, 150h
0x18001f212  pop     r14
0x18001f214  pop     rdi
0x18001f215  pop     rsi
0x18001f216  pop     rbx
0x18001f217  pop     rbp
0x18001f218  retn
```
