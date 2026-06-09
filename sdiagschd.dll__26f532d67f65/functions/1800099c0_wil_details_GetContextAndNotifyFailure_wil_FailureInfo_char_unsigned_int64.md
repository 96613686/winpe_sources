# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800099c0`
- end: `0x180009b2e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `366`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800099c0`
- `0x18000a058`
- `0x18000a158`
- `0x18000bd00`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800099f8`
- `KERNEL32!GetCurrentThreadId` at `0x180009abc`
- `KERNEL32!GetCurrentThreadId` at `0x1800099f8`
- `KERNEL32!GetCurrentThreadId` at `0x180009abc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800099c0  mov     rax, rsp
0x1800099c3  mov     [rax+8], rbx
0x1800099c7  mov     [rax+10h], rbp
0x1800099cb  mov     [rax+18h], rsi
0x1800099cf  mov     [rax+20h], rdi
0x1800099d3  push    r14
0x1800099d5  sub     rsp, 20h
0x1800099d9  mov     r14, r8
0x1800099dc  mov     rsi, rdx
0x1800099df  mov     rdi, rcx
0x1800099e2  mov     byte ptr [rdx], 0
0x1800099e5  xor     bpl, bpl
0x1800099e8  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800099ef  test    rbx, rbx
0x1800099f2  jz      loc_180009A90
0x1800099f8  call    cs:__imp_GetCurrentThreadId
0x1800099ff  nop     dword ptr [rax+rax+00h]
0x180009a04  mov     r9d, eax
0x180009a07  mov     r8d, eax
0x180009a0a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009a14  mul     r9
0x180009a17  shr     rdx, 3
0x180009a1b  lea     rcx, [rdx+rdx*4]
0x180009a1f  add     rcx, rcx
0x180009a22  sub     r8, rcx
0x180009a25  mov     rbx, [rbx+r8*8]
0x180009a29  jmp     short loc_180009A34
0x180009a2b  cmp     [rbx], r9d
0x180009a2e  jz      short loc_180009AAB
0x180009a30  mov     rbx, [rbx+8]
0x180009a34  test    rbx, rbx
0x180009a37  jnz     short loc_180009A2B
0x180009a39  test    rbx, rbx
0x180009a3c  jz      short loc_180009A90
0x180009a3e  cmp     qword ptr [rbx], 0
0x180009a42  jz      short loc_180009A90
0x180009a44  mov     [rsi], bpl
0x180009a47  mov     r9, r14; unsigned __int64
0x180009a4a  mov     r8, rsi; char *
0x180009a4d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180009a50  mov     rcx, rdi; struct wil::FailureInfo *
0x180009a53  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009a58  test    al, al
0x180009a5a  jz      short loc_180009A60
0x180009a5c  mov     [rdi+48h], rsi
0x180009a60  mov     rbx, [rbx]
0x180009a63  mov     al, [rbx+28h]
0x180009a66  mov     byte ptr [rbx+28h], 1
0x180009a6a  test    al, al
0x180009a6c  jnz     short loc_180009A87
0x180009a6e  mov     rcx, [rbx+8]
0x180009a72  mov     rax, [rcx]
0x180009a75  mov     rdx, rdi
0x180009a78  mov     rax, [rax]
0x180009a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a80  or      bpl, al
0x180009a83  mov     byte ptr [rbx+28h], 0
0x180009a87  mov     rbx, [rbx+10h]
0x180009a8b  test    rbx, rbx
0x180009a8e  jnz     short loc_180009A63
0x180009a90  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009a97  test    rax, rax
0x180009a9a  jz      short loc_180009ABC
0x180009a9c  test    bpl, bpl
0x180009a9f  jnz     short loc_180009AB1
0x180009aa1  test    byte ptr [rdi+4], 2
0x180009aa5  jnz     short loc_180009AB1
0x180009aa7  xor     ecx, ecx
0x180009aa9  jmp     short loc_180009AB3
0x180009aab  add     rbx, 10h
0x180009aaf  jmp     short loc_180009A39
0x180009ab1  mov     cl, 1
0x180009ab3  mov     rdx, rdi
0x180009ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009abb  nop
0x180009abc  call    cs:__imp_GetCurrentThreadId
0x180009ac3  nop     dword ptr [rax+rax+00h]
0x180009ac8  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009ace  cmp     ecx, eax
0x180009ad0  jz      short loc_180009B12
0x180009ad2  mov     ecx, 1
0x180009ad7  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009adf  inc     ecx; this
0x180009ae1  cmp     ecx, 4
0x180009ae4  jge     short loc_180009B0B
0x180009ae6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009aec  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180009af1  test    rax, rax
0x180009af4  jz      short loc_180009B01
0x180009af6  mov     rdx, rdi; struct wil::FailureInfo *
0x180009af9  mov     rcx, rax; this
0x180009afc  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180009b01  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009b0b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009b12  mov     rbx, [rsp+28h+arg_0]
0x180009b17  mov     rbp, [rsp+28h+arg_8]
0x180009b1c  mov     rsi, [rsp+28h+arg_10]
0x180009b21  mov     rdi, [rsp+28h+arg_18]
0x180009b26  add     rsp, 20h
0x180009b2a  pop     r14
0x180009b2c  retn
```
