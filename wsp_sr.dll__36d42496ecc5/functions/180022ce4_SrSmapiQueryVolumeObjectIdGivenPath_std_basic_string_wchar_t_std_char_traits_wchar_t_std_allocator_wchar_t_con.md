# SrSmapiQueryVolumeObjectIdGivenPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CWMIContext &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180022ce4`
- end: `0x180022f2c`
- name: `?SrSmapiQueryVolumeObjectIdGivenPath@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@AEAV23@@Z`
- size: `584`
- prototype: `__int64 __fastcall(_QWORD *, struct CWMIContext *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000b98c`

## callees

- `0x1800014e0`
- `0x18000584c`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x18001a4cc`
- `0x180022ce4`
- `0x180025ea4`
- `0x180026134`
- `0x180027bbc`
- `0x1800280c0`
- `0x180029ab8`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapiQueryVolumeObjectIdGivenPath(_QWORD *a1, struct CWMIContext *a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  _QWORD *v4; // rsi
  unsigned __int64 v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rdi
  mi::MiAsyncOperation::MiOperationArgs **v9; // rcx
  enum _MI_CancellationReason v10; // edx
  _QWORD *v11; // rdx
  unsigned int v12; // edi
  char v14; // [rsp+20h] [rbp-178h] BYREF
  struct CWMIContext *v15; // [rsp+30h] [rbp-168h]
  _QWORD *v16; // [rsp+40h] [rbp-158h]
  __int64 v17; // [rsp+50h] [rbp-148h] BYREF
  std::_Ref_count_base *v18; // [rsp+58h] [rbp-140h]
  __int64 v19; // [rsp+60h] [rbp-138h] BYREF
  std::_Ref_count_base *v20; // [rsp+68h] [rbp-130h]
  std::system_error *v21; // [rsp+70h] [rbp-128h] BYREF
  _BYTE v22[80]; // [rsp+78h] [rbp-120h] BYREF
  _QWORD v23[2]; // [rsp+C8h] [rbp-D0h] BYREF
  unsigned __int64 v24; // [rsp+D8h] [rbp-C0h]
  unsigned __int64 v25; // [rsp+E0h] [rbp-B8h]
  _QWORD v26[7]; // [rsp+F0h] [rbp-A8h] BYREF
  _QWORD *v27; // [rsp+128h] [rbp-70h]
  MI_Char v28[16]; // [rsp+130h] [rbp-68h] BYREF
  _BYTE v29[32]; // [rsp+150h] [rbp-48h] BYREF

  v3 = a3;
  v15 = a2;
  v4 = a3;
  v16 = a3;
  std::wstring::wstring((__int64)v23, a1);
  v14 = 0;
  v5 = v24;
  if ( v24 )
  {
    v6 = v23;
    if ( v25 > 7 )
      v6 = (_QWORD *)v23[0];
    if ( *((_WORD *)v6 + v24 - 1) != 92 )
    {
      if ( v24 >= v25 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(v23);
      }
      else
      {
        ++v24;
        v7 = v23;
        if ( v25 > 7 )
          v7 = (_QWORD *)v23[0];
        *(_DWORD *)((char *)v7 + 2 * v5) = 92;
      }
    }
  }
  try
  {
    std::wstring::wstring((__int64)v28, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v19, v28);
    std::wstring::_Tidy_deallocate((__int64)v28);
    v8 = v19;
    std::wstring::wstring((__int64)v29, (__int64)L"root/microsoft/windows/storage");
    mi::MiApplication::CreateSession(v8, &v17, (__int64)v29);
    std::wstring::_Tidy_deallocate((__int64)v29);
    v26[0] = &std::_Func_impl_no_alloc<_lambda_36c2d625613d75af49b4862ff1ce672d_,bool,srstor::MSFT_Partition const &>::`vftable';
    v26[1] = v23;
    v26[2] = v3;
    v26[3] = &v14;
    v27 = v26;
    v9 = (mi::MiAsyncOperation::MiOperationArgs **)srstor::MSFT_Partition::Enumerate(v22, &v17, v26);
    mi::MiAsyncOperation::Join(v9);
    mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v22, v10);
    if ( v27 )
    {
      v11 = v26;
      LOBYTE(v11) = v27 != v26;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v27 + 32LL))(v27, v11);
    }
    v12 = 0;
    if ( !v14 )
      v12 = 6;
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
  }
  catch ( std::system_error *v21 )
  {
    LODWORD(v15) = CatchErrorFromMiClient(v21, v15);
    v12 = (unsigned int)v15;
    v4 = v16;
    v3 = v16;
  }
  std::wstring::wstring((__int64)v28, (__int64)byte_1800AA410);
  mi::MiApplication::Create(&v19, v28);
  std::wstring::_Tidy_deallocate((__int64)v28);
}

