# p9fs::Plan9FileSystem::Teardown(void)

- ea: `0x180027950`
- end: `0x180027b92`
- name: `?Teardown@Plan9FileSystem@p9fs@@UEAAJXZ`
- size: `578`
- prototype: `__int64 __fastcall(p9fs::Plan9FileSystem *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1800245d4`

## callees

- `0x180002c6c`
- `0x180004120`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000ca98`
- `0x18000fddc`
- `0x180016684`
- `0x18001c924`
- `0x180027950`
- `0x18002b720`
- `0x180034010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027a02`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027a1f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027a8b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027aa7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027a02`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027a1f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027a8b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180027aa7`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180027a50`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180027a50`
- `msvcp_win!_Mtx_lock` at `0x1800279f3`
- `msvcp_win!_Mtx_lock` at `0x180027a7c`
- `msvcp_win!_Mtx_lock` at `0x1800279f3`
- `msvcp_win!_Mtx_lock` at `0x180027a7c`
- `msvcp_win!_Mtx_unlock` at `0x180027a61`
- `msvcp_win!_Mtx_unlock` at `0x180027ace`
- `msvcp_win!_Mtx_unlock` at `0x180027a61`
- `msvcp_win!_Mtx_unlock` at `0x180027ace`
- `msvcp_win!_Cnd_wait` at `0x180027a39`
- `msvcp_win!_Cnd_wait` at `0x180027a39`

## string_xrefs

- `0x180027b61`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::Plan9FileSystem::Teardown(p9fs::Plan9FileSystem *this)
{
  p9fs::Plan9FileSystem *v1; // r14
  volatile signed __int32 **v2; // rsi
  _DWORD *v3; // rcx
  struct _Mtx_internal_imp_t *v4; // rbx
  ULONGLONG v5; // r15
  int v6; // eax
  volatile signed __int32 *v7; // rax
  struct _Cnd_internal_imp_t *v8; // r12
  wil *v9; // rcx
  const char *v10; // r9
  volatile signed __int32 *v11; // rbx
  const struct std::exception_ptr *v13; // rax
  std::exception_ptr *v14; // rax
  const char *v15; // r9
  volatile signed __int32 **v16; // [rsp+30h] [rbp-68h]
  struct _Mtx_internal_imp_t *v20; // [rsp+40h] [rbp-58h]
  char v22[16]; // [rsp+48h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = this;
  v2 = (volatile signed __int32 **)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
  {
    v16 = (volatile signed __int32 **)((char *)this + 56);
    v3 = (_DWORD *)*((_QWORD *)Plan9TraceLoggingProvider::Instance() + 1);
    if ( *v3 > 4u )
      tlgWriteTransfer_EventWriteTransfer((__int64)v3, (unsigned __int8 *)&word_18003955E, 0, 0, 2u, &v23);
    v4 = (p9fs::Plan9FileSystem *)((char *)v1 + 72);
    v20 = (p9fs::Plan9FileSystem *)((char *)v1 + 72);
    p9fs::CancelToken::Cancel((p9fs::Plan9FileSystem *)((char *)v1 + 72));
    v23 = 0;
    v5 = (ULONGLONG)(*v2 + 4);
    v23.Ptr = v5;
    LOBYTE(v23.Size) = 0;
    v6 = _Mtx_lock((_Mtx_t)v5);
    try
    {
      if ( v6 )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v5 + 76) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v5 + 76) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      LOBYTE(v23.Size) = 1;
      v7 = *v2;
      v8 = (struct _Cnd_internal_imp_t *)(*v2 + 24);
      while ( !*((_BYTE *)v7 + 168) )
      {
        _Cnd_wait(v8, (_Mtx_t)v5);
        v7 = *v2;
      }
      if ( __ExceptionPtrToBool((const void *)*v2) )
      {
        v13 = (const struct std::exception_ptr *)std::shared_ptr<p9fs::AsyncTask::Storage>::operator-><p9fs::AsyncTask::Storage,0>(v2);
        v14 = std::exception_ptr::exception_ptr((std::exception_ptr *)v22, v13);
        std::rethrow_exception(v14);
      }
      _Mtx_unlock((_Mtx_t)v5);
    }
    catch ( ... )
    {
      if ( (unsigned int)wil::ResultFromCaughtException(v9) != -2147023901 )
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x2AC,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
          v15);
      v2 = v16;
      v1 = this;
      v4 = v20;
    }
    if ( _Mtx_lock(v4) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v4 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    if ( *((_QWORD *)v4 + 10)
      || *((struct _Mtx_internal_imp_t **)v4 + 13) != (struct _Mtx_internal_imp_t *)((char *)v4 + 104) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x38A,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
        v10);
    }
    *((_BYTE *)v4 + 88) = 0;
    _Mtx_unlock(v4);
    *v2 = 0;
    v11 = v2[1];
    v2[1] = 0;
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  p9fs::Socket::Reset((p9fs::Plan9FileSystem *)((char *)v1 + 16), (void *)0xFFFFFFFFFFFFFFFFLL);
  return 0;
}

```

