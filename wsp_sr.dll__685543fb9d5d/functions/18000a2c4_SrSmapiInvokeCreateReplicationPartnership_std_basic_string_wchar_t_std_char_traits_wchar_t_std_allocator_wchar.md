# SrSmapiInvokeCreateReplicationPartnership(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CWMIContext &)

- ea: `0x18000a2c4`
- end: `0x18000a4a7`
- name: `?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAVCWMIContext@@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000950c`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000a2c4`
- `0x18001f18c`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct CWMIContext *a4)
{
  struct CWMIContext *v4; // r13
  __int64 v5; // r15
  __int64 v6; // r14
  __int64 v7; // rsi
  enum _MI_Result v8; // ebx
  int v9; // edi
  unsigned int v10; // edi
  unsigned int v12; // [rsp+30h] [rbp-E8h]
  enum _MI_Result v13; // [rsp+34h] [rbp-E4h]
  __int64 v15; // [rsp+50h] [rbp-C8h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-C0h]
  __int64 v17; // [rsp+60h] [rbp-B8h] BYREF
  std::_Ref_count_base *v18; // [rsp+68h] [rbp-B0h]
  std::system_error *v19; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+78h] [rbp-A0h]
  __int64 v21; // [rsp+80h] [rbp-98h]
  __int64 v22; // [rsp+88h] [rbp-90h]
  MI_Char v23[16]; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v24[32]; // [rsp+B0h] [rbp-68h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  v20 = a1;
  v21 = a2;
  v22 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  try
  {
    v8 = MI_RESULT_OK;
    std::wstring::wstring(v23, byte_1800AA3F0);
    mi::MiApplication::Create(&v17, v23);
    std::wstring::_Tidy_deallocate(v23);
    v9 = v17;
    std::wstring::wstring(v24, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v9, (__int64)&v15, (int)v24);
    std::wstring::_Tidy_deallocate(v24);
    v10 = wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(&v15, v7, v6, v5);
    v12 = v10;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
  }
  catch ( std::system_error *v19 )
  {
    v13 = CatchErrorFromMiClient(v19, a4);
    v8 = v13;
    v7 = v20;
    v6 = v21;
    v5 = v22;
    if ( v13 )
      goto LABEL_13;
    v10 = v12;
    v4 = a4;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, v10);
    v8 = MapWinErrorToMIResult(v10);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v8);
  std::wstring::_Tidy_deallocate(v7);
  std::wstring::_Tidy_deallocate(v6);
  std::wstring::_Tidy_deallocate(v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a2c4  push    rbx
0x18000a2c6  push    rsi
0x18000a2c7  push    rdi
0x18000a2c8  push    r12
0x18000a2ca  push    r13
0x18000a2cc  push    r14
0x18000a2ce  push    r15
0x18000a2d0  sub     rsp, 0E0h
0x18000a2d7  mov     rax, cs:__security_cookie
0x18000a2de  xor     rax, rsp
0x18000a2e1  mov     [rsp+118h+var_48], rax
0x18000a2e9  mov     r13, r9
0x18000a2ec  mov     r15, r8
0x18000a2ef  mov     r14, rdx
0x18000a2f2  mov     rsi, rcx
0x18000a2f5  mov     [rsp+118h+var_A0], rcx
0x18000a2fa  mov     [rsp+118h+var_98], rdx
0x18000a302  mov     [rsp+118h+var_90], r8
0x18000a30a  mov     [rsp+118h+var_D8], r9
0x18000a30f  lea     r12, WPP_GLOBAL_Control
0x18000a316  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a31d  cmp     rcx, r12
0x18000a320  jz      short loc_18000A33D
0x18000a322  test    byte ptr [rcx+1Ch], 4
0x18000a326  jz      short loc_18000A33D
0x18000a328  mov     edx, 33h ; '3'
0x18000a32d  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a334  mov     rcx, [rcx+10h]
0x18000a338  call    WPP_SF_
0x18000a33d  xor     ebx, ebx
0x18000a33f  mov     [rsp+118h+var_E8], ebx
0x18000a343  lea     rdx, byte_1800AA3F0
0x18000a34a  lea     rcx, [rsp+118h+var_88]
0x18000a352  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a357  nop
0x18000a358  lea     rdx, [rsp+118h+var_88]
0x18000a360  lea     rcx, [rsp+118h+var_B8]
0x18000a365  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000a36a  nop
0x18000a36b  lea     rcx, [rsp+118h+var_88]
0x18000a373  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a378  mov     rdi, [rsp+118h+var_B8]
0x18000a37d  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000a384  lea     rcx, [rsp+118h+var_68]
0x18000a38c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a391  nop
0x18000a392  lea     r8, [rsp+118h+var_68]
0x18000a39a  lea     rdx, [rsp+118h+var_C8]
0x18000a39f  mov     rcx, rdi
0x18000a3a2  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000a3a7  nop
0x18000a3a8  lea     rcx, [rsp+118h+var_68]
0x18000a3b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a3b5  mov     r9, r15
0x18000a3b8  mov     r8, r14
0x18000a3bb  mov     rdx, rsi
0x18000a3be  lea     rcx, [rsp+118h+var_C8]
0x18000a3c3  call    ?WvrCreateReplicationPartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111@Z; wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *)
0x18000a3c8  mov     edi, eax
0x18000a3ca  mov     [rsp+118h+var_E8], eax
0x18000a3ce  mov     rcx, [rsp+118h+var_C0]; this
0x18000a3d3  test    rcx, rcx
0x18000a3d6  jz      short loc_18000A3DE
0x18000a3d8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a3dd  nop
0x18000a3de  mov     rcx, [rsp+118h+var_B0]; this
0x18000a3e3  test    rcx, rcx
0x18000a3e6  jz      short loc_18000A3EE
0x18000a3e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a3ed  nop
0x18000a3ee  jmp     short loc_18000A41D
0x18000a3f0  mov     ebx, [rsp+118h+var_E4]
0x18000a3f4  lea     r12, WPP_GLOBAL_Control
0x18000a3fb  mov     rsi, [rsp+118h+var_A0]
0x18000a400  mov     r14, [rsp+118h+var_98]
0x18000a408  mov     r15, [rsp+118h+var_90]
0x18000a410  test    ebx, ebx
0x18000a412  jnz     short loc_18000A43C
0x18000a414  mov     edi, [rsp+118h+var_E8]
0x18000a418  mov     r13, [rsp+118h+var_D8]
0x18000a41d  test    edi, edi
0x18000a41f  jz      short loc_18000A43C
0x18000a421  mov     rax, [r13+0]
0x18000a425  mov     edx, edi
0x18000a427  mov     rcx, r13
0x18000a42a  mov     rax, [rax+20h]
0x18000a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a433  mov     ecx, edi; unsigned int
0x18000a435  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000a43a  mov     ebx, eax
0x18000a43c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a443  cmp     rcx, r12
0x18000a446  jz      short loc_18000A467
0x18000a448  test    byte ptr [rcx+1Ch], 1
0x18000a44c  jz      short loc_18000A467
0x18000a44e  mov     edx, 34h ; '4'
0x18000a453  mov     r9d, ebx
0x18000a456  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a45d  mov     rcx, [rcx+10h]
0x18000a461  call    WPP_SF_d
0x18000a466  nop
0x18000a467  mov     rcx, rsi
0x18000a46a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a46f  nop
0x18000a470  mov     rcx, r14
0x18000a473  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a478  nop
0x18000a479  mov     rcx, r15
0x18000a47c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a481  mov     eax, ebx
0x18000a483  mov     rcx, [rsp+118h+var_48]
0x18000a48b  xor     rcx, rsp; StackCookie
0x18000a48e  call    __security_check_cookie
0x18000a493  add     rsp, 0E0h
0x18000a49a  pop     r15
0x18000a49c  pop     r14
0x18000a49e  pop     r13
0x18000a4a0  pop     r12
0x18000a4a2  pop     rdi
0x18000a4a3  pop     rsi
0x18000a4a4  pop     rbx
0x18000a4a5  retn
```
