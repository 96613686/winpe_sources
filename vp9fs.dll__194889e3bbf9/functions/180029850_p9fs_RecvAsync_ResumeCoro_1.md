# p9fs::RecvAsync$_ResumeCoro$1

- ea: `0x180029850`
- end: `0x180029a18`
- name: `p9fs::RecvAsync$_ResumeCoro$1`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18002b650`

## callees

- `0x180004120`
- `0x180004534`
- `0x180005b24`
- `0x18000ae8c`
- `0x180028e10`
- `0x180029850`
- `0x180029e3c`
- `0x180029ec0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800299c5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800299c5`

## string_xrefs

- `0x18002997b`: `onecore\vm\dv\storage\plan9\dll\windows\p9io.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall p9fs::RecvAsync__ResumeCoro_1(__int64 a1)
{
  _WORD *v2; // rsi
  __int64 v3; // rcx
  _DWORD *v4; // r14
  __int64 v5; // rcx
  unsigned int v6; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
    case 5:
      __ExceptionPtrDestroy((void *)(a1 - 32));
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 48), 0x120u);
      break;
    case 2:
      *(_QWORD *)(a1 + 16) = &p9fs::CoroutineIoOperation::`vftable';
      *(_QWORD *)(a1 + 72) = 0;
      *(_BYTE *)(a1 + 80) = 0;
      *(_DWORD *)(a1 + 96) = *(_DWORD *)(a1 + 208);
      *(_DWORD *)(a1 + 100) = 0;
      *(_QWORD *)(a1 + 104) = *(_QWORD *)(a1 + 216);
      *(_QWORD *)(a1 + 112) = a1 + 96;
      v6 = a1 + 112;
      v3 = p9fs::CoroutineIoIssuer::Issue__lambda_58792c6c817149607d46bba5bc9ac091___(
             *(_QWORD *)(a1 + 200),
             a1 + 120,
             a1 + 16,
             *(_QWORD *)(a1 + 224));
      *(_QWORD *)(a1 + 176) = v3;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        goto LABEL_4;
      *v2 = 4;
      if ( !(unsigned __int8)p9fs::CoroutineIoIssuer::Awaiter::await_suspend(v3, a1) )
        goto LABEL_4;
      break;
    case 4:
LABEL_4:
      v4 = (_DWORD *)(a1 + 136);
      p9fs::CoroutineIoIssuer::Awaiter::await_resume(*(_QWORD *)(a1 + 176), a1 + 136);
      if ( *(_DWORD *)(a1 + 136) )
      {
        if ( *v4 != 1236 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x66,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9io.cpp",
            (const char *)(unsigned int)*v4,
            v6);
        *(_QWORD *)(a1 - 16) = 0;
      }
      else
      {
        *(_QWORD *)(a1 - 16) = *(unsigned int *)(a1 + 140);
      }
      *(_BYTE *)(a1 + 144) = 0;
      *v2 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
        v5,
        a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x180029850  mov     r11, rsp
0x180029853  mov     [r11+8], rcx
0x180029857  push    rbx
0x180029858  push    rsi
0x180029859  push    rdi
0x18002985a  push    r14
0x18002985c  sub     rsp, 68h
0x180029860  mov     rax, cs:__security_cookie
0x180029867  xor     rax, rsp
0x18002986a  mov     [rsp+88h+var_30], rax
0x18002986f  mov     rbx, rcx
0x180029872  mov     [rsp+88h+var_48], rcx
0x180029877  lea     rsi, [rbx+8]
0x18002987b  mov     [rsp+88h+var_40], rsi
0x180029880  movzx   eax, word ptr [rsi]
0x180029883  mov     [rsp+88h+var_58], ax
0x180029888  inc     ax; switch 7 cases
0x18002988b  cmp     ax, 6
0x18002988f  ja      def_1800298AA; jumptable 00000001800298AA default case, case 0
0x180029895  movsx   rax, ax
0x180029899  lea     rdx, cs:180000000h
0x1800298a0  mov     ecx, ds:(jpt_1800298AA - 180000000h)[rdx+rax*4]
0x1800298a7  add     rcx, rdx
0x1800298aa  jmp     rcx; switch jump
0x1800298ac  jmp     loc_1800299C1; jumptable 00000001800298AA case 3
0x1800298b1  lea     r8, [rbx+10h]; jumptable 00000001800298AA case 2
0x1800298b5  lea     rax, ??_7CoroutineIoOperation@p9fs@@6B@; const p9fs::CoroutineIoOperation::`vftable'
0x1800298bc  mov     [r8], rax
0x1800298bf  xor     edi, edi
0x1800298c1  mov     [rbx+48h], rdi
0x1800298c5  mov     [rbx+50h], dil
0x1800298c9  lea     rcx, [rbx+60h]
0x1800298cd  mov     eax, [r8+0C0h]
0x1800298d4  mov     [rcx], eax
0x1800298d6  xor     eax, eax
0x1800298d8  mov     [rbx+64h], eax
0x1800298db  mov     rax, [rbx+0D8h]
0x1800298e2  mov     [rbx+68h], rax
0x1800298e6  lea     rax, [rbx+70h]
0x1800298ea  mov     [rax], rcx
0x1800298ed  lea     rdx, [rbx+78h]
0x1800298f1  mov     qword ptr [rsp+88h+var_68], rax
0x1800298f6  mov     r9, [rbx+0E0h]
0x1800298fd  mov     rcx, [rsi+0C0h]
0x180029904  call    p9fs__CoroutineIoIssuer__Issue__lambda_58792c6c817149607d46bba5bc9ac091___
0x180029909  mov     rcx, rax
0x18002990c  mov     [rbx+0B0h], rax
0x180029913  mov     rax, [rax]
0x180029916  mov     dl, [rax+40h]
0x180029919  nop
0x18002991a  test    dl, dl
0x18002991c  jnz     short loc_18002993C
0x18002991e  lea     eax, [rdi+4]
0x180029921  mov     [rsi], ax
0x180029924  mov     rdx, rbx
0x180029927  call    ?await_suspend@Awaiter@CoroutineIoIssuer@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::CoroutineIoIssuer::Awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18002992c  test    al, al
0x18002992e  jz      short loc_18002993C
0x180029930  jmp     loc_1800299E4
0x180029935  jmp     loc_1800299C1; jumptable 00000001800298AA case 5
0x18002993a  xor     edi, edi; jumptable 00000001800298AA case 4
0x18002993c  lea     r14, [rbx+88h]
0x180029943  mov     rdx, r14
0x180029946  mov     rcx, [rbx+0B0h]
0x18002994d  call    ?await_resume@Awaiter@CoroutineIoIssuer@p9fs@@QEAA?AUIoResult@3@XZ; p9fs::CoroutineIoIssuer::Awaiter::await_resume(void)
0x180029952  mov     eax, [r14]
0x180029955  mov     [rsp+88h+var_50], eax
0x180029959  test    eax, eax
0x18002995b  jz      short loc_180029992
0x18002995d  mov     eax, [r14]
0x180029960  mov     [rsp+88h+var_50], eax
0x180029964  cmp     eax, 4D4h
0x180029969  jz      short loc_18002998C
0x18002996b  mov     r9d, [r14]; char *
0x18002996e  mov     [rsp+88h+var_50], r9d
0x180029973  mov     rcx, [rsp+88h]; this
0x18002997b  lea     r8, aOnecoreVmDvSto_4; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180029982  mov     edx, 66h ; 'f'; void *
0x180029987  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002998c  mov     [rbx-10h], rdi
0x180029990  jmp     short loc_1800299AC
0x180029992  mov     eax, [rbx+8Ch]
0x180029998  mov     [rsp+88h+var_4C], eax
0x18002999c  mov     [rbx-10h], rax
0x1800299a0  jmp     short loc_1800299AC
0x1800299a2  mov     rsi, [rsp+88h+var_40]
0x1800299a7  mov     rbx, [rsp+88h+var_48]
0x1800299ac  xor     eax, eax
0x1800299ae  mov     [rbx+90h], al
0x1800299b4  mov     [rsi], ax
0x1800299b7  mov     rdx, rbx
0x1800299ba  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x1800299bf  jmp     short loc_1800299E4
0x1800299c1  lea     rcx, [rbx-20h]; jumptable 00000001800298AA cases -1,1
0x1800299c5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800299cb  xor     edi, edi
0x1800299cd  cmp     [rbx+0Ah], di
0x1800299d1  jz      short loc_1800299E4
0x1800299d3  mov     edx, 120h; unsigned __int64
0x1800299d8  lea     rcx, [rbx-30h]; void *
0x1800299dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800299e1  jmp     short loc_1800299E4
0x1800299e3  int     3; Trap to Debugger
0x1800299e4  mov     rcx, [rsp+88h+var_30]
0x1800299e9  xor     rcx, rsp; StackCookie
0x1800299ec  call    __security_check_cookie
0x1800299f1  add     rsp, 68h
0x1800299f5  pop     r14
0x1800299f7  pop     rdi
0x1800299f8  pop     rsi
0x1800299f9  pop     rbx
0x1800299fa  retn
```
