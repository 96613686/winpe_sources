# p9fs::Handler::FillData$_ResumeCoro$1

- ea: `0x180010160`
- end: `0x18001041c`
- name: `p9fs::Handler::FillData$_ResumeCoro$1`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180010424`

## callees

- `0x180004534`
- `0x180004c74`
- `0x180005b24`
- `0x180005dd0`
- `0x1800074e0`
- `0x180010160`
- `0x18001c7c4`
- `0x18001c924`
- `0x18001c93c`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800103d4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800103d4`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001025c`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18001025c`

## string_xrefs

- `0x180010224`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18001029b`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall p9fs::Handler::FillData__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v6; // rax
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  char *v10; // rdx
  size_t v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  const char *v14; // r9
  std::exception_ptr *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  gsl::details *v18; // rcx
  __int64 v19; // r10
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // r8
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_35;
    case 2:
      v6 = *(_QWORD *)(a1 + 104);
      v7 = *(_DWORD *)(v6 + 80);
      *(_DWORD *)(a1 + 12) = v7;
      v8 = v7;
      if ( !v7 )
        break;
      v9 = *(_QWORD **)(v6 + 56);
      if ( *(_QWORD **)(v6 + 88) == v9 )
        break;
      v10 = *(char **)(v6 + 88);
      v11 = *(_QWORD *)(v6 + 80);
      if ( v10 > &v10[v11] )
        goto LABEL_34;
      memmove_0(v9, v10, v11);
      break;
    case 4:
      goto LABEL_11;
    case 5:
      v12 = *(_QWORD *)(a1 + 16);
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
      }
LABEL_35:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0xB0u);
      return;
    default:
      __debugbreak();
      return;
  }
  while ( v8 < *(_DWORD *)(a1 + 112) )
  {
    v18 = *(gsl::details **)(a1 + 104);
    v19 = *((_QWORD *)v18 + 7);
    v20 = *((_QWORD *)v18 + 8) - v19;
    if ( v20 == -1 || !v19 && v20 || v20 < v8 || (v21 = v20 - v8, v21 == -1) )
      gsl::details::terminate(v18);
    v22 = *((_QWORD *)v18 + 3);
    *(_QWORD *)(a1 + 32) = v21;
    *(_QWORD *)(a1 + 40) = v19 + v8;
    v23 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v22 + 16LL))(
                      v22,
                      a1 + 16,
                      a1 + 32,
                      *(_QWORD *)(a1 + 120));
    *(_QWORD *)(a1 + 80) = v23;
    if ( !*(_BYTE *)(*v23 - 40LL) )
    {
      *(_WORD *)(a1 + 8) = 4;
      if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v23, a1) )
        return;
    }
LABEL_11:
    v13 = **(_QWORD **)(a1 + 80);
    if ( __ExceptionPtrToBool((const void *)(v13 - 32)) )
    {
      v15 = std::exception_ptr::exception_ptr(
              (std::exception_ptr *)(a1 + 48),
              (const struct std::exception_ptr *)(v13 - 32));
      std::rethrow_exception(v15);
    }
    v16 = *(_QWORD *)(v13 - 16);
    v17 = *(_QWORD *)(a1 + 16);
    if ( v17 )
    {
      if ( *(_WORD *)(v17 + 8) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
          v14);
      *(_QWORD *)(v17 + 8) |= 1uLL;
      (*(void (**)(void))v17)();
      *(_QWORD *)(a1 + 16) = 0;
    }
    if ( !v16 )
      break;
    v8 = *(_DWORD *)(a1 + 12) + v16;
    *(_DWORD *)(a1 + 12) = v8;
  }
  v9 = *(_QWORD **)(a1 + 104);
  v24 = v9[7];
  v25 = v9[8] - v24;
  if ( v25 == -1 || !v24 && v25 || (v26 = *(unsigned int *)(a1 + 12), v25 < v26) )
LABEL_34:
    gsl::details::terminate((gsl::details *)v9);
  v9[10] = v26;
  v9[11] = v24;
  *(_BYTE *)(a1 - 16) = *(_DWORD *)(a1 + 12) >= *(_DWORD *)(a1 + 112);
  *(_BYTE *)(a1 + 24) = 0;
  *(_WORD *)(a1 + 8) = 0;
  p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
    v9,
    a1);
}

```

## disassembly

