# SrSmapiInvokeRemoveMember(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,CWMIContext &)

- ea: `0x18000aa28`
- end: `0x18000abbb`
- name: `?SrSmapiInvokeRemoveMember@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAVCWMIContext@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD *, __int64, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bec0`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000aa28`
- `0x18001ec00`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiInvokeRemoveMember(_QWORD *a1, __int64 a2, struct CWMIContext *a3)
{
  struct CWMIContext *v3; // r14
  unsigned int v6; // ebx
  __int64 v7; // rdi
  unsigned int v8; // edi
  unsigned int v10; // [rsp+20h] [rbp-B8h]
  unsigned int v11; // [rsp+24h] [rbp-B4h]
  __int64 v13; // [rsp+40h] [rbp-98h] BYREF
  std::_Ref_count_base *v14; // [rsp+48h] [rbp-90h]
  __int64 v15; // [rsp+50h] [rbp-88h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-80h]
  std::system_error *v17; // [rsp+60h] [rbp-78h] BYREF
  MI_Char v18[16]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v19[32]; // [rsp+88h] [rbp-50h] BYREF

  v3 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v6 = 0;
    std::wstring::wstring((__int64)v18, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v15, v18);
    std::wstring::_Tidy_deallocate((__int64)v18);
    v7 = v15;
    std::wstring::wstring((__int64)v19, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v7, &v13, (__int64)v19);
    std::wstring::_Tidy_deallocate((__int64)v19);
    v8 = wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(&v13, a1, a2);
    v10 = v8;
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v17) )
    {
      v11 = CatchErrorFromMiClient(v17, a3);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000AB31);
      v6 = v11;
      if ( v11 )
        goto LABEL_13;
      v8 = v10;
      v3 = a3;
    }
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v8);
    v6 = MapWinErrorToMIResult(v8);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000aa28  mov     [rsp+arg_18], rbx
0x18000aa2d  push    rsi
0x18000aa2e  push    rdi
0x18000aa2f  push    r12
0x18000aa31  push    r14
0x18000aa33  push    r15
0x18000aa35  sub     rsp, 0B0h
0x18000aa3c  mov     rax, cs:__security_cookie
0x18000aa43  xor     rax, rsp
0x18000aa46  mov     [rsp+0D8h+var_30], rax
0x18000aa4e  mov     r14, r8
0x18000aa51  mov     r12, rdx
0x18000aa54  mov     r15, rcx
0x18000aa57  mov     [rsp+0D8h+var_A8], r8
0x18000aa5c  lea     rsi, WPP_GLOBAL_Control
0x18000aa63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa6a  cmp     rcx, rsi
0x18000aa6d  jz      short loc_18000AA8A
0x18000aa6f  test    byte ptr [rcx+1Ch], 4
0x18000aa73  jz      short loc_18000AA8A
0x18000aa75  mov     edx, 4Dh ; 'M'
0x18000aa7a  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000aa81  mov     rcx, [rcx+10h]
0x18000aa85  call    WPP_SF_
0x18000aa8a  xor     ebx, ebx
0x18000aa8c  mov     [rsp+0D8h+var_B8], ebx
0x18000aa90  lea     rdx, byte_1800AA410
0x18000aa97  lea     rcx, [rsp+0D8h+var_70]
0x18000aa9c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000aaa1  nop
0x18000aaa2  lea     rdx, [rsp+0D8h+var_70]
0x18000aaa7  lea     rcx, [rsp+0D8h+var_88]
0x18000aaac  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000aab1  nop
0x18000aab2  lea     rcx, [rsp+0D8h+var_70]
0x18000aab7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000aabc  mov     rdi, [rsp+0D8h+var_88]
0x18000aac1  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000aac8  lea     rcx, [rsp+0D8h+var_50]
0x18000aad0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000aad5  nop
0x18000aad6  lea     r8, [rsp+0D8h+var_50]
0x18000aade  lea     rdx, [rsp+0D8h+var_98]
0x18000aae3  mov     rcx, rdi
0x18000aae6  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000aaeb  nop
0x18000aaec  lea     rcx, [rsp+0D8h+var_50]
0x18000aaf4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000aaf9  mov     r8, r12
0x18000aafc  mov     rdx, r15
0x18000aaff  lea     rcx, [rsp+0D8h+var_98]
0x18000ab04  call    ?SmapiRemoveMember@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z; wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::vector<std::wstring> const *)
0x18000ab09  mov     edi, eax
0x18000ab0b  mov     [rsp+0D8h+var_B8], eax
0x18000ab0f  mov     rcx, [rsp+0D8h+var_90]; this
0x18000ab14  test    rcx, rcx
0x18000ab17  jz      short loc_18000AB1F
0x18000ab19  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ab1e  nop
0x18000ab1f  mov     rcx, [rsp+0D8h+var_80]; this
0x18000ab24  test    rcx, rcx
0x18000ab27  jz      short loc_18000AB2F
0x18000ab29  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ab2e  nop
0x18000ab2f  jmp     short loc_18000AB49
0x18000ab31  mov     ebx, [rsp+0D8h+var_B4]
0x18000ab35  lea     rsi, WPP_GLOBAL_Control
0x18000ab3c  test    ebx, ebx
0x18000ab3e  jnz     short loc_18000AB67
0x18000ab40  mov     edi, [rsp+0D8h+var_B8]
0x18000ab44  mov     r14, [rsp+0D8h+var_A8]
0x18000ab49  test    edi, edi
0x18000ab4b  jz      short loc_18000AB67
0x18000ab4d  mov     rax, [r14]
0x18000ab50  mov     edx, edi
0x18000ab52  mov     rcx, r14
0x18000ab55  mov     rax, [rax+20h]
0x18000ab59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab5e  mov     ecx, edi; unsigned int
0x18000ab60  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000ab65  mov     ebx, eax
0x18000ab67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab6e  cmp     rcx, rsi
0x18000ab71  jz      short loc_18000AB91
0x18000ab73  test    byte ptr [rcx+1Ch], 1
0x18000ab77  jz      short loc_18000AB91
0x18000ab79  mov     edx, 4Eh ; 'N'
0x18000ab7e  mov     r9d, ebx
0x18000ab81  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000ab88  mov     rcx, [rcx+10h]
0x18000ab8c  call    WPP_SF_d
0x18000ab91  mov     eax, ebx
0x18000ab93  mov     rcx, [rsp+0D8h+var_30]
0x18000ab9b  xor     rcx, rsp; StackCookie
0x18000ab9e  call    __security_check_cookie
0x18000aba3  mov     rbx, [rsp+0D8h+arg_18]
0x18000abab  add     rsp, 0B0h
0x18000abb2  pop     r15
0x18000abb4  pop     r14
0x18000abb6  pop     r12
0x18000abb8  pop     rdi
0x18000abb9  pop     rsi
0x18000abba  retn
```
