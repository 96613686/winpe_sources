# wvr::MSFT_WvrAdminTasks::CreateTopology(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 const *,ushort const *,uint const *,bool const *,bool const *,uint const *,bool const *,bool const *,std::vector<wvr::MSFT_WvrReplicationPartnership,std::allocator<wvr::MSFT_WvrReplicationPartnership>> *)

- ea: `0x18001da60`
- end: `0x18001dec4`
- name: `?CreateTopology@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@111121PEB_KPEBGPEBIPEB_N6566PEAV?$vector@VMSFT_WvrReplicationPartnership@wvr@@V?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@std@@@4@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000efc0`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180008704`
- `0x18001ca68`
- `0x18001caec`
- `0x18001cb6c`
- `0x18001da60`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001de22`: `MSFT_WvrAdminTasks`
- `0x18001db38`: `SourceComputerName`
- `0x18001dc46`: `DestinationComputerName`
- `0x18001de11`: `CreateTopology`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::CreateTopology(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        __int64 a14)
{
  __int64 *application; // rax
  __int64 v17; // rbx
  int v18; // eax
  mi::MiAsyncOperation *v19; // rax
  enum _MI_CancellationReason v20; // edx
  __int64 v21; // rdx
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-C8h]
  _QWORD *v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  _QWORD *v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 *v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v31[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[32]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v33[7]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v34[8]; // [rsp+118h] [rbp+18h] BYREF
  std::_Ref_count_base *v35; // [rsp+120h] [rbp+20h]
  _QWORD v36[8]; // [rsp+140h] [rbp+40h] BYREF

  v29 = a1;
  v24 = a9;
  v25 = a10;
  v26 = a11;
  v27 = a12;
  v28 = a13;
  v30 = 0;
  v23 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, v34);
  mi::MiApplication::CreateParameterSet(*application, v33);
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  if ( a3 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"SourceComputerName");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"SourceRGName");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, a4, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( a5 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"SourceRGDescription");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, a5, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( a6 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"SourceVolumeName");
    mi::MiInstance::AddElement(v33, v32, a6);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( a7 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"SourceLogVolumeName");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, a7, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( a8 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"DestinationComputerName");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, a8, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( v24 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"DestinationRGName");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, v24, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( v25 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"DestinationRGDescription");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, v25, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( v26 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"DestinationVolumeName");
    mi::MiInstance::AddElement(v33, v32, v26);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( v27 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"DestinationLogVolumeName");
    mi::MiInstance::AddElement<std::wstring>((int)v33, (int)v32, v27, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( v28 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"LogSizeInBytes");
    mi::MiInstance::AddElement<unsigned __int64>(v33, v32, v28);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  if ( a14 )
  {
    std::wstring::wstring((__int64)v32, (__int64)L"LogType");
    mi::MiInstance::AddElement<unsigned short>(v33, v32, a14);
    std::wstring::_Tidy_deallocate((__int64)v32);
  }
  std::wstring::wstring((__int64)v32, (__int64)L"ReplicationMode");
  mi::MiInstance::AddElement<unsigned int>(v33, v32, 3);
  std::wstring::_Tidy_deallocate((__int64)v32);
  v17 = *v29;
  v36[0] = &std::_Func_impl_no_alloc<_lambda_27d2306f9f9381b2e65b2d534fbdc5f4_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v36[1] = &v23;
  v36[2] = &v30;
  v36[7] = v36;
  std::wstring::wstring((__int64)v32, (__int64)L"CreateTopology");
  v18 = std::wstring::wstring((__int64)v34, (__int64)L"MSFT_WvrAdminTasks");
  v19 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v17,
                                  (unsigned int)v31,
                                  v18,
                                  (unsigned int)v32,
                                  (__int64)v33,
                                  (__int64)v36);
  mi::MiAsyncOperation::Join(v19);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v31, v20);
  std::wstring::_Tidy_deallocate((__int64)v34);
  std::wstring::_Tidy_deallocate((__int64)v32);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v36, v21);
  LODWORD(v17) = v23;
  mi::MiInstance::~MiInstance(v33);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001da60  mov     [rsp-8+arg_8], rbx