```asm
0x180010160  mov     rax, rsp
0x180010163  mov     [rax+8], rcx
0x180010167  push    rbx
0x180010168  push    rsi
0x180010169  push    rdi
0x18001016a  push    r12
0x18001016c  push    r14
0x18001016e  push    r15
0x180010170  sub     rsp, 68h
0x180010174  mov     rdi, rcx
0x180010177  mov     [rsp+98h+var_58], rcx
0x18001017c  mov     r15, rcx
0x18001017f  mov     [rsp+98h+var_50], rcx
0x180010184  movzx   eax, word ptr [rdi+8]
0x180010188  mov     [rsp+98h+var_68], ax
0x18001018d  mov     r12d, 1
0x180010193  add     ax, r12w
0x180010197  cmp     ax, 6; switch 7 cases
0x18001019b  ja      def_1800101B6; jumptable 00000001800101B6 default case, case 1
0x1800101a1  movsx   rax, ax
0x1800101a5  lea     rdx, cs:180000000h
0x1800101ac  mov     ecx, ds:(jpt_1800101B6 - 180000000h)[rdx+rax*4]
0x1800101b3  add     rcx, rdx
0x1800101b6  jmp     rcx; switch jump
0x1800101b8  xor     esi, esi; jumptable 00000001800101B6 case 4
0x1800101ba  jmp     loc_1800103D0
0x1800101bf  mov     rax, [rdi+68h]; jumptable 00000001800101B6 case 3
0x1800101c3  mov     r14d, [rax+50h]
0x1800101c7  mov     [rdi+0Ch], r14d
0x1800101cb  mov     ebx, r14d
0x1800101ce  xor     esi, esi
0x1800101d0  test    r14d, r14d
0x1800101d3  jz      loc_1800102D5
0x1800101d9  mov     rcx, [rax+38h]; this
0x1800101dd  cmp     [rax+58h], rcx
0x1800101e1  jz      loc_1800102D5
0x1800101e7  mov     rdx, [rax+58h]; Src
0x1800101eb  mov     r8, [rax+50h]; Size
0x1800101ef  lea     rax, [r8+rdx]
0x1800101f3  cmp     rdx, rax
0x1800101f6  ja      loc_1800103C8
0x1800101fc  call    memmove_0
0x180010201  jmp     loc_1800102D5
0x180010206  mov     rax, [rdi+10h]; jumptable 00000001800101B6 case 6
0x18001020a  mov     [rsp+98h+var_60], rax
0x18001020f  xor     esi, esi
0x180010211  test    rax, rax
0x180010214  jz      short loc_18001024A
0x180010216  mov     rcx, [rsp+98h]; this
0x18001021e  cmp     [rax+8], si
0x180010222  jz      short loc_180010234
0x180010224  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18001022b  lea     edx, [rsi+34h]; void *
0x18001022e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180010234  or      [rax+8], r12
0x180010238  mov     rax, [rax]
0x18001023b  mov     rcx, [rdi+10h]
0x18001023f  mov     [rsp+98h+var_60], rcx
0x180010244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010249  nop
0x18001024a  jmp     loc_1800103D0
0x18001024f  xor     esi, esi; jumptable 00000001800101B6 case 5
0x180010251  mov     rbx, [rdi+50h]
0x180010255  mov     rbx, [rbx]
0x180010258  lea     rcx, [rbx-20h]
0x18001025c  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180010262  test    al, al
0x180010264  jz      short loc_18001027B
0x180010266  lea     rcx, [rdi+30h]; this
0x18001026a  lea     rdx, [rbx-20h]; struct std::exception_ptr *
0x18001026e  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180010273  mov     rcx, rax
0x180010276  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18001027b  mov     rbx, [rbx-10h]
0x18001027f  mov     rax, [rdi+10h]
0x180010283  mov     [rsp+98h+var_60], rax
0x180010288  test    rax, rax
0x18001028b  jz      short loc_1800102C6
0x18001028d  mov     rcx, [rsp+98h]; this
0x180010295  cmp     [rax+8], si
0x180010299  jz      short loc_1800102AD
0x18001029b  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x1800102a2  mov     edx, 34h ; '4'; void *
0x1800102a7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800102ad  or      [rax+8], r12
0x1800102b1  mov     rax, [rax]
0x1800102b4  mov     rcx, [rdi+10h]
0x1800102b8  mov     [rsp+98h+var_60], rcx
0x1800102bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102c2  mov     [rdi+10h], rsi
0x1800102c6  test    rbx, rbx
0x1800102c9  jz      loc_18001036F
0x1800102cf  add     ebx, [rdi+0Ch]
0x1800102d2  mov     [rdi+0Ch], ebx
0x1800102d5  lea     rdx, [rdi+10h]
0x1800102d9  cmp     ebx, [rdx+60h]
0x1800102dc  jnb     loc_18001036F
0x1800102e2  mov     rcx, [rdi+68h]; this
0x1800102e6  mov     r10, [rcx+38h]
0x1800102ea  mov     rax, [rcx+40h]
0x1800102ee  sub     rax, r10
0x1800102f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800102f5  jz      short loc_180010369
0x1800102f7  test    r10, r10
0x1800102fa  jnz     short loc_180010301
0x1800102fc  test    rax, rax
0x1800102ff  jnz     short loc_180010369
0x180010301  mov     r9d, ebx
0x180010304  cmp     rax, r9
0x180010307  jb      short loc_180010369
0x180010309  sub     rax, r9
0x18001030c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010310  jz      short loc_180010369
0x180010312  mov     rcx, [rcx+18h]
0x180010316  lea     r8, [rdi+20h]
0x18001031a  mov     [r8], rax
0x18001031d  lea     rax, [r10+r9]
0x180010321  mov     [rdi+28h], rax
0x180010325  mov     rax, [rcx]
0x180010328  mov     r9, [rdi+78h]
0x18001032c  mov     rax, [rax+10h]
0x180010330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010335  mov     rcx, rax
0x180010338  mov     [rdi+50h], rax
0x18001033c  mov     rax, [rax]
0x18001033f  mov     dl, [rax-28h]
0x180010342  nop
0x180010343  test    dl, dl
0x180010345  jnz     loc_180010251
0x18001034b  mov     eax, 4
0x180010350  mov     [rdi+8], ax
0x180010354  mov     rdx, rdi
0x180010357  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x18001035c  test    al, al
0x18001035e  jz      loc_180010251
0x180010364  jmp     loc_1800103F1
0x180010369  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18001036f  mov     rcx, [rdi+68h]
0x180010373  mov     rdx, [rcx+38h]
0x180010377  mov     rax, [rcx+40h]
0x18001037b  sub     rax, rdx
0x18001037e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010382  jz      short loc_1800103C8
0x180010384  test    rdx, rdx
0x180010387  jnz     short loc_18001038E
0x180010389  test    rax, rax
0x18001038c  jnz     short loc_1800103C8
0x18001038e  mov     r8d, [rdi+0Ch]
0x180010392  cmp     rax, r8
0x180010395  jb      short loc_1800103C8
0x180010397  mov     [rcx+50h], r8
0x18001039b  mov     [rcx+58h], rdx
0x18001039f  mov     eax, [rdi+0Ch]
0x1800103a2  cmp     eax, [rdi+70h]
0x1800103a5  setnb   al
0x1800103a8  mov     [rdi-10h], al
0x1800103ab  jmp     short loc_1800103B5
0x1800103ad  mov     r15, [rsp+98h+var_50]
0x1800103b2  mov     rdi, r15
0x1800103b5  xor     eax, eax
0x1800103b7  mov     [rdi+18h], al
0x1800103ba  mov     [rdi+8], ax
0x1800103be  mov     rdx, r15
0x1800103c1  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x1800103c6  jmp     short loc_1800103F1
0x1800103c8  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x1800103ce  xor     esi, esi; jumptable 00000001800101B6 cases 0,2
0x1800103d0  lea     rcx, [rdi-20h]
0x1800103d4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800103da  cmp     [rdi+0Ah], si
0x1800103de  jz      short loc_1800103F1
0x1800103e0  mov     edx, 0B0h; unsigned __int64
0x1800103e5  lea     rcx, [rdi-30h]; void *
0x1800103e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800103ee  jmp     short loc_1800103F1
0x1800103f0  int     3; Trap to Debugger
0x1800103f1  add     rsp, 68h
0x1800103f5  pop     r15
0x1800103f7  pop     r14
0x1800103f9  pop     r12
0x1800103fb  pop     rdi
0x1800103fc  pop     rsi
0x1800103fd  pop     rbx
0x1800103fe  retn
```
