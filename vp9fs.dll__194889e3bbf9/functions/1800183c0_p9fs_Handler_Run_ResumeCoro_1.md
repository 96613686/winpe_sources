# p9fs::Handler::Run$_ResumeCoro$1

- ea: `0x1800183c0`
- end: `0x180018f0c`
- name: `p9fs::Handler::Run$_ResumeCoro$1`
- size: `2892`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18000e5a0`

## callees

- `0x180002c6c`
- `0x180004120`
- `0x180004144`
- `0x180004534`
- `0x180004c74`
- `0x180004c80`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000c4bc`
- `0x18000c880`
- `0x18000d5d8`
- `0x18000d87c`
- `0x18000d9a4`
- `0x18000ddf0`
- `0x18000dedc`
- `0x18000e23c`
- `0x18000e334`
- `0x18000e45c`
- `0x18000fd3c`
- `0x18000fddc`
- `0x180016684`
- `0x180016b50`
- `0x1800183c0`
- `0x18001c794`
- `0x18001c7c4`
- `0x18001c878`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018e91`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180018e91`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180018bd8`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180018bd8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018b56`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018b56`

## string_xrefs

- `0x180018575`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x180018c3c`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall p9fs::Handler::Run__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  _DWORD *v5; // rcx
  __int64 v6; // rax
  gsl::details *v7; // rcx
  size_t v8; // rdi
  __int64 *v9; // r13
  void *v10; // rax
  void *v11; // rcx
  _QWORD *v12; // rax
  char *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r11
  __int64 v19; // r10
  _QWORD *v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rbx
  _QWORD *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  _QWORD *v30; // rcx
  __int64 v31; // rbx
  gsl::details *v32; // rcx
  const char *v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  __int64 v37; // r8
  _QWORD *v38; // rdx
  __int64 v39; // r9
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  _DWORD *v43; // rcx
  __int64 v44; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_53;
    case 2:
      v5 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
      if ( *v5 > 4u )
        tlgWriteTransfer_EventWriteTransfer((int)v5, (int)&byte_18003917D, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)(a1 + 816));
      memset_0((void *)(a1 + 16), 0, 0x88u);
      p9fs::CancelToken::CancelToken((p9fs::CancelToken *)(a1 + 16), *(struct p9fs::CancelToken **)(a1 + 2320));
      memset_0((void *)(a1 + 160), 0, 0x88u);
      p9fs::CancelToken::CancelToken((p9fs::CancelToken *)(a1 + 160), (struct p9fs::CancelToken *)(a1 + 16));
      memset_0((void *)(a1 + 304), 0, 0x88u);
      p9fs::CancelToken::CancelToken((p9fs::CancelToken *)(a1 + 304), (struct p9fs::CancelToken *)(a1 + 16));
      memset_0((void *)(a1 + 452), 0, 0x5Cu);
      *(_QWORD *)(a1 + 448) = 2;
      *(_OWORD *)(a1 + 472) = 0;
      *(_OWORD *)(a1 + 488) = 0;
      *(_OWORD *)(a1 + 504) = 0;
      *(_QWORD *)(a1 + 456) = 0;
      *(_QWORD *)(a1 + 464) = 0;
      *(_DWORD *)(a1 + 520) = -1;
      *(_DWORD *)(a1 + 524) = 0;
      *(_QWORD *)(a1 + 528) = 32;
      *(_QWORD *)(a1 + 536) = 0;
      goto LABEL_24;
    case 4:
      goto LABEL_27;
    case 5:
      if ( *(_QWORD *)(a1 + 544) )
      {
        if ( *(_WORD *)(*(_QWORD *)(a1 + 544) + 8LL) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        v6 = *(_QWORD *)(a1 + 544);
        *(_QWORD *)(v6 + 8) |= 1uLL;
        (*(void (**)(void))v6)();
        *(_QWORD *)(a1 + 544) = 0;
      }
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 304));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 160));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 16));
      goto LABEL_53;
    case 6:
      goto LABEL_11;
    case 7:
      p9fs::Handler::RequestTracker::~RequestTracker((p9fs::Handler::RequestTracker *)(a1 + 552));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 304));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 160));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 16));
      goto LABEL_53;
    case 8:
      goto LABEL_50;
    case 9:
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 304));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 160));
      p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 16));
