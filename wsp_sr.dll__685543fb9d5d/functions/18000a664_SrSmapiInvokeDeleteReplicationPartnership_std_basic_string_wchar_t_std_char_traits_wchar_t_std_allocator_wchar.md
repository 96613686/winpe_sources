# SrSmapiInvokeDeleteReplicationPartnership(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CWMIContext &)

- ea: `0x18000a664`
- end: `0x18000a7fc`
- name: `?SrSmapiInvokeDeleteReplicationPartnership@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAVCWMIContext@@@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c348`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000a664`
- `0x18001dff4`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrSmapiInvokeDeleteReplicationPartnership(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct CWMIContext *a4)
{
  struct CWMIContext *v4; // r14
  enum _MI_Result v8; // ebx
  int v9; // edi
  unsigned int v10; // edi
  unsigned int v12; // [rsp+30h] [rbp-C8h]
  enum _MI_Result v13; // [rsp+34h] [rbp-C4h]
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
  try
  {
    v8 = MI_RESULT_OK;
    std::wstring::wstring(v20, byte_1800AA3F0);
    mi::MiApplication::Create(&v17, v20);
    std::wstring::_Tidy_deallocate(v20);
    v9 = v17;
    std::wstring::wstring(v21, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v9, (__int64)&v15, (int)v21);
    std::wstring::_Tidy_deallocate(v21);
    v10 = wvr::MSFT_WvrAdminTasks::RemovePartnership(&v15, 0, a1, a3, a2);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000a664  push    rbx
0x18000a666  push    rsi
0x18000a667  push    rdi
0x18000a668  push    r12
0x18000a66a  push    r13
0x18000a66c  push    r14
0x18000a66e  push    r15
0x18000a670  sub     rsp, 0C0h
0x18000a677  mov     rax, cs:__security_cookie
0x18000a67e  xor     rax, rsp
0x18000a681  mov     [rsp+0F8h+var_40], rax
0x18000a689  mov     r14, r9
0x18000a68c  mov     r13, r8
0x18000a68f  mov     r12, rdx
0x18000a692  mov     r15, rcx
0x18000a695  mov     [rsp+0F8h+var_B8], r9
0x18000a69a  lea     rsi, WPP_GLOBAL_Control
0x18000a6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6a8  cmp     rcx, rsi
0x18000a6ab  jz      short loc_18000A6C8
0x18000a6ad  test    byte ptr [rcx+1Ch], 4
0x18000a6b1  jz      short loc_18000A6C8
0x18000a6b3  mov     edx, 1Ch
0x18000a6b8  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a6bf  mov     rcx, [rcx+10h]
0x18000a6c3  call    WPP_SF_
0x18000a6c8  xor     ebx, ebx
0x18000a6ca  mov     [rsp+0F8h+var_C8], ebx
0x18000a6ce  lea     rdx, byte_1800AA3F0
0x18000a6d5  lea     rcx, [rsp+0F8h+var_80]
0x18000a6da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a6df  nop
0x18000a6e0  lea     rdx, [rsp+0F8h+var_80]
0x18000a6e5  lea     rcx, [rsp+0F8h+var_98]
0x18000a6ea  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000a6ef  nop
0x18000a6f0  lea     rcx, [rsp+0F8h+var_80]
0x18000a6f5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a6fa  mov     rdi, [rsp+0F8h+var_98]
0x18000a6ff  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000a706  lea     rcx, [rsp+0F8h+var_60]
0x18000a70e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a713  nop
0x18000a714  lea     r8, [rsp+0F8h+var_60]
0x18000a71c  lea     rdx, [rsp+0F8h+var_A8]
0x18000a721  mov     rcx, rdi
0x18000a724  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000a729  nop
0x18000a72a  lea     rcx, [rsp+0F8h+var_60]
0x18000a732  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a737  mov     [rsp+0F8h+var_D8], r12
0x18000a73c  mov     r9, r13
0x18000a73f  mov     r8, r15
0x18000a742  xor     edx, edx
0x18000a744  lea     rcx, [rsp+0F8h+var_A8]
0x18000a749  call    ?RemovePartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEB_N@Z; wvr::MSFT_WvrAdminTasks::RemovePartnership(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,bool const *)
0x18000a74e  mov     edi, eax
0x18000a750  mov     [rsp+0F8h+var_C8], eax
0x18000a754  mov     rcx, [rsp+0F8h+var_A0]; this
0x18000a759  test    rcx, rcx
0x18000a75c  jz      short loc_18000A764
0x18000a75e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a763  nop
0x18000a764  mov     rcx, [rsp+0F8h+var_90]; this
0x18000a769  test    rcx, rcx
0x18000a76c  jz      short loc_18000A774
0x18000a76e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a773  nop
0x18000a774  jmp     short loc_18000A78E
0x18000a776  mov     ebx, [rsp+0F8h+var_C4]
0x18000a77a  lea     rsi, WPP_GLOBAL_Control
0x18000a781  test    ebx, ebx
0x18000a783  jnz     short loc_18000A7AC
0x18000a785  mov     edi, [rsp+0F8h+var_C8]
0x18000a789  mov     r14, [rsp+0F8h+var_B8]
0x18000a78e  test    edi, edi
0x18000a790  jz      short loc_18000A7AC
0x18000a792  mov     rax, [r14]
0x18000a795  mov     edx, edi
0x18000a797  mov     rcx, r14
0x18000a79a  mov     rax, [rax+20h]
0x18000a79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a3  mov     ecx, edi; unsigned int
0x18000a7a5  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000a7aa  mov     ebx, eax
0x18000a7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7b3  cmp     rcx, rsi
0x18000a7b6  jz      short loc_18000A7D6
0x18000a7b8  test    byte ptr [rcx+1Ch], 1
0x18000a7bc  jz      short loc_18000A7D6
0x18000a7be  mov     edx, 1Dh
0x18000a7c3  mov     r9d, ebx
0x18000a7c6  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a7cd  mov     rcx, [rcx+10h]
0x18000a7d1  call    WPP_SF_d
0x18000a7d6  mov     eax, ebx
0x18000a7d8  mov     rcx, [rsp+0F8h+var_40]
0x18000a7e0  xor     rcx, rsp; StackCookie
0x18000a7e3  call    __security_check_cookie
0x18000a7e8  add     rsp, 0C0h
0x18000a7ef  pop     r15
0x18000a7f1  pop     r14
0x18000a7f3  pop     r13
0x18000a7f5  pop     r12
0x18000a7f7  pop     rdi
0x18000a7f8  pop     rsi
0x18000a7f9  pop     rbx
0x18000a7fa  retn
```
