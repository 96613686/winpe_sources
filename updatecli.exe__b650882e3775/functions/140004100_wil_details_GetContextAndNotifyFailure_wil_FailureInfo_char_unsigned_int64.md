# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004100`
- end: `0x140004307`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004100`
- `0x1400047fc`
- `0x1400048e0`
- `0x140005158`
- `0x1400054c0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000412a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400041ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000412a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400041ec`

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
0x140004100  push    rbx
0x140004102  push    rbp
0x140004103  push    rsi
0x140004104  push    rdi
0x140004105  push    r14
0x140004107  sub     rsp, 20h
0x14000410b  mov     r14, r8
0x14000410e  mov     rsi, rdx
0x140004111  mov     rdi, rcx
0x140004114  mov     byte ptr [rdx], 0
0x140004117  xor     bpl, bpl
0x14000411a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004121  test    rbx, rbx
0x140004124  jz      loc_1400041C0
0x14000412a  call    cs:__imp_GetCurrentThreadId
0x140004130  mov     r9d, eax
0x140004133  mov     r8d, eax
0x140004136  shr     r8, 2
0x14000413a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004144  mul     r8
0x140004147  shr     rdx, 3
0x14000414b  lea     rcx, [rdx+rdx*4]
0x14000414f  add     rcx, rcx
0x140004152  sub     r8, rcx
0x140004155  mov     rbx, [rbx+r8*8]
0x140004159  jmp     short loc_140004164
0x14000415b  cmp     [rbx], r9d
0x14000415e  jz      short loc_1400041DB
0x140004160  mov     rbx, [rbx+8]
0x140004164  test    rbx, rbx
0x140004167  jnz     short loc_14000415B
0x140004169  test    rbx, rbx
0x14000416c  jz      short loc_1400041C0
0x14000416e  cmp     qword ptr [rbx], 0
0x140004172  jz      short loc_1400041C0
0x140004174  mov     [rsi], bpl
0x140004177  mov     r9, r14; unsigned __int64
0x14000417a  mov     r8, rsi; char *
0x14000417d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004180  mov     rcx, rdi; struct wil::FailureInfo *
0x140004183  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004188  test    al, al
0x14000418a  jz      short loc_140004190
0x14000418c  mov     [rdi+48h], rsi
0x140004190  mov     rbx, [rbx]
0x140004193  mov     al, [rbx+28h]
0x140004196  mov     byte ptr [rbx+28h], 1
0x14000419a  test    al, al
0x14000419c  jnz     short loc_1400041B7
0x14000419e  mov     rcx, [rbx+8]
0x1400041a2  mov     rax, [rcx]
0x1400041a5  mov     rdx, rdi
0x1400041a8  mov     rax, [rax]
0x1400041ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041b0  or      bpl, al
0x1400041b3  mov     byte ptr [rbx+28h], 0
0x1400041b7  mov     rbx, [rbx+10h]
0x1400041bb  test    rbx, rbx
0x1400041be  jnz     short loc_140004193
0x1400041c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400041c7  test    rax, rax
0x1400041ca  jz      short loc_1400041EC
0x1400041cc  test    bpl, bpl
0x1400041cf  jnz     short loc_1400041E1
0x1400041d1  test    byte ptr [rdi+4], 2
0x1400041d5  jnz     short loc_1400041E1
0x1400041d7  xor     ecx, ecx
0x1400041d9  jmp     short loc_1400041E3
0x1400041db  add     rbx, 10h
0x1400041df  jmp     short loc_140004169
0x1400041e1  mov     cl, 1
0x1400041e3  mov     rdx, rdi
0x1400041e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041eb  nop
0x1400041ec  call    cs:__imp_GetCurrentThreadId
0x1400041f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400041f8  cmp     ecx, eax
0x1400041fa  jz      loc_1400042FC
0x140004200  mov     ecx, 1
0x140004205  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000420d  inc     ecx; this
0x14000420f  cmp     ecx, 4
0x140004212  jge     loc_1400042F5
0x140004218  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000421e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004223  mov     rbx, rax
0x140004226  test    rax, rax
0x140004229  jz      loc_1400042EB
0x14000422f  mov     esi, [rax+10h]
0x140004232  mov     ebp, 50h ; 'P'
0x140004237  cmp     qword ptr [rax+18h], 0
0x14000423c  jnz     short loc_140004273
0x14000423e  test    esi, esi
0x140004240  jz      short loc_140004273
0x140004242  mov     edx, 190h; dwBytes
0x140004247  lea     ecx, [rbp-48h]; dwFlags
0x14000424a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000424f  mov     [rbx+18h], rax
0x140004253  test    rax, rax
0x140004256  jz      short loc_140004273
0x140004258  mov     dword ptr [rbx+20h], 5
0x14000425f  lea     rcx, [rax+190h]
0x140004266  jmp     short loc_14000426E
0x140004268  mov     [rax], bp
0x14000426b  add     rax, rbp
0x14000426e  cmp     rax, rcx
0x140004271  jnz     short loc_140004268
0x140004273  mov     r9, [rbx+18h]
0x140004277  test    r9, r9
0x14000427a  jz      short loc_1400042EB
0x14000427c  test    esi, esi
0x14000427e  jz      short loc_1400042B1
0x140004280  mov     rcx, r9
0x140004283  movzx   eax, word ptr [rbx+20h]
0x140004287  lea     rdx, [rax+rax*4]
0x14000428b  shl     rdx, 4
0x14000428f  add     rdx, r9
0x140004292  cmp     r9, rdx
0x140004295  jz      short loc_1400042B1
0x140004297  mov     r8d, [rbx+10h]
0x14000429b  cmp     [rcx+4], r8d
0x14000429f  jbe     short loc_1400042A9
0x1400042a1  mov     eax, [rdi+8]
0x1400042a4  cmp     [rcx+8], eax
0x1400042a7  jz      short loc_1400042EB
0x1400042a9  add     rcx, rbp
0x1400042ac  cmp     rcx, rdx
0x1400042af  jnz     short loc_14000429B
0x1400042b1  movzx   eax, word ptr [rbx+22h]
0x1400042b5  inc     eax
0x1400042b7  movzx   ecx, word ptr [rbx+20h]
0x1400042bb  xor     edx, edx
0x1400042bd  div     ecx
0x1400042bf  mov     [rbx+22h], dx
0x1400042c3  mov     rax, [rbx+8]
0x1400042c7  mov     r8d, 1
0x1400042cd  lock xadd [rax], r8d
0x1400042d2  inc     r8d; unsigned int
0x1400042d5  movzx   eax, dx
0x1400042d8  lea     rcx, [rax+rax*4]
0x1400042dc  shl     rcx, 4
0x1400042e0  add     rcx, r9; this
0x1400042e3  mov     rdx, rdi; struct wil::FailureInfo *
0x1400042e6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400042eb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400042f5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400042fc  add     rsp, 20h
0x140004300  pop     r14
0x140004302  pop     rdi
0x140004303  pop     rsi
0x140004304  pop     rbp
0x140004305  pop     rbx
0x140004306  retn
```
