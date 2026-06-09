# SrSmapiQueryPartitionAccessPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,CWMIContext &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18002295c`
- end: `0x180022b19`
- name: `?SrSmapiQueryPartitionAccessPath@@YA?AW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCWMIContext@@AEAV23@@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64, struct CWMIContext *, _QWORD *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000c0a8`
- `0x18001ba4c`
- `0x18001bc4c`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800065ec`
- `0x1800066d8`
- `0x18002295c`
- `0x180025ea4`
- `0x180026134`
- `0x180027bbc`
- `0x1800280c0`
- `0x180029ab8`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SrSmapiQueryPartitionAccessPath(__int64 a1, struct CWMIContext *a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  _QWORD *v5; // rsi
  __int64 v6; // rdi
  mi::MiAsyncOperation::MiOperationArgs **v7; // rcx
  enum _MI_CancellationReason v8; // edx
  _QWORD *v9; // rdx
  unsigned int v10; // edi
  char v12; // [rsp+20h] [rbp-158h] BYREF
  struct CWMIContext *v13; // [rsp+30h] [rbp-148h]
  _QWORD *v14; // [rsp+40h] [rbp-138h]
  __int64 v15; // [rsp+50h] [rbp-128h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-120h]
  __int64 v17; // [rsp+60h] [rbp-118h] BYREF
  std::_Ref_count_base *v18; // [rsp+68h] [rbp-110h]
  std::system_error *v19; // [rsp+70h] [rbp-108h] BYREF
  _BYTE v20[88]; // [rsp+78h] [rbp-100h] BYREF
  _QWORD v21[7]; // [rsp+D0h] [rbp-A8h] BYREF
  _QWORD *v22; // [rsp+108h] [rbp-70h]
  MI_Char v23[16]; // [rsp+110h] [rbp-68h] BYREF
  _BYTE v24[32]; // [rsp+130h] [rbp-48h] BYREF

  try
  {
    v3 = a3;
    v13 = a2;
    v5 = a3;
    v14 = a3;
    std::wstring::wstring((__int64)v23, (__int64)byte_1800AA410);
    mi::MiApplication::Create(&v17, v23);
    std::wstring::_Tidy_deallocate((__int64)v23);
    v6 = v17;
    std::wstring::wstring((__int64)v24, (__int64)L"root/microsoft/windows/storage");
    mi::MiApplication::CreateSession(v6, &v15, (__int64)v24);
    std::wstring::_Tidy_deallocate((__int64)v24);
    v12 = 0;
    v21[0] = &std::_Func_impl_no_alloc<_lambda_e78de86cc8a8661442aa672103284202_,bool,srstor::MSFT_Partition const &>::`vftable';
    v21[1] = a1;
    v21[2] = v5;
    v21[3] = &v12;
    v22 = v21;
    v7 = (mi::MiAsyncOperation::MiOperationArgs **)srstor::MSFT_Partition::Enumerate(v20, &v15, v21);
    mi::MiAsyncOperation::Join(v7);
    mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v20, v8);
    if ( v22 )
    {
      v9 = v21;
      LOBYTE(v9) = v22 != v21;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v22 + 32LL))(v22, v9);
    }
    v10 = 0;
    if ( !v12 )
      v10 = 6;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
  }
  catch ( std::system_error *v19 )
  {
    LODWORD(v13) = CatchErrorFromMiClient(v19, v13);
    v10 = (unsigned int)v13;
    v5 = v14;
    v3 = v14;
  }
  v3 = a3;
  v13 = a2;
}

