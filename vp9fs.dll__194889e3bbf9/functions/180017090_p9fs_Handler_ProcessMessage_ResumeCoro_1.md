# p9fs::Handler::ProcessMessage$_ResumeCoro$1

- ea: `0x180017090`
- end: `0x180017560`
- name: `p9fs::Handler::ProcessMessage$_ResumeCoro$1`
- size: `1232`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180017a44`

## callees

- `0x180004120`
- `0x180004144`
- `0x180004534`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000d5d8`
- `0x180012700`
- `0x180017090`
- `0x180019414`
- `0x18001c7c4`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800174f6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800174f6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180017377`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180017377`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800172c3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800172c3`

## string_xrefs

- `0x180017339`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x1800173b8`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall p9fs::Handler::ProcessMessage__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // r14
  const char *v6; // r9
  _QWORD *v7; // rdx
  gsl::details *v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // r10
  __int64 v11; // r9
  unsigned __int64 v12; // r8
  __int64 v13; // rcx
  char v14; // si
  __int64 v15; // rbx
  __int64 v16; // r13
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rdx
  const char *v27; // r9
  __int64 v28; // rcx
  int v29; // ebx
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned __int64 *v32; // r8
  unsigned __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rcx
  unsigned __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // [rsp+20h] [rbp-F8h]
  __int64 v40; // [rsp+60h] [rbp-B8h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_39;
    case 2:
      *(_OWORD *)(a1 + 64) = *(_OWORD *)*(_QWORD *)(a1 + 1184);
      ((void (*)(void))p9fs::TraceLogMessage)();
      v7 = *(_QWORD **)(a1 + 1184);
      v8 = (gsl::details *)v7[2];
      if ( *v7 - (_QWORD)v8 < 4u )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          v6);
      if ( *v7 < (unsigned __int64)v8 )
        goto LABEL_38;
      v7[2] = (char *)v8 + 4;
      v8 = *(gsl::details **)(a1 + 1184);
      v9 = *((_QWORD *)v8 + 2);
      if ( *(_QWORD *)v8 == v9 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          v6);
      if ( *(_QWORD *)v8 < v9 )
        goto LABEL_38;
      v10 = *((_QWORD *)v8 + 1);
      *((_QWORD *)v8 + 2) = v9 + 1;
      v11 = *(_QWORD *)(a1 + 1184);
      v12 = *(_QWORD *)(v11 + 16);
      if ( *(_QWORD *)v11 - v12 < 2 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          (const char *)v11);
      if ( *(_QWORD *)v11 < v12 )
        goto LABEL_38;
      v13 = *(_QWORD *)(v11 + 8);
      v14 = *(_BYTE *)(v10 + v9);
      *(_BYTE *)(a1 + 12) = v14;
      *(_QWORD *)(v11 + 16) = v12 + 2;
      *(_WORD *)(a1 + 1104) = *(_WORD *)(v13 + v12);
      v15 = *(_QWORD *)(a1 + 1192);
      *(_OWORD *)(a1 + 16) = *(_OWORD *)v15;
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(v15 + 16);
      v16 = *(_QWORD *)(a1 + 1184);
      v17 = operator new(0x3D0u);
      v18 = *(_QWORD *)(v5 + 1168);
      v17 += 6;
      *(_QWORD *)(a1 + 80) = v17;
      v17[111] = v18;
      *((_BYTE *)v17 + 896) = v14;
      v17[113] = v16;
      v17[114] = v15;
      **(_QWORD **)(a1 + 80) = p9fs::Handler::HandleMessage__ResumeCoro_1;
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL) = 65538;
      v19 = *(_QWORD *)(a1 + 80);
      *(_OWORD *)(v19 - 48) = 0;
      *(_OWORD *)(v19 - 32) = 0;
      *(_QWORD *)(v19 - 16) = 0;
      v39 = *(_QWORD *)(a1 + 80);
      *(_QWORD *)(v39 - 48) = 0;
      *(_BYTE *)(v39 - 40) = 0;
      v20 = (_QWORD *)(v39 - 32);
      *v20 = 0;
      v20[1] = 0;
      __ExceptionPtrCreate((void *)(v39 - 32));
      *(_QWORD *)(a1 + 40) = v19;
      *(_BYTE *)(*(_QWORD *)(a1 + 80) + 880LL) = 0;
      p9fs::Handler::HandleMessage__ResumeCoro_1(*(_QWORD *)(a1 + 80), v21, v22, v23);
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 40) - 40LL) )
      {
        *(_WORD *)v5 = 4;
        if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(a1 + 40, a1) )
          return;
      }
