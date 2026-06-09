# SrSmapiInvokeCreateReplicationPartnership(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)

- ea: `0x18000efc0`
- end: `0x18000f288`
- name: `?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@100PEA_KPEAIPEAGAEAVCWMIContext@@@Z`
- size: `712`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e874`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x180006778`
- `0x1800067a0`
- `0x180008f64`
- `0x18000efc0`
- `0x18001da60`
- `0x180025ea4`
- `0x180026134`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _QWORD *a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        struct CWMIContext *a14)
{
  struct CWMIContext *v16; // r15
  unsigned int v17; // edi
  __int64 v18; // rsi
  __int64 v19; // rdx
  unsigned int v20; // esi
  unsigned int v22; // [rsp+B0h] [rbp-118h] BYREF
  unsigned int v23; // [rsp+B4h] [rbp-114h]
  struct CWMIContext *v24; // [rsp+C0h] [rbp-108h]
  __int64 v25; // [rsp+D0h] [rbp-F8h]
  _QWORD *v26; // [rsp+D8h] [rbp-F0h]
  __int64 v27; // [rsp+E0h] [rbp-E8h]
  _QWORD *v28; // [rsp+E8h] [rbp-E0h]
  _QWORD *v29; // [rsp+F0h] [rbp-D8h]
  _QWORD *v30; // [rsp+F8h] [rbp-D0h]
  __int64 v31; // [rsp+100h] [rbp-C8h]
  _QWORD *v32; // [rsp+108h] [rbp-C0h]
  _QWORD *v33; // [rsp+110h] [rbp-B8h]
  __int64 v34; // [rsp+118h] [rbp-B0h] BYREF
  std::_Ref_count_base *v35; // [rsp+120h] [rbp-A8h]
  __int64 v36; // [rsp+128h] [rbp-A0h] BYREF
  std::_Ref_count_base *v37; // [rsp+130h] [rbp-98h]
  std::system_error *v38; // [rsp+138h] [rbp-90h] BYREF
  MI_Char v39[16]; // [rsp+140h] [rbp-88h] BYREF
  _BYTE v40[32]; // [rsp+160h] [rbp-68h] BYREF

  v29 = a4;
  v33 = a3;
  v32 = a5;
  v28 = a6;
  v31 = a7;
  v27 = a8;
  v30 = a9;
  v26 = a10;
  v25 = a11;
  v16 = a14;
  v24 = a14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v17 = 0;
    v23 = 0;
    LOWORD(v22) = 0;
    std::wstring::wstring((__int64)v39, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v36, v39);
    std::wstring::_Tidy_deallocate((__int64)v39);
    v18 = v36;
    std::wstring::wstring((__int64)v40, (__int64)L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v18, &v34, (__int64)v40);
    std::wstring::_Tidy_deallocate((__int64)v40);
    v20 = wvr::MSFT_WvrAdminTasks::CreateTopology(
            &v34,
            v19,
            v33,
            a1,
            v32,
            v31,
            v30,
            v29,
            a2,
            v28,
            v27,
            v26,
            v25,
            (__int64)&v22);
    v23 = v20;
    if ( v35 )
      std::_Ref_count_base::_Decref(v35);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::system_error `RTTI Type Descriptor', &v38) )
    {
      v22 = CatchErrorFromMiClient(v38, v24);
      __eh34_try_continuation(0, &std::system_error `RTTI Type Descriptor', &loc_18000F1FA);
      v17 = v22;
      if ( v22 )
        goto LABEL_13;
      v20 = v23;
      v16 = v24;
    }
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v16 + 32LL))(v16, v20);
    v17 = MapWinErrorToMIResult(v20);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids, v17);
  return v17;
}