LABEL_53:
      __ExceptionPtrDestroy((void *)(a1 - 16));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 32), 0x940u);
      return;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
LABEL_11:
    *(_QWORD *)(a1 + 744) = a1 + 448;
    *(_BYTE *)(a1 + 752) = 1;
    v7 = *(gsl::details **)(a1 + 1248);
    v8 = *(_QWORD *)(a1 + 1240);
    v9 = (__int64 *)(a1 + 720);
    *(_QWORD *)(a1 + 720) = 0;
    *(_QWORD *)(a1 + 728) = 0;
    *(_QWORD *)(a1 + 736) = 0;
    if ( v7 > (gsl::details *)((char *)v7 + v8) )
      gsl::details::terminate(v7);
    if ( v8 )
    {
      if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<std::basic_string_view<unsigned short>>::_Xlength();
      if ( v8 < 0x1000 )
      {
        v12 = operator new(v8);
      }
      else
      {
        if ( v8 + 39 < v8 )
          __scrt_throw_std_bad_array_new_length();
        v10 = operator new(v8 + 39);
        v11 = v10;
        if ( !v10 )
          __fastfail(5u);
        v12 = (_QWORD *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v12 - 1) = v11;
      }
      *v9 = (__int64)v12;
      *(_QWORD *)(a1 + 728) = v12;
      v13 = (char *)v12 + v8;
      *(_QWORD *)(a1 + 736) = (char *)v12 + v8;
      memmove_0(v12, *(const void **)(a1 + 1248), v8);
      *(_QWORD *)(a1 + 728) = v13;
      *(_QWORD *)(a1 + 1232) = 0;
      std::_Tidy_guard<std::vector<enum gsl::byte>>::~_Tidy_guard<std::vector<enum gsl::byte>>();
    }
    v14 = *(_QWORD *)(a1 + 2312);
    *(_QWORD *)(a1 + 632) = v14;
    *(_QWORD *)(a1 + 640) = a1 + 448;
    *(_BYTE *)(a1 + 752) = 0;
    v15 = *(_QWORD *)(a1 + 736);
    *(_QWORD *)(a1 + 736) = 0;
    v16 = *(_QWORD *)(a1 + 728);
    *(_QWORD *)(a1 + 728) = 0;
    v17 = *v9;
    *v9 = 0;
    v18 = *(_QWORD *)(a1 + 552);
    *(_QWORD *)(a1 + 688) = *(_QWORD *)(a1 + 560);
    *(_QWORD *)(a1 + 552) = 0;
    *(_QWORD *)(a1 + 560) = 0;
    v19 = *(_QWORD *)(a1 + 568);
    *(_QWORD *)(a1 + 568) = 0;
    *(_QWORD *)(a1 + 704) = a1 + 16;
    *(_QWORD *)(a1 + 712) = a1 + 304;
    *(_BYTE *)(a1 + 1136) = 0;
    *(_QWORD *)(a1 + 1144) = v14;
    *(_QWORD *)(a1 + 1152) = a1 + 448;
    *(_BYTE *)(a1 + 1160) = 1;
    *(_BYTE *)(a1 + 648) = 0;
    *(_QWORD *)(a1 + 672) = 0;
    *(_QWORD *)(a1 + 664) = 0;
    *(_QWORD *)(a1 + 656) = 0;
    *(_QWORD *)(a1 + 1168) = v17;
    *(_QWORD *)(a1 + 1176) = v16;
    *(_QWORD *)(a1 + 1184) = v15;
    *(_QWORD *)(a1 + 1192) = v18;
    *(_QWORD *)(a1 + 1200) = *(_QWORD *)(a1 + 688);
    *(_QWORD *)(a1 + 680) = 0;
    *(_QWORD *)(a1 + 688) = 0;
    *(_QWORD *)(a1 + 696) = 0;
    *(_QWORD *)(a1 + 1208) = v19;
    *(_QWORD *)(a1 + 1216) = a1 + 16;
    *(_QWORD *)(a1 + 1224) = a1 + 304;
    *(_QWORD *)(a1 + 808) = a1 + 1144;
    v20 = operator new(0x3C0u);
    *(_QWORD *)(a1 + 1256) = v20;
    v20[107] = a1 + 1136;
    v20[108] = *(_QWORD *)(a1 + 1144);
    v20[109] = *(_QWORD *)(a1 + 1152);
    *((_BYTE *)v20 + 880) = *(_BYTE *)(a1 + 1160);
    *(_BYTE *)(a1 + 1160) = 0;
    v21 = *(_QWORD *)(a1 + 1184);
    *(_QWORD *)(a1 + 1184) = 0;
    v22 = *(_QWORD *)(a1 + 1176);
    *(_QWORD *)(a1 + 1176) = 0;
    v23 = *(_QWORD *)(a1 + 1168);
    *(_QWORD *)(a1 + 1168) = 0;
    v20[111] = v23;
    v20[112] = v22;
    v20[113] = v21;
    v20[114] = 0;
    v20[115] = 0;
    v20[114] = *(_QWORD *)(a1 + 1192);
    v20[115] = *(_QWORD *)(a1 + 1200);
    *(_QWORD *)(a1 + 1192) = 0;
    *(_QWORD *)(a1 + 1200) = 0;
    v24 = *(_QWORD *)(a1 + 1208);
    *(_QWORD *)(a1 + 1208) = 0;
    v20[116] = v24;
    v20[117] = *(_QWORD *)(a1 + 1216);
    v20[118] = *(_QWORD *)(a1 + 1224);
    **(_QWORD **)(a1 + 1256) = lambda_ed880bf6c21129580bbd6a5328219adc___ResumeCoro_1::operator();
    *(_DWORD *)(*(_QWORD *)(a1 + 1256) + 8LL) = 65538;
    p9fs::Scheduler::Schedule(&p9fs::g_Scheduler);
    *(_BYTE *)(*(_QWORD *)(a1 + 1256) + 848LL) = 0;
    p9fs::Handler::RequestTracker::~RequestTracker((p9fs::Handler::RequestTracker *)(a1 + 1192));
    std::vector<unsigned char>::~vector<unsigned char>(a1 + 1168);
    wil::details::lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>::~lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>(a1 + 1152);
    p9fs::Handler::RequestTracker::~RequestTracker((p9fs::Handler::RequestTracker *)(a1 + 680));
    std::vector<unsigned char>::~vector<unsigned char>(a1 + 656);
    wil::details::lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>::~lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>(a1 + 640);
    std::vector<unsigned char>::~vector<unsigned char>(a1 + 720);
    wil::details::lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>::~lambda_call<_lambda_38114c5ce917be83d17d394d1d91bf81_>(a1 + 744);
    p9fs::Handler::RequestTracker::~RequestTracker((p9fs::Handler::RequestTracker *)(a1 + 552));
