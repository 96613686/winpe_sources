# SrSmapiInvokeCreateReplicationPartnership(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CWMIContext &)

- ea: `0x18000a16c`
- end: `0x18000a34e`
- name: `?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAVCWMIContext@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000934c`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000a16c`
- `0x18001f058`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned int v8; // ebx
  __int64 v9; // rdi
  unsigned int v10; // edi
  unsigned int v12; // [rsp+30h] [rbp-E8h]
  unsigned int v13; // [rsp+34h] [rbp-E4h]
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
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v8 = 0;
    std::wstring::wstring((__int64)v23, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v17, v23);
    std::wstring::_Tidy_deallocate((__int64)v23);
    v9 = v17;
    std::wstring::wstring((__int64)v24, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v9, &v15, (__int64)v24);
    std::wstring::_Tidy_deallocate((__int64)v24);
    v10 = wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(&v15, (_QWORD *)v7, (_QWORD *)v6, (_QWORD *)v5);
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
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000A298);
      v8 = v13;
      v7 = v20;
      v6 = v21;
      v5 = v22;
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_97259de4980931de249eb41af43a46d5_Traceguids, v8);
  std::wstring::_Tidy_deallocate(v7);
  std::wstring::_Tidy_deallocate(v6);
  std::wstring::_Tidy_deallocate(v5);
  return v8;
}

```

## disassembly

```asm
0x18000a16c  push    rbx
0x18000a16e  push    rsi
0x18000a16f  push    rdi
0x18000a170  push    r12
0x18000a172  push    r13
0x18000a174  push    r14
0x18000a176  push    r15
0x18000a178  sub     rsp, 0E0h
0x18000a17f  mov     rax, cs:__security_cookie
0x18000a186  xor     rax, rsp
0x18000a189  mov     [rsp+118h+var_48], rax
0x18000a191  mov     r13, r9
0x18000a194  mov     r15, r8
0x18000a197  mov     r14, rdx
0x18000a19a  mov     rsi, rcx
0x18000a19d  mov     [rsp+118h+var_A0], rcx
0x18000a1a2  mov     [rsp+118h+var_98], rdx
0x18000a1aa  mov     [rsp+118h+var_90], r8
0x18000a1b2  mov     [rsp+118h+var_D8], r9
0x18000a1b7  lea     r12, WPP_GLOBAL_Control
0x18000a1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1c5  cmp     rcx, r12
0x18000a1c8  jz      short loc_18000A1E5
0x18000a1ca  test    byte ptr [rcx+1Ch], 4
0x18000a1ce  jz      short loc_18000A1E5
0x18000a1d0  mov     edx, 33h ; '3'
0x18000a1d5  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a1dc  mov     rcx, [rcx+10h]
0x18000a1e0  call    WPP_SF_
0x18000a1e5  xor     ebx, ebx
0x18000a1e7  mov     [rsp+118h+var_E8], ebx
0x18000a1eb  lea     rdx, byte_1800AA410
0x18000a1f2  lea     rcx, [rsp+118h+var_88]
0x18000a1fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a1ff  nop
0x18000a200  lea     rdx, [rsp+118h+var_88]
0x18000a208  lea     rcx, [rsp+118h+var_B8]
0x18000a20d  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000a212  nop
0x18000a213  lea     rcx, [rsp+118h+var_88]
0x18000a21b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a220  mov     rdi, [rsp+118h+var_B8]
0x18000a225  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000a22c  lea     rcx, [rsp+118h+var_68]
0x18000a234  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000a239  nop
0x18000a23a  lea     r8, [rsp+118h+var_68]
0x18000a242  lea     rdx, [rsp+118h+var_C8]
0x18000a247  mov     rcx, rdi
0x18000a24a  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000a24f  nop
0x18000a250  lea     rcx, [rsp+118h+var_68]
0x18000a258  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a25d  mov     r9, r15
0x18000a260  mov     r8, r14
0x18000a263  mov     rdx, rsi
0x18000a266  lea     rcx, [rsp+118h+var_C8]
0x18000a26b  call    ?WvrCreateReplicationPartnership@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111@Z; wvr::MSFT_WvrAdminTasks::WvrCreateReplicationPartnership(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *)
0x18000a270  mov     edi, eax
0x18000a272  mov     [rsp+118h+var_E8], eax
0x18000a276  mov     rcx, [rsp+118h+var_C0]; this
0x18000a27b  test    rcx, rcx
0x18000a27e  jz      short loc_18000A286
0x18000a280  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a285  nop
0x18000a286  mov     rcx, [rsp+118h+var_B0]; this
0x18000a28b  test    rcx, rcx
0x18000a28e  jz      short loc_18000A296
0x18000a290  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a295  nop
0x18000a296  jmp     short loc_18000A2C5
0x18000a298  mov     ebx, [rsp+118h+var_E4]
0x18000a29c  lea     r12, WPP_GLOBAL_Control
0x18000a2a3  mov     rsi, [rsp+118h+var_A0]
0x18000a2a8  mov     r14, [rsp+118h+var_98]
0x18000a2b0  mov     r15, [rsp+118h+var_90]
0x18000a2b8  test    ebx, ebx
0x18000a2ba  jnz     short loc_18000A2E4
0x18000a2bc  mov     edi, [rsp+118h+var_E8]
0x18000a2c0  mov     r13, [rsp+118h+var_D8]
0x18000a2c5  test    edi, edi
0x18000a2c7  jz      short loc_18000A2E4
0x18000a2c9  mov     rax, [r13+0]
0x18000a2cd  mov     edx, edi
0x18000a2cf  mov     rcx, r13
0x18000a2d2  mov     rax, [rax+20h]
0x18000a2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2db  mov     ecx, edi; unsigned int
0x18000a2dd  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000a2e2  mov     ebx, eax
0x18000a2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2eb  cmp     rcx, r12
0x18000a2ee  jz      short loc_18000A30F
0x18000a2f0  test    byte ptr [rcx+1Ch], 1
0x18000a2f4  jz      short loc_18000A30F
0x18000a2f6  mov     edx, 34h ; '4'
0x18000a2fb  mov     r9d, ebx
0x18000a2fe  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000a305  mov     rcx, [rcx+10h]
0x18000a309  call    WPP_SF_d
0x18000a30e  nop
0x18000a30f  mov     rcx, rsi
0x18000a312  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a317  nop
0x18000a318  mov     rcx, r14
0x18000a31b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a320  nop
0x18000a321  mov     rcx, r15
0x18000a324  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a329  mov     eax, ebx
0x18000a32b  mov     rcx, [rsp+118h+var_48]
0x18000a333  xor     rcx, rsp; StackCookie
0x18000a336  call    __security_check_cookie
0x18000a33b  add     rsp, 0E0h
0x18000a342  pop     r15
0x18000a344  pop     r14
0x18000a346  pop     r13
0x18000a348  pop     r12
0x18000a34a  pop     rdi
0x18000a34b  pop     rsi
0x18000a34c  pop     rbx
0x18000a34d  retn
```
