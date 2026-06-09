# SrSmapiInvokeRemoveSyncPair(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,CWMIContext &)

- ea: `0x18000abc4`
- end: `0x18000ad5c`
- name: `?SrSmapiInvokeRemoveSyncPair@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1AEAVCWMIContext@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, int, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c0a8`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000abc4`
- `0x18001e0d4`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiInvokeRemoveSyncPair(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        struct CWMIContext *a6)
{
  struct CWMIContext *v8; // r14
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned int v12; // edi
  unsigned int v14; // [rsp+20h] [rbp-B8h]
  unsigned int v15; // [rsp+24h] [rbp-B4h]
  __int64 v16; // [rsp+40h] [rbp-98h] BYREF
  std::_Ref_count_base *v17; // [rsp+48h] [rbp-90h]
  __int64 v18; // [rsp+50h] [rbp-88h] BYREF
  std::_Ref_count_base *v19; // [rsp+58h] [rbp-80h]
  std::system_error *v20; // [rsp+60h] [rbp-78h] BYREF
  MI_Char v21[16]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v22[32]; // [rsp+88h] [rbp-50h] BYREF

  v8 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
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
    v12 = wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(&v16, v11, a1, a4);
    v14 = v12;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v20) )
    {
      v15 = CatchErrorFromMiClient(v20, a6);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000ACD2);
      v9 = v15;
      if ( v15 )
        goto LABEL_13;
      v12 = v14;
      v8 = a6;
    }
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, v12);
    v9 = MapWinErrorToMIResult(v12);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000abc4  mov     [rsp+arg_8], rbx
0x18000abc9  push    rsi
0x18000abca  push    rdi
0x18000abcb  push    r12
0x18000abcd  push    r14
0x18000abcf  push    r15
0x18000abd1  sub     rsp, 0B0h
0x18000abd8  mov     rax, cs:__security_cookie
0x18000abdf  xor     rax, rsp
0x18000abe2  mov     [rsp+0D8h+var_30], rax
0x18000abea  mov     r12, r9
0x18000abed  mov     r15, rcx
0x18000abf0  mov     r14, [rsp+0D8h+arg_28]
0x18000abf8  mov     [rsp+0D8h+var_A8], r14
0x18000abfd  lea     rsi, WPP_GLOBAL_Control
0x18000ac04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac0b  cmp     rcx, rsi
0x18000ac0e  jz      short loc_18000AC2B
0x18000ac10  test    byte ptr [rcx+1Ch], 4
0x18000ac14  jz      short loc_18000AC2B
0x18000ac16  mov     edx, 22h ; '"'
0x18000ac1b  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000ac22  mov     rcx, [rcx+10h]
0x18000ac26  call    WPP_SF_
0x18000ac2b  xor     ebx, ebx
0x18000ac2d  mov     [rsp+0D8h+var_B8], ebx
0x18000ac31  lea     rdx, byte_1800AA410
0x18000ac38  lea     rcx, [rsp+0D8h+var_70]
0x18000ac3d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000ac42  nop
0x18000ac43  lea     rdx, [rsp+0D8h+var_70]
0x18000ac48  lea     rcx, [rsp+0D8h+var_88]
0x18000ac4d  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000ac52  nop
0x18000ac53  lea     rcx, [rsp+0D8h+var_70]
0x18000ac58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ac5d  mov     rdi, [rsp+0D8h+var_88]
0x18000ac62  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000ac69  lea     rcx, [rsp+0D8h+var_50]
0x18000ac71  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000ac76  nop
0x18000ac77  lea     r8, [rsp+0D8h+var_50]
0x18000ac7f  lea     rdx, [rsp+0D8h+var_98]
0x18000ac84  mov     rcx, rdi
0x18000ac87  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000ac8c  nop
0x18000ac8d  lea     rcx, [rsp+0D8h+var_50]
0x18000ac95  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ac9a  mov     r9, r12
0x18000ac9d  mov     r8, r15
0x18000aca0  lea     rcx, [rsp+0D8h+var_98]
0x18000aca5  call    ?SetGroupRemoveVolumes@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z; wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *)
0x18000acaa  mov     edi, eax
0x18000acac  mov     [rsp+0D8h+var_B8], eax
0x18000acb0  mov     rcx, [rsp+0D8h+var_90]; this
0x18000acb5  test    rcx, rcx
0x18000acb8  jz      short loc_18000ACC0
0x18000acba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000acbf  nop
0x18000acc0  mov     rcx, [rsp+0D8h+var_80]; this
0x18000acc5  test    rcx, rcx
0x18000acc8  jz      short loc_18000ACD0
0x18000acca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000accf  nop
0x18000acd0  jmp     short loc_18000ACEA
0x18000acd2  mov     ebx, [rsp+0D8h+var_B4]
0x18000acd6  lea     rsi, WPP_GLOBAL_Control
0x18000acdd  test    ebx, ebx
0x18000acdf  jnz     short loc_18000AD08
0x18000ace1  mov     edi, [rsp+0D8h+var_B8]
0x18000ace5  mov     r14, [rsp+0D8h+var_A8]
0x18000acea  test    edi, edi
0x18000acec  jz      short loc_18000AD08
0x18000acee  mov     rax, [r14]
0x18000acf1  mov     edx, edi
0x18000acf3  mov     rcx, r14
0x18000acf6  mov     rax, [rax+20h]
0x18000acfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acff  mov     ecx, edi; unsigned int
0x18000ad01  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000ad06  mov     ebx, eax
0x18000ad08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad0f  cmp     rcx, rsi
0x18000ad12  jz      short loc_18000AD32
0x18000ad14  test    byte ptr [rcx+1Ch], 1
0x18000ad18  jz      short loc_18000AD32
0x18000ad1a  mov     edx, 23h ; '#'
0x18000ad1f  mov     r9d, ebx
0x18000ad22  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000ad29  mov     rcx, [rcx+10h]
0x18000ad2d  call    WPP_SF_d
0x18000ad32  mov     eax, ebx
0x18000ad34  mov     rcx, [rsp+0D8h+var_30]
0x18000ad3c  xor     rcx, rsp; StackCookie
0x18000ad3f  call    __security_check_cookie
0x18000ad44  mov     rbx, [rsp+0D8h+arg_8]
0x18000ad4c  add     rsp, 0B0h
0x18000ad53  pop     r15
0x18000ad55  pop     r14
0x18000ad57  pop     r12
0x18000ad59  pop     rdi
0x18000ad5a  pop     rsi
0x18000ad5b  retn
```
