# SrSmapiInvokeDeleteReplicationPartnership(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CWMIContext &)

- ea: `0x18000a508`
- end: `0x18000a69f`
- name: `?SrSmapiInvokeDeleteReplicationPartnership@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAVCWMIContext@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c2b4`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000a508`
- `0x18001decc`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiInvokeDeleteReplicationPartnership(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        struct CWMIContext *a4)
{
  struct CWMIContext *v4; // r14
  unsigned int v8; // ebx
  __int64 v9; // rdi
  unsigned int v10; // edi
  unsigned int v12; // [rsp+30h] [rbp-C8h]
  unsigned int v13; // [rsp+34h] [rbp-C4h]
  __int64 v15; // [rsp+50h] [rbp-A8h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-A0h]
  __int64 v17; // [rsp+60h] [rbp-98h] BYREF
  std::_Ref_count_base *v18; // [rsp+68h] [rbp-90h]
  std::system_error *v19; // [rsp+70h] [rbp-88h] BYREF
  MI_Char v20[16]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v21[32]; // [rsp+98h] [rbp-60h] BYREF

  v4 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v8 = 0;
    std::wstring::wstring((__int64)v20, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v17, v20);
    std::wstring::_Tidy_deallocate((__int64)v20);
    v9 = v17;
    std::wstring::wstring((__int64)v21, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v9, &v15, (__int64)v21);
    std::wstring::_Tidy_deallocate((__int64)v21);
    v10 = wvr::MSFT_WvrAdminTasks::RemovePartnership(&v15, 0, a1, a3, a2);
    v12 = v10;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v19) )
    {
      v13 = CatchErrorFromMiClient(v19, a4);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000A61A);
      v8 = v13;
      if ( v13 )
        goto LABEL_13;
      v10 = v12;
      v4 = a4;
    }
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, v10);
    v8 = MapWinErrorToMIResult(v10);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000a508  push    rbx
0x18000a50a  push    rsi
0x18000a50b  push    rdi
0x18000a50c  push    r12
0x18000a50e  push    r13
0x18000a510  push    r14
0x18000a512  push    r15
0x18000a514  sub     rsp, 0C0h
0x18000a51b  mov     rax, cs:__security_cookie
0x18000a522  xor     rax, rsp
0x18000a525  mov     [rsp+0F8h+var_40], rax
0x18000a52d  mov     r14, r9
0x18000a530  mov     r13, r8
0x18000a533  mov     r12, rdx
0x18000a536  mov     r15, rcx
0x18000a539  mov     [rsp+0F8h+var_B8], r9
0x18000a53e  lea     rsi, WPP_GLOBAL_Control
0x18000a545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a54c  cmp     rcx, rsi
0x18000a54f  jz      short loc_18000A56C
0x18000a551  test    byte ptr [rcx+1Ch], 4
0x18000a555  jz      short loc_18000A56C
0x18000a557  mov     edx, 1Ch
0x18000a55c  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a563  mov     rcx, [rcx+10h]
0x18000a567  call    WPP_SF_
0x18000a56c  xor     ebx, ebx
0x18000a56e  mov     [rsp+0F8h+var_C8], ebx
0x18000a572  lea     rdx, byte_1800AA410
0x18000a579  lea     rcx, [rsp+0F8h+var_80]
0x18000a57e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a583  nop
0x18000a584  lea     rdx, [rsp+0F8h+var_80]
0x18000a589  lea     rcx, [rsp+0F8h+var_98]
0x18000a58e  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000a593  nop
0x18000a594  lea     rcx, [rsp+0F8h+var_80]
0x18000a599  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a59e  mov     rdi, [rsp+0F8h+var_98]
0x18000a5a3  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000a5aa  lea     rcx, [rsp+0F8h+var_60]
0x18000a5b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a5b7  nop
0x18000a5b8  lea     r8, [rsp+0F8h+var_60]
0x18000a5c0  lea     rdx, [rsp+0F8h+var_A8]
0x18000a5c5  mov     rcx, rdi
0x18000a5c8  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000a5cd  nop
0x18000a5ce  lea     rcx, [rsp+0F8h+var_60]
0x18000a5d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a5db  mov     [rsp+0F8h+var_D8], r12
0x18000a5e0  mov     r9, r13
0x18000a5e3  mov     r8, r15
0x18000a5e6  xor     edx, edx
0x18000a5e8  lea     rcx, [rsp+0F8h+var_A8]
0x18000a5ed  call    ?RemovePartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEB_N@Z; wvr::MSFT_WvrAdminTasks::RemovePartnership(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,bool const *)
0x18000a5f2  mov     edi, eax
0x18000a5f4  mov     [rsp+0F8h+var_C8], eax
0x18000a5f8  mov     rcx, [rsp+0F8h+var_A0]; this
0x18000a5fd  test    rcx, rcx
0x18000a600  jz      short loc_18000A608
0x18000a602  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a607  nop
0x18000a608  mov     rcx, [rsp+0F8h+var_90]; this
0x18000a60d  test    rcx, rcx
0x18000a610  jz      short loc_18000A618
0x18000a612  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a617  nop
0x18000a618  jmp     short loc_18000A632
0x18000a61a  mov     ebx, [rsp+0F8h+var_C4]
0x18000a61e  lea     rsi, WPP_GLOBAL_Control
0x18000a625  test    ebx, ebx
0x18000a627  jnz     short loc_18000A650
0x18000a629  mov     edi, [rsp+0F8h+var_C8]
0x18000a62d  mov     r14, [rsp+0F8h+var_B8]
0x18000a632  test    edi, edi
0x18000a634  jz      short loc_18000A650
0x18000a636  mov     rax, [r14]
0x18000a639  mov     edx, edi
0x18000a63b  mov     rcx, r14
0x18000a63e  mov     rax, [rax+20h]
0x18000a642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a647  mov     ecx, edi; unsigned int
0x18000a649  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000a64e  mov     ebx, eax
0x18000a650  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a657  cmp     rcx, rsi
0x18000a65a  jz      short loc_18000A67A
0x18000a65c  test    byte ptr [rcx+1Ch], 1
0x18000a660  jz      short loc_18000A67A
0x18000a662  mov     edx, 1Dh
0x18000a667  mov     r9d, ebx
0x18000a66a  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a671  mov     rcx, [rcx+10h]
0x18000a675  call    WPP_SF_d
0x18000a67a  mov     eax, ebx
0x18000a67c  mov     rcx, [rsp+0F8h+var_40]
0x18000a684  xor     rcx, rsp; StackCookie
0x18000a687  call    __security_check_cookie
0x18000a68c  add     rsp, 0C0h
0x18000a693  pop     r15
0x18000a695  pop     r14
0x18000a697  pop     r13
0x18000a699  pop     r12
0x18000a69b  pop     rdi
0x18000a69c  pop     rsi
0x18000a69d  pop     rbx
0x18000a69e  retn
```
