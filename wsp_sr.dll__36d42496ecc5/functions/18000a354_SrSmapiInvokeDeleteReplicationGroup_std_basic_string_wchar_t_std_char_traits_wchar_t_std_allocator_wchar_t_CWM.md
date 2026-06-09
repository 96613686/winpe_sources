# SrSmapiInvokeDeleteReplicationGroup(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CWMIContext &)

- ea: `0x18000a354`
- end: `0x18000a501`
- name: `?SrSmapiInvokeDeleteReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009844`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000a354`
- `0x18001f220`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiInvokeDeleteReplicationGroup(__int64 a1, struct CWMIContext *a2)
{
  struct CWMIContext *v2; // r15
  __int64 v3; // rdi
  unsigned int v4; // ebx
  __int64 v5; // rsi
  unsigned int v6; // esi
  char v8[4]; // [rsp+20h] [rbp-B8h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-B4h]
  unsigned int v10; // [rsp+28h] [rbp-B0h]
  struct CWMIContext *v11; // [rsp+30h] [rbp-A8h]
  __int64 v12; // [rsp+40h] [rbp-98h] BYREF
  std::_Ref_count_base *v13; // [rsp+48h] [rbp-90h]
  __int64 v14; // [rsp+50h] [rbp-88h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-80h]
  std::system_error *v16; // [rsp+60h] [rbp-78h] BYREF
  __int64 v17; // [rsp+68h] [rbp-70h]
  MI_Char v18[16]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v19[32]; // [rsp+90h] [rbp-48h] BYREF

  v2 = a2;
  v3 = a1;
  v17 = a1;
  v11 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v4 = 0;
    v9 = 0;
    v8[0] = 1;
    std::wstring::wstring((__int64)v18, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v14, v18);
    std::wstring::_Tidy_deallocate((__int64)v18);
    v5 = v14;
    std::wstring::wstring((__int64)v19, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v5, &v12, (__int64)v19);
    std::wstring::_Tidy_deallocate((__int64)v19);
    v6 = wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(&v12, (_QWORD *)v3, (__int64)v8);
    v9 = v6;
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v16) )
    {
      v10 = CatchErrorFromMiClient(v16, v11);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000A468);
      v4 = v10;
      v3 = v17;
      if ( v10 )
        goto LABEL_13;
      v6 = v9;
      v2 = v11;
    }
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, v6);
    v4 = MapWinErrorToMIResult(v6);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v4);
  std::wstring::_Tidy_deallocate(v3);
  return v4;
}

```

## disassembly

