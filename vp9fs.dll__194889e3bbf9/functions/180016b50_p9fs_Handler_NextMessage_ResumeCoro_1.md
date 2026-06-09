# p9fs::Handler::NextMessage$_ResumeCoro$1

- ea: `0x180016b50`
- end: `0x180016f58`
- name: `p9fs::Handler::NextMessage$_ResumeCoro$1`
- size: `1032`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1800183c0`

## callees

- `0x180004120`
- `0x180004534`
- `0x180005b24`
- `0x180005dd0`
- `0x1800074e0`
- `0x180010424`
- `0x180016b50`
- `0x18001c75c`
- `0x18001c7c4`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180016eef`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180016eef`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180016c7d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180016e18`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180016c7d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180016e18`

## string_xrefs

- `0x180016c3e`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180016cbb`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180016de0`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180016e56`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180016d62`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall p9fs::Handler::NextMessage__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // r14
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  gsl::details *v10; // rcx
  __int64 v11; // rcx
  char v12; // bl
  __int64 v13; // rax
  __int64 v14; // r10
  unsigned int *v15; // r8
  unsigned __int64 v16; // r8
  char v17; // al
  _QWORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  const char *v21; // r9
  __int64 v22; // rcx
  char v23; // bl
  __int64 v24; // rax
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rdx
  __int64 v27; // r8
  unsigned __int64 v28; // rax
  int v29; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_50;
    case 2:
      v6 = *(_QWORD *)(a1 + 152);
      if ( *(_QWORD *)(v6 + 80) >= 4u )
        goto LABEL_18;
      v7 = p9fs::Handler::FillData(v6, (_QWORD *)(a1 + 16), 4, *(_QWORD *)(a1 + 160));
      *(_QWORD *)(a1 + 128) = v7;
      if ( !*(_BYTE *)(*v7 - 40LL) )
      {
        *(_WORD *)v5 = 4;
        if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v7, a1) )
          return;
      }
LABEL_10:
      v9 = **(_QWORD **)(a1 + 128);
      if ( __ExceptionPtrToBool((const void *)(v9 - 32)) )
      {
        v11 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)(a1 + 64),
                (const struct std::exception_ptr *)(v9 - 32));
        std::rethrow_exception(v11);
      }
      v12 = *(_BYTE *)(v9 - 16);
      v13 = *(_QWORD *)(a1 + 16);
      if ( v13 )
      {
        if ( *(_WORD *)(v13 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v13 + 8) |= 1uLL;
        (*(void (**)(void))v13)();
      }
      if ( !v12 )
      {
        *(_QWORD *)(a1 - 16) = 0;
        *(_QWORD *)(a1 - 8) = 0;
LABEL_48:
        *(_BYTE *)(a1 + 32) = 0;
        *(_WORD *)v5 = 0;
        p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
          v10,
          a1);
        return;
      }
LABEL_18:
      v14 = *(_QWORD *)(v5 + 144);
      v10 = *(gsl::details **)(v14 + 80);
      if ( v10 == (gsl::details *)-1LL )
        goto LABEL_49;
      v15 = *(unsigned int **)(v14 + 88);
      if ( !v15 )
      {
        if ( !v10 )
LABEL_23:
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
            a4);
LABEL_49:
        gsl::details::terminate(v10);
      }
      if ( (unsigned __int64)v10 < 4 )
        goto LABEL_23;
      v16 = *v15;
      if ( (unsigned int)v16 < 7 || (v17 = 0, (unsigned int)v16 > *(_DWORD *)(v14 + 112)) )
        v17 = 1;
      if ( v17 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4B9,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
          (const char *)0x8007000DLL,
          v29);
      *(_QWORD *)(a1 + 48) = v16;
      if ( (unsigned __int64)v10 >= v16 )
        goto LABEL_45;
      v18 = p9fs::Handler::FillData(v14, (_QWORD *)(a1 + 24), v16, *(_QWORD *)(a1 + 160));
      *(_QWORD *)(a1 + 112) = v18;
      if ( *(_BYTE *)(*v18 - 40LL)
        || (*(_WORD *)v5 = 6, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v18, a1)) )
      {
LABEL_37:
        v20 = **(_QWORD **)(a1 + 112);
        if ( __ExceptionPtrToBool((const void *)(v20 - 32)) )
        {
          v22 = std::exception_ptr::exception_ptr(
                  (std::exception_ptr *)(a1 + 80),
                  (const struct std::exception_ptr *)(v20 - 32));
          std::rethrow_exception(v22);
        }
        v23 = *(_BYTE *)(v20 - 16);
        v24 = *(_QWORD *)(a1 + 24);
        if ( v24 )
        {
          if ( *(_WORD *)(v24 + 8) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x34,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
              v21);
          *(_QWORD *)(v24 + 8) |= 1uLL;
          (*(void (__fastcall **)(_QWORD))v24)(*(_QWORD *)(a1 + 24));
        }
        if ( !v23 )
        {
          *(_QWORD *)(a1 - 16) = 0;
          *(_QWORD *)(a1 - 8) = 0;
          goto LABEL_48;
        }
LABEL_45:
        v10 = *(gsl::details **)(v5 + 144);
        v25 = *((_QWORD *)v10 + 10);
        v26 = *(_QWORD *)(a1 + 48);
        if ( v25 >= v26 )
        {
          v27 = *((_QWORD *)v10 + 11);
          v28 = v25 - v26;
          if ( v28 != -1 )
          {
            *((_QWORD *)v10 + 10) = v28;
            *((_QWORD *)v10 + 11) = v26 + v27;
            *(_QWORD *)(a1 - 16) = *(_QWORD *)(a1 + 48);
            *(_QWORD *)(a1 - 8) = v27;
            goto LABEL_48;
          }
        }
        goto LABEL_49;
      }
      return;
    case 4:
      goto LABEL_10;
    case 5:
      v8 = *(_QWORD *)(a1 + 16);
      if ( v8 )
      {
        if ( *(_WORD *)(v8 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v8 + 8) |= 1uLL;
        (*(void (**)(void))v8)();
      }
      goto LABEL_50;
    case 6:
      goto LABEL_37;
    case 7:
      v19 = *(_QWORD *)(a1 + 24);
      if ( v19 )
      {
        if ( *(_WORD *)(v19 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v19 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD))v19)(*(_QWORD *)(a1 + 24));
      }
LABEL_50:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0xE0u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180016b50  mov     r11, rsp
0x180016b53  mov     [r11+10h], rbx
0x180016b57  mov     [r11+18h], rsi
0x180016b5b  mov     [r11+8], rcx
0x180016b5f  push    rdi
0x180016b60  push    r12
0x180016b62  push    r13
0x180016b64  push    r14
0x180016b66  push    r15
0x180016b68  sub     rsp, 70h
0x180016b6c  mov     rax, cs:__security_cookie
0x180016b73  xor     rax, rsp
0x180016b76  mov     [rsp+98h+var_38], rax
0x180016b7b  mov     rsi, rcx
0x180016b7e  mov     [rsp+98h+var_60], rcx
0x180016b83  lea     r14, [rsi+8]
0x180016b87  mov     [rsp+98h+var_58], r14
0x180016b8c  movzx   eax, word ptr [r14]
0x180016b90  mov     [rsp+98h+var_70], ax
0x180016b95  mov     r13d, 1
0x180016b9b  add     ax, r13w
0x180016b9f  cmp     ax, 8; switch 9 cases
0x180016ba3  ja      def_180016BBE; jumptable 0000000180016BBE default case, case 1
0x180016ba9  movsx   rax, ax
0x180016bad  lea     rdx, cs:180000000h
0x180016bb4  mov     ecx, ds:(jpt_180016BBE - 180000000h)[rdx+rax*4]
0x180016bbb  add     rcx, rdx
0x180016bbe  jmp     rcx; switch jump
0x180016bc0  xor     edi, edi; jumptable 0000000180016BBE case 4
0x180016bc2  jmp     loc_180016EEB
0x180016bc7  mov     rcx, [r14+90h]; jumptable 0000000180016BBE case 3
0x180016bce  mov     r15d, 4
0x180016bd4  cmp     [rcx+50h], r15
0x180016bd8  jnb     short loc_180016C19
0x180016bda  lea     rdx, [rsi+10h]
0x180016bde  mov     r9, [rdx+90h]
0x180016be5  mov     r8d, r15d
0x180016be8  call    ?FillData@Handler@p9fs@@AEAA?AV?$Task@_N@2@IAEAVCancelToken@2@@Z; p9fs::Handler::FillData(uint,p9fs::CancelToken &)
0x180016bed  mov     rcx, rax
0x180016bf0  mov     [rsi+80h], rax
0x180016bf7  mov     rax, [rax]
0x180016bfa  mov     dl, [rax-28h]
0x180016bfd  nop
0x180016bfe  xor     edi, edi
0x180016c00  test    dl, dl
0x180016c02  jnz     short loc_180016C6F
0x180016c04  mov     [r14], r15w
0x180016c08  mov     rdx, rsi
0x180016c0b  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180016c10  test    al, al
0x180016c12  jz      short loc_180016C6F
0x180016c14  jmp     loc_180016F0C
0x180016c19  xor     edi, edi
0x180016c1b  jmp     loc_180016CF3
0x180016c20  mov     rax, [rsi+10h]; jumptable 0000000180016BBE case 6
0x180016c24  mov     [rsp+98h+var_68], rax
0x180016c29  xor     edi, edi
0x180016c2b  test    rax, rax
0x180016c2e  jz      short loc_180016C64
0x180016c30  mov     rcx, [rsp+98h]; this
0x180016c38  cmp     [rax+8], di
0x180016c3c  jz      short loc_180016C4E
0x180016c3e  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016c45  lea     edx, [rdi+34h]; void *
0x180016c48  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016c4e  or      [rax+8], r13
0x180016c52  mov     rax, [rax]
0x180016c55  mov     rcx, [rsi+10h]
0x180016c59  mov     [rsp+98h+var_68], rcx
0x180016c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c63  nop
0x180016c64  jmp     loc_180016EEB
0x180016c69  xor     edi, edi; jumptable 0000000180016BBE case 5
0x180016c6b  lea     r15d, [rdi+4]
0x180016c6f  mov     rbx, [rsi+80h]
0x180016c76  mov     rbx, [rbx]
0x180016c79  lea     rcx, [rbx-20h]
0x180016c7d  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180016c83  test    al, al
0x180016c85  jz      short loc_180016C9C
0x180016c87  lea     rcx, [rsi+40h]; this
0x180016c8b  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x180016c8f  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180016c94  mov     rcx, rax
0x180016c97  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180016c9c  mov     bl, [rbx-10h]
0x180016c9f  mov     rax, [rsi+10h]
0x180016ca3  mov     [rsp+98h+var_68], rax
0x180016ca8  test    rax, rax
0x180016cab  jz      short loc_180016CE2
0x180016cad  mov     rcx, [rsp+98h]; this
0x180016cb5  cmp     [rax+8], di
0x180016cb9  jz      short loc_180016CCD
0x180016cbb  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016cc2  mov     edx, 34h ; '4'; void *
0x180016cc7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016ccd  or      [rax+8], r13
0x180016cd1  mov     rax, [rax]
0x180016cd4  mov     rcx, [rsi+10h]
0x180016cd8  mov     [rsp+98h+var_68], rcx
0x180016cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce2  test    bl, bl
0x180016ce4  jnz     short loc_180016CF3
0x180016ce6  mov     [rsi-10h], rdi
0x180016cea  mov     [rsi-8], rdi
0x180016cee  jmp     loc_180016ED0
0x180016cf3  mov     r10, [r14+90h]
0x180016cfa  mov     rcx, [r10+50h]; this
0x180016cfe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016d02  jz      loc_180016EE3
0x180016d08  mov     r8, [r10+58h]
0x180016d0c  test    r8, r8
0x180016d0f  jnz     short loc_180016D1C
0x180016d11  test    rcx, rcx
0x180016d14  jnz     loc_180016EE3
0x180016d1a  jmp     short loc_180016D21
0x180016d1c  cmp     rcx, r15
0x180016d1f  jnb     short loc_180016D3B
0x180016d21  mov     rcx, [rsp+98h]; this
0x180016d29  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180016d30  mov     edx, 29h ; ')'; void *
0x180016d35  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016d3b  mov     r8d, [r8]
0x180016d3e  cmp     r8d, 7
0x180016d42  jb      short loc_180016D4D
0x180016d44  cmp     r8d, [r10+70h]
0x180016d48  mov     al, dil
0x180016d4b  jbe     short loc_180016D50
0x180016d4d  mov     al, r13b
0x180016d50  mov     r11, [rsp+98h]
0x180016d58  test    al, al
0x180016d5a  jz      short loc_180016D76
0x180016d5c  mov     r9d, 8007000Dh; char *
0x180016d62  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016d69  mov     edx, 4B9h; void *
0x180016d6e  mov     rcx, r11; this
0x180016d71  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016d76  mov     [rsi+30h], r8
0x180016d7a  cmp     rcx, r8
0x180016d7d  jnb     loc_180016E8B
0x180016d83  lea     rdx, [rsi+18h]
0x180016d87  mov     r9, [rsi+0A0h]
0x180016d8e  mov     rcx, r10
0x180016d91  call    ?FillData@Handler@p9fs@@AEAA?AV?$Task@_N@2@IAEAVCancelToken@2@@Z; p9fs::Handler::FillData(uint,p9fs::CancelToken &)
0x180016d96  mov     rcx, rax
0x180016d99  mov     [rsi+70h], rax
0x180016d9d  mov     rax, [rax]
0x180016da0  mov     dl, [rax-28h]
0x180016da3  nop
0x180016da4  test    dl, dl
0x180016da6  jnz     short loc_180016E0D
0x180016da8  mov     eax, 6
0x180016dad  mov     [r14], ax
0x180016db1  mov     rdx, rsi
0x180016db4  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180016db9  test    al, al
0x180016dbb  jz      short loc_180016E0D
0x180016dbd  jmp     loc_180016F0C
0x180016dc2  mov     rax, [rsi+18h]; jumptable 0000000180016BBE case 8
0x180016dc6  mov     [rsp+98h+var_78], rax
0x180016dcb  xor     edi, edi
0x180016dcd  test    rax, rax
0x180016dd0  jz      short loc_180016E06
0x180016dd2  mov     rcx, [rsp+98h]; this
0x180016dda  cmp     [rax+8], di
0x180016dde  jz      short loc_180016DF0
0x180016de0  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016de7  lea     edx, [rdi+34h]; void *
0x180016dea  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016df0  or      [rax+8], r13
0x180016df4  mov     rax, [rax]
0x180016df7  mov     rcx, [rsi+18h]
0x180016dfb  mov     [rsp+98h+var_78], rcx
0x180016e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e05  nop
0x180016e06  jmp     loc_180016EEB
0x180016e0b  xor     edi, edi; jumptable 0000000180016BBE case 7
0x180016e0d  mov     rbx, [rsi+70h]
0x180016e11  mov     rbx, [rbx]
0x180016e14  lea     rcx, [rbx-20h]
0x180016e18  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180016e1e  test    al, al
0x180016e20  jz      short loc_180016E37
0x180016e22  lea     rcx, [rsi+50h]; this
0x180016e26  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x180016e2a  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180016e2f  mov     rcx, rax
0x180016e32  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180016e37  mov     bl, [rbx-10h]
0x180016e3a  mov     rax, [rsi+18h]
0x180016e3e  mov     [rsp+98h+var_78], rax
0x180016e43  test    rax, rax
0x180016e46  jz      short loc_180016E7D
0x180016e48  mov     rcx, [rsp+98h]; this
0x180016e50  cmp     [rax+8], di
0x180016e54  jz      short loc_180016E68
0x180016e56  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016e5d  mov     edx, 34h ; '4'; void *
0x180016e62  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016e68  or      [rax+8], r13
0x180016e6c  mov     rax, [rax]
0x180016e6f  mov     rcx, [rsi+18h]
0x180016e73  mov     [rsp+98h+var_78], rcx
0x180016e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e7d  test    bl, bl
0x180016e7f  jnz     short loc_180016E8B
0x180016e81  mov     [rsi-10h], rdi
0x180016e85  mov     [rsi-8], rdi
0x180016e89  jmp     short loc_180016ED0
0x180016e8b  mov     rcx, [r14+90h]
0x180016e92  mov     rax, [rcx+50h]
0x180016e96  mov     rdx, [rsi+30h]
0x180016e9a  cmp     rax, rdx
0x180016e9d  jb      short loc_180016EE3
0x180016e9f  mov     r8, [rcx+58h]
0x180016ea3  sub     rax, rdx
0x180016ea6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016eaa  jz      short loc_180016EE3
0x180016eac  mov     [rcx+50h], rax
0x180016eb0  lea     rax, [rdx+r8]
0x180016eb4  mov     [rcx+58h], rax
0x180016eb8  mov     rax, [rsi+30h]
0x180016ebc  mov     [rsi-10h], rax
0x180016ec0  mov     [rsi-8], r8
0x180016ec4  jmp     short loc_180016ED0
0x180016ec6  mov     rsi, [rsp+98h+var_60]
0x180016ecb  mov     r14, [rsp+98h+var_58]
0x180016ed0  xor     eax, eax
0x180016ed2  mov     [rsi+20h], al
0x180016ed5  mov     [r14], ax
0x180016ed9  mov     rdx, rsi
0x180016edc  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x180016ee1  jmp     short loc_180016F0C
0x180016ee3  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180016ee9  xor     edi, edi; jumptable 0000000180016BBE cases 0,2
0x180016eeb  lea     rcx, [rsi-20h]
0x180016eef  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180016ef5  cmp     [rsi+0Ah], di
0x180016ef9  jz      short loc_180016F0C
0x180016efb  mov     edx, 0E0h; unsigned __int64
0x180016f00  lea     rcx, [rsi-30h]; void *
0x180016f04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016f09  jmp     short loc_180016F0C
0x180016f0b  int     3; Trap to Debugger
0x180016f0c  mov     rcx, [rsp+98h+var_38]
0x180016f11  xor     rcx, rsp; StackCookie
0x180016f14  call    __security_check_cookie
0x180016f19  lea     r11, [rsp+98h+var_28]
0x180016f1e  mov     rbx, [r11+38h]
0x180016f22  mov     rsi, [r11+40h]
0x180016f26  mov     rsp, r11
0x180016f29  pop     r15
0x180016f2b  pop     r14
0x180016f2d  pop     r13
0x180016f2f  pop     r12
0x180016f31  pop     rdi
0x180016f32  retn
```