```

## disassembly

```asm
0x18000efc0  push    rbx
0x18000efc2  push    rsi
0x18000efc3  push    rdi
0x18000efc4  push    r12
0x18000efc6  push    r13
0x18000efc8  push    r14
0x18000efca  push    r15
0x18000efcc  sub     rsp, 190h
0x18000efd3  mov     rax, cs:__security_cookie
0x18000efda  xor     rax, rsp
0x18000efdd  mov     [rsp+1C8h+var_48], rax
0x18000efe5  mov     [rsp+1C8h+var_D8], r9
0x18000efed  mov     [rsp+1C8h+var_B8], r8
0x18000eff5  mov     r13, rdx
0x18000eff8  mov     r12, rcx
0x18000effb  mov     rax, [rsp+1C8h+arg_20]
0x18000f003  mov     [rsp+1C8h+var_C0], rax
0x18000f00b  mov     rax, [rsp+1C8h+arg_28]
0x18000f013  mov     [rsp+1C8h+var_E0], rax
0x18000f01b  mov     rax, [rsp+1C8h+arg_30]
0x18000f023  mov     [rsp+1C8h+var_C8], rax
0x18000f02b  mov     rax, [rsp+1C8h+arg_38]
0x18000f033  mov     [rsp+1C8h+var_E8], rax
0x18000f03b  mov     rax, [rsp+1C8h+arg_40]
0x18000f043  mov     [rsp+1C8h+var_D0], rax
0x18000f04b  mov     rax, [rsp+1C8h+arg_48]
0x18000f053  mov     [rsp+1C8h+var_F0], rax
0x18000f05b  mov     rax, [rsp+1C8h+arg_50]
0x18000f063  mov     [rsp+1C8h+var_F8], rax
0x18000f06b  mov     r15, [rsp+1C8h+arg_68]
0x18000f073  mov     [rsp+1C8h+var_108], r15
0x18000f07b  lea     r14, WPP_GLOBAL_Control
0x18000f082  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f089  cmp     rcx, r14
0x18000f08c  jz      short loc_18000F0A9
0x18000f08e  test    byte ptr [rcx+1Ch], 4
0x18000f092  jz      short loc_18000F0A9
0x18000f094  mov     edx, 0Eh
0x18000f099  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f0a0  mov     rcx, [rcx+10h]
0x18000f0a4  call    WPP_SF_
0x18000f0a9  xor     ebx, ebx
0x18000f0ab  mov     edi, ebx
0x18000f0ad  mov     [rsp+1C8h+var_114], ebx
0x18000f0b4  mov     word ptr [rsp+1C8h+var_118], bx
0x18000f0bc  lea     rdx, byte_1800AA410
0x18000f0c3  lea     rcx, [rsp+1C8h+var_88]
0x18000f0cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f0d0  nop
0x18000f0d1  lea     rdx, [rsp+1C8h+var_88]
0x18000f0d9  lea     rcx, [rsp+1C8h+var_A0]
0x18000f0e1  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000f0e6  nop
0x18000f0e7  lea     rcx, [rsp+1C8h+var_88]
0x18000f0ef  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f0f4  mov     rsi, [rsp+1C8h+var_A0]
0x18000f0fc  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000f103  lea     rcx, [rsp+1C8h+var_68]
0x18000f10b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f110  nop
0x18000f111  lea     r8, [rsp+1C8h+var_68]
0x18000f119  lea     rdx, [rsp+1C8h+var_B0]
0x18000f121  mov     rcx, rsi
0x18000f124  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000f129  nop
0x18000f12a  lea     rcx, [rsp+1C8h+var_68]
0x18000f132  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f137  lea     rax, [rsp+1C8h+var_118]
0x18000f13f  mov     [rsp+1C8h+var_160], rax
0x18000f144  mov     rax, [rsp+1C8h+var_F8]
0x18000f14c  mov     [rsp+1C8h+var_168], rax
0x18000f151  mov     rax, [rsp+1C8h+var_F0]
0x18000f159  mov     [rsp+1C8h+var_170], rax
0x18000f15e  mov     rax, [rsp+1C8h+var_E8]
0x18000f166  mov     [rsp+1C8h+var_178], rax
0x18000f16b  mov     rax, [rsp+1C8h+var_E0]
0x18000f173  mov     [rsp+1C8h+var_180], rax
0x18000f178  mov     [rsp+1C8h+var_188], r13
0x18000f17d  mov     rax, [rsp+1C8h+var_D8]
0x18000f185  mov     [rsp+1C8h+var_190], rax
0x18000f18a  mov     rax, [rsp+1C8h+var_D0]
0x18000f192  mov     [rsp+1C8h+var_198], rax
0x18000f197  mov     rax, [rsp+1C8h+var_C8]
0x18000f19f  mov     [rsp+1C8h+var_1A0], rax
0x18000f1a4  mov     rax, [rsp+1C8h+var_C0]
0x18000f1ac  mov     [rsp+1C8h+var_1A8], rax
0x18000f1b1  mov     r9, r12
0x18000f1b4  mov     r8, [rsp+1C8h+var_B8]
0x18000f1bc  lea     rcx, [rsp+1C8h+var_B0]
0x18000f1c4  call    ?CreateTopology@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@111121PEB_KPEBGPEBIPEB_N6566PEAV?$vector@VMSFT_WvrReplicationPartnership@wvr@@V?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@std@@@4@@Z; wvr::MSFT_WvrAdminTasks::CreateTopology(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,unsigned __int64 const *,ushort const *,uint const *,bool const *,bool const *,uint const *,bool const *,bool const *,std::vector<wvr::MSFT_WvrReplicationPartnership> *)
0x18000f1c9  mov     esi, eax
0x18000f1cb  mov     [rsp+1C8h+var_114], eax
0x18000f1d2  mov     rcx, [rsp+1C8h+var_A8]; this
0x18000f1da  test    rcx, rcx
0x18000f1dd  jz      short loc_18000F1E5
0x18000f1df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f1e4  nop
0x18000f1e5  mov     rcx, [rsp+1C8h+var_98]; this
0x18000f1ed  test    rcx, rcx
0x18000f1f0  jz      short loc_18000F1F8
0x18000f1f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f1f7  nop
0x18000f1f8  jmp     short loc_18000F21B
0x18000f1fa  mov     edi, [rsp+1C8h+var_118]
0x18000f201  lea     r14, WPP_GLOBAL_Control
0x18000f208  test    edi, edi
0x18000f20a  jnz     short loc_18000F239
0x18000f20c  mov     esi, [rsp+1C8h+var_114]
0x18000f213  mov     r15, [rsp+1C8h+var_108]
0x18000f21b  test    esi, esi
0x18000f21d  jz      short loc_18000F239
0x18000f21f  mov     rax, [r15]
0x18000f222  mov     edx, esi
0x18000f224  mov     rcx, r15
0x18000f227  mov     rax, [rax+20h]
0x18000f22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f230  mov     ecx, esi; unsigned int
0x18000f232  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000f237  mov     edi, eax
0x18000f239  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f240  cmp     rcx, r14
0x18000f243  jz      short loc_18000F263
0x18000f245  test    byte ptr [rcx+1Ch], 1
0x18000f249  jz      short loc_18000F263
0x18000f24b  mov     edx, 0Fh
0x18000f250  mov     r9d, edi
0x18000f253  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f25a  mov     rcx, [rcx+10h]
0x18000f25e  call    WPP_SF_d
0x18000f263  mov     eax, edi
0x18000f265  mov     rcx, [rsp+1C8h+var_48]
0x18000f26d  xor     rcx, rsp; StackCookie
0x18000f270  call    __security_check_cookie
0x18000f275  add     rsp, 190h
0x18000f27c  pop     r15
0x18000f27e  pop     r14
0x18000f280  pop     r13
0x18000f282  pop     r12
0x18000f284  pop     rdi
0x18000f285  pop     rsi
0x18000f286  pop     rbx
0x18000f287  retn
```
