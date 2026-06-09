# SrSmapiInvokeCreateReplicationGroup(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)

- ea: `0x18000ed90`
- end: `0x18000efb9`
- name: `?SrSmapiInvokeCreateReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBV23@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1PEA_KPEAIPEAGAEAVCWMIContext@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(const MI_Char *, int, __int64, __int64, __int64, __int64, __int64, __int64, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e5d4`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000ed90`
- `0x18001ed90`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapiInvokeCreateReplicationGroup(
        const MI_Char *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        struct CWMIContext *a9)
{
  const MI_Char *v10; // r14
  struct CWMIContext *v11; // r12
  unsigned int v12; // edi
  __int64 v13; // rsi
  unsigned int ReplicationGroup; // esi
  unsigned int v16; // [rsp+70h] [rbp-D8h] BYREF
  unsigned int v17; // [rsp+74h] [rbp-D4h]
  struct CWMIContext *v18; // [rsp+80h] [rbp-C8h]
  __int64 v19; // [rsp+90h] [rbp-B8h]
  __int64 v20; // [rsp+98h] [rbp-B0h]
  _QWORD *v21; // [rsp+A0h] [rbp-A8h]
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
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v12 = 0;
    v17 = 0;
    LOWORD(v16) = 0;
    mi::MiApplication::Create(&v26, v10);
    v13 = v26;
    std::wstring::wstring((__int64)v30, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v13, &v24, (__int64)v30);
    std::wstring::_Tidy_deallocate((__int64)v30);
    ReplicationGroup = wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(
                         (__int64 *)(unsigned int)&v24,
                         (_QWORD *)a2,
                         (_QWORD *)(_DWORD)v23,
                         (unsigned int)v22,
                         v21,
                         v20,
                         (__int64)&v16,
                         v19);
    v17 = ReplicationGroup;
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v28) )
    {
      v16 = CatchErrorFromMiClient(v28, v18);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000EF1F);
      v12 = v16;
      v10 = v29;
      if ( v16 )
        goto LABEL_13;
      ReplicationGroup = v17;
      v11 = v18;
    }
  }
  if ( ReplicationGroup )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v11 + 32LL))(v11, ReplicationGroup);
    v12 = MapWinErrorToMIResult(ReplicationGroup);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids, v12);
  std::wstring::_Tidy_deallocate((__int64)v10);
  return v12;
}

```

## disassembly