LABEL_24:
    if ( *(_BYTE *)(a1 + 104) )
      break;
    *(_QWORD *)(a1 + 1240) = 0;
    *(_QWORD *)(a1 + 1248) = 0;
    v25 = *(_QWORD *)(a1 + 2312);
    v26 = operator new(0xE0u);
    *(_QWORD *)(a1 + 848) = v26 + 6;
    v26[25] = v25;
    v26[26] = a1 + 160;
    **(_QWORD **)(a1 + 848) = p9fs::Handler::NextMessage__ResumeCoro_1;
    *(_DWORD *)(*(_QWORD *)(a1 + 848) + 8LL) = 65538;
    v27 = *(_QWORD *)(a1 + 848);
    *(_OWORD *)(v27 - 48) = 0;
    *(_OWORD *)(v27 - 32) = 0;
    *(_OWORD *)(v27 - 16) = 0;
    v28 = *(_QWORD *)(a1 + 848);
    *(_OWORD *)(v28 - 48) = 0;
    *(_OWORD *)(v28 - 32) = 0;
    *(_OWORD *)(v28 - 16) = 0;
    v29 = *(_QWORD *)(a1 + 848);
    *(_QWORD *)(v29 - 48) = 0;
    *(_BYTE *)(v29 - 40) = 0;
    v30 = (_QWORD *)(v29 - 32);
    *v30 = 0;
    v30[1] = 0;
    __ExceptionPtrCreate((void *)(v29 - 32));
    *(_QWORD *)(v29 - 16) = 0;
    *(_QWORD *)(v29 - 8) = 0;
    *(_QWORD *)(a1 + 544) = *(_QWORD *)(a1 + 848);
    *(_BYTE *)(*(_QWORD *)(a1 + 848) + 144LL) = 0;
    p9fs::Handler::NextMessage__ResumeCoro_1();
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 544) - 40LL) )
    {
      *(_WORD *)(a1 + 8) = 4;
      if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(a1 + 544, a1) )
        return;
    }