```asm
0x18000a354  mov     [rsp+arg_10], rbx
0x18000a359  mov     [rsp+arg_18], rsi
0x18000a35e  push    rdi
0x18000a35f  push    r14
0x18000a361  push    r15
0x18000a363  sub     rsp, 0C0h
0x18000a36a  mov     rax, cs:__security_cookie
0x18000a371  xor     rax, rsp
0x18000a374  mov     [rsp+0D8h+var_28], rax
0x18000a37c  mov     r15, rdx
0x18000a37f  mov     rdi, rcx
0x18000a382  mov     [rsp+0D8h+var_70], rcx
0x18000a387  mov     [rsp+0D8h+var_A8], rdx
0x18000a38c  lea     r14, WPP_GLOBAL_Control
0x18000a393  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a39a  cmp     rcx, r14
0x18000a39d  jz      short loc_18000A3BA
0x18000a39f  test    byte ptr [rcx+1Ch], 4
0x18000a3a3  jz      short loc_18000A3BA
0x18000a3a5  mov     edx, 16h
0x18000a3aa  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a3b1  mov     rcx, [rcx+10h]
0x18000a3b5  call    WPP_SF_
0x18000a3ba  xor     ebx, ebx
0x18000a3bc  mov     [rsp+0D8h+var_B4], ebx
0x18000a3c0  mov     [rsp+0D8h+var_B8], 1
0x18000a3c5  lea     rdx, byte_1800AA410
0x18000a3cc  lea     rcx, [rsp+0D8h+var_68]
0x18000a3d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a3d6  nop
0x18000a3d7  lea     rdx, [rsp+0D8h+var_68]
0x18000a3dc  lea     rcx, [rsp+0D8h+var_88]
0x18000a3e1  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000a3e6  nop
0x18000a3e7  lea     rcx, [rsp+0D8h+var_68]
0x18000a3ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a3f1  mov     rsi, [rsp+0D8h+var_88]
0x18000a3f6  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000a3fd  lea     rcx, [rsp+0D8h+var_48]
0x18000a405  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a40a  nop
0x18000a40b  lea     r8, [rsp+0D8h+var_48]
0x18000a413  lea     rdx, [rsp+0D8h+var_98]
0x18000a418  mov     rcx, rsi
0x18000a41b  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000a420  nop
0x18000a421  lea     rcx, [rsp+0D8h+var_48]
0x18000a429  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a42e  lea     r8, [rsp+0D8h+var_B8]
0x18000a433  mov     rdx, rdi
0x18000a436  lea     rcx, [rsp+0D8h+var_98]
0x18000a43b  call    ?WvrDeleteReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEB_N@Z; wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::wstring const *,bool const *)
0x18000a440  mov     esi, eax
0x18000a442  mov     [rsp+0D8h+var_B4], eax
0x18000a446  mov     rcx, [rsp+0D8h+var_90]; this
0x18000a44b  test    rcx, rcx
0x18000a44e  jz      short loc_18000A456
0x18000a450  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a455  nop
0x18000a456  mov     rcx, [rsp+0D8h+var_80]; this
0x18000a45b  test    rcx, rcx
0x18000a45e  jz      short loc_18000A466
0x18000a460  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a465  nop
0x18000a466  jmp     short loc_18000A485
0x18000a468  mov     ebx, [rsp+0D8h+var_B0]
0x18000a46c  lea     r14, WPP_GLOBAL_Control
0x18000a473  mov     rdi, [rsp+0D8h+var_70]
0x18000a478  test    ebx, ebx
0x18000a47a  jnz     short loc_18000A4A3
0x18000a47c  mov     esi, [rsp+0D8h+var_B4]
0x18000a480  mov     r15, [rsp+0D8h+var_A8]
0x18000a485  test    esi, esi
0x18000a487  jz      short loc_18000A4A3
0x18000a489  mov     rax, [r15]
0x18000a48c  mov     edx, esi
0x18000a48e  mov     rcx, r15
0x18000a491  mov     rax, [rax+20h]
0x18000a495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a49a  mov     ecx, esi; unsigned int
0x18000a49c  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000a4a1  mov     ebx, eax
0x18000a4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4aa  cmp     rcx, r14
0x18000a4ad  jz      short loc_18000A4CE
0x18000a4af  test    byte ptr [rcx+1Ch], 1
0x18000a4b3  jz      short loc_18000A4CE
0x18000a4b5  mov     edx, 17h
0x18000a4ba  mov     r9d, ebx
0x18000a4bd  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a4c4  mov     rcx, [rcx+10h]
0x18000a4c8  call    WPP_SF_d
0x18000a4cd  nop
0x18000a4ce  mov     rcx, rdi
0x18000a4d1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a4d6  mov     eax, ebx
0x18000a4d8  mov     rcx, [rsp+0D8h+var_28]
0x18000a4e0  xor     rcx, rsp; StackCookie
0x18000a4e3  call    __security_check_cookie
0x18000a4e8  lea     r11, [rsp+0D8h+var_18]
0x18000a4f0  mov     rbx, [r11+30h]
0x18000a4f4  mov     rsi, [r11+38h]
0x18000a4f8  mov     rsp, r11
0x18000a4fb  pop     r15
0x18000a4fd  pop     r14
0x18000a4ff  pop     rdi
0x18000a500  retn
```
