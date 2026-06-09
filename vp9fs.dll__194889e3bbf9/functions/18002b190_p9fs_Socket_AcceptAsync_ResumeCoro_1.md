# p9fs::Socket::AcceptAsync$_ResumeCoro$1

- ea: `0x18002b190`
- end: `0x18002b568`
- name: `p9fs::Socket::AcceptAsync$_ResumeCoro$1`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18002b570`

## callees

- `0x180004120`
- `0x180004144`
- `0x180004534`
- `0x180005b24`
- `0x180005dd0`
- `0x1800074e0`
- `0x18000ae8c`
- `0x18001c7c4`
- `0x18001c924`
- `0x1800286fc`
- `0x180028fdc`
- `0x1800292c4`
- `0x18002a5d8`
- `0x18002b190`
- `0x18002b644`
- `0x180034010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b50a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002b50a`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002b34f`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18002b34f`
- `WS2_32!__imp_closesocket` at `0x18002b333`
- `WS2_32!__imp_closesocket` at `0x18002b457`
- `WS2_32!__imp_closesocket` at `0x18002b333`
- `WS2_32!__imp_closesocket` at `0x18002b457`
- `WS2_32!__imp_socket` at `0x18002b228`
- `WS2_32!__imp_socket` at `0x18002b228`

## string_xrefs

- `0x18002b2ee`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18002b3bb`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18002b240`: `onecore\vm\dv\storage\plan9\dll\windows\p9windows.cpp`
- `0x18002b420`: `onecore\vm\dv\storage\plan9\dll\windows\p9windows.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall p9fs::Socket::AcceptAsync__ResumeCoro_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v5; // rsi
  int v6; // r8d
  __int64 v7; // r14
  int v8; // ecx
  p9fs::util *v9; // rax
  unsigned __int64 v10; // rdx
  const char *v11; // r9
  _QWORD *v12; // rcx
  __int64 v13; // rax
  SOCKET v14; // rcx
  __int64 v15; // r15
  const char *v16; // r9
  std::exception_ptr *v17; // rcx
  __int64 v18; // rax
  unsigned int *v19; // rax
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 v22; // r15
  void *v23; // r14
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  unsigned int v25; // [rsp+20h] [rbp-C8h]
  int v26; // [rsp+28h] [rbp-C0h]
  int v27; // [rsp+30h] [rbp-B8h]
  struct _TP_IO *FileHandle; // [rsp+50h] [rbp-98h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v5 = a1 + 8;
  v6 = 6;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 6u )
  {
LABEL_41:
    __debugbreak();
  }
  else
  {
    switch ( *(_WORD *)(a1 + 8) )
    {
      case 0xFFFF:
      case 1:
      case 3:
        goto LABEL_37;
      case 0:
        goto LABEL_41;
      case 2:
        v7 = *(_QWORD *)(a1 + 248);
        if ( *(_BYTE *)(v7 + 32) )
        {
          v8 = 2;
        }
        else
        {
          v8 = 34;
          v6 = 1;
        }
        v9 = (p9fs::util *)socket(v8, 1, v6);
        *(_QWORD *)(a1 + 16) = v9;
        if ( v9 == (p9fs::util *)-1LL )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x21,
            (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9windows.cpp",
            v11);
        if ( !*(_BYTE *)(v7 + 32) )
          p9fs::util::SetConnectedSuspendFlag(v9, v10);
        v12 = p9fs::AcceptExAsync(
                (_QWORD *)(a1 + 144),
                v7 + 16,
                *(_QWORD *)(a1 + 16),
                a1 + 32,
                v25,
                v26,
                v27,
                *(_QWORD *)(a1 + 256));
        *(_QWORD *)(a1 + 176) = v12;
        if ( !*(_BYTE *)(*v12 - 40LL) )
        {
          *(_WORD *)v5 = 4;
          if ( (unsigned __int8)p9fs::Task<unsigned __int64>::await_suspend(v12, a1) )
            return;
        }
        goto LABEL_20;
      case 4:
LABEL_20:
        v15 = **(_QWORD **)(a1 + 176);
        if ( __ExceptionPtrToBool((const void *)(v15 - 32)) )
        {
          v17 = std::exception_ptr::exception_ptr(
                  (std::exception_ptr *)(a1 + 192),
                  (const struct std::exception_ptr *)(v15 - 32));
          std::rethrow_exception(v17);
        }
        *(_BYTE *)(a1 + 152) = *(_BYTE *)(v15 - 16);
        *(_BYTE *)(a1 + 156) = 0;
        *(_DWORD *)(a1 + 156) = *(_DWORD *)(v15 - 12);
        if ( *(_QWORD *)(a1 + 144) )
        {
          if ( *(_WORD *)(*(_QWORD *)(a1 + 144) + 8LL) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x34,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
              v16);
          v18 = *(_QWORD *)(a1 + 144);
          *(_QWORD *)(v18 + 8) |= 1uLL;
          (*(void (**)(void))v18)();
        }
        if ( *(_BYTE *)(a1 + 152) )
        {
          v22 = *(_QWORD *)(v5 + 240);
          FileHandle = *(struct _TP_IO **)(a1 + 16);
          *(_QWORD *)(a1 + 16) = -1;
          v23 = operator new(0x28u);
          *(_QWORD *)(a1 + 208) = v23;
          LOBYTE(v22) = *(_BYTE *)(v22 + 32);
          *(_QWORD *)v23 = &p9fs::Socket::`vftable';
          *((_QWORD *)v23 + 1) = FileHandle;
          p9fs::CoroutineIoIssuer::CoroutineIoIssuer((PTP_IO *)v23 + 2, FileHandle);
          *((_BYTE *)v23 + 32) = v22;
          v21 = *(void (__fastcall ****)(_QWORD, __int64))(a1 - 16);
          *(_QWORD *)(a1 - 16) = v23;
          if ( v21 )
            (**v21)(v21, 1);
        }
        else
        {
          if ( *(_DWORD *)(a1 + 156) != 995 )
          {
            v19 = (unsigned int *)util::BasicExpected<unsigned long,unsigned long>::Error(a1 + 152);
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x30,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9windows.cpp",
              (const char *)*v19,
              v25);
          }
          v20 = *(void (__fastcall ****)(_QWORD, __int64))(a1 - 16);
          *(_QWORD *)(a1 - 16) = 0;
          if ( v20 )
            (**v20)(v20, 1);
          v21 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 16);
          if ( v21 != (void (__fastcall ***)(_QWORD, __int64))-1LL )
            closesocket((SOCKET)v21);
        }
        *(_BYTE *)(a1 + 160) = 0;
        *(_WORD *)v5 = 0;
        p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<enum gsl::byte,-1>,p9fs::Task<gsl::span<enum gsl::byte,-1>>,p9fs::TaskPromise>>(
          v21,
          a1);
        break;
      case 5:
        if ( *(_QWORD *)(a1 + 144) )
        {
          if ( *(_WORD *)(*(_QWORD *)(a1 + 144) + 8LL) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x34,
              (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
              a4);
          v13 = *(_QWORD *)(a1 + 144);
          *(_QWORD *)(v13 + 8) |= 1uLL;
          (*(void (**)(void))v13)();
          *(_QWORD *)(a1 + 144) = 0;
        }
        v14 = *(_QWORD *)(a1 + 16);
        if ( v14 != -1 )
          closesocket(v14);
LABEL_37:
        v24 = *(void (__fastcall ****)(_QWORD, __int64))(a1 - 16);
        if ( v24 )
          (**v24)(v24, 1);
        __ExceptionPtrDestroy((void *)(a1 - 32));
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 48), 0x140u);
        break;
    }
  }
}

```

## disassembly

```asm
0x18002b190  mov     r11, rsp
0x18002b193  mov     [r11+8], rcx
0x18002b197  push    rbx
0x18002b198  push    rsi
0x18002b199  push    rdi
0x18002b19a  push    r12
0x18002b19c  push    r14
0x18002b19e  push    r15
0x18002b1a0  sub     rsp, 0B8h
0x18002b1a7  mov     rax, cs:__security_cookie
0x18002b1ae  xor     rax, rsp
0x18002b1b1  mov     [rsp+0E8h+var_48], rax
0x18002b1b9  mov     rbx, rcx
0x18002b1bc  mov     [rsp+0E8h+var_90], rcx
0x18002b1c1  lea     rsi, [rbx+8]
0x18002b1c5  mov     [rsp+0E8h+var_88], rsi
0x18002b1ca  movzx   eax, word ptr [rsi]
0x18002b1cd  mov     [rsp+0E8h+var_9E], ax
0x18002b1d2  mov     r12d, 1
0x18002b1d8  add     ax, r12w
0x18002b1dc  lea     r8d, [r12+5]
0x18002b1e1  cmp     ax, r8w
0x18002b1e5  ja      loc_18002B526; jumptable 000000018002B200 case 1
0x18002b1eb  movsx   rax, ax
0x18002b1ef  lea     rdx, cs:180000000h
0x18002b1f6  mov     ecx, ds:(jpt_18002B200 - 180000000h)[rdx+rax*4]; switch 7 cases
0x18002b1fd  add     rcx, rdx
0x18002b200  jmp     rcx; switch jump
0x18002b202  xor     edi, edi; jumptable 000000018002B200 case 4
0x18002b204  jmp     loc_18002B4EF
0x18002b209  xor     edi, edi; jumptable 000000018002B200 case 3
0x18002b20b  mov     r14, [rsi+0F0h]
0x18002b212  cmp     [r14+20h], dil
0x18002b216  jz      short loc_18002B21D
0x18002b218  lea     ecx, [rdi+2]
0x18002b21b  jmp     short loc_18002B225
0x18002b21d  mov     ecx, 22h ; '"'; af
0x18002b222  mov     r8d, r12d; protocol
0x18002b225  mov     edx, r12d; type
0x18002b228  call    cs:__imp_socket
0x18002b22e  mov     [rbx+10h], rax
0x18002b232  mov     rcx, [rsp+0E8h]; this
0x18002b23a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b23e  jnz     short loc_18002B24F
0x18002b240  lea     r8, aOnecoreVmDvSto_9; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002b247  lea     edx, [rax+22h]; void *
0x18002b24a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b24f  cmp     [r14+20h], dil
0x18002b253  jnz     short loc_18002B262
0x18002b255  mov     rcx, rax; this
0x18002b258  mov     [rsp+0E8h+FileHandle], rax
0x18002b25d  call    ?SetConnectedSuspendFlag@util@p9fs@@YAX_K@Z; p9fs::util::SetConnectedSuspendFlag(unsigned __int64)
0x18002b262  mov     r8, [rbx+10h]
0x18002b266  mov     [rsp+0E8h+FileHandle], r8
0x18002b26b  lea     r9, [rbx+20h]
0x18002b26f  lea     rdx, [r14+10h]
0x18002b273  lea     rcx, [rbx+90h]
0x18002b27a  mov     rax, [rbx+100h]
0x18002b281  mov     [rsp+0E8h+var_B0], rax
0x18002b286  call    ?AcceptExAsync@p9fs@@YA?AV?$Task@V?$BasicExpected@KK@util@@@1@AEAUCoroutineIoIssuer@1@_KPEAXKKKAEAVCancelToken@1@@Z; p9fs::AcceptExAsync(p9fs::CoroutineIoIssuer &,unsigned __int64,void *,ulong,ulong,ulong,p9fs::CancelToken &)
0x18002b28b  mov     rcx, rax
0x18002b28e  mov     [rbx+0B0h], rax
0x18002b295  mov     rax, [rax]
0x18002b298  mov     dl, [rax-28h]
0x18002b29b  nop
0x18002b29c  test    dl, dl
0x18002b29e  jnz     loc_18002B341
0x18002b2a4  mov     eax, 4
0x18002b2a9  mov     [rsi], ax
0x18002b2ac  mov     rdx, rbx
0x18002b2af  call    ?await_suspend@?$Task@_K@p9fs@@QEAA_NU?$coroutine_handle@X@experimental@std@@@Z; p9fs::Task<unsigned __int64>::await_suspend(std::experimental::coroutine_handle<void>)
0x18002b2b4  test    al, al
0x18002b2b6  jz      loc_18002B341
0x18002b2bc  jmp     loc_18002B527
0x18002b2c1  mov     rax, [rbx+90h]; jumptable 000000018002B200 case 6
0x18002b2c8  mov     [rsp+0E8h+var_A8], rax
0x18002b2cd  xor     edi, edi
0x18002b2cf  test    rax, rax
0x18002b2d2  jz      short loc_18002B329
0x18002b2d4  mov     rax, [rbx+90h]
0x18002b2db  mov     [rsp+0E8h+var_A8], rax
0x18002b2e0  mov     rcx, [rsp+0E8h]; this
0x18002b2e8  cmp     [rax+8], di
0x18002b2ec  jz      short loc_18002B2FE
0x18002b2ee  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18002b2f5  lea     edx, [rdi+34h]; void *
0x18002b2f8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002b2fe  mov     rax, [rbx+90h]
0x18002b305  mov     [rsp+0E8h+var_A8], rax
0x18002b30a  or      [rax+8], r12
0x18002b30e  mov     rcx, [rbx+90h]
0x18002b315  mov     [rsp+0E8h+var_A8], rcx
0x18002b31a  mov     rax, [rax]
0x18002b31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b322  mov     [rbx+90h], rdi
0x18002b329  mov     rcx, [rbx+10h]; s
0x18002b32d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b331  jz      short loc_18002B33A
0x18002b333  call    cs:__imp_closesocket
0x18002b339  nop
0x18002b33a  jmp     loc_18002B4EF
0x18002b33f  xor     edi, edi; jumptable 000000018002B200 case 5
0x18002b341  mov     rax, [rbx+0B0h]
0x18002b348  mov     r15, [rax]
0x18002b34b  lea     rcx, [r15-20h]
0x18002b34f  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18002b355  test    al, al
0x18002b357  jz      short loc_18002B371
0x18002b359  lea     rcx, [rbx+0C0h]; this
0x18002b360  lea     rdx, [r15-20h]; struct std::exception_ptr *
0x18002b364  call    ??0exception_ptr@std@@QEAA@AEBV01@@Z; std::exception_ptr::exception_ptr(std::exception_ptr const &)
0x18002b369  mov     rcx, rax
0x18002b36c  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
0x18002b371  lea     r14, [rbx+98h]
0x18002b378  mov     al, [r15-10h]
0x18002b37c  mov     [r14], al
0x18002b37f  mov     [rbx+9Ch], dil
0x18002b386  mov     eax, [r15-0Ch]
0x18002b38a  mov     [rbx+9Ch], eax
0x18002b390  mov     rax, [rbx+90h]
0x18002b397  mov     [rsp+0E8h+var_A8], rax
0x18002b39c  test    rax, rax
0x18002b39f  jz      short loc_18002B3F1
0x18002b3a1  mov     rax, [rbx+90h]
0x18002b3a8  mov     [rsp+0E8h+var_A8], rax
0x18002b3ad  mov     rcx, [rsp+0E8h]; this
0x18002b3b5  cmp     [rax+8], di
0x18002b3b9  jz      short loc_18002B3CD
0x18002b3bb  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18002b3c2  mov     edx, 34h ; '4'; void *
0x18002b3c7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002b3cd  mov     rax, [rbx+90h]
0x18002b3d4  mov     [rsp+0E8h+var_A8], rax
0x18002b3d9  or      [rax+8], r12
0x18002b3dd  mov     rcx, [rbx+90h]
0x18002b3e4  mov     [rsp+0E8h+var_A8], rcx
0x18002b3e9  mov     rax, [rax]
0x18002b3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f1  mov     al, [r14]
0x18002b3f4  mov     [rsp+0E8h+var_78], al
0x18002b3f8  test    al, al
0x18002b3fa  jnz     short loc_18002B460
0x18002b3fc  mov     eax, [rbx+9Ch]
0x18002b402  mov     [rsp+0E8h+var_74], eax
0x18002b406  cmp     eax, 3E3h
0x18002b40b  jz      short loc_18002B431
0x18002b40d  mov     rcx, r14
0x18002b410  call    ?Error@?$BasicExpected@KK@util@@QEBAAEBKXZ; util::BasicExpected<ulong,ulong>::Error(void)
0x18002b415  mov     rcx, [rsp+0E8h]; this
0x18002b41d  mov     r9d, [rax]; char *
0x18002b420  lea     r8, aOnecoreVmDvSto_9; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002b427  mov     edx, 30h ; '0'; void *
0x18002b42c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002b431  mov     rcx, [rbx-10h]
0x18002b435  mov     [rbx-10h], rdi
0x18002b439  test    rcx, rcx
0x18002b43c  jz      short loc_18002B44D
0x18002b43e  mov     rax, [rcx]
0x18002b441  mov     edx, r12d
0x18002b444  mov     rax, [rax]
0x18002b447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b44c  nop
0x18002b44d  mov     rcx, [rbx+10h]; s
0x18002b451  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b455  jz      short loc_18002B45E
0x18002b457  call    cs:__imp_closesocket
0x18002b45d  nop
0x18002b45e  jmp     short loc_18002B4D8
0x18002b460  mov     r15, [rsi+0F0h]
0x18002b467  mov     rax, [rbx+10h]
0x18002b46b  mov     [rsp+0E8h+FileHandle], rax
0x18002b470  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x18002b478  mov     ecx, 28h ; '('; Size
0x18002b47d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b482  mov     r14, rax
0x18002b485  mov     [rbx+0D0h], rax
0x18002b48c  mov     r15b, [r15+20h]
0x18002b490  lea     rax, ??_7Socket@p9fs@@6B@; const p9fs::Socket::`vftable'
0x18002b497  mov     [r14], rax
0x18002b49a  mov     rdx, [rsp+0E8h+FileHandle]; FileHandle
0x18002b49f  mov     [r14+8], rdx
0x18002b4a3  lea     rcx, [r14+10h]; pv
0x18002b4a7  call    ??0CoroutineIoIssuer@p9fs@@QEAA@PEAX@Z; p9fs::CoroutineIoIssuer::CoroutineIoIssuer(void *)
0x18002b4ac  mov     [r14+20h], r15b
0x18002b4b0  mov     rcx, [rbx-10h]
0x18002b4b4  mov     [rbx-10h], r14
0x18002b4b8  test    rcx, rcx
0x18002b4bb  jz      short loc_18002B4CC
0x18002b4bd  mov     rax, [rcx]
0x18002b4c0  mov     edx, r12d
0x18002b4c3  mov     rax, [rax]
0x18002b4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4cb  nop
0x18002b4cc  jmp     short loc_18002B4D8
0x18002b4ce  mov     rsi, [rsp+0E8h+var_88]
0x18002b4d3  mov     rbx, [rsp+0E8h+var_90]
0x18002b4d8  xor     eax, eax
0x18002b4da  mov     [rbx+0A0h], al
0x18002b4e0  mov     [rsi], ax
0x18002b4e3  mov     rdx, rbx
0x18002b4e6  call    ??$await_suspend@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@FinalAwaiter@?$PromiseBase@VTaskPromise@p9fs@@@p9fs@@QEAAXU?$coroutine_handle@V?$Promise@V?$span@W4byte@gsl@@$0?0@gsl@@V?$Task@V?$span@W4byte@gsl@@$0?0@gsl@@@p9fs@@VTaskPromise@4@@p9fs@@@experimental@std@@@Z; p9fs::PromiseBase<p9fs::TaskPromise>::FinalAwaiter::await_suspend<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>(std::experimental::coroutine_handle<p9fs::Promise<gsl::span<gsl::byte,-1>,p9fs::Task<gsl::span<gsl::byte,-1>>,p9fs::TaskPromise>>)
0x18002b4eb  jmp     short loc_18002B527
0x18002b4ed  xor     edi, edi; jumptable 000000018002B200 cases 0,2
0x18002b4ef  mov     rcx, [rbx-10h]
0x18002b4f3  test    rcx, rcx
0x18002b4f6  jz      short loc_18002B506
0x18002b4f8  mov     rax, [rcx]
0x18002b4fb  mov     edx, r12d
0x18002b4fe  mov     rax, [rax]
0x18002b501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b506  lea     rcx, [rbx-20h]
0x18002b50a  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002b510  cmp     [rbx+0Ah], di
0x18002b514  jz      short loc_18002B527
0x18002b516  mov     edx, 140h; unsigned __int64
0x18002b51b  lea     rcx, [rbx-30h]; void *
0x18002b51f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b524  jmp     short loc_18002B527
0x18002b526  int     3; Trap to Debugger
0x18002b527  mov     rcx, [rsp+0E8h+var_48]
0x18002b52f  xor     rcx, rsp; StackCookie
0x18002b532  call    __security_check_cookie
0x18002b537  add     rsp, 0B8h
0x18002b53e  pop     r15
0x18002b540  pop     r14
0x18002b542  pop     r12
0x18002b544  pop     rdi
0x18002b545  pop     rsi
0x18002b546  pop     rbx
0x18002b547  retn
```