## disassembly

```asm
0x180027950  mov     [rsp+arg_8], rbx
0x180027955  mov     [rsp+arg_10], rsi
0x18002795a  push    r12
0x18002795c  push    r14
0x18002795e  push    r15
0x180027960  sub     rsp, 80h
0x180027967  mov     rax, cs:__security_cookie
0x18002796e  xor     rax, rsp
0x180027971  mov     [rsp+98h+var_20], rax
0x180027976  mov     r14, rcx
0x180027979  mov     [rsp+98h+var_60], rcx
0x18002797e  lea     rsi, [rcx+38h]
0x180027982  cmp     qword ptr [rsi], 0
0x180027986  jz      loc_180027B23
0x18002798c  mov     [rsp+98h+var_68], rsi
0x180027991  call    ?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ; Plan9TraceLoggingProvider::Instance(void)
0x180027996  mov     rcx, [rax+8]; int
0x18002799a  mov     eax, [rcx]
0x18002799c  cmp     eax, 4
0x18002799f  jbe     short loc_1800279C5
0x1800279a1  lea     rax, [rsp+98h+var_40]
0x1800279a6  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x1800279ab  mov     [rsp+98h+var_78], 2; ULONG
0x1800279b3  xor     r9d, r9d; int
0x1800279b6  xor     r8d, r8d; int
0x1800279b9  lea     rdx, word_18003955E; int
0x1800279c0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800279c5  lea     rbx, [r14+48h]
0x1800279c9  mov     [rsp+98h+var_58], rbx
0x1800279ce  mov     rcx, rbx; this
0x1800279d1  call    ?Cancel@CancelToken@p9fs@@QEAAXXZ; p9fs::CancelToken::Cancel(void)
0x1800279d6  nop
0x1800279d7  xorps   xmm0, xmm0
0x1800279da  movups  xmmword ptr [rsp+98h+var_40.Ptr], xmm0
0x1800279df  mov     r15, [rsi]
0x1800279e2  add     r15, 10h
0x1800279e6  mov     [rsp+98h+var_40.Ptr], r15
0x1800279eb  mov     byte ptr [rsp+98h+var_40.Size], 0
0x1800279f0  mov     rcx, r15; _Mtx_t
0x1800279f3  call    cs:__imp__Mtx_lock
0x1800279f9  test    eax, eax
0x1800279fb  jz      short loc_180027A08
0x1800279fd  mov     ecx, 5
0x180027a02  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180027a08  cmp     dword ptr [r15+4Ch], 7FFFFFFFh
0x180027a10  jnz     short loc_180027A25
0x180027a12  mov     dword ptr [r15+4Ch], 7FFFFFFEh
0x180027a1a  mov     ecx, 6
0x180027a1f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180027a25  mov     byte ptr [rsp+98h+var_40.Size], 1
0x180027a2a  mov     rax, [rsi]
0x180027a2d  lea     r12, [rax+60h]
0x180027a31  jmp     short loc_180027A42
0x180027a33  mov     rdx, r15; _Mtx_t
0x180027a36  mov     rcx, r12; _Cnd_t
0x180027a39  call    cs:__imp__Cnd_wait
0x180027a3f  mov     rax, [rsi]
0x180027a42  mov     cl, [rax+0A8h]
0x180027a48  test    cl, cl
0x180027a4a  nop
0x180027a4b  jz      short loc_180027A33
0x180027a4d  mov     rcx, [rsi]
0x180027a50  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180027a56  test    al, al
0x180027a58  jnz     loc_180027B73
0x180027a5e  mov     rcx, r15; _Mtx_t
0x180027a61  call    cs:__imp__Mtx_unlock
0x180027a67  nop
0x180027a68  jmp     short loc_180027A79
0x180027a6a  mov     rsi, [rsp+98h+var_68]
0x180027a6f  mov     r14, [rsp+98h+var_60]
0x180027a74  mov     rbx, [rsp+98h+var_58]
0x180027a79  mov     rcx, rbx; _Mtx_t
0x180027a7c  call    cs:__imp__Mtx_lock
0x180027a82  test    eax, eax
0x180027a84  jz      short loc_180027A92
0x180027a86  mov     ecx, 5
0x180027a8b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180027a91  int     3; Trap to Debugger
0x180027a92  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180027a99  jnz     short loc_180027AAE
0x180027a9b  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180027aa2  mov     ecx, 6
0x180027aa7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180027aad  int     3; Trap to Debugger
0x180027aae  cmp     qword ptr [rbx+50h], 0
0x180027ab3  jnz     loc_180027B59
0x180027ab9  lea     rax, [rbx+68h]
0x180027abd  cmp     [rax], rax
0x180027ac0  jnz     loc_180027B59
0x180027ac6  xor     eax, eax
0x180027ac8  xchg    al, [rbx+58h]
0x180027acb  mov     rcx, rbx; _Mtx_t
0x180027ace  call    cs:__imp__Mtx_unlock
0x180027ad4  mov     qword ptr [rsi], 0
0x180027adb  mov     rbx, [rsi+8]
0x180027adf  mov     qword ptr [rsi+8], 0
0x180027ae7  test    rbx, rbx
0x180027aea  jz      short loc_180027B23
0x180027aec  or      eax, 0FFFFFFFFh
0x180027aef  lock xadd [rbx+8], eax
0x180027af4  cmp     eax, 1
0x180027af7  jnz     short loc_180027B23
0x180027af9  mov     rax, [rbx]
0x180027afc  mov     rcx, rbx
0x180027aff  mov     rax, [rax]
0x180027b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b07  or      eax, 0FFFFFFFFh
0x180027b0a  lock xadd [rbx+0Ch], eax
0x180027b0f  cmp     eax, 1
0x180027b12  jnz     short loc_180027B23
0x180027b14  mov     rax, [rbx]
0x180027b17  mov     rcx, rbx
0x180027b1a  mov     rax, [rax+8]
0x180027b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b23  lea     rcx, [r14+10h]; this
0x180027b27  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180027b2b  call    ?Reset@Socket@p9fs@@QEAAX_K@Z; p9fs::Socket::Reset(unsigned __int64)
0x180027b30  xor     eax, eax
0x180027b32  mov     rcx, [rsp+98h+var_20]
0x180027b37  xor     rcx, rsp; StackCookie
0x180027b3a  call    __security_check_cookie
0x180027b3f  lea     r11, [rsp+98h+var_18]
0x180027b47  mov     rbx, [r11+28h]
0x180027b4b  mov     rsi, [r11+30h]
0x180027b4f  mov     rsp, r11
0x180027b52  pop     r15
0x180027b54  pop     r14
0x180027b56  pop     r12
0x180027b58  retn
0x180027b59  mov     rcx, [rsp+98h]; this
0x180027b61  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180027b68  mov     edx, 38Ah; void *
0x180027b6d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180027b73  mov     rcx, rsi
0x180027b76  call    ??$?CUStorage@AsyncTask@p9fs@@$0A@@?$shared_ptr@UStorage@AsyncTask@p9fs@@@std@@QEBAPEAUStorage@AsyncTask@p9fs@@XZ; std::shared_ptr<p9fs::AsyncTask::Storage>::operator-><p9fs::AsyncTask::Storage,0>(void)
0x180027b7b  mov     rdx, rax; struct std::exception_ptr *
0x180027b7e  lea     rcx, [rsp+98h+var_50]; this
0x180027b83  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x180027b88  mov     rcx, rax
0x180027b8b  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
```
