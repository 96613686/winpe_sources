# SrSmapiInvokeRemoveReplicationRelationship(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,CWMIContext &)

- ea: `0x18000f264`
- end: `0x18000f40c`
- name: `?SrSmapiInvokeRemoveReplicationRelationship@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAVCWMIContext@@@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eba8`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000f264`
- `0x18001dff4`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrSmapiInvokeRemoveReplicationRelationship(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct CWMIContext *a5)
{
  struct CWMIContext *v8; // r14
  enum _MI_Result v9; // ebx
  int v10; // edi
  unsigned int v11; // edi
  unsigned int v13; // [rsp+30h] [rbp-C8h]
  enum _MI_Result v15; // [rsp+38h] [rbp-C0h]
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
    v11 = wvr::MSFT_WvrAdminTasks::RemovePartnership(&v16, a1, a2, a3, a4);
    v13 = v11;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  catch ( std::system_error *v20 )
  {
    v15 = CatchErrorFromMiClient(v20, a5);
    v9 = v15;
    if ( v15 )
      goto LABEL_13;
    v11 = v13;
    v8 = a5;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, v11);
    v9 = MapWinErrorToMIResult(v11);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f264  push    rbx
0x18000f266  push    rsi
0x18000f267  push    rdi
0x18000f268  push    r12
0x18000f26a  push    r13
0x18000f26c  push    r14
0x18000f26e  push    r15
0x18000f270  sub     rsp, 0C0h
0x18000f277  mov     rax, cs:__security_cookie
0x18000f27e  xor     rax, rsp
0x18000f281  mov     [rsp+0F8h+var_40], rax
0x18000f289  mov     [rsp+0F8h+var_C0], r9
0x18000f28e  mov     r13, r8
0x18000f291  mov     r12, rdx
0x18000f294  mov     r15, rcx
0x18000f297  mov     r14, [rsp+0F8h+arg_20]
0x18000f29f  mov     [rsp+0F8h+var_B8], r14
0x18000f2a4  lea     rsi, WPP_GLOBAL_Control
0x18000f2ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2b2  cmp     rcx, rsi
0x18000f2b5  jz      short loc_18000F2D2
0x18000f2b7  test    byte ptr [rcx+1Ch], 4
0x18000f2bb  jz      short loc_18000F2D2
0x18000f2bd  mov     edx, 10h
0x18000f2c2  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f2c9  mov     rcx, [rcx+10h]
0x18000f2cd  call    WPP_SF_
0x18000f2d2  xor     ebx, ebx
0x18000f2d4  mov     [rsp+0F8h+var_C8], ebx
0x18000f2d8  lea     rdx, byte_1800AA3F0
0x18000f2df  lea     rcx, [rsp+0F8h+var_80]
0x18000f2e4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f2e9  nop
0x18000f2ea  lea     rdx, [rsp+0F8h+var_80]
0x18000f2ef  lea     rcx, [rsp+0F8h+var_98]
0x18000f2f4  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000f2f9  nop
0x18000f2fa  lea     rcx, [rsp+0F8h+var_80]
0x18000f2ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f304  mov     rdi, [rsp+0F8h+var_98]
0x18000f309  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000f310  lea     rcx, [rsp+0F8h+var_60]
0x18000f318  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f31d  nop
0x18000f31e  lea     r8, [rsp+0F8h+var_60]
0x18000f326  lea     rdx, [rsp+0F8h+var_A8]
0x18000f32b  mov     rcx, rdi
0x18000f32e  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000f333  nop
0x18000f334  lea     rcx, [rsp+0F8h+var_60]
0x18000f33c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f341  mov     rax, [rsp+0F8h+var_C0]
0x18000f346  mov     [rsp+0F8h+var_D8], rax
0x18000f34b  mov     r9, r13
0x18000f34e  mov     r8, r12
0x18000f351  mov     rdx, r15
0x18000f354  lea     rcx, [rsp+0F8h+var_A8]
0x18000f359  call    ?RemovePartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEB_N@Z; wvr::MSFT_WvrAdminTasks::RemovePartnership(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,bool const *)
0x18000f35e  mov     edi, eax
0x18000f360  mov     [rsp+0F8h+var_C8], eax
0x18000f364  mov     rcx, [rsp+0F8h+var_A0]; this
0x18000f369  test    rcx, rcx
0x18000f36c  jz      short loc_18000F374
0x18000f36e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f373  nop
0x18000f374  mov     rcx, [rsp+0F8h+var_90]; this
0x18000f379  test    rcx, rcx
0x18000f37c  jz      short loc_18000F384
0x18000f37e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f383  nop
0x18000f384  jmp     short loc_18000F39E
0x18000f386  mov     ebx, dword ptr [rsp+0F8h+var_C0]
0x18000f38a  lea     rsi, WPP_GLOBAL_Control
0x18000f391  test    ebx, ebx
0x18000f393  jnz     short loc_18000F3BC
0x18000f395  mov     edi, [rsp+0F8h+var_C8]
0x18000f399  mov     r14, [rsp+0F8h+var_B8]
0x18000f39e  test    edi, edi
0x18000f3a0  jz      short loc_18000F3BC
0x18000f3a2  mov     rax, [r14]
0x18000f3a5  mov     edx, edi
0x18000f3a7  mov     rcx, r14
0x18000f3aa  mov     rax, [rax+20h]
0x18000f3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3b3  mov     ecx, edi; unsigned int
0x18000f3b5  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000f3ba  mov     ebx, eax
0x18000f3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3c3  cmp     rcx, rsi
0x18000f3c6  jz      short loc_18000F3E6
0x18000f3c8  test    byte ptr [rcx+1Ch], 1
0x18000f3cc  jz      short loc_18000F3E6
0x18000f3ce  mov     edx, 11h
0x18000f3d3  mov     r9d, ebx
0x18000f3d6  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f3dd  mov     rcx, [rcx+10h]
0x18000f3e1  call    WPP_SF_d
0x18000f3e6  mov     eax, ebx
0x18000f3e8  mov     rcx, [rsp+0F8h+var_40]
0x18000f3f0  xor     rcx, rsp; StackCookie
0x18000f3f3  call    __security_check_cookie
0x18000f3f8  add     rsp, 0C0h
0x18000f3ff  pop     r15
0x18000f401  pop     r14
0x18000f403  pop     r13
0x18000f405  pop     r12
0x18000f407  pop     rdi
0x18000f408  pop     rsi
0x18000f409  pop     rbx
0x18000f40a  retn
```
