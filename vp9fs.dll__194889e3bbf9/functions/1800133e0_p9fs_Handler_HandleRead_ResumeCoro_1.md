# p9fs::Handler::HandleRead$_ResumeCoro$1

- ea: `0x1800133e0`
- end: `0x1800138a8`
- name: `p9fs::Handler::HandleRead$_ResumeCoro$1`
- size: `1224`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180012700`

## callees

- `0x180004120`
- `0x180004534`
- `0x180005b24`
- `0x180005dd0`
- `0x1800074e0`
- `0x180010020`
- `0x1800133e0`
- `0x180016840`
- `0x18001c7c4`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180013843`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180013843`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800136aa`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800136aa`

## string_xrefs

- `0x180013613`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x1800136ec`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall p9fs::Handler::HandleRead__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // r15
  _OWORD *v6; // rbx
  gsl::details *v7; // rcx
  unsigned __int64 v8; // rdx
  const char *v9; // r9
  unsigned __int64 v10; // r8
  __int64 v11; // r10
  unsigned int v12; // r11d
  __int64 v13; // r9
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r12
  __int64 v17; // rsi
  __int64 v18; // r13
  __int64 v19; // rdx
  gsl::details *v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rax
  volatile signed __int32 *v26; // r14
  __int64 v27; // rbx
  gsl::details *v28; // rcx
  const char *v29; // r9
  std::exception_ptr *v30; // rcx
  char v31; // r12
  unsigned __int64 v32; // rbx
  __int64 v33; // rax
  volatile signed __int32 *v34; // rsi
  unsigned __int64 *v35; // r8
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // rcx
  _QWORD *v38; // r8
  volatile signed __int32 *v39; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_50;
    case 2:
      v6 = (_OWORD *)(a1 + 16);
      v7 = *(gsl::details **)(a1 + 128);
      v8 = *((_QWORD *)v7 + 2);
      if ( *(_QWORD *)v7 - v8 < 4 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          a4);
      if ( *(_QWORD *)v7 < v8 )
        goto LABEL_18;
      v9 = (const char *)*((_QWORD *)v7 + 1);
      *((_QWORD *)v7 + 2) = v8 + 4;
      v7 = *(gsl::details **)(a1 + 128);
      v10 = *((_QWORD *)v7 + 2);
      if ( *(_QWORD *)v7 - v10 < 8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          v9);
      if ( *(_QWORD *)v7 < v10 )
        goto LABEL_18;
      v11 = *((_QWORD *)v7 + 1);
      v12 = *(_DWORD *)&v9[v8];
      *((_QWORD *)v7 + 2) = v10 + 8;
      v13 = *(_QWORD *)(a1 + 128);
      v14 = *(_QWORD *)(v13 + 16);
      if ( *(_QWORD *)v13 - v14 < 4 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          (const char *)v13);
      if ( *(_QWORD *)v13 < v14 )
LABEL_18:
        gsl::details::terminate(v7);
      v15 = *(_QWORD *)(v13 + 8);
      v16 = *(_QWORD *)(v11 + v10);
      *(_QWORD *)(v13 + 16) = v14 + 4;
      v17 = *(unsigned int *)(v15 + v14);
      *v6 = 0;
      v18 = *(_QWORD *)(v5 + 112);
      p9fs::Handler::LookupFid(v18, a1 + 16, v12);
      LOBYTE(v19) = 117;
      p9fs::Handler::MessageResponse::EnsureSize(
        *(_QWORD *)(a1 + 136),
        v19,
        (unsigned int)v17,
        *(unsigned int *)(v18 + 112));
      v20 = *(gsl::details **)(a1 + 136);
      v21 = *((_QWORD *)v20 + 2);
      if ( *(_QWORD *)v20 < v21 || *(_QWORD *)v20 - v21 < v17 + 4 || (unsigned __int64)(v17 + 4) < 4 )
        gsl::details::terminate(v20);
      v22 = *((_QWORD *)v20 + 1) + 4LL;
      v23 = *(_QWORD *)v6;
      *(_QWORD *)(a1 + 48) = v17;
      *(_QWORD *)(a1 + 56) = v22 + v21;
      v24 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v23 + 64LL))(v23, a1 + 32, v16);
      *(_QWORD *)(a1 + 96) = v24;
      if ( !*(_BYTE *)(*v24 - 40LL) )
      {
        *(_WORD *)v5 = 4;
        if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v24, a1) )
          return;
      }
      goto LABEL_28;
    case 4:
