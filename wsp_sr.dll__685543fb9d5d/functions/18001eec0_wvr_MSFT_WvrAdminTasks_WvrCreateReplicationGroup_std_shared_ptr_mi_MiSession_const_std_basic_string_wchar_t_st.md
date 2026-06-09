# wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 const *,ushort const *,uint const *,uint const *,bool const *,bool const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,wvr::MSFT_SrJob *)

- ea: `0x18001eec0`
- end: `0x18001f183`
- name: `?WvrCreateReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@1PEB_KPEBGPEBI5PEB_N61PEAVMSFT_SrJob@2@@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x18000ed64`

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
- `0x18001eec0`
- `0x180025014`
- `0x180025b40`
- `0x18002639c`
- `0x180026c30`
- `0x18002704c`
- `0x180027f54`
- `0x180028488`

## string_xrefs

- `0x18001f0ea`: `MSFT_WvrAdminTasks`
- `0x18001efeb`: `LogPath`
- `0x18001f0d9`: `WvrCreateReplicationGroup`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _QWORD *application; // rax
  __int64 v12; // rbx
  int v13; // eax
  mi::MiAsyncOperation *v14; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[80]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v21[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v22[8]; // [rsp+F0h] [rbp-10h] BYREF
  std::_Ref_count_base *v23; // [rsp+F8h] [rbp-8h]
  _QWORD v24[8]; // [rsp+110h] [rbp+10h] BYREF

  v17 = a1;
  v18 = 0;
  v16 = 0;
  application = (_QWORD *)mi::MiSession::get_application(*a1, v22);
  mi::MiApplication::CreateParameterSet(*application, v21);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  if ( a2 )
  {
    std::wstring::wstring(v20, L"ReplicationGroupName");
    mi::MiInstance::AddElement<std::wstring>(v21, v20, a2, 0x2000);
    std::wstring::_Tidy_deallocate(v20);
  }
  if ( a3 )
  {
    std::wstring::wstring(v20, L"Description");
    mi::MiInstance::AddElement<std::wstring>(v21, v20, a3, 0x2000);
    std::wstring::_Tidy_deallocate(v20);
  }
  if ( a4 )
  {
    std::wstring::wstring(v20, L"VolumeNames");
    mi::MiInstance::AddElement(v21, v20, a4);
    std::wstring::_Tidy_deallocate(v20);
  }
  if ( a5 )
  {
    std::wstring::wstring(v20, L"LogPath");
    mi::MiInstance::AddElement<std::wstring>(v21, v20, a5, 0x2000);
    std::wstring::_Tidy_deallocate(v20);
  }
  if ( a6 )
  {
    std::wstring::wstring(v20, L"MaxLogSizeInByte");
    mi::MiInstance::AddElement<unsigned __int64>(v21, v20, a6);
    std::wstring::_Tidy_deallocate(v20);
  }
  if ( a7 )
  {
    std::wstring::wstring(v20, L"LogType");
    mi::MiInstance::AddElement<unsigned short>(v21, v20, a7);
    std::wstring::_Tidy_deallocate(v20);
  }
  if ( a8 )
  {
    std::wstring::wstring(v20, L"ReplicationMode");
    mi::MiInstance::AddElement<unsigned int>(v21, v20, a8);
    std::wstring::_Tidy_deallocate(v20);
  }
  v12 = *v17;
  v24[0] = &std::_Func_impl_no_alloc<_lambda_ea30ea57b1af8bd6b5bca6039fabff68_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  v24[1] = &v16;
  v24[2] = &v18;
  v24[7] = v24;
  std::wstring::wstring(v20, L"WvrCreateReplicationGroup");
  v13 = std::wstring::wstring(v22, L"MSFT_WvrAdminTasks");
  v14 = (mi::MiAsyncOperation *)mi::MiSession::InvokeMethod(
                                  v12,
                                  (unsigned int)v19,
                                  v13,
                                  (unsigned int)v20,
                                  (__int64)v21,
                                  (__int64)v24);
  mi::MiAsyncOperation::Join(v14);
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v19);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v20);
  std::_Func_class<void,>::~_Func_class<void,>(v24);
  LODWORD(v12) = v16;
  mi::MiInstance::~MiInstance((mi::MiInstance *)v21);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001eec0  push    rbp
