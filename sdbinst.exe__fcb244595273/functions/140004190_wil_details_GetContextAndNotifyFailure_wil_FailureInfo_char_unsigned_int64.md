# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004190`
- end: `0x1400042d7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004190`
- `0x140004974`
- `0x140004a58`
- `0x140006cd4`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400041ba`
- `KERNEL32!GetCurrentThreadId` at `0x14000427c`
- `KERNEL32!GetCurrentThreadId` at `0x1400041ba`
- `KERNEL32!GetCurrentThreadId` at `0x14000427c`

## pseudocode

```c
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
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
0x140004190  push    rbx
0x140004192  push    rbp
0x140004193  push    rsi
0x140004194  push    rdi
0x140004195  push    r14
0x140004197  sub     rsp, 20h
0x14000419b  mov     r14, r8
0x14000419e  mov     rsi, rdx
0x1400041a1  mov     rdi, rcx
0x1400041a4  mov     byte ptr [rdx], 0
0x1400041a7  xor     bpl, bpl
0x1400041aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400041b1  test    rbx, rbx
0x1400041b4  jz      loc_140004250
0x1400041ba  call    cs:__imp_GetCurrentThreadId
0x1400041c0  mov     r9d, eax
0x1400041c3  mov     r8d, eax
0x1400041c6  shr     r8, 2
0x1400041ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400041d4  mul     r8
0x1400041d7  shr     rdx, 3
0x1400041db  lea     rcx, [rdx+rdx*4]
0x1400041df  add     rcx, rcx
0x1400041e2  sub     r8, rcx
0x1400041e5  mov     rbx, [rbx+r8*8]
0x1400041e9  jmp     short loc_1400041F4
0x1400041eb  cmp     [rbx], r9d
0x1400041ee  jz      short loc_14000426B
0x1400041f0  mov     rbx, [rbx+8]
0x1400041f4  test    rbx, rbx
0x1400041f7  jnz     short loc_1400041EB
0x1400041f9  test    rbx, rbx
0x1400041fc  jz      short loc_140004250
0x1400041fe  cmp     qword ptr [rbx], 0
0x140004202  jz      short loc_140004250
0x140004204  mov     [rsi], bpl
0x140004207  mov     r9, r14; unsigned __int64
0x14000420a  mov     r8, rsi; char *
0x14000420d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004210  mov     rcx, rdi; struct wil::FailureInfo *
0x140004213  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004218  test    al, al
0x14000421a  jz      short loc_140004220
0x14000421c  mov     [rdi+48h], rsi
0x140004220  mov     rbx, [rbx]
0x140004223  mov     al, [rbx+28h]
0x140004226  mov     byte ptr [rbx+28h], 1
0x14000422a  test    al, al
0x14000422c  jnz     short loc_140004247
0x14000422e  mov     rcx, [rbx+8]
0x140004232  mov     rax, [rcx]
0x140004235  mov     rdx, rdi
0x140004238  mov     rax, [rax]
0x14000423b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004240  or      bpl, al
0x140004243  mov     byte ptr [rbx+28h], 0
0x140004247  mov     rbx, [rbx+10h]
0x14000424b  test    rbx, rbx
0x14000424e  jnz     short loc_140004223
0x140004250  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004257  test    rax, rax
0x14000425a  jz      short loc_14000427C
0x14000425c  test    bpl, bpl
0x14000425f  jnz     short loc_140004271
0x140004261  test    byte ptr [rdi+4], 2
0x140004265  jnz     short loc_140004271
0x140004267  xor     ecx, ecx
0x140004269  jmp     short loc_140004273
0x14000426b  add     rbx, 10h
0x14000426f  jmp     short loc_1400041F9
0x140004271  mov     cl, 1
0x140004273  mov     rdx, rdi
0x140004276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000427b  nop
0x14000427c  call    cs:__imp_GetCurrentThreadId
0x140004282  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004288  cmp     ecx, eax
0x14000428a  jz      short loc_1400042CC
0x14000428c  mov     ecx, 1
0x140004291  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004299  inc     ecx; this
0x14000429b  cmp     ecx, 4
0x14000429e  jge     short loc_1400042C5
0x1400042a0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400042a6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400042ab  test    rax, rax
0x1400042ae  jz      short loc_1400042BB
0x1400042b0  mov     rdx, rdi; struct wil::FailureInfo *
0x1400042b3  mov     rcx, rax; this
0x1400042b6  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1400042bb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400042c5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400042cc  add     rsp, 20h
0x1400042d0  pop     r14
0x1400042d2  pop     rdi
0x1400042d3  pop     rsi
0x1400042d4  pop     rbp
0x1400042d5  pop     rbx
0x1400042d6  retn
```
