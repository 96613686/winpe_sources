# SrSmapiQueryPartitionAccessPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CWMIContext &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180022b1c`
- end: `0x180022cda`
- name: `?SrSmapiQueryPartitionAccessPath@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@AEAV23@@Z`
- size: `446`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000c13c`
- `0x18001babc`
- `0x18001bcbc`

## callees

- `0x1800014e0`
- `0x1800058c8`
- `0x180006630`
- `0x180006724`
- `0x180022b1c`
- `0x1800261d4`
- `0x180026470`
- `0x180027f54`
- `0x180028488`
- `0x180029f64`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SrSmapiQueryPartitionAccessPath(__int64 a1, struct CWMIContext *a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  _QWORD *v5; // rsi
  int v6; // edi
  mi::MiAsyncOperation *v7; // rcx
  _QWORD *v8; // rdx
  unsigned int v9; // edi
  char v11; // [rsp+20h] [rbp-158h] BYREF
  struct CWMIContext *v12; // [rsp+30h] [rbp-148h]
  _QWORD *v13; // [rsp+40h] [rbp-138h]
  char v14[8]; // [rsp+50h] [rbp-128h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-120h]
  __int64 v16; // [rsp+60h] [rbp-118h] BYREF
  std::_Ref_count_base *v17; // [rsp+68h] [rbp-110h]
  std::system_error *v18; // [rsp+70h] [rbp-108h] BYREF
  _BYTE v19[88]; // [rsp+78h] [rbp-100h] BYREF
  _QWORD v20[7]; // [rsp+D0h] [rbp-A8h] BYREF
  _QWORD *v21; // [rsp+108h] [rbp-70h]
  MI_Char v22[16]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v23[32]; // [rsp+130h] [rbp-48h] BYREF

  try
  {
    v3 = a3;
    v12 = a2;
    v5 = a3;
    v13 = a3;
    std::wstring::wstring(v22, byte_1800AA3F0);
    mi::MiApplication::Create(&v16, v22);
    std::wstring::_Tidy_deallocate(v22);
    v6 = v16;
    std::wstring::wstring(v23, L"root/microsoft/windows/storage");
    mi::MiApplication::CreateSession(v6, (__int64)v14, (int)v23);
    std::wstring::_Tidy_deallocate(v23);
    v11 = 0;
    v20[0] = &std::_Func_impl_no_alloc<_lambda_e78de86cc8a8661442aa672103284202_,bool,srstor::MSFT_Partition const &>::`vftable';
    v20[1] = a1;
    v20[2] = v5;
    v20[3] = &v11;
    v21 = v20;
    v7 = (mi::MiAsyncOperation *)srstor::MSFT_Partition::Enumerate(v19, v14, v20);
    mi::MiAsyncOperation::Join(v7);
    mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v19);
    if ( v21 )
    {
      v8 = v20;
      LOBYTE(v8) = v21 != v20;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v8);
    }
    v9 = 0;
    if ( !v11 )
      v9 = 6;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
  }
  catch ( std::system_error *v18 )
  {
    LODWORD(v12) = CatchErrorFromMiClient(v18, v12);
    v9 = (unsigned int)v12;
    v5 = v13;
    v3 = v13;
  }
  if ( v9 )
  {
    v3[2] = 0;
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v3;
    *(_WORD *)v5 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180022b1c  mov     r11, rsp
0x180022b1f  mov     [r11+8], rbx
0x180022b23  mov     [r11+20h], rsi
0x180022b27  push    rdi
0x180022b28  push    r14
0x180022b2a  push    r15
0x180022b2c  sub     rsp, 160h
0x180022b33  mov     rax, cs:__security_cookie
0x180022b3a  xor     rax, rsp
0x180022b3d  mov     [rsp+178h+var_28], rax
0x180022b45  mov     r14, r8
0x180022b48  mov     r15, rcx
0x180022b4b  mov     [rsp+178h+var_148], rdx
0x180022b50  mov     rsi, r8
0x180022b53  mov     [rsp+178h+var_138], r8
0x180022b58  xor     ebx, ebx
0x180022b5a  lea     rdx, byte_1800AA3F0
0x180022b61  lea     rcx, [r11-68h]
0x180022b65  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022b6a  nop
0x180022b6b  lea     rdx, [rsp+178h+var_68]
0x180022b73  lea     rcx, [rsp+178h+var_118]
0x180022b78  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x180022b7d  nop
0x180022b7e  lea     rcx, [rsp+178h+var_68]
0x180022b86  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b8b  mov     rdi, [rsp+178h+var_118]
0x180022b90  lea     rdx, aRootMicrosoftW_0; "root/microsoft/windows/storage"
0x180022b97  lea     rcx, [rsp+178h+var_48]
0x180022b9f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180022ba4  nop
0x180022ba5  lea     r8, [rsp+178h+var_48]
0x180022bad  lea     rdx, [rsp+178h+var_128]
0x180022bb2  mov     rcx, rdi
0x180022bb5  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x180022bba  nop
0x180022bbb  lea     rcx, [rsp+178h+var_48]
0x180022bc3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022bc8  mov     [rsp+178h+var_158], bl
0x180022bcc  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e78de86cc8a8661442aa672103284202_@@_NAEBVMSFT_Partition@srstor@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e78de86cc8a8661442aa672103284202_,bool,srstor::MSFT_Partition const &>::`vftable'
0x180022bd3  mov     [rsp+178h+var_A8], rax
0x180022bdb  mov     [rsp+178h+var_A0], r15
0x180022be3  mov     [rsp+178h+var_98], rsi
0x180022beb  lea     rax, [rsp+178h+var_158]
0x180022bf0  mov     [rsp+178h+var_90], rax
0x180022bf8  lea     rax, [rsp+178h+var_A8]
0x180022c00  mov     [rsp+178h+var_70], rax
0x180022c08  lea     r8, [rsp+178h+var_A8]
0x180022c10  lea     rdx, [rsp+178h+var_128]
0x180022c15  lea     rcx, [rsp+178h+var_100]
0x180022c1a  call    ?Enumerate@MSFT_Partition@srstor@@SA?AVMiAsyncOperation@mi@@AEBV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$function@$$A6A_NAEBVMSFT_Partition@srstor@@@Z@6@@Z; srstor::MSFT_Partition::Enumerate(std::shared_ptr<mi::MiSession> const &,std::function<bool (srstor::MSFT_Partition const &)> const &)
0x180022c1f  nop
0x180022c20  mov     rcx, rax; this
0x180022c23  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x180022c28  nop
0x180022c29  lea     rcx, [rsp+178h+var_100]; this
0x180022c2e  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x180022c33  nop
0x180022c34  mov     rcx, [rsp+178h+var_70]
0x180022c3c  test    rcx, rcx
0x180022c3f  jz      short loc_180022C5B
0x180022c41  mov     rax, [rcx]
0x180022c44  lea     rdx, [rsp+178h+var_A8]
0x180022c4c  cmp     rcx, rdx
0x180022c4f  setnz   dl
0x180022c52  mov     rax, [rax+20h]
0x180022c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c5b  mov     edi, ebx
0x180022c5d  mov     eax, 6
0x180022c62  cmp     [rsp+178h+var_158], bl
0x180022c66  cmovz   edi, eax
0x180022c69  mov     rcx, [rsp+178h+var_120]; this
0x180022c6e  test    rcx, rcx
0x180022c71  jz      short loc_180022C79
0x180022c73  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022c78  nop
0x180022c79  mov     rcx, [rsp+178h+var_110]; this
0x180022c7e  test    rcx, rcx
0x180022c81  jz      short loc_180022C89
0x180022c83  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022c88  nop
0x180022c89  jmp     short loc_180022C99
0x180022c8b  xor     ebx, ebx
0x180022c8d  mov     edi, dword ptr [rsp+178h+var_148]
0x180022c91  mov     rsi, [rsp+178h+var_138]
0x180022c96  mov     r14, rsi
0x180022c99  test    edi, edi
0x180022c9b  jz      short loc_180022CAE
0x180022c9d  mov     [r14+10h], rbx
0x180022ca1  cmp     qword ptr [rsi+18h], 7
0x180022ca6  jbe     short loc_180022CAB
0x180022ca8  mov     rsi, [r14]
0x180022cab  mov     [rsi], bx
0x180022cae  mov     eax, edi
0x180022cb0  mov     rcx, [rsp+178h+var_28]
0x180022cb8  xor     rcx, rsp; StackCookie
0x180022cbb  call    __security_check_cookie
0x180022cc0  lea     r11, [rsp+178h+var_18]
0x180022cc8  mov     rbx, [r11+20h]
0x180022ccc  mov     rsi, [r11+38h]
0x180022cd0  mov     rsp, r11
0x180022cd3  pop     r15
0x180022cd5  pop     r14
0x180022cd7  pop     rdi
0x180022cd8  retn
```
