# p9fs::Handler::ProcessMessage$_ResumeCoro$1_0

- ea: `0x180017570`
- end: `0x180017a3c`
- name: `p9fs::Handler::ProcessMessage$_ResumeCoro$1_0`
- size: `1228`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18000e930`

## callees

- `0x180004120`
- `0x180004534`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000d5d8`
- `0x18000e23c`
- `0x18000e2a8`
- `0x180017570`
- `0x180017a44`
- `0x18001c7c4`
- `0x18001c7e0`
- `0x18001c82c`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800179c9`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800179c9`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800176fa`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001791e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800176fa`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001791e`

## string_xrefs

- `0x1800176ac`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18001773c`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x1800178c3`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180017960`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall p9fs::Handler::ProcessMessage__ResumeCoro_1_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // rsi
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r14
  const char *v9; // r9
  std::exception_ptr *v10; // rcx
  __int64 v11; // rax
  gsl::details *v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r14
  const char *v21; // r9
  std::exception_ptr *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_44;
    case 2:
      *(_OWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      *(_OWORD *)(a1 + 16) = *(_OWORD *)(a1 + 544);
      *(_QWORD *)(a1 + 32) = 0;
      *(_OWORD *)(a1 + 40) = 0;
      *(_OWORD *)(a1 + 56) = 0;
      *(_OWORD *)(a1 + 72) = 0;
      *(_QWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 40) = 256;
      *(_QWORD *)(a1 + 48) = a1 + 96;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      *(_QWORD *)(a1 + 80) = 0;
      *(_BYTE *)(a1 + 88) = 1;
      *(_QWORD *)(a1 + 56) = 7;
      v6 = p9fs::Handler::ProcessMessage(*(_QWORD *)(a1 + 536), (__int64 *)(a1 + 352), a1 + 16, a1 + 40);
      *(_QWORD *)(a1 + 512) = v6;
      if ( !*(_BYTE *)(*v6 - 24) )
      {
        *(_WORD *)v5 = 4;
        if ( (unsigned __int8)p9fs::Task<void>::await_suspend(v6, a1) )
          return;
      }
      goto LABEL_10;
    case 4:
LABEL_10:
      v8 = **(_QWORD **)(a1 + 512);
      if ( __ExceptionPtrToBool((const void *)(v8 - 16)) )
      {
        v10 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)(a1 + 432),
                (const struct std::exception_ptr *)(v8 - 16));
        std::rethrow_exception(v10);
      }
      v11 = *(_QWORD *)(a1 + 352);
      if ( v11 )
      {
        if ( *(_WORD *)(v11 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v9);
        *(_QWORD *)(v11 + 8) |= 1uLL;
        (*(void (**)(void))v11)();
      }
      v12 = *(gsl::details **)(a1 + 56);
      v13 = *(_QWORD *)(a1 + 40);
      if ( v12 != (gsl::details *)-1LL )
      {
        if ( v13 >= (unsigned __int64)v12 )
        {
          v13 = *(_QWORD *)(a1 + 56);
          goto LABEL_21;
        }
LABEL_23:
        gsl::details::terminate(v12);
      }
      if ( v13 == -1 )
        goto LABEL_23;
LABEL_21:
      v14 = *(_QWORD *)(a1 + 48);
      *(_QWORD *)(a1 + 456) = v13;
      *(_QWORD *)(a1 + 448) = v14;
      *(_QWORD *)(a1 + 368) = *(_QWORD *)(v5 + 528) + 8LL;
      *(_QWORD *)(a1 + 376) = 0;
      *(_QWORD *)(a1 + 384) = 0;
      *(_WORD *)v5 = 6;
      if ( !(unsigned __int8)p9fs::AsyncLock::AsyncLockTask::await_suspend(a1 + 368, a1) )
      {
LABEL_25:
        *(_QWORD *)(a1 + 360) = *(_QWORD *)(a1 + 368);
        v15 = *(_QWORD *)(a1 + 456);
        if ( v15 == -1 || (v16 = *(_QWORD *)(a1 + 448)) == 0 && v15 )
          gsl::details::terminate((gsl::details *)a1);
        v17 = *(_QWORD *)(*(_QWORD *)(v5 + 528) + 24LL);
        *(_QWORD *)(a1 + 416) = v15;
        *(_QWORD *)(a1 + 424) = v16;
        v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v17 + 24LL))(
                          v17,
                          a1 + 392,
                          a1 + 416,
                          *(_QWORD *)(a1 + 560));
        *(_QWORD *)(a1 + 480) = v18;
        if ( *(_BYTE *)(*v18 - 40LL)
          || (*(_WORD *)v5 = 8, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v18, a1)) )
        {
LABEL_37:
          v20 = **(_QWORD **)(a1 + 480);
          if ( __ExceptionPtrToBool((const void *)(v20 - 32)) )
          {
            v22 = std::exception_ptr::exception_ptr(
                    (std::exception_ptr *)(a1 + 464),
                    (const struct std::exception_ptr *)(v20 - 32));
            std::rethrow_exception(v22);
          }
          v23 = *(_QWORD *)(a1 + 392);
          if ( v23 )
          {
            if ( *(_WORD *)(v23 + 8) )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x34,
                (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
                v21);
            *(_QWORD *)(v23 + 8) |= 1uLL;
            (*(void (**)(void))v23)();
          }
          p9fs::AsyncLock::AsyncLockGuard::~AsyncLockGuard((p9fs::AsyncLock::AsyncLockGuard *)(a1 + 360));
          std::vector<unsigned char>::~vector<unsigned char>(a1 + 64);
          *(_BYTE *)(a1 + 400) = 0;
          *(_WORD *)v5 = 0;
          p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(
            v24,
            a1);
        }
      }
      return;
    case 5:
      v7 = *(_QWORD *)(a1 + 352);
      if ( v7 )
      {
        if ( *(_WORD *)(v7 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v7 + 8) |= 1uLL;
        (*(void (**)(void))v7)();
        *(_QWORD *)(a1 + 352) = 0;
      }
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 64);
      goto LABEL_44;
    case 6:
      goto LABEL_25;
    case 7:
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 64);
      goto LABEL_44;
    case 8:
      goto LABEL_37;
    case 9:
      v19 = *(_QWORD *)(a1 + 392);
      if ( v19 )
      {
        if ( *(_WORD *)(v19 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v19 + 8) |= 1uLL;
        (*(void (**)(void))v19)();
        *(_QWORD *)(a1 + 392) = 0;
      }
      p9fs::AsyncLock::AsyncLockGuard::~AsyncLockGuard((p9fs::AsyncLock::AsyncLockGuard *)(a1 + 360));
      std::vector<unsigned char>::~vector<unsigned char>(a1 + 64);
LABEL_44:
      __ExceptionPtrDestroy((void *)(a1 - 16));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 32), 0x260u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180017570  mov     r11, rsp
