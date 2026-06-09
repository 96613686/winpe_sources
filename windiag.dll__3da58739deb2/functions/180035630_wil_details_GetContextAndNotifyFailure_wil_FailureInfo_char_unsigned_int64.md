# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180035630`
- end: `0x180035837`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180035630`
- `0x180035d2c`
- `0x180035e10`
- `0x180036888`
- `0x180037f94`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003565a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003571c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003565a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003571c`

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
0x180035630  push    rbx
0x180035632  push    rbp
0x180035633  push    rsi
0x180035634  push    rdi
0x180035635  push    r14
0x180035637  sub     rsp, 20h
0x18003563b  mov     r14, r8
0x18003563e  mov     rsi, rdx
0x180035641  mov     rdi, rcx
0x180035644  mov     byte ptr [rdx], 0
0x180035647  xor     bpl, bpl
0x18003564a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180035651  test    rbx, rbx
0x180035654  jz      loc_1800356F0
0x18003565a  call    cs:__imp_GetCurrentThreadId
0x180035660  mov     r9d, eax
0x180035663  mov     r8d, eax
0x180035666  shr     r8, 2
0x18003566a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180035674  mul     r8
0x180035677  shr     rdx, 3
0x18003567b  lea     rcx, [rdx+rdx*4]
0x18003567f  add     rcx, rcx
0x180035682  sub     r8, rcx
0x180035685  mov     rbx, [rbx+r8*8]
0x180035689  jmp     short loc_180035694
0x18003568b  cmp     [rbx], r9d
0x18003568e  jz      short loc_18003570B
0x180035690  mov     rbx, [rbx+8]
0x180035694  test    rbx, rbx
0x180035697  jnz     short loc_18003568B
0x180035699  test    rbx, rbx
0x18003569c  jz      short loc_1800356F0
0x18003569e  cmp     qword ptr [rbx], 0
0x1800356a2  jz      short loc_1800356F0
0x1800356a4  mov     [rsi], bpl
0x1800356a7  mov     r9, r14; unsigned __int64
0x1800356aa  mov     r8, rsi; char *
0x1800356ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800356b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800356b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800356b8  test    al, al
0x1800356ba  jz      short loc_1800356C0
0x1800356bc  mov     [rdi+48h], rsi
0x1800356c0  mov     rbx, [rbx]
0x1800356c3  mov     al, [rbx+28h]
0x1800356c6  mov     byte ptr [rbx+28h], 1
0x1800356ca  test    al, al
0x1800356cc  jnz     short loc_1800356E7
0x1800356ce  mov     rcx, [rbx+8]
0x1800356d2  mov     rax, [rcx]
0x1800356d5  mov     rdx, rdi
0x1800356d8  mov     rax, [rax]
0x1800356db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356e0  or      bpl, al
0x1800356e3  mov     byte ptr [rbx+28h], 0
0x1800356e7  mov     rbx, [rbx+10h]
0x1800356eb  test    rbx, rbx
0x1800356ee  jnz     short loc_1800356C3
0x1800356f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800356f7  test    rax, rax
0x1800356fa  jz      short loc_18003571C
0x1800356fc  test    bpl, bpl
0x1800356ff  jnz     short loc_180035711
0x180035701  test    byte ptr [rdi+4], 2
0x180035705  jnz     short loc_180035711
0x180035707  xor     ecx, ecx
0x180035709  jmp     short loc_180035713
0x18003570b  add     rbx, 10h
0x18003570f  jmp     short loc_180035699
0x180035711  mov     cl, 1
0x180035713  mov     rdx, rdi
0x180035716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003571b  nop
0x18003571c  call    cs:__imp_GetCurrentThreadId
0x180035722  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180035728  cmp     ecx, eax
0x18003572a  jz      loc_18003582C
0x180035730  mov     ecx, 1
0x180035735  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18003573d  inc     ecx; this
0x18003573f  cmp     ecx, 4
0x180035742  jge     loc_180035825
0x180035748  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18003574e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180035753  mov     rbx, rax
0x180035756  test    rax, rax
0x180035759  jz      loc_18003581B
0x18003575f  mov     esi, [rax+10h]
0x180035762  mov     ebp, 50h ; 'P'
0x180035767  cmp     qword ptr [rax+18h], 0
0x18003576c  jnz     short loc_1800357A3
0x18003576e  test    esi, esi
0x180035770  jz      short loc_1800357A3
0x180035772  mov     edx, 190h; dwBytes
0x180035777  lea     ecx, [rbp-48h]; dwFlags
0x18003577a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003577f  mov     [rbx+18h], rax
0x180035783  test    rax, rax
0x180035786  jz      short loc_1800357A3
0x180035788  mov     dword ptr [rbx+20h], 5
0x18003578f  lea     rcx, [rax+190h]
0x180035796  jmp     short loc_18003579E
0x180035798  mov     [rax], bp
0x18003579b  add     rax, rbp
0x18003579e  cmp     rax, rcx
0x1800357a1  jnz     short loc_180035798
0x1800357a3  mov     r9, [rbx+18h]
0x1800357a7  test    r9, r9
0x1800357aa  jz      short loc_18003581B
0x1800357ac  test    esi, esi
0x1800357ae  jz      short loc_1800357E1
0x1800357b0  mov     rcx, r9
0x1800357b3  movzx   eax, word ptr [rbx+20h]
0x1800357b7  lea     rdx, [rax+rax*4]
0x1800357bb  shl     rdx, 4
0x1800357bf  add     rdx, r9
0x1800357c2  cmp     r9, rdx
0x1800357c5  jz      short loc_1800357E1
0x1800357c7  mov     r8d, [rbx+10h]
0x1800357cb  cmp     [rcx+4], r8d
0x1800357cf  jbe     short loc_1800357D9
0x1800357d1  mov     eax, [rdi+8]
0x1800357d4  cmp     [rcx+8], eax
0x1800357d7  jz      short loc_18003581B
0x1800357d9  add     rcx, rbp
0x1800357dc  cmp     rcx, rdx
0x1800357df  jnz     short loc_1800357CB
0x1800357e1  movzx   eax, word ptr [rbx+22h]
0x1800357e5  inc     eax
0x1800357e7  movzx   ecx, word ptr [rbx+20h]
0x1800357eb  xor     edx, edx
0x1800357ed  div     ecx
0x1800357ef  mov     [rbx+22h], dx
0x1800357f3  mov     rax, [rbx+8]
0x1800357f7  mov     r8d, 1
0x1800357fd  lock xadd [rax], r8d
0x180035802  inc     r8d; unsigned int
0x180035805  movzx   eax, dx
0x180035808  lea     rcx, [rax+rax*4]
0x18003580c  shl     rcx, 4
0x180035810  add     rcx, r9; this
0x180035813  mov     rdx, rdi; struct wil::FailureInfo *
0x180035816  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18003581b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180035825  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18003582c  add     rsp, 20h
0x180035830  pop     r14
0x180035832  pop     rdi
0x180035833  pop     rsi
0x180035834  pop     rbp
0x180035835  pop     rbx
0x180035836  retn
```