LABEL_28:
      v27 = **(_QWORD **)(a1 + 96);
      if ( __ExceptionPtrToBool((const void *)(v27 - 32)) )
      {
        v30 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)(a1 + 64),
                (const struct std::exception_ptr *)(v27 - 32));
        std::rethrow_exception(v30);
      }
      v31 = *(_BYTE *)(v27 - 16);
      v32 = *(unsigned int *)(v27 - 12);
      v33 = *(_QWORD *)(a1 + 32);
      if ( v33 )
      {
        if ( *(_WORD *)(v33 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v29);
        *(_QWORD *)(v33 + 8) |= 1uLL;
        (*(void (**)(void))v33)();
      }
      if ( v31 )
      {
        v35 = *(unsigned __int64 **)(a1 + 136);
        v36 = v35[2];
        if ( *v35 < v36
          || *v35 - v36 < 4
          || (v37 = v35[1],
              v35[2] = v36 + 4,
              *(_DWORD *)(v37 + v36) = v32,
              v38 = *(_QWORD **)(a1 + 136),
              v28 = (gsl::details *)v38[2],
              *v38 < (unsigned __int64)v28)
          || *v38 - (_QWORD)v28 < v32 )
        {
          gsl::details::terminate(v28);
        }
        v38[2] = (char *)v28 + v32;
        *(_DWORD *)(a1 - 16) = 0;
        if ( *(_QWORD *)(a1 + 24) )
        {
          v39 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
            if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
          }
        }
      }
      else
      {
        *(_DWORD *)(a1 - 16) = v32;
        if ( *(_QWORD *)(a1 + 24) )
        {
          v34 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
            if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
          }
        }
      }
      *(_BYTE *)(a1 + 40) = 0;
      *(_WORD *)v5 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
        v28,
        a1);
      break;
    case 5:
      v25 = *(_QWORD *)(a1 + 32);
      if ( v25 )
      {
        if ( *(_WORD *)(v25 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v25 + 8) |= 1uLL;
        (*(void (**)(void))v25)();
        *(_QWORD *)(a1 + 32) = 0;
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v26 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
LABEL_50:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0xC0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1800133e0  mov     r11, rsp
0x1800133e3  mov     [r11+10h], rbx
0x1800133e7  mov     [r11+18h], rsi
0x1800133eb  mov     [r11+8], rcx
0x1800133ef  push    rdi
0x1800133f0  push    r12
0x1800133f2  push    r13
0x1800133f4  push    r14
0x1800133f6  push    r15
0x1800133f8  sub     rsp, 80h
0x1800133ff  mov     rax, cs:__security_cookie
0x180013406  xor     rax, rsp
0x180013409  mov     [rsp+0A8h+var_30], rax
0x18001340e  mov     rdi, rcx
0x180013411  mov     [rsp+0A8h+var_68], rcx
0x180013416  lea     r15, [rdi+8]
0x18001341a  mov     [rsp+0A8h+var_60], r15
0x18001341f  movzx   eax, word ptr [r15]
0x180013423  mov     [rsp+0A8h+var_78], ax
0x180013428  mov     r13d, 1
0x18001342e  add     ax, r13w
0x180013432  cmp     ax, 6; switch 7 cases
0x180013436  ja      def_180013451; jumptable 0000000180013451 default case, case 1
0x18001343c  movsx   rax, ax
0x180013440  lea     rdx, cs:180000000h
0x180013447  mov     ecx, ds:(jpt_180013451 - 180000000h)[rdx+rax*4]
0x18001344e  add     rcx, rdx
0x180013451  jmp     rcx; switch jump
0x180013453  xor     esi, esi; jumptable 0000000180013451 case 4
0x180013455  jmp     loc_18001383F
0x18001345a  lea     rbx, [rdi+10h]; jumptable 0000000180013451 case 3
0x18001345e  mov     rcx, [rbx+70h]; this
0x180013462  mov     rdx, [rcx+10h]
0x180013466  mov     rax, [rcx]
0x180013469  sub     rax, rdx
0x18001346c  mov     r14d, 4
0x180013472  cmp     rax, r14
0x180013475  jnb     short loc_180013490
0x180013477  mov     rcx, [rsp+0A8h]; this
0x18001347f  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180013486  lea     edx, [r14+25h]; void *
0x18001348a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013490  cmp     [rcx], rdx
0x180013493  jb      loc_1800135EF
0x180013499  mov     r9, [rcx+8]; char *
0x18001349d  lea     rax, [rdx+4]
0x1800134a1  mov     [rcx+10h], rax
0x1800134a5  mov     rcx, [rbx+70h]
0x1800134a9  mov     r8, [rcx+10h]
0x1800134ad  mov     rax, [rcx]
0x1800134b0  sub     rax, r8
0x1800134b3  cmp     rax, 8
0x1800134b7  jnb     short loc_1800134D3
0x1800134b9  mov     rcx, [rsp+0A8h]; this
0x1800134c1  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x1800134c8  mov     edx, 29h ; ')'; void *
0x1800134cd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800134d3  cmp     [rcx], r8
0x1800134d6  jb      loc_1800135EF
0x1800134dc  mov     r10, [rcx+8]
0x1800134e0  mov     r11d, [r9+rdx]
0x1800134e4  lea     rax, [r8+8]
0x1800134e8  mov     [rcx+10h], rax
0x1800134ec  mov     r9, [rbx+70h]; char *
0x1800134f0  mov     rdx, [r9+10h]
0x1800134f4  mov     rax, [r9]
0x1800134f7  sub     rax, rdx
0x1800134fa  cmp     rax, r14
0x1800134fd  jnb     short loc_180013519
0x1800134ff  mov     rcx, [rsp+0A8h]; this
0x180013507  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x18001350e  mov     edx, 29h ; ')'; void *
0x180013513  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013519  cmp     [r9], rdx
0x18001351c  jb      loc_1800135EF
0x180013522  mov     rcx, [r9+8]
0x180013526  mov     r12, [r10+r8]
0x18001352a  lea     rax, [rdx+4]
0x18001352e  mov     [r9+10h], rax
0x180013532  mov     esi, [rcx+rdx]
0x180013535  xorps   xmm0, xmm0
0x180013538  movups  xmmword ptr [rbx], xmm0
0x18001353b  mov     r13, [r15+70h]
0x18001353f  mov     r8d, r11d
0x180013542  mov     rdx, rbx
0x180013545  mov     rcx, r13
0x180013548  call    ?LookupFid@Handler@p9fs@@AEAA?AV?$shared_ptr@VFid@p9fs@@@std@@I@Z; p9fs::Handler::LookupFid(uint)
0x18001354d  nop
0x18001354e  mov     r9d, [r13+70h]
0x180013552  mov     r8d, esi
0x180013555  mov     dl, 75h ; 'u'
0x180013557  mov     rcx, [rdi+88h]
0x18001355e  call    ?EnsureSize@MessageResponse@Handler@p9fs@@QEAAXW4MessageType@3@II@Z; p9fs::Handler::MessageResponse::EnsureSize(p9fs::MessageType,uint,uint)
0x180013563  mov     rcx, [rdi+88h]; this
0x18001356a  mov     rdx, [rcx+10h]
0x18001356e  mov     rax, [rcx]
0x180013571  cmp     rax, rdx
0x180013574  jb      short loc_1800135E9
0x180013576  lea     r8, [rsi+4]
0x18001357a  sub     rax, rdx
0x18001357d  cmp     rax, r8
0x180013580  jb      short loc_1800135E9
0x180013582  cmp     r8, r14
0x180013585  jb      short loc_1800135E9
0x180013587  mov     rax, [rcx+8]
0x18001358b  add     rax, 4
0x18001358f  add     rdx, rax
0x180013592  mov     rcx, [rbx]
0x180013595  mov     [rsp+0A8h+var_50], rcx
0x18001359a  lea     r9, [rdi+30h]
0x18001359e  mov     [r9], rsi
0x1800135a1  mov     [rdi+38h], rdx
0x1800135a5  mov     rax, [rcx]
0x1800135a8  lea     rdx, [rdi+20h]
0x1800135ac  mov     r8, r12
0x1800135af  mov     rax, [rax+40h]
0x1800135b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b8  mov     rcx, rax
0x1800135bb  mov     [rdi+60h], rax
0x1800135bf  mov     rax, [rax]
0x1800135c2  mov     dl, [rax-28h]
0x1800135c5  nop
0x1800135c6  xor     esi, esi
0x1800135c8  test    dl, dl
0x1800135ca  jnz     loc_180013699
0x1800135d0  mov     [r15], r14w
0x1800135d4  mov     rdx, rdi
0x1800135d7  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x1800135dc  test    al, al
0x1800135de  jz      loc_180013699
0x1800135e4  jmp     loc_180013860
0x1800135e9  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800135ef  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800135f5  mov     rax, [rdi+20h]; jumptable 0000000180013451 case 6
0x1800135f9  mov     [rsp+0A8h+var_70], rax
0x1800135fe  xor     esi, esi
0x180013600  test    rax, rax
0x180013603  jz      short loc_18001363C
0x180013605  mov     rcx, [rsp+0A8h]; this
0x18001360d  cmp     [rax+8], si
0x180013611  jz      short loc_180013623
0x180013613  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18001361a  lea     edx, [rsi+34h]; void *
0x18001361d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013623  or      [rax+8], r13
0x180013627  mov     rax, [rax]
0x18001362a  mov     rcx, [rdi+20h]
0x18001362e  mov     [rsp+0A8h+var_70], rcx
0x180013633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013638  mov     [rdi+20h], rsi
0x18001363c  mov     rax, [rdi+18h]
0x180013640  mov     [rsp+0A8h+var_48], rax
0x180013645  test    rax, rax
0x180013648  jz      short loc_18001368C
0x18001364a  mov     r14, [rdi+18h]
0x18001364e  mov     [rsp+0A8h+var_48], r14
0x180013653  or      ebx, 0FFFFFFFFh
0x180013656  mov     eax, ebx
0x180013658  lock xadd [r14+8], eax
0x18001365e  add     eax, ebx
0x180013660  jnz     short loc_18001368C
0x180013662  mov     rax, [r14]
0x180013665  mov     rcx, r14
0x180013668  mov     rax, [rax]
0x18001366b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013670  mov     eax, ebx
0x180013672  lock xadd [r14+0Ch], eax
0x180013678  add     eax, ebx
0x18001367a  jnz     short loc_18001368C
0x18001367c  mov     rax, [r14]
0x18001367f  mov     rcx, r14
0x180013682  mov     rax, [rax+8]
0x180013686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001368b  nop
0x18001368c  jmp     loc_18001383F
0x180013691  xor     esi, esi; jumptable 0000000180013451 case 5
0x180013693  lea     r14d, [rsi+4]
0x180013697  jmp     short loc_18001369F
0x180013699  mov     r13d, 1
0x18001369f  mov     rbx, [rdi+60h]
0x1800136a3  mov     rbx, [rbx]
0x1800136a6  lea     rcx, [rbx-20h]
0x1800136aa  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800136b0  test    al, al
0x1800136b2  jz      short loc_1800136C9
0x1800136b4  lea     rcx, [rdi+40h]; this
0x1800136b8  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x1800136bc  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x1800136c1  mov     rcx, rax
0x1800136c4  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x1800136c9  mov     r12b, [rbx-10h]
0x1800136cd  mov     ebx, [rbx-0Ch]
0x1800136d0  mov     rax, [rdi+20h]
0x1800136d4  mov     [rsp+0A8h+var_70], rax
0x1800136d9  test    rax, rax
0x1800136dc  jz      short loc_180013713
0x1800136de  mov     rcx, [rsp+0A8h]; this
0x1800136e6  cmp     [rax+8], si
0x1800136ea  jz      short loc_1800136FE
0x1800136ec  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800136f3  mov     edx, 34h ; '4'; void *
0x1800136f8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800136fe  or      [rax+8], r13
0x180013702  mov     rax, [rax]
0x180013705  mov     rcx, [rdi+20h]
0x180013709  mov     [rsp+0A8h+var_70], rcx
0x18001370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013713  test    r12b, r12b
0x180013716  jnz     short loc_18001376E
0x180013718  mov     [rdi-10h], ebx
0x18001371b  mov     rax, [rdi+18h]
0x18001371f  mov     [rsp+0A8h+var_48], rax
0x180013724  test    rax, rax
0x180013727  jz      short loc_180013769
0x180013729  mov     rsi, [rdi+18h]
0x18001372d  mov     [rsp+0A8h+var_48], rsi
0x180013732  or      ebx, 0FFFFFFFFh
0x180013735  mov     eax, ebx
0x180013737  lock xadd [rsi+8], eax
0x18001373c  add     eax, ebx
0x18001373e  jnz     short loc_180013769
0x180013740  mov     rax, [rsi]
0x180013743  mov     rcx, rsi
0x180013746  mov     rax, [rax]
0x180013749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001374e  mov     eax, ebx
0x180013750  lock xadd [rsi+0Ch], eax
0x180013755  add     eax, ebx
0x180013757  jnz     short loc_180013769
0x180013759  mov     rax, [rsi]
0x18001375c  mov     rcx, rsi
0x18001375f  mov     rax, [rax+8]
0x180013763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013768  nop
0x180013769  jmp     loc_180013824
0x18001376e  mov     r8, [rdi+88h]
0x180013775  mov     rdx, [r8+10h]
0x180013779  mov     rax, [r8]
0x18001377c  cmp     rax, rdx
0x18001377f  jb      loc_180013837
0x180013785  sub     rax, rdx
0x180013788  cmp     rax, r14
0x18001378b  jb      loc_180013837
0x180013791  mov     rcx, [r8+8]
0x180013795  lea     rax, [rdx+4]
0x180013799  mov     [r8+10h], rax
0x18001379d  mov     [rcx+rdx], ebx
0x1800137a0  mov     r8, [rdi+88h]
0x1800137a7  mov     rcx, [r8+10h]
0x1800137ab  mov     rax, [r8]
0x1800137ae  cmp     rax, rcx
0x1800137b1  jb      loc_180013837
0x1800137b7  sub     rax, rcx
0x1800137ba  cmp     rax, rbx
0x1800137bd  jb      short loc_180013837
0x1800137bf  lea     rax, [rcx+rbx]
0x1800137c3  mov     [r8+10h], rax
0x1800137c7  mov     [rdi-10h], esi
0x1800137ca  mov     rax, [rdi+18h]
0x1800137ce  mov     [rsp+0A8h+var_48], rax
0x1800137d3  test    rax, rax
0x1800137d6  jz      short loc_180013818
0x1800137d8  mov     rsi, [rdi+18h]
0x1800137dc  mov     [rsp+0A8h+var_48], rsi
0x1800137e1  or      ebx, 0FFFFFFFFh
0x1800137e4  mov     eax, ebx
0x1800137e6  lock xadd [rsi+8], eax
0x1800137eb  add     eax, ebx
0x1800137ed  jnz     short loc_180013818
0x1800137ef  mov     rax, [rsi]
0x1800137f2  mov     rcx, rsi
0x1800137f5  mov     rax, [rax]
0x1800137f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137fd  mov     eax, ebx
0x1800137ff  lock xadd [rsi+0Ch], eax
0x180013804  add     eax, ebx
0x180013806  jnz     short loc_180013818
0x180013808  mov     rax, [rsi]
0x18001380b  mov     rcx, rsi
0x18001380e  mov     rax, [rax+8]
0x180013812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013817  nop
0x180013818  jmp     short loc_180013824
0x18001381a  mov     rdi, [rsp+0A8h+var_68]
0x18001381f  mov     r15, [rsp+0A8h+var_60]
0x180013824  xor     eax, eax
0x180013826  mov     [rdi+28h], al
0x180013829  mov     [r15], ax
0x18001382d  mov     rdx, rdi
0x180013830  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x180013835  jmp     short loc_180013860
0x180013837  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001383d  xor     esi, esi; jumptable 0000000180013451 cases 0,2
0x18001383f  lea     rcx, [rdi-20h]
0x180013843  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180013849  cmp     [rdi+0Ah], si
0x18001384d  jz      short loc_180013860
0x18001384f  mov     edx, 0C0h; unsigned __int64
0x180013854  lea     rcx, [rdi-30h]; void *
0x180013858  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
  ... truncated ...
```
