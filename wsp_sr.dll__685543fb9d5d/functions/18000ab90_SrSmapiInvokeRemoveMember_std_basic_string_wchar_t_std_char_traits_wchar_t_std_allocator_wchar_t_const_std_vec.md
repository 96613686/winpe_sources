# SrSmapiInvokeRemoveMember(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,CWMIContext &)

- ea: `0x18000ab90`
- end: `0x18000ad24`
- name: `?SrSmapiInvokeRemoveMember@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@AEAVCWMIContext@@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bf54`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000ab90`
- `0x18001ed30`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrSmapiInvokeRemoveMember(__int64 a1, __int64 a2, struct CWMIContext *a3)
{
  struct CWMIContext *v3; // r14
  enum _MI_Result v6; // ebx
  int v7; // edi
  unsigned int v8; // edi
  unsigned int v10; // [rsp+20h] [rbp-B8h]
  enum _MI_Result v11; // [rsp+24h] [rbp-B4h]
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
  try
  {
    v6 = MI_RESULT_OK;
    std::wstring::wstring(v18, byte_1800AA3F0);
    mi::MiApplication::Create(&v15, v18);
    std::wstring::_Tidy_deallocate(v18);
    v7 = v15;
    std::wstring::wstring(v19, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v7, (__int64)&v13, (int)v19);
    std::wstring::_Tidy_deallocate(v19);
    v8 = wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(&v13, a1, a2);
    v10 = v8;
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
  }
  catch ( std::system_error *v17 )
  {
    v11 = CatchErrorFromMiClient(v17, a3);
    v6 = v11;
    if ( v11 )
      goto LABEL_13;
    v8 = v10;
    v3 = a3;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v8);
    v6 = MapWinErrorToMIResult(v8);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ab90  mov     [rsp+arg_18], rbx
0x18000ab95  push    rsi
0x18000ab96  push    rdi
0x18000ab97  push    r12
0x18000ab99  push    r14
0x18000ab9b  push    r15
0x18000ab9d  sub     rsp, 0B0h
0x18000aba4  mov     rax, cs:__security_cookie
0x18000abab  xor     rax, rsp
0x18000abae  mov     [rsp+0D8h+var_30], rax
0x18000abb6  mov     r14, r8
0x18000abb9  mov     r12, rdx
0x18000abbc  mov     r15, rcx
0x18000abbf  mov     [rsp+0D8h+var_A8], r8
0x18000abc4  lea     rsi, WPP_GLOBAL_Control
0x18000abcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abd2  cmp     rcx, rsi
0x18000abd5  jz      short loc_18000ABF2
0x18000abd7  test    byte ptr [rcx+1Ch], 4
0x18000abdb  jz      short loc_18000ABF2
0x18000abdd  mov     edx, 4Dh ; 'M'
0x18000abe2  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000abe9  mov     rcx, [rcx+10h]
0x18000abed  call    WPP_SF_
0x18000abf2  xor     ebx, ebx
0x18000abf4  mov     [rsp+0D8h+var_B8], ebx
0x18000abf8  lea     rdx, byte_1800AA3F0
0x18000abff  lea     rcx, [rsp+0D8h+var_70]
0x18000ac04  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000ac09  nop
0x18000ac0a  lea     rdx, [rsp+0D8h+var_70]
0x18000ac0f  lea     rcx, [rsp+0D8h+var_88]
0x18000ac14  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000ac19  nop
0x18000ac1a  lea     rcx, [rsp+0D8h+var_70]
0x18000ac1f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ac24  mov     rdi, [rsp+0D8h+var_88]
0x18000ac29  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000ac30  lea     rcx, [rsp+0D8h+var_50]
0x18000ac38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000ac3d  nop
0x18000ac3e  lea     r8, [rsp+0D8h+var_50]
0x18000ac46  lea     rdx, [rsp+0D8h+var_98]
0x18000ac4b  mov     rcx, rdi
0x18000ac4e  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000ac53  nop
0x18000ac54  lea     rcx, [rsp+0D8h+var_50]
0x18000ac5c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ac61  mov     r8, r12
0x18000ac64  mov     rdx, r15
0x18000ac67  lea     rcx, [rsp+0D8h+var_98]
0x18000ac6c  call    ?SmapiRemoveMember@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z; wvr::MSFT_WvrAdminTasks::SmapiRemoveMember(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::vector<std::wstring> const *)
0x18000ac71  mov     edi, eax
0x18000ac73  mov     [rsp+0D8h+var_B8], eax
0x18000ac77  mov     rcx, [rsp+0D8h+var_90]; this
0x18000ac7c  test    rcx, rcx
0x18000ac7f  jz      short loc_18000AC87
0x18000ac81  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ac86  nop
0x18000ac87  mov     rcx, [rsp+0D8h+var_80]; this
0x18000ac8c  test    rcx, rcx
0x18000ac8f  jz      short loc_18000AC97
0x18000ac91  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ac96  nop
0x18000ac97  jmp     short loc_18000ACB1
0x18000ac99  mov     ebx, [rsp+0D8h+var_B4]
0x18000ac9d  lea     rsi, WPP_GLOBAL_Control
0x18000aca4  test    ebx, ebx
0x18000aca6  jnz     short loc_18000ACCF
0x18000aca8  mov     edi, [rsp+0D8h+var_B8]
0x18000acac  mov     r14, [rsp+0D8h+var_A8]
0x18000acb1  test    edi, edi
0x18000acb3  jz      short loc_18000ACCF
0x18000acb5  mov     rax, [r14]
0x18000acb8  mov     edx, edi
0x18000acba  mov     rcx, r14
0x18000acbd  mov     rax, [rax+20h]
0x18000acc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc6  mov     ecx, edi; unsigned int
0x18000acc8  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000accd  mov     ebx, eax
0x18000accf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acd6  cmp     rcx, rsi
0x18000acd9  jz      short loc_18000ACF9
0x18000acdb  test    byte ptr [rcx+1Ch], 1
0x18000acdf  jz      short loc_18000ACF9
0x18000ace1  mov     edx, 4Eh ; 'N'
0x18000ace6  mov     r9d, ebx
0x18000ace9  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000acf0  mov     rcx, [rcx+10h]
0x18000acf4  call    WPP_SF_d
0x18000acf9  mov     eax, ebx
0x18000acfb  mov     rcx, [rsp+0D8h+var_30]
0x18000ad03  xor     rcx, rsp; StackCookie
0x18000ad06  call    __security_check_cookie
0x18000ad0b  mov     rbx, [rsp+0D8h+arg_18]
0x18000ad13  add     rsp, 0B0h
0x18000ad1a  pop     r15
0x18000ad1c  pop     r14
0x18000ad1e  pop     r12
0x18000ad20  pop     rdi
0x18000ad21  pop     rsi
0x18000ad22  retn
```
