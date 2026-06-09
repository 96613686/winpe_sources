# p9fs::SendAsync$_ResumeCoro$1

- ea: `0x180029a20`
- end: `0x180029bcc`
- name: `p9fs::SendAsync$_ResumeCoro$1`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18002b900`

## callees

- `0x180004120`
- `0x180004534`
- `0x180005b24`
- `0x18000ae8c`
- `0x180028b60`
- `0x180029a20`
- `0x180029e3c`
- `0x180029ec0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180029b76`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180029b76`

## string_xrefs

- `0x180029b32`: `onecore\vm\dv\storage\plan9\dll\windows\p9io.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall p9fs::SendAsync__ResumeCoro_1(__int64 a1)
{
  _WORD *v2; // rsi
  __int64 v3; // rcx
  const char *v4; // r9
  unsigned int v5; // [rsp+20h] [rbp-68h]
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
      v5 = a1 + 112;
      v3 = p9fs::CoroutineIoIssuer::Issue__lambda_368f41a3bd3d19460c6d6a09bbbf9e93___(
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
      p9fs::CoroutineIoIssuer::Awaiter::await_resume(*(_QWORD *)(a1 + 176), a1 + 136);
      v4 = (const char *)*(unsigned int *)(a1 + 136);
      if ( (_DWORD)v4 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9io.cpp",
          v4,
          v5);
      *(_QWORD *)(a1 - 16) = *(unsigned int *)(a1 + 140);
      *(_BYTE *)(a1 + 144) = 0;
      *v2 = 0;
      p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
        retaddr,
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
0x180029a20  mov     r11, rsp
0x180029a23  mov     [r11+8], rcx
0x180029a27  push    rbx
0x180029a28  push    rsi
0x180029a29  push    rdi
0x180029a2a  push    r14
0x180029a2c  sub     rsp, 68h
0x180029a30  mov     rax, cs:__security_cookie
0x180029a37  xor     rax, rsp
0x180029a3a  mov     [rsp+88h+var_30], rax
0x180029a3f  mov     rbx, rcx
0x180029a42  mov     [rsp+88h+var_50], rcx
0x180029a47  lea     rsi, [rbx+8]
0x180029a4b  mov     [rsp+88h+var_40], rsi
0x180029a50  movzx   eax, word ptr [rsi]
0x180029a53  mov     [rsp+88h+var_58], ax
0x180029a58  inc     ax; switch 7 cases
0x180029a5b  cmp     ax, 6
0x180029a5f  ja      def_180029A7A; jumptable 0000000180029A7A default case, case 0
0x180029a65  movsx   rax, ax
0x180029a69  lea     rdx, cs:180000000h
0x180029a70  mov     ecx, ds:(jpt_180029A7A - 180000000h)[rdx+rax*4]
0x180029a77  add     rcx, rdx
0x180029a7a  jmp     rcx; switch jump
0x180029a7c  jmp     loc_180029B72; jumptable 0000000180029A7A case 3
0x180029a81  lea     r8, [rbx+10h]; jumptable 0000000180029A7A case 2
0x180029a85  lea     rax, ??_7CoroutineIoOperation@p9fs@@6B@; const p9fs::CoroutineIoOperation::`vftable'
0x180029a8c  mov     [r8], rax
0x180029a8f  xor     edi, edi
0x180029a91  mov     [rbx+48h], rdi
0x180029a95  mov     [rbx+50h], dil
0x180029a99  lea     rcx, [rbx+60h]
0x180029a9d  mov     eax, [r8+0C0h]
0x180029aa4  mov     [rcx], eax
0x180029aa6  xor     eax, eax
0x180029aa8  mov     [rbx+64h], eax
0x180029aab  mov     rax, [rbx+0D8h]
0x180029ab2  mov     [rbx+68h], rax
0x180029ab6  lea     rax, [rbx+70h]
0x180029aba  mov     [rax], rcx
0x180029abd  lea     rdx, [rbx+78h]
0x180029ac1  mov     qword ptr [rsp+88h+var_68], rax
0x180029ac6  mov     r9, [rbx+0E0h]
0x180029acd  mov     rcx, [rsi+0C0h]
0x180029ad4  call    p9fs__CoroutineIoIssuer__Issue__lambda_368f41a3bd3d19460c6d6a09bbbf9e93___
0x180029ad9  mov     rcx, rax
0x180029adc  mov     [rbx+0B0h], rax
0x180029ae3  mov     rax, [rax]
0x180029ae6  mov     dl, [rax+40h]
0x180029ae9  nop
0x180029aea  test    dl, dl
0x180029aec  jnz     short loc_180029B07; jumptable 0000000180029A7A case 4
0x180029aee  lea     eax, [rdi+4]
0x180029af1  mov     [rsi], ax
0x180029af4  mov     rdx, rbx
0x180029af7  call    ?await_suspend@Awaiter@CoroutineIoIssuer@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::CoroutineIoIssuer::Awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x180029afc  test    al, al
0x180029afe  jz      short loc_180029B07; jumptable 0000000180029A7A case 4
0x180029b00  jmp     loc_180029B95
0x180029b05  jmp     short loc_180029B72; jumptable 0000000180029A7A case 5
0x180029b07  lea     r14, [rbx+88h]; jumptable 0000000180029A7A case 4
0x180029b0e  mov     rdx, r14
0x180029b11  mov     rcx, [rbx+0B0h]
0x180029b18  call    ?await_resume@Awaiter@CoroutineIoIssuer@p9fs@@QEAA?AUIoResult@3@XZ; p9fs::CoroutineIoIssuer::Awaiter::await_resume(void)
0x180029b1d  mov     r9d, [r14]; char *
0x180029b20  mov     [rsp+88h+var_48], r9d
0x180029b25  mov     rcx, [rsp+88h]; this
0x180029b2d  test    r9d, r9d
0x180029b30  jz      short loc_180029B43
0x180029b32  lea     r8, aOnecoreVmDvSto_4; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180029b39  mov     edx, 80h; void *
0x180029b3e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029b43  mov     eax, [rbx+8Ch]
0x180029b49  mov     [rsp+88h+var_44], eax
0x180029b4d  mov     [rbx-10h], rax
0x180029b51  jmp     short loc_180029B5D
0x180029b53  mov     rsi, [rsp+88h+var_40]
0x180029b58  mov     rbx, [rsp+88h+var_50]
0x180029b5d  xor     eax, eax
0x180029b5f  mov     [rbx+90h], al
0x180029b65  mov     [rsi], ax
0x180029b68  mov     rdx, rbx
0x180029b6b  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x180029b70  jmp     short loc_180029B95
0x180029b72  lea     rcx, [rbx-20h]; jumptable 0000000180029A7A cases -1,1
0x180029b76  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180029b7c  xor     edi, edi
0x180029b7e  cmp     [rbx+0Ah], di
0x180029b82  jz      short loc_180029B95
0x180029b84  mov     edx, 120h; unsigned __int64
0x180029b89  lea     rcx, [rbx-30h]; void *
0x180029b8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029b92  jmp     short loc_180029B95
0x180029b94  int     3; Trap to Debugger
0x180029b95  mov     rcx, [rsp+88h+var_30]
0x180029b9a  xor     rcx, rsp; StackCookie
0x180029b9d  call    __security_check_cookie
0x180029ba2  add     rsp, 68h
0x180029ba6  pop     r14
0x180029ba8  pop     rdi
0x180029ba9  pop     rsi
0x180029baa  pop     rbx
0x180029bab  retn
```