LABEL_27:
    v31 = *(_QWORD *)(a1 + 544);
    if ( __ExceptionPtrToBool((const void *)(v31 - 32)) )
    {
      v34 = std::exception_ptr::exception_ptr(
              (std::exception_ptr *)(a1 + 1120),
              (const struct std::exception_ptr *)(v31 - 32));
      std::rethrow_exception(v34);
    }
    *(_QWORD *)(a1 + 1240) = *(_QWORD *)(v31 - 16);
    *(_QWORD *)(a1 + 1248) = *(_QWORD *)(v31 - 8);
    if ( *(_QWORD *)(a1 + 544) )
    {
      if ( *(_WORD *)(*(_QWORD *)(a1 + 544) + 8LL) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
          v33);
      v35 = *(_QWORD *)(a1 + 544);
      *(_QWORD *)(v35 + 8) |= 1uLL;
      (*(void (**)(void))v35)();
      *(_QWORD *)(a1 + 544) = 0;
    }
    v36 = *(_QWORD *)(a1 + 1240);
    if ( !v36 )
      break;
    if ( v36 < 5 || (v32 = (gsl::details *)(v36 - 5), *(_QWORD *)(a1 + 1248) == -5) && v36 != 5 )
      gsl::details::terminate(v32);
    if ( (unsigned __int64)v32 < 2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\inc\\p9protohelpers.h",
        v33);
    v37 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 1248) + 5LL);
    *(_OWORD *)(a1 + 552) = 0;
    *(_QWORD *)(a1 + 568) = 0;
    v38 = (_QWORD *)(a1 + 576);
    v39 = *(_QWORD *)(a1 + 2312);
    *(_QWORD *)(a1 + 576) = 0;
    *(_QWORD *)(a1 + 584) = 0;
    v40 = *(_QWORD *)(v39 + 104);
    if ( v40 )
      _InterlockedAdd((volatile signed __int32 *)(v40 + 8), 1u);
    *v38 = *(_QWORD *)(v39 + 96);
    *(_QWORD *)(a1 + 584) = *(_QWORD *)(v39 + 104);
    p9fs::Handler::RequestTracker::RequestTracker(a1 + 552, v38, v37);
    v41 = p9fs::AsyncSemaphore::Acquire(a1 + 448, a1 + 600, 1);
    *(_QWORD *)(a1 + 592) = v41;
    if ( *(_QWORD *)(v41 + 24) )
    {
      *(_WORD *)(a1 + 8) = 6;
      if ( (unsigned __int8)p9fs::AsyncSemaphore::AsyncSemaphoreTask::await_suspend(v41, a1) )
        return;
    }
  }
  p9fs::CancelToken::Cancel((p9fs::CancelToken *)(a1 + 16));
  v42 = p9fs::AsyncSemaphore::Acquire(a1 + 448, a1 + 768, 32);
  *(_QWORD *)(a1 + 760) = v42;
  if ( !*(_QWORD *)(v42 + 24)
    || (*(_WORD *)(a1 + 8) = 8, !(unsigned __int8)p9fs::AsyncSemaphore::AsyncSemaphoreTask::await_suspend(v42, a1)) )
  {
LABEL_50:
    v43 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
    if ( *v43 > 4u )
      tlgWriteTransfer_EventWriteTransfer((int)v43, (int)&byte_18003843F, 0, 0, 2u, (PEVENT_DATA_DESCRIPTOR)(a1 + 2272));
    p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 304));
    p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 160));
    p9fs::CancelToken::~CancelToken((p9fs::CancelToken *)(a1 + 16));
    *(_BYTE *)(a1 + 800) = 0;
    *(_WORD *)(a1 + 8) = 0;
    p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(
      v44,
      a1);
  }
}

