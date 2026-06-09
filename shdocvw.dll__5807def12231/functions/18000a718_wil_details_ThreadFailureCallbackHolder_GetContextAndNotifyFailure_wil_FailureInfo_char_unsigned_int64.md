# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000a718`
- end: `0x18000a813`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a820`

## callees

- `0x18000a718`
- `0x18000ac78`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a747`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  v5 = (struct wil::FailureInfo *)a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v6 && (*((_BYTE *)v5 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v5);
  }
}

```

## disassembly

```asm
0x18000a718  push    rbx
0x18000a71a  push    rbp
0x18000a71b  push    rsi
0x18000a71c  push    rdi
0x18000a71d  push    r14
0x18000a71f  push    r15
0x18000a721  sub     rsp, 28h
0x18000a725  mov     r15, r8
0x18000a728  mov     rsi, rdx
0x18000a72b  mov     rdi, rcx
0x18000a72e  mov     byte ptr [rdx], 0
0x18000a731  xor     r14b, r14b
0x18000a734  mov     bpl, 1
0x18000a737  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a73e  test    rbx, rbx
0x18000a741  jz      loc_18000A7E1
0x18000a747  call    cs:__imp_GetCurrentThreadId
0x18000a74d  mov     r9d, eax
0x18000a750  mov     r8d, eax
0x18000a753  shr     r8, 2
0x18000a757  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a761  mul     r8
0x18000a764  shr     rdx, 3
0x18000a768  lea     rcx, [rdx+rdx*4]
0x18000a76c  add     rcx, rcx
0x18000a76f  sub     r8, rcx
0x18000a772  mov     rbx, [rbx+r8*8]
0x18000a776  test    rbx, rbx
0x18000a779  jz      short loc_18000A78A
0x18000a77b  cmp     [rbx], r9d
0x18000a77e  jz      short loc_18000A786
0x18000a780  mov     rbx, [rbx+8]
0x18000a784  jmp     short loc_18000A776
0x18000a786  add     rbx, 10h
0x18000a78a  test    rbx, rbx
0x18000a78d  jz      short loc_18000A7E1
0x18000a78f  cmp     qword ptr [rbx], 0
0x18000a793  jz      short loc_18000A7E1
0x18000a795  mov     [rsi], r14b
0x18000a798  mov     r9, r15; unsigned __int64
0x18000a79b  mov     r8, rsi; char *
0x18000a79e  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000a7a1  mov     rcx, rdi; struct wil::FailureInfo *
0x18000a7a4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000a7a9  test    al, al
0x18000a7ab  jz      short loc_18000A7B1
0x18000a7ad  mov     [rdi+48h], rsi
0x18000a7b1  mov     rbx, [rbx]
0x18000a7b4  mov     al, [rbx+28h]
0x18000a7b7  mov     [rbx+28h], bpl
0x18000a7bb  test    al, al
0x18000a7bd  jnz     short loc_18000A7D8
0x18000a7bf  mov     rcx, [rbx+8]
0x18000a7c3  mov     rax, [rcx]
0x18000a7c6  mov     rdx, rdi
0x18000a7c9  mov     rax, [rax]
0x18000a7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d1  or      r14b, al
0x18000a7d4  mov     byte ptr [rbx+28h], 0
0x18000a7d8  mov     rbx, [rbx+10h]
0x18000a7dc  test    rbx, rbx
0x18000a7df  jnz     short loc_18000A7B4
0x18000a7e1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000a7e8  test    rax, rax
0x18000a7eb  jz      short loc_18000A806
0x18000a7ed  test    r14b, r14b
0x18000a7f0  jnz     short loc_18000A7FA
0x18000a7f2  test    byte ptr [rdi+4], 2
0x18000a7f6  jnz     short loc_18000A7FA
0x18000a7f8  xor     ebp, ebp
0x18000a7fa  mov     rdx, rdi
0x18000a7fd  mov     cl, bpl
0x18000a800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a805  nop
0x18000a806  add     rsp, 28h
0x18000a80a  pop     r15
0x18000a80c  pop     r14
0x18000a80e  pop     rdi
0x18000a80f  pop     rsi
0x18000a810  pop     rbp
0x18000a811  pop     rbx
0x18000a812  retn
```
