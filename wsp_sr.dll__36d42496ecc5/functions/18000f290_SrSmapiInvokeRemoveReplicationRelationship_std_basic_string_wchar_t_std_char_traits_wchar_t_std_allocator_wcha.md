# SrSmapiInvokeRemoveReplicationRelationship(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,CWMIContext &)

- ea: `0x18000f290`
- end: `0x18000f437`
- name: `?SrSmapiInvokeRemoveReplicationRelationship@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAVCWMIContext@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, _QWORD *, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ebd4`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000f290`
- `0x18001decc`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiInvokeRemoveReplicationRelationship(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        struct CWMIContext *a5)
{
  struct CWMIContext *v8; // r14
  unsigned int v9; // ebx
  __int64 v10; // rdi
  unsigned int v11; // edi
  unsigned int v13; // [rsp+30h] [rbp-C8h]
  unsigned int v15; // [rsp+38h] [rbp-C0h]
  __int64 v16; // [rsp+50h] [rbp-A8h] BYREF
  std::_Ref_count_base *v17; // [rsp+58h] [rbp-A0h]
  __int64 v18; // [rsp+60h] [rbp-98h] BYREF
  std::_Ref_count_base *v19; // [rsp+68h] [rbp-90h]
  std::system_error *v20; // [rsp+70h] [rbp-88h] BYREF
  MI_Char v21[16]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v22[32]; // [rsp+98h] [rbp-60h] BYREF

  v8 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v9 = 0;
    std::wstring::wstring((__int64)v21, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v18, v21);
    std::wstring::_Tidy_deallocate((__int64)v21);
    v10 = v18;
    std::wstring::wstring((__int64)v22, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v10, &v16, (__int64)v22);
    std::wstring::_Tidy_deallocate((__int64)v22);
    v11 = wvr::MSFT_WvrAdminTasks::RemovePartnership(&v16, a1, a2, a3, a4);
    v13 = v11;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v20) )
    {
      v15 = CatchErrorFromMiClient(v20, a5);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000F3B2);
      v9 = v15;
      if ( v15 )
        goto LABEL_13;
      v11 = v13;
      v8 = a5;
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, v11);
    v9 = MapWinErrorToMIResult(v11);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000f290  push    rbx
0x18000f292  push    rsi
0x18000f293  push    rdi
0x18000f294  push    r12
0x18000f296  push    r13
0x18000f298  push    r14
0x18000f29a  push    r15
0x18000f29c  sub     rsp, 0C0h
0x18000f2a3  mov     rax, cs:__security_cookie
0x18000f2aa  xor     rax, rsp
0x18000f2ad  mov     [rsp+0F8h+var_40], rax
0x18000f2b5  mov     [rsp+0F8h+var_C0], r9
0x18000f2ba  mov     r13, r8
0x18000f2bd  mov     r12, rdx
0x18000f2c0  mov     r15, rcx
0x18000f2c3  mov     r14, [rsp+0F8h+arg_20]
0x18000f2cb  mov     [rsp+0F8h+var_B8], r14
0x18000f2d0  lea     rsi, WPP_GLOBAL_Control
0x18000f2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2de  cmp     rcx, rsi
0x18000f2e1  jz      short loc_18000F2FE
0x18000f2e3  test    byte ptr [rcx+1Ch], 4
0x18000f2e7  jz      short loc_18000F2FE
0x18000f2e9  mov     edx, 10h
0x18000f2ee  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f2f5  mov     rcx, [rcx+10h]
0x18000f2f9  call    WPP_SF_
0x18000f2fe  xor     ebx, ebx
0x18000f300  mov     [rsp+0F8h+var_C8], ebx
0x18000f304  lea     rdx, byte_1800AA410
0x18000f30b  lea     rcx, [rsp+0F8h+var_80]
0x18000f310  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f315  nop
0x18000f316  lea     rdx, [rsp+0F8h+var_80]
0x18000f31b  lea     rcx, [rsp+0F8h+var_98]
0x18000f320  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000f325  nop
0x18000f326  lea     rcx, [rsp+0F8h+var_80]
0x18000f32b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f330  mov     rdi, [rsp+0F8h+var_98]
0x18000f335  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000f33c  lea     rcx, [rsp+0F8h+var_60]
0x18000f344  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f349  nop
0x18000f34a  lea     r8, [rsp+0F8h+var_60]
0x18000f352  lea     rdx, [rsp+0F8h+var_A8]
0x18000f357  mov     rcx, rdi
0x18000f35a  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000f35f  nop
0x18000f360  lea     rcx, [rsp+0F8h+var_60]
0x18000f368  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f36d  mov     rax, [rsp+0F8h+var_C0]
0x18000f372  mov     [rsp+0F8h+var_D8], rax
0x18000f377  mov     r9, r13
0x18000f37a  mov     r8, r12
0x18000f37d  mov     rdx, r15
0x18000f380  lea     rcx, [rsp+0F8h+var_A8]
0x18000f385  call    ?RemovePartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEB_N@Z; wvr::MSFT_WvrAdminTasks::RemovePartnership(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,bool const *)
0x18000f38a  mov     edi, eax
0x18000f38c  mov     [rsp+0F8h+var_C8], eax
0x18000f390  mov     rcx, [rsp+0F8h+var_A0]; this
0x18000f395  test    rcx, rcx
0x18000f398  jz      short loc_18000F3A0
0x18000f39a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f39f  nop
0x18000f3a0  mov     rcx, [rsp+0F8h+var_90]; this
0x18000f3a5  test    rcx, rcx
0x18000f3a8  jz      short loc_18000F3B0
0x18000f3aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f3af  nop
0x18000f3b0  jmp     short loc_18000F3CA
0x18000f3b2  mov     ebx, dword ptr [rsp+0F8h+var_C0]
0x18000f3b6  lea     rsi, WPP_GLOBAL_Control
0x18000f3bd  test    ebx, ebx
0x18000f3bf  jnz     short loc_18000F3E8
0x18000f3c1  mov     edi, [rsp+0F8h+var_C8]
0x18000f3c5  mov     r14, [rsp+0F8h+var_B8]
0x18000f3ca  test    edi, edi
0x18000f3cc  jz      short loc_18000F3E8
0x18000f3ce  mov     rax, [r14]
0x18000f3d1  mov     edx, edi
0x18000f3d3  mov     rcx, r14
0x18000f3d6  mov     rax, [rax+20h]
0x18000f3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3df  mov     ecx, edi; unsigned int
0x18000f3e1  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000f3e6  mov     ebx, eax
0x18000f3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3ef  cmp     rcx, rsi
0x18000f3f2  jz      short loc_18000F412
0x18000f3f4  test    byte ptr [rcx+1Ch], 1
0x18000f3f8  jz      short loc_18000F412
0x18000f3fa  mov     edx, 11h
0x18000f3ff  mov     r9d, ebx
0x18000f402  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f409  mov     rcx, [rcx+10h]
0x18000f40d  call    WPP_SF_d
0x18000f412  mov     eax, ebx
0x18000f414  mov     rcx, [rsp+0F8h+var_40]
0x18000f41c  xor     rcx, rsp; StackCookie
0x18000f41f  call    __security_check_cookie
0x18000f424  add     rsp, 0C0h
0x18000f42b  pop     r15
0x18000f42d  pop     r14
0x18000f42f  pop     r13
0x18000f431  pop     r12
0x18000f433  pop     rdi
0x18000f434  pop     rsi
0x18000f435  pop     rbx
0x18000f436  retn
```
