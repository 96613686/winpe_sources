# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008190`
- end: `0x180008397`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008190`
- `0x1800086f0`
- `0x18000881c`
- `0x180008c88`
- `0x180009258`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000827c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000827c`

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
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
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
0x180008190  push    rbx
0x180008192  push    rbp
0x180008193  push    rsi
0x180008194  push    rdi
0x180008195  push    r14
0x180008197  sub     rsp, 20h
0x18000819b  mov     r14, r8
0x18000819e  mov     rsi, rdx
0x1800081a1  mov     rdi, rcx
0x1800081a4  mov     byte ptr [rdx], 0
0x1800081a7  xor     bpl, bpl
0x1800081aa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800081b1  test    rbx, rbx
0x1800081b4  jz      loc_180008250
0x1800081ba  call    cs:__imp_GetCurrentThreadId
0x1800081c0  mov     r9d, eax
0x1800081c3  mov     r8d, eax
0x1800081c6  shr     r8, 2
0x1800081ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800081d4  mul     r8
0x1800081d7  shr     rdx, 3
0x1800081db  lea     rcx, [rdx+rdx*4]
0x1800081df  add     rcx, rcx
0x1800081e2  sub     r8, rcx
0x1800081e5  mov     rbx, [rbx+r8*8]
0x1800081e9  jmp     short loc_1800081F4
0x1800081eb  cmp     [rbx], r9d
0x1800081ee  jz      short loc_18000826B
0x1800081f0  mov     rbx, [rbx+8]
0x1800081f4  test    rbx, rbx
0x1800081f7  jnz     short loc_1800081EB
0x1800081f9  test    rbx, rbx
0x1800081fc  jz      short loc_180008250
0x1800081fe  cmp     qword ptr [rbx], 0
0x180008202  jz      short loc_180008250
0x180008204  mov     [rsi], bpl
0x180008207  mov     r9, r14; unsigned __int64
0x18000820a  mov     r8, rsi; char *
0x18000820d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008210  mov     rcx, rdi; struct wil::FailureInfo *
0x180008213  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008218  test    al, al
0x18000821a  jz      short loc_180008220
0x18000821c  mov     [rdi+48h], rsi
0x180008220  mov     rbx, [rbx]
0x180008223  mov     al, [rbx+28h]
0x180008226  mov     byte ptr [rbx+28h], 1
0x18000822a  test    al, al
0x18000822c  jnz     short loc_180008247
0x18000822e  mov     rcx, [rbx+8]
0x180008232  mov     rax, [rcx]
0x180008235  mov     rdx, rdi
0x180008238  mov     rax, [rax]
0x18000823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008240  or      bpl, al
0x180008243  mov     byte ptr [rbx+28h], 0
0x180008247  mov     rbx, [rbx+10h]
0x18000824b  test    rbx, rbx
0x18000824e  jnz     short loc_180008223
0x180008250  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008257  test    rax, rax
0x18000825a  jz      short loc_18000827C
0x18000825c  test    bpl, bpl
0x18000825f  jnz     short loc_180008271
0x180008261  test    byte ptr [rdi+4], 2
0x180008265  jnz     short loc_180008271
0x180008267  xor     ecx, ecx
0x180008269  jmp     short loc_180008273
0x18000826b  add     rbx, 10h
0x18000826f  jmp     short loc_1800081F9
0x180008271  mov     cl, 1
0x180008273  mov     rdx, rdi
0x180008276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827b  nop
0x18000827c  call    cs:__imp_GetCurrentThreadId
0x180008282  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008288  cmp     ecx, eax
0x18000828a  jz      loc_18000838C
0x180008290  mov     ecx, 1
0x180008295  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000829d  inc     ecx; this
0x18000829f  cmp     ecx, 4
0x1800082a2  jge     loc_180008385
0x1800082a8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800082ae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800082b3  mov     rbx, rax
0x1800082b6  test    rax, rax
0x1800082b9  jz      loc_18000837B
0x1800082bf  mov     esi, [rax+10h]
0x1800082c2  mov     ebp, 50h ; 'P'
0x1800082c7  cmp     qword ptr [rax+18h], 0
0x1800082cc  jnz     short loc_180008303
0x1800082ce  test    esi, esi
0x1800082d0  jz      short loc_180008303
0x1800082d2  mov     edx, 190h; dwBytes
0x1800082d7  lea     ecx, [rbp-48h]; dwFlags
0x1800082da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800082df  mov     [rbx+18h], rax
0x1800082e3  test    rax, rax
0x1800082e6  jz      short loc_180008303
0x1800082e8  mov     dword ptr [rbx+20h], 5
0x1800082ef  lea     rcx, [rax+190h]
0x1800082f6  jmp     short loc_1800082FE
0x1800082f8  mov     [rax], bp
0x1800082fb  add     rax, rbp
0x1800082fe  cmp     rax, rcx
0x180008301  jnz     short loc_1800082F8
0x180008303  mov     r9, [rbx+18h]
0x180008307  test    r9, r9
0x18000830a  jz      short loc_18000837B
0x18000830c  test    esi, esi
0x18000830e  jz      short loc_180008341
0x180008310  mov     rcx, r9
0x180008313  movzx   eax, word ptr [rbx+20h]
0x180008317  lea     rdx, [rax+rax*4]
0x18000831b  shl     rdx, 4
0x18000831f  add     rdx, r9
0x180008322  cmp     r9, rdx
0x180008325  jz      short loc_180008341
0x180008327  mov     r8d, [rbx+10h]
0x18000832b  cmp     [rcx+4], r8d
0x18000832f  jbe     short loc_180008339
0x180008331  mov     eax, [rdi+8]
0x180008334  cmp     [rcx+8], eax
0x180008337  jz      short loc_18000837B
0x180008339  add     rcx, rbp
0x18000833c  cmp     rcx, rdx
0x18000833f  jnz     short loc_18000832B
0x180008341  movzx   eax, word ptr [rbx+22h]
0x180008345  inc     eax
0x180008347  movzx   ecx, word ptr [rbx+20h]
0x18000834b  xor     edx, edx
0x18000834d  div     ecx
0x18000834f  mov     [rbx+22h], dx
0x180008353  mov     rax, [rbx+8]
0x180008357  mov     r8d, 1
0x18000835d  lock xadd [rax], r8d
0x180008362  inc     r8d; unsigned int
0x180008365  movzx   eax, dx
0x180008368  lea     rcx, [rax+rax*4]
0x18000836c  shl     rcx, 4
0x180008370  add     rcx, r9; this
0x180008373  mov     rdx, rdi; struct wil::FailureInfo *
0x180008376  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000837b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008385  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000838c  add     rsp, 20h
0x180008390  pop     r14
0x180008392  pop     rdi
0x180008393  pop     rsi
0x180008394  pop     rbp
0x180008395  pop     rbx
0x180008396  retn
```
