# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000c8a0`
- end: `0x18000caa6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000c8a0`
- `0x18000cf98`
- `0x18000d07c`
- `0x18000da6c`
- `0x18000ee88`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c8ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c98b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c8ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c98b`

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
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx
  volatile signed __int32 *v25; // rax

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
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000c8a0  push    rbx
0x18000c8a2  push    rbp
0x18000c8a3  push    rsi
0x18000c8a4  push    rdi
0x18000c8a5  push    r14
0x18000c8a7  sub     rsp, 20h
0x18000c8ab  mov     byte ptr [rdx], 0
0x18000c8ae  xor     bpl, bpl
0x18000c8b1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c8b8  mov     r14, r8
0x18000c8bb  mov     rsi, rdx
0x18000c8be  mov     rdi, rcx
0x18000c8c1  test    rbx, rbx
0x18000c8c4  jz      loc_18000C960
0x18000c8ca  call    cs:__imp_GetCurrentThreadId
0x18000c8d0  mov     r8d, eax
0x18000c8d3  mov     r9d, eax
0x18000c8d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c8e0  shr     r8, 2
0x18000c8e4  mul     r8
0x18000c8e7  shr     rdx, 3
0x18000c8eb  lea     rcx, [rdx+rdx*4]
0x18000c8ef  add     rcx, rcx
0x18000c8f2  sub     r8, rcx
0x18000c8f5  mov     rbx, [rbx+r8*8]
0x18000c8f9  jmp     short loc_18000C904
0x18000c8fb  cmp     [rbx], r9d
0x18000c8fe  jz      short loc_18000C97B
0x18000c900  mov     rbx, [rbx+8]
0x18000c904  test    rbx, rbx
0x18000c907  jnz     short loc_18000C8FB
0x18000c909  test    rbx, rbx
0x18000c90c  jz      short loc_18000C960
0x18000c90e  cmp     qword ptr [rbx], 0
0x18000c912  jz      short loc_18000C960
0x18000c914  mov     [rsi], bpl
0x18000c917  mov     r9, r14; unsigned __int64
0x18000c91a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000c91d  mov     r8, rsi; char *
0x18000c920  mov     rcx, rdi; struct wil::FailureInfo *
0x18000c923  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000c928  test    al, al
0x18000c92a  jz      short loc_18000C930
0x18000c92c  mov     [rdi+48h], rsi
0x18000c930  mov     rbx, [rbx]
0x18000c933  mov     al, [rbx+28h]
0x18000c936  mov     byte ptr [rbx+28h], 1
0x18000c93a  test    al, al
0x18000c93c  jnz     short loc_18000C957
0x18000c93e  mov     rcx, [rbx+8]
0x18000c942  mov     rdx, rdi
0x18000c945  mov     rax, [rcx]
0x18000c948  mov     rax, [rax]
0x18000c94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c950  or      bpl, al
0x18000c953  mov     byte ptr [rbx+28h], 0
0x18000c957  mov     rbx, [rbx+10h]
0x18000c95b  test    rbx, rbx
0x18000c95e  jnz     short loc_18000C933
0x18000c960  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000c967  test    rax, rax
0x18000c96a  jz      short loc_18000C98B
0x18000c96c  test    bpl, bpl
0x18000c96f  jnz     short loc_18000C981
0x18000c971  test    byte ptr [rdi+4], 2
0x18000c975  jnz     short loc_18000C981
0x18000c977  xor     ecx, ecx
0x18000c979  jmp     short loc_18000C983
0x18000c97b  add     rbx, 10h
0x18000c97f  jmp     short loc_18000C909
0x18000c981  mov     cl, 1
0x18000c983  mov     rdx, rdi
0x18000c986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c98b  call    cs:__imp_GetCurrentThreadId
0x18000c991  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000c997  cmp     ecx, eax
0x18000c999  jz      loc_18000CA9B
0x18000c99f  mov     ecx, 1
0x18000c9a4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000c9ac  inc     ecx; this
0x18000c9ae  cmp     ecx, 4
0x18000c9b1  jge     loc_18000CA94
0x18000c9b7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000c9bd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000c9c2  mov     rbx, rax
0x18000c9c5  test    rax, rax
0x18000c9c8  jz      loc_18000CA8A
0x18000c9ce  cmp     qword ptr [rax+18h], 0
0x18000c9d3  mov     ebp, 50h ; 'P'
0x18000c9d8  mov     esi, [rax+10h]
0x18000c9db  jnz     short loc_18000CA12
0x18000c9dd  test    esi, esi
0x18000c9df  jz      short loc_18000CA12
0x18000c9e1  mov     edx, 190h; dwBytes
0x18000c9e6  lea     ecx, [rbp-48h]; dwFlags
0x18000c9e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c9ee  mov     [rbx+18h], rax
0x18000c9f2  test    rax, rax
0x18000c9f5  jz      short loc_18000CA12
0x18000c9f7  mov     dword ptr [rbx+20h], 5
0x18000c9fe  lea     rcx, [rax+190h]
0x18000ca05  jmp     short loc_18000CA0D
0x18000ca07  mov     [rax], bp
0x18000ca0a  add     rax, rbp
0x18000ca0d  cmp     rax, rcx
0x18000ca10  jnz     short loc_18000CA07
0x18000ca12  mov     r9, [rbx+18h]
0x18000ca16  test    r9, r9
0x18000ca19  jz      short loc_18000CA8A
0x18000ca1b  test    esi, esi
0x18000ca1d  jz      short loc_18000CA50
0x18000ca1f  movzx   eax, word ptr [rbx+20h]
0x18000ca23  mov     rcx, r9
0x18000ca26  lea     rdx, [rax+rax*4]
0x18000ca2a  shl     rdx, 4
0x18000ca2e  add     rdx, r9
0x18000ca31  cmp     r9, rdx
0x18000ca34  jz      short loc_18000CA50
0x18000ca36  mov     r8d, [rbx+10h]
0x18000ca3a  cmp     [rcx+4], r8d
0x18000ca3e  jbe     short loc_18000CA48
0x18000ca40  mov     eax, [rdi+8]
0x18000ca43  cmp     [rcx+8], eax
0x18000ca46  jz      short loc_18000CA8A
0x18000ca48  add     rcx, rbp
0x18000ca4b  cmp     rcx, rdx
0x18000ca4e  jnz     short loc_18000CA3A
0x18000ca50  movzx   eax, word ptr [rbx+22h]
0x18000ca54  xor     edx, edx
0x18000ca56  movzx   ecx, word ptr [rbx+20h]
0x18000ca5a  inc     eax
0x18000ca5c  div     ecx
0x18000ca5e  mov     rax, [rbx+8]
0x18000ca62  mov     r8d, 1
0x18000ca68  mov     [rbx+22h], dx
0x18000ca6c  lock xadd [rax], r8d
0x18000ca71  movzx   eax, dx
0x18000ca74  inc     r8d; unsigned int
0x18000ca77  mov     rdx, rdi; struct wil::FailureInfo *
0x18000ca7a  lea     rcx, [rax+rax*4]
0x18000ca7e  shl     rcx, 4
0x18000ca82  add     rcx, r9; this
0x18000ca85  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000ca8a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000ca94  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000ca9b  add     rsp, 20h
0x18000ca9f  pop     r14
0x18000caa1  pop     rdi
0x18000caa2  pop     rsi
0x18000caa3  pop     rbp
0x18000caa4  pop     rbx
0x18000caa5  retn
```
