# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b610`
- end: `0x18000b76e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `350`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000b610`
- `0x18000bf80`
- `0x18000c080`
- `0x18000fa7c`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000b648`
- `KERNEL32!GetCurrentThreadId` at `0x18000b6fc`
- `KERNEL32!GetCurrentThreadId` at `0x18000b648`
- `KERNEL32!GetCurrentThreadId` at `0x18000b6fc`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r10
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        v3 |= v11;
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000b610  mov     rax, rsp
0x18000b613  mov     [rax+8], rbx
0x18000b617  mov     [rax+10h], rbp
0x18000b61b  mov     [rax+18h], rsi
0x18000b61f  mov     [rax+20h], rdi
0x18000b623  push    r14
0x18000b625  sub     rsp, 20h
0x18000b629  mov     byte ptr [rdx], 0
0x18000b62c  xor     bpl, bpl
0x18000b62f  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b636  mov     r14, r8
0x18000b639  mov     rsi, rdx
0x18000b63c  mov     rdi, rcx
0x18000b63f  test    rbx, rbx
0x18000b642  jz      loc_18000B6D1
0x18000b648  call    cs:__imp_GetCurrentThreadId
0x18000b64f  nop     dword ptr [rax+rax+00h]
0x18000b654  mov     r9d, eax
0x18000b657  mov     r10d, eax
0x18000b65a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b664  mul     r10
0x18000b667  shr     rdx, 3
0x18000b66b  lea     rcx, [rdx+rdx*4]
0x18000b66f  add     rcx, rcx
0x18000b672  sub     r9, rcx
0x18000b675  mov     rbx, [rbx+r9*8]
0x18000b679  jmp     short loc_18000B684
0x18000b67b  cmp     [rbx], r10d
0x18000b67e  jz      short loc_18000B6EC
0x18000b680  mov     rbx, [rbx+8]
0x18000b684  test    rbx, rbx
0x18000b687  jnz     short loc_18000B67B
0x18000b689  test    rbx, rbx
0x18000b68c  jz      short loc_18000B6D1
0x18000b68e  cmp     qword ptr [rbx], 0
0x18000b692  jz      short loc_18000B6D1
0x18000b694  mov     [rsi], bpl
0x18000b697  mov     r9, r14; unsigned __int64
0x18000b69a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b69d  mov     r8, rsi; char *
0x18000b6a0  mov     rcx, rdi; struct wil::FailureInfo *
0x18000b6a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b6a8  test    al, al
0x18000b6aa  jz      short loc_18000B6B0
0x18000b6ac  mov     [rdi+48h], rsi
0x18000b6b0  mov     rbx, [rbx]
0x18000b6b3  mov     rcx, [rbx+8]
0x18000b6b7  mov     rdx, rdi
0x18000b6ba  mov     rax, [rcx]
0x18000b6bd  mov     rax, [rax]
0x18000b6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c5  mov     rbx, [rbx+10h]
0x18000b6c9  or      bpl, al
0x18000b6cc  test    rbx, rbx
0x18000b6cf  jnz     short loc_18000B6B3
0x18000b6d1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b6d8  test    rax, rax
0x18000b6db  jz      short loc_18000B6FC
0x18000b6dd  test    bpl, bpl
0x18000b6e0  jnz     short loc_18000B6F2
0x18000b6e2  test    byte ptr [rdi+4], 2
0x18000b6e6  jnz     short loc_18000B6F2
0x18000b6e8  xor     ecx, ecx
0x18000b6ea  jmp     short loc_18000B6F4
0x18000b6ec  add     rbx, 10h
0x18000b6f0  jmp     short loc_18000B689
0x18000b6f2  mov     cl, 1
0x18000b6f4  mov     rdx, rdi
0x18000b6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6fc  call    cs:__imp_GetCurrentThreadId
0x18000b703  nop     dword ptr [rax+rax+00h]
0x18000b708  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b70e  cmp     ecx, eax
0x18000b710  jz      short loc_18000B752
0x18000b712  mov     ecx, 1
0x18000b717  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b71f  inc     ecx; this
0x18000b721  cmp     ecx, 4
0x18000b724  jge     short loc_18000B74B
0x18000b726  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b72c  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b731  test    rax, rax
0x18000b734  jz      short loc_18000B741
0x18000b736  mov     rdx, rdi; struct wil::FailureInfo *
0x18000b739  mov     rcx, rax; this
0x18000b73c  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000b741  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b74b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b752  mov     rbx, [rsp+28h+arg_0]
0x18000b757  mov     rbp, [rsp+28h+arg_8]
0x18000b75c  mov     rsi, [rsp+28h+arg_10]
0x18000b761  mov     rdi, [rsp+28h+arg_18]
0x18000b766  add     rsp, 20h
0x18000b76a  pop     r14
0x18000b76c  retn
```
