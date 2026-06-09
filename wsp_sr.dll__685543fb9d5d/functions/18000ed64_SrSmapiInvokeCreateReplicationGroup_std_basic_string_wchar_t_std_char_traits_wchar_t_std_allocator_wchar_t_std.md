# SrSmapiInvokeCreateReplicationGroup(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)

- ea: `0x18000ed64`
- end: `0x18000ef8e`
- name: `?SrSmapiInvokeCreateReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBV23@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1PEA_KPEAIPEAGAEAVCWMIContext@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e5a8`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000ed64`
- `0x18001eec0`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SrSmapiInvokeCreateReplicationGroup(
        const MI_Char *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        struct CWMIContext *a9)
{
  const MI_Char *v10; // r14
  struct CWMIContext *v11; // r12
  enum _MI_Result v12; // edi
  int v13; // esi
  unsigned int v14; // esi
  enum _MI_Result v16; // [rsp+70h] [rbp-D8h] BYREF
  unsigned int v17; // [rsp+74h] [rbp-D4h]
  struct CWMIContext *v18; // [rsp+80h] [rbp-C8h]
  __int64 v19; // [rsp+90h] [rbp-B8h]
  __int64 v20; // [rsp+98h] [rbp-B0h]
  __int64 v21; // [rsp+A0h] [rbp-A8h]
  __int64 v22; // [rsp+A8h] [rbp-A0h]
  __int64 v23; // [rsp+B0h] [rbp-98h]
  __int64 v24; // [rsp+B8h] [rbp-90h] BYREF
  std::_Ref_count_base *v25; // [rsp+C0h] [rbp-88h]
  __int64 v26; // [rsp+C8h] [rbp-80h] BYREF
  std::_Ref_count_base *v27; // [rsp+D0h] [rbp-78h]
  std::system_error *v28; // [rsp+D8h] [rbp-70h] BYREF
  const MI_Char *v29; // [rsp+E0h] [rbp-68h]
  _BYTE v30[32]; // [rsp+E8h] [rbp-60h] BYREF

  v22 = a4;
  v23 = a3;
  v10 = a1;
  v29 = a1;
  v21 = a5;
  v20 = a6;
  v19 = a7;
  v11 = a9;
  v18 = a9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  try
  {
    v12 = MI_RESULT_OK;
    v17 = 0;
    LOWORD(v16) = 0;
    mi::MiApplication::Create(&v26, v10);
    v13 = v26;
    std::wstring::wstring(v30, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v13, (__int64)&v24, (int)v30);
    std::wstring::_Tidy_deallocate(v30);
    v14 = wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(&v24, a2, v23, v22, v21, v20, (__int64)&v16, v19);
    v17 = v14;
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  catch ( std::system_error *v28 )
  {
    v16 = CatchErrorFromMiClient(v28, v18);
    v12 = v16;
    v10 = v29;
    if ( v16 )
      goto LABEL_13;
    v14 = v17;
    v11 = v18;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v11 + 32LL))(v11, v14);
    v12 = MapWinErrorToMIResult(v14);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      (unsigned int)v12);
  std::wstring::_Tidy_deallocate(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000ed64  mov     r11, rsp
0x18000ed67  push    rbx
0x18000ed68  push    rsi
0x18000ed69  push    rdi
0x18000ed6a  push    r12
0x18000ed6c  push    r13
0x18000ed6e  push    r14
0x18000ed70  push    r15
0x18000ed72  sub     rsp, 110h
0x18000ed79  mov     rax, cs:__security_cookie
0x18000ed80  xor     rax, rsp
0x18000ed83  mov     [rsp+148h+var_40], rax
0x18000ed8b  mov     [rsp+148h+var_A0], r9
0x18000ed93  mov     [rsp+148h+var_98], r8
0x18000ed9b  mov     r13, rdx
0x18000ed9e  mov     r14, rcx
0x18000eda1  mov     [r11-68h], rcx
0x18000eda5  mov     rax, [rsp+148h+arg_20]
0x18000edad  mov     [rsp+148h+var_A8], rax
0x18000edb5  mov     rax, [rsp+148h+arg_28]
0x18000edbd  mov     [rsp+148h+var_B0], rax
0x18000edc5  mov     rax, [rsp+148h+arg_30]
0x18000edcd  mov     [rsp+148h+var_B8], rax
0x18000edd5  mov     r12, [rsp+148h+arg_40]
0x18000eddd  mov     [rsp+148h+var_C8], r12
0x18000ede5  lea     r15, WPP_GLOBAL_Control
0x18000edec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edf3  cmp     rcx, r15
0x18000edf6  jz      short loc_18000EE13
0x18000edf8  test    byte ptr [rcx+1Ch], 4
0x18000edfc  jz      short loc_18000EE13
0x18000edfe  mov     edx, 0Ch
0x18000ee03  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ee0a  mov     rcx, [rcx+10h]
0x18000ee0e  call    WPP_SF_
0x18000ee13  xor     ebx, ebx
0x18000ee15  mov     edi, ebx
0x18000ee17  mov     [rsp+148h+var_D4], ebx
0x18000ee1b  mov     word ptr [rsp+148h+var_D8], bx
0x18000ee20  mov     rdx, r14
0x18000ee23  lea     rcx, [rsp+148h+var_80]
0x18000ee2b  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000ee30  nop
0x18000ee31  mov     rsi, [rsp+148h+var_80]
0x18000ee39  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000ee40  lea     rcx, [rsp+148h+var_60]
0x18000ee48  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000ee4d  nop
0x18000ee4e  lea     r8, [rsp+148h+var_60]
0x18000ee56  lea     rdx, [rsp+148h+var_90]
0x18000ee5e  mov     rcx, rsi
0x18000ee61  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000ee66  nop
0x18000ee67  lea     rcx, [rsp+148h+var_60]
0x18000ee6f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ee74  mov     rax, [rsp+148h+var_B8]
0x18000ee7c  mov     [rsp+148h+var_110], rax
0x18000ee81  lea     rax, [rsp+148h+var_D8]
0x18000ee86  mov     [rsp+148h+var_118], rax
0x18000ee8b  mov     rax, [rsp+148h+var_B0]
0x18000ee93  mov     [rsp+148h+var_120], rax
0x18000ee98  mov     rax, [rsp+148h+var_A8]
0x18000eea0  mov     [rsp+148h+var_128], rax
0x18000eea5  mov     r9, [rsp+148h+var_A0]
0x18000eead  mov     r8, [rsp+148h+var_98]
0x18000eeb5  mov     rdx, r13
0x18000eeb8  lea     rcx, [rsp+148h+var_90]
0x18000eec0  call    ?WvrCreateReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@1PEB_KPEBGPEBI5PEB_N61PEAVMSFT_SrJob@2@@Z; wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,unsigned __int64 const *,ushort const *,uint const *,uint const *,bool const *,bool const *,std::wstring const *,wvr::MSFT_SrJob *)
0x18000eec5  mov     esi, eax
0x18000eec7  mov     [rsp+148h+var_D4], eax
0x18000eecb  mov     rcx, [rsp+148h+var_88]; this
0x18000eed3  test    rcx, rcx
0x18000eed6  jz      short loc_18000EEDE
0x18000eed8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000eedd  nop
0x18000eede  mov     rcx, [rsp+148h+var_78]; this
0x18000eee6  test    rcx, rcx
0x18000eee9  jz      short loc_18000EEF1
0x18000eeeb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000eef0  nop
0x18000eef1  jmp     short loc_18000EF16
0x18000eef3  mov     edi, [rsp+148h+var_D8]
0x18000eef7  lea     r15, WPP_GLOBAL_Control
0x18000eefe  mov     r14, [rsp+148h+var_68]
0x18000ef06  test    edi, edi
0x18000ef08  jnz     short loc_18000EF35
0x18000ef0a  mov     esi, [rsp+148h+var_D4]
0x18000ef0e  mov     r12, [rsp+148h+var_C8]
0x18000ef16  test    esi, esi
0x18000ef18  jz      short loc_18000EF35
0x18000ef1a  mov     rax, [r12]
0x18000ef1e  mov     edx, esi
0x18000ef20  mov     rcx, r12
0x18000ef23  mov     rax, [rax+20h]
0x18000ef27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef2c  mov     ecx, esi; unsigned int
0x18000ef2e  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000ef33  mov     edi, eax
0x18000ef35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef3c  cmp     rcx, r15
0x18000ef3f  jz      short loc_18000EF60
0x18000ef41  test    byte ptr [rcx+1Ch], 1
0x18000ef45  jz      short loc_18000EF60
0x18000ef47  mov     edx, 0Dh
0x18000ef4c  mov     r9d, edi
0x18000ef4f  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ef56  mov     rcx, [rcx+10h]
0x18000ef5a  call    WPP_SF_d
0x18000ef5f  nop
0x18000ef60  mov     rcx, r14
0x18000ef63  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ef68  mov     eax, edi
0x18000ef6a  mov     rcx, [rsp+148h+var_40]
0x18000ef72  xor     rcx, rsp; StackCookie
0x18000ef75  call    __security_check_cookie
0x18000ef7a  add     rsp, 110h
0x18000ef81  pop     r15
0x18000ef83  pop     r14
0x18000ef85  pop     r13
0x18000ef87  pop     r12
0x18000ef89  pop     rdi
0x18000ef8a  pop     rsi
0x18000ef8b  pop     rbx
0x18000ef8c  retn
```
