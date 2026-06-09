# _lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1::operator()

- ea: `0x18000ef00`
- end: `0x18000f2c8`
- name: `_lambda_3d5f3bee0032f150f7b5c906833347cc_$_ResumeCoro$1::operator()`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18000ec20`

## callees

- `0x180004120`
- `0x180004534`
- `0x180004c80`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000d498`
- `0x18000d5d8`
- `0x18000e23c`
- `0x18000ef00`
- `0x180017a44`
- `0x18001c7e0`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000f25e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000f25e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000f215`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000f215`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000f121`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000f121`

## string_xrefs

- `0x18000f0c7`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18000f160`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall lambda_3d5f3bee0032f150f7b5c906833347cc___ResumeCoro_1::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _WORD *v5; // r14
  __int64 v6; // r13
  gsl::details **v7; // rsi
  __int64 *v8; // r15
  __int64 *v9; // r12
  gsl::details *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int64 *v13; // r9
  unsigned __int64 v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rsi
  const char *v18; // r9
  std::exception_ptr *v19; // rcx
  __int64 v20; // rax
  char *v21; // rsi
  __int64 v22; // rdx
  char *v23; // r15
  char *v24; // rax
  size_t v25; // rsi
  __int64 v26; // rcx
  __int64 v27; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v5 = (_WORD *)(a1 + 8);
  v6 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_36;
    case 2:
      v7 = (gsl::details **)(a1 + 16);
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      v8 = (__int64 *)(a1 + 40);
      *(_OWORD *)(a1 + 40) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      v9 = *(__int64 **)(a1 + 200);
      v10 = (gsl::details *)v9[1];
      v11 = v9[2] - (_QWORD)v10;
      if ( v11 == -1 || !v10 && v11 )
        goto LABEL_14;
      *v8 = v11;
      *(_QWORD *)(a1 + 48) = v10;
      *(_QWORD *)(a1 + 56) = 0;
      v12 = v9[7];
      if ( v12 )
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1 + 16, v12);
      v13 = (unsigned __int64 *)(a1 + 64);
      *(_OWORD *)(a1 + 64) = 0;
      *(_OWORD *)(a1 + 80) = 0;
      *(_OWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 112) = 0;
      v10 = *v7;
      v14 = *(_QWORD *)(a1 + 24) - (_QWORD)*v7;
      if ( v14 == -1 || !v10 && v14 )
        goto LABEL_14;
      *v13 = v14;
      *(_QWORD *)(a1 + 72) = v10;
      *(_QWORD *)(a1 + 80) = 0;
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 104) = 0;
      *(_BYTE *)(a1 + 112) = 0;
      if ( v14 < 7 )
LABEL_14:
        gsl::details::terminate(v10);
      *(_QWORD *)(a1 + 80) = 7;
      v15 = p9fs::Handler::ProcessMessage(*v9, (__int64 *)(a1 + 120), a1 + 40, (__int64)v13);
      *(_QWORD *)(a1 + 176) = v15;
      if ( !*(_BYTE *)(*v15 - 24) )
      {
        *v5 = 4;
        if ( (unsigned __int8)p9fs::Task<void>::await_suspend(v15, a1) )
          return;
      }
      goto LABEL_20;
    case 4:
LABEL_20:
      v17 = **(_QWORD **)(a1 + 176);
      if ( __ExceptionPtrToBool((const void *)(v17 - 16)) )
      {
        v19 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)(a1 + 152),
                (const struct std::exception_ptr *)(v17 - 16));
        std::rethrow_exception(v19);
      }
      v20 = *(_QWORD *)(a1 + 120);
      if ( v20 )
      {
        if ( *(_WORD *)(v20 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v18);
        *(_QWORD *)(v20 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD))v20)(*(_QWORD *)(a1 + 120));
      }
      v21 = *(char **)(a1 + 80);
      v22 = *(_QWORD *)(a1 + 16);
      v23 = *(char **)(a1 + 24);
      if ( v21 >= &v23[-v22] )
      {
        if ( v21 <= &v23[-v22] )
          goto LABEL_33;
        if ( (unsigned __int64)v21 > *(_QWORD *)(a1 + 32) - v22 )
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1 + 16, v21);
          goto LABEL_33;
        }
        v25 = v21 - &v23[-v22];
        memset_0(v23, 0, v25);
        v24 = &v23[v25];
      }
      else
      {
        v24 = &v21[v22];
      }
      *(_QWORD *)(a1 + 24) = v24;
LABEL_33:
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 88);
      v26 = *(_QWORD *)(*(_QWORD *)(v6 + 192) + 120LL);
      if ( !v26 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, a1 + 16);
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 16);
      *(_BYTE *)(a1 + 128) = 0;
      *v5 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(
        v27,
        a1);
      return;
    case 5:
      v16 = *(_QWORD *)(a1 + 120);
      if ( v16 )
      {
        if ( *(_WORD *)(v16 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v16 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD))v16)(*(_QWORD *)(a1 + 120));
        *(_QWORD *)(a1 + 120) = 0;
      }
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 88);
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 16);
LABEL_36:
      __ExceptionPtrDestroy((void *)(a1 - 16));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 32), 0xF0u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18000ef00  mov     r11, rsp
0x18000ef03  mov     [r11+10h], rbx
0x18000ef07  mov     [r11+18h], rsi
0x18000ef0b  mov     [r11+8], rcx
0x18000ef0f  push    rdi
0x18000ef10  push    r12
0x18000ef12  push    r13
0x18000ef14  push    r14
0x18000ef16  push    r15
0x18000ef18  sub     rsp, 0C0h
0x18000ef1f  mov     rax, cs:__security_cookie
0x18000ef26  xor     rax, rsp
0x18000ef29  mov     [rsp+0E8h+var_30], rax
0x18000ef31  mov     rbx, rcx
0x18000ef34  mov     [rsp+0E8h+var_C8], rcx
0x18000ef39  lea     r14, [rbx+8]
0x18000ef3d  mov     [rsp+0E8h+var_B0], r14
0x18000ef42  movzx   eax, word ptr [r14]
0x18000ef46  mov     [rsp+0E8h+var_C0], ax
0x18000ef4b  mov     r15d, 1
0x18000ef51  add     ax, r15w
0x18000ef55  cmp     ax, 6; switch 7 cases
0x18000ef59  ja      def_18000EF7C; jumptable 000000018000EF7C default case, case 1
0x18000ef5f  mov     r13, r14
0x18000ef62  mov     [rsp+0E8h+var_A8], r14
0x18000ef67  movsx   rax, ax
0x18000ef6b  lea     rdx, cs:180000000h
0x18000ef72  mov     ecx, ds:(jpt_18000EF7C - 180000000h)[rdx+rax*4]
0x18000ef79  add     rcx, rdx
0x18000ef7c  jmp     rcx; switch jump
0x18000ef7e  xor     edi, edi; jumptable 000000018000EF7C case 4
0x18000ef80  jmp     loc_18000F25A
0x18000ef85  lea     rsi, [rbx+10h]; jumptable 000000018000EF7C case 3
0x18000ef89  xor     edi, edi
0x18000ef8b  mov     [rsi+8], rdi
0x18000ef8f  mov     [rsi+10h], rdi
0x18000ef93  mov     [rsi], rdi
0x18000ef96  mov     [rbx+18h], rdi
0x18000ef9a  mov     [rbx+20h], rdi
0x18000ef9e  lea     r15, [rbx+28h]
0x18000efa2  xorps   xmm0, xmm0
0x18000efa5  xor     eax, eax
0x18000efa7  movups  xmmword ptr [r15], xmm0
0x18000efab  mov     [r15+10h], rax
0x18000efaf  mov     r12, [r14+0C0h]
0x18000efb6  mov     rcx, [r12+8]; this
0x18000efbb  mov     rax, [r12+10h]
0x18000efc0  sub     rax, rcx
0x18000efc3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000efc7  jz      loc_18000F0A3
0x18000efcd  test    rcx, rcx
0x18000efd0  jnz     short loc_18000EFDB
0x18000efd2  test    rax, rax
0x18000efd5  jnz     loc_18000F0A3
0x18000efdb  mov     [r15], rax
0x18000efde  mov     [rbx+30h], rcx
0x18000efe2  mov     [rbx+38h], rdi
0x18000efe6  mov     rdx, [r12+38h]
0x18000efeb  test    rdx, rdx
0x18000efee  jz      short loc_18000EFF8
0x18000eff0  mov     rcx, rsi
0x18000eff3  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000eff8  lea     r9, [rbx+40h]
0x18000effc  xorps   xmm0, xmm0
0x18000efff  xor     eax, eax
0x18000f001  movups  xmmword ptr [r9], xmm0
0x18000f005  movups  xmmword ptr [r9+10h], xmm0
0x18000f00a  movups  xmmword ptr [r9+20h], xmm0
0x18000f00f  mov     [r9+30h], rax
0x18000f013  mov     rcx, [rsi]
0x18000f016  mov     [rsp+0E8h+var_98], rcx
0x18000f01b  mov     rax, [rbx+18h]
0x18000f01f  mov     [rsp+0E8h+var_90], rax
0x18000f024  sub     rax, rcx
0x18000f027  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f02b  jz      short loc_18000F0A3
0x18000f02d  test    rcx, rcx
0x18000f030  jnz     short loc_18000F037
0x18000f032  test    rax, rax
0x18000f035  jnz     short loc_18000F0A3
0x18000f037  mov     [r9], rax
0x18000f03a  mov     [rbx+48h], rcx
0x18000f03e  mov     [rbx+50h], rdi
0x18000f042  mov     [rbx+58h], rdi
0x18000f046  mov     [rbx+60h], rdi
0x18000f04a  mov     [rbx+68h], rdi
0x18000f04e  mov     [rbx+70h], dil
0x18000f052  cmp     rax, 7
0x18000f056  jb      short loc_18000F0A3
0x18000f058  mov     qword ptr [rbx+50h], 7
0x18000f060  lea     rdx, [rbx+78h]
0x18000f064  mov     r8, r15
0x18000f067  mov     rcx, [r12]
0x18000f06b  call    ?ProcessMessage@Handler@p9fs@@AEAA?AV?$Task@X@2@AEAVSpanReader@2@AEAVMessageResponse@12@@Z; p9fs::Handler::ProcessMessage(p9fs::SpanReader &,p9fs::Handler::MessageResponse &)
0x18000f070  mov     rcx, rax
0x18000f073  mov     [rbx+0B0h], rax
0x18000f07a  mov     rax, [rax]
0x18000f07d  mov     dl, [rax-18h]
0x18000f080  nop
0x18000f081  test    dl, dl
0x18000f083  jnz     loc_18000F10D
0x18000f089  mov     eax, 4
0x18000f08e  mov     [r14], ax
0x18000f092  mov     rdx, rbx
0x18000f095  call    ?await_suspend@?$Task@X@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<void>::await_suspend(std::experimental::coroutine_handle<void>)
0x18000f09a  test    al, al
0x18000f09c  jz      short loc_18000F10D
0x18000f09e  jmp     loc_18000F27B
0x18000f0a3  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18000f0a9  mov     rax, [rbx+78h]; jumptable 000000018000EF7C case 6
0x18000f0ad  mov     [rsp+0E8h+var_B8], rax
0x18000f0b2  xor     edi, edi
0x18000f0b4  test    rax, rax
0x18000f0b7  jz      short loc_18000F0F0
0x18000f0b9  mov     rcx, [rsp+0E8h]; this
0x18000f0c1  cmp     [rax+8], di
0x18000f0c5  jz      short loc_18000F0D7
0x18000f0c7  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000f0ce  lea     edx, [rdi+34h]; void *
0x18000f0d1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f0d7  or      [rax+8], r15
0x18000f0db  mov     rax, [rax]
0x18000f0de  mov     rcx, [rbx+78h]
0x18000f0e2  mov     [rsp+0E8h+var_B8], rcx
0x18000f0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ec  mov     [rbx+78h], rdi
0x18000f0f0  lea     rcx, [rbx+58h]
0x18000f0f4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f0f9  nop
0x18000f0fa  lea     rcx, [rbx+10h]
0x18000f0fe  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f103  nop
0x18000f104  jmp     loc_18000F25A
0x18000f109  xor     edi, edi; jumptable 000000018000EF7C case 5
0x18000f10b  jmp     short loc_18000F113
0x18000f10d  mov     r15d, 1
0x18000f113  mov     rax, [rbx+0B0h]
0x18000f11a  mov     rsi, [rax]
0x18000f11d  lea     rcx, [rsi-10h]
0x18000f121  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000f127  test    al, al
0x18000f129  jz      short loc_18000F144
0x18000f12b  lea     rcx, [rbx+98h]; this
0x18000f132  lea     rdx, [rsi-10h]; struct std::exception_ptr *
0x18000f136  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x18000f13b  mov     rcx, rax
0x18000f13e  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18000f144  mov     rax, [rbx+78h]
0x18000f148  mov     [rsp+0E8h+var_B8], rax
0x18000f14d  test    rax, rax
0x18000f150  jz      short loc_18000F187
0x18000f152  mov     rcx, [rsp+0E8h]; this
0x18000f15a  cmp     [rax+8], di
0x18000f15e  jz      short loc_18000F172
0x18000f160  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000f167  mov     edx, 34h ; '4'; void *
0x18000f16c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f172  or      [rax+8], r15
0x18000f176  mov     rax, [rax]
0x18000f179  mov     rcx, [rbx+78h]
0x18000f17d  mov     [rsp+0E8h+var_B8], rcx
0x18000f182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f187  mov     rsi, [rbx+50h]
0x18000f18b  mov     [rsp+0E8h+var_70], rsi
0x18000f190  mov     rdx, [rbx+10h]
0x18000f194  mov     [rsp+0E8h+var_98], rdx
0x18000f199  mov     r15, [rbx+18h]
0x18000f19d  mov     [rsp+0E8h+var_90], r15
0x18000f1a2  mov     rcx, r15
0x18000f1a5  sub     rcx, rdx
0x18000f1a8  cmp     rsi, rcx
0x18000f1ab  jnb     short loc_18000F1B3
0x18000f1ad  lea     rax, [rsi+rdx]
0x18000f1b1  jmp     short loc_18000F1E8
0x18000f1b3  jbe     short loc_18000F1EC
0x18000f1b5  mov     rax, [rbx+20h]
0x18000f1b9  mov     [rsp+0E8h+var_88], rax
0x18000f1be  sub     rax, rdx
0x18000f1c1  cmp     rsi, rax
0x18000f1c4  jbe     short loc_18000F1D4
0x18000f1c6  mov     rdx, rsi
0x18000f1c9  lea     rcx, [rbx+10h]
0x18000f1cd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000f1d2  jmp     short loc_18000F1EC
0x18000f1d4  sub     rsi, rcx
0x18000f1d7  mov     r8, rsi; Size
0x18000f1da  xor     edx, edx; Val
0x18000f1dc  mov     rcx, r15; void *
0x18000f1df  call    memset_0
0x18000f1e4  lea     rax, [r15+rsi]
0x18000f1e8  mov     [rbx+18h], rax
0x18000f1ec  lea     rcx, [rbx+58h]
0x18000f1f0  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f1f5  nop
0x18000f1f6  jmp     short loc_18000F205
0x18000f1f8  mov     r13, [rsp+0E8h+var_A8]
0x18000f1fd  mov     r14, r13
0x18000f200  mov     rbx, [rsp+0E8h+var_C8]
0x18000f205  mov     rax, [r13+0C0h]
0x18000f20c  mov     rcx, [rax+78h]
0x18000f210  test    rcx, rcx
0x18000f213  jnz     short loc_18000F21B
0x18000f215  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000f21b  mov     rax, [rcx]
0x18000f21e  lea     rdx, [rbx+10h]
0x18000f222  mov     rax, [rax+10h]
0x18000f226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f22b  nop
0x18000f22c  lea     rcx, [rbx+10h]
0x18000f230  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f235  nop
0x18000f236  jmp     short loc_18000F242
0x18000f238  mov     r14, [rsp+0E8h+var_B0]
0x18000f23d  mov     rbx, [rsp+0E8h+var_C8]
0x18000f242  xor     eax, eax
0x18000f244  mov     [rbx+80h], al
0x18000f24a  mov     [r14], ax
0x18000f24e  mov     rdx, rbx
0x18000f251  call    ??$await_suspend@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>)
0x18000f256  jmp     short loc_18000F27B
0x18000f258  xor     edi, edi; jumptable 000000018000EF7C cases 0,2
0x18000f25a  lea     rcx, [rbx-10h]
0x18000f25e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18000f264  cmp     [rbx+0Ah], di
0x18000f268  jz      short loc_18000F27B
0x18000f26a  mov     edx, 0F0h; unsigned __int64
0x18000f26f  lea     rcx, [rbx-20h]; void *
0x18000f273  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f278  jmp     short loc_18000F27B
0x18000f27a  int     3; Trap to Debugger
0x18000f27b  mov     rcx, [rsp+0E8h+var_30]
0x18000f283  xor     rcx, rsp; StackCookie
0x18000f286  call    __security_check_cookie
0x18000f28b  lea     r11, [rsp+0E8h+var_28]
0x18000f293  mov     rbx, [r11+38h]
0x18000f297  mov     rsi, [r11+40h]
0x18000f29b  mov     rsp, r11
0x18000f29e  pop     r15
0x18000f2a0  pop     r14
0x18000f2a2  pop     r13
0x18000f2a4  pop     r12
0x18000f2a6  pop     rdi
0x18000f2a7  retn
```
