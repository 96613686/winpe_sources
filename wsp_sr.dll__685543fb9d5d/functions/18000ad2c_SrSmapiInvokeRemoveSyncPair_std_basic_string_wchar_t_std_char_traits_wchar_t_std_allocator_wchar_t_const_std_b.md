# SrSmapiInvokeRemoveSyncPair(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,CWMIContext &)

- ea: `0x18000ad2c`
- end: `0x18000aec5`
- name: `?SrSmapiInvokeRemoveSyncPair@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@1AEAVCWMIContext@@@Z`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c13c`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000ad2c`
- `0x18001e200`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrSmapiInvokeRemoveSyncPair(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        struct CWMIContext *a6)
{
  struct CWMIContext *v8; // r14
  enum _MI_Result v9; // ebx
  int v10; // edi
  __int64 v11; // rdx
  unsigned int v12; // edi
  unsigned int v14; // [rsp+20h] [rbp-B8h]
  enum _MI_Result v15; // [rsp+24h] [rbp-B4h]
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
  try
  {
    v9 = MI_RESULT_OK;
    std::wstring::wstring(v21, byte_1800AA3F0);
    mi::MiApplication::Create(&v18, v21);
    std::wstring::_Tidy_deallocate(v21);
    v10 = v18;
    std::wstring::wstring(v22, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v10, (__int64)&v16, (int)v22);
    std::wstring::_Tidy_deallocate(v22);
    v12 = wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(&v16, v11, a1, a4);
    v14 = v12;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  catch ( std::system_error *v20 )
  {
    v15 = CatchErrorFromMiClient(v20, a6);
    v9 = v15;
    if ( v15 )
      goto LABEL_13;
    v12 = v14;
    v8 = a6;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, v12);
    v9 = MapWinErrorToMIResult(v12);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ad2c  mov     [rsp+arg_8], rbx
0x18000ad31  push    rsi
0x18000ad32  push    rdi
0x18000ad33  push    r12
0x18000ad35  push    r14
0x18000ad37  push    r15
0x18000ad39  sub     rsp, 0B0h
0x18000ad40  mov     rax, cs:__security_cookie
0x18000ad47  xor     rax, rsp
0x18000ad4a  mov     [rsp+0D8h+var_30], rax
0x18000ad52  mov     r12, r9
0x18000ad55  mov     r15, rcx
0x18000ad58  mov     r14, [rsp+0D8h+arg_28]
0x18000ad60  mov     [rsp+0D8h+var_A8], r14
0x18000ad65  lea     rsi, WPP_GLOBAL_Control
0x18000ad6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad73  cmp     rcx, rsi
0x18000ad76  jz      short loc_18000AD93
0x18000ad78  test    byte ptr [rcx+1Ch], 4
0x18000ad7c  jz      short loc_18000AD93
0x18000ad7e  mov     edx, 22h ; '"'
0x18000ad83  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000ad8a  mov     rcx, [rcx+10h]
0x18000ad8e  call    WPP_SF_
0x18000ad93  xor     ebx, ebx
0x18000ad95  mov     [rsp+0D8h+var_B8], ebx
0x18000ad99  lea     rdx, byte_1800AA3F0
0x18000ada0  lea     rcx, [rsp+0D8h+var_70]
0x18000ada5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000adaa  nop
0x18000adab  lea     rdx, [rsp+0D8h+var_70]
0x18000adb0  lea     rcx, [rsp+0D8h+var_88]
0x18000adb5  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000adba  nop
0x18000adbb  lea     rcx, [rsp+0D8h+var_70]
0x18000adc0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000adc5  mov     rdi, [rsp+0D8h+var_88]
0x18000adca  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000add1  lea     rcx, [rsp+0D8h+var_50]
0x18000add9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000adde  nop
0x18000addf  lea     r8, [rsp+0D8h+var_50]
0x18000ade7  lea     rdx, [rsp+0D8h+var_98]
0x18000adec  mov     rcx, rdi
0x18000adef  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000adf4  nop
0x18000adf5  lea     rcx, [rsp+0D8h+var_50]
0x18000adfd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ae02  mov     r9, r12
0x18000ae05  mov     r8, r15
0x18000ae08  lea     rcx, [rsp+0D8h+var_98]
0x18000ae0d  call    ?SetGroupRemoveVolumes@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@1PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z; wvr::MSFT_WvrAdminTasks::SetGroupRemoveVolumes(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *)
0x18000ae12  mov     edi, eax
0x18000ae14  mov     [rsp+0D8h+var_B8], eax
0x18000ae18  mov     rcx, [rsp+0D8h+var_90]; this
0x18000ae1d  test    rcx, rcx
0x18000ae20  jz      short loc_18000AE28
0x18000ae22  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ae27  nop
0x18000ae28  mov     rcx, [rsp+0D8h+var_80]; this
0x18000ae2d  test    rcx, rcx
0x18000ae30  jz      short loc_18000AE38
0x18000ae32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ae37  nop
0x18000ae38  jmp     short loc_18000AE52
0x18000ae3a  mov     ebx, [rsp+0D8h+var_B4]
0x18000ae3e  lea     rsi, WPP_GLOBAL_Control
0x18000ae45  test    ebx, ebx
0x18000ae47  jnz     short loc_18000AE70
0x18000ae49  mov     edi, [rsp+0D8h+var_B8]
0x18000ae4d  mov     r14, [rsp+0D8h+var_A8]
0x18000ae52  test    edi, edi
0x18000ae54  jz      short loc_18000AE70
0x18000ae56  mov     rax, [r14]
0x18000ae59  mov     edx, edi
0x18000ae5b  mov     rcx, r14
0x18000ae5e  mov     rax, [rax+20h]
0x18000ae62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae67  mov     ecx, edi; unsigned int
0x18000ae69  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000ae6e  mov     ebx, eax
0x18000ae70  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae77  cmp     rcx, rsi
0x18000ae7a  jz      short loc_18000AE9A
0x18000ae7c  test    byte ptr [rcx+1Ch], 1
0x18000ae80  jz      short loc_18000AE9A
0x18000ae82  mov     edx, 23h ; '#'
0x18000ae87  mov     r9d, ebx
0x18000ae8a  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000ae91  mov     rcx, [rcx+10h]
0x18000ae95  call    WPP_SF_d
0x18000ae9a  mov     eax, ebx
0x18000ae9c  mov     rcx, [rsp+0D8h+var_30]
0x18000aea4  xor     rcx, rsp; StackCookie
0x18000aea7  call    __security_check_cookie
0x18000aeac  mov     rbx, [rsp+0D8h+arg_8]
0x18000aeb4  add     rsp, 0B0h
0x18000aebb  pop     r15
0x18000aebd  pop     r14
0x18000aebf  pop     r12
0x18000aec1  pop     rdi
0x18000aec2  pop     rsi
0x18000aec3  retn
```
