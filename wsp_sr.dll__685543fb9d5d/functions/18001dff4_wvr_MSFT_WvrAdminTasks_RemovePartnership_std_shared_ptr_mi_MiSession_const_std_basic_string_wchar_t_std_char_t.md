# wvr::MSFT_WvrAdminTasks::RemovePartnership(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,bool const *)

- ea: `0x18001dff4`
- end: `0x18001e1f7`
- name: `?RemovePartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEB_N@Z`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a664`
- `0x18000f264`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001dff4`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001e162`: `MSFT_WvrAdminTasks`
- `0x18001e05f`: `SourceComputerName`
- `0x18001e0cb`: `DestinationComputerName`
- `0x18001e151`: `RemovePartnership`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall wvr::MSFT_WvrAdminTasks::RemovePartnership(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD *application; // rax
  __int64 v10; // rbx
  int v11; // eax
  mi::MiAsyncOperation *v12; // rax
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v17[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v18; // [rsp+B0h] [rbp-50h]
  _BYTE v19[56]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v20[8]; // [rsp+100h] [rbp+0h] BYREF

  v14 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v17);
  mi::MiApplication::CreateParameterSet(*application, v19);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( a2 )
  {
    std::wstring::wstring(v16, L"SourceComputerName");
    mi::MiInstance::AddElement<std::wstring>(v19, v16, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v16);
  }
  if ( a3 )
  {
    std::wstring::wstring(v16, L"SourceRGName");
    mi::MiInstance::AddElement<std::wstring>(v19, v16, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v16);
  }
  if ( a4 )
  {
    std::wstring::wstring(v16, L"DestinationComputerName");
    mi::MiInstance::AddElement<std::wstring>(v19, v16, a4, 0x2000);
    std::wstring::_Tidy_deallocate(v16);
  }
  if ( a5 )
  {
    std::wstring::wstring(v16, L"DestinationRGName");
    mi::MiInstance::AddElement<std::wstring>(v19, v16, a5, 0x2000);
    std::wstring::_Tidy_deallocate(v16);
  }
  v10 = *a1;
  v20[0] = &std::_Func_impl_no_alloc<_lambda_6a7950d46c2b48219a8687d2e23b1caa_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v20[1] = &v14;
  v20[7] = v20;
  std::wstring::wstring(v16, L"RemovePartnership");
  v11 = std::wstring::wstring(v17, L"MSFT_WvrAdminTasks");
  v12 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v10,
                                  (unsigned int)v15,
                                  v11,
                                  (unsigned int)v16,
                                  (__int64)v19,
                                  (__int64)v20);
  mi::MiAsyncOperation::Join(v12);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v15);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v16);
  std::_Func_class<void,>::~_Func_class<void,>(v20);
  LODWORD(v10) = v14;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v19);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001dff4  push    rbp
0x18001dff6  push    rbx
0x18001dff7  push    rsi
0x18001dff8  push    rdi
0x18001dff9  push    r14
0x18001dffb  push    r15
0x18001dffd  lea     rbp, [rsp-58h]
0x18001e002  sub     rsp, 158h
0x18001e009  mov     rax, cs:__security_cookie
0x18001e010  xor     rax, rsp
0x18001e013  mov     [rbp+80h+var_40], rax
0x18001e017  mov     r14, r9
0x18001e01a  mov     rsi, r8
0x18001e01d  mov     rbx, rdx
0x18001e020  mov     r15, rcx
0x18001e023  mov     rdi, [rbp+80h+arg_20]
0x18001e02a  mov     [rsp+180h+var_150], 0
0x18001e032  lea     rdx, [rbp+80h+var_D8]
0x18001e036  mov     rcx, [rcx]
0x18001e039  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001e03e  nop
0x18001e03f  lea     rdx, [rbp+80h+var_B8]
0x18001e043  mov     rcx, [rax]
0x18001e046  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001e04b  nop
0x18001e04c  mov     rcx, [rbp+80h+var_D0]; this
0x18001e050  test    rcx, rcx
0x18001e053  jz      short loc_18001E05A
0x18001e055  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e05a  test    rbx, rbx
0x18001e05d  jz      short loc_18001E090
0x18001e05f  lea     rdx, aSourcecomputer; "SourceComputerName"
0x18001e066  lea     rcx, [rbp+80h+var_F8]
0x18001e06a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e06f  nop
0x18001e070  mov     r9d, 2000h
0x18001e076  mov     r8, rbx
0x18001e079  lea     rdx, [rbp+80h+var_F8]
0x18001e07d  lea     rcx, [rbp+80h+var_B8]
0x18001e081  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e086  nop
0x18001e087  lea     rcx, [rbp+80h+var_F8]
0x18001e08b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e090  test    rsi, rsi
0x18001e093  jz      short loc_18001E0C6
0x18001e095  lea     rdx, aSourcergname; "SourceRGName"
0x18001e09c  lea     rcx, [rbp+80h+var_F8]
0x18001e0a0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e0a5  nop
0x18001e0a6  mov     r9d, 2000h
0x18001e0ac  mov     r8, rsi
0x18001e0af  lea     rdx, [rbp+80h+var_F8]
0x18001e0b3  lea     rcx, [rbp+80h+var_B8]
0x18001e0b7  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e0bc  nop
0x18001e0bd  lea     rcx, [rbp+80h+var_F8]
0x18001e0c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e0c6  test    r14, r14
0x18001e0c9  jz      short loc_18001E0FC
0x18001e0cb  lea     rdx, aDestinationcom; "DestinationComputerName"
0x18001e0d2  lea     rcx, [rbp+80h+var_F8]
0x18001e0d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e0db  nop
0x18001e0dc  mov     r9d, 2000h
0x18001e0e2  mov     r8, r14
0x18001e0e5  lea     rdx, [rbp+80h+var_F8]
0x18001e0e9  lea     rcx, [rbp+80h+var_B8]
0x18001e0ed  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e0f2  nop
0x18001e0f3  lea     rcx, [rbp+80h+var_F8]
0x18001e0f7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e0fc  test    rdi, rdi
0x18001e0ff  jz      short loc_18001E132
0x18001e101  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18001e108  lea     rcx, [rbp+80h+var_F8]
0x18001e10c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e111  nop
0x18001e112  mov     r9d, 2000h
0x18001e118  mov     r8, rdi
0x18001e11b  lea     rdx, [rbp+80h+var_F8]
0x18001e11f  lea     rcx, [rbp+80h+var_B8]
0x18001e123  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e128  nop
0x18001e129  lea     rcx, [rbp+80h+var_F8]
0x18001e12d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e132  mov     rbx, [r15]
0x18001e135  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6a7950d46c2b48219a8687d2e23b1caa_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6a7950d46c2b48219a8687d2e23b1caa_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e13c  mov     [rbp+80h+var_80], rax
0x18001e140  lea     rax, [rsp+180h+var_150]
0x18001e145  mov     [rbp+80h+var_78], rax
0x18001e149  lea     rax, [rbp+80h+var_80]
0x18001e14d  mov     [rbp+80h+var_48], rax
0x18001e151  lea     rdx, aRemovepartners; "RemovePartnership"
0x18001e158  lea     rcx, [rbp+80h+var_F8]
0x18001e15c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e161  nop
0x18001e162  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e169  lea     rcx, [rbp+80h+var_D8]
0x18001e16d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e172  nop
0x18001e173  lea     rcx, [rbp+80h+var_80]
0x18001e177  mov     [rsp+180h+var_158], rcx
0x18001e17c  lea     rcx, [rbp+80h+var_B8]
0x18001e180  mov     [rsp+180h+var_160], rcx
0x18001e185  lea     r9, [rbp+80h+var_F8]
0x18001e189  mov     r8, rax
0x18001e18c  lea     rdx, [rsp+180h+var_148]
0x18001e191  mov     rcx, rbx
0x18001e194  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e199  nop
0x18001e19a  mov     rcx, rax; this
0x18001e19d  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e1a2  nop
0x18001e1a3  lea     rcx, [rsp+180h+var_148]; this
0x18001e1a8  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e1ad  nop
0x18001e1ae  lea     rcx, [rbp+80h+var_D8]
0x18001e1b2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e1b7  nop
0x18001e1b8  lea     rcx, [rbp+80h+var_F8]
0x18001e1bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e1c1  nop
0x18001e1c2  lea     rcx, [rbp+80h+var_80]
0x18001e1c6  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e1cb  mov     ebx, [rsp+180h+var_150]
0x18001e1cf  lea     rcx, [rbp+80h+var_B8]; this
0x18001e1d3  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e1d8  mov     eax, ebx
0x18001e1da  mov     rcx, [rbp+80h+var_40]
0x18001e1de  xor     rcx, rsp; StackCookie
0x18001e1e1  call    __security_check_cookie
0x18001e1e6  add     rsp, 158h
0x18001e1ed  pop     r15
0x18001e1ef  pop     r14
0x18001e1f1  pop     rdi
0x18001e1f2  pop     rsi
0x18001e1f3  pop     rbx
0x18001e1f4  pop     rbp
0x18001e1f5  retn
```
