# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400117e0`
- end: `0x1400119e7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140008ea8`
- `0x1400117e0`
- `0x140011bb8`
- `0x140011c9c`
- `0x140013534`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001180a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400118cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001180a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400118cc`

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
0x1400117e0  push    rbx
0x1400117e2  push    rbp
0x1400117e3  push    rsi
0x1400117e4  push    rdi
0x1400117e5  push    r14
0x1400117e7  sub     rsp, 20h
0x1400117eb  mov     r14, r8
0x1400117ee  mov     rsi, rdx
0x1400117f1  mov     rdi, rcx
0x1400117f4  mov     byte ptr [rdx], 0
0x1400117f7  xor     bpl, bpl
0x1400117fa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140011801  test    rbx, rbx
0x140011804  jz      loc_1400118A0
0x14001180a  call    cs:__imp_GetCurrentThreadId
0x140011810  mov     r9d, eax
0x140011813  mov     r8d, eax
0x140011816  shr     r8, 2
0x14001181a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140011824  mul     r8
0x140011827  shr     rdx, 3
0x14001182b  lea     rcx, [rdx+rdx*4]
0x14001182f  add     rcx, rcx
0x140011832  sub     r8, rcx
0x140011835  mov     rbx, [rbx+r8*8]
0x140011839  jmp     short loc_140011844
0x14001183b  cmp     [rbx], r9d
0x14001183e  jz      short loc_1400118BB
0x140011840  mov     rbx, [rbx+8]
0x140011844  test    rbx, rbx
0x140011847  jnz     short loc_14001183B
0x140011849  test    rbx, rbx
0x14001184c  jz      short loc_1400118A0
0x14001184e  cmp     qword ptr [rbx], 0
0x140011852  jz      short loc_1400118A0
0x140011854  mov     [rsi], bpl
0x140011857  mov     r9, r14; unsigned __int64
0x14001185a  mov     r8, rsi; char *
0x14001185d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140011860  mov     rcx, rdi; struct wil::FailureInfo *
0x140011863  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140011868  test    al, al
0x14001186a  jz      short loc_140011870
0x14001186c  mov     [rdi+48h], rsi
0x140011870  mov     rbx, [rbx]
0x140011873  mov     al, [rbx+28h]
0x140011876  mov     byte ptr [rbx+28h], 1
0x14001187a  test    al, al
0x14001187c  jnz     short loc_140011897
0x14001187e  mov     rcx, [rbx+8]
0x140011882  mov     rax, [rcx]
0x140011885  mov     rdx, rdi
0x140011888  mov     rax, [rax]
0x14001188b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011890  or      bpl, al
0x140011893  mov     byte ptr [rbx+28h], 0
0x140011897  mov     rbx, [rbx+10h]
0x14001189b  test    rbx, rbx
0x14001189e  jnz     short loc_140011873
0x1400118a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400118a7  test    rax, rax
0x1400118aa  jz      short loc_1400118CC
0x1400118ac  test    bpl, bpl
0x1400118af  jnz     short loc_1400118C1
0x1400118b1  test    byte ptr [rdi+4], 2
0x1400118b5  jnz     short loc_1400118C1
0x1400118b7  xor     ecx, ecx
0x1400118b9  jmp     short loc_1400118C3
0x1400118bb  add     rbx, 10h
0x1400118bf  jmp     short loc_140011849
0x1400118c1  mov     cl, 1
0x1400118c3  mov     rdx, rdi
0x1400118c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400118cb  nop
0x1400118cc  call    cs:__imp_GetCurrentThreadId
0x1400118d2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400118d8  cmp     ecx, eax
0x1400118da  jz      loc_1400119DC
0x1400118e0  mov     ecx, 1
0x1400118e5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400118ed  inc     ecx; this
0x1400118ef  cmp     ecx, 4
0x1400118f2  jge     loc_1400119D5
0x1400118f8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400118fe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140011903  mov     rbx, rax
0x140011906  test    rax, rax
0x140011909  jz      loc_1400119CB
0x14001190f  mov     esi, [rax+10h]
0x140011912  mov     ebp, 50h ; 'P'
0x140011917  cmp     qword ptr [rax+18h], 0
0x14001191c  jnz     short loc_140011953
0x14001191e  test    esi, esi
0x140011920  jz      short loc_140011953
0x140011922  mov     edx, 190h; dwBytes
0x140011927  lea     ecx, [rbp-48h]; dwFlags
0x14001192a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001192f  mov     [rbx+18h], rax
0x140011933  test    rax, rax
0x140011936  jz      short loc_140011953
0x140011938  mov     dword ptr [rbx+20h], 5
0x14001193f  lea     rcx, [rax+190h]
0x140011946  jmp     short loc_14001194E
0x140011948  mov     [rax], bp
0x14001194b  add     rax, rbp
0x14001194e  cmp     rax, rcx
0x140011951  jnz     short loc_140011948
0x140011953  mov     r9, [rbx+18h]
0x140011957  test    r9, r9
0x14001195a  jz      short loc_1400119CB
0x14001195c  test    esi, esi
0x14001195e  jz      short loc_140011991
0x140011960  mov     rcx, r9
0x140011963  movzx   eax, word ptr [rbx+20h]
0x140011967  lea     rdx, [rax+rax*4]
0x14001196b  shl     rdx, 4
0x14001196f  add     rdx, r9
0x140011972  cmp     r9, rdx
0x140011975  jz      short loc_140011991
0x140011977  mov     r8d, [rbx+10h]
0x14001197b  cmp     [rcx+4], r8d
0x14001197f  jbe     short loc_140011989
0x140011981  mov     eax, [rdi+8]
0x140011984  cmp     [rcx+8], eax
0x140011987  jz      short loc_1400119CB
0x140011989  add     rcx, rbp
0x14001198c  cmp     rcx, rdx
0x14001198f  jnz     short loc_14001197B
0x140011991  movzx   eax, word ptr [rbx+22h]
0x140011995  inc     eax
0x140011997  movzx   ecx, word ptr [rbx+20h]
0x14001199b  xor     edx, edx
0x14001199d  div     ecx
0x14001199f  mov     [rbx+22h], dx
0x1400119a3  mov     rax, [rbx+8]
0x1400119a7  mov     r8d, 1
0x1400119ad  lock xadd [rax], r8d
0x1400119b2  inc     r8d; unsigned int
0x1400119b5  movzx   eax, dx
0x1400119b8  lea     rcx, [rax+rax*4]
0x1400119bc  shl     rcx, 4
0x1400119c0  add     rcx, r9; this
0x1400119c3  mov     rdx, rdi; struct wil::FailureInfo *
0x1400119c6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400119cb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400119d5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400119dc  add     rsp, 20h
0x1400119e0  pop     r14
0x1400119e2  pop     rdi
0x1400119e3  pop     rsi
0x1400119e4  pop     rbp
0x1400119e5  pop     rbx
0x1400119e6  retn
```
