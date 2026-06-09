# p9fs::File::Read$_ResumeCoro$1

- ea: `0x180020600`
- end: `0x18002096c`
- name: `p9fs::File::Read$_ResumeCoro$1`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180020980`

## callees

- `0x180004120`
- `0x180004534`
- `0x180004c80`
- `0x180005b24`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000e334`
- `0x18001c7c4`
- `0x18001c924`
- `0x18001c970`
- `0x180020600`
- `0x180029770`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180020915`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180020915`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180020816`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180020816`
- `lxutil!LxUtilFsReadAppExecLink` at `0x1800206c3`
- `lxutil!LxUtilFsReadAppExecLink` at `0x1800206c3`

## string_xrefs

- `0x1800207c8`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180020860`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall p9fs::File::Read__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  _WORD *v5; // r14
  __int64 v6; // r15
  __int64 v7; // rcx
  int AppExecLink; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rbx
  _QWORD *Async; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // edx
  const char *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v5 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_35;
    case 2:
      v6 = *(_QWORD *)(a1 + 280);
      if ( ((*(_QWORD *)(v6 + 48) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v7 = a1 - 16;
        if ( a1 + 192 != a1 - 16 )
        {
          *(_DWORD *)(v7 + 4) = -9;
          *(_BYTE *)v7 = 0;
        }
LABEL_34:
        *(_BYTE *)(a1 + 168) = 0;
        *v5 = 0;
        p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
          v7,
          a1);
        return;
      }
      if ( *(_BYTE *)(v6 + 113) )
      {
        AppExecLink = LxUtilFsReadAppExecLink(*(_QWORD *)(a1 + 288), *(_QWORD *)(a1 + 304), *(_QWORD *)(a1 + 296));
        v9 = a1 - 16;
        v7 = a1 + 200;
        if ( a1 + 200 != a1 - 16 )
        {
          *(_DWORD *)(v9 + 4) = AppExecLink;
          *(_BYTE *)v9 = 1;
        }
        goto LABEL_34;
      }
      v10 = (_DWORD *)(a1 + 16);
      memset_0((void *)(a1 + 20), 0, 0x84u);
      *(_DWORD *)(a1 + 20) = 0;
      *(_OWORD *)(a1 + 40) = 0;
      *(_OWORD *)(a1 + 56) = 0;
      *(_OWORD *)(a1 + 72) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      *(_DWORD *)(a1 + 88) = -1;
      *v10 = 2;
      *(_DWORD *)(a1 + 92) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      *(_BYTE *)(a1 + 104) = 0;
      *(_QWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 128) = 0;
      *(_OWORD *)(a1 + 136) = 0;
      *(_QWORD *)(a1 + 128) = a1 + 120;
      *(_QWORD *)(a1 + 120) = a1 + 120;
      *(_OWORD *)(a1 + 176) = *(_OWORD *)(a1 + 296);
      Async = (_QWORD *)p9fs::ReadAsync((int)a1 + 160, (int)v6 + 56, *(_QWORD *)(a1 + 288), (int)a1 + 176, a1 + 16);
      *(_QWORD *)(a1 + 256) = Async;
      if ( *(_BYTE *)(*Async - 40LL)
        || (*v5 = 4, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(Async, a1)) )
      {
LABEL_18:
        v13 = **(_QWORD **)(a1 + 256);
        if ( __ExceptionPtrToBool((const void *)(v13 - 32)) )
        {
          v16 = std::exception_ptr::exception_ptr(
                  (std::exception_ptr *)(a1 + 208),
                  (const struct std::exception_ptr *)(v13 - 32));
          std::rethrow_exception(v16);
        }
        v17 = *(_QWORD *)(v13 - 16);
        v18 = *(_QWORD *)(a1 + 160);
        if ( v18 )
        {
          if ( *(_WORD *)(v18 + 8) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x34,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
              v15);
          *(_QWORD *)(v18 + 8) |= 1uLL;
          (*(void (**)(void))v18)();
        }
        if ( !(_DWORD)v17 || (_DWORD)v17 == 38 )
        {
          v21 = a1 - 16;
          if ( a1 + 248 != a1 - 16 )
          {
            *(_DWORD *)(v21 + 4) = HIDWORD(v17);
            *(_BYTE *)v21 = 1;
          }
        }
        else
        {
          if ( (int)v17 > 0 )
            LODWORD(v17) = (unsigned __int16)v17 | 0x80070000;
          v19 = p9fs::util::HResultToLinuxError((p9fs::util *)(unsigned int)v17, v14);
          v20 = a1 - 16;
          if ( a1 + 240 != a1 - 16 )
          {
            *(_DWORD *)(v20 + 4) = v19;
            *(_BYTE *)v20 = 0;
          }
        }
        p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 16));
        goto LABEL_34;
      }
      return;
    case 4:
      goto LABEL_18;
    case 5:
      v12 = *(_QWORD *)(a1 + 160);
      if ( v12 )
      {
        if ( *(_WORD *)(v12 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v12 + 8) |= 1uLL;
        (*(void (**)(void))v12)();
        *(_QWORD *)(a1 + 160) = 0;
      }
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 16));
LABEL_35:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0x170u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180020600  mov     r11, rsp
0x180020603  mov     [r11+8], rcx
0x180020607  push    rbx
0x180020608  push    rsi
0x180020609  push    rdi
0x18002060a  push    r12
0x18002060c  push    r14
0x18002060e  push    r15
0x180020610  sub     rsp, 78h
0x180020614  mov     rax, cs:__security_cookie
0x18002061b  xor     rax, rsp
0x18002061e  mov     [rsp+0A8h+var_40], rax
0x180020623  mov     rdi, rcx
0x180020626  mov     [rsp+0A8h+var_68], rcx
0x18002062b  lea     r14, [rdi+8]
0x18002062f  mov     [rsp+0A8h+var_58], r14
0x180020634  movzx   eax, word ptr [r14]
0x180020638  mov     [rsp+0A8h+var_78], ax
0x18002063d  mov     r12d, 1
0x180020643  add     ax, r12w
0x180020647  cmp     ax, 6; switch 7 cases
0x18002064b  ja      def_180020666; jumptable 0000000180020666 default case, case 1
0x180020651  movsx   rax, ax
0x180020655  lea     rdx, cs:180000000h
0x18002065c  mov     ecx, ds:(jpt_180020666 - 180000000h)[rdx+rax*4]
0x180020663  add     rcx, rdx
0x180020666  jmp     rcx; switch jump
0x180020668  xor     esi, esi; jumptable 0000000180020666 case 4
0x18002066a  jmp     loc_180020911
0x18002066f  mov     r15, [r14+110h]; jumptable 0000000180020666 case 3
0x180020676  mov     rax, [r15+30h]
0x18002067a  add     rax, r12
0x18002067d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180020683  jnz     short loc_1800206A6
0x180020685  lea     rcx, [rdi-10h]
0x180020689  lea     rax, [rdi+0C0h]
0x180020690  cmp     rax, rcx
0x180020693  jz      short loc_1800206A1
0x180020695  mov     dword ptr [rcx+4], 0FFFFFFF7h
0x18002069c  xor     esi, esi
0x18002069e  mov     [rcx], sil
0x1800206a1  jmp     loc_1800208F9
0x1800206a6  xor     esi, esi
0x1800206a8  cmp     [r15+71h], sil
0x1800206ac  jz      short loc_1800206E4
0x1800206ae  mov     r8, [rdi+128h]
0x1800206b5  mov     rdx, [rdi+130h]
0x1800206bc  mov     rcx, [rdi+120h]
0x1800206c3  call    cs:__imp_LxUtilFsReadAppExecLink
0x1800206c9  lea     rdx, [rdi-10h]
0x1800206cd  lea     rcx, [rdi+0C8h]
0x1800206d4  cmp     rcx, rdx
0x1800206d7  jz      short loc_1800206DF
0x1800206d9  mov     [rdx+4], eax
0x1800206dc  mov     [rdx], r12b
0x1800206df  jmp     loc_1800208F9
0x1800206e4  lea     rbx, [rdi+10h]
0x1800206e8  lea     rcx, [rbx+4]; void *
0x1800206ec  xor     edx, edx; Val
0x1800206ee  mov     r8d, 84h; Size
0x1800206f4  call    memset_0
0x1800206f9  xor     eax, eax
0x1800206fb  mov     [rdi+14h], eax
0x1800206fe  xorps   xmm0, xmm0
0x180020701  movups  xmmword ptr [rdi+28h], xmm0
0x180020705  movups  xmmword ptr [rdi+38h], xmm0
0x180020709  movups  xmmword ptr [rdi+48h], xmm0
0x18002070d  mov     [rdi+18h], rsi
0x180020711  mov     [rdi+20h], rsi
0x180020715  mov     dword ptr [rdi+58h], 0FFFFFFFFh
0x18002071c  mov     dword ptr [rbx], 2
0x180020722  mov     [rdi+5Ch], esi
0x180020725  mov     [rdi+60h], rsi
0x180020729  mov     [rdi+68h], al
0x18002072c  mov     [rdi+70h], rsi
0x180020730  lea     rax, [rdi+78h]
0x180020734  mov     [rax+8], rsi
0x180020738  movups  xmmword ptr [rdi+88h], xmm0
0x18002073f  mov     [rdi+80h], rax
0x180020746  mov     [rax], rax
0x180020749  lea     r9, [rdi+0B0h]
0x180020750  movups  xmm0, xmmword ptr [rdi+128h]
0x180020757  movdqu  xmmword ptr [r9], xmm0
0x18002075c  lea     rdx, [r15+38h]
0x180020760  lea     rcx, [rdi+0A0h]
0x180020767  mov     [rsp+0A8h+var_88], rbx
0x18002076c  mov     r8, [rbx+110h]
0x180020773  call    ?ReadAsync@p9fs@@YA?AV?$Task@UIoResult@p9fs@@@1@AEAUCoroutineIoIssuer@1@_KV?$span@W4byte@gsl@@$0?0@gsl@@AEAVCancelToken@1@@Z; p9fs::ReadAsync(p9fs::CoroutineIoIssuer &,unsigned __int64,gsl::span<gsl::byte,-1>,p9fs::CancelToken &)
0x180020778  mov     rcx, rax
0x18002077b  mov     [rdi+100h], rax
0x180020782  mov     rax, [rax]
0x180020785  mov     dl, [rax-28h]
0x180020788  nop
0x180020789  test    dl, dl
0x18002078b  jnz     short loc_180020808
0x18002078d  mov     eax, 4
0x180020792  mov     [r14], ax
0x180020796  mov     rdx, rdi
0x180020799  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x18002079e  test    al, al
0x1800207a0  jz      short loc_180020808
0x1800207a2  jmp     loc_180020932
0x1800207a7  mov     rax, [rdi+0A0h]; jumptable 0000000180020666 case 6
0x1800207ae  mov     [rsp+0A8h+var_70], rax
0x1800207b3  xor     esi, esi
0x1800207b5  test    rax, rax
0x1800207b8  jz      short loc_1800207F7
0x1800207ba  mov     rcx, [rsp+0A8h]; this
0x1800207c2  cmp     [rax+8], si
0x1800207c6  jz      short loc_1800207D8
0x1800207c8  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800207cf  lea     edx, [rsi+34h]; void *
0x1800207d2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800207d8  or      [rax+8], r12
0x1800207dc  mov     rax, [rax]
0x1800207df  mov     rcx, [rdi+0A0h]
0x1800207e6  mov     [rsp+0A8h+var_70], rcx
0x1800207eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207f0  mov     [rdi+0A0h], rsi
0x1800207f7  lea     rcx, [rdi+10h]; this
0x1800207fb  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x180020800  nop
0x180020801  jmp     loc_180020911
0x180020806  xor     esi, esi; jumptable 0000000180020666 case 5
0x180020808  mov     rbx, [rdi+100h]
0x18002080f  mov     rbx, [rbx]
0x180020812  lea     rcx, [rbx-20h]
0x180020816  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002081c  test    al, al
0x18002081e  jz      short loc_180020838
0x180020820  lea     rcx, [rdi+0D0h]; this
0x180020827  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x18002082b  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180020830  mov     rcx, rax
0x180020833  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180020838  mov     rbx, [rbx-10h]
0x18002083c  mov     [rsp+0A8h+var_60], rbx
0x180020841  mov     rax, [rdi+0A0h]
0x180020848  mov     [rsp+0A8h+var_70], rax
0x18002084d  test    rax, rax
0x180020850  jz      short loc_18002088A
0x180020852  mov     rcx, [rsp+0A8h]; this
0x18002085a  cmp     [rax+8], si
0x18002085e  jz      short loc_180020872
0x180020860  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180020867  mov     edx, 34h ; '4'; void *
0x18002086c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180020872  or      [rax+8], r12
0x180020876  mov     rax, [rax]
0x180020879  mov     rcx, [rdi+0A0h]
0x180020880  mov     [rsp+0A8h+var_70], rcx
0x180020885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002088a  test    ebx, ebx
0x18002088c  jz      short loc_1800208C9
0x18002088e  cmp     ebx, 26h ; '&'
0x180020891  jz      short loc_1800208C9
0x180020893  test    ebx, ebx
0x180020895  jle     short loc_1800208A0
0x180020897  movzx   ebx, bx
0x18002089a  or      ebx, 80070000h
0x1800208a0  mov     ecx, ebx; this
0x1800208a2  call    ?HResultToLinuxError@util@p9fs@@YAJJ@Z; p9fs::util::HResultToLinuxError(long)
0x1800208a7  lea     rdx, [rdi-10h]
0x1800208ab  lea     rcx, [rdi+0F0h]
0x1800208b2  cmp     rcx, rdx
0x1800208b5  jz      short loc_1800208BD
0x1800208b7  mov     [rdx+4], eax
0x1800208ba  mov     [rdx], sil
0x1800208bd  lea     rcx, [rdi+10h]; this
0x1800208c1  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800208c6  nop
0x1800208c7  jmp     short loc_1800208F9
0x1800208c9  lea     rcx, [rdi-10h]
0x1800208cd  lea     rax, [rdi+0F8h]
0x1800208d4  cmp     rax, rcx
0x1800208d7  jz      short loc_1800208E3
0x1800208d9  mov     eax, dword ptr [rsp+0A8h+var_60+4]
0x1800208dd  mov     [rcx+4], eax
0x1800208e0  mov     [rcx], r12b
0x1800208e3  lea     rcx, [rdi+10h]; this
0x1800208e7  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800208ec  nop
0x1800208ed  jmp     short loc_1800208F9
0x1800208ef  mov     rdi, [rsp+0A8h+var_68]
0x1800208f4  mov     r14, [rsp+0A8h+var_58]
0x1800208f9  xor     eax, eax
0x1800208fb  mov     [rdi+0A8h], al
0x180020901  mov     [r14], ax
0x180020905  mov     rdx, rdi
0x180020908  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x18002090d  jmp     short loc_180020932
0x18002090f  xor     esi, esi; jumptable 0000000180020666 cases 0,2
0x180020911  lea     rcx, [rdi-20h]
0x180020915  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002091b  cmp     [rdi+0Ah], si
0x18002091f  jz      short loc_180020932
0x180020921  mov     edx, 170h; unsigned __int64
0x180020926  lea     rcx, [rdi-30h]; void *
0x18002092a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002092f  jmp     short loc_180020932
0x180020931  int     3; Trap to Debugger
0x180020932  mov     rcx, [rsp+0A8h+var_40]
0x180020937  xor     rcx, rsp; StackCookie
0x18002093a  call    __security_check_cookie
0x18002093f  add     rsp, 78h
0x180020943  pop     r15
0x180020945  pop     r14
0x180020947  pop     r12
0x180020949  pop     rdi
0x18002094a  pop     rsi
0x18002094b  pop     rbx
0x18002094c  retn
```
