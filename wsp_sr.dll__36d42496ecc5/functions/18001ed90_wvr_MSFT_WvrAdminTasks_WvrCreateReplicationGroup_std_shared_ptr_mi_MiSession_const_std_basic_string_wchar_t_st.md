# wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 const *,ushort const *,uint const *,uint const *,bool const *,bool const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,wvr::MSFT_SrJob *)

- ea: `0x18001ed90`
- end: `0x18001f052`
- name: `?WvrCreateReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@1PEB_KPEBGPEBI5PEB_N61PEAVMSFT_SrJob@2@@Z`
- size: `706`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, _QWORD *, __int64, _QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x18000ed90`

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
- `0x18001ed90`
- `0x180024d20`
- `0x180025820`
- `0x180026064`
- `0x1800268e4`
- `0x180026cf4`
- `0x180027bbc`
- `0x1800280c0`

## string_xrefs

- `0x18001efba`: `MSFT_WvrAdminTasks`
- `0x18001eebb`: `LogPath`
- `0x18001efa9`: `WvrCreateReplicationGroup`

## pseudocode

```c
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 *application; // rax
  __int64 v12; // rbx
  int v13; // eax
  mi::MiAsyncOperation::MiOperationArgs **v14; // rax
  enum _MI_CancellationReason v15; // edx
  __int64 v16; // rdx
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[80]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[32]; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v23[7]; // [rsp+B8h] [rbp-48h] BYREF
  char v24[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v25; // [rsp+F8h] [rbp-8h]
  _QWORD v26[8]; // [rsp+110h] [rbp+10h] BYREF

  v19 = a1;
  v20 = 0;
  v18 = 0;
  application = (__int64 *)mi::MiSession::get_application(*a1, (__int64)v24);
  mi::MiApplication::CreateParameterSet(*application, v23);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  if ( a2 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>((int)v23, (int)v22, a2, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( a3 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"Description");
    mi::MiInstance::AddElement<std::wstring>((int)v23, (int)v22, a3, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( a4 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"VolumeNames");
    mi::MiInstance::AddElement(v23, v22, a4);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( a5 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"LogPath");
    mi::MiInstance::AddElement<std::wstring>((int)v23, (int)v22, a5, 0x2000);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( a6 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"MaxLogSizeInByte");
    mi::MiInstance::AddElement<unsigned __int64>(v23, v22, a6);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( a7 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"LogType");
    mi::MiInstance::AddElement<unsigned short>(v23, v22, a7);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  if ( a8 )
  {
    std::wstring::wstring((__int64)v22, (__int64)L"ReplicationMode");
    mi::MiInstance::AddElement<unsigned int>(v23, v22, a8);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  v12 = *v19;
  v26[0] = &std::_Func_impl_no_alloc<_lambda_ea30ea57b1af8bd6b5bca6039fabff68_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v26[1] = &v18;
  v26[2] = &v20;
  v26[7] = v26;
  std::wstring::wstring((__int64)v22, (__int64)L"WvrCreateReplicationGroup");
  v13 = std::wstring::wstring((__int64)v24, (__int64)L"MSFT_WvrAdminTasks");
  v14 = (mi::MiAsyncOperation::MiOperationArgs **)mi::MiSession::InvokeMethod(
                                                    v12,
                                                    (__int64)v21,
                                                    v13,
                                                    (int)v22,
                                                    (__int64)v23,
                                                    (__int64)v26);
  mi::MiAsyncOperation::Join(v14);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v21, v15);
  std::wstring::_Tidy_deallocate((__int64)v24);
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::_Func_class<void,>::~_Func_class<void,>((__int64)v26, v16);
  LODWORD(v12) = v18;
  mi::MiInstance::~MiInstance(v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001ed90  push    rbp
0x18001ed92  push    rbx
0x18001ed93  push    rsi
0x18001ed94  push    rdi
0x18001ed95  push    r12
0x18001ed97  push    r13
0x18001ed99  push    r14
0x18001ed9b  push    r15
0x18001ed9d  lea     rbp, [rsp-68h]
0x18001eda2  sub     rsp, 168h
0x18001eda9  mov     rax, cs:__security_cookie
0x18001edb0  xor     rax, rsp
0x18001edb3  mov     [rbp+0A0h+var_50], rax
0x18001edb7  mov     r12, r9
0x18001edba  mov     r15, r8
0x18001edbd  mov     rdi, rdx
0x18001edc0  mov     [rsp+1A0h+var_168], rcx
0x18001edc5  mov     r13, [rbp+0A0h+arg_20]
0x18001edcc  mov     rsi, [rbp+0A0h+arg_28]
0x18001edd3  mov     r14, [rbp+0A0h+arg_30]
0x18001edda  mov     rbx, [rbp+0A0h+arg_38]
0x18001ede1  mov     [rsp+1A0h+var_160], 0
0x18001edea  mov     [rsp+1A0h+var_170], 0
0x18001edf2  lea     rdx, [rbp+0A0h+var_B0]
0x18001edf6  mov     rcx, [rcx]
0x18001edf9  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001edfe  nop
0x18001edff  lea     rdx, [rbp+0A0h+var_E8]
0x18001ee03  mov     rcx, [rax]
0x18001ee06  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001ee0b  nop
0x18001ee0c  mov     rcx, [rbp+0A0h+var_A8]; this
0x18001ee10  test    rcx, rcx
0x18001ee13  jz      short loc_18001EE1A
0x18001ee15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ee1a  test    rdi, rdi
0x18001ee1d  jz      short loc_18001EE50
0x18001ee1f  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001ee26  lea     rcx, [rbp+0A0h+var_108]
0x18001ee2a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ee2f  nop
0x18001ee30  mov     r9d, 2000h
0x18001ee36  mov     r8, rdi
0x18001ee39  lea     rdx, [rbp+0A0h+var_108]
0x18001ee3d  lea     rcx, [rbp+0A0h+var_E8]
0x18001ee41  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ee46  nop
0x18001ee47  lea     rcx, [rbp+0A0h+var_108]
0x18001ee4b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee50  test    r15, r15
0x18001ee53  jz      short loc_18001EE86
0x18001ee55  lea     rdx, aDescription; "Description"
0x18001ee5c  lea     rcx, [rbp+0A0h+var_108]
0x18001ee60  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ee65  nop
0x18001ee66  mov     r9d, 2000h
0x18001ee6c  mov     r8, r15
0x18001ee6f  lea     rdx, [rbp+0A0h+var_108]
0x18001ee73  lea     rcx, [rbp+0A0h+var_E8]
0x18001ee77  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ee7c  nop
0x18001ee7d  lea     rcx, [rbp+0A0h+var_108]
0x18001ee81  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ee86  test    r12, r12
0x18001ee89  jz      short loc_18001EEB6
0x18001ee8b  lea     rdx, aVolumenames; "VolumeNames"
0x18001ee92  lea     rcx, [rbp+0A0h+var_108]
0x18001ee96  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ee9b  nop
0x18001ee9c  mov     r8, r12
0x18001ee9f  lea     rdx, [rbp+0A0h+var_108]
0x18001eea3  lea     rcx, [rbp+0A0h+var_E8]
0x18001eea7  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001eeac  nop
0x18001eead  lea     rcx, [rbp+0A0h+var_108]
0x18001eeb1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eeb6  test    r13, r13
0x18001eeb9  jz      short loc_18001EEEC
0x18001eebb  lea     rdx, aLogpath; "LogPath"
0x18001eec2  lea     rcx, [rbp+0A0h+var_108]
0x18001eec6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001eecb  nop
0x18001eecc  mov     r9d, 2000h
0x18001eed2  mov     r8, r13
0x18001eed5  lea     rdx, [rbp+0A0h+var_108]
0x18001eed9  lea     rcx, [rbp+0A0h+var_E8]
0x18001eedd  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001eee2  nop
0x18001eee3  lea     rcx, [rbp+0A0h+var_108]
0x18001eee7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eeec  test    rsi, rsi
0x18001eeef  jz      short loc_18001EF1C
0x18001eef1  lea     rdx, aMaxlogsizeinby; "MaxLogSizeInByte"
0x18001eef8  lea     rcx, [rbp+0A0h+var_108]
0x18001eefc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ef01  nop
0x18001ef02  mov     r8, rsi
0x18001ef05  lea     rdx, [rbp+0A0h+var_108]
0x18001ef09  lea     rcx, [rbp+0A0h+var_E8]
0x18001ef0d  call    ??$AddElement@_K@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_KI@Z; mi::MiInstance::AddElement<unsigned __int64>(std::wstring const &,unsigned __int64 const &,uint)
0x18001ef12  nop
0x18001ef13  lea     rcx, [rbp+0A0h+var_108]
0x18001ef17  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef1c  test    r14, r14
0x18001ef1f  jz      short loc_18001EF4C
0x18001ef21  lea     rdx, aLogtype; "LogType"
0x18001ef28  lea     rcx, [rbp+0A0h+var_108]
0x18001ef2c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ef31  nop
0x18001ef32  mov     r8, r14
0x18001ef35  lea     rdx, [rbp+0A0h+var_108]
0x18001ef39  lea     rcx, [rbp+0A0h+var_E8]
0x18001ef3d  call    ??$AddElement@G@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBGI@Z; mi::MiInstance::AddElement<ushort>(std::wstring const &,ushort const &,uint)
0x18001ef42  nop
0x18001ef43  lea     rcx, [rbp+0A0h+var_108]
0x18001ef47  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef4c  test    rbx, rbx
0x18001ef4f  jz      short loc_18001EF7C
0x18001ef51  lea     rdx, aReplicationmod; "ReplicationMode"
0x18001ef58  lea     rcx, [rbp+0A0h+var_108]
0x18001ef5c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ef61  nop
0x18001ef62  mov     r8, rbx
0x18001ef65  lea     rdx, [rbp+0A0h+var_108]
0x18001ef69  lea     rcx, [rbp+0A0h+var_E8]
0x18001ef6d  call    ??$AddElement@I@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBII@Z; mi::MiInstance::AddElement<uint>(std::wstring const &,uint const &,uint)
0x18001ef72  nop
0x18001ef73  lea     rcx, [rbp+0A0h+var_108]
0x18001ef77  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef7c  mov     rbx, [rsp+1A0h+var_168]
0x18001ef81  mov     rbx, [rbx]
0x18001ef84  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ea30ea57b1af8bd6b5bca6039fabff68_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_ea30ea57b1af8bd6b5bca6039fabff68_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001ef8b  mov     [rbp+0A0h+var_90], rax
0x18001ef8f  lea     rax, [rsp+1A0h+var_170]
0x18001ef94  mov     [rbp+0A0h+var_88], rax
0x18001ef98  lea     rax, [rsp+1A0h+var_160]
0x18001ef9d  mov     [rbp+0A0h+var_80], rax
0x18001efa1  lea     rax, [rbp+0A0h+var_90]
0x18001efa5  mov     [rbp+0A0h+var_58], rax
0x18001efa9  lea     rdx, aWvrcreaterepli_0; "WvrCreateReplicationGroup"
0x18001efb0  lea     rcx, [rbp+0A0h+var_108]
0x18001efb4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001efb9  nop
0x18001efba  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001efc1  lea     rcx, [rbp+0A0h+var_B0]
0x18001efc5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001efca  nop
0x18001efcb  lea     rcx, [rbp+0A0h+var_90]
0x18001efcf  mov     [rsp+1A0h+var_178], rcx
0x18001efd4  lea     rcx, [rbp+0A0h+var_E8]
0x18001efd8  mov     [rsp+1A0h+var_180], rcx
0x18001efdd  lea     r9, [rbp+0A0h+var_108]
0x18001efe1  mov     r8, rax
0x18001efe4  lea     rdx, [rsp+1A0h+var_158]
0x18001efe9  mov     rcx, rbx
0x18001efec  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001eff1  nop
0x18001eff2  mov     rcx, rax; this
0x18001eff5  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001effa  nop
0x18001effb  lea     rcx, [rsp+1A0h+var_158]; this
0x18001f000  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f005  nop
0x18001f006  lea     rcx, [rbp+0A0h+var_B0]
0x18001f00a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f00f  nop
0x18001f010  lea     rcx, [rbp+0A0h+var_108]
0x18001f014  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f019  nop
0x18001f01a  lea     rcx, [rbp+0A0h+var_90]
0x18001f01e  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f023  mov     ebx, [rsp+1A0h+var_170]
0x18001f027  lea     rcx, [rbp+0A0h+var_E8]; this
0x18001f02b  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f030  mov     eax, ebx
0x18001f032  mov     rcx, [rbp+0A0h+var_50]
0x18001f036  xor     rcx, rsp; StackCookie
0x18001f039  call    __security_check_cookie
0x18001f03e  add     rsp, 168h
0x18001f045  pop     r15
0x18001f047  pop     r14
0x18001f049  pop     r13
0x18001f04b  pop     r12
0x18001f04d  pop     rdi
0x18001f04e  pop     rsi
0x18001f04f  pop     rbx
0x18001f050  pop     rbp
0x18001f051  retn
```
