# SrSmapiQueryVolumeObjectIdGivenPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CWMIContext &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180022ea4`
- end: `0x1800230ed`
- name: `?SrSmapiQueryVolumeObjectIdGivenPath@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@AEAV23@@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000bab8`

## callees

- `0x1800014e0`
- `0x180005884`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x18001a4dc`
- `0x180022ea4`
- `0x1800261d4`
- `0x180026470`
- `0x180027f54`
- `0x180028488`
- `0x180029f64`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SrSmapiQueryVolumeObjectIdGivenPath(__int64 a1, struct CWMIContext *a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  _QWORD *v4; // rsi
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  int v8; // edi
  mi::MiAsyncOperation *v9; // rcx
  _QWORD *v10; // rdx
  unsigned int v11; // edi
  char v13; // [rsp+20h] [rbp-178h] BYREF
  struct CWMIContext *v14; // [rsp+30h] [rbp-168h]
  _QWORD *v15; // [rsp+40h] [rbp-158h]
  char v16[8]; // [rsp+50h] [rbp-148h] BYREF
  std::_Ref_count_base *v17; // [rsp+58h] [rbp-140h]
  __int64 v18; // [rsp+60h] [rbp-138h] BYREF
  std::_Ref_count_base *v19; // [rsp+68h] [rbp-130h]
  std::system_error *v20; // [rsp+70h] [rbp-128h] BYREF
  _BYTE v21[80]; // [rsp+78h] [rbp-120h] BYREF
  _QWORD v22[2]; // [rsp+C8h] [rbp-D0h] BYREF
  unsigned __int64 v23; // [rsp+D8h] [rbp-C0h]
  unsigned __int64 v24; // [rsp+E0h] [rbp-B8h]
  _QWORD v25[7]; // [rsp+F0h] [rbp-A8h] BYREF
  _QWORD *v26; // [rsp+128h] [rbp-70h]
  MI_Char v27[16]; // [rsp+130h] [rbp-68h] BYREF
  _BYTE v28[32]; // [rsp+150h] [rbp-48h] BYREF

  v3 = a3;
  v14 = a2;
  v4 = a3;
  v15 = a3;
  std::wstring::wstring(v22, a1);
  v13 = 0;
  v5 = v23;
  if ( v23 )
  {
    v6 = v22;
    if ( v24 > 7 )
      v6 = (_QWORD *)v22[0];
    if ( *((_WORD *)v6 + v23 - 1) != 92 )
    {
      if ( v23 >= v24 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(v22);
      }
      else
      {
        ++v23;
        v7 = v22;
        if ( v24 > 7 )
          v7 = (_QWORD *)v22[0];
        *(_DWORD *)((char *)v7 + 2 * v5) = 92;
      }
    }
  }
  try
  {
    std::wstring::wstring(v27, byte_1800AA3F0);
    mi::MiApplication::Create(&v18, v27);
    std::wstring::_Tidy_deallocate(v27);
    v8 = v18;
    std::wstring::wstring(v28, L"root/microsoft/windows/storage");
    mi::MiApplication::CreateSession(v8, (__int64)v16, (int)v28);
    std::wstring::_Tidy_deallocate(v28);
    v25[0] = &std::_Func_impl_no_alloc<_lambda_36c2d625613d75af49b4862ff1ce672d_,bool,srstor::MSFT_Partition const &>::`vftable';
    v25[1] = v22;
    v25[2] = v3;
    v25[3] = &v13;
    v26 = v25;
    v9 = (mi::MiAsyncOperation *)srstor::MSFT_Partition::Enumerate(v21, v16, v25);
    mi::MiAsyncOperation::Join(v9);
    mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v21);
    if ( v26 )
    {
      v10 = v25;
      LOBYTE(v10) = v26 != v25;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v26 + 32LL))(v26, v10);
    }
    v11 = 0;
    if ( !v13 )
      v11 = 6;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
  }
  catch ( std::system_error *v20 )
  {
    LODWORD(v14) = CatchErrorFromMiClient(v20, v14);
    v11 = (unsigned int)v14;
    v4 = v15;
    v3 = v15;
  }
  if ( v11 )
  {
    v3[2] = 0;
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v3;
    *(_WORD *)v4 = 0;
  }
  std::wstring::_Tidy_deallocate(v22);
  return v11;
}