```

## disassembly

```asm
0x1800183c0  mov     r11, rsp
0x1800183c3  mov     [r11+10h], rbx
0x1800183c7  mov     [r11+18h], rsi
0x1800183cb  mov     [r11+8], rcx
0x1800183cf  push    rdi
0x1800183d0  push    r12
0x1800183d2  push    r13
0x1800183d4  push    r14
0x1800183d6  push    r15
0x1800183d8  sub     rsp, 310h
0x1800183df  mov     rax, cs:__security_cookie
0x1800183e6  xor     rax, rsp
0x1800183e9  mov     [rsp+338h+var_30], rax
0x1800183f1  mov     rsi, rcx
0x1800183f4  mov     [rsp+338h+var_2E8], rcx
0x1800183f9  movzx   eax, word ptr [rsi+8]
0x1800183fd  mov     [rsp+338h+var_2F0], ax
0x180018402  mov     r15d, 1
0x180018408  add     ax, r15w
0x18001840c  cmp     ax, 0Ah; switch 11 cases
0x180018410  ja      def_18001842B; jumptable 000000018001842B default case, case 1
0x180018416  movsx   rax, ax
0x18001841a  lea     rdx, cs:180000000h
0x180018421  mov     ecx, ds:(jpt_18001842B - 180000000h)[rdx+rax*4]
0x180018428  add     rcx, rdx
0x18001842b  jmp     rcx; switch jump
0x18001842d  xor     r14d, r14d; jumptable 000000018001842B case 4
0x180018430  jmp     loc_180018E8D
0x180018435  call    ?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ; jumptable 000000018001842B case 3
0x18001843a  mov     rcx, [rax+8]; int
0x18001843e  mov     eax, [rcx]
0x180018440  mov     r12d, 4
0x180018446  cmp     eax, r12d
0x180018449  jbe     short loc_180018471
0x18001844b  lea     rax, [rsi+330h]
0x180018452  mov     [rsp+338h+var_310], rax; PEVENT_DATA_DESCRIPTOR
0x180018457  mov     [rsp+338h+var_318], 2; ULONG
0x18001845f  xor     r9d, r9d; int
0x180018462  xor     r8d, r8d; int
0x180018465  lea     rdx, byte_18003917D; int
0x18001846c  call    _tlgWriteTransfer_EventWriteTransfer
0x180018471  lea     rdi, [rsi+10h]
0x180018475  mov     r14d, 88h
0x18001847b  mov     r8d, r14d; Size
0x18001847e  xor     edx, edx; Val
0x180018480  mov     rcx, rdi; void *
0x180018483  call    memset_0
0x180018488  mov     rdx, [rdi+900h]; struct p9fs::CancelToken *
0x18001848f  mov     rcx, rdi; this
0x180018492  call    ??0CancelToken@p9fs@@QEAA@AEAV01@@Z; p9fs::CancelToken::CancelToken(p9fs::CancelToken &)
0x180018497  nop
0x180018498  lea     rbx, [rsi+0A0h]
0x18001849f  mov     r8d, r14d; Size
0x1800184a2  xor     edx, edx; Val
0x1800184a4  mov     rcx, rbx; void *
0x1800184a7  call    memset_0
0x1800184ac  mov     rdx, rdi; struct p9fs::CancelToken *
0x1800184af  mov     rcx, rbx; this
0x1800184b2  call    ??0CancelToken@p9fs@@QEAA@AEAV01@@Z; p9fs::CancelToken::CancelToken(p9fs::CancelToken &)
0x1800184b7  nop
0x1800184b8  lea     rbx, [rsi+130h]
0x1800184bf  mov     r8d, r14d; Size
0x1800184c2  xor     edx, edx; Val
0x1800184c4  mov     rcx, rbx; void *
0x1800184c7  call    memset_0
0x1800184cc  mov     rdx, rdi; struct p9fs::CancelToken *
0x1800184cf  mov     rcx, rbx; this
0x1800184d2  call    ??0CancelToken@p9fs@@QEAA@AEAV01@@Z; p9fs::CancelToken::CancelToken(p9fs::CancelToken &)
0x1800184d7  nop
0x1800184d8  lea     rcx, [rsi+1C4h]; void *
0x1800184df  xor     edx, edx; Val
0x1800184e1  lea     r8d, [r14-2Ch]; Size
0x1800184e5  call    memset_0
0x1800184ea  mov     qword ptr [rsi+1C0h], 2
0x1800184f5  xorps   xmm0, xmm0
0x1800184f8  movups  xmmword ptr [rsi+1D8h], xmm0
0x1800184ff  movups  xmmword ptr [rsi+1E8h], xmm0
0x180018506  movups  xmmword ptr [rsi+1F8h], xmm0
0x18001850d  xor     r14d, r14d
0x180018510  mov     [rsi+1C8h], r14
0x180018517  mov     [rsi+1D0h], r14
0x18001851e  mov     dword ptr [rsi+208h], 0FFFFFFFFh
0x180018528  mov     [rsi+20Ch], r14d
0x18001852f  mov     qword ptr [rsi+210h], 20h ; ' '
0x18001853a  mov     [rsi+218h], r14
0x180018541  jmp     loc_180018A78
0x180018546  mov     rax, [rsi+220h]; jumptable 000000018001842B case 6
0x18001854d  mov     [rsp+338h+var_300], rax
0x180018552  xor     r14d, r14d
0x180018555  test    rax, rax
0x180018558  jz      short loc_1800185B1
0x18001855a  mov     rax, [rsi+220h]
0x180018561  mov     [rsp+338h+var_300], rax
0x180018566  mov     rcx, [rsp+338h]; this
0x18001856e  cmp     [rax+8], r14w
0x180018573  jz      short loc_180018586
0x180018575  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18001857c  lea     edx, [r14+34h]; void *
0x180018580  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018586  mov     rax, [rsi+220h]
0x18001858d  mov     [rsp+338h+var_300], rax
0x180018592  or      [rax+8], r15
0x180018596  mov     rcx, [rsi+220h]
0x18001859d  mov     [rsp+338h+var_300], rcx
0x1800185a2  mov     rax, [rax]
0x1800185a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185aa  mov     [rsi+220h], r14
0x1800185b1  lea     rcx, [rsi+130h]; this
0x1800185b8  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800185bd  nop
0x1800185be  lea     rcx, [rsi+0A0h]; this
0x1800185c5  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800185ca  nop
0x1800185cb  lea     rcx, [rsi+10h]; this
0x1800185cf  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800185d4  nop
0x1800185d5  jmp     loc_180018E8D
0x1800185da  lea     rcx, [rsi+228h]; jumptable 000000018001842B case 8
0x1800185e1  call    ??1RequestTracker@Handler@p9fs@@QEAA@XZ; p9fs::Handler::RequestTracker::~RequestTracker(void)
0x1800185e6  nop
0x1800185e7  lea     rcx, [rsi+130h]; this
0x1800185ee  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x1800185f3  nop
0x1800185f4  lea     rcx, [rsi+0A0h]; this
0x1800185fb  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x180018600  nop
0x180018601  lea     rcx, [rsi+10h]; this
0x180018605  call    ??1CancelToken@p9fs@@QEAA@XZ; p9fs::CancelToken::~CancelToken(void)
0x18001860a  nop
0x18001860b  xor     r14d, r14d
0x18001860e  jmp     loc_180018E8D
0x180018613  mov     r12d, 4; jumptable 000000018001842B case 5
0x180018619  xor     r14d, r14d
0x18001861c  jmp     loc_180018BC8
0x180018621  mov     r12d, 4; jumptable 000000018001842B case 7
0x180018627  xor     r14d, r14d
0x18001862a  lea     rax, [rsi+1C0h]
0x180018631  mov     [rsi+2E8h], rax
0x180018638  mov     [rsi+2F0h], r15b
0x18001863f  mov     rcx, [rsi+4E0h]; this
0x180018646  mov     rdi, [rsi+4D8h]
0x18001864d  lea     r13, [rsi+2D0h]
0x180018654  mov     [r13+0], r14
0x180018658  mov     [rsi+2D8h], r14
0x18001865f  mov     [rsi+2E0h], r14
0x180018666  lea     rax, [rdi+rcx]
0x18001866a  cmp     rcx, rax
0x18001866d  ja      loc_180018DDA
0x180018673  test    rdi, rdi
0x180018676  jz      loc_18001870E
0x18001867c  mov     rax, 7FFFFFFFFFFFFFFFh
0x180018686  cmp     rdi, rax
0x180018689  jbe     short loc_180018690
0x18001868b  call    ?_Xlength@?$vector@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@2@@std@@CAXXZ; std::vector<std::basic_string_view<ushort>>::_Xlength(void)
0x180018690  cmp     rdi, 1000h
0x180018697  jb      short loc_1800186C7
0x180018699  lea     rcx, [rdi+27h]; Size
0x18001869d  cmp     rcx, rdi
0x1800186a0  ja      short loc_1800186A7
0x1800186a2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x1800186a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800186ac  mov     rcx, rax
0x1800186af  test    rax, rax
0x1800186b2  jnz     short loc_1800186B9
0x1800186b4  lea     ecx, [rax+5]
0x1800186b7  int     29h; Win8: RtlFailFast(ecx)
0x1800186b9  add     rax, 27h ; '''
0x1800186bd  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800186c1  mov     [rax-8], rcx
0x1800186c5  jmp     short loc_1800186CF
0x1800186c7  mov     rcx, rdi; Size
0x1800186ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800186cf  mov     [r13+0], rax
0x1800186d3  mov     [rsi+2D8h], rax
0x1800186da  lea     rbx, [rax+rdi]
0x1800186de  mov     [rsi+2E0h], rbx
0x1800186e5  mov     r8, rdi; Size
0x1800186e8  mov     rdx, [rsi+4E0h]; Src
0x1800186ef  mov     rcx, rax; void *
0x1800186f2  call    memmove_0
0x1800186f7  mov     [rsi+2D8h], rbx
0x1800186fe  lea     rcx, [rsi+4D0h]
0x180018705  mov     [rcx], r14
0x180018708  call    ??1?$_Tidy_guard@V?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<gsl::byte>>::~_Tidy_guard<std::vector<gsl::byte>>(void)
0x18001870d  nop
0x18001870e  mov     rcx, [rsi+908h]
0x180018715  mov     [rsi+278h], rcx
0x18001871c  lea     rax, [rsi+1C0h]
0x180018723  mov     [rsi+280h], rax
0x18001872a  mov     [rsi+2F0h], r14b
0x180018731  mov     rdi, [rsi+2E0h]
0x180018738  mov     [rsp+338h+var_2C8], rdi
0x18001873d  mov     [rsi+2E0h], r14
0x180018744  mov     rbx, [rsi+2D8h]
0x18001874b  mov     [rsp+338h+var_2D0], rbx
0x180018750  mov     [rsi+2D8h], r14
0x180018757  mov     rdx, [r13+0]
0x18001875b  mov     [rsp+338h+var_2D8], rdx
0x180018760  mov     [r13+0], r14
0x180018764  lea     r8, [rsi+228h]
0x18001876b  mov     r11, [r8]
0x18001876e  mov     [rsp+338h+var_210], r11
0x180018776  mov     rax, [rsi+230h]
0x18001877d  mov     [rsp+338h+var_208], rax
0x180018785  mov     [rsi+2B0h], rax
0x18001878c  mov     [r8], r14
0x18001878f  mov     [rsi+230h], r14
0x180018796  mov     r10, [rsi+238h]
0x18001879d  mov     [rsp+338h+var_200], r10
0x1800187a5  mov     [rsi+238h], r14
0x1800187ac  lea     r8, [rsi+10h]
0x1800187b0  mov     [rsi+2C0h], r8
0x1800187b7  lea     r9, [rsi+130h]
0x1800187be  mov     [rsi+2C8h], r9
0x1800187c5  mov     [rsi+470h], r14b
0x1800187cc  mov     [rsi+478h], rcx
0x1800187d3  lea     rax, [rsi+1C0h]
0x1800187da  mov     [rsi+480h], rax
0x1800187e1  mov     [rsi+488h], r15b
0x1800187e8  mov     [rsi+288h], r14b
0x1800187ef  mov     [rsi+2A0h], r14
0x1800187f6  mov     [rsi+298h], r14
0x1800187fd  mov     [rsi+290h], r14
0x180018804  mov     [rsi+490h], rdx
0x18001880b  mov     [rsi+498h], rbx
0x180018812  mov     [rsi+4A0h], rdi
0x180018819  lea     rdi, [rsi+4A8h]
0x180018820  mov     [rsp+338h+var_238], r11
0x180018828  mov     [rdi], r11
0x18001882b  mov     rax, [rsi+2B0h]
0x180018832  mov     [rsp+338h+var_230], rax
0x18001883a  mov     [rsi+4B0h], rax
0x180018841  mov     [rsi+2A8h], r14
0x180018848  mov     [rsi+2B0h], r14
0x18001884f  mov     [rsi+2B8h], r14
0x180018856  mov     [rsi+4B8h], r10
0x18001885d  mov     [rsi+4C0h], r8
0x180018864  mov     [rsi+4C8h], r9
0x18001886b  lea     rbx, [rsi+478h]
0x180018872  mov     [rsi+328h], rbx
0x180018879  mov     ecx, 3C0h; Size
0x18001887e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018883  mov     r8, rax
0x180018886  mov     [rsi+4E8h], rax
0x18001888d  mov     [rsp+338h+var_2F8], rax
0x180018892  lea     rax, [rsi+470h]
0x180018899  mov     [r8+358h], rax
0x1800188a0  mov     rcx, [rbx]
0x1800188a3  mov     [rsp+338h+var_2C0], rcx
0x1800188a8  mov     [r8+360h], rcx
0x1800188af  mov     rax, [rsi+480h]
0x1800188b6  mov     [rsp+338h+var_2B8], rax
0x1800188be  mov     [r8+368h], rax
0x1800188c5  mov     al, [rsi+488h]
0x1800188cb  mov     [rsp+338h+var_2B0], al
0x1800188d2  mov     [r8+370h], al
0x1800188d9  mov     [rsi+488h], r14b
0x1800188e0  mov     rdx, [rsi+4A0h]
0x1800188e7  mov     [rsp+338h+var_298], rdx
0x1800188ef  mov     [rsi+4A0h], r14
0x1800188f6  mov     rcx, [rsi+498h]
0x1800188fd  mov     [rsp+338h+var_2A0], rcx
0x180018905  mov     [rsi+498h], r14
0x18001890c  lea     rbx, [rsi+490h]
0x180018913  mov     rax, [rbx]
0x180018916  mov     [rsp+338h+var_2A8], rax
0x18001891e  mov     [rbx], r14
0x180018921  mov     [r8+378h], rax
0x180018928  mov     [r8+380h], rcx
0x18001892f  mov     [r8+388h], rdx
0x180018936  mov     [r8+390h], r14
0x18001893d  mov     [r8+398h], r14
0x180018944  mov     rax, [rdi]
0x180018947  mov     [rsp+338h+var_290], rax
0x18001894f  mov     [r8+390h], rax
0x180018956  mov     rax, [rsi+4B0h]
0x18001895d  mov     [rsp+338h+var_288], rax
0x180018965  mov     [r8+398h], rax
0x18001896c  mov     [rdi], r14
0x18001896f  mov     [rsi+4B0h], r14
0x180018976  mov     rax, [rsi+4B8h]
0x18001897d  mov     [rsp+338h+var_280], rax
0x180018985  mov     [rsi+4B8h], r14
0x18001898c  mov     [r8+3A0h], rax
0x180018993  mov     rax, [rsi+4C0h]
0x18001899a  mov     [rsp+338h+var_278], rax
0x1800189a2  mov     [r8+3A8h], rax
0x1800189a9  mov     rax, [rsi+4C8h]
0x1800189b0  mov     [rsp+338h+var_270], rax
0x1800189b8  mov     [r8+3B0h], rax
0x1800189bf  mov     rax, [rsi+4E8h]
0x1800189c6  mov     [rsp+338h+var_2F8], rax
0x1800189cb  lea     rcx, _lambda_ed880bf6c21129580bbd6a5328219adc_$_ResumeCoro$1__operator__
0x1800189d2  mov     [rax], rcx
0x1800189d5  mov     rax, [rsi+4E8h]
0x1800189dc  mov     [rsp+338h+var_2F8], rax
0x1800189e1  mov     dword ptr [rax+8], 10002h
0x1800189e8  mov     rdx, [rsi+4E8h]
0x1800189ef  mov     [rsp+338h+var_2F8], rdx
0x1800189f4  lea     rcx, ?g_Scheduler@p9fs@@3VScheduler@1@A; _Smtx_t *
  ... truncated ...
```
