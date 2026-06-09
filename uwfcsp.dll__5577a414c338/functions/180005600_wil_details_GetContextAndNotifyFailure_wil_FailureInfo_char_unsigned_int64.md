# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005600`
- end: `0x180005746`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `326`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005600`
- `0x180005cdc`
- `0x180005dc0`
- `0x180006980`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000562a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000562a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056eb`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r9
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
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
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
0x180005600  push    rbx
0x180005602  push    rbp
0x180005603  push    rsi
0x180005604  push    rdi
0x180005605  push    r14
0x180005607  sub     rsp, 20h
0x18000560b  mov     byte ptr [rdx], 0
0x18000560e  xor     bpl, bpl
0x180005611  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005618  mov     r14, r8
0x18000561b  mov     rsi, rdx
0x18000561e  mov     rdi, rcx
0x180005621  test    rbx, rbx
0x180005624  jz      loc_1800056C0
0x18000562a  call    cs:__imp_GetCurrentThreadId
0x180005630  mov     r8d, eax
0x180005633  mov     r9d, eax
0x180005636  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005640  shr     r8, 2
0x180005644  mul     r8
0x180005647  shr     rdx, 3
0x18000564b  lea     rcx, [rdx+rdx*4]
0x18000564f  add     rcx, rcx
0x180005652  sub     r8, rcx
0x180005655  mov     rbx, [rbx+r8*8]
0x180005659  jmp     short loc_180005664
0x18000565b  cmp     [rbx], r9d
0x18000565e  jz      short loc_1800056DB
0x180005660  mov     rbx, [rbx+8]
0x180005664  test    rbx, rbx
0x180005667  jnz     short loc_18000565B
0x180005669  test    rbx, rbx
0x18000566c  jz      short loc_1800056C0
0x18000566e  cmp     qword ptr [rbx], 0
0x180005672  jz      short loc_1800056C0
0x180005674  mov     [rsi], bpl
0x180005677  mov     r9, r14; unsigned __int64
0x18000567a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000567d  mov     r8, rsi; char *
0x180005680  mov     rcx, rdi; struct wil::FailureInfo *
0x180005683  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005688  test    al, al
0x18000568a  jz      short loc_180005690
0x18000568c  mov     [rdi+48h], rsi
0x180005690  mov     rbx, [rbx]
0x180005693  mov     al, [rbx+28h]
0x180005696  mov     byte ptr [rbx+28h], 1
0x18000569a  test    al, al
0x18000569c  jnz     short loc_1800056B7
0x18000569e  mov     rcx, [rbx+8]
0x1800056a2  mov     rdx, rdi
0x1800056a5  mov     rax, [rcx]
0x1800056a8  mov     rax, [rax]
0x1800056ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b0  or      bpl, al
0x1800056b3  mov     byte ptr [rbx+28h], 0
0x1800056b7  mov     rbx, [rbx+10h]
0x1800056bb  test    rbx, rbx
0x1800056be  jnz     short loc_180005693
0x1800056c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800056c7  test    rax, rax
0x1800056ca  jz      short loc_1800056EB
0x1800056cc  test    bpl, bpl
0x1800056cf  jnz     short loc_1800056E1
0x1800056d1  test    byte ptr [rdi+4], 2
0x1800056d5  jnz     short loc_1800056E1
0x1800056d7  xor     ecx, ecx
0x1800056d9  jmp     short loc_1800056E3
0x1800056db  add     rbx, 10h
0x1800056df  jmp     short loc_180005669
0x1800056e1  mov     cl, 1
0x1800056e3  mov     rdx, rdi
0x1800056e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056eb  call    cs:__imp_GetCurrentThreadId
0x1800056f1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800056f7  cmp     ecx, eax
0x1800056f9  jz      short loc_18000573B
0x1800056fb  mov     ecx, 1
0x180005700  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005708  inc     ecx; this
0x18000570a  cmp     ecx, 4
0x18000570d  jge     short loc_180005734
0x18000570f  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005715  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000571a  test    rax, rax
0x18000571d  jz      short loc_18000572A
0x18000571f  mov     rdx, rdi; struct wil::FailureInfo *
0x180005722  mov     rcx, rax; this
0x180005725  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000572a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005734  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000573b  add     rsp, 20h
0x18000573f  pop     r14
0x180005741  pop     rdi
0x180005742  pop     rsi
0x180005743  pop     rbp
0x180005744  pop     rbx
0x180005745  retn
```