```

## disassembly

```asm
0x180022ea4  mov     [rsp+arg_18], rbx
0x180022ea9  push    rsi
0x180022eaa  push    rdi
0x180022eab  push    r14
0x180022ead  sub     rsp, 180h
0x180022eb4  mov     rax, cs:__security_cookie
0x180022ebb  xor     rax, rsp
0x180022ebe  mov     [rsp+198h+var_28], rax
0x180022ec6  mov     r14, r8
0x180022ec9  mov     [rsp+198h+var_168], rdx
0x180022ece  mov     rsi, r8
0x180022ed1  mov     [rsp+198h+var_158], r8
0x180022ed6  xor     ebx, ebx
0x180022ed8  mov     rdx, rcx
0x180022edb  lea     rcx, [rsp+198h+var_D0]
0x180022ee3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022ee8  nop
0x180022ee9  mov     [rsp+198h+var_178], bl
0x180022eed  mov     rcx, [rsp+198h+var_C0]
0x180022ef5  test    rcx, rcx
0x180022ef8  jz      short loc_180022F5D
0x180022efa  mov     rdx, [rsp+198h+var_B8]
0x180022f02  lea     rax, [rsp+198h+var_D0]
0x180022f0a  cmp     rdx, 7
0x180022f0e  cmova   rax, [rsp+198h+var_D0]
0x180022f17  lea     r9d, [rbx+5Ch]
0x180022f1b  cmp     [rax+rcx*2-2], r9w
0x180022f21  jz      short loc_180022F5D
0x180022f23  cmp     rcx, rdx
0x180022f26  jnb     short loc_180022F4F
0x180022f28  lea     rax, [rcx+1]
0x180022f2c  mov     [rsp+198h+var_C0], rax
0x180022f34  lea     rax, [rsp+198h+var_D0]
0x180022f3c  cmp     rdx, 7
0x180022f40  cmova   rax, [rsp+198h+var_D0]
0x180022f49  mov     [rax+rcx*2], r9d
0x180022f4d  jmp     short loc_180022F5D
0x180022f4f  lea     rcx, [rsp+198h+var_D0]
0x180022f57  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x180022f5c  nop
0x180022f5d  lea     rdx, byte_1800AA3F0
0x180022f64  lea     rcx, [rsp+198h+var_68]
0x180022f6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022f71  nop
0x180022f72  lea     rdx, [rsp+198h+var_68]
0x180022f7a  lea     rcx, [rsp+198h+var_138]
0x180022f7f  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x180022f84  nop
0x180022f85  lea     rcx, [rsp+198h+var_68]
0x180022f8d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022f92  mov     rdi, [rsp+198h+var_138]
0x180022f97  lea     rdx, aRootMicrosoftW_0; "root/microsoft/windows/storage"
0x180022f9e  lea     rcx, [rsp+198h+var_48]
0x180022fa6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022fab  nop
0x180022fac  lea     r8, [rsp+198h+var_48]
0x180022fb4  lea     rdx, [rsp+198h+var_148]
0x180022fb9  mov     rcx, rdi
0x180022fbc  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x180022fc1  nop
0x180022fc2  lea     rcx, [rsp+198h+var_48]
0x180022fca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022fcf  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_36c2d625613d75af49b4862ff1ce672d_@@_NAEBVMSFT_Partition@srstor@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_36c2d625613d75af49b4862ff1ce672d_,bool,srstor::MSFT_Partition const &>::`vftable'
0x180022fd6  mov     [rsp+198h+var_A8], rax
0x180022fde  lea     rax, [rsp+198h+var_D0]
0x180022fe6  mov     [rsp+198h+var_A0], rax
0x180022fee  mov     [rsp+198h+var_98], r14
0x180022ff6  lea     rax, [rsp+198h+var_178]
0x180022ffb  mov     [rsp+198h+var_90], rax
0x180023003  lea     rax, [rsp+198h+var_A8]
0x18002300b  mov     [rsp+198h+var_70], rax
0x180023013  lea     r8, [rsp+198h+var_A8]
0x18002301b  lea     rdx, [rsp+198h+var_148]
0x180023020  lea     rcx, [rsp+198h+var_120]
0x180023025  call    ?Enumerate@MSFT_Partition@srstor@@SA?AVMiAsyncOperation@mi@@AEBV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$function@$$A6A_NAEBVMSFT_Partition@srstor@@@Z@6@@Z; srstor::MSFT_Partition::Enumerate(std::shared_ptr<mi::MiSession> const &,std::function<bool (srstor::MSFT_Partition const &)> const &)
0x18002302a  nop
0x18002302b  mov     rcx, rax; this
0x18002302e  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x180023033  nop
0x180023034  lea     rcx, [rsp+198h+var_120]; this
0x180023039  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18002303e  nop
0x18002303f  mov     rcx, [rsp+198h+var_70]
0x180023047  test    rcx, rcx
0x18002304a  jz      short loc_180023066
0x18002304c  mov     rax, [rcx]
0x18002304f  lea     rdx, [rsp+198h+var_A8]
0x180023057  cmp     rcx, rdx
0x18002305a  setnz   dl
0x18002305d  mov     rax, [rax+20h]
0x180023061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023066  mov     edi, ebx
0x180023068  mov     eax, 6
0x18002306d  cmp     [rsp+198h+var_178], bl
0x180023071  cmovz   edi, eax
0x180023074  mov     rcx, [rsp+198h+var_140]; this
0x180023079  test    rcx, rcx
0x18002307c  jz      short loc_180023084
0x18002307e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023083  nop
0x180023084  mov     rcx, [rsp+198h+var_130]; this
0x180023089  test    rcx, rcx
0x18002308c  jz      short loc_180023094
0x18002308e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023093  nop
0x180023094  jmp     short loc_1800230A4
0x180023096  xor     ebx, ebx
0x180023098  mov     edi, dword ptr [rsp+198h+var_168]
0x18002309c  mov     rsi, [rsp+198h+var_158]
0x1800230a1  mov     r14, rsi
0x1800230a4  test    edi, edi
0x1800230a6  jz      short loc_1800230B9
0x1800230a8  mov     [r14+10h], rbx
0x1800230ac  cmp     qword ptr [rsi+18h], 7
0x1800230b1  jbe     short loc_1800230B6
0x1800230b3  mov     rsi, [r14]
0x1800230b6  mov     [rsi], bx
0x1800230b9  lea     rcx, [rsp+198h+var_D0]
0x1800230c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800230c6  mov     eax, edi
0x1800230c8  mov     rcx, [rsp+198h+var_28]
0x1800230d0  xor     rcx, rsp; StackCookie
0x1800230d3  call    __security_check_cookie
0x1800230d8  mov     rbx, [rsp+198h+arg_18]
0x1800230e0  add     rsp, 180h
0x1800230e7  pop     r14
0x1800230e9  pop     rdi
0x1800230ea  pop     rsi
0x1800230eb  retn
```
