# _lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_$_ResumeCoro$1::operator()

- ea: `0x18000e5a0`
- end: `0x18000e924`
- name: `_lambda_14a7a5d5c2db807f1a68f78f3c68b6c0_$_ResumeCoro$1::operator()`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f2d0`

## callees

- `0x180004120`
- `0x180004144`
- `0x180004534`
- `0x180004c80`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000cdf4`
- `0x18000d5d8`
- `0x18000d610`
- `0x18000d7a0`
- `0x18000e3c0`
- `0x18000e5a0`
- `0x1800183c0`
- `0x18001c7e0`
- `0x18001c924`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000e8bf`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18000e8bf`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000e80a`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18000e80a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000e720`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000e720`

## string_xrefs

- `0x18000e79a`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18000e84c`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall lambda_14a7a5d5c2db807f1a68f78f3c68b6c0___ResumeCoro_1::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _WORD *v5; // r13
  __int64 *v6; // rsi
  _QWORD *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rdi
  _QWORD *v10; // rax
  __int64 v11; // rbx
  char *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // rax
  const struct std::exception_ptr *v18; // rbx
  const char *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  volatile signed __int64 *v23; // [rsp+48h] [rbp-60h]
  volatile signed __int64 *v24; // [rsp+48h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v5 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_17;
    case 2:
      v6 = *(__int64 **)(a1 + 2584);
      *(_QWORD *)(a1 + 16) = v6[2];
      *(_BYTE *)(a1 + 24) = 1;
      v7 = (_QWORD *)(a1 + 32);
      memset_0((void *)(a1 + 32), 0, 0x80u);
      v8 = *v6;
      v9 = v6[3];
      *v7 = &p9fs::Handler::`vftable';
      *(_QWORD *)(a1 + 40) = 0;
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = v8;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      *(_QWORD *)(a1 + 80) = 0;
      v10 = operator new(0x38u);
      *v10 = v10;
      v10[1] = v10;
      v10[2] = v10;
      *((_WORD *)v10 + 12) = 257;
      *(_QWORD *)(a1 + 72) = v10;
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(a1 + 88, 0x40000);
      *(_QWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = 0;
      std::make_shared<p9fs::Handler::RequestList,>(a1 + 128);
      *(_DWORD *)(a1 + 144) = 64;
      *(_WORD *)(a1 + 148) = 0;
      *(_BYTE *)(a1 + 150) = 0;
      *(_QWORD *)(a1 + 152) = v9;
      v11 = v6[4];
      v12 = (char *)operator new(0x940u);
      v13 = (__int64)(v12 + 32);
      *((_QWORD *)v12 + 293) = v7;
      *((_QWORD *)v12 + 294) = v11;
      *((_QWORD *)v12 + 4) = p9fs::Handler::Run__ResumeCoro_1;
      *((_DWORD *)v12 + 10) = 65538;
      *(_DWORD *)(v12 + 9) = 0;
      *(_WORD *)(v12 + 13) = 0;
      v12[15] = 0;
      *(_QWORD *)v12 = 0;
      v12[8] = 0;
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 3) = 0;
      __ExceptionPtrCreate(v12 + 16);
      *(_QWORD *)(a1 + 160) = v13;
      *(_BYTE *)(v13 + 2304) = 0;
      p9fs::Handler::Run__ResumeCoro_1(v13, v14, v15, v16);
      if ( !*(_BYTE *)(*(_QWORD *)(a1 + 160) - 24LL) )
      {
        *v5 = 4;
        if ( (unsigned __int8)p9fs::Task<void>::await_suspend(a1 + 160, a1) )
          return;
      }
      goto LABEL_10;
    case 4:
LABEL_10:
      v18 = (const struct std::exception_ptr *)(*(_QWORD *)(a1 + 160) - 16LL);
      if ( __ExceptionPtrToBool(v18) )
      {
        v20 = std::exception_ptr::exception_ptr((std::exception_ptr *)(a1 + 2544), v18);
        std::rethrow_exception(v20);
      }
      v21 = *(_QWORD *)(a1 + 160);
      if ( v21 )
      {
        if ( *(_WORD *)(v21 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            v19);
        *(_QWORD *)(v21 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD))v21)(*(_QWORD *)(a1 + 160));
      }
      p9fs::Handler::~Handler((p9fs::Handler *)(a1 + 32));
      v24 = *(volatile signed __int64 **)(a1 + 16);
      _InterlockedDecrement64(v24);
      Plan9TraceLoggingProvider::ClientDisconnected<std::atomic<unsigned __int64> &>(v24);
      *(_BYTE *)(a1 + 168) = 0;
      *v5 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(
        v22,
        a1);
      break;
    case 5:
      v17 = *(_QWORD *)(a1 + 160);
      if ( v17 )
      {
        if ( *(_WORD *)(v17 + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
            a4);
        *(_QWORD *)(v17 + 8) |= 1uLL;
        (*(void (__fastcall **)(_QWORD))v17)(*(_QWORD *)(a1 + 160));
        *(_QWORD *)(a1 + 160) = 0;
      }
      p9fs::Handler::~Handler((p9fs::Handler *)(a1 + 32));
      v23 = *(volatile signed __int64 **)(a1 + 16);
      _InterlockedDecrement64(v23);
      Plan9TraceLoggingProvider::ClientDisconnected<std::atomic<unsigned __int64> &>(v23);
LABEL_17:
      __ExceptionPtrDestroy((void *)(a1 - 16));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 32), 0xA40u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18000e5a0  mov     r11, rsp
0x18000e5a3  mov     [r11+10h], rbx
0x18000e5a7  mov     [r11+18h], rsi
0x18000e5ab  mov     [r11+8], rcx
0x18000e5af  push    rdi
0x18000e5b0  push    r12
0x18000e5b2  push    r13
0x18000e5b4  push    r14
0x18000e5b6  push    r15
0x18000e5b8  sub     rsp, 80h
0x18000e5bf  mov     rax, cs:__security_cookie
0x18000e5c6  xor     rax, rsp
0x18000e5c9  mov     [rsp+0A8h+var_38], rax
0x18000e5ce  mov     r15, rcx
0x18000e5d1  mov     [rsp+0A8h+var_78], rcx
0x18000e5d6  lea     r13, [r15+8]
0x18000e5da  mov     [rsp+0A8h+var_70], r13
0x18000e5df  movzx   eax, word ptr [r13+0]
0x18000e5e4  mov     [rsp+0A8h+var_80], ax
0x18000e5e9  mov     edi, 1
0x18000e5ee  add     ax, di
0x18000e5f1  cmp     ax, 6; switch 7 cases
0x18000e5f5  ja      def_18000E610; jumptable 000000018000E610 default case, case 1
0x18000e5fb  movsx   rax, ax
0x18000e5ff  lea     rdx, cs:180000000h
0x18000e606  mov     ecx, ds:(jpt_18000E610 - 180000000h)[rdx+rax*4]
0x18000e60d  add     rcx, rdx
0x18000e610  jmp     rcx; switch jump
0x18000e612  xor     r12d, r12d; jumptable 000000018000E610 case 4
0x18000e615  jmp     loc_18000E8BB
0x18000e61a  mov     rsi, [r13+0A10h]; jumptable 000000018000E610 case 3
0x18000e621  mov     rax, [rsi+10h]
0x18000e625  mov     [r15+10h], rax
0x18000e629  mov     [r15+18h], dil
0x18000e62d  lea     r14, [r15+20h]
0x18000e631  xor     edx, edx; Val
0x18000e633  mov     r8d, 80h; Size
0x18000e639  mov     rcx, r14; void *
0x18000e63c  call    memset_0
0x18000e641  mov     rax, [rsi]
0x18000e644  mov     rdi, [rsi+18h]
0x18000e648  lea     rcx, ??_7Handler@p9fs@@6B@; const p9fs::Handler::`vftable'
0x18000e64f  mov     [r14], rcx
0x18000e652  xor     r12d, r12d
0x18000e655  mov     [r15+28h], r12
0x18000e659  mov     [r15+30h], r12
0x18000e65d  mov     [r15+38h], rax
0x18000e661  mov     [r15+40h], r12
0x18000e665  mov     [r15+48h], r12
0x18000e669  mov     [r15+50h], r12
0x18000e66d  lea     ecx, [r12+38h]; Size
0x18000e672  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e677  mov     [rax], rax
0x18000e67a  mov     [rax+8], rax
0x18000e67e  mov     [rax+10h], rax
0x18000e682  mov     word ptr [rax+18h], 101h
0x18000e688  mov     [r15+48h], rax
0x18000e68c  lea     rcx, [r15+58h]
0x18000e690  mov     edx, 40000h
0x18000e695  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x18000e69a  mov     [r15+70h], r12
0x18000e69e  mov     [r15+78h], r12
0x18000e6a2  lea     rcx, [r15+80h]
0x18000e6a9  call    ??$make_shared@URequestList@Handler@p9fs@@$$V@std@@YA?AV?$shared_ptr@URequestList@Handler@p9fs@@@0@XZ; std::make_shared<p9fs::Handler::RequestList,>(void)
0x18000e6ae  mov     dword ptr [r15+90h], 40h ; '@'
0x18000e6b9  mov     [r15+94h], r12w
0x18000e6c1  mov     [r15+96h], r12b
0x18000e6c8  mov     [r15+98h], rdi
0x18000e6cf  mov     rbx, [rsi+20h]
0x18000e6d3  mov     ecx, 940h; Size
0x18000e6d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e6dd  lea     rdi, [rax+20h]
0x18000e6e1  mov     [rdi+908h], r14
0x18000e6e8  mov     [rdi+910h], rbx
0x18000e6ef  lea     rcx, p9fs__Handler__Run$_ResumeCoro$1
0x18000e6f6  mov     [rdi], rcx
0x18000e6f9  mov     dword ptr [rdi+8], 10002h
0x18000e700  mov     [rax+9], r12d
0x18000e704  xor     ecx, ecx
0x18000e706  mov     [rax+0Dh], cx
0x18000e70a  mov     [rax+0Fh], r12b
0x18000e70e  mov     [rax], r12
0x18000e711  mov     [rax+8], r12b
0x18000e715  lea     rcx, [rax+10h]
0x18000e719  mov     [rcx], r12
0x18000e71c  mov     [rcx+8], r12
0x18000e720  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000e726  lea     rbx, [r15+0A0h]
0x18000e72d  mov     [rbx], rdi
0x18000e730  xor     eax, eax
0x18000e732  mov     [rdi+900h], al
0x18000e738  mov     rcx, rdi
0x18000e73b  call    p9fs__Handler__Run$_ResumeCoro$1
0x18000e740  nop
0x18000e741  mov     rax, [rbx]
0x18000e744  mov     [rsp+0A8h+var_88], rax
0x18000e749  mov     dl, [rax-18h]
0x18000e74c  nop
0x18000e74d  test    dl, dl
0x18000e74f  jnz     loc_18000E7F2
0x18000e755  lea     eax, [r12+4]
0x18000e75a  mov     [r13+0], ax
0x18000e75f  mov     rdx, r15
0x18000e762  mov     rcx, rbx
0x18000e765  call    ?await_suspend@?$Task@X@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<void>::await_suspend(std::experimental::coroutine_handle<void>)
0x18000e76a  test    al, al
0x18000e76c  jz      loc_18000E7F2
0x18000e772  jmp     loc_18000E8DD
0x18000e777  mov     rax, [r15+0A0h]; jumptable 000000018000E610 case 6
0x18000e77e  mov     [rsp+0A8h+var_88], rax
0x18000e783  xor     r12d, r12d
0x18000e786  test    rax, rax
0x18000e789  jz      short loc_18000E7CB
0x18000e78b  mov     rcx, [rsp+0A8h]; this
0x18000e793  cmp     [rax+8], r12w
0x18000e798  jz      short loc_18000E7AC
0x18000e79a  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000e7a1  lea     edx, [r12+34h]; void *
0x18000e7a6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000e7ac  or      [rax+8], rdi
0x18000e7b0  mov     rax, [rax]
0x18000e7b3  mov     rcx, [r15+0A0h]
0x18000e7ba  mov     [rsp+0A8h+var_88], rcx
0x18000e7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c4  mov     [r15+0A0h], r12
0x18000e7cb  lea     rcx, [r15+20h]; this
0x18000e7cf  call    ??1Handler@p9fs@@UEAA@XZ; p9fs::Handler::~Handler(void)
0x18000e7d4  nop
0x18000e7d5  mov     rcx, [r15+10h]
0x18000e7d9  mov     [rsp+0A8h+var_60], rcx
0x18000e7de  lock dec qword ptr [rcx]
0x18000e7e2  call    ??$ClientDisconnected@AEAU?$atomic@_K@std@@@Plan9TraceLoggingProvider@@SAXAEAU?$atomic@_K@std@@@Z; Plan9TraceLoggingProvider::ClientDisconnected<std::atomic<unsigned __int64> &>(std::atomic<unsigned __int64> &)
0x18000e7e7  nop
0x18000e7e8  jmp     loc_18000E8BB
0x18000e7ed  xor     r12d, r12d; jumptable 000000018000E610 case 5
0x18000e7f0  jmp     short loc_18000E7F7
0x18000e7f2  mov     edi, 1
0x18000e7f7  mov     rax, [r15+0A0h]
0x18000e7fe  mov     [rsp+0A8h+var_88], rax
0x18000e803  lea     rbx, [rax-10h]
0x18000e807  mov     rcx, rbx
0x18000e80a  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18000e810  test    al, al
0x18000e812  jz      short loc_18000E82C
0x18000e814  lea     rcx, [r15+9F0h]; this
0x18000e81b  mov     rdx, rbx; struct std::exception_ptr *
0x18000e81e  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x18000e823  mov     rcx, rax
0x18000e826  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18000e82c  mov     rax, [r15+0A0h]
0x18000e833  mov     [rsp+0A8h+var_88], rax
0x18000e838  test    rax, rax
0x18000e83b  jz      short loc_18000E877
0x18000e83d  mov     rcx, [rsp+0A8h]; this
0x18000e845  cmp     [rax+8], r12w
0x18000e84a  jz      short loc_18000E85E
0x18000e84c  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000e853  mov     edx, 34h ; '4'; void *
0x18000e858  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000e85e  or      [rax+8], rdi
0x18000e862  mov     rax, [rax]
0x18000e865  mov     rcx, [r15+0A0h]
0x18000e86c  mov     [rsp+0A8h+var_88], rcx
0x18000e871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e876  nop
0x18000e877  lea     rcx, [r15+20h]; this
0x18000e87b  call    ??1Handler@p9fs@@UEAA@XZ; p9fs::Handler::~Handler(void)
0x18000e880  nop
0x18000e881  mov     rcx, [r15+10h]
0x18000e885  mov     [rsp+0A8h+var_60], rcx
0x18000e88a  lock dec qword ptr [rcx]
0x18000e88e  call    ??$ClientDisconnected@AEAU?$atomic@_K@std@@@Plan9TraceLoggingProvider@@SAXAEAU?$atomic@_K@std@@@Z; Plan9TraceLoggingProvider::ClientDisconnected<std::atomic<unsigned __int64> &>(std::atomic<unsigned __int64> &)
0x18000e893  nop
0x18000e894  jmp     short loc_18000E8A0
0x18000e896  mov     r13, [rsp+0A8h+var_70]
0x18000e89b  mov     r15, [rsp+0A8h+var_78]
0x18000e8a0  xor     eax, eax
0x18000e8a2  mov     [r15+0A8h], al
0x18000e8a9  mov     [r13+0], ax
0x18000e8ae  mov     rdx, r15
0x18000e8b1  call    ??$await_suspend@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@XV?$Task@X@p9fs@@VTaskPromise@2@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<void,p9fs::Task<void>,p9fs::TaskPromise>>)
0x18000e8b6  jmp     short loc_18000E8DD
0x18000e8b8  xor     r12d, r12d; jumptable 000000018000E610 cases 0,2
0x18000e8bb  lea     rcx, [r15-10h]
0x18000e8bf  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18000e8c5  cmp     [r15+0Ah], r12w
0x18000e8ca  jz      short loc_18000E8DD
0x18000e8cc  mov     edx, 0A40h; unsigned __int64
0x18000e8d1  lea     rcx, [r15-20h]; void *
0x18000e8d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e8da  jmp     short loc_18000E8DD
0x18000e8dc  int     3; Trap to Debugger
0x18000e8dd  mov     rcx, [rsp+0A8h+var_38]
0x18000e8e2  xor     rcx, rsp; StackCookie
0x18000e8e5  call    __security_check_cookie
0x18000e8ea  lea     r11, [rsp+0A8h+var_28]
0x18000e8f2  mov     rbx, [r11+38h]
0x18000e8f6  mov     rsi, [r11+40h]
0x18000e8fa  mov     rsp, r11
0x18000e8fd  pop     r15
0x18000e8ff  pop     r14
0x18000e901  pop     r13
0x18000e903  pop     r12
0x18000e905  pop     rdi
0x18000e906  retn
```
