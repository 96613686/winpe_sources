# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400065e0`
- end: `0x1400067e6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400065e0`
- `0x140006cd8`
- `0x140006dbc`
- `0x140007748`
- `0x140008ad8`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000660a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400066cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000660a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400066cb`

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
0x1400065e0  push    rbx
0x1400065e2  push    rbp
0x1400065e3  push    rsi
0x1400065e4  push    rdi
0x1400065e5  push    r14
0x1400065e7  sub     rsp, 20h
0x1400065eb  mov     byte ptr [rdx], 0
0x1400065ee  xor     bpl, bpl
0x1400065f1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400065f8  mov     r14, r8
0x1400065fb  mov     rsi, rdx
0x1400065fe  mov     rdi, rcx
0x140006601  test    rbx, rbx
0x140006604  jz      loc_1400066A0
0x14000660a  call    cs:__imp_GetCurrentThreadId
0x140006610  mov     r8d, eax
0x140006613  mov     r9d, eax
0x140006616  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006620  shr     r8, 2
0x140006624  mul     r8
0x140006627  shr     rdx, 3
0x14000662b  lea     rcx, [rdx+rdx*4]
0x14000662f  add     rcx, rcx
0x140006632  sub     r8, rcx
0x140006635  mov     rbx, [rbx+r8*8]
0x140006639  jmp     short loc_140006644
0x14000663b  cmp     [rbx], r9d
0x14000663e  jz      short loc_1400066BB
0x140006640  mov     rbx, [rbx+8]
0x140006644  test    rbx, rbx
0x140006647  jnz     short loc_14000663B
0x140006649  test    rbx, rbx
0x14000664c  jz      short loc_1400066A0
0x14000664e  cmp     qword ptr [rbx], 0
0x140006652  jz      short loc_1400066A0
0x140006654  mov     [rsi], bpl
0x140006657  mov     r9, r14; unsigned __int64
0x14000665a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000665d  mov     r8, rsi; char *
0x140006660  mov     rcx, rdi; struct wil::FailureInfo *
0x140006663  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006668  test    al, al
0x14000666a  jz      short loc_140006670
0x14000666c  mov     [rdi+48h], rsi
0x140006670  mov     rbx, [rbx]
0x140006673  mov     al, [rbx+28h]
0x140006676  mov     byte ptr [rbx+28h], 1
0x14000667a  test    al, al
0x14000667c  jnz     short loc_140006697
0x14000667e  mov     rcx, [rbx+8]
0x140006682  mov     rdx, rdi
0x140006685  mov     rax, [rcx]
0x140006688  mov     rax, [rax]
0x14000668b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006690  or      bpl, al
0x140006693  mov     byte ptr [rbx+28h], 0
0x140006697  mov     rbx, [rbx+10h]
0x14000669b  test    rbx, rbx
0x14000669e  jnz     short loc_140006673
0x1400066a0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400066a7  test    rax, rax
0x1400066aa  jz      short loc_1400066CB
0x1400066ac  test    bpl, bpl
0x1400066af  jnz     short loc_1400066C1
0x1400066b1  test    byte ptr [rdi+4], 2
0x1400066b5  jnz     short loc_1400066C1
0x1400066b7  xor     ecx, ecx
0x1400066b9  jmp     short loc_1400066C3
0x1400066bb  add     rbx, 10h
0x1400066bf  jmp     short loc_140006649
0x1400066c1  mov     cl, 1
0x1400066c3  mov     rdx, rdi
0x1400066c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066cb  call    cs:__imp_GetCurrentThreadId
0x1400066d1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400066d7  cmp     ecx, eax
0x1400066d9  jz      loc_1400067DB
0x1400066df  mov     ecx, 1
0x1400066e4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400066ec  inc     ecx; this
0x1400066ee  cmp     ecx, 4
0x1400066f1  jge     loc_1400067D4
0x1400066f7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400066fd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140006702  mov     rbx, rax
0x140006705  test    rax, rax
0x140006708  jz      loc_1400067CA
0x14000670e  cmp     qword ptr [rax+18h], 0
0x140006713  mov     ebp, 50h ; 'P'
0x140006718  mov     esi, [rax+10h]
0x14000671b  jnz     short loc_140006752
0x14000671d  test    esi, esi
0x14000671f  jz      short loc_140006752
0x140006721  mov     edx, 190h; dwBytes
0x140006726  lea     ecx, [rbp-48h]; dwFlags
0x140006729  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000672e  mov     [rbx+18h], rax
0x140006732  test    rax, rax
0x140006735  jz      short loc_140006752
0x140006737  mov     dword ptr [rbx+20h], 5
0x14000673e  lea     rcx, [rax+190h]
0x140006745  jmp     short loc_14000674D
0x140006747  mov     [rax], bp
0x14000674a  add     rax, rbp
0x14000674d  cmp     rax, rcx
0x140006750  jnz     short loc_140006747
0x140006752  mov     r9, [rbx+18h]
0x140006756  test    r9, r9
0x140006759  jz      short loc_1400067CA
0x14000675b  test    esi, esi
0x14000675d  jz      short loc_140006790
0x14000675f  movzx   eax, word ptr [rbx+20h]
0x140006763  mov     rcx, r9
0x140006766  lea     rdx, [rax+rax*4]
0x14000676a  shl     rdx, 4
0x14000676e  add     rdx, r9
0x140006771  cmp     r9, rdx
0x140006774  jz      short loc_140006790
0x140006776  mov     r8d, [rbx+10h]
0x14000677a  cmp     [rcx+4], r8d
0x14000677e  jbe     short loc_140006788
0x140006780  mov     eax, [rdi+8]
0x140006783  cmp     [rcx+8], eax
0x140006786  jz      short loc_1400067CA
0x140006788  add     rcx, rbp
0x14000678b  cmp     rcx, rdx
0x14000678e  jnz     short loc_14000677A
0x140006790  movzx   eax, word ptr [rbx+22h]
0x140006794  xor     edx, edx
0x140006796  movzx   ecx, word ptr [rbx+20h]
0x14000679a  inc     eax
0x14000679c  div     ecx
0x14000679e  mov     rax, [rbx+8]
0x1400067a2  mov     r8d, 1
0x1400067a8  mov     [rbx+22h], dx
0x1400067ac  lock xadd [rax], r8d
0x1400067b1  movzx   eax, dx
0x1400067b4  inc     r8d; unsigned int
0x1400067b7  mov     rdx, rdi; struct wil::FailureInfo *
0x1400067ba  lea     rcx, [rax+rax*4]
0x1400067be  shl     rcx, 4
0x1400067c2  add     rcx, r9; this
0x1400067c5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400067ca  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400067d4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400067db  add     rsp, 20h
0x1400067df  pop     r14
0x1400067e1  pop     rdi
0x1400067e2  pop     rsi
0x1400067e3  pop     rbp
0x1400067e4  pop     rbx
0x1400067e5  retn
```