LABEL_19:
      v25 = *(_QWORD *)(a1 + 40);
      if ( __ExceptionPtrToBool((const void *)(v25 - 32)) )
      {
        v28 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)(a1 + 1120),
                (const struct std::exception_ptr *)(v25 - 32));
        std::rethrow_exception(v28);
      }
      v29 = *(_DWORD *)(v25 - 16);
      v30 = *(_QWORD *)(a1 + 40);
      if ( v30 )
      {
        if ( *(_WORD *)(v30 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v27);
        *(_QWORD *)(v30 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD, __int64))v30)(*(_QWORD *)(a1 + 40), v26);
      }
      if ( !v29 )
        goto LABEL_29;
      v40 = *(_QWORD *)(a1 + 32);
      v31 = *(_QWORD *)(a1 + 1192);
      *(_OWORD *)v31 = *(_OWORD *)(a1 + 16);
      *(_QWORD *)(v31 + 16) = v40;
      v32 = *(unsigned __int64 **)(a1 + 1192);
      v33 = v32[2];
      if ( *v32 < v33 || *v32 - v33 < 4 )
        goto LABEL_38;
      v8 = (gsl::details *)v32[1];
      v32[2] = v33 + 4;
      *(_DWORD *)((char *)v8 + v33) = -v29;
      *(_BYTE *)(a1 + 12) = 6;
LABEL_29:
      v34 = *(_QWORD *)(a1 + 1192);
      if ( *(_QWORD *)v34 < 7u )
        goto LABEL_38;
      v35 = *(_QWORD *)(v34 + 8);
      *(_DWORD *)v35 = *(_DWORD *)(v34 + 16);
      *(_BYTE *)(v35 + 4) = *(_BYTE *)(a1 + 12) + 1;
      *(_WORD *)(v35 + 5) = *(_WORD *)(a1 + 1104);
      v8 = *(gsl::details **)(a1 + 1192);
      v36 = *(_QWORD *)v8;
      if ( *((_QWORD *)v8 + 2) == -1 )
      {
        if ( v36 == -1 )
          goto LABEL_38;
      }
      else
      {
        if ( v36 < *((_QWORD *)v8 + 2) )
          goto LABEL_38;
        v36 = *((_QWORD *)v8 + 2);
      }
      v37 = *((_QWORD *)v8 + 1);
      if ( !v37 && v36 )
LABEL_38:
        gsl::details::terminate(v8);
      *(_QWORD *)(a1 + 1152) = v36;
      *(_QWORD *)(a1 + 1160) = v37;
      p9fs::TraceLogMessage(a1 + 1152, v37);
      *(_BYTE *)(a1 + 48) = 0;
      *(_WORD *)v5 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(
        v38,
        a1);
      return;
    case 4:
      goto LABEL_19;
    case 5:
      v24 = *(_QWORD *)(a1 + 40);
      if ( v24 )
      {
        if ( *(_WORD *)(v24 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v24 + 8) |= 1uLL;
        (*(void (**)(void))v24)();
      }
LABEL_39:
      __ExceptionPtrDestroy((void *)(a1 - 16));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 32), 0x4D0u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180017090  mov     r11, rsp
