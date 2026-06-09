# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006760`
- end: `0x180006967`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006760`
- `0x18000708c`
- `0x180007170`
- `0x180007d28`
- `0x18000a934`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000678a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000684c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000678a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000684c`

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
0x180006760  push    rbx
0x180006762  push    rbp
0x180006763  push    rsi
0x180006764  push    rdi
0x180006765  push    r14
0x180006767  sub     rsp, 20h
0x18000676b  mov     r14, r8
0x18000676e  mov     rsi, rdx
0x180006771  mov     rdi, rcx
0x180006774  mov     byte ptr [rdx], 0
0x180006777  xor     bpl, bpl
0x18000677a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006781  test    rbx, rbx
0x180006784  jz      loc_180006820
0x18000678a  call    cs:__imp_GetCurrentThreadId
0x180006790  mov     r9d, eax
0x180006793  mov     r8d, eax
0x180006796  shr     r8, 2
0x18000679a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800067a4  mul     r8
0x1800067a7  shr     rdx, 3
0x1800067ab  lea     rcx, [rdx+rdx*4]
0x1800067af  add     rcx, rcx
0x1800067b2  sub     r8, rcx
0x1800067b5  mov     rbx, [rbx+r8*8]
0x1800067b9  jmp     short loc_1800067C4
0x1800067bb  cmp     [rbx], r9d
0x1800067be  jz      short loc_18000683B
0x1800067c0  mov     rbx, [rbx+8]
0x1800067c4  test    rbx, rbx
0x1800067c7  jnz     short loc_1800067BB
0x1800067c9  test    rbx, rbx
0x1800067cc  jz      short loc_180006820
0x1800067ce  cmp     qword ptr [rbx], 0
0x1800067d2  jz      short loc_180006820
0x1800067d4  mov     [rsi], bpl
0x1800067d7  mov     r9, r14; unsigned __int64
0x1800067da  mov     r8, rsi; char *
0x1800067dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800067e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800067e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800067e8  test    al, al
0x1800067ea  jz      short loc_1800067F0
0x1800067ec  mov     [rdi+48h], rsi
0x1800067f0  mov     rbx, [rbx]
0x1800067f3  mov     al, [rbx+28h]
0x1800067f6  mov     byte ptr [rbx+28h], 1
0x1800067fa  test    al, al
0x1800067fc  jnz     short loc_180006817
0x1800067fe  mov     rcx, [rbx+8]
0x180006802  mov     rax, [rcx]
0x180006805  mov     rdx, rdi
0x180006808  mov     rax, [rax]
0x18000680b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006810  or      bpl, al
0x180006813  mov     byte ptr [rbx+28h], 0
0x180006817  mov     rbx, [rbx+10h]
0x18000681b  test    rbx, rbx
0x18000681e  jnz     short loc_1800067F3
0x180006820  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006827  test    rax, rax
0x18000682a  jz      short loc_18000684C
0x18000682c  test    bpl, bpl
0x18000682f  jnz     short loc_180006841
0x180006831  test    byte ptr [rdi+4], 2
0x180006835  jnz     short loc_180006841
0x180006837  xor     ecx, ecx
0x180006839  jmp     short loc_180006843
0x18000683b  add     rbx, 10h
0x18000683f  jmp     short loc_1800067C9
0x180006841  mov     cl, 1
0x180006843  mov     rdx, rdi
0x180006846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684b  nop
0x18000684c  call    cs:__imp_GetCurrentThreadId
0x180006852  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006858  cmp     ecx, eax
0x18000685a  jz      loc_18000695C
0x180006860  mov     ecx, 1
0x180006865  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000686d  inc     ecx; this
0x18000686f  cmp     ecx, 4
0x180006872  jge     loc_180006955
0x180006878  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000687e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006883  mov     rbx, rax
0x180006886  test    rax, rax
0x180006889  jz      loc_18000694B
0x18000688f  mov     esi, [rax+10h]
0x180006892  mov     ebp, 50h ; 'P'
0x180006897  cmp     qword ptr [rax+18h], 0
0x18000689c  jnz     short loc_1800068D3
0x18000689e  test    esi, esi
0x1800068a0  jz      short loc_1800068D3
0x1800068a2  mov     edx, 190h; dwBytes
0x1800068a7  lea     ecx, [rbp-48h]; dwFlags
0x1800068aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068af  mov     [rbx+18h], rax
0x1800068b3  test    rax, rax
0x1800068b6  jz      short loc_1800068D3
0x1800068b8  mov     dword ptr [rbx+20h], 5
0x1800068bf  lea     rcx, [rax+190h]
0x1800068c6  jmp     short loc_1800068CE
0x1800068c8  mov     [rax], bp
0x1800068cb  add     rax, rbp
0x1800068ce  cmp     rax, rcx
0x1800068d1  jnz     short loc_1800068C8
0x1800068d3  mov     r9, [rbx+18h]
0x1800068d7  test    r9, r9
0x1800068da  jz      short loc_18000694B
0x1800068dc  test    esi, esi
0x1800068de  jz      short loc_180006911
0x1800068e0  mov     rcx, r9
0x1800068e3  movzx   eax, word ptr [rbx+20h]
0x1800068e7  lea     rdx, [rax+rax*4]
0x1800068eb  shl     rdx, 4
0x1800068ef  add     rdx, r9
0x1800068f2  cmp     r9, rdx
0x1800068f5  jz      short loc_180006911
0x1800068f7  mov     r8d, [rbx+10h]
0x1800068fb  cmp     [rcx+4], r8d
0x1800068ff  jbe     short loc_180006909
0x180006901  mov     eax, [rdi+8]
0x180006904  cmp     [rcx+8], eax
0x180006907  jz      short loc_18000694B
0x180006909  add     rcx, rbp
0x18000690c  cmp     rcx, rdx
0x18000690f  jnz     short loc_1800068FB
0x180006911  movzx   eax, word ptr [rbx+22h]
0x180006915  inc     eax
0x180006917  movzx   ecx, word ptr [rbx+20h]
0x18000691b  xor     edx, edx
0x18000691d  div     ecx
0x18000691f  mov     [rbx+22h], dx
0x180006923  mov     rax, [rbx+8]
0x180006927  mov     r8d, 1
0x18000692d  lock xadd [rax], r8d
0x180006932  inc     r8d; unsigned int
0x180006935  movzx   eax, dx
0x180006938  lea     rcx, [rax+rax*4]
0x18000693c  shl     rcx, 4
0x180006940  add     rcx, r9; this
0x180006943  mov     rdx, rdi; struct wil::FailureInfo *
0x180006946  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000694b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006955  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000695c  add     rsp, 20h
0x180006960  pop     r14
0x180006962  pop     rdi
0x180006963  pop     rsi
0x180006964  pop     rbp
0x180006965  pop     rbx
0x180006966  retn
```