0x18001eec2  push    rbx
0x18001eec3  push    rsi
0x18001eec4  push    rdi
0x18001eec5  push    r12
0x18001eec7  push    r13
0x18001eec9  push    r14
0x18001eecb  push    r15
0x18001eecd  lea     rbp, [rsp-68h]
0x18001eed2  sub     rsp, 168h
0x18001eed9  mov     rax, cs:__security_cookie
0x18001eee0  xor     rax, rsp
0x18001eee3  mov     [rbp+0A0h+var_50], rax
0x18001eee7  mov     r12, r9
0x18001eeea  mov     r15, r8
0x18001eeed  mov     rdi, rdx
0x18001eef0  mov     [rsp+1A0h+var_168], rcx
0x18001eef5  mov     r13, [rbp+0A0h+arg_20]
0x18001eefc  mov     rsi, [rbp+0A0h+arg_28]
0x18001ef03  mov     r14, [rbp+0A0h+arg_30]
0x18001ef0a  mov     rbx, [rbp+0A0h+arg_38]
0x18001ef11  mov     [rsp+1A0h+var_160], 0
0x18001ef1a  mov     [rsp+1A0h+var_170], 0
0x18001ef22  lea     rdx, [rbp+0A0h+var_B0]
0x18001ef26  mov     rcx, [rcx]
0x18001ef29  call    ?get_application@MiSession@mi@@QEBA?BV?$shared_ptr@VMiApplication@mi@@@std@@XZ; mi::MiSession::get_application(void)
0x18001ef2e  nop
0x18001ef2f  lea     rdx, [rbp+0A0h+var_E8]
0x18001ef33  mov     rcx, [rax]
0x18001ef36  call    ?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ; mi::MiApplication::CreateParameterSet(void)
0x18001ef3b  nop
0x18001ef3c  mov     rcx, [rbp+0A0h+var_A8]; this
0x18001ef40  test    rcx, rcx
0x18001ef43  jz      short loc_18001EF4A
0x18001ef45  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001ef4a  test    rdi, rdi
0x18001ef4d  jz      short loc_18001EF80
0x18001ef4f  lea     rdx, aReplicationgro_0; "ReplicationGroupName"
0x18001ef56  lea     rcx, [rbp+0A0h+var_108]
0x18001ef5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ef5f  nop
0x18001ef60  mov     r9d, 2000h
0x18001ef66  mov     r8, rdi
0x18001ef69  lea     rdx, [rbp+0A0h+var_108]
0x18001ef6d  lea     rcx, [rbp+0A0h+var_E8]
0x18001ef71  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001ef76  nop
0x18001ef77  lea     rcx, [rbp+0A0h+var_108]
0x18001ef7b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ef80  test    r15, r15
0x18001ef83  jz      short loc_18001EFB6
0x18001ef85  lea     rdx, aDescription; "Description"
0x18001ef8c  lea     rcx, [rbp+0A0h+var_108]
0x18001ef90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ef95  nop
0x18001ef96  mov     r9d, 2000h
0x18001ef9c  mov     r8, r15
0x18001ef9f  lea     rdx, [rbp+0A0h+var_108]
0x18001efa3  lea     rcx, [rbp+0A0h+var_E8]
0x18001efa7  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001efac  nop
0x18001efad  lea     rcx, [rbp+0A0h+var_108]
0x18001efb1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001efb6  test    r12, r12
0x18001efb9  jz      short loc_18001EFE6
0x18001efbb  lea     rdx, aVolumenames; "VolumeNames"
0x18001efc2  lea     rcx, [rbp+0A0h+var_108]
0x18001efc6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001efcb  nop
0x18001efcc  mov     r8, r12
0x18001efcf  lea     rdx, [rbp+0A0h+var_108]
0x18001efd3  lea     rcx, [rbp+0A0h+var_E8]
0x18001efd7  call    ?AddElement@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@I@Z; mi::MiInstance::AddElement(std::wstring const &,std::vector<std::wstring> const &,uint)
0x18001efdc  nop
0x18001efdd  lea     rcx, [rbp+0A0h+var_108]
0x18001efe1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001efe6  test    r13, r13
0x18001efe9  jz      short loc_18001F01C
0x18001efeb  lea     rdx, aLogpath; "LogPath"
0x18001eff2  lea     rcx, [rbp+0A0h+var_108]
0x18001eff6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001effb  nop
0x18001effc  mov     r9d, 2000h
0x18001f002  mov     r8, r13
0x18001f005  lea     rdx, [rbp+0A0h+var_108]
0x18001f009  lea     rcx, [rbp+0A0h+var_E8]
0x18001f00d  call    ??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z; mi::MiInstance::AddElement<std::wstring>(std::wstring const &,std::wstring const &,uint)
0x18001f012  nop
0x18001f013  lea     rcx, [rbp+0A0h+var_108]
0x18001f017  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f01c  test    rsi, rsi
0x18001f01f  jz      short loc_18001F04C
0x18001f021  lea     rdx, aMaxlogsizeinby; "MaxLogSizeInByte"
0x18001f028  lea     rcx, [rbp+0A0h+var_108]
0x18001f02c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f031  nop
0x18001f032  mov     r8, rsi
0x18001f035  lea     rdx, [rbp+0A0h+var_108]
0x18001f039  lea     rcx, [rbp+0A0h+var_E8]
0x18001f03d  call    ??$AddElement@_K@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_KI@Z; mi::MiInstance::AddElement<unsigned __int64>(std::wstring const &,unsigned __int64 const &,uint)
0x18001f042  nop
0x18001f043  lea     rcx, [rbp+0A0h+var_108]
0x18001f047  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f04c  test    r14, r14
0x18001f04f  jz      short loc_18001F07C
0x18001f051  lea     rdx, aLogtype; "LogType"
0x18001f058  lea     rcx, [rbp+0A0h+var_108]
0x18001f05c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f061  nop
0x18001f062  mov     r8, r14
0x18001f065  lea     rdx, [rbp+0A0h+var_108]
0x18001f069  lea     rcx, [rbp+0A0h+var_E8]
0x18001f06d  call    ??$AddElement@G@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBGI@Z; mi::MiInstance::AddElement<ushort>(std::wstring const &,ushort const &,uint)
0x18001f072  nop
0x18001f073  lea     rcx, [rbp+0A0h+var_108]
0x18001f077  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f07c  test    rbx, rbx
0x18001f07f  jz      short loc_18001F0AC
0x18001f081  lea     rdx, aReplicationmod; "ReplicationMode"
0x18001f088  lea     rcx, [rbp+0A0h+var_108]
0x18001f08c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f091  nop
0x18001f092  mov     r8, rbx
0x18001f095  lea     rdx, [rbp+0A0h+var_108]
0x18001f099  lea     rcx, [rbp+0A0h+var_E8]
0x18001f09d  call    ??$AddElement@I@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBII@Z; mi::MiInstance::AddElement<uint>(std::wstring const &,uint const &,uint)
0x18001f0a2  nop
0x18001f0a3  lea     rcx, [rbp+0A0h+var_108]
0x18001f0a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f0ac  mov     rbx, [rsp+1A0h+var_168]
0x18001f0b1  mov     rbx, [rbx]
0x18001f0b4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ea30ea57b1af8bd6b5bca6039fabff68_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_ea30ea57b1af8bd6b5bca6039fabff68_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x18001f0bb  mov     [rbp+0A0h+var_90], rax
0x18001f0bf  lea     rax, [rsp+1A0h+var_170]
0x18001f0c4  mov     [rbp+0A0h+var_88], rax
0x18001f0c8  lea     rax, [rsp+1A0h+var_160]
0x18001f0cd  mov     [rbp+0A0h+var_80], rax
0x18001f0d1  lea     rax, [rbp+0A0h+var_90]
0x18001f0d5  mov     [rbp+0A0h+var_58], rax
0x18001f0d9  lea     rdx, aWvrcreaterepli_0; "WvrCreateReplicationGroup"
0x18001f0e0  lea     rcx, [rbp+0A0h+var_108]
0x18001f0e4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f0e9  nop
0x18001f0ea  lea     rdx, aMsftWvradminta; "MSFT_WvrAdminTasks"
0x18001f0f1  lea     rcx, [rbp+0A0h+var_B0]
0x18001f0f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f0fa  nop
0x18001f0fb  lea     rcx, [rbp+0A0h+var_90]
0x18001f0ff  mov     [rsp+1A0h+var_178], rcx
0x18001f104  lea     rcx, [rbp+0A0h+var_E8]
0x18001f108  mov     [rsp+1A0h+var_180], rcx
0x18001f10d  lea     r9, [rbp+0A0h+var_108]
0x18001f111  mov     r8, rax
0x18001f114  lea     rdx, [rsp+1A0h+var_158]
0x18001f119  mov     rcx, rbx
0x18001f11c  call    ?InvokeMethod@MiSession@mi@@QEBA?AVMiAsyncOperation@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEBVMiInstance@2@AEBV?$function@$$A6A_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z@5@@Z; mi::MiSession::InvokeMethod(std::wstring const &,std::wstring const &,mi::MiInstance const &,std::function<bool (mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &)> const &)
0x18001f121  nop
0x18001f122  mov     rcx, rax; this
0x18001f125  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x18001f12a  nop
0x18001f12b  lea     rcx, [rsp+1A0h+var_158]; this
0x18001f130  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18001f135  nop
0x18001f136  lea     rcx, [rbp+0A0h+var_B0]
0x18001f13a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f13f  nop
0x18001f140  lea     rcx, [rbp+0A0h+var_108]
0x18001f144  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f149  nop
0x18001f14a  lea     rcx, [rbp+0A0h+var_90]
0x18001f14e  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18001f153  mov     ebx, [rsp+1A0h+var_170]
0x18001f157  lea     rcx, [rbp+0A0h+var_E8]; this
0x18001f15b  call    ??1MiInstance@mi@@QEAA@XZ; mi::MiInstance::~MiInstance(void)
0x18001f160  mov     eax, ebx
0x18001f162  mov     rcx, [rbp+0A0h+var_50]
0x18001f166  xor     rcx, rsp; StackCookie
0x18001f169  call    __security_check_cookie
0x18001f16e  add     rsp, 168h
0x18001f175  pop     r15
0x18001f177  pop     r14
0x18001f179  pop     r13
0x18001f17b  pop     r12
0x18001f17d  pop     rdi
0x18001f17e  pop     rsi
0x18001f17f  pop     rbx
0x18001f180  pop     rbp
0x18001f181  retn
```