```

## disassembly

```asm
0x180022ce4  mov     [rsp+arg_18], rbx
0x180022ce9  push    rsi
0x180022cea  push    rdi
0x180022ceb  push    r14
0x180022ced  sub     rsp, 180h
0x180022cf4  mov     rax, cs:__security_cookie
0x180022cfb  xor     rax, rsp
0x180022cfe  mov     [rsp+198h+var_28], rax
0x180022d06  mov     r14, r8
0x180022d09  mov     [rsp+198h+var_168], rdx
0x180022d0e  mov     rsi, r8
0x180022d11  mov     [rsp+198h+var_158], r8
0x180022d16  xor     ebx, ebx
0x180022d18  mov     rdx, rcx
0x180022d1b  lea     rcx, [rsp+198h+var_D0]
0x180022d23  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022d28  nop
0x180022d29  mov     [rsp+198h+var_178], bl
0x180022d2d  mov     rcx, [rsp+198h+var_C0]
0x180022d35  test    rcx, rcx
0x180022d38  jz      short loc_180022D9D
0x180022d3a  mov     rdx, [rsp+198h+var_B8]
0x180022d42  lea     rax, [rsp+198h+var_D0]
0x180022d4a  cmp     rdx, 7
0x180022d4e  cmova   rax, [rsp+198h+var_D0]
0x180022d57  lea     r9d, [rbx+5Ch]
0x180022d5b  cmp     [rax+rcx*2-2], r9w
0x180022d61  jz      short loc_180022D9D
0x180022d63  cmp     rcx, rdx
0x180022d66  jnb     short loc_180022D8F
0x180022d68  lea     rax, [rcx+1]
0x180022d6c  mov     [rsp+198h+var_C0], rax
0x180022d74  lea     rax, [rsp+198h+var_D0]
0x180022d7c  cmp     rdx, 7
0x180022d80  cmova   rax, [rsp+198h+var_D0]
0x180022d89  mov     [rax+rcx*2], r9d
0x180022d8d  jmp     short loc_180022D9D
0x180022d8f  lea     rcx, [rsp+198h+var_D0]
0x180022d97  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x180022d9c  nop
0x180022d9d  lea     rdx, byte_1800AA410
0x180022da4  lea     rcx, [rsp+198h+var_68]
0x180022dac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022db1  nop
0x180022db2  lea     rdx, [rsp+198h+var_68]
0x180022dba  lea     rcx, [rsp+198h+var_138]
0x180022dbf  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x180022dc4  nop
0x180022dc5  lea     rcx, [rsp+198h+var_68]
0x180022dcd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022dd2  mov     rdi, [rsp+198h+var_138]
0x180022dd7  lea     rdx, aRootMicrosoftW_0; "root/microsoft/windows/storage"
0x180022dde  lea     rcx, [rsp+198h+var_48]
0x180022de6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022deb  nop
0x180022dec  lea     r8, [rsp+198h+var_48]
0x180022df4  lea     rdx, [rsp+198h+var_148]
0x180022df9  mov     rcx, rdi
0x180022dfc  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x180022e01  nop
0x180022e02  lea     rcx, [rsp+198h+var_48]
0x180022e0a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022e0f  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_36c2d625613d75af49b4862ff1ce672d_@@_NAEBVMSFT_Partition@srstor@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_36c2d625613d75af49b4862ff1ce672d_,bool,srstor::MSFT_Partition const &>::`vftable'
0x180022e16  mov     [rsp+198h+var_A8], rax
0x180022e1e  lea     rax, [rsp+198h+var_D0]
0x180022e26  mov     [rsp+198h+var_A0], rax
0x180022e2e  mov     [rsp+198h+var_98], r14
0x180022e36  lea     rax, [rsp+198h+var_178]
0x180022e3b  mov     [rsp+198h+var_90], rax
0x180022e43  lea     rax, [rsp+198h+var_A8]
0x180022e4b  mov     [rsp+198h+var_70], rax
0x180022e53  lea     r8, [rsp+198h+var_A8]
0x180022e5b  lea     rdx, [rsp+198h+var_148]
0x180022e60  lea     rcx, [rsp+198h+var_120]
0x180022e65  call    ?Enumerate@MSFT_Partition@srstor@@SA?AVMiAsyncOperation@mi@@AEBV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$function@$$A6A_NAEBVMSFT_Partition@srstor@@@Z@6@@Z; srstor::MSFT_Partition::Enumerate(std::shared_ptr<mi::MiSession> const &,std::function<bool (srstor::MSFT_Partition const &)> const &)
0x180022e6a  nop
0x180022e6b  mov     rcx, rax; this
0x180022e6e  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x180022e73  nop
0x180022e74  lea     rcx, [rsp+198h+var_120]; this
0x180022e79  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x180022e7e  nop
0x180022e7f  mov     rcx, [rsp+198h+var_70]
0x180022e87  test    rcx, rcx
0x180022e8a  jz      short loc_180022EA6
0x180022e8c  mov     rax, [rcx]
0x180022e8f  lea     rdx, [rsp+198h+var_A8]
0x180022e97  cmp     rcx, rdx
0x180022e9a  setnz   dl
0x180022e9d  mov     rax, [rax+20h]
0x180022ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ea6  mov     edi, ebx
0x180022ea8  mov     eax, 6
0x180022ead  cmp     [rsp+198h+var_178], bl
0x180022eb1  cmovz   edi, eax
0x180022eb4  mov     rcx, [rsp+198h+var_140]; this
0x180022eb9  test    rcx, rcx
0x180022ebc  jz      short loc_180022EC4
0x180022ebe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022ec3  nop
0x180022ec4  mov     rcx, [rsp+198h+var_130]; this
0x180022ec9  test    rcx, rcx
0x180022ecc  jz      short loc_180022ED4
0x180022ece  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022ed3  nop
0x180022ed4  jmp     short loc_180022EE4
0x180022ed6  xor     ebx, ebx
0x180022ed8  mov     edi, dword ptr [rsp+198h+var_168]
0x180022edc  mov     rsi, [rsp+198h+var_158]
0x180022ee1  mov     r14, rsi
0x180022ee4  test    edi, edi
0x180022ee6  jz      short loc_180022EF9
0x180022ee8  mov     [r14+10h], rbx
0x180022eec  cmp     qword ptr [rsi+18h], 7
0x180022ef1  jbe     short loc_180022EF6
0x180022ef3  mov     rsi, [r14]
0x180022ef6  mov     [rsi], bx
0x180022ef9  lea     rcx, [rsp+198h+var_D0]
0x180022f01  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022f06  mov     eax, edi
0x180022f08  mov     rcx, [rsp+198h+var_28]
0x180022f10  xor     rcx, rsp; StackCookie
0x180022f13  call    __security_check_cookie
0x180022f18  mov     rbx, [rsp+198h+arg_18]
0x180022f20  add     rsp, 180h
0x180022f27  pop     r14
0x180022f29  pop     rdi
0x180022f2a  pop     rsi
0x180022f2b  retn
```
