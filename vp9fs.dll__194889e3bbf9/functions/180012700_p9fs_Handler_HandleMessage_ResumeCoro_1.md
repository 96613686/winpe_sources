# p9fs::Handler::HandleMessage$_ResumeCoro$1

- ea: `0x180012700`
- end: `0x180012ea0`
- name: `p9fs::Handler::HandleMessage$_ResumeCoro$1`
- size: `1952`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180017090`

## callees

- `0x180004144`
- `0x180004534`
- `0x180005b24`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000ccb8`
- `0x1800114d0`
- `0x180012700`
- `0x1800133e0`
- `0x180015ad0`
- `0x18001c7c4`
- `0x18001c924`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180012e3d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180012e3d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012b51`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012c1a`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012ce3`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012dac`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012b51`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012c1a`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012ce3`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180012dac`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800128a0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001299e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180012a94`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800128a0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001299e`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180012a94`

## string_xrefs

- `0x180012b16`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012b95`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012be0`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012c5e`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012ca9`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012d27`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012d72`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180012df0`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall p9fs::Handler::HandleMessage__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // r14
  _QWORD *v6; // r15
  char v7; // al
  _QWORD *v8; // r8
  __int64 v9; // rbx
  _QWORD *v10; // r15
  __int64 v11; // rsi
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rsi
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rbx
  _QWORD *v21; // rcx
  __int64 v22; // rbx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rbx
  _QWORD *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rcx
  const char *v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rdx
  const char *v36; // r9
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  __int64 v41; // rdx
  const char *v42; // r9
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rdx
  const char *v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // [rsp+20h] [rbp-1F8h]
  __int64 v52; // [rsp+20h] [rbp-1F8h]
  __int64 v53; // [rsp+20h] [rbp-1F8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_65;
    case 2:
      v6 = (_QWORD *)(a1 + 16);
      v7 = *(_BYTE *)(a1 + 896);
      switch ( v7 )
      {
        case 'l':
          v22 = *(_QWORD *)(a1 + 904);
          v23 = operator new(0xA0u);
          v24 = *(_QWORD *)(v5 + 880);
          v23 += 6;
          *(_QWORD *)(a1 + 608) = v23;
          v23[11] = v24;
          v23[12] = v22;
          **(_QWORD **)(a1 + 608) = p9fs::Handler::HandleFlush__ResumeCoro_1;
          *(_DWORD *)(*(_QWORD *)(a1 + 608) + 8LL) = 65538;
          v25 = *(_QWORD *)(a1 + 608);
          *(_OWORD *)(v25 - 48) = 0;
          *(_OWORD *)(v25 - 32) = 0;
          *(_QWORD *)(v25 - 16) = 0;
          v53 = *(_QWORD *)(a1 + 608);
          *(_QWORD *)(v53 - 48) = 0;
          *(_BYTE *)(v53 - 40) = 0;
          v26 = (_QWORD *)(v53 - 32);
          *v26 = 0;
          v26[1] = 0;
          __ExceptionPtrCreate((void *)(v53 - 32));
          *(_QWORD *)(a1 + 32) = v25;
          *(_BYTE *)(*(_QWORD *)(a1 + 608) + 80LL) = 0;
          p9fs::Handler::HandleFlush__ResumeCoro_1(*(_QWORD *)(a1 + 608));
          if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) - 40LL)
            || (*(_WORD *)v5 = 8, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(a1 + 32, a1)) )
          {
LABEL_58:
            v46 = *(_QWORD *)(a1 + 32);
            if ( __ExceptionPtrToBool((const void *)(v46 - 32)) )
            {
              v49 = std::exception_ptr::exception_ptr(
                      (std::exception_ptr *)(a1 + 816),
                      (const struct std::exception_ptr *)(v46 - 32));
              std::rethrow_exception(v49);
            }
            *(_DWORD *)(a1 - 16) = *(_DWORD *)(v46 - 16);
            v50 = *(_QWORD *)(a1 + 32);
            if ( v50 )
            {
              if ( *(_WORD *)(v50 + 8) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x34,
                  (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
                  v48);
              *(_QWORD *)(v50 + 8) |= 1uLL;
              (*(void (__fastcall **)(_QWORD, __int64))v50)(*(_QWORD *)(a1 + 32), v47);
            }
            goto LABEL_64;
          }
          break;
        case 't':
          v16 = *(_QWORD *)(a1 + 912);
          v17 = *(_QWORD *)(a1 + 904);
          v18 = operator new(0xC0u);
          v19 = *(_QWORD *)(v5 + 880);
          v18 += 6;
          *(_QWORD *)(a1 + 96) = v18;
          v18[15] = v19;
          v18[16] = v17;
          v18[17] = v16;
          **(_QWORD **)(a1 + 96) = p9fs::Handler::HandleRead__ResumeCoro_1;
          *(_DWORD *)(*(_QWORD *)(a1 + 96) + 8LL) = 65538;
          v20 = *(_QWORD *)(a1 + 96);
          *(_OWORD *)(v20 - 48) = 0;
          *(_OWORD *)(v20 - 32) = 0;
          *(_QWORD *)(v20 - 16) = 0;
          v52 = *(_QWORD *)(a1 + 96);
          *(_QWORD *)(v52 - 48) = 0;
          *(_BYTE *)(v52 - 40) = 0;
          v21 = (_QWORD *)(v52 - 32);
          *v21 = 0;
          v21[1] = 0;
          __ExceptionPtrCreate((void *)(v52 - 32));
          *v6 = v20;
          *(_BYTE *)(*(_QWORD *)(a1 + 96) + 112LL) = 0;
          p9fs::Handler::HandleRead__ResumeCoro_1(*(_QWORD *)(a1 + 96));
          if ( *(_BYTE *)(*v6 - 40LL)
            || (*(_WORD *)v5 = 4, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(a1 + 16, a1)) )
          {
LABEL_46:
            v40 = *(_QWORD *)(a1 + 16);
            if ( __ExceptionPtrToBool((const void *)(v40 - 32)) )
            {
              v43 = std::exception_ptr::exception_ptr(
                      (std::exception_ptr *)(a1 + 336),
                      (const struct std::exception_ptr *)(v40 - 32));
              std::rethrow_exception(v43);
            }
            *(_DWORD *)(a1 - 16) = *(_DWORD *)(v40 - 16);
            v44 = *(_QWORD *)(a1 + 16);
            if ( v44 )
            {
              if ( *(_WORD *)(v44 + 8) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x34,
                  (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
                  v42);
              *(_QWORD *)(v44 + 8) |= 1uLL;
              (*(void (__fastcall **)(_QWORD, __int64))v44)(*(_QWORD *)(a1 + 16), v41);
            }
            goto LABEL_64;
          }
          break;
        case 'v':
          v9 = *(_QWORD *)(a1 + 912);
          v10 = (_QWORD *)(a1 + 24);
          v11 = *(_QWORD *)(a1 + 904);
          v12 = operator new(0xC0u);
          v13 = *(_QWORD *)(v5 + 880);
          v12 += 6;
          *(_QWORD *)(a1 + 352) = v12;
          v12[15] = v13;
          v12[16] = v11;
          v12[17] = v9;
          **(_QWORD **)(a1 + 352) = p9fs::Handler::HandleWrite__ResumeCoro_1;
          *(_DWORD *)(*(_QWORD *)(a1 + 352) + 8LL) = 65538;
          v14 = *(_QWORD *)(a1 + 352);
          *(_OWORD *)(v14 - 48) = 0;
          *(_OWORD *)(v14 - 32) = 0;
          *(_QWORD *)(v14 - 16) = 0;
          v51 = *(_QWORD *)(a1 + 352);
          *(_QWORD *)(v51 - 48) = 0;
          *(_BYTE *)(v51 - 40) = 0;
          v15 = (_QWORD *)(v51 - 32);
          *v15 = 0;
          v15[1] = 0;
          __ExceptionPtrCreate((void *)(v51 - 32));
          *v10 = v14;
          *(_BYTE *)(*(_QWORD *)(a1 + 352) + 112LL) = 0;
          p9fs::Handler::HandleWrite__ResumeCoro_1(*(_QWORD *)(a1 + 352));
          if ( *(_BYTE *)(*v10 - 40LL)
            || (*(_WORD *)v5 = 6, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(a1 + 24, a1)) )
          {
LABEL_34:
            v34 = *(_QWORD *)(a1 + 24);
            if ( __ExceptionPtrToBool((const void *)(v34 - 32)) )
            {
              v37 = std::exception_ptr::exception_ptr(
                      (std::exception_ptr *)(a1 + 592),
                      (const struct std::exception_ptr *)(v34 - 32));
              std::rethrow_exception(v37);
            }
            *(_DWORD *)(a1 - 16) = *(_DWORD *)(v34 - 16);
            v38 = *(_QWORD *)(a1 + 24);
            if ( v38 )
            {
              if ( *(_WORD *)(v38 + 8) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x34,
                  (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
                  v36);
              *(_QWORD *)(v38 + 8) |= 1uLL;
              (*(void (__fastcall **)(_QWORD, __int64))v38)(*(_QWORD *)(a1 + 24), v35);
            }
            goto LABEL_64;
          }
          break;
        default:
          *(_QWORD *)(a1 + 64) = a1 + 896;
          *(_QWORD *)(a1 + 72) = *(_QWORD *)(a1 + 888);
          *(_QWORD *)(a1 + 80) = *(_QWORD *)(a1 + 904);
          *(_QWORD *)(a1 + 88) = *(_QWORD *)(a1 + 912);
          v8 = (_QWORD *)p9fs::BlockingCode<_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_>(a1 + 40);
          *(_QWORD *)(a1 + 864) = v8;
          if ( !*(_BYTE *)(*v8 - 40LL) )
          {
            *(_WORD *)v5 = 10;
            if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v8, a1) )
              return;
          }
LABEL_22:
          v28 = **(_QWORD **)(a1 + 864);
          if ( __ExceptionPtrToBool((const void *)(v28 - 32)) )
          {
            v31 = std::exception_ptr::exception_ptr(
                    (std::exception_ptr *)(a1 + 832),
                    (const struct std::exception_ptr *)(v28 - 32));
            std::rethrow_exception(v31);
          }
          *(_DWORD *)(a1 - 16) = *(_DWORD *)(v28 - 16);
          v32 = *(_QWORD *)(a1 + 40);
          if ( v32 )
          {
            if ( *(_WORD *)(v32 + 8) )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x34,
                (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
                v30);
            *(_QWORD *)(v32 + 8) |= 1uLL;
            (*(void (**)(void))v32)();
          }
LABEL_64:
          *(_BYTE *)(a1 + 48) = 0;
          *(_WORD *)v5 = 0;
          p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
            v29,
            a1);
          return;
      }
      return;
    case 4:
      goto LABEL_46;
    case 5:
      v39 = *(_QWORD *)(a1 + 16);
      if ( v39 )
      {
        if ( *(_WORD *)(v39 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v39 + 8) |= 1uLL;
        (*(void (**)(void))v39)();
      }
      goto LABEL_65;
    case 6:
      goto LABEL_34;
    case 7:
      v33 = *(_QWORD *)(a1 + 24);
      if ( v33 )
      {
        if ( *(_WORD *)(v33 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v33 + 8) |= 1uLL;
        (*(void (**)(void))v33)();
      }
      goto LABEL_65;
    case 8:
      goto LABEL_58;
    case 9:
      v45 = *(_QWORD *)(a1 + 32);
      if ( v45 )
      {
        if ( *(_WORD *)(v45 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v45 + 8) |= 1uLL;
        (*(void (**)(void))v45)();
      }
      goto LABEL_65;
    case 0xA:
      goto LABEL_22;
    case 0xB:
      v27 = *(_QWORD *)(a1 + 40);
      if ( v27 )
      {
        if ( *(_WORD *)(v27 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v27 + 8) |= 1uLL;
        (*(void (**)(void))v27)();
      }
LABEL_65:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0x3D0u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180012700  mov     rax, rsp
0x180012703  mov     [rax+8], rcx
0x180012707  push    rbx
0x180012708  push    rsi
0x180012709  push    rdi
0x18001270a  push    r12
0x18001270c  push    r14
0x18001270e  push    r15
0x180012710  sub     rsp, 1E8h
0x180012717  mov     rdi, rcx
0x18001271a  mov     [rsp+218h+var_1E0], rcx
0x18001271f  lea     r14, [rdi+8]
0x180012723  mov     [rsp+218h+var_1D0], r14
0x180012728  movzx   eax, word ptr [r14]
0x18001272c  mov     [rsp+218h+var_1E8], ax
0x180012731  mov     r12d, 1
0x180012737  add     ax, r12w
0x18001273b  cmp     ax, 0Ch; switch 13 cases
0x18001273f  ja      def_18001275A; jumptable 000000018001275A default case, case 1
0x180012745  movsx   rax, ax
0x180012749  lea     rdx, cs:180000000h
0x180012750  mov     ecx, ds:(jpt_18001275A - 180000000h)[rdx+rax*4]
0x180012757  add     rcx, rdx
0x18001275a  jmp     rcx; switch jump
0x18001275c  xor     esi, esi; jumptable 000000018001275A case 4
0x18001275e  jmp     loc_180012E39
0x180012763  lea     r15, [rdi+10h]; jumptable 000000018001275A case 3
0x180012767  lea     rcx, [r15+370h]
0x18001276e  mov     al, [rcx]
0x180012770  cmp     al, 6Ch ; 'l'
0x180012772  jz      loc_1800129F8
0x180012778  cmp     al, 74h ; 't'
0x18001277a  jz      loc_180012900
0x180012780  cmp     al, 76h ; 'v'
0x180012782  jz      short loc_1800127EF
0x180012784  lea     rdx, [rdi+40h]
0x180012788  mov     [rdx], rcx
0x18001278b  mov     rax, [r14+370h]
0x180012792  mov     [rdi+48h], rax
0x180012796  mov     rax, [rdi+388h]
0x18001279d  mov     [rdi+50h], rax
0x1800127a1  mov     rax, [rdi+390h]
0x1800127a8  mov     [rdi+58h], rax
0x1800127ac  lea     rcx, [rdi+28h]
0x1800127b0  call    ??$BlockingCode@V_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_@@@p9fs@@YA?AV?$Task@J@0@V_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_@@@Z; p9fs::BlockingCode<_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_>(_lambda_ba3c1d9efddbfd0bb9bd71913ea5c746_)
0x1800127b5  mov     r8, rax
0x1800127b8  mov     [rdi+360h], rax
0x1800127bf  mov     rax, [rax]
0x1800127c2  mov     cl, [rax-28h]
0x1800127c5  nop
0x1800127c6  xor     esi, esi
0x1800127c8  test    cl, cl
0x1800127ca  jnz     loc_180012B43
0x1800127d0  lea     eax, [rsi+0Ah]
0x1800127d3  mov     [r14], ax
0x1800127d7  mov     rdx, rdi
0x1800127da  mov     rcx, r8
0x1800127dd  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x1800127e2  test    al, al
0x1800127e4  jz      loc_180012B43
0x1800127ea  jmp     loc_180012E5A
0x1800127ef  mov     rbx, [rdi+390h]
0x1800127f6  lea     r15, [rdi+18h]
0x1800127fa  mov     rsi, [r15+370h]
0x180012801  mov     ecx, 0C0h; Size
0x180012806  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001280b  mov     rcx, [r14+370h]
0x180012812  mov     [rsp+218h+var_1F8], rax
0x180012817  add     rax, 30h ; '0'
0x18001281b  mov     [rdi+160h], rax
0x180012822  mov     [rsp+218h+var_1F8], rax
0x180012827  mov     [rax+78h], rcx
0x18001282b  mov     [rax+80h], rsi
0x180012832  mov     [rax+88h], rbx
0x180012839  mov     rax, [rdi+160h]
0x180012840  mov     [rsp+218h+var_1F8], rax
0x180012845  lea     rcx, p9fs__Handler__HandleWrite$_ResumeCoro$1
0x18001284c  mov     [rax], rcx
0x18001284f  mov     rax, [rdi+160h]
0x180012856  mov     [rsp+218h+var_1F8], rax
0x18001285b  mov     dword ptr [rax+8], 10002h
0x180012862  mov     rbx, [rdi+160h]
0x180012869  mov     [rsp+218h+var_1F8], rbx
0x18001286e  xorps   xmm0, xmm0
0x180012871  xor     eax, eax
0x180012873  movups  xmmword ptr [rbx-30h], xmm0
0x180012877  movups  xmmword ptr [rbx-20h], xmm0
0x18001287b  mov     [rbx-10h], rax
0x18001287f  mov     rcx, [rdi+160h]
0x180012886  mov     [rsp+218h+var_1F8], rcx
0x18001288b  xor     esi, esi
0x18001288d  mov     [rcx-30h], rsi
0x180012891  mov     [rcx-28h], sil
0x180012895  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180012899  mov     [rcx], rsi
0x18001289c  mov     [rcx+8], rsi
0x1800128a0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800128a6  nop
0x1800128a7  mov     [r15], rbx
0x1800128aa  mov     rax, [rdi+160h]
0x1800128b1  mov     [rsp+218h+var_1F8], rax
0x1800128b6  xor     ecx, ecx
0x1800128b8  mov     [rax+70h], cl
0x1800128bb  mov     rcx, [rdi+160h]
0x1800128c2  mov     [rsp+218h+var_1F8], rcx
0x1800128c7  call    p9fs__Handler__HandleWrite$_ResumeCoro$1
0x1800128cc  nop
0x1800128cd  mov     rax, [r15]
0x1800128d0  mov     [rsp+218h+var_1F0], rax
0x1800128d5  mov     cl, [rax-28h]
0x1800128d8  nop
0x1800128d9  test    cl, cl
0x1800128db  jnz     loc_180012C0D
0x1800128e1  lea     eax, [rsi+6]
0x1800128e4  mov     [r14], ax
0x1800128e8  mov     rdx, rdi
0x1800128eb  mov     rcx, r15
0x1800128ee  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x1800128f3  test    al, al
0x1800128f5  jz      loc_180012C0D
0x1800128fb  jmp     loc_180012E5A
0x180012900  mov     rbx, [rdi+390h]
0x180012907  mov     rsi, [rdi+388h]
0x18001290e  mov     ecx, 0C0h; Size
0x180012913  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012918  mov     rcx, [r14+370h]
0x18001291f  mov     [rsp+218h+var_1F8], rax
0x180012924  add     rax, 30h ; '0'
0x180012928  mov     [rdi+60h], rax
0x18001292c  mov     [rsp+218h+var_1F8], rax
0x180012931  mov     [rax+78h], rcx
0x180012935  mov     [rax+80h], rsi
0x18001293c  mov     [rax+88h], rbx
0x180012943  mov     rax, [rdi+60h]
0x180012947  mov     [rsp+218h+var_1F8], rax
0x18001294c  lea     rcx, p9fs__Handler__HandleRead$_ResumeCoro$1
0x180012953  mov     [rax], rcx
0x180012956  mov     rax, [rdi+60h]
0x18001295a  mov     [rsp+218h+var_1F8], rax
0x18001295f  mov     dword ptr [rax+8], 10002h
0x180012966  mov     rbx, [rdi+60h]
0x18001296a  mov     [rsp+218h+var_1F8], rbx
0x18001296f  xorps   xmm0, xmm0
0x180012972  xor     eax, eax
0x180012974  movups  xmmword ptr [rbx-30h], xmm0
0x180012978  movups  xmmword ptr [rbx-20h], xmm0
0x18001297c  mov     [rbx-10h], rax
0x180012980  mov     rcx, [rdi+60h]
0x180012984  mov     [rsp+218h+var_1F8], rcx
0x180012989  xor     esi, esi
0x18001298b  mov     [rcx-30h], rsi
0x18001298f  mov     [rcx-28h], sil
0x180012993  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180012997  mov     [rcx], rsi
0x18001299a  mov     [rcx+8], rsi
0x18001299e  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800129a4  nop
0x1800129a5  mov     [r15], rbx
0x1800129a8  mov     rax, [rdi+60h]
0x1800129ac  mov     [rsp+218h+var_1F8], rax
0x1800129b1  xor     ecx, ecx
0x1800129b3  mov     [rax+70h], cl
0x1800129b6  mov     rcx, [rdi+60h]
0x1800129ba  mov     [rsp+218h+var_1F8], rcx
0x1800129bf  call    p9fs__Handler__HandleRead$_ResumeCoro$1
0x1800129c4  nop
0x1800129c5  mov     rax, [r15]
0x1800129c8  mov     [rsp+218h+var_1F0], rax
0x1800129cd  mov     dl, [rax-28h]
0x1800129d0  nop
0x1800129d1  test    dl, dl
0x1800129d3  jnz     loc_180012CD6
0x1800129d9  lea     eax, [rsi+4]
0x1800129dc  mov     [r14], ax
0x1800129e0  mov     rdx, rdi
0x1800129e3  mov     rcx, r15
0x1800129e6  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x1800129eb  test    al, al
0x1800129ed  jz      loc_180012CD6
0x1800129f3  jmp     loc_180012E5A
0x1800129f8  mov     rbx, [rdi+388h]
0x1800129ff  mov     ecx, 0A0h; Size
0x180012a04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012a09  mov     rcx, [r14+370h]
0x180012a10  mov     [rsp+218h+var_1F8], rax
0x180012a15  add     rax, 30h ; '0'
0x180012a19  mov     [rdi+260h], rax
0x180012a20  mov     [rsp+218h+var_1F8], rax
0x180012a25  mov     [rax+58h], rcx
0x180012a29  mov     [rax+60h], rbx
0x180012a2d  mov     rax, [rdi+260h]
0x180012a34  mov     [rsp+218h+var_1F8], rax
0x180012a39  lea     rcx, p9fs__Handler__HandleFlush$_ResumeCoro$1
0x180012a40  mov     [rax], rcx
0x180012a43  mov     rax, [rdi+260h]
0x180012a4a  mov     [rsp+218h+var_1F8], rax
0x180012a4f  mov     dword ptr [rax+8], 10002h
0x180012a56  mov     rbx, [rdi+260h]
0x180012a5d  mov     [rsp+218h+var_1F8], rbx
0x180012a62  xorps   xmm0, xmm0
0x180012a65  xor     eax, eax
0x180012a67  movups  xmmword ptr [rbx-30h], xmm0
0x180012a6b  movups  xmmword ptr [rbx-20h], xmm0
0x180012a6f  mov     [rbx-10h], rax
0x180012a73  mov     rcx, [rdi+260h]
0x180012a7a  mov     [rsp+218h+var_1F8], rcx
0x180012a7f  xor     esi, esi
0x180012a81  mov     [rcx-30h], rsi
0x180012a85  mov     [rcx-28h], sil
0x180012a89  add     rcx, 0FFFFFFFFFFFFFFE0h
0x180012a8d  mov     [rcx], rsi
0x180012a90  mov     [rcx+8], rsi
0x180012a94  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180012a9a  nop
0x180012a9b  lea     r15, [rdi+20h]
0x180012a9f  mov     [r15], rbx
0x180012aa2  mov     rax, [rdi+260h]
0x180012aa9  mov     [rsp+218h+var_1F8], rax
0x180012aae  xor     ecx, ecx
0x180012ab0  mov     [rax+50h], cl
0x180012ab3  mov     rcx, [rdi+260h]
0x180012aba  mov     [rsp+218h+var_1F8], rcx
0x180012abf  call    p9fs__Handler__HandleFlush$_ResumeCoro$1
0x180012ac4  nop
0x180012ac5  mov     rax, [r15]
0x180012ac8  mov     [rsp+218h+var_1F0], rax
0x180012acd  mov     dl, [rax-28h]
0x180012ad0  nop
0x180012ad1  test    dl, dl
0x180012ad3  jnz     loc_180012D9F
0x180012ad9  lea     eax, [rsi+8]
0x180012adc  mov     [r14], ax
0x180012ae0  mov     rdx, rdi
0x180012ae3  mov     rcx, r15
0x180012ae6  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180012aeb  test    al, al
0x180012aed  jz      loc_180012D9F
0x180012af3  jmp     loc_180012E5A
0x180012af8  mov     rax, [rdi+28h]; jumptable 000000018001275A case 12
0x180012afc  mov     [rsp+218h+var_1F0], rax
0x180012b01  xor     esi, esi
0x180012b03  test    rax, rax
0x180012b06  jz      short loc_180012B3C
0x180012b08  mov     rcx, [rsp+218h]; this
0x180012b10  cmp     [rax+8], si
0x180012b14  jz      short loc_180012B26
0x180012b16  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180012b1d  lea     edx, [rsi+34h]; void *
0x180012b20  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180012b26  or      [rax+8], r12
0x180012b2a  mov     rax, [rax]
0x180012b2d  mov     rcx, [rdi+28h]
0x180012b31  mov     [rsp+218h+var_1F0], rcx
0x180012b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b3b  nop
0x180012b3c  jmp     loc_180012E39
0x180012b41  xor     esi, esi; jumptable 000000018001275A case 11
0x180012b43  mov     rbx, [rdi+360h]
0x180012b4a  mov     rbx, [rbx]
0x180012b4d  lea     rcx, [rbx-20h]
0x180012b51  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180012b57  test    al, al
0x180012b59  jz      short loc_180012B73
0x180012b5b  lea     rcx, [rdi+340h]; this
0x180012b62  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x180012b66  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180012b6b  mov     rcx, rax
0x180012b6e  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180012b73  mov     eax, [rbx-10h]
0x180012b76  mov     [rdi-10h], eax
0x180012b79  mov     rax, [rdi+28h]
0x180012b7d  mov     [rsp+218h+var_1F0], rax
0x180012b82  test    rax, rax
0x180012b85  jz      short loc_180012BBD
0x180012b87  mov     rcx, [rsp+218h]; this
0x180012b8f  cmp     [rax+8], si
0x180012b93  jz      short loc_180012BA7
0x180012b95  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180012b9c  mov     edx, 34h ; '4'; void *
0x180012ba1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180012ba7  or      [rax+8], r12
0x180012bab  mov     rax, [rax]
0x180012bae  mov     rcx, [rdi+28h]
0x180012bb2  mov     [rsp+218h+var_1F0], rcx
0x180012bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bbc  nop
0x180012bbd  jmp     loc_180012E24
0x180012bc2  mov     rax, [rdi+18h]; jumptable 000000018001275A case 8
0x180012bc6  mov     [rsp+218h+var_1F0], rax
0x180012bcb  xor     esi, esi
0x180012bcd  test    rax, rax
0x180012bd0  jz      short loc_180012C06
0x180012bd2  mov     rcx, [rsp+218h]; this
0x180012bda  cmp     [rax+8], si
0x180012bde  jz      short loc_180012BF0
0x180012be0  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180012be7  lea     edx, [rsi+34h]; void *
0x180012bea  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180012bf0  or      [rax+8], r12
0x180012bf4  mov     rax, [rax]
  ... truncated ...
```
