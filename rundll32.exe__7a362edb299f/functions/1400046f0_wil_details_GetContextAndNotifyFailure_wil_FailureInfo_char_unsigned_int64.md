# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400046f0`
- end: `0x1400048f6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400046f0`
- `0x140004e50`
- `0x140004f34`
- `0x1400058a8`
- `0x140005fe4`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000471a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000471a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047db`

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
0x1400046f0  push    rbx
0x1400046f2  push    rbp
0x1400046f3  push    rsi
0x1400046f4  push    rdi
0x1400046f5  push    r14
0x1400046f7  sub     rsp, 20h
0x1400046fb  mov     byte ptr [rdx], 0
0x1400046fe  xor     bpl, bpl
0x140004701  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004708  mov     r14, r8
0x14000470b  mov     rsi, rdx
0x14000470e  mov     rdi, rcx
0x140004711  test    rbx, rbx
0x140004714  jz      loc_1400047B0
0x14000471a  call    cs:__imp_GetCurrentThreadId
0x140004720  mov     r8d, eax
0x140004723  mov     r9d, eax
0x140004726  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004730  shr     r8, 2
0x140004734  mul     r8
0x140004737  shr     rdx, 3
0x14000473b  lea     rcx, [rdx+rdx*4]
0x14000473f  add     rcx, rcx
0x140004742  sub     r8, rcx
0x140004745  mov     rbx, [rbx+r8*8]
0x140004749  jmp     short loc_140004754
0x14000474b  cmp     [rbx], r9d
0x14000474e  jz      short loc_1400047CB
0x140004750  mov     rbx, [rbx+8]
0x140004754  test    rbx, rbx
0x140004757  jnz     short loc_14000474B
0x140004759  test    rbx, rbx
0x14000475c  jz      short loc_1400047B0
0x14000475e  cmp     qword ptr [rbx], 0
0x140004762  jz      short loc_1400047B0
0x140004764  mov     [rsi], bpl
0x140004767  mov     r9, r14; unsigned __int64
0x14000476a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000476d  mov     r8, rsi; char *
0x140004770  mov     rcx, rdi; struct wil::FailureInfo *
0x140004773  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004778  test    al, al
0x14000477a  jz      short loc_140004780
0x14000477c  mov     [rdi+48h], rsi
0x140004780  mov     rbx, [rbx]
0x140004783  mov     al, [rbx+28h]
0x140004786  mov     byte ptr [rbx+28h], 1
0x14000478a  test    al, al
0x14000478c  jnz     short loc_1400047A7
0x14000478e  mov     rcx, [rbx+8]
0x140004792  mov     rdx, rdi
0x140004795  mov     rax, [rcx]
0x140004798  mov     rax, [rax]
0x14000479b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047a0  or      bpl, al
0x1400047a3  mov     byte ptr [rbx+28h], 0
0x1400047a7  mov     rbx, [rbx+10h]
0x1400047ab  test    rbx, rbx
0x1400047ae  jnz     short loc_140004783
0x1400047b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400047b7  test    rax, rax
0x1400047ba  jz      short loc_1400047DB
0x1400047bc  test    bpl, bpl
0x1400047bf  jnz     short loc_1400047D1
0x1400047c1  test    byte ptr [rdi+4], 2
0x1400047c5  jnz     short loc_1400047D1
0x1400047c7  xor     ecx, ecx
0x1400047c9  jmp     short loc_1400047D3
0x1400047cb  add     rbx, 10h
0x1400047cf  jmp     short loc_140004759
0x1400047d1  mov     cl, 1
0x1400047d3  mov     rdx, rdi
0x1400047d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047db  call    cs:__imp_GetCurrentThreadId
0x1400047e1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400047e7  cmp     ecx, eax
0x1400047e9  jz      loc_1400048EB
0x1400047ef  mov     ecx, 1
0x1400047f4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400047fc  inc     ecx; this
0x1400047fe  cmp     ecx, 4
0x140004801  jge     loc_1400048E4
0x140004807  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000480d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004812  mov     rbx, rax
0x140004815  test    rax, rax
0x140004818  jz      loc_1400048DA
0x14000481e  cmp     qword ptr [rax+18h], 0
0x140004823  mov     ebp, 50h ; 'P'
0x140004828  mov     esi, [rax+10h]
0x14000482b  jnz     short loc_140004862
0x14000482d  test    esi, esi
0x14000482f  jz      short loc_140004862
0x140004831  mov     edx, 190h; dwBytes
0x140004836  lea     ecx, [rbp-48h]; dwFlags
0x140004839  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000483e  mov     [rbx+18h], rax
0x140004842  test    rax, rax
0x140004845  jz      short loc_140004862
0x140004847  mov     dword ptr [rbx+20h], 5
0x14000484e  lea     rcx, [rax+190h]
0x140004855  jmp     short loc_14000485D
0x140004857  mov     [rax], bp
0x14000485a  add     rax, rbp
0x14000485d  cmp     rax, rcx
0x140004860  jnz     short loc_140004857
0x140004862  mov     r9, [rbx+18h]
0x140004866  test    r9, r9
0x140004869  jz      short loc_1400048DA
0x14000486b  test    esi, esi
0x14000486d  jz      short loc_1400048A0
0x14000486f  movzx   eax, word ptr [rbx+20h]
0x140004873  mov     rcx, r9
0x140004876  lea     rdx, [rax+rax*4]
0x14000487a  shl     rdx, 4
0x14000487e  add     rdx, r9
0x140004881  cmp     r9, rdx
0x140004884  jz      short loc_1400048A0
0x140004886  mov     r8d, [rbx+10h]
0x14000488a  cmp     [rcx+4], r8d
0x14000488e  jbe     short loc_140004898
0x140004890  mov     eax, [rdi+8]
0x140004893  cmp     [rcx+8], eax
0x140004896  jz      short loc_1400048DA
0x140004898  add     rcx, rbp
0x14000489b  cmp     rcx, rdx
0x14000489e  jnz     short loc_14000488A
0x1400048a0  movzx   eax, word ptr [rbx+22h]
0x1400048a4  xor     edx, edx
0x1400048a6  movzx   ecx, word ptr [rbx+20h]
0x1400048aa  inc     eax
0x1400048ac  div     ecx
0x1400048ae  mov     rax, [rbx+8]
0x1400048b2  mov     r8d, 1
0x1400048b8  mov     [rbx+22h], dx
0x1400048bc  lock xadd [rax], r8d
0x1400048c1  movzx   eax, dx
0x1400048c4  inc     r8d; unsigned int
0x1400048c7  mov     rdx, rdi; struct wil::FailureInfo *
0x1400048ca  lea     rcx, [rax+rax*4]
0x1400048ce  shl     rcx, 4
0x1400048d2  add     rcx, r9; this
0x1400048d5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400048da  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400048e4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400048eb  add     rsp, 20h
0x1400048ef  pop     r14
0x1400048f1  pop     rdi
0x1400048f2  pop     rsi
0x1400048f3  pop     rbp
0x1400048f4  pop     rbx
0x1400048f5  retn
```
