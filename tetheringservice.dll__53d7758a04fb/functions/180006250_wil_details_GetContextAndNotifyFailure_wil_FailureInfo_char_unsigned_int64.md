# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006250`
- end: `0x180006457`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006250`
- `0x18000694c`
- `0x180006a30`
- `0x1800071b8`
- `0x180008a24`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000627a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000633c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000627a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000633c`

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
0x180006250  push    rbx
0x180006252  push    rbp
0x180006253  push    rsi
0x180006254  push    rdi
0x180006255  push    r14
0x180006257  sub     rsp, 20h
0x18000625b  mov     r14, r8
0x18000625e  mov     rsi, rdx
0x180006261  mov     rdi, rcx
0x180006264  mov     byte ptr [rdx], 0
0x180006267  xor     bpl, bpl
0x18000626a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006271  test    rbx, rbx
0x180006274  jz      loc_180006310
0x18000627a  call    cs:__imp_GetCurrentThreadId
0x180006280  mov     r9d, eax
0x180006283  mov     r8d, eax
0x180006286  shr     r8, 2
0x18000628a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006294  mul     r8
0x180006297  shr     rdx, 3
0x18000629b  lea     rcx, [rdx+rdx*4]
0x18000629f  add     rcx, rcx
0x1800062a2  sub     r8, rcx
0x1800062a5  mov     rbx, [rbx+r8*8]
0x1800062a9  jmp     short loc_1800062B4
0x1800062ab  cmp     [rbx], r9d
0x1800062ae  jz      short loc_18000632B
0x1800062b0  mov     rbx, [rbx+8]
0x1800062b4  test    rbx, rbx
0x1800062b7  jnz     short loc_1800062AB
0x1800062b9  test    rbx, rbx
0x1800062bc  jz      short loc_180006310
0x1800062be  cmp     qword ptr [rbx], 0
0x1800062c2  jz      short loc_180006310
0x1800062c4  mov     [rsi], bpl
0x1800062c7  mov     r9, r14; unsigned __int64
0x1800062ca  mov     r8, rsi; char *
0x1800062cd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800062d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800062d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800062d8  test    al, al
0x1800062da  jz      short loc_1800062E0
0x1800062dc  mov     [rdi+48h], rsi
0x1800062e0  mov     rbx, [rbx]
0x1800062e3  mov     al, [rbx+28h]
0x1800062e6  mov     byte ptr [rbx+28h], 1
0x1800062ea  test    al, al
0x1800062ec  jnz     short loc_180006307
0x1800062ee  mov     rcx, [rbx+8]
0x1800062f2  mov     rax, [rcx]
0x1800062f5  mov     rdx, rdi
0x1800062f8  mov     rax, [rax]
0x1800062fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006300  or      bpl, al
0x180006303  mov     byte ptr [rbx+28h], 0
0x180006307  mov     rbx, [rbx+10h]
0x18000630b  test    rbx, rbx
0x18000630e  jnz     short loc_1800062E3
0x180006310  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006317  test    rax, rax
0x18000631a  jz      short loc_18000633C
0x18000631c  test    bpl, bpl
0x18000631f  jnz     short loc_180006331
0x180006321  test    byte ptr [rdi+4], 2
0x180006325  jnz     short loc_180006331
0x180006327  xor     ecx, ecx
0x180006329  jmp     short loc_180006333
0x18000632b  add     rbx, 10h
0x18000632f  jmp     short loc_1800062B9
0x180006331  mov     cl, 1
0x180006333  mov     rdx, rdi
0x180006336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000633b  nop
0x18000633c  call    cs:__imp_GetCurrentThreadId
0x180006342  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006348  cmp     ecx, eax
0x18000634a  jz      loc_18000644C
0x180006350  mov     ecx, 1
0x180006355  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000635d  inc     ecx; this
0x18000635f  cmp     ecx, 4
0x180006362  jge     loc_180006445
0x180006368  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000636e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006373  mov     rbx, rax
0x180006376  test    rax, rax
0x180006379  jz      loc_18000643B
0x18000637f  mov     esi, [rax+10h]
0x180006382  mov     ebp, 50h ; 'P'
0x180006387  cmp     qword ptr [rax+18h], 0
0x18000638c  jnz     short loc_1800063C3
0x18000638e  test    esi, esi
0x180006390  jz      short loc_1800063C3
0x180006392  mov     edx, 190h; dwBytes
0x180006397  lea     ecx, [rbp-48h]; dwFlags
0x18000639a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000639f  mov     [rbx+18h], rax
0x1800063a3  test    rax, rax
0x1800063a6  jz      short loc_1800063C3
0x1800063a8  mov     dword ptr [rbx+20h], 5
0x1800063af  lea     rcx, [rax+190h]
0x1800063b6  jmp     short loc_1800063BE
0x1800063b8  mov     [rax], bp
0x1800063bb  add     rax, rbp
0x1800063be  cmp     rax, rcx
0x1800063c1  jnz     short loc_1800063B8
0x1800063c3  mov     r9, [rbx+18h]
0x1800063c7  test    r9, r9
0x1800063ca  jz      short loc_18000643B
0x1800063cc  test    esi, esi
0x1800063ce  jz      short loc_180006401
0x1800063d0  mov     rcx, r9
0x1800063d3  movzx   eax, word ptr [rbx+20h]
0x1800063d7  lea     rdx, [rax+rax*4]
0x1800063db  shl     rdx, 4
0x1800063df  add     rdx, r9
0x1800063e2  cmp     r9, rdx
0x1800063e5  jz      short loc_180006401
0x1800063e7  mov     r8d, [rbx+10h]
0x1800063eb  cmp     [rcx+4], r8d
0x1800063ef  jbe     short loc_1800063F9
0x1800063f1  mov     eax, [rdi+8]
0x1800063f4  cmp     [rcx+8], eax
0x1800063f7  jz      short loc_18000643B
0x1800063f9  add     rcx, rbp
0x1800063fc  cmp     rcx, rdx
0x1800063ff  jnz     short loc_1800063EB
0x180006401  movzx   eax, word ptr [rbx+22h]
0x180006405  inc     eax
0x180006407  movzx   ecx, word ptr [rbx+20h]
0x18000640b  xor     edx, edx
0x18000640d  div     ecx
0x18000640f  mov     [rbx+22h], dx
0x180006413  mov     rax, [rbx+8]
0x180006417  mov     r8d, 1
0x18000641d  lock xadd [rax], r8d
0x180006422  inc     r8d; unsigned int
0x180006425  movzx   eax, dx
0x180006428  lea     rcx, [rax+rax*4]
0x18000642c  shl     rcx, 4
0x180006430  add     rcx, r9; this
0x180006433  mov     rdx, rdi; struct wil::FailureInfo *
0x180006436  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000643b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006445  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000644c  add     rsp, 20h
0x180006450  pop     r14
0x180006452  pop     rdi
0x180006453  pop     rsi
0x180006454  pop     rbp
0x180006455  pop     rbx
0x180006456  retn
```
