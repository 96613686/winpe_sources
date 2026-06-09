# SrSmapiInvokeDeleteReplicationGroup(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CWMIContext &)

- ea: `0x18000a4b0`
- end: `0x18000a65e`
- name: `?SrSmapiInvokeDeleteReplicationGroup@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@@Z`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009994`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000a4b0`
- `0x18001f354`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SrSmapiInvokeDeleteReplicationGroup(__int64 a1, struct CWMIContext *a2)
{
  struct CWMIContext *v2; // r15
  __int64 v3; // rdi
  enum _MI_Result v4; // ebx
  int v5; // esi
  unsigned int v6; // esi
  char v8[4]; // [rsp+20h] [rbp-B8h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-B4h]
  enum _MI_Result v10; // [rsp+28h] [rbp-B0h]
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
  try
  {
    v4 = MI_RESULT_OK;
    v9 = 0;
    v8[0] = 1;
    std::wstring::wstring(v18, byte_1800AA3F0);
    mi::MiApplication::Create(&v14, v18);
    std::wstring::_Tidy_deallocate(v18);
    v5 = v14;
    std::wstring::wstring(v19, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v5, (__int64)&v12, (int)v19);
    std::wstring::_Tidy_deallocate(v19);
    v6 = wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(&v12, v3, (__int64)v8);
    v9 = v6;
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
  }
  catch ( std::system_error *v16 )
  {
    v10 = CatchErrorFromMiClient(v16, v11);
    v4 = v10;
    v3 = v17;
    if ( v10 )
      goto LABEL_13;
    v6 = v9;
    v2 = v11;
  }
  if ( v6 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, v6);
    v4 = MapWinErrorToMIResult(v6);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v4);
  std::wstring::_Tidy_deallocate(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a4b0  mov     [rsp+arg_10], rbx
0x18000a4b5  mov     [rsp+arg_18], rsi
0x18000a4ba  push    rdi
0x18000a4bb  push    r14
0x18000a4bd  push    r15
0x18000a4bf  sub     rsp, 0C0h
0x18000a4c6  mov     rax, cs:__security_cookie
0x18000a4cd  xor     rax, rsp
0x18000a4d0  mov     [rsp+0D8h+var_28], rax
0x18000a4d8  mov     r15, rdx
0x18000a4db  mov     rdi, rcx
0x18000a4de  mov     [rsp+0D8h+var_70], rcx
0x18000a4e3  mov     [rsp+0D8h+var_A8], rdx
0x18000a4e8  lea     r14, WPP_GLOBAL_Control
0x18000a4ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4f6  cmp     rcx, r14
0x18000a4f9  jz      short loc_18000A516
0x18000a4fb  test    byte ptr [rcx+1Ch], 4
0x18000a4ff  jz      short loc_18000A516
0x18000a501  mov     edx, 16h
0x18000a506  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a50d  mov     rcx, [rcx+10h]
0x18000a511  call    WPP_SF_
0x18000a516  xor     ebx, ebx
0x18000a518  mov     [rsp+0D8h+var_B4], ebx
0x18000a51c  mov     [rsp+0D8h+var_B8], 1
0x18000a521  lea     rdx, byte_1800AA3F0
0x18000a528  lea     rcx, [rsp+0D8h+var_68]
0x18000a52d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a532  nop
0x18000a533  lea     rdx, [rsp+0D8h+var_68]
0x18000a538  lea     rcx, [rsp+0D8h+var_88]
0x18000a53d  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000a542  nop
0x18000a543  lea     rcx, [rsp+0D8h+var_68]
0x18000a548  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a54d  mov     rsi, [rsp+0D8h+var_88]
0x18000a552  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000a559  lea     rcx, [rsp+0D8h+var_48]
0x18000a561  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a566  nop
0x18000a567  lea     r8, [rsp+0D8h+var_48]
0x18000a56f  lea     rdx, [rsp+0D8h+var_98]
0x18000a574  mov     rcx, rsi
0x18000a577  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000a57c  nop
0x18000a57d  lea     rcx, [rsp+0D8h+var_48]
0x18000a585  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a58a  lea     r8, [rsp+0D8h+var_B8]
0x18000a58f  mov     rdx, rdi
0x18000a592  lea     rcx, [rsp+0D8h+var_98]
0x18000a597  call    ?WvrDeleteReplicationGroup@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEB_N@Z; wvr::MSFT_WvrAdminTasks::WvrDeleteReplicationGroup(std::shared_ptr<mi::MiSession> const &,std::wstring const *,bool const *)
0x18000a59c  mov     esi, eax
0x18000a59e  mov     [rsp+0D8h+var_B4], eax
0x18000a5a2  mov     rcx, [rsp+0D8h+var_90]; this
0x18000a5a7  test    rcx, rcx
0x18000a5aa  jz      short loc_18000A5B2
0x18000a5ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a5b1  nop
0x18000a5b2  mov     rcx, [rsp+0D8h+var_80]; this
0x18000a5b7  test    rcx, rcx
0x18000a5ba  jz      short loc_18000A5C2
0x18000a5bc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a5c1  nop
0x18000a5c2  jmp     short loc_18000A5E1
0x18000a5c4  mov     ebx, [rsp+0D8h+var_B0]
0x18000a5c8  lea     r14, WPP_GLOBAL_Control
0x18000a5cf  mov     rdi, [rsp+0D8h+var_70]
0x18000a5d4  test    ebx, ebx
0x18000a5d6  jnz     short loc_18000A5FF
0x18000a5d8  mov     esi, [rsp+0D8h+var_B4]
0x18000a5dc  mov     r15, [rsp+0D8h+var_A8]
0x18000a5e1  test    esi, esi
0x18000a5e3  jz      short loc_18000A5FF
0x18000a5e5  mov     rax, [r15]
0x18000a5e8  mov     edx, esi
0x18000a5ea  mov     rcx, r15
0x18000a5ed  mov     rax, [rax+20h]
0x18000a5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f6  mov     ecx, esi; unsigned int
0x18000a5f8  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000a5fd  mov     ebx, eax
0x18000a5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a606  cmp     rcx, r14
0x18000a609  jz      short loc_18000A62A
0x18000a60b  test    byte ptr [rcx+1Ch], 1
0x18000a60f  jz      short loc_18000A62A
0x18000a611  mov     edx, 17h
0x18000a616  mov     r9d, ebx
0x18000a619  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a620  mov     rcx, [rcx+10h]
0x18000a624  call    WPP_SF_d
0x18000a629  nop
0x18000a62a  mov     rcx, rdi
0x18000a62d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a632  mov     eax, ebx
0x18000a634  mov     rcx, [rsp+0D8h+var_28]
0x18000a63c  xor     rcx, rsp; StackCookie
0x18000a63f  call    __security_check_cookie
0x18000a644  lea     r11, [rsp+0D8h+var_18]
0x18000a64c  mov     rbx, [r11+30h]
0x18000a650  mov     rsi, [r11+38h]
0x18000a654  mov     rsp, r11
0x18000a657  pop     r15
0x18000a659  pop     r14
0x18000a65b  pop     rdi
0x18000a65c  retn
```