```

## disassembly

```asm
0x18002295c  mov     r11, rsp
0x18002295f  mov     [r11+8], rbx
0x180022963  mov     [r11+20h], rsi
0x180022967  push    rdi
0x180022968  push    r14
0x18002296a  push    r15
0x18002296c  sub     rsp, 160h
0x180022973  mov     rax, cs:__security_cookie
0x18002297a  xor     rax, rsp
0x18002297d  mov     [rsp+178h+var_28], rax
0x180022985  mov     r14, r8
0x180022988  mov     r15, rcx
0x18002298b  mov     [rsp+178h+var_148], rdx
0x180022990  mov     rsi, r8
0x180022993  mov     [rsp+178h+var_138], r8
0x180022998  xor     ebx, ebx
0x18002299a  lea     rdx, byte_1800AA410
0x1800229a1  lea     rcx, [r11-68h]
0x1800229a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800229aa  nop
0x1800229ab  lea     rdx, [rsp+178h+var_68]
0x1800229b3  lea     rcx, [rsp+178h+var_118]
0x1800229b8  call    ?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::Create(std::wstring const &)
0x1800229bd  nop
0x1800229be  lea     rcx, [rsp+178h+var_68]
0x1800229c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800229cb  mov     rdi, [rsp+178h+var_118]
0x1800229d0  lea     rdx, aRootMicrosoftW_0; "root/microsoft/windows/storage"
0x1800229d7  lea     rcx, [rsp+178h+var_48]
0x1800229df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800229e4  nop
0x1800229e5  lea     r8, [rsp+178h+var_48]
0x1800229ed  lea     rdx, [rsp+178h+var_128]
0x1800229f2  mov     rcx, rdi
0x1800229f5  call    ?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; mi::MiApplication::CreateSession(std::wstring const &)
0x1800229fa  nop
0x1800229fb  lea     rcx, [rsp+178h+var_48]
0x180022a03  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a08  mov     [rsp+178h+var_158], bl
0x180022a0c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e78de86cc8a8661442aa672103284202_@@_NAEBVMSFT_Partition@srstor@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e78de86cc8a8661442aa672103284202_,bool,srstor::MSFT_Partition const &>::`vftable'
0x180022a13  mov     [rsp+178h+var_A8], rax
0x180022a1b  mov     [rsp+178h+var_A0], r15
0x180022a23  mov     [rsp+178h+var_98], rsi
0x180022a2b  lea     rax, [rsp+178h+var_158]
0x180022a30  mov     [rsp+178h+var_90], rax
0x180022a38  lea     rax, [rsp+178h+var_A8]
0x180022a40  mov     [rsp+178h+var_70], rax
0x180022a48  lea     r8, [rsp+178h+var_A8]
0x180022a50  lea     rdx, [rsp+178h+var_128]
0x180022a55  lea     rcx, [rsp+178h+var_100]
0x180022a5a  call    ?Enumerate@MSFT_Partition@srstor@@SA?AVMiAsyncOperation@mi@@AEBV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$function@$$A6A_NAEBVMSFT_Partition@srstor@@@Z@6@@Z; srstor::MSFT_Partition::Enumerate(std::shared_ptr<mi::MiSession> const &,std::function<bool (srstor::MSFT_Partition const &)> const &)
0x180022a5f  nop
0x180022a60  mov     rcx, rax; this
0x180022a63  call    ?Join@MiAsyncOperation@mi@@QEAAXXZ; mi::MiAsyncOperation::Join(void)
0x180022a68  nop
0x180022a69  lea     rcx, [rsp+178h+var_100]; this
0x180022a6e  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x180022a73  nop
0x180022a74  mov     rcx, [rsp+178h+var_70]
0x180022a7c  test    rcx, rcx
0x180022a7f  jz      short loc_180022A9B
0x180022a81  mov     rax, [rcx]
0x180022a84  lea     rdx, [rsp+178h+var_A8]
0x180022a8c  cmp     rcx, rdx
0x180022a8f  setnz   dl
0x180022a92  mov     rax, [rax+20h]
0x180022a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a9b  mov     edi, ebx
0x180022a9d  mov     eax, 6
0x180022aa2  cmp     [rsp+178h+var_158], bl
0x180022aa6  cmovz   edi, eax
0x180022aa9  mov     rcx, [rsp+178h+var_120]; this
0x180022aae  test    rcx, rcx
0x180022ab1  jz      short loc_180022AB9
0x180022ab3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022ab8  nop
0x180022ab9  mov     rcx, [rsp+178h+var_110]; this
0x180022abe  test    rcx, rcx
0x180022ac1  jz      short loc_180022AC9
0x180022ac3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022ac8  nop
0x180022ac9  jmp     short loc_180022AD9
0x180022acb  xor     ebx, ebx
0x180022acd  mov     edi, dword ptr [rsp+178h+var_148]
0x180022ad1  mov     rsi, [rsp+178h+var_138]
0x180022ad6  mov     r14, rsi
0x180022ad9  test    edi, edi
0x180022adb  jz      short loc_180022AEE
0x180022add  mov     [r14+10h], rbx
0x180022ae1  cmp     qword ptr [rsi+18h], 7
0x180022ae6  jbe     short loc_180022AEB
0x180022ae8  mov     rsi, [r14]
0x180022aeb  mov     [rsi], bx
0x180022aee  mov     eax, edi
0x180022af0  mov     rcx, [rsp+178h+var_28]
0x180022af8  xor     rcx, rsp; StackCookie
0x180022afb  call    __security_check_cookie
0x180022b00  lea     r11, [rsp+178h+var_18]
0x180022b08  mov     rbx, [r11+20h]
0x180022b0c  mov     rsi, [r11+38h]
0x180022b10  mov     rsp, r11
0x180022b13  pop     r15
0x180022b15  pop     r14
0x180022b17  pop     rdi
0x180022b18  retn
```
