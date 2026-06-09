# p9fs::Handler::HandleWrite$_ResumeCoro$1

- ea: `0x180015ad0`
- end: `0x180015f78`
- name: `p9fs::Handler::HandleWrite$_ResumeCoro$1`
- size: `1192`
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
- `0x180015ad0`
- `0x180016840`
- `0x18001c7c4`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180015f11`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180015f11`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180015d8e`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180015d8e`

## string_xrefs

- `0x180015cf7`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180015dd0`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall p9fs::Handler::HandleWrite__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // r14
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
  __int64 v16; // r13
  _QWORD *v17; // r8
  unsigned __int64 v18; // rsi
  char *v19; // r12
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rax
  volatile signed __int32 *v23; // r14
  __int64 v24; // rbx
  __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  const char *v27; // r9
  std::exception_ptr *v28; // rcx
  char v29; // r12
  int v30; // ebx
  __int64 v31; // rax
  volatile signed __int32 *v32; // rsi
  gsl::details *v33; // rcx
  unsigned __int64 *v34; // r8
  unsigned __int64 v35; // rdx
  volatile signed __int32 *v36; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v5 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_48;
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
        goto LABEL_17;
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
        goto LABEL_17;
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
        goto LABEL_17;
      v15 = *(_QWORD *)(v13 + 8);
      v16 = *(_QWORD *)(v11 + v10);
      *(_QWORD *)(v13 + 16) = v14 + 4;
      v17 = *(_QWORD **)(a1 + 128);
      v18 = *(unsigned int *)(v15 + v14);
      v7 = (gsl::details *)v17[2];
      if ( *v17 - (_QWORD)v7 < v18 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x29,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
          (const char *)v13);
      if ( *v17 < (unsigned __int64)v7 )
LABEL_17:
        gsl::details::terminate(v7);
      v19 = (char *)v7 + v17[1];
      v17[2] = (char *)v7 + v18;
      *v6 = 0;
      p9fs::Handler::LookupFid(*(_QWORD *)(v5 + 112), a1 + 16, v12);
      v20 = *(_QWORD *)v6;
      *(_QWORD *)(a1 + 48) = v18;
      *(_QWORD *)(a1 + 56) = v19;
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v20 + 72LL))(v20, a1 + 32, v16);
      *(_QWORD *)(a1 + 96) = v21;
      if ( !*(_BYTE *)(*v21 - 40LL) )
      {
        *(_WORD *)v5 = 4;
        if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v21, a1) )
          return;
      }
      goto LABEL_27;
    case 4:
LABEL_27:
      v24 = **(_QWORD **)(a1 + 96);
      if ( __ExceptionPtrToBool((const void *)(v24 - 32)) )
      {
        v28 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)(a1 + 64),
                (const struct std::exception_ptr *)(v24 - 32));
        std::rethrow_exception(v28);
      }
      v29 = *(_BYTE *)(v24 - 16);
      v30 = *(_DWORD *)(v24 - 12);
      v31 = *(_QWORD *)(a1 + 32);
      if ( v31 )
      {
        if ( *(_WORD *)(v31 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v27);
        *(_QWORD *)(v31 + 8) |= 1uLL;
        (*(void (**)(void))v31)();
      }
      if ( v29 )
      {
        LOBYTE(v25) = 119;
        p9fs::Handler::MessageResponse::EnsureSize(
          *(_QWORD *)(a1 + 136),
          v25,
          0,
          *(unsigned int *)(*(_QWORD *)(v5 + 112) + 112LL));
        v34 = *(unsigned __int64 **)(a1 + 136);
        v35 = v34[2];
        if ( *v34 < v35 || *v34 - v35 < 4 )
          gsl::details::terminate(v33);
        v26 = v34[1];
        v34[2] = v35 + 4;
        *(_DWORD *)(v26 + v35) = v30;
        *(_DWORD *)(a1 - 16) = 0;
        if ( *(_QWORD *)(a1 + 24) )
        {
          v36 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
            if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
          }
        }
      }
      else
      {
        *(_DWORD *)(a1 - 16) = v30;
        if ( *(_QWORD *)(a1 + 24) )
        {
          v32 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
            if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
      }
      *(_BYTE *)(a1 + 40) = 0;
      *(_WORD *)v5 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
        v26,
        a1);
      break;
    case 5:
      v22 = *(_QWORD *)(a1 + 32);
      if ( v22 )
      {
        if ( *(_WORD *)(v22 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v22 + 8) |= 1uLL;
        (*(void (**)(void))v22)();
        *(_QWORD *)(a1 + 32) = 0;
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v23 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
LABEL_48:
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
0x180015ad0  mov     r11, rsp
0x180015ad3  mov     [r11+10h], rbx
0x180015ad7  mov     [r11+18h], rsi
0x180015adb  mov     [r11+8], rcx
0x180015adf  push    rdi
0x180015ae0  push    r12
0x180015ae2  push    r13
0x180015ae4  push    r14
0x180015ae6  push    r15
0x180015ae8  sub     rsp, 80h
0x180015aef  mov     rax, cs:__security_cookie
0x180015af6  xor     rax, rsp
0x180015af9  mov     [rsp+0A8h+var_30], rax
0x180015afe  mov     rdi, rcx
0x180015b01  mov     [rsp+0A8h+var_68], rcx
0x180015b06  lea     r14, [rdi+8]
0x180015b0a  mov     [rsp+0A8h+var_60], r14
0x180015b0f  movzx   eax, word ptr [r14]
0x180015b13  mov     [rsp+0A8h+var_78], ax
0x180015b18  mov     r13d, 1
0x180015b1e  add     ax, r13w
0x180015b22  cmp     ax, 6; switch 7 cases
0x180015b26  ja      def_180015B41; jumptable 0000000180015B41 default case, case 1
0x180015b2c  movsx   rax, ax
0x180015b30  lea     rdx, cs:180000000h
0x180015b37  mov     ecx, ds:(jpt_180015B41 - 180000000h)[rdx+rax*4]
0x180015b3e  add     rcx, rdx
0x180015b41  jmp     rcx; switch jump
0x180015b43  xor     esi, esi; jumptable 0000000180015B41 case 4
0x180015b45  jmp     loc_180015F0D
0x180015b4a  lea     rbx, [rdi+10h]; jumptable 0000000180015B41 case 3
0x180015b4e  mov     rcx, [rbx+70h]; this
0x180015b52  mov     rdx, [rcx+10h]
0x180015b56  mov     rax, [rcx]
0x180015b59  sub     rax, rdx
0x180015b5c  mov     r15d, 4
0x180015b62  cmp     rax, r15
0x180015b65  jnb     short loc_180015B80
0x180015b67  mov     rcx, [rsp+0A8h]; this
0x180015b6f  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180015b76  lea     edx, [r15+25h]; void *
0x180015b7a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015b80  cmp     [rcx], rdx
0x180015b83  jb      loc_180015CD3
0x180015b89  mov     r9, [rcx+8]; char *
0x180015b8d  lea     rax, [rdx+4]
0x180015b91  mov     [rcx+10h], rax
0x180015b95  mov     rcx, [rbx+70h]
0x180015b99  mov     r8, [rcx+10h]
0x180015b9d  mov     rax, [rcx]
0x180015ba0  sub     rax, r8
0x180015ba3  cmp     rax, 8
0x180015ba7  jnb     short loc_180015BC3
0x180015ba9  mov     rcx, [rsp+0A8h]; this
0x180015bb1  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180015bb8  mov     edx, 29h ; ')'; void *
0x180015bbd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015bc3  cmp     [rcx], r8
0x180015bc6  jb      loc_180015CD3
0x180015bcc  mov     r10, [rcx+8]
0x180015bd0  mov     r11d, [r9+rdx]
0x180015bd4  lea     rax, [r8+8]
0x180015bd8  mov     [rcx+10h], rax
0x180015bdc  mov     r9, [rbx+70h]; char *
0x180015be0  mov     rdx, [r9+10h]
0x180015be4  mov     rax, [r9]
0x180015be7  sub     rax, rdx
0x180015bea  cmp     rax, r15
0x180015bed  jnb     short loc_180015C09
0x180015bef  mov     rcx, [rsp+0A8h]; this
0x180015bf7  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180015bfe  mov     edx, 29h ; ')'; void *
0x180015c03  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015c09  cmp     [r9], rdx
0x180015c0c  jb      loc_180015CD3
0x180015c12  mov     rcx, [r9+8]
0x180015c16  mov     r13, [r10+r8]
0x180015c1a  lea     rax, [rdx+4]
0x180015c1e  mov     [r9+10h], rax
0x180015c22  mov     r8, [rbx+70h]
0x180015c26  mov     esi, [rcx+rdx]
0x180015c29  mov     rcx, [r8+10h]
0x180015c2d  mov     rax, [r8]
0x180015c30  sub     rax, rcx
0x180015c33  cmp     rax, rsi
0x180015c36  jnb     short loc_180015C52
0x180015c38  mov     rcx, [rsp+0A8h]; this
0x180015c40  lea     r8, aOnecoreVmDvSto_7; "onecore\\vm\\dv\\storage\\plan9\\inc\\p"...
0x180015c47  mov     edx, 29h ; ')'; void *
0x180015c4c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015c52  cmp     [r8], rcx
0x180015c55  jb      short loc_180015CD3
0x180015c57  mov     r12, [r8+8]
0x180015c5b  add     r12, rcx
0x180015c5e  lea     rax, [rsi+rcx]
0x180015c62  mov     [r8+10h], rax
0x180015c66  xorps   xmm0, xmm0
0x180015c69  movups  xmmword ptr [rbx], xmm0
0x180015c6c  mov     r8d, r11d
0x180015c6f  mov     rdx, rbx
0x180015c72  mov     rcx, [r14+70h]
0x180015c76  call    ?LookupFid@Handler@p9fs@@AEAA?AV?$shared_ptr@VFid@p9fs@@@std@@I@Z; p9fs::Handler::LookupFid(uint)
0x180015c7b  nop
0x180015c7c  mov     rcx, [rbx]
0x180015c7f  mov     [rsp+0A8h+var_50], rcx
0x180015c84  lea     r9, [rdi+30h]
0x180015c88  mov     [r9], rsi
0x180015c8b  mov     [rdi+38h], r12
0x180015c8f  mov     rax, [rcx]
0x180015c92  lea     rdx, [rdi+20h]
0x180015c96  mov     r8, r13
0x180015c99  mov     rax, [rax+48h]
0x180015c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca2  mov     rcx, rax
0x180015ca5  mov     [rdi+60h], rax
0x180015ca9  mov     rax, [rax]
0x180015cac  mov     dl, [rax-28h]
0x180015caf  nop
0x180015cb0  xor     esi, esi
0x180015cb2  test    dl, dl
0x180015cb4  jnz     loc_180015D7D
0x180015cba  mov     [r14], r15w
0x180015cbe  mov     rdx, rdi
0x180015cc1  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180015cc6  test    al, al
0x180015cc8  jz      loc_180015D7D
0x180015cce  jmp     loc_180015F2E
0x180015cd3  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180015cd9  mov     rax, [rdi+20h]; jumptable 0000000180015B41 case 6
0x180015cdd  mov     [rsp+0A8h+var_70], rax
0x180015ce2  xor     esi, esi
0x180015ce4  test    rax, rax
0x180015ce7  jz      short loc_180015D20
0x180015ce9  mov     rcx, [rsp+0A8h]; this
0x180015cf1  cmp     [rax+8], si
0x180015cf5  jz      short loc_180015D07
0x180015cf7  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180015cfe  lea     edx, [rsi+34h]; void *
0x180015d01  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015d07  or      [rax+8], r13
0x180015d0b  mov     rax, [rax]
0x180015d0e  mov     rcx, [rdi+20h]
0x180015d12  mov     [rsp+0A8h+var_70], rcx
0x180015d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d1c  mov     [rdi+20h], rsi
0x180015d20  mov     rax, [rdi+18h]
0x180015d24  mov     [rsp+0A8h+var_48], rax
0x180015d29  test    rax, rax
0x180015d2c  jz      short loc_180015D70
0x180015d2e  mov     r14, [rdi+18h]
0x180015d32  mov     [rsp+0A8h+var_48], r14
0x180015d37  or      ebx, 0FFFFFFFFh
0x180015d3a  mov     eax, ebx
0x180015d3c  lock xadd [r14+8], eax
0x180015d42  add     eax, ebx
0x180015d44  jnz     short loc_180015D70
0x180015d46  mov     rax, [r14]
0x180015d49  mov     rcx, r14
0x180015d4c  mov     rax, [rax]
0x180015d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d54  mov     eax, ebx
0x180015d56  lock xadd [r14+0Ch], eax
0x180015d5c  add     eax, ebx
0x180015d5e  jnz     short loc_180015D70
0x180015d60  mov     rax, [r14]
0x180015d63  mov     rcx, r14
0x180015d66  mov     rax, [rax+8]
0x180015d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d6f  nop
0x180015d70  jmp     loc_180015F0D
0x180015d75  xor     esi, esi; jumptable 0000000180015B41 case 5
0x180015d77  lea     r15d, [rsi+4]
0x180015d7b  jmp     short loc_180015D83
0x180015d7d  mov     r13d, 1
0x180015d83  mov     rbx, [rdi+60h]
0x180015d87  mov     rbx, [rbx]
0x180015d8a  lea     rcx, [rbx-20h]
0x180015d8e  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180015d94  test    al, al
0x180015d96  jz      short loc_180015DAD
0x180015d98  lea     rcx, [rdi+40h]; this
0x180015d9c  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x180015da0  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180015da5  mov     rcx, rax
0x180015da8  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180015dad  mov     r12b, [rbx-10h]
0x180015db1  mov     ebx, [rbx-0Ch]
0x180015db4  mov     rax, [rdi+20h]
0x180015db8  mov     [rsp+0A8h+var_70], rax
0x180015dbd  test    rax, rax
0x180015dc0  jz      short loc_180015DF7
0x180015dc2  mov     rcx, [rsp+0A8h]; this
0x180015dca  cmp     [rax+8], si
0x180015dce  jz      short loc_180015DE2
0x180015dd0  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180015dd7  mov     edx, 34h ; '4'; void *
0x180015ddc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015de2  or      [rax+8], r13
0x180015de6  mov     rax, [rax]
0x180015de9  mov     rcx, [rdi+20h]
0x180015ded  mov     [rsp+0A8h+var_70], rcx
0x180015df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df7  test    r12b, r12b
0x180015dfa  jnz     short loc_180015E52
0x180015dfc  mov     [rdi-10h], ebx
0x180015dff  mov     rax, [rdi+18h]
0x180015e03  mov     [rsp+0A8h+var_48], rax
0x180015e08  test    rax, rax
0x180015e0b  jz      short loc_180015E4D
0x180015e0d  mov     rsi, [rdi+18h]
0x180015e11  mov     [rsp+0A8h+var_48], rsi
0x180015e16  or      ebx, 0FFFFFFFFh
0x180015e19  mov     eax, ebx
0x180015e1b  lock xadd [rsi+8], eax
0x180015e20  add     eax, ebx
0x180015e22  jnz     short loc_180015E4D
0x180015e24  mov     rax, [rsi]
0x180015e27  mov     rcx, rsi
0x180015e2a  mov     rax, [rax]
0x180015e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e32  mov     eax, ebx
0x180015e34  lock xadd [rsi+0Ch], eax
0x180015e39  add     eax, ebx
0x180015e3b  jnz     short loc_180015E4D
0x180015e3d  mov     rax, [rsi]
0x180015e40  mov     rcx, rsi
0x180015e43  mov     rax, [rax+8]
0x180015e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e4c  nop
0x180015e4d  jmp     loc_180015EF8
0x180015e52  mov     r9, [r14+70h]
0x180015e56  mov     r9d, [r9+70h]
0x180015e5a  xor     r8d, r8d
0x180015e5d  mov     dl, 77h ; 'w'
0x180015e5f  mov     rcx, [rdi+88h]
0x180015e66  call    ?EnsureSize@MessageResponse@Handler@p9fs@@QEAAXW4MessageType@3@II@Z; p9fs::Handler::MessageResponse::EnsureSize(p9fs::MessageType,uint,uint)
0x180015e6b  mov     r8, [rdi+88h]
0x180015e72  mov     rdx, [r8+10h]
0x180015e76  mov     rax, [r8]
0x180015e79  cmp     rax, rdx
0x180015e7c  jb      short loc_180015EE8
0x180015e7e  sub     rax, rdx
0x180015e81  cmp     rax, r15
0x180015e84  jb      short loc_180015EE8
0x180015e86  mov     rcx, [r8+8]
0x180015e8a  lea     rax, [rdx+4]
0x180015e8e  mov     [r8+10h], rax
0x180015e92  mov     [rcx+rdx], ebx
0x180015e95  mov     [rdi-10h], esi
0x180015e98  mov     rax, [rdi+18h]
0x180015e9c  mov     [rsp+0A8h+var_48], rax
0x180015ea1  test    rax, rax
0x180015ea4  jz      short loc_180015EE6
0x180015ea6  mov     rsi, [rdi+18h]
0x180015eaa  mov     [rsp+0A8h+var_48], rsi
0x180015eaf  or      ebx, 0FFFFFFFFh
0x180015eb2  mov     eax, ebx
0x180015eb4  lock xadd [rsi+8], eax
0x180015eb9  add     eax, ebx
0x180015ebb  jnz     short loc_180015EE6
0x180015ebd  mov     rax, [rsi]
0x180015ec0  mov     rcx, rsi
0x180015ec3  mov     rax, [rax]
0x180015ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ecb  mov     eax, ebx
0x180015ecd  lock xadd [rsi+0Ch], eax
0x180015ed2  add     eax, ebx
0x180015ed4  jnz     short loc_180015EE6
0x180015ed6  mov     rax, [rsi]
0x180015ed9  mov     rcx, rsi
0x180015edc  mov     rax, [rax+8]
0x180015ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ee5  nop
0x180015ee6  jmp     short loc_180015EF8
0x180015ee8  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180015eee  mov     r14, [rsp+0A8h+var_60]
0x180015ef3  mov     rdi, [rsp+0A8h+var_68]
0x180015ef8  xor     eax, eax
0x180015efa  mov     [rdi+28h], al
0x180015efd  mov     [r14], ax
0x180015f01  mov     rdx, rdi
0x180015f04  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x180015f09  jmp     short loc_180015F2E
0x180015f0b  xor     esi, esi; jumptable 0000000180015B41 cases 0,2
0x180015f0d  lea     rcx, [rdi-20h]
0x180015f11  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180015f17  cmp     [rdi+0Ah], si
0x180015f1b  jz      short loc_180015F2E
0x180015f1d  mov     edx, 0C0h; unsigned __int64
0x180015f22  lea     rcx, [rdi-30h]; void *
0x180015f26  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f2b  jmp     short loc_180015F2E
0x180015f2d  int     3; Trap to Debugger
0x180015f2e  mov     rcx, [rsp+0A8h+var_30]
0x180015f33  xor     rcx, rsp; StackCookie
0x180015f36  call    __security_check_cookie
0x180015f3b  lea     r11, [rsp+0A8h+var_28]
0x180015f43  mov     rbx, [r11+38h]
0x180015f47  mov     rsi, [r11+40h]
0x180015f4b  mov     rsp, r11
  ... truncated ...
```