0x18001da65  push    rbp
0x18001da66  push    rsi
0x18001da67  push    rdi
0x18001da68  push    r12
0x18001da6a  push    r13
0x18001da6c  push    r14
0x18001da6e  push    r15
0x18001da70  lea     rbp, [rsp-90h]
0x18001da78  sub     rsp, 190h
0x18001da7f  mov     rax, cs:__security_cookie
0x18001da86  xor     rax, rsp
0x18001da89  mov     [rbp+0C0h+var_40], rax
0x18001da90  mov     rdi, r9
0x18001da93  mov     rbx, r8
0x18001da96  mov     [rsp+1C0h+var_160], rcx
0x18001da9b  mov     rsi, [rbp+0C0h+arg_20]
0x18001daa2  mov     r14, [rbp+0C0h+arg_28]
0x18001daa9  mov     r15, [rbp+0C0h+arg_30]
0x18001dab0  mov     r12, [rbp+0C0h+arg_38]
0x18001dab7  mov     rax, [rbp+0C0h+arg_40]
0x18001dabe  mov     [rsp+1C0h+var_188], rax
0x18001dac3  mov     rax, [rbp+0C0h+arg_48]
0x18001daca  mov     [rsp+1C0h+var_180], rax
0x18001dacf  mov     rax, [rbp+0C0h+arg_50]
0x18001dad6  mov     [rsp+1C0h+var_178], rax
0x18001dadb  mov     rax, [rbp+0C0h+arg_58]
0x18001dae2  mov     [rsp+1C0h+var_170], rax
0x18001dae7  mov     rax, [rbp+0C0h+arg_60]
0x18001daee  mov     [rsp+1C0h+var_168], rax
0x18001daf3  mov     r13, [rbp+0C0h+arg_68]
0x18001dafa  mov     [rsp+1C0h+var_158], 0
0x18001db03  mov     [rsp+1C0h+var_190], 0
0x18001db0b  lea     rdx, [rbp+0C0h+var_A8]
0x18001db0f  mov     rcx, [rcx]
0x18001db12  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001db17  nop
0x18001db18  lea     rdx, [rbp+0C0h+var_E0]
0x18001db1c  mov     rcx, [rax]
0x18001db1f  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001db24  nop
0x18001db25  mov     rcx, [rbp+0C0h+var_A0]; this
0x18001db29  test    rcx, rcx
0x18001db2c  jz      short loc_18001DB33
0x18001db2e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001db33  test    rbx, rbx
0x18001db36  jz      short loc_18001DB69
0x18001db38  lea     rdx, aSourcecomputer; "SourceComputerName"
0x18001db3f  lea     rcx, [rbp+0C0h+var_100]
0x18001db43  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001db48  nop
0x18001db49  mov     r9d, 2000h
0x18001db4f  mov     r8, rbx
0x18001db52  lea     rdx, [rbp+0C0h+var_100]
0x18001db56  lea     rcx, [rbp+0C0h+var_E0]
0x18001db5a  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001db5f  nop
0x18001db60  lea     rcx, [rbp+0C0h+var_100]
0x18001db64  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001db69  test    rdi, rdi
0x18001db6c  jz      short loc_18001DB9F
0x18001db6e  lea     rdx, aSourcergname; "SourceRGName"
0x18001db75  lea     rcx, [rbp+0C0h+var_100]
0x18001db79  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001db7e  nop
0x18001db7f  mov     r9d, 2000h
0x18001db85  mov     r8, rdi
0x18001db88  lea     rdx, [rbp+0C0h+var_100]
0x18001db8c  lea     rcx, [rbp+0C0h+var_E0]
0x18001db90  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001db95  nop
0x18001db96  lea     rcx, [rbp+0C0h+var_100]
0x18001db9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001db9f  test    rsi, rsi
0x18001dba2  jz      short loc_18001DBD9
0x18001dba4  lea     rdx, aSourcergdescri; "SourceRGDescription"
0x18001dbab  lea     rcx, [rbp+0C0h+var_100]
0x18001dbaf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dbb4  nop
0x18001dbb5  mov     edi, 2000h
0x18001dbba  mov     r9d, edi
0x18001dbbd  mov     r8, rsi
0x18001dbc0  lea     rdx, [rbp+0C0h+var_100]
0x18001dbc4  lea     rcx, [rbp+0C0h+var_E0]
0x18001dbc8  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dbcd  nop
0x18001dbce  lea     rcx, [rbp+0C0h+var_100]
0x18001dbd2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dbd7  jmp     short loc_18001DBDE
0x18001dbd9  mov     edi, 2000h
0x18001dbde  test    r14, r14
0x18001dbe1  jz      short loc_18001DC0E
0x18001dbe3  lea     rdx, aSourcevolumena; "SourceVolumeName"
0x18001dbea  lea     rcx, [rbp+0C0h+var_100]
0x18001dbee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dbf3  nop
0x18001dbf4  mov     r8, r14
0x18001dbf7  lea     rdx, [rbp+0C0h+var_100]
0x18001dbfb  lea     rcx, [rbp+0C0h+var_E0]
0x18001dbff  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001dc04  nop
0x18001dc05  lea     rcx, [rbp+0C0h+var_100]
0x18001dc09  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dc0e  test    r15, r15
0x18001dc11  jz      short loc_18001DC41
0x18001dc13  lea     rdx, aSourcelogvolum; "SourceLogVolumeName"
0x18001dc1a  lea     rcx, [rbp+0C0h+var_100]
0x18001dc1e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc23  nop
0x18001dc24  mov     r9d, edi
0x18001dc27  mov     r8, r15
0x18001dc2a  lea     rdx, [rbp+0C0h+var_100]
0x18001dc2e  lea     rcx, [rbp+0C0h+var_E0]
0x18001dc32  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dc37  nop
0x18001dc38  lea     rcx, [rbp+0C0h+var_100]
0x18001dc3c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dc41  test    r12, r12
0x18001dc44  jz      short loc_18001DC74
0x18001dc46  lea     rdx, aDestinationcom; "DestinationComputerName"
0x18001dc4d  lea     rcx, [rbp+0C0h+var_100]
0x18001dc51  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc56  nop
0x18001dc57  mov     r9d, edi
0x18001dc5a  mov     r8, r12
0x18001dc5d  lea     rdx, [rbp+0C0h+var_100]
0x18001dc61  lea     rcx, [rbp+0C0h+var_E0]
0x18001dc65  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dc6a  nop
0x18001dc6b  lea     rcx, [rbp+0C0h+var_100]
0x18001dc6f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dc74  mov     rbx, [rsp+1C0h+var_188]
0x18001dc79  test    rbx, rbx
0x18001dc7c  jz      short loc_18001DCAC
0x18001dc7e  lea     rdx, aDestinationrgn; "DestinationRGName"
0x18001dc85  lea     rcx, [rbp+0C0h+var_100]
0x18001dc89  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc8e  nop
0x18001dc8f  mov     r9d, edi
0x18001dc92  mov     r8, rbx
0x18001dc95  lea     rdx, [rbp+0C0h+var_100]
0x18001dc99  lea     rcx, [rbp+0C0h+var_E0]
0x18001dc9d  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dca2  nop
0x18001dca3  lea     rcx, [rbp+0C0h+var_100]
0x18001dca7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dcac  mov     rbx, [rsp+1C0h+var_180]
0x18001dcb1  test    rbx, rbx
0x18001dcb4  jz      short loc_18001DCE4
0x18001dcb6  lea     rdx, aDestinationrgd; "DestinationRGDescription"
0x18001dcbd  lea     rcx, [rbp+0C0h+var_100]
0x18001dcc1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dcc6  nop
0x18001dcc7  mov     r9d, edi
0x18001dcca  mov     r8, rbx
0x18001dccd  lea     rdx, [rbp+0C0h+var_100]
0x18001dcd1  lea     rcx, [rbp+0C0h+var_E0]
0x18001dcd5  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dcda  nop
0x18001dcdb  lea     rcx, [rbp+0C0h+var_100]
0x18001dcdf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dce4  mov     rbx, [rsp+1C0h+var_178]
0x18001dce9  test    rbx, rbx
0x18001dcec  jz      short loc_18001DD19
0x18001dcee  lea     rdx, aDestinationvol; "DestinationVolumeName"
0x18001dcf5  lea     rcx, [rbp+0C0h+var_100]
0x18001dcf9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dcfe  nop
0x18001dcff  mov     r8, rbx
0x18001dd02  lea     rdx, [rbp+0C0h+var_100]
0x18001dd06  lea     rcx, [rbp+0C0h+var_E0]
0x18001dd0a  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001dd0f  nop
0x18001dd10  lea     rcx, [rbp+0C0h+var_100]
0x18001dd14  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dd19  mov     rbx, [rsp+1C0h+var_170]
0x18001dd1e  test    rbx, rbx
0x18001dd21  jz      short loc_18001DD51
0x18001dd23  lea     rdx, aDestinationlog; "DestinationLogVolumeName"
0x18001dd2a  lea     rcx, [rbp+0C0h+var_100]
0x18001dd2e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd33  nop
0x18001dd34  mov     r9d, edi
0x18001dd37  mov     r8, rbx
0x18001dd3a  lea     rdx, [rbp+0C0h+var_100]
0x18001dd3e  lea     rcx, [rbp+0C0h+var_E0]
0x18001dd42  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001dd47  nop
0x18001dd48  lea     rcx, [rbp+0C0h+var_100]
0x18001dd4c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dd51  mov     rbx, [rsp+1C0h+var_168]
0x18001dd56  test    rbx, rbx
0x18001dd59  jz      short loc_18001DD86
0x18001dd5b  lea     rdx, aLogsizeinbytes; "LogSizeInBytes"
0x18001dd62  lea     rcx, [rbp+0C0h+var_100]
0x18001dd66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd6b  nop
0x18001dd6c  mov     r8, rbx
0x18001dd6f  lea     rdx, [rbp+0C0h+var_100]
0x18001dd73  lea     rcx, [rbp+0C0h+var_E0]
0x18001dd77  call    ??$AddElement@_K@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_KI@Z; mi::MiInstance::AddElement<unsigned __int64>(std::wstring const &,unsigned __int64 const &,uint)
0x18001dd7c  nop
0x18001dd7d  lea     rcx, [rbp+0C0h+var_100]
0x18001dd81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dd86  test    r13, r13
0x18001dd89  jz      short loc_18001DDB6
0x18001dd8b  lea     rdx, aLogtype; "LogType"
0x18001dd92  lea     rcx, [rbp+0C0h+var_100]
0x18001dd96  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd9b  nop
0x18001dd9c  mov     r8, r13
0x18001dd9f  lea     rdx, [rbp+0C0h+var_100]
0x18001dda3  lea     rcx, [rbp+0C0h+var_E0]
0x18001dda7  call    ??$AddElement@G@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBGI@Z; mi::MiInstance::AddElement<ushort>(std::wstring const &,ushort const &,uint)
0x18001ddac  nop
0x18001ddad  lea     rcx, [rbp+0C0h+var_100]
0x18001ddb1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ddb6  lea     rdx, aReplicationmod; "ReplicationMode"
0x18001ddbd  lea     rcx, [rbp+0C0h+var_100]
0x18001ddc1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ddc6  nop
0x18001ddc7  mov     r8d, 3
0x18001ddcd  lea     rdx, [rbp+0C0h+var_100]
0x18001ddd1  lea     rcx, [rbp+0C0h+var_E0]
0x18001ddd5  call    ??$AddElement@I@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBII@Z; mi::MiInstance::AddElement<uint>(std::wstring const &,uint const &,uint)
0x18001ddda  nop
0x18001dddb  lea     rcx, [rbp+0C0h+var_100]
0x18001dddf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001dde4  mov     rbx, [rsp+1C0h+var_160]
0x18001dde9  mov     rbx, [rbx]
0x18001ddec  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_27d2306f9f9381b2e65b2d534fbdc5f4_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_27d2306f9f9381b2e65b2d534fbdc5f4_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001ddf3  mov     [rbp+0C0h+var_80], rax
0x18001ddf7  lea     rax, [rsp+1C0h+var_190]
0x18001ddfc  mov     [rbp+0C0h+var_78], rax
0x18001de00  lea     rax, [rsp+1C0h+var_158]
0x18001de05  mov     [rbp+0C0h+var_70], rax
0x18001de09  lea     rax, [rbp+0C0h+var_80]
0x18001de0d  mov     [rbp+0C0h+var_48], rax
0x18001de11  lea     rdx, aCreatetopology; "CreateTopology"
0x18001de18  lea     rcx, [rbp+0C0h+var_100]
0x18001de1c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001de21  nop
0x18001de22  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001de29  lea     rcx, [rbp+0C0h+var_A8]
0x18001de2d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001de32  nop
0x18001de33  lea     rcx, [rbp+0C0h+var_80]
0x18001de37  mov     [rsp+1C0h+var_198], rcx
0x18001de3c  lea     rcx, [rbp+0C0h+var_E0]
0x18001de40  mov     [rsp+1C0h+var_1A0], rcx
0x18001de45  lea     r9, [rbp+0C0h+var_100]
0x18001de49  mov     r8, rax
0x18001de4c  lea     rdx, [rsp+1C0h+var_150]
0x18001de51  mov     rcx, rbx
0x18001de54  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001de59  nop
0x18001de5a  mov     rcx, rax; this
0x18001de5d  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001de62  nop
0x18001de63  lea     rcx, [rsp+1C0h+var_150]; this
0x18001de68  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001de6d  nop
0x18001de6e  lea     rcx, [rbp+0C0h+var_A8]
0x18001de72  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001de77  nop
0x18001de78  lea     rcx, [rbp+0C0h+var_100]
0x18001de7c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001de81  nop
0x18001de82  lea     rcx, [rbp+0C0h+var_80]
0x18001de86  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001de8b  mov     ebx, [rsp+1C0h+var_190]
0x18001de8f  lea     rcx, [rbp+0C0h+var_E0]; this
0x18001de93  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001de98  mov     eax, ebx
0x18001de9a  mov     rcx, [rbp+0C0h+var_40]
0x18001dea1  xor     rcx, rsp; StackCookie
0x18001dea4  call    __security_check_cookie
0x18001dea9  mov     rbx, [rsp+1C0h+arg_8]
0x18001deb1  add     rsp, 190h
0x18001deb8  pop     r15
0x18001deba  pop     r14
0x18001debc  pop     r13
0x18001debe  pop     r12
0x18001dec0  pop     rdi
0x18001dec1  pop     rsi
0x18001dec2  pop     rbp
0x18001dec3  retn
```
