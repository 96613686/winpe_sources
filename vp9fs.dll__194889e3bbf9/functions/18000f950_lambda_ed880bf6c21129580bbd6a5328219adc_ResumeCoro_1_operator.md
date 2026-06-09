# _lambda_ed880bf6c21129580bbd6a5328219adc_$_ResumeCoro$1::operator()

- ea: `0x18000f950`
- end: `0x18000fbb8`
- name: `_lambda_ed880bf6c21129580bbd6a5328219adc_$_ResumeCoro$1::operator()`
- size: `616`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180004144`
- `0x180004534`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000dedc`
- `0x18000e23c`
- `0x18000e45c`
- `0x18000e930`
- `0x18000f950`
- `0x18001c7e0`
- `0x18001c924`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000fade`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000fade`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000fa31`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000fa31`

## string_xrefs

- `0x18000faa4`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18000fb1c`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall lambda_ed880bf6c21129580bbd6a5328219adc___ResumeCoro_1::operator()(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  char *v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  __int64 v11; // rax
  const struct std::exception_ptr *v12; // rbx
  __int64 v13; // rdx
  const char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // [rsp+20h] [rbp-C8h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  switch ( *((_WORD *)a1 + 4) )
  {
    case 0xFFFF:
    case 3:
      goto LABEL_16;
    case 2:
      v5 = (char *)operator new(0x300u) + 32;
      a1[3] = v5;
      *((_QWORD *)v5 + 91) = a1 + 108;
      *(_QWORD *)a1[3] = lambda_27c81364226c014e40805797043135a3___ResumeCoro_1::operator();
      *(_DWORD *)(a1[3] + 8LL) = 65538;
      v6 = a1[3];
      *(_OWORD *)(v6 - 32) = 0;
      *(_OWORD *)(v6 - 16) = 0;
      v17 = a1[3];
      *(_QWORD *)(v17 - 32) = 0;
      *(_BYTE *)(v17 - 24) = 0;
      v7 = (_QWORD *)(v17 - 16);
      *v7 = 0;
      v7[1] = 0;
      __ExceptionPtrCreate((void *)(v17 - 16));
      a1[2] = v6;
      *(_BYTE *)(a1[3] + 720LL) = 0;
      lambda_27c81364226c014e40805797043135a3___ResumeCoro_1::operator()(a1[3], v8, v9, v10);
      if ( !*(_BYTE *)(a1[2] - 24LL) )
      {
        *((_WORD *)a1 + 4) = 4;
        if ( (unsigned __int8)p9fs::Task<void>::await_suspend(a1 + 2, a1) )
          return;
      }
      goto LABEL_10;
    case 4:
LABEL_10:
      v12 = (const struct std::exception_ptr *)(a1[2] - 16LL);
      if ( __ExceptionPtrToBool(v12) )
      {
        v15 = std::exception_ptr::exception_ptr((std::exception_ptr *)(a1 + 104), v12);
        std::rethrow_exception(v15);
      }
      v16 = a1[2];
      if ( v16 )
      {
        if ( *(_WORD *)(v16 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v14);
        *(_QWORD *)(v16 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD, __int64))v16)(a1[2], v13);
      }
      goto LABEL_16;
    case 5:
      v11 = a1[2];
      if ( v11 )
      {
        if ( *(_WORD *)(v11 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v11 + 8) |= 1uLL;
        (*(void (**)(void))v11)();
      }
LABEL_16:
      p9fs::Handler::RequestTracker::~RequestTracker((p9fs::Handler::RequestTracker *)(a1 + 114));
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 111);
      wil::details::lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>::~lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>(a1 + 109);
      if ( *((_WORD *)a1 + 5) )
        operator delete(a1, 0x3C0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18000f950  mov     rax, rsp
0x18000f953  mov     [rax+10h], rbx
0x18000f957  mov     [rax+18h], rsi
0x18000f95b  mov     [rax+8], rcx
0x18000f95f  push    rdi
0x18000f960  push    r14
0x18000f962  push    r15
0x18000f964  sub     rsp, 0D0h
0x18000f96b  mov     rdi, rcx
0x18000f96e  mov     [rsp+0E8h+var_B0], rcx
0x18000f973  movzx   eax, word ptr [rdi+8]
0x18000f977  mov     [rsp+0E8h+var_B8], ax
0x18000f97c  mov     r15d, 1
0x18000f982  add     ax, r15w
0x18000f986  cmp     ax, 6; switch 7 cases
0x18000f98a  ja      def_18000F9A5; jumptable 000000018000F9A5 default case, cases 1,2
0x18000f990  movsx   rax, ax
0x18000f994  lea     rdx, cs:180000000h
0x18000f99b  mov     ecx, ds:(jpt_18000F9A5 - 180000000h)[rdx+rax*4]
0x18000f9a2  add     rcx, rdx
0x18000f9a5  jmp     rcx; switch jump
0x18000f9a7  xor     esi, esi; jumptable 000000018000F9A5 case 4
0x18000f9a9  jmp     loc_18000FB48
0x18000f9ae  mov     ecx, 300h; jumptable 000000018000F9A5 case 3
0x18000f9b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f9b8  lea     r14, [rdi+10h]
0x18000f9bc  lea     rcx, [r14+350h]
0x18000f9c3  mov     [rsp+0E8h+var_C8], rax
0x18000f9c8  add     rax, 20h ; ' '
0x18000f9cc  mov     [rdi+18h], rax
0x18000f9d0  mov     [rsp+0E8h+var_C8], rax
0x18000f9d5  mov     [rax+2D8h], rcx
0x18000f9dc  mov     rax, [rdi+18h]
0x18000f9e0  mov     [rsp+0E8h+var_C8], rax
0x18000f9e5  lea     rcx, _lambda_27c81364226c014e40805797043135a3_$_ResumeCoro$1__operator__
0x18000f9ec  mov     [rax], rcx
0x18000f9ef  mov     rax, [rdi+18h]
0x18000f9f3  mov     [rsp+0E8h+var_C8], rax
0x18000f9f8  mov     dword ptr [rax+8], 10002h
0x18000f9ff  mov     rbx, [rdi+18h]
0x18000fa03  mov     [rsp+0E8h+var_C8], rbx
0x18000fa08  xorps   xmm0, xmm0
0x18000fa0b  movups  xmmword ptr [rbx-20h], xmm0
0x18000fa0f  movups  xmmword ptr [rbx-10h], xmm0
0x18000fa13  mov     rcx, [rdi+18h]
0x18000fa17  mov     [rsp+0E8h+var_C8], rcx
0x18000fa1c  xor     esi, esi
0x18000fa1e  mov     [rcx-20h], rsi
0x18000fa22  mov     [rcx-18h], sil
0x18000fa26  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000fa2a  mov     [rcx], rsi
0x18000fa2d  mov     [rcx+8], rsi
0x18000fa31  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000fa37  nop
0x18000fa38  mov     [r14], rbx
0x18000fa3b  mov     rax, [rdi+18h]
0x18000fa3f  mov     [rsp+0E8h+var_C8], rax
0x18000fa44  xor     ecx, ecx
0x18000fa46  mov     [rax+2D0h], cl
0x18000fa4c  mov     rcx, [rdi+18h]
0x18000fa50  mov     [rsp+0E8h+var_C8], rcx
0x18000fa55  call    _lambda_27c81364226c014e40805797043135a3_$_ResumeCoro$1__operator__
0x18000fa5a  nop
0x18000fa5b  mov     rax, [r14]
0x18000fa5e  mov     [rsp+0E8h+var_C0], rax
0x18000fa63  mov     dl, [rax-18h]
0x18000fa66  nop
0x18000fa67  test    dl, dl
0x18000fa69  jnz     short loc_18000FACE
0x18000fa6b  lea     eax, [rsi+4]
0x18000fa6e  mov     [rdi+8], ax
0x18000fa72  mov     rdx, rdi
0x18000fa75  mov     rcx, r14
0x18000fa78  call    ?await_suspend@?$Task@X@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<void>::await_suspend(std::experimental::coroutine_handle<void>)
0x18000fa7d  test    al, al
0x18000fa7f  jz      short loc_18000FACE
0x18000fa81  jmp     loc_18000FB82
0x18000fa86  mov     rax, [rdi+10h]; jumptable 000000018000F9A5 case 6
0x18000fa8a  mov     [rsp+0E8h+var_C0], rax
0x18000fa8f  xor     esi, esi
0x18000fa91  test    rax, rax
0x18000fa94  jz      short loc_18000FACA
0x18000fa96  mov     rcx, [rsp+0E8h]; this
0x18000fa9e  cmp     [rax+8], si
0x18000faa2  jz      short loc_18000FAB4
0x18000faa4  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000faab  lea     edx, [rsi+34h]; void *
0x18000faae  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000fab4  or      [rax+8], r15
0x18000fab8  mov     rax, [rax]
0x18000fabb  mov     rcx, [rdi+10h]
0x18000fabf  mov     [rsp+0E8h+var_C0], rcx
0x18000fac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fac9  nop
0x18000faca  jmp     short loc_18000FB48
0x18000facc  xor     esi, esi; jumptable 000000018000F9A5 case 5
0x18000face  mov     rax, [rdi+10h]
0x18000fad2  mov     [rsp+0E8h+var_C0], rax
0x18000fad7  lea     rbx, [rax-10h]
0x18000fadb  mov     rcx, rbx
0x18000fade  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000fae4  test    al, al
0x18000fae6  jz      short loc_18000FB00
0x18000fae8  lea     rcx, [rdi+340h]; this
0x18000faef  mov     rdx, rbx; struct std::exception_ptr *
0x18000faf2  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x18000faf7  mov     rcx, rax
0x18000fafa  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18000fb00  mov     rax, [rdi+10h]
0x18000fb04  mov     [rsp+0E8h+var_C0], rax
0x18000fb09  test    rax, rax
0x18000fb0c  jz      short loc_18000FB44
0x18000fb0e  mov     rcx, [rsp+0E8h]; this
0x18000fb16  cmp     [rax+8], si
0x18000fb1a  jz      short loc_18000FB2E
0x18000fb1c  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000fb23  mov     edx, 34h ; '4'; void *
0x18000fb28  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000fb2e  or      [rax+8], r15
0x18000fb32  mov     rax, [rax]
0x18000fb35  mov     rcx, [rdi+10h]
0x18000fb39  mov     [rsp+0E8h+var_C0], rcx
0x18000fb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb43  nop
0x18000fb44  jmp     short loc_18000FB48
0x18000fb46  xor     esi, esi; jumptable 000000018000F9A5 case 0
0x18000fb48  lea     rcx, [rdi+390h]; this
0x18000fb4f  call    ??1RequestTracker@Handler@p9fs@@QEAA@XZ; p9fs::Handler::RequestTracker::~RequestTracker(void)
0x18000fb54  lea     rcx, [rdi+378h]
0x18000fb5b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000fb60  lea     rcx, [rdi+368h]
0x18000fb67  call    ??1?$lambda_call@V_lambda_38114c5ce917be83d17d394d1d91bf81_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>::~lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>(void)
0x18000fb6c  cmp     [rdi+0Ah], si
0x18000fb70  jz      short loc_18000FB82
0x18000fb72  mov     edx, 3C0h; unsigned __int64
0x18000fb77  mov     rcx, rdi; void *
0x18000fb7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fb7f  jmp     short loc_18000FB82
0x18000fb81  int     3; Trap to Debugger
0x18000fb82  lea     r11, [rsp+0E8h+var_18]
0x18000fb8a  mov     rbx, [r11+28h]
0x18000fb8e  mov     rsi, [r11+30h]
0x18000fb92  mov     rsp, r11
0x18000fb95  pop     r15
0x18000fb97  pop     r14
0x18000fb99  pop     rdi
0x18000fb9a  retn
```
