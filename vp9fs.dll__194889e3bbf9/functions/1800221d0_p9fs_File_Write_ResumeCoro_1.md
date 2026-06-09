# p9fs::File::Write$_ResumeCoro$1

- ea: `0x1800221d0`
- end: `0x180022648`
- name: `p9fs::File::Write$_ResumeCoro$1`
- size: `1144`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x180022650`

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
- `0x1800221d0`
- `0x180029d60`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800225df`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800225df`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800224e7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800224e7`
- `lxutil!LxUtilFsQueryStatLxInformation` at `0x1800222c0`
- `lxutil!LxUtilFsQueryStatLxInformation` at `0x1800222c0`
- `lxutil!LxUtilFsUpdateLxAttributes` at `0x180022349`
- `lxutil!LxUtilFsUpdateLxAttributes` at `0x180022349`

## string_xrefs

- `0x180022491`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180022531`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall p9fs::File::Write__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  _WORD *v5; // r15
  __int64 v6; // r14
  __int64 v7; // r13
  __int64 v8; // rcx
  int StatLxInformation; // eax
  __int64 v10; // rdx
  int updated; // eax
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbx
  int v16; // edx
  const char *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v5 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_44;
    case 2:
      v6 = *(_QWORD *)(a1 + 392);
      v7 = *(_QWORD *)(v6 + 48);
      if ( ((v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v8 = a1 - 16;
        if ( a1 + 288 != a1 - 16 )
        {
          *(_DWORD *)(v8 + 4) = -9;
          *(_BYTE *)v8 = 0;
        }
LABEL_43:
        *(_BYTE *)(a1 + 264) = 0;
        *v5 = 0;
        p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
          v8,
          a1);
        return;
      }
      if ( *(_DWORD *)(v6 + 92) && (*(_DWORD *)(v6 + 136) & 0xC00) != 0 )
      {
        memset_0((void *)(a1 + 16), 0, 0x60u);
        StatLxInformation = LxUtilFsQueryStatLxInformation(v7, *(_QWORD *)(v6 + 72) + 32LL, a1 + 16);
        if ( StatLxInformation < 0 )
        {
          v10 = a1 - 16;
          v8 = a1 + 296;
          if ( a1 + 296 != a1 - 16 )
          {
            *(_DWORD *)(v10 + 4) = StatLxInformation;
            *(_BYTE *)v10 = 0;
          }
          goto LABEL_43;
        }
        if ( (*(_DWORD *)(a1 + 88) & 4) != 0 )
        {
          *(_DWORD *)(v6 + 136) = *(_DWORD *)(a1 + 100);
          if ( (*(_DWORD *)(a1 + 100) & 0xC00) != 0 )
          {
            *(_DWORD *)(a1 + 100) &= 0xFFFFF3FF;
            updated = LxUtilFsUpdateLxAttributes(*(_QWORD *)(v6 + 48), 0xFFFFFFFFLL, 0xFFFFFFFFLL);
            if ( updated < 0 )
            {
              v12 = a1 - 16;
              v8 = a1 + 304;
              if ( a1 + 304 != a1 - 16 )
              {
                *(_DWORD *)(v12 + 4) = updated;
                *(_BYTE *)v12 = 0;
              }
              goto LABEL_43;
            }
            *(_DWORD *)(v6 + 136) = *(_DWORD *)(a1 + 100);
          }
        }
        else
        {
          *(_DWORD *)(v6 + 136) &= 0xFFFFF3FF;
        }
      }
      memset_0((void *)(a1 + 116), 0, 0x84u);
      *(_DWORD *)(a1 + 116) = 0;
      *(_OWORD *)(a1 + 136) = 0;
      *(_OWORD *)(a1 + 152) = 0;
      *(_OWORD *)(a1 + 168) = 0;
      *(_QWORD *)(a1 + 120) = 0;
      *(_QWORD *)(a1 + 128) = 0;
      *(_DWORD *)(a1 + 184) = -1;
      *(_DWORD *)(a1 + 112) = 2;
      *(_DWORD *)(a1 + 188) = 0;
      *(_QWORD *)(a1 + 192) = 0;
      *(_BYTE *)(a1 + 200) = 0;
      *(_QWORD *)(a1 + 208) = 0;
      *(_QWORD *)(a1 + 224) = 0;
      *(_OWORD *)(a1 + 232) = 0;
      *(_QWORD *)(a1 + 224) = a1 + 216;
      *(_QWORD *)(a1 + 216) = a1 + 216;
      *(_OWORD *)(a1 + 272) = *(_OWORD *)(a1 + 408);
      v13 = (_QWORD *)p9fs::WriteAsync((int)a1 + 256, (int)v6 + 56, *(_QWORD *)(a1 + 400), (int)a1 + 272, a1 + 112);
      *(_QWORD *)(a1 + 368) = v13;
      if ( *(_BYTE *)(*v13 - 40LL) || (*v5 = 4, !(unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v13, a1)) )
      {
LABEL_28:
        v15 = **(_QWORD **)(a1 + 368);
        if ( __ExceptionPtrToBool((const void *)(v15 - 32)) )
        {
          v18 = std::exception_ptr::exception_ptr(
                  (std::exception_ptr *)(a1 + 312),
                  (const struct std::exception_ptr *)(v15 - 32));
          std::rethrow_exception(v18);
        }
        v19 = *(_QWORD *)(v15 - 16);
        v20 = *(_QWORD *)(a1 + 256);
        if ( v20 )
        {
          if ( *(_WORD *)(v20 + 8) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x34,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
              v17);
          *(_QWORD *)(v20 + 8) |= 1uLL;
          (*(void (**)(void))v20)();
        }
        if ( (_DWORD)v19 )
        {
          if ( (int)v19 > 0 )
            LODWORD(v19) = (unsigned __int16)v19 | 0x80070000;
          v21 = p9fs::util::HResultToLinuxError((p9fs::util *)(unsigned int)v19, v16);
          v22 = a1 - 16;
          if ( a1 + 344 != a1 - 16 )
          {
            *(_DWORD *)(v22 + 4) = v21;
            *(_BYTE *)v22 = 0;
          }
        }
        else
        {
          v23 = a1 - 16;
          if ( a1 + 352 != a1 - 16 )
          {
            *(_DWORD *)(v23 + 4) = HIDWORD(v19);
            *(_BYTE *)v23 = 1;
          }
        }
        p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 112));
        goto LABEL_43;
      }
      return;
    case 4:
      goto LABEL_28;
    case 5:
      v14 = *(_QWORD *)(a1 + 256);
      if ( v14 )
      {
        if ( *(_WORD *)(v14 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v14 + 8) |= 1uLL;
        (*(void (**)(void))v14)();
        *(_QWORD *)(a1 + 256) = 0;
      }
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 112));
LABEL_44:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0x1E0u);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x1800221d0  mov     r11, rsp
0x1800221d3  mov     [r11+10h], rbx
0x1800221d7  mov     [r11+18h], rsi
0x1800221db  mov     [r11+8], rcx
0x1800221df  push    rdi
0x1800221e0  push    r12
0x1800221e2  push    r13
0x1800221e4  push    r14
0x1800221e6  push    r15
0x1800221e8  sub     rsp, 0E0h
0x1800221ef  mov     rax, cs:__security_cookie
0x1800221f6  xor     rax, rsp
0x1800221f9  mov     [rsp+108h+var_38], rax
0x180022201  mov     rdi, rcx
0x180022204  mov     [rsp+108h+var_C8], rcx
0x180022209  lea     r15, [rdi+8]
0x18002220d  mov     [rsp+108h+var_B8], r15
0x180022212  movzx   eax, word ptr [r15]
0x180022216  mov     [rsp+108h+var_D8], ax
0x18002221b  mov     r12d, 1
0x180022221  add     ax, r12w
0x180022225  cmp     ax, 6; switch 7 cases
0x180022229  ja      def_180022244; jumptable 0000000180022244 default case, case 1
0x18002222f  movsx   rax, ax
0x180022233  lea     rdx, cs:180000000h
0x18002223a  mov     ecx, ds:(jpt_180022244 - 180000000h)[rdx+rax*4]
0x180022241  add     rcx, rdx
0x180022244  jmp     rcx; switch jump
0x180022246  xor     esi, esi; jumptable 0000000180022244 case 4
0x180022248  jmp     loc_1800225DB
0x18002224d  mov     r14, [r15+180h]; jumptable 0000000180022244 case 3
0x180022254  mov     r13, [r14+30h]
0x180022258  lea     rax, [r13+1]
0x18002225c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180022262  jnz     short loc_180022285
0x180022264  lea     rcx, [rdi-10h]
0x180022268  lea     rax, [rdi+120h]
0x18002226f  cmp     rax, rcx
0x180022272  jz      short loc_180022280
0x180022274  mov     dword ptr [rcx+4], 0FFFFFFF7h
0x18002227b  xor     esi, esi
0x18002227d  mov     [rcx], sil
0x180022280  jmp     loc_1800225C3
0x180022285  xor     esi, esi
0x180022287  cmp     [r14+5Ch], esi
0x18002228b  jz      loc_18002238E
0x180022291  test    dword ptr [r14+88h], 0C00h
0x18002229c  jz      loc_18002238E
0x1800222a2  xor     edx, edx; Val
0x1800222a4  lea     r8d, [rsi+60h]; Size
0x1800222a8  lea     rcx, [rdi+10h]; void *
0x1800222ac  call    memset_0
0x1800222b1  mov     rdx, [r14+48h]
0x1800222b5  add     rdx, 20h ; ' '
0x1800222b9  lea     r8, [rdi+10h]
0x1800222bd  mov     rcx, r13
0x1800222c0  call    cs:__imp_LxUtilFsQueryStatLxInformation
0x1800222c6  test    eax, eax
0x1800222c8  jns     short loc_1800222E5
0x1800222ca  lea     rdx, [rdi-10h]
0x1800222ce  lea     rcx, [rdi+128h]
0x1800222d5  cmp     rcx, rdx
0x1800222d8  jz      short loc_1800222E0
0x1800222da  mov     [rdx+4], eax
0x1800222dd  mov     [rdx], sil
0x1800222e0  jmp     loc_1800225C3
0x1800222e5  mov     eax, [rdi+58h]
0x1800222e8  mov     [rsp+108h+var_60], eax
0x1800222ef  mov     r12d, 4
0x1800222f5  test    r12d, eax
0x1800222f8  jz      loc_180022381
0x1800222fe  mov     eax, [rdi+64h]
0x180022301  mov     [rsp+108h+var_54], eax
0x180022308  mov     [r14+88h], eax
0x18002230f  mov     eax, [rdi+64h]
0x180022312  mov     [rsp+108h+var_54], eax
0x180022319  test    eax, 0C00h
0x18002231e  jz      short loc_180022394
0x180022320  mov     r9d, [rdi+64h]
0x180022324  mov     [rsp+108h+var_54], r9d
0x18002232c  and     r9d, 0FFFFF3FFh
0x180022333  mov     [rdi+64h], r9d
0x180022337  mov     rcx, [r14+30h]
0x18002233b  mov     [rsp+108h+var_54], r9d
0x180022343  or      edx, 0FFFFFFFFh
0x180022346  mov     r8d, edx
0x180022349  call    cs:__imp_LxUtilFsUpdateLxAttributes
0x18002234f  test    eax, eax
0x180022351  jns     short loc_18002236E
0x180022353  lea     rdx, [rdi-10h]
0x180022357  lea     rcx, [rdi+130h]
0x18002235e  cmp     rcx, rdx
0x180022361  jz      short loc_180022369
0x180022363  mov     [rdx+4], eax
0x180022366  mov     [rdx], sil
0x180022369  jmp     loc_1800225C3
0x18002236e  mov     eax, [rdi+64h]
0x180022371  mov     [rsp+108h+var_54], eax
0x180022378  mov     [r14+88h], eax
0x18002237f  jmp     short loc_180022394
0x180022381  and     dword ptr [r14+88h], 0FFFFF3FFh
0x18002238c  jmp     short loc_180022394
0x18002238e  mov     r12d, 4
0x180022394  lea     rbx, [rdi+70h]
0x180022398  lea     rcx, [rbx+4]; void *
0x18002239c  xor     edx, edx; Val
0x18002239e  mov     r8d, 84h; Size
0x1800223a4  call    memset_0
0x1800223a9  xor     eax, eax
0x1800223ab  mov     [rdi+74h], eax
0x1800223ae  xorps   xmm0, xmm0
0x1800223b1  movups  xmmword ptr [rdi+88h], xmm0
0x1800223b8  movups  xmmword ptr [rdi+98h], xmm0
0x1800223bf  movups  xmmword ptr [rdi+0A8h], xmm0
0x1800223c6  mov     [rdi+78h], rsi
0x1800223ca  mov     [rdi+80h], rsi
0x1800223d1  mov     dword ptr [rdi+0B8h], 0FFFFFFFFh
0x1800223db  mov     dword ptr [rbx], 2
0x1800223e1  mov     [rdi+0BCh], esi
0x1800223e7  mov     [rdi+0C0h], rsi
0x1800223ee  mov     [rdi+0C8h], al
0x1800223f4  mov     [rdi+0D0h], rsi
0x1800223fb  lea     rax, [rdi+0D8h]
0x180022402  mov     [rax+8], rsi
0x180022406  movups  xmmword ptr [rdi+0E8h], xmm0
0x18002240d  mov     [rdi+0E0h], rax
0x180022414  mov     [rax], rax
0x180022417  lea     r9, [rdi+110h]
0x18002241e  movups  xmm0, xmmword ptr [rdi+198h]
0x180022425  movdqu  xmmword ptr [r9], xmm0
0x18002242a  lea     rdx, [r14+38h]
0x18002242e  lea     rcx, [rdi+100h]
0x180022435  mov     [rsp+108h+var_E8], rbx
0x18002243a  mov     r8, [rdi+190h]
0x180022441  call    ?WriteAsync@p9fs@@YA?AV?$Task@UIoResult@p9fs@@@1@AEAUCoroutineIoIssuer@1@_KV?$span@$$CBW4byte@gsl@@$0?0@gsl@@AEAVCancelToken@1@@Z; p9fs::WriteAsync(p9fs::CoroutineIoIssuer &,unsigned __int64,gsl::span<gsl::byte const,-1>,p9fs::CancelToken &)
0x180022446  mov     rcx, rax
0x180022449  mov     [rdi+170h], rax
0x180022450  mov     rax, [rax]
0x180022453  mov     dl, [rax-28h]
0x180022456  nop
0x180022457  test    dl, dl
0x180022459  jnz     short loc_1800224D3
0x18002245b  mov     [r15], r12w
0x18002245f  mov     rdx, rdi
0x180022462  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x180022467  test    al, al
0x180022469  jz      short loc_1800224D3
0x18002246b  jmp     loc_1800225FC
0x180022470  mov     rax, [rdi+100h]; jumptable 0000000180022244 case 6
0x180022477  mov     [rsp+108h+var_D0], rax
0x18002247c  xor     esi, esi
0x18002247e  test    rax, rax
0x180022481  jz      short loc_1800224C0
0x180022483  mov     rcx, [rsp+108h]; this
0x18002248b  cmp     [rax+8], si
0x18002248f  jz      short loc_1800224A1
0x180022491  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180022498  lea     edx, [rsi+34h]; void *
0x18002249b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800224a1  or      [rax+8], r12
0x1800224a5  mov     rax, [rax]
0x1800224a8  mov     rcx, [rdi+100h]
0x1800224af  mov     [rsp+108h+var_D0], rcx
0x1800224b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224b9  mov     [rdi+100h], rsi
0x1800224c0  lea     rcx, [rdi+70h]; this
0x1800224c4  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800224c9  nop
0x1800224ca  jmp     loc_1800225DB
0x1800224cf  xor     esi, esi; jumptable 0000000180022244 case 5
0x1800224d1  jmp     short loc_1800224D9
0x1800224d3  mov     r12d, 1
0x1800224d9  mov     rbx, [rdi+170h]
0x1800224e0  mov     rbx, [rbx]
0x1800224e3  lea     rcx, [rbx-20h]
0x1800224e7  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800224ed  test    al, al
0x1800224ef  jz      short loc_180022509
0x1800224f1  lea     rcx, [rdi+138h]; this
0x1800224f8  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x1800224fc  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180022501  mov     rcx, rax
0x180022504  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x180022509  mov     rbx, [rbx-10h]
0x18002250d  mov     [rsp+108h+var_C0], rbx
0x180022512  mov     rax, [rdi+100h]
0x180022519  mov     [rsp+108h+var_D0], rax
0x18002251e  test    rax, rax
0x180022521  jz      short loc_18002255B
0x180022523  mov     rcx, [rsp+108h]; this
0x18002252b  cmp     [rax+8], si
0x18002252f  jz      short loc_180022543
0x180022531  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180022538  mov     edx, 34h ; '4'; void *
0x18002253d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180022543  or      [rax+8], r12
0x180022547  mov     rax, [rax]
0x18002254a  mov     rcx, [rdi+100h]
0x180022551  mov     [rsp+108h+var_D0], rcx
0x180022556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002255b  test    ebx, ebx
0x18002255d  jz      short loc_180022593
0x18002255f  jle     short loc_18002256A
0x180022561  movzx   ebx, bx
0x180022564  or      ebx, 80070000h
0x18002256a  mov     ecx, ebx; this
0x18002256c  call    ?HResultToLinuxError@util@p9fs@@YAJJ@Z; p9fs::util::HResultToLinuxError(long)
0x180022571  lea     rdx, [rdi-10h]
0x180022575  lea     rcx, [rdi+158h]
0x18002257c  cmp     rcx, rdx
0x18002257f  jz      short loc_180022587
0x180022581  mov     [rdx+4], eax
0x180022584  mov     [rdx], sil
0x180022587  lea     rcx, [rdi+70h]; this
0x18002258b  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x180022590  nop
0x180022591  jmp     short loc_1800225C3
0x180022593  lea     rcx, [rdi-10h]
0x180022597  lea     rax, [rdi+160h]
0x18002259e  cmp     rax, rcx
0x1800225a1  jz      short loc_1800225AD
0x1800225a3  mov     eax, dword ptr [rsp+108h+var_C0+4]
0x1800225a7  mov     [rcx+4], eax
0x1800225aa  mov     [rcx], r12b
0x1800225ad  lea     rcx, [rdi+70h]; this
0x1800225b1  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800225b6  nop
0x1800225b7  jmp     short loc_1800225C3
0x1800225b9  mov     rdi, [rsp+108h+var_C8]
0x1800225be  mov     r15, [rsp+108h+var_B8]
0x1800225c3  xor     eax, eax
0x1800225c5  mov     [rdi+108h], al
0x1800225cb  mov     [r15], ax
0x1800225cf  mov     rdx, rdi
0x1800225d2  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x1800225d7  jmp     short loc_1800225FC
0x1800225d9  xor     esi, esi; jumptable 0000000180022244 cases 0,2
0x1800225db  lea     rcx, [rdi-20h]
0x1800225df  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800225e5  cmp     [rdi+0Ah], si
0x1800225e9  jz      short loc_1800225FC
0x1800225eb  mov     edx, 1E0h; unsigned __int64
0x1800225f0  lea     rcx, [rdi-30h]; void *
0x1800225f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800225f9  jmp     short loc_1800225FC
0x1800225fb  int     3; Trap to Debugger
0x1800225fc  mov     rcx, [rsp+108h+var_38]
0x180022604  xor     rcx, rsp; StackCookie
0x180022607  call    __security_check_cookie
0x18002260c  lea     r11, [rsp+108h+var_28]
0x180022614  mov     rbx, [r11+38h]
0x180022618  mov     rsi, [r11+40h]
0x18002261c  mov     rsp, r11
0x18002261f  pop     r15
0x180022621  pop     r14
0x180022623  pop     r13
0x180022625  pop     r12
0x180022627  pop     rdi
0x180022628  retn
```
