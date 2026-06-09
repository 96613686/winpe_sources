# wvr::MSFT_WvrAdminTasks::CreateTopology(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 const *,ushort const *,uint const *,bool const *,bool const *,uint const *,bool const *,bool const *,std::vector<wvr::MSFT_WvrReplicationPartnership,std::allocator<wvr::MSFT_WvrReplicationPartnership>> *)

- ea: `0x18001db88`
- end: `0x18001dfed`
- name: `?CreateTopology@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@111121PEB_KPEBGPEBIPEB_N6566PEAV?$vector@VMSFT_WvrReplicationPartnership@wvr@@V?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@std@@@4@@Z`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ef94`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180008868`
- `0x18001cb6c`
- `0x18001cbf0`
- `0x18001cc70`
- `0x18001db88`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001df4a`: `MSFT_WvrAdminTasks`
- `0x18001dc60`: `SourceComputerName`
- `0x18001dd6e`: `DestinationComputerName`
- `0x18001df39`: `CreateTopology`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall wvr::MSFT_WvrAdminTasks::CreateTopology(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  _QWORD *application; // rax
  __int64 v17; // rbx
  int v18; // eax
  mi::MiAsyncOperation *v19; // rax
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  __int64 *v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v32[8]; // [rsp+118h] [rbp+18h] BYREF
  std::_Ref_count_base *v33; // [rsp+120h] [rbp+20h]
  _QWORD v34[8]; // [rsp+140h] [rbp+40h] BYREF

  v27 = a1;
  v22 = a9;
  v23 = a10;
  v24 = a11;
  v25 = a12;
  v26 = a13;
  v28 = 0;
  v21 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v32);
  mi::MiApplication::CreateParameterSet(*application, v31);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  if ( a3 )
  {
    std::wstring::wstring(v30, L"SourceComputerName");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( a4 )
  {
    std::wstring::wstring(v30, L"SourceRGName");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, a4, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( a5 )
  {
    std::wstring::wstring(v30, L"SourceRGDescription");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, a5, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( a6 )
  {
    std::wstring::wstring(v30, L"SourceVolumeName");
    mi::MiInstance::AddElement(v31, v30, a6);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( a7 )
  {
    std::wstring::wstring(v30, L"SourceLogVolumeName");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, a7, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( a8 )
  {
    std::wstring::wstring(v30, L"DestinationComputerName");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, a8, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( v22 )
  {
    std::wstring::wstring(v30, L"DestinationRGName");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, v22, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( v23 )
  {
    std::wstring::wstring(v30, L"DestinationRGDescription");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, v23, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( v24 )
  {
    std::wstring::wstring(v30, L"DestinationVolumeName");
    mi::MiInstance::AddElement(v31, v30, v24);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( v25 )
  {
    std::wstring::wstring(v30, L"DestinationLogVolumeName");
    mi::MiInstance::AddElement<std::wstring>(v31, v30, v25, 0x2000);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( v26 )
  {
    std::wstring::wstring(v30, L"LogSizeInBytes");
    mi::MiInstance::AddElement<unsigned __int64>(v31, v30, v26);
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( a14 )
  {
    std::wstring::wstring(v30, L"LogType");
    mi::MiInstance::AddElement<unsigned short>(v31, v30, a14);
    std::wstring::_Tidy_deallocate(v30);
  }
  std::wstring::wstring(v30, L"ReplicationMode");
  mi::MiInstance::AddElement<unsigned int>(v31, v30, 3);
  std::wstring::_Tidy_deallocate(v30);
  v17 = *v27;
  v34[0] = &std::_Func_impl_no_alloc<_lambda_27d2306f9f9381b2e65b2d534fbdc5f4_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v34[1] = &v21;
  v34[2] = &v28;
  v34[7] = v34;
  std::wstring::wstring(v30, L"CreateTopology");
  v18 = std::wstring::wstring(v32, L"MSFT_WvrAdminTasks");
  v19 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v17,
                                  (unsigned int)v29,
                                  v18,
                                  (unsigned int)v30,
                                  (__int64)v31,
                                  (__int64)v34);
  mi::MiAsyncOperation::Join(v19);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v29);
  std::wstring::_Tidy_deallocate(v32);
  std::wstring::_Tidy_deallocate(v30);
  std::_Func_class<void,>::~_Func_class<void,>(v34);
  LODWORD(v17) = v21;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v31);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001db88  mov     [rsp-8+arg_8], rbx
0x18001db8d  push    rbp
0x18001db8e  push    rsi
0x18001db8f  push    rdi
0x18001db90  push    r12
0x18001db92  push    r13
0x18001db94  push    r14
0x18001db96  push    r15
0x18001db98  lea     rbp, [rsp-90h]
0x18001dba0  sub     rsp, 190h
0x18001dba7  mov     rax, cs:__security_cookie
0x18001dbae  xor     rax, rsp
0x18001dbb1  mov     [rbp+0C0h+var_40], rax
0x18001dbb8  mov     rdi, r9
0x18001dbbb  mov     rbx, r8
0x18001dbbe  mov     [rsp+1C0h+var_160], rcx
0x18001dbc3  mov     rsi, [rbp+0C0h+arg_20]
0x18001dbca  mov     r14, [rbp+0C0h+arg_28]
0x18001dbd1  mov     r15, [rbp+0C0h+arg_30]
0x18001dbd8  mov     r12, [rbp+0C0h+arg_38]
0x18001dbdf  mov     rax, [rbp+0C0h+arg_40]
0x18001dbe6  mov     [rsp+1C0h+var_188], rax
0x18001dbeb  mov     rax, [rbp+0C0h+arg_48]
0x18001dbf2  mov     [rsp+1C0h+var_180], rax
0x18001dbf7  mov     rax, [rbp+0C0h+arg_50]
0x18001dbfe  mov     [rsp+1C0h+var_178], rax
0x18001dc03  mov     rax, [rbp+0C0h+arg_58]
0x18001dc0a  mov     [rsp+1C0h+var_170], rax
0x18001dc0f  mov     rax, [rbp+0C0h+arg_60]
0x18001dc16  mov     [rsp+1C0h+var_168], rax
0x18001dc1b  mov     r13, [rbp+0C0h+arg_68]
0x18001dc22  mov     [rsp+1C0h+var_158], 0
0x18001dc2b  mov     [rsp+1C0h+var_190], 0
0x18001dc33  lea     rdx, [rbp+0C0h+var_A8]
0x18001dc37  mov     rcx, [rcx]
0x18001dc3a  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001dc3f  nop
0x18001dc40  lea     rdx, [rbp+0C0h+var_E0]
0x18001dc44  mov     rcx, [rax]
0x18001dc47  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001dc4c  nop
0x18001dc4d  mov     rcx, [rbp+0C0h+var_A0]; this
0x18001dc51  test    rcx, rcx
0x18001dc54  jz      short loc_18001DC5B
0x18001dc56  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001dc5b  test    rbx, rbx
0x18001dc5e  jz      short loc_18001DC91
0x18001dc60  lea     rdx, aSourcecomputer; "SourceComputerName"
0x18001dc67  lea     rcx, [rbp+0C0h+var_100]
0x18001dc6b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc70  nop
0x18001dc71  mov     r9d, 2000h
0x18001dc77  mov     r8, rbx
0x18001dc7a  lea     rdx, [rbp+0C0h+var_100]
0x18001dc7e  lea     rcx, [rbp+0C0h+var_E0]
0x18001dc82  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dc87  nop
0x18001dc88  lea     rcx, [rbp+0C0h+var_100]
0x18001dc8c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dc91  test    rdi, rdi
0x18001dc94  jz      short loc_18001DCC7
0x18001dc96  lea     rdx, aSourcergname; "SourceRGName"
0x18001dc9d  lea     rcx, [rbp+0C0h+var_100]
0x18001dca1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dca6  nop
0x18001dca7  mov     r9d, 2000h
0x18001dcad  mov     r8, rdi
0x18001dcb0  lea     rdx, [rbp+0C0h+var_100]
0x18001dcb4  lea     rcx, [rbp+0C0h+var_E0]
0x18001dcb8  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dcbd  nop
0x18001dcbe  lea     rcx, [rbp+0C0h+var_100]
0x18001dcc2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dcc7  test    rsi, rsi
0x18001dcca  jz      short loc_18001DD01
0x18001dccc  lea     rdx, aSourcergdescri; "SourceRGDescription"
0x18001dcd3  lea     rcx, [rbp+0C0h+var_100]
0x18001dcd7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dcdc  nop
0x18001dcdd  mov     edi, 2000h
0x18001dce2  mov     r9d, edi
0x18001dce5  mov     r8, rsi
0x18001dce8  lea     rdx, [rbp+0C0h+var_100]
0x18001dcec  lea     rcx, [rbp+0C0h+var_E0]
0x18001dcf0  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dcf5  nop
0x18001dcf6  lea     rcx, [rbp+0C0h+var_100]
0x18001dcfa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dcff  jmp     short loc_18001DD06
0x18001dd01  mov     edi, 2000h
0x18001dd06  test    r14, r14
0x18001dd09  jz      short loc_18001DD36
0x18001dd0b  lea     rdx, aSourcevolumena; "SourceVolumeName"
0x18001dd12  lea     rcx, [rbp+0C0h+var_100]
0x18001dd16  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd1b  nop
0x18001dd1c  mov     r8, r14
0x18001dd1f  lea     rdx, [rbp+0C0h+var_100]
0x18001dd23  lea     rcx, [rbp+0C0h+var_E0]
0x18001dd27  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001dd2c  nop
0x18001dd2d  lea     rcx, [rbp+0C0h+var_100]
0x18001dd31  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dd36  test    r15, r15
0x18001dd39  jz      short loc_18001DD69
0x18001dd3b  lea     rdx, aSourcelogvolum; "SourceLogVolumeName"
0x18001dd42  lea     rcx, [rbp+0C0h+var_100]
0x18001dd46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd4b  nop
0x18001dd4c  mov     r9d, edi
0x18001dd4f  mov     r8, r15
0x18001dd52  lea     rdx, [rbp+0C0h+var_100]
0x18001dd56  lea     rcx, [rbp+0C0h+var_E0]
0x18001dd5a  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dd5f  nop
0x18001dd60  lea     rcx, [rbp+0C0h+var_100]
0x18001dd64  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dd69  test    r12, r12
0x18001dd6c  jz      short loc_18001DD9C
0x18001dd6e  lea     rdx, aDestinationcom; "DestinationComputerName"
0x18001dd75  lea     rcx, [rbp+0C0h+var_100]
0x18001dd79  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd7e  nop
0x18001dd7f  mov     r9d, edi
0x18001dd82  mov     r8, r12
0x18001dd85  lea     rdx, [rbp+0C0h+var_100]
0x18001dd89  lea     rcx, [rbp+0C0h+var_E0]
0x18001dd8d  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dd92  nop
0x18001dd93  lea     rcx, [rbp+0C0h+var_100]
0x18001dd97  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dd9c  mov     rbx, [rsp+1C0h+var_188]
0x18001dda1  test    rbx, rbx
0x18001dda4  jz      short loc_18001DDD4
0x18001dda6  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18001ddad  lea     rcx, [rbp+0C0h+var_100]
0x18001ddb1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ddb6  nop
0x18001ddb7  mov     r9d, edi
0x18001ddba  mov     r8, rbx
0x18001ddbd  lea     rdx, [rbp+0C0h+var_100]
0x18001ddc1  lea     rcx, [rbp+0C0h+var_E0]
0x18001ddc5  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ddca  nop
0x18001ddcb  lea     rcx, [rbp+0C0h+var_100]
0x18001ddcf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ddd4  mov     rbx, [rsp+1C0h+var_180]
0x18001ddd9  test    rbx, rbx
0x18001dddc  jz      short loc_18001DE0C
0x18001ddde  lea     rdx, aDestinationrgd; "DestinationRGDescription"
0x18001dde5  lea     rcx, [rbp+0C0h+var_100]
0x18001dde9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ddee  nop
0x18001ddef  mov     r9d, edi
0x18001ddf2  mov     r8, rbx
0x18001ddf5  lea     rdx, [rbp+0C0h+var_100]
0x18001ddf9  lea     rcx, [rbp+0C0h+var_E0]
0x18001ddfd  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001de02  nop
0x18001de03  lea     rcx, [rbp+0C0h+var_100]
0x18001de07  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001de0c  mov     rbx, [rsp+1C0h+var_178]
0x18001de11  test    rbx, rbx
0x18001de14  jz      short loc_18001DE41
0x18001de16  lea     rdx, aDestinationvol; "DestinationVolumeName"
0x18001de1d  lea     rcx, [rbp+0C0h+var_100]
0x18001de21  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001de26  nop
0x18001de27  mov     r8, rbx
0x18001de2a  lea     rdx, [rbp+0C0h+var_100]
0x18001de2e  lea     rcx, [rbp+0C0h+var_E0]
0x18001de32  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001de37  nop
0x18001de38  lea     rcx, [rbp+0C0h+var_100]
0x18001de3c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001de41  mov     rbx, [rsp+1C0h+var_170]
0x18001de46  test    rbx, rbx
0x18001de49  jz      short loc_18001DE79
0x18001de4b  lea     rdx, aDestinationlog; "DestinationLogVolumeName"
0x18001de52  lea     rcx, [rbp+0C0h+var_100]
0x18001de56  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001de5b  nop
0x18001de5c  mov     r9d, edi
0x18001de5f  mov     r8, rbx
0x18001de62  lea     rdx, [rbp+0C0h+var_100]
0x18001de66  lea     rcx, [rbp+0C0h+var_E0]
0x18001de6a  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001de6f  nop
0x18001de70  lea     rcx, [rbp+0C0h+var_100]
0x18001de74  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001de79  mov     rbx, [rsp+1C0h+var_168]
0x18001de7e  test    rbx, rbx
0x18001de81  jz      short loc_18001DEAE
0x18001de83  lea     rdx, aLogsizeinbytes; "LogSizeInBytes"
0x18001de8a  lea     rcx, [rbp+0C0h+var_100]
0x18001de8e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001de93  nop
0x18001de94  mov     r8, rbx
0x18001de97  lea     rdx, [rbp+0C0h+var_100]
0x18001de9b  lea     rcx, [rbp+0C0h+var_E0]
0x18001de9f  call    ??$AddElement@_K@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_KI@Z; mi::MiInstance::AddElement<unsigned __int64>(std::wstring const &,unsigned __int64 const &,uint)
0x18001dea4  nop
0x18001dea5  lea     rcx, [rbp+0C0h+var_100]
0x18001dea9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001deae  test    r13, r13
0x18001deb1  jz      short loc_18001DEDE
0x18001deb3  lea     rdx, aLogtype; "LogType"
0x18001deba  lea     rcx, [rbp+0C0h+var_100]
0x18001debe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dec3  nop
0x18001dec4  mov     r8, r13
0x18001dec7  lea     rdx, [rbp+0C0h+var_100]
0x18001decb  lea     rcx, [rbp+0C0h+var_E0]
0x18001decf  call    ??$AddElement@G@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBGI@Z; mi::MiInstance::AddElement<ushort>(std::wstring const &,ushort const &,uint)
0x18001ded4  nop
0x18001ded5  lea     rcx, [rbp+0C0h+var_100]
0x18001ded9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dede  lea     rdx, aReplicationmod; "ReplicationMode"
0x18001dee5  lea     rcx, [rbp+0C0h+var_100]
0x18001dee9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001deee  nop
0x18001deef  mov     r8d, 3
0x18001def5  lea     rdx, [rbp+0C0h+var_100]
0x18001def9  lea     rcx, [rbp+0C0h+var_E0]
0x18001defd  call    ??$AddElement@I@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBII@Z; mi::MiInstance::AddElement<uint>(std::wstring const &,uint const &,uint)
0x18001df02  nop
0x18001df03  lea     rcx, [rbp+0C0h+var_100]
0x18001df07  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df0c  mov     rbx, [rsp+1C0h+var_160]
0x18001df11  mov     rbx, [rbx]
0x18001df14  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_27d2306f9f9381b2e65b2d534fbdc5f4_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_27d2306f9f9381b2e65b2d534fbdc5f4_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001df1b  mov     [rbp+0C0h+var_80], rax
0x18001df1f  lea     rax, [rsp+1C0h+var_190]
0x18001df24  mov     [rbp+0C0h+var_78], rax
0x18001df28  lea     rax, [rsp+1C0h+var_158]
0x18001df2d  mov     [rbp+0C0h+var_70], rax
0x18001df31  lea     rax, [rbp+0C0h+var_80]
0x18001df35  mov     [rbp+0C0h+var_48], rax
0x18001df39  lea     rdx, aCreatetopology; "CreateTopology"
0x18001df40  lea     rcx, [rbp+0C0h+var_100]
0x18001df44  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001df49  nop
0x18001df4a  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001df51  lea     rcx, [rbp+0C0h+var_A8]
0x18001df55  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001df5a  nop
0x18001df5b  lea     rcx, [rbp+0C0h+var_80]
0x18001df5f  mov     [rsp+1C0h+var_198], rcx
0x18001df64  lea     rcx, [rbp+0C0h+var_E0]
0x18001df68  mov     [rsp+1C0h+var_1A0], rcx
0x18001df6d  lea     r9, [rbp+0C0h+var_100]
0x18001df71  mov     r8, rax
0x18001df74  lea     rdx, [rsp+1C0h+var_150]
0x18001df79  mov     rcx, rbx
0x18001df7c  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001df81  nop
0x18001df82  mov     rcx, rax; this
0x18001df85  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001df8a  nop
0x18001df8b  lea     rcx, [rsp+1C0h+var_150]; this
0x18001df90  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001df95  nop
0x18001df96  lea     rcx, [rbp+0C0h+var_A8]
0x18001df9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001df9f  nop
0x18001dfa0  lea     rcx, [rbp+0C0h+var_100]
0x18001dfa4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dfa9  nop
0x18001dfaa  lea     rcx, [rbp+0C0h+var_80]
0x18001dfae  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001dfb3  mov     ebx, [rsp+1C0h+var_190]
0x18001dfb7  lea     rcx, [rbp+0C0h+var_E0]; this
0x18001dfbb  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001dfc0  mov     eax, ebx
0x18001dfc2  mov     rcx, [rbp+0C0h+var_40]
0x18001dfc9  xor     rcx, rsp; StackCookie
0x18001dfcc  call    __security_check_cookie
0x18001dfd1  mov     rbx, [rsp+1C0h+arg_8]
0x18001dfd9  add     rsp, 190h
0x18001dfe0  pop     r15
0x18001dfe2  pop     r14
0x18001dfe4  pop     r13
0x18001dfe6  pop     r12
0x18001dfe8  pop     rdi
0x18001dfe9  pop     rsi
0x18001dfea  pop     rbp
0x18001dfeb  retn
```
