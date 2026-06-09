# wvr::MSFT_WvrAdminTasks::RemovePartnership(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,bool const *)

- ea: `0x18001decc`
- end: `0x18001e0ce`
- name: `?RemovePartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEB_N@Z`
- size: `514`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a508`
- `0x18000f290`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001decc`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001e03a`: `MSFT_WvrAdminTasks`
- `0x18001df37`: `SourceComputerName`
- `0x18001dfa3`: `DestinationComputerName`
- `0x18001e029`: `RemovePartnership`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::RemovePartnership(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  __int64 *application; // rax
  __int64 v10; // rbx
  int v11; // eax
  mi::MiAsyncOperation::MiOperationArgs **v12; // rax
  enum _MI_CancellationReason v13; // edx
  __int64 v14; // rdx
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[80]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v19[8]; // [rsp+A8h] [rbp-58h] BYREF
  std::_Ref_count_base *v20; // [rsp+B0h] [rbp-50h]
  std::_Ref_count_base *v21[7]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v22[8]; // [rsp+100h] [rbp+0h] BYREF

  v16 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v19);
  mi::MiApplication::CreateParameterSet(*application, v21);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v18, (__int64)L"SourceComputerName");
    mi::MiInstance::AddElement<std::wstring>((int)v21, (int)v18, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v18);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v18, (__int64)L"SourceRGName");
    mi::MiInstance::AddElement<std::wstring>((int)v21, (int)v18, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v18);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v18, (__int64)L"DestinationComputerName");
    mi::MiInstance::AddElement<std::wstring>((int)v21, (int)v18, a4, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v18);
  }
  if ( a5 )
  {
    std::wstring::wstring((__int64)v18, (__int64)L"DestinationRGName");
    mi::MiInstance::AddElement<std::wstring>((int)v21, (int)v18, a5, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v18);
  }
  v10 = *a1;
  v22[0] = &std::_Func_impl_no_alloc<_lambda_6a7950d46c2b48219a8687d2e23b1caa_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v22[1] = &v16;
  v22[7] = v22;
  std::wstring::wstring((__int64)v18, (__int64)L"RemovePartnership");
  v11 = std::wstring::wstring((__int64)v19, (__int64)L"MSFT_WvrAdminTasks");
  v12 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v10,
                                                    (__int64)v17,
                                                    v11,
                                                    (int)v18,
                                                    (__int64)v21,
                                                    (__int64)v22);
  mi::MiAsyncOperation::Join(v12);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v17, v13);
  std::wstring::_Tidy_deallocate((__int64)v19);
  std::wstring::_Tidy_deallocate((__int64)v18);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v22, v14);
  LODWORD(v10) = v16;
  mi::MiInstance::~MiInstance(v21);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001decc  push    rbp
0x18001dece  push    rbx
0x18001decf  push    rsi
0x18001ded0  push    rdi
0x18001ded1  push    r14
0x18001ded3  push    r15
0x18001ded5  lea     rbp, [rsp-58h]
0x18001deda  sub     rsp, 158h
0x18001dee1  mov     rax, cs:__security_cookie
0x18001dee8  xor     rax, rsp
0x18001deeb  mov     [rbp+80h+var_40], rax
0x18001deef  mov     r14, r9
0x18001def2  mov     rsi, r8
0x18001def5  mov     rbx, rdx
0x18001def8  mov     r15, rcx
0x18001defb  mov     rdi, [rbp+80h+arg_20]
0x18001df02  mov     [rsp+180h+var_150], 0
0x18001df0a  lea     rdx, [rbp+80h+var_D8]
0x18001df0e  mov     rcx, [rcx]
0x18001df11  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001df16  nop
0x18001df17  lea     rdx, [rbp+80h+var_B8]
0x18001df1b  mov     rcx, [rax]
0x18001df1e  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001df23  nop
0x18001df24  mov     rcx, [rbp+80h+var_D0]; this
0x18001df28  test    rcx, rcx
0x18001df2b  jz      short loc_18001DF32
0x18001df2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001df32  test    rbx, rbx
0x18001df35  jz      short loc_18001DF68
0x18001df37  lea     rdx, aSourcecomputer; "SourceComputerName"
0x18001df3e  lea     rcx, [rbp+80h+var_F8]
0x18001df42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001df47  nop
0x18001df48  mov     r9d, 2000h
0x18001df4e  mov     r8, rbx
0x18001df51  lea     rdx, [rbp+80h+var_F8]
0x18001df55  lea     rcx, [rbp+80h+var_B8]
0x18001df59  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001df5e  nop
0x18001df5f  lea     rcx, [rbp+80h+var_F8]
0x18001df63  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df68  test    rsi, rsi
0x18001df6b  jz      short loc_18001DF9E
0x18001df6d  lea     rdx, aSourcergname; "SourceRGName"
0x18001df74  lea     rcx, [rbp+80h+var_F8]
0x18001df78  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001df7d  nop
0x18001df7e  mov     r9d, 2000h
0x18001df84  mov     r8, rsi
0x18001df87  lea     rdx, [rbp+80h+var_F8]
0x18001df8b  lea     rcx, [rbp+80h+var_B8]
0x18001df8f  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001df94  nop
0x18001df95  lea     rcx, [rbp+80h+var_F8]
0x18001df99  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df9e  test    r14, r14
0x18001dfa1  jz      short loc_18001DFD4
0x18001dfa3  lea     rdx, aDestinationcom; "DestinationComputerName"
0x18001dfaa  lea     rcx, [rbp+80h+var_F8]
0x18001dfae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dfb3  nop
0x18001dfb4  mov     r9d, 2000h
0x18001dfba  mov     r8, r14
0x18001dfbd  lea     rdx, [rbp+80h+var_F8]
0x18001dfc1  lea     rcx, [rbp+80h+var_B8]
0x18001dfc5  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dfca  nop
0x18001dfcb  lea     rcx, [rbp+80h+var_F8]
0x18001dfcf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dfd4  test    rdi, rdi
0x18001dfd7  jz      short loc_18001E00A
0x18001dfd9  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18001dfe0  lea     rcx, [rbp+80h+var_F8]
0x18001dfe4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dfe9  nop
0x18001dfea  mov     r9d, 2000h
0x18001dff0  mov     r8, rdi
0x18001dff3  lea     rdx, [rbp+80h+var_F8]
0x18001dff7  lea     rcx, [rbp+80h+var_B8]
0x18001dffb  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001e000  nop
0x18001e001  lea     rcx, [rbp+80h+var_F8]
0x18001e005  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e00a  mov     rbx, [r15]
0x18001e00d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6a7950d46c2b48219a8687d2e23b1caa_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6a7950d46c2b48219a8687d2e23b1caa_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001e014  mov     [rbp+80h+var_80], rax
0x18001e018  lea     rax, [rsp+180h+var_150]
0x18001e01d  mov     [rbp+80h+var_78], rax
0x18001e021  lea     rax, [rbp+80h+var_80]
0x18001e025  mov     [rbp+80h+var_48], rax
0x18001e029  lea     rdx, aRemovepartners; "RemovePartnership"
0x18001e030  lea     rcx, [rbp+80h+var_F8]
0x18001e034  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e039  nop
0x18001e03a  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001e041  lea     rcx, [rbp+80h+var_D8]
0x18001e045  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e04a  nop
0x18001e04b  lea     rcx, [rbp+80h+var_80]
0x18001e04f  mov     [rsp+180h+var_158], rcx
0x18001e054  lea     rcx, [rbp+80h+var_B8]
0x18001e058  mov     [rsp+180h+var_160], rcx
0x18001e05d  lea     r9, [rbp+80h+var_F8]
0x18001e061  mov     r8, rax
0x18001e064  lea     rdx, [rsp+180h+var_148]
0x18001e069  mov     rcx, rbx
0x18001e06c  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001e071  nop
0x18001e072  mov     rcx, rax; this
0x18001e075  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001e07a  nop
0x18001e07b  lea     rcx, [rsp+180h+var_148]; this
0x18001e080  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001e085  nop
0x18001e086  lea     rcx, [rbp+80h+var_D8]
0x18001e08a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e08f  nop
0x18001e090  lea     rcx, [rbp+80h+var_F8]
0x18001e094  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e099  nop
0x18001e09a  lea     rcx, [rbp+80h+var_80]
0x18001e09e  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001e0a3  mov     ebx, [rsp+180h+var_150]
0x18001e0a7  lea     rcx, [rbp+80h+var_B8]; this
0x18001e0ab  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001e0b0  mov     eax, ebx
0x18001e0b2  mov     rcx, [rbp+80h+var_40]
0x18001e0b6  xor     rcx, rsp; StackCookie
0x18001e0b9  call    __security_check_cookie
0x18001e0be  add     rsp, 158h
0x18001e0c5  pop     r15
0x18001e0c7  pop     r14
0x18001e0c9  pop     rdi
0x18001e0ca  pop     rsi
0x18001e0cb  pop     rbx
0x18001e0cc  pop     rbp
0x18001e0cd  retn
```