0x180017573  mov     [r11+10h], rbx
0x180017577  mov     [r11+18h], rsi
0x18001757b  mov     [r11+8], rcx
0x18001757f  push    rdi
0x180017580  push    r14
0x180017582  push    r15
0x180017584  sub     rsp, 0E0h
0x18001758b  mov     rax, cs:__security_cookie
0x180017592  xor     rax, rsp
0x180017595  mov     [rsp+0F8h+var_28], rax
0x18001759d  mov     rbx, rcx
0x1800175a0  mov     [rsp+0F8h+var_B0], rcx
0x1800175a5  lea     rsi, [rbx+8]
0x1800175a9  mov     [rsp+0F8h+var_A8], rsi
0x1800175ae  movzx   eax, word ptr [rsi]
0x1800175b1  mov     [rsp+0F8h+var_C0], ax
0x1800175b6  mov     r15d, 1
0x1800175bc  add     ax, r15w
0x1800175c0  cmp     ax, 0Ah; switch 11 cases
0x1800175c4  ja      def_1800175DF; jumptable 00000001800175DF default case, case 1
0x1800175ca  movsx   rax, ax
0x1800175ce  lea     rdx, cs:180000000h
0x1800175d5  mov     ecx, ds:(jpt_1800175DF - 180000000h)[rdx+rax*4]
0x1800175dc  add     rcx, rdx; this
0x1800175df  jmp     rcx; switch jump
0x1800175e1  xor     edi, edi; jumptable 00000001800175DF case 4
0x1800175e3  jmp     loc_1800179C5
0x1800175e8  lea     r8, [rbx+10h]; jumptable 00000001800175DF case 3
0x1800175ec  xorps   xmm0, xmm0
0x1800175ef  xor     eax, eax
0x1800175f1  movups  xmmword ptr [r8], xmm0
0x1800175f5  mov     [r8+10h], rax
0x1800175f9  movups  xmm0, xmmword ptr [r8+210h]
0x180017601  movdqu  xmmword ptr [r8], xmm0
0x180017606  xor     edi, edi
0x180017608  mov     [rbx+20h], rdi
0x18001760c  lea     r9, [rbx+28h]
0x180017610  xorps   xmm0, xmm0
0x180017613  movups  xmmword ptr [r9], xmm0
0x180017617  movups  xmmword ptr [r9+10h], xmm0
0x18001761c  movups  xmmword ptr [r9+20h], xmm0
0x180017621  mov     [r9+30h], rax
0x180017625  mov     qword ptr [r9], 100h
0x18001762c  lea     rax, [rbx+60h]
0x180017630  mov     [rbx+30h], rax
0x180017634  mov     [rbx+40h], rdi
0x180017638  mov     [rbx+48h], rdi
0x18001763c  mov     [rbx+50h], rdi
0x180017640  mov     [rbx+58h], r15b
0x180017644  mov     qword ptr [rbx+38h], 7
0x18001764c  lea     rdx, [rbx+160h]
0x180017653  mov     rcx, [rsi+210h]
0x18001765a  call    ?ProcessMessage@Handler@p9fs@@AEAA?AV?$Task@X@2@AEAVSpanReader@2@AEAVMessageResponse@12@@Z; p9fs::Handler::ProcessMessage(p9fs::SpanReader &,p9fs::Handler::MessageResponse &)
0x18001765f  mov     rcx, rax
0x180017662  mov     [rbx+200h], rax
0x180017669  mov     rax, [rax]
0x18001766c  mov     dl, [rax-18h]
0x18001766f  nop
0x180017670  test    dl, dl
0x180017672  jnz     short loc_1800176EC
0x180017674  lea     eax, [rdi+4]
0x180017677  mov     [rsi], ax
0x18001767a  mov     rdx, rbx
0x18001767d  call    ?await_suspend@?$Task@X@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<void>::await_suspend(std::experimental::coroutine_handle<void>)
0x180017682  test    al, al
0x180017684  jz      short loc_1800176EC
0x180017686  jmp     loc_1800179E6
0x18001768b  mov     rax, [rbx+160h]; jumptable 00000001800175DF case 6
0x180017692  mov     [rsp+0F8h+var_B8], rax
0x180017697  xor     edi, edi
0x180017699  test    rax, rax
0x18001769c  jz      short loc_1800176DB
0x18001769e  mov     rcx, [rsp+0F8h]; this
0x1800176a6  cmp     [rax+8], di
0x1800176aa  jz      short loc_1800176BC
0x1800176ac  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800176b3  lea     edx, [rdi+34h]; void *
0x1800176b6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800176bc  or      [rax+8], r15
0x1800176c0  mov     rax, [rax]
0x1800176c3  mov     rcx, [rbx+160h]
0x1800176ca  mov     [rsp+0F8h+var_B8], rcx
0x1800176cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176d4  mov     [rbx+160h], rdi
0x1800176db  lea     rcx, [rbx+40h]
0x1800176df  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800176e4  nop
0x1800176e5  jmp     loc_1800179C5
0x1800176ea  xor     edi, edi; jumptable 00000001800175DF case 5
0x1800176ec  mov     rax, [rbx+200h]
0x1800176f3  mov     r14, [rax]
0x1800176f6  lea     rcx, [r14-10h]
0x1800176fa  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180017700  test    al, al
0x180017702  jz      short loc_18001771D
0x180017704  lea     rcx, [rbx+1B0h]; this
0x18001770b  lea     rdx, [r14-10h]; struct std::exception_ptr *
0x18001770f  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180017714  mov     rcx, rax
0x180017717  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18001771d  mov     rax, [rbx+160h]
0x180017724  mov     [rsp+0F8h+var_B8], rax
0x180017729  test    rax, rax
0x18001772c  jz      short loc_180017766
0x18001772e  mov     rcx, [rsp+0F8h]; this
0x180017736  cmp     [rax+8], di
0x18001773a  jz      short loc_18001774E
0x18001773c  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180017743  mov     edx, 34h ; '4'; void *
0x180017748  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001774e  or      [rax+8], r15
0x180017752  mov     rax, [rax]
0x180017755  mov     rcx, [rbx+160h]
0x18001775c  mov     [rsp+0F8h+var_B8], rcx
0x180017761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017766  mov     rcx, [rbx+38h]; this
0x18001776a  mov     [rsp+0F8h+var_70], rcx
0x180017772  mov     rax, [rbx+28h]
0x180017776  mov     [rsp+0F8h+var_80], rax
0x18001777b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001777f  jnz     short loc_180017788
0x180017781  cmp     rax, rcx
0x180017784  jz      short loc_1800177EA
0x180017786  jmp     short loc_180017790
0x180017788  cmp     rax, rcx
0x18001778b  jb      short loc_1800177EA
0x18001778d  mov     rax, rcx
0x180017790  mov     rdx, [rbx+30h]
0x180017794  mov     [rsp+0F8h+var_78], rdx
0x18001779c  mov     [rbx+1C8h], rax
0x1800177a3  mov     [rbx+1C0h], rdx
0x1800177aa  lea     rcx, [rbx+170h]
0x1800177b1  mov     rax, [rsi+210h]
0x1800177b8  mov     r14d, 8
0x1800177be  add     rax, r14
0x1800177c1  mov     [rcx], rax
0x1800177c4  mov     [rbx+178h], rdi
0x1800177cb  mov     [rbx+180h], rdi
0x1800177d2  lea     eax, [r14-2]
0x1800177d6  mov     [rsi], ax
0x1800177d9  mov     rdx, rbx
0x1800177dc  call    ?await_suspend@AsyncLockTask@AsyncLock@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::AsyncLock::AsyncLockTask::await_suspend(std::experimental::coroutine_handle<void>)
0x1800177e1  test    al, al
0x1800177e3  jz      short loc_180017807
0x1800177e5  jmp     loc_1800179E6
0x1800177ea  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800177f0  lea     rcx, [rbx+40h]; jumptable 00000001800175DF case 8
0x1800177f4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800177f9  nop
0x1800177fa  xor     edi, edi
0x1800177fc  jmp     loc_1800179C5
0x180017801  xor     edi, edi; jumptable 00000001800175DF case 7
0x180017803  lea     r14d, [rdi+8]
0x180017807  mov     rax, [rbx+170h]
0x18001780e  mov     [rsp+0F8h+var_98], rax
0x180017813  mov     [rbx+168h], rax
0x18001781a  mov     rdx, [rbx+1C8h]
0x180017821  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180017825  jz      short loc_18001789C
0x180017827  mov     r9, [rbx+1C0h]
0x18001782e  test    r9, r9
0x180017831  jnz     short loc_180017838
0x180017833  test    rdx, rdx
0x180017836  jnz     short loc_18001789C
0x180017838  mov     rax, [rsi+210h]
0x18001783f  mov     rcx, [rax+18h]
0x180017843  lea     r8, [rbx+1A0h]
0x18001784a  mov     [r8], rdx
0x18001784d  mov     [rbx+1A8h], r9
0x180017854  mov     rax, [rcx]
0x180017857  lea     rdx, [rbx+188h]
0x18001785e  mov     r9, [rbx+230h]
0x180017865  mov     rax, [rax+18h]
0x180017869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001786e  mov     rcx, rax
0x180017871  mov     [rbx+1E0h], rax
0x180017878  mov     rax, [rax]
0x18001787b  mov     dl, [rax-28h]
0x18001787e  nop
0x18001787f  test    dl, dl
0x180017881  jnz     loc_180017910
0x180017887  mov     [rsi], r14w
0x18001788b  mov     rdx, rbx
0x18001788e  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180017893  test    al, al
0x180017895  jz      short loc_180017910
0x180017897  jmp     loc_1800179E6
0x18001789c  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800178a2  mov     rax, [rbx+188h]; jumptable 00000001800175DF case 10
0x1800178a9  mov     [rsp+0F8h+var_C8], rax
0x1800178ae  xor     edi, edi
0x1800178b0  test    rax, rax
0x1800178b3  jz      short loc_1800178F2
0x1800178b5  mov     rcx, [rsp+0F8h]; this
0x1800178bd  cmp     [rax+8], di
0x1800178c1  jz      short loc_1800178D3
0x1800178c3  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800178ca  lea     edx, [rdi+34h]; void *
0x1800178cd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800178d3  or      [rax+8], r15
0x1800178d7  mov     rax, [rax]
0x1800178da  mov     rcx, [rbx+188h]
0x1800178e1  mov     [rsp+0F8h+var_C8], rcx
0x1800178e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178eb  mov     [rbx+188h], rdi
0x1800178f2  lea     rcx, [rbx+168h]; this
0x1800178f9  call    ??1AsyncLockGuard@AsyncLock@p9fs@@QEAA@XZ; p9fs::AsyncLock::AsyncLockGuard::~AsyncLockGuard(void)
0x1800178fe  nop
0x1800178ff  lea     rcx, [rbx+40h]
0x180017903  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180017908  nop
0x180017909  jmp     loc_1800179C5
0x18001790e  xor     edi, edi; jumptable 00000001800175DF case 9
0x180017910  mov     rax, [rbx+1E0h]
0x180017917  mov     r14, [rax]
0x18001791a  lea     rcx, [r14-20h]
0x18001791e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180017924  test    al, al
0x180017926  jz      short loc_180017941
0x180017928  lea     rcx, [rbx+1D0h]; this
0x18001792f  lea     rdx, [r14-20h]; struct std::exception_ptr *
0x180017933  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180017938  mov     rcx, rax
0x18001793b  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180017941  mov     rax, [rbx+188h]
0x180017948  mov     [rsp+0F8h+var_C8], rax
0x18001794d  test    rax, rax
0x180017950  jz      short loc_18001798B
0x180017952  mov     rcx, [rsp+0F8h]; this
0x18001795a  cmp     [rax+8], di
0x18001795e  jz      short loc_180017972
0x180017960  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180017967  mov     edx, 34h ; '4'; void *
0x18001796c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017972  or      [rax+8], r15
0x180017976  mov     rax, [rax]
0x180017979  mov     rcx, [rbx+188h]
0x180017980  mov     [rsp+0F8h+var_C8], rcx
0x180017985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798a  nop
0x18001798b  lea     rcx, [rbx+168h]; this
0x180017992  call    ??1AsyncLockGuard@AsyncLock@p9fs@@QEAA@XZ; p9fs::AsyncLock::AsyncLockGuard::~AsyncLockGuard(void)
0x180017997  nop
0x180017998  lea     rcx, [rbx+40h]
0x18001799c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800179a1  nop
0x1800179a2  jmp     short loc_1800179AE
0x1800179a4  mov     rsi, [rsp+0F8h+var_A8]
0x1800179a9  mov     rbx, [rsp+0F8h+var_B0]
0x1800179ae  xor     eax, eax
0x1800179b0  mov     [rbx+190h], al
0x1800179b6  mov     [rsi], ax
0x1800179b9  mov     rdx, rbx
0x1800179bc  call    ??$await_suspend@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>)
0x1800179c1  jmp     short loc_1800179E6
0x1800179c3  xor     edi, edi; jumptable 00000001800175DF cases 0,2
0x1800179c5  lea     rcx, [rbx-10h]
0x1800179c9  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800179cf  cmp     [rbx+0Ah], di
0x1800179d3  jz      short loc_1800179E6
0x1800179d5  mov     edx, 260h; unsigned __int64
0x1800179da  lea     rcx, [rbx-20h]; void *
0x1800179de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800179e3  jmp     short loc_1800179E6
0x1800179e5  int     3; Trap to Debugger
0x1800179e6  mov     rcx, [rsp+0F8h+var_28]
0x1800179ee  xor     rcx, rsp; StackCookie
0x1800179f1  call    __security_check_cookie
0x1800179f6  lea     r11, [rsp+0F8h+var_18]
0x1800179fe  mov     rbx, [r11+28h]
0x180017a02  mov     rsi, [r11+30h]
0x180017a06  mov     rsp, r11
0x180017a09  pop     r15
0x180017a0b  pop     r14
0x180017a0d  pop     rdi
0x180017a0e  retn
```
