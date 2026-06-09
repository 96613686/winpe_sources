# SrSmapiInvokeCreateReplicationPartnership(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const *,unsigned __int64 *,uint *,ushort *,CWMIContext &)

- ea: `0x18000ef94`
- end: `0x18000f25d`
- name: `?SrSmapiInvokeCreateReplicationPartnership@@YA?AW4_MI_Result@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@3@100PEA_KPEAIPEAGAEAVCWMIContext@@@Z`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e848`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x1800067cc`
- `0x1800067fc`
- `0x18000911c`
- `0x18000ef94`
- `0x18001db88`
- `0x1800261d4`
- `0x180026470`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        struct CWMIContext *a14)
{
  struct CWMIContext *v16; // r15
  enum _MI_Result v17; // edi
  int v18; // esi
  __int64 v19; // rdx
  unsigned int v20; // esi
  enum _MI_Result v22; // [rsp+B0h] [rbp-118h] BYREF
  unsigned int v23; // [rsp+B4h] [rbp-114h]
  struct CWMIContext *v24; // [rsp+C0h] [rbp-108h]
  __int64 v25; // [rsp+D0h] [rbp-F8h]
  __int64 v26; // [rsp+D8h] [rbp-F0h]
  __int64 v27; // [rsp+E0h] [rbp-E8h]
  __int64 v28; // [rsp+E8h] [rbp-E0h]
  __int64 v29; // [rsp+F0h] [rbp-D8h]
  __int64 v30; // [rsp+F8h] [rbp-D0h]
  __int64 v31; // [rsp+100h] [rbp-C8h]
  __int64 v32; // [rsp+108h] [rbp-C0h]
  __int64 v33; // [rsp+110h] [rbp-B8h]
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
  try
  {
    v17 = MI_RESULT_OK;
    v23 = 0;
    LOWORD(v22) = 0;
    std::wstring::wstring(v39, byte_1800AA3F0);
    mi::MiApplication::Create(&v36, v39);
    std::wstring::_Tidy_deallocate(v39);
    v18 = v36;
    std::wstring::wstring(v40, L"root/microsoft/windows/storagereplica");
    mi::MiApplication::CreateSession(v18, (__int64)&v34, (int)v40);
    std::wstring::_Tidy_deallocate(v40);
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
  catch ( std::system_error *v38 )
  {
    v22 = CatchErrorFromMiClient(v38, v24);
    v17 = v22;
    if ( v22 )
      goto LABEL_13;
    v20 = v23;
    v16 = v24;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(struct CWMIContext *, _QWORD))(*(_QWORD *)v16 + 32LL))(v16, v20);
    v17 = MapWinErrorToMIResult(v20);
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids,
      (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000ef94  push    rbx
0x18000ef96  push    rsi
0x18000ef97  push    rdi
0x18000ef98  push    r12
0x18000ef9a  push    r13
0x18000ef9c  push    r14
0x18000ef9e  push    r15
0x18000efa0  sub     rsp, 190h
0x18000efa7  mov     rax, cs:__security_cookie
0x18000efae  xor     rax, rsp
0x18000efb1  mov     [rsp+1C8h+var_48], rax
0x18000efb9  mov     [rsp+1C8h+var_D8], r9
0x18000efc1  mov     [rsp+1C8h+var_B8], r8
0x18000efc9  mov     r13, rdx
0x18000efcc  mov     r12, rcx
0x18000efcf  mov     rax, [rsp+1C8h+arg_20]
0x18000efd7  mov     [rsp+1C8h+var_C0], rax
0x18000efdf  mov     rax, [rsp+1C8h+arg_28]
0x18000efe7  mov     [rsp+1C8h+var_E0], rax
0x18000efef  mov     rax, [rsp+1C8h+arg_30]
0x18000eff7  mov     [rsp+1C8h+var_C8], rax
0x18000efff  mov     rax, [rsp+1C8h+arg_38]
0x18000f007  mov     [rsp+1C8h+var_E8], rax
0x18000f00f  mov     rax, [rsp+1C8h+arg_40]
0x18000f017  mov     [rsp+1C8h+var_D0], rax
0x18000f01f  mov     rax, [rsp+1C8h+arg_48]
0x18000f027  mov     [rsp+1C8h+var_F0], rax
0x18000f02f  mov     rax, [rsp+1C8h+arg_50]
0x18000f037  mov     [rsp+1C8h+var_F8], rax
0x18000f03f  mov     r15, [rsp+1C8h+arg_68]
0x18000f047  mov     [rsp+1C8h+var_108], r15
0x18000f04f  lea     r14, WPP_GLOBAL_Control
0x18000f056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f05d  cmp     rcx, r14
0x18000f060  jz      short loc_18000F07D
0x18000f062  test    byte ptr [rcx+1Ch], 4
0x18000f066  jz      short loc_18000F07D
0x18000f068  mov     edx, 0Eh
0x18000f06d  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f074  mov     rcx, [rcx+10h]
0x18000f078  call    WPP_SF_
0x18000f07d  xor     ebx, ebx
0x18000f07f  mov     edi, ebx
0x18000f081  mov     [rsp+1C8h+var_114], ebx
0x18000f088  mov     word ptr [rsp+1C8h+var_118], bx
0x18000f090  lea     rdx, byte_1800AA3F0
0x18000f097  lea     rcx, [rsp+1C8h+var_88]
0x18000f09f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f0a4  nop
0x18000f0a5  lea     rdx, [rsp+1C8h+var_88]
0x18000f0ad  lea     rcx, [rsp+1C8h+var_A0]
0x18000f0b5  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x18000f0ba  nop
0x18000f0bb  lea     rcx, [rsp+1C8h+var_88]
0x18000f0c3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f0c8  mov     rsi, [rsp+1C8h+var_A0]
0x18000f0d0  lea     rdx, aRootMicrosoftW; "root/microsoft/windows/storagereplica"
0x18000f0d7  lea     rcx, [rsp+1C8h+var_68]
0x18000f0df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18000f0e4  nop
0x18000f0e5  lea     r8, [rsp+1C8h+var_68]
0x18000f0ed  lea     rdx, [rsp+1C8h+var_B0]
0x18000f0f5  mov     rcx, rsi
0x18000f0f8  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x18000f0fd  nop
0x18000f0fe  lea     rcx, [rsp+1C8h+var_68]
0x18000f106  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f10b  lea     rax, [rsp+1C8h+var_118]
0x18000f113  mov     [rsp+1C8h+var_160], rax
0x18000f118  mov     rax, [rsp+1C8h+var_F8]
0x18000f120  mov     [rsp+1C8h+var_168], rax
0x18000f125  mov     rax, [rsp+1C8h+var_F0]
0x18000f12d  mov     [rsp+1C8h+var_170], rax
0x18000f132  mov     rax, [rsp+1C8h+var_E8]
0x18000f13a  mov     [rsp+1C8h+var_178], rax
0x18000f13f  mov     rax, [rsp+1C8h+var_E0]
0x18000f147  mov     [rsp+1C8h+var_180], rax
0x18000f14c  mov     [rsp+1C8h+var_188], r13
0x18000f151  mov     rax, [rsp+1C8h+var_D8]
0x18000f159  mov     [rsp+1C8h+var_190], rax
0x18000f15e  mov     rax, [rsp+1C8h+var_D0]
0x18000f166  mov     [rsp+1C8h+var_198], rax
0x18000f16b  mov     rax, [rsp+1C8h+var_C8]
0x18000f173  mov     [rsp+1C8h+var_1A0], rax
0x18000f178  mov     rax, [rsp+1C8h+var_C0]
0x18000f180  mov     [rsp+1C8h+var_1A8], rax
0x18000f185  mov     r9, r12
0x18000f188  mov     r8, [rsp+1C8h+var_B8]
0x18000f190  lea     rcx, [rsp+1C8h+var_B0]
0x18000f198  call    ?CreateTopology@MSFT_WvrAdminTasks@wvr@@SAIAEBV?$shared_ptr@VMiSession@mi@@@std@@PEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@111PEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@111121PEB_KPEBGPEBIPEB_N6566PEAV?$vector@VMSFT_WvrReplicationPartnership@wvr@@V?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@std@@@4@@Z; wvr::MSFT_WvrAdminTasks::CreateTopology(std::shared_ptr<mi::MiSession> const &,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,std::wstring const *,std::wstring const *,std::wstring const *,std::vector<std::wstring> const *,std::wstring const *,unsigned __int64 const *,ushort const *,uint const *,bool const *,bool const *,uint const *,bool const *,bool const *,std::vector<wvr::MSFT_WvrReplicationPartnership> *)
0x18000f19d  mov     esi, eax
0x18000f19f  mov     [rsp+1C8h+var_114], eax
0x18000f1a6  mov     rcx, [rsp+1C8h+var_A8]; this
0x18000f1ae  test    rcx, rcx
0x18000f1b1  jz      short loc_18000F1B9
0x18000f1b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f1b8  nop
0x18000f1b9  mov     rcx, [rsp+1C8h+var_98]; this
0x18000f1c1  test    rcx, rcx
0x18000f1c4  jz      short loc_18000F1CC
0x18000f1c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f1cb  nop
0x18000f1cc  jmp     short loc_18000F1EF
0x18000f1ce  mov     edi, [rsp+1C8h+var_118]
0x18000f1d5  lea     r14, WPP_GLOBAL_Control
0x18000f1dc  test    edi, edi
0x18000f1de  jnz     short loc_18000F20D
0x18000f1e0  mov     esi, [rsp+1C8h+var_114]
0x18000f1e7  mov     r15, [rsp+1C8h+var_108]
0x18000f1ef  test    esi, esi
0x18000f1f1  jz      short loc_18000F20D
0x18000f1f3  mov     rax, [r15]
0x18000f1f6  mov     edx, esi
0x18000f1f8  mov     rcx, r15
0x18000f1fb  mov     rax, [rax+20h]
0x18000f1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f204  mov     ecx, esi; unsigned int
0x18000f206  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000f20b  mov     edi, eax
0x18000f20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f214  cmp     rcx, r14
0x18000f217  jz      short loc_18000F237
0x18000f219  test    byte ptr [rcx+1Ch], 1
0x18000f21d  jz      short loc_18000F237
0x18000f21f  mov     edx, 0Fh
0x18000f224  mov     r9d, edi
0x18000f227  lea     r8, WPP_dc343923babc33dbba3c8f9f14f89261_Traceguids
0x18000f22e  mov     rcx, [rcx+10h]
0x18000f232  call    WPP_SF_d
0x18000f237  mov     eax, edi
0x18000f239  mov     rcx, [rsp+1C8h+var_48]
0x18000f241  xor     rcx, rsp; StackCookie
0x18000f244  call    __security_check_cookie
0x18000f249  add     rsp, 190h
0x18000f250  pop     r15
0x18000f252  pop     r14
0x18000f254  pop     r13
0x18000f256  pop     r12
0x18000f258  pop     rdi
0x18000f259  pop     rsi
0x18000f25a  pop     rbx
0x18000f25b  retn
```