0x180017093  mov     [r11+10h], rbx
0x180017097  mov     [r11+18h], rsi
0x18001709b  mov     [r11+8], rcx
0x18001709f  push    rdi
0x1800170a0  push    r12
0x1800170a2  push    r13
0x1800170a4  push    r14
0x1800170a6  push    r15
0x1800170a8  sub     rsp, 0F0h
0x1800170af  mov     rax, cs:__security_cookie
0x1800170b6  xor     rax, rsp
0x1800170b9  mov     [rsp+118h+var_30], rax
0x1800170c1  mov     rdi, rcx
0x1800170c4  mov     [rsp+118h+var_E0], rcx
0x1800170c9  lea     r14, [rdi+8]
0x1800170cd  mov     [rsp+118h+var_D0], r14
0x1800170d2  movzx   eax, word ptr [r14]
0x1800170d6  mov     [rsp+118h+var_E8], ax
0x1800170db  mov     r15d, 1
0x1800170e1  add     ax, r15w
0x1800170e5  cmp     ax, 6; switch 7 cases
0x1800170e9  ja      def_180017104; jumptable 0000000180017104 default case, case 1
0x1800170ef  movsx   rax, ax
0x1800170f3  lea     rdx, cs:180000000h
0x1800170fa  mov     ecx, ds:(jpt_180017104 - 180000000h)[rdx+rax*4]
0x180017101  add     rcx, rdx
0x180017104  jmp     rcx; switch jump
0x180017106  xor     esi, esi; jumptable 0000000180017104 case 4
0x180017108  jmp     loc_1800174F2
0x18001710d  lea     rcx, [rdi+40h]; jumptable 0000000180017104 case 3
0x180017111  mov     rax, [rdi+4A0h]
0x180017118  movups  xmm0, xmmword ptr [rax]
0x18001711b  movdqu  xmmword ptr [rcx], xmm0
0x18001711f  call    ?TraceLogMessage@p9fs@@YAXV?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; p9fs::TraceLogMessage(gsl::span<gsl::byte const,-1>)
0x180017124  mov     rdx, [rdi+4A0h]
0x18001712b  mov     rcx, [rdx+10h]; this
0x18001712f  mov     rax, [rdx]
0x180017132  sub     rax, rcx
0x180017135  mov     r12d, 4
0x18001713b  cmp     rax, r12
0x18001713e  jnb     short loc_18001715A
0x180017140  mov     rcx, [rsp+118h]; this
0x180017148  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x18001714f  lea     edx, [r12+25h]; void *
0x180017154  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001715a  cmp     [rdx], rcx
0x18001715d  jb      loc_1800174CD
0x180017163  lea     rax, [rcx+4]
0x180017167  mov     [rdx+10h], rax
0x18001716b  mov     rcx, [rdi+4A0h]
0x180017172  mov     rdx, [rcx+10h]
0x180017176  mov     rax, [rcx]
0x180017179  sub     rax, rdx
0x18001717c  cmp     rax, r15
0x18001717f  jnb     short loc_18001719B
0x180017181  mov     rcx, [rsp+118h]; this
0x180017189  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180017190  mov     edx, 29h ; ')'; void *
0x180017195  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001719b  cmp     [rcx], rdx
0x18001719e  jb      loc_1800174CD
0x1800171a4  mov     r10, [rcx+8]
0x1800171a8  lea     rax, [rdx+1]
0x1800171ac  mov     [rcx+10h], rax
0x1800171b0  mov     r9, [rdi+4A0h]; char *
0x1800171b7  mov     r8, [r9+10h]
0x1800171bb  mov     rax, [r9]
0x1800171be  sub     rax, r8
0x1800171c1  cmp     rax, 2
0x1800171c5  jnb     short loc_1800171E1
0x1800171c7  mov     rcx, [rsp+118h]; this
0x1800171cf  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x1800171d6  mov     edx, 29h ; ')'; void *
0x1800171db  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800171e1  cmp     [r9], r8
0x1800171e4  jb      loc_1800174CD
0x1800171ea  mov     rcx, [r9+8]
0x1800171ee  mov     sil, [r10+rdx]
0x1800171f2  mov     [rdi+0Ch], sil
0x1800171f6  lea     rax, [r8+2]
0x1800171fa  mov     [r9+10h], rax
0x1800171fe  movzx   eax, word ptr [rcx+r8]
0x180017203  mov     [rdi+450h], ax
0x18001720a  mov     rbx, [rdi+4A8h]
0x180017211  movups  xmm0, xmmword ptr [rbx]
0x180017214  movups  xmmword ptr [rdi+10h], xmm0
0x180017218  movsd   xmm1, qword ptr [rbx+10h]
0x18001721d  movsd   qword ptr [rdi+20h], xmm1
0x180017222  mov     r13, [rdi+4A0h]
0x180017229  mov     ecx, 3D0h; Size
0x18001722e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017233  mov     rcx, [r14+490h]
0x18001723a  mov     [rsp+118h+var_F8], rax
0x18001723f  add     rax, 30h ; '0'
0x180017243  mov     [rdi+50h], rax
0x180017247  mov     [rsp+118h+var_F8], rax
0x18001724c  mov     [rax+378h], rcx
0x180017253  mov     [rax+380h], sil
0x18001725a  mov     [rax+388h], r13
0x180017261  mov     [rax+390h], rbx
0x180017268  mov     rax, [rdi+50h]
0x18001726c  mov     [rsp+118h+var_F8], rax
0x180017271  lea     rcx, p9fs__Handler__HandleMessage$_ResumeCoro$1
0x180017278  mov     [rax], rcx
0x18001727b  mov     rax, [rdi+50h]
0x18001727f  mov     [rsp+118h+var_F8], rax
0x180017284  mov     dword ptr [rax+8], 10002h
0x18001728b  mov     rbx, [rdi+50h]
0x18001728f  mov     [rsp+118h+var_F8], rbx
0x180017294  xorps   xmm0, xmm0
0x180017297  xor     eax, eax
0x180017299  movups  xmmword ptr [rbx-30h], xmm0
0x18001729d  movups  xmmword ptr [rbx-20h], xmm0
0x1800172a1  mov     [rbx-10h], rax
0x1800172a5  mov     rcx, [rdi+50h]
0x1800172a9  mov     [rsp+118h+var_F8], rcx
0x1800172ae  xor     esi, esi
0x1800172b0  mov     [rcx-30h], rsi
0x1800172b4  mov     [rcx-28h], sil
0x1800172b8  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800172bc  mov     [rcx], rsi
0x1800172bf  mov     [rcx+8], rsi
0x1800172c3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800172c9  nop
0x1800172ca  lea     r13, [rdi+28h]
0x1800172ce  mov     [r13+0], rbx
0x1800172d2  mov     rax, [rdi+50h]
0x1800172d6  mov     [rsp+118h+var_F8], rax
0x1800172db  xor     ecx, ecx
0x1800172dd  mov     [rax+370h], cl
0x1800172e3  mov     rcx, [rdi+50h]
0x1800172e7  mov     [rsp+118h+var_F8], rcx
0x1800172ec  call    p9fs__Handler__HandleMessage$_ResumeCoro$1
0x1800172f1  nop
0x1800172f2  mov     rax, [r13+0]
0x1800172f6  mov     [rsp+118h+var_F0], rax
0x1800172fb  mov     dl, [rax-28h]
0x1800172fe  nop
0x1800172ff  test    dl, dl
0x180017301  jnz     short loc_18001736A
0x180017303  mov     [r14], r12w
0x180017307  mov     rdx, rdi
0x18001730a  mov     rcx, r13
0x18001730d  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180017312  test    al, al
0x180017314  jz      short loc_18001736A
0x180017316  jmp     loc_180017513
0x18001731b  mov     rax, [rdi+28h]; jumptable 0000000180017104 case 6
0x18001731f  mov     [rsp+118h+var_F0], rax
0x180017324  xor     esi, esi
0x180017326  test    rax, rax
0x180017329  jz      short loc_18001735F
0x18001732b  mov     rcx, [rsp+118h]; this
0x180017333  cmp     [rax+8], si
0x180017337  jz      short loc_180017349
0x180017339  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180017340  lea     edx, [rsi+34h]; void *
0x180017343  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017349  or      [rax+8], r15
0x18001734d  mov     rax, [rax]
0x180017350  mov     rcx, [rdi+28h]
0x180017354  mov     [rsp+118h+var_F0], rcx
0x180017359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001735e  nop
0x18001735f  jmp     loc_1800174F2
0x180017364  xor     esi, esi; jumptable 0000000180017104 case 5
0x180017366  lea     r12d, [rsi+4]
0x18001736a  mov     rbx, [rdi+28h]
0x18001736e  mov     [rsp+118h+var_F0], rbx
0x180017373  lea     rcx, [rbx-20h]
0x180017377  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18001737d  test    al, al
0x18001737f  jz      short loc_180017399
0x180017381  lea     rcx, [rdi+460h]; this
0x180017388  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x18001738c  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180017391  mov     rcx, rax
0x180017394  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180017399  mov     ebx, [rbx-10h]
0x18001739c  mov     rax, [rdi+28h]
0x1800173a0  mov     [rsp+118h+var_F0], rax
0x1800173a5  test    rax, rax
0x1800173a8  jz      short loc_1800173E0
0x1800173aa  mov     rcx, [rsp+118h]; this
0x1800173b2  cmp     [rax+8], si
0x1800173b6  jz      short loc_1800173CA
0x1800173b8  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800173bf  mov     edx, 34h ; '4'; void *
0x1800173c4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800173ca  or      [rax+8], r15
0x1800173ce  mov     rax, [rax]
0x1800173d1  mov     rcx, [rdi+28h]
0x1800173d5  mov     [rsp+118h+var_F0], rcx
0x1800173da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173df  nop
0x1800173e0  jmp     short loc_1800173FA
0x1800173e2  mov     r15d, 1
0x1800173e8  lea     r12d, [r15+3]
0x1800173ec  mov     ebx, [rsp+118h+var_D8]
0x1800173f0  mov     r14, [rsp+118h+var_D0]
0x1800173f5  mov     rdi, [rsp+118h+var_E0]
0x1800173fa  test    ebx, ebx
0x1800173fc  jz      short loc_180017459
0x1800173fe  movups  xmm1, xmmword ptr [rdi+10h]
0x180017402  movups  [rsp+118h+var_C8], xmm1
0x180017407  movsd   xmm0, qword ptr [rdi+20h]
0x18001740c  movsd   [rsp+118h+var_B8], xmm0
0x180017412  mov     rax, [rdi+4A8h]
0x180017419  movups  xmmword ptr [rax], xmm1
0x18001741c  movsd   qword ptr [rax+10h], xmm0
0x180017421  mov     r8, [rdi+4A8h]
0x180017428  mov     rdx, [r8+10h]
0x18001742c  mov     rax, [r8]
0x18001742f  cmp     rax, rdx
0x180017432  jb      loc_1800174CD
0x180017438  sub     rax, rdx
0x18001743b  cmp     rax, r12
0x18001743e  jb      loc_1800174CD
0x180017444  mov     rcx, [r8+8]
0x180017448  lea     rax, [rdx+4]
0x18001744c  mov     [r8+10h], rax
0x180017450  neg     ebx
0x180017452  mov     [rcx+rdx], ebx
0x180017455  mov     byte ptr [rdi+0Ch], 6
0x180017459  mov     rax, [rdi+4A8h]
0x180017460  cmp     qword ptr [rax], 7
0x180017464  jb      short loc_1800174CD
0x180017466  mov     rcx, [rax+8]
0x18001746a  mov     eax, [rax+10h]
0x18001746d  mov     [rcx], eax
0x18001746f  mov     al, [rdi+0Ch]
0x180017472  add     al, r15b
0x180017475  mov     [rcx+4], al
0x180017478  movzx   eax, word ptr [rdi+450h]
0x18001747f  mov     [rcx+5], ax
0x180017483  mov     rcx, [rdi+4A8h]
0x18001748a  mov     rax, [rcx]
0x18001748d  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x180017492  jnz     short loc_18001749C
0x180017494  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017498  jz      short loc_1800174CD
0x18001749a  jmp     short loc_1800174A6
0x18001749c  cmp     rax, [rcx+10h]
0x1800174a0  jb      short loc_1800174CD
0x1800174a2  mov     rax, [rcx+10h]
0x1800174a6  mov     rdx, [rcx+8]
0x1800174aa  test    rdx, rdx
0x1800174ad  jnz     short loc_1800174B4
0x1800174af  test    rax, rax
0x1800174b2  jnz     short loc_1800174CD
0x1800174b4  lea     rcx, [rdi+480h]
0x1800174bb  mov     [rcx], rax
0x1800174be  mov     [rdi+488h], rdx
0x1800174c5  call    ?TraceLogMessage@p9fs@@YAXV?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; p9fs::TraceLogMessage(gsl::span<gsl::byte const,-1>)
0x1800174ca  nop
0x1800174cb  jmp     short loc_1800174DD
0x1800174cd  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800174d3  mov     r14, [rsp+118h+var_D0]
0x1800174d8  mov     rdi, [rsp+118h+var_E0]
0x1800174dd  xor     eax, eax
0x1800174df  mov     [rdi+30h], al
0x1800174e2  mov     [r14], ax
0x1800174e6  mov     rdx, rdi
0x1800174e9  call    ??$await_suspend@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>)
0x1800174ee  jmp     short loc_180017513
0x1800174f0  xor     esi, esi; jumptable 0000000180017104 cases 0,2
0x1800174f2  lea     rcx, [rdi-10h]
0x1800174f6  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800174fc  cmp     [rdi+0Ah], si
0x180017500  jz      short loc_180017513
0x180017502  mov     edx, 4D0h; unsigned __int64
0x180017507  lea     rcx, [rdi-20h]; void *
0x18001750b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017510  jmp     short loc_180017513
0x180017512  int     3; Trap to Debugger
0x180017513  mov     rcx, [rsp+118h+var_30]
0x18001751b  xor     rcx, rsp; StackCookie
0x18001751e  call    __security_check_cookie
0x180017523  lea     r11, [rsp+118h+var_28]
0x18001752b  mov     rbx, [r11+38h]
0x18001752f  mov     rsi, [r11+40h]
0x180017533  mov     rsp, r11
0x180017536  pop     r15
0x180017538  pop     r14
0x18001753a  pop     r13
0x18001753c  pop     r12
0x18001753e  pop     rdi
0x18001753f  retn
```