```asm
0x18000ed90  mov     r11, rsp
0x18000ed93  push    rbx
0x18000ed94  push    rsi
0x18000ed95  push    rdi
0x18000ed96  push    r12
0x18000ed98  push    r13
0x18000ed9a  push    r14
0x18000ed9c  push    r15
0x18000ed9e  sub     rsp, 110h
0x18000eda5  mov     rax, cs:__security_cookie
0x18000edac  xor     rax, rsp
0x18000edaf  mov     [rsp+148h+var_40], rax
0x18000edb7  mov     [rsp+148h+var_A0], r9
0x18000edbf  mov     [rsp+148h+var_98], r8
0x18000edc7  mov     r13, rdx
0x18000edca  mov     r14, rcx
0x18000edcd  mov     [r11-68h], rcx
0x18000edd1  mov     rax, [rsp+148h+arg_20]
0x18000edd9  mov     [rsp+148h+var_A8], rax
0x18000ede1  mov     rax, [rsp+148h+arg_28]
0x18000ede9  mov     [rsp+148h+var_B0], rax
0x18000edf1  mov     rax, [rsp+148h+arg_30]
0x18000edf9  mov     [rsp+148h+var_B8], rax
0x18000ee01  mov     r12, [rsp+148h+arg_40]
0x18000ee09  mov     [rsp+148h+var_C8], r12
0x18000ee11  lea     r15, WPP_GLOBAL_Control
0x18000ee18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee1f  cmp     rcx, r15
0x18000ee22  jz      short loc_18000EE3F
0x18000ee24  test    byte ptr [rcx+1Ch], 4
0x18000ee28  jz      short loc_18000EE3F
0x18000ee2a  mov     edx, 0Ch
0x18000ee2f  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ee36  mov     rcx, [rcx+10h]
0x18000ee3a  call    WPP_SF_
0x18000ee3f  xor     ebx, ebx
0x18000ee41  mov     edi, ebx
0x18000ee43  mov     [rsp+148h+var_D4], ebx
0x18000ee47  mov     word ptr [rsp+148h+var_D8], bx
0x18000ee4c  mov     rdx, r14
0x18000ee4f  lea     rcx, [rsp+148h+var_80]
0x18000ee57  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000ee5c  nop
0x18000ee5d  mov     rsi, [rsp+148h+var_80]
0x18000ee65  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000ee6c  lea     rcx, [rsp+148h+var_60]
0x18000ee74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000ee79  nop
0x18000ee7a  lea     r8, [rsp+148h+var_60]
0x18000ee82  lea     rdx, [rsp+148h+var_90]
0x18000ee8a  mov     rcx, rsi
0x18000ee8d  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000ee92  nop
0x18000ee93  lea     rcx, [rsp+148h+var_60]
0x18000ee9b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000eea0  mov     rax, [rsp+148h+var_B8]
0x18000eea8  mov     [rsp+148h+var_110], rax
0x18000eead  lea     rax, [rsp+148h+var_D8]
0x18000eeb2  mov     [rsp+148h+var_118], rax
0x18000eeb7  mov     rax, [rsp+148h+var_B0]
0x18000eebf  mov     [rsp+148h+var_120], rax
0x18000eec4  mov     rax, [rsp+148h+var_A8]
0x18000eecc  mov     [rsp+148h+var_128], rax
0x18000eed1  mov     r9, [rsp+148h+var_A0]
0x18000eed9  mov     r8, [rsp+148h+var_98]
0x18000eee1  mov     rdx, r13
0x18000eee4  lea     rcx, [rsp+148h+var_90]
0x18000eeec  call    ?WvrCreateReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@1PEB_KPEBGPEBI5PEB_N61PEAVMSFT_SrJob@2@@Z; wvr::MSFT_WvrAdminTasks::WvrCreateReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,unsigned __int64 const *,ushort const *,uint const *,uint const *,bool const *,bool const *,std::wstring const *,wvr::MSFT_SrJob *)
0x18000eef1  mov     esi, eax
0x18000eef3  mov     [rsp+148h+var_D4], eax
0x18000eef7  mov     rcx, [rsp+148h+var_88]; this
0x18000eeff  test    rcx, rcx
0x18000ef02  jz      short loc_18000EF0A
0x18000ef04  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ef09  nop
0x18000ef0a  mov     rcx, [rsp+148h+var_78]; this
0x18000ef12  test    rcx, rcx
0x18000ef15  jz      short loc_18000EF1D
0x18000ef17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ef1c  nop
0x18000ef1d  jmp     short loc_18000EF42
0x18000ef1f  mov     edi, [rsp+148h+var_D8]
0x18000ef23  lea     r15, WPP_GLOBAL_Control
0x18000ef2a  mov     r14, [rsp+148h+var_68]
0x18000ef32  test    edi, edi
0x18000ef34  jnz     short loc_18000EF61
0x18000ef36  mov     esi, [rsp+148h+var_D4]
0x18000ef3a  mov     r12, [rsp+148h+var_C8]
0x18000ef42  test    esi, esi
0x18000ef44  jz      short loc_18000EF61
0x18000ef46  mov     rax, [r12]
0x18000ef4a  mov     edx, esi
0x18000ef4c  mov     rcx, r12
0x18000ef4f  mov     rax, [rax+20h]
0x18000ef53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef58  mov     ecx, esi; unsigned int
0x18000ef5a  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000ef5f  mov     edi, eax
0x18000ef61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef68  cmp     rcx, r15
0x18000ef6b  jz      short loc_18000EF8C
0x18000ef6d  test    byte ptr [rcx+1Ch], 1
0x18000ef71  jz      short loc_18000EF8C
0x18000ef73  mov     edx, 0Dh
0x18000ef78  mov     r9d, edi
0x18000ef7b  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000ef82  mov     rcx, [rcx+10h]
0x18000ef86  call    WPP_SF_d
0x18000ef8b  nop
0x18000ef8c  mov     rcx, r14
0x18000ef8f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ef94  mov     eax, edi
0x18000ef96  mov     rcx, [rsp+148h+var_40]
0x18000ef9e  xor     rcx, rsp; StackCookie
0x18000efa1  call    __security_check_cookie
0x18000efa6  add     rsp, 110h
0x18000efad  pop     r15
0x18000efaf  pop     r14
0x18000efb1  pop     r13
0x18000efb3  pop     r12
0x18000efb5  pop     rdi
0x18000efb6  pop     rsi
0x18000efb7  pop     rbx
0x18000efb8  retn
```
