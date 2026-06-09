# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004710`
- end: `0x180004917`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004710`
- `0x180004e0c`
- `0x180004ef0`
- `0x180005768`
- `0x180005ab4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000473a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000473a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047fc`

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
0x180004710  push    rbx
0x180004712  push    rbp
0x180004713  push    rsi
0x180004714  push    rdi
0x180004715  push    r14
0x180004717  sub     rsp, 20h
0x18000471b  mov     r14, r8
0x18000471e  mov     rsi, rdx
0x180004721  mov     rdi, rcx
0x180004724  mov     byte ptr [rdx], 0
0x180004727  xor     bpl, bpl
0x18000472a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004731  test    rbx, rbx
0x180004734  jz      loc_1800047D0
0x18000473a  call    cs:__imp_GetCurrentThreadId
0x180004740  mov     r9d, eax
0x180004743  mov     r8d, eax
0x180004746  shr     r8, 2
0x18000474a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004754  mul     r8
0x180004757  shr     rdx, 3
0x18000475b  lea     rcx, [rdx+rdx*4]
0x18000475f  add     rcx, rcx
0x180004762  sub     r8, rcx
0x180004765  mov     rbx, [rbx+r8*8]
0x180004769  jmp     short loc_180004774
0x18000476b  cmp     [rbx], r9d
0x18000476e  jz      short loc_1800047EB
0x180004770  mov     rbx, [rbx+8]
0x180004774  test    rbx, rbx
0x180004777  jnz     short loc_18000476B
0x180004779  test    rbx, rbx
0x18000477c  jz      short loc_1800047D0
0x18000477e  cmp     qword ptr [rbx], 0
0x180004782  jz      short loc_1800047D0
0x180004784  mov     [rsi], bpl
0x180004787  mov     r9, r14; unsigned __int64
0x18000478a  mov     r8, rsi; char *
0x18000478d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004790  mov     rcx, rdi; struct wil::FailureInfo *
0x180004793  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004798  test    al, al
0x18000479a  jz      short loc_1800047A0
0x18000479c  mov     [rdi+48h], rsi
0x1800047a0  mov     rbx, [rbx]
0x1800047a3  mov     al, [rbx+28h]
0x1800047a6  mov     byte ptr [rbx+28h], 1
0x1800047aa  test    al, al
0x1800047ac  jnz     short loc_1800047C7
0x1800047ae  mov     rcx, [rbx+8]
0x1800047b2  mov     rax, [rcx]
0x1800047b5  mov     rdx, rdi
0x1800047b8  mov     rax, [rax]
0x1800047bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c0  or      bpl, al
0x1800047c3  mov     byte ptr [rbx+28h], 0
0x1800047c7  mov     rbx, [rbx+10h]
0x1800047cb  test    rbx, rbx
0x1800047ce  jnz     short loc_1800047A3
0x1800047d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800047d7  test    rax, rax
0x1800047da  jz      short loc_1800047FC
0x1800047dc  test    bpl, bpl
0x1800047df  jnz     short loc_1800047F1
0x1800047e1  test    byte ptr [rdi+4], 2
0x1800047e5  jnz     short loc_1800047F1
0x1800047e7  xor     ecx, ecx
0x1800047e9  jmp     short loc_1800047F3
0x1800047eb  add     rbx, 10h
0x1800047ef  jmp     short loc_180004779
0x1800047f1  mov     cl, 1
0x1800047f3  mov     rdx, rdi
0x1800047f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047fb  nop
0x1800047fc  call    cs:__imp_GetCurrentThreadId
0x180004802  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004808  cmp     ecx, eax
0x18000480a  jz      loc_18000490C
0x180004810  mov     ecx, 1
0x180004815  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000481d  inc     ecx; this
0x18000481f  cmp     ecx, 4
0x180004822  jge     loc_180004905
0x180004828  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000482e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004833  mov     rbx, rax
0x180004836  test    rax, rax
0x180004839  jz      loc_1800048FB
0x18000483f  mov     esi, [rax+10h]
0x180004842  mov     ebp, 50h ; 'P'
0x180004847  cmp     qword ptr [rax+18h], 0
0x18000484c  jnz     short loc_180004883
0x18000484e  test    esi, esi
0x180004850  jz      short loc_180004883
0x180004852  mov     edx, 190h; dwBytes
0x180004857  lea     ecx, [rbp-48h]; dwFlags
0x18000485a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000485f  mov     [rbx+18h], rax
0x180004863  test    rax, rax
0x180004866  jz      short loc_180004883
0x180004868  mov     dword ptr [rbx+20h], 5
0x18000486f  lea     rcx, [rax+190h]
0x180004876  jmp     short loc_18000487E
0x180004878  mov     [rax], bp
0x18000487b  add     rax, rbp
0x18000487e  cmp     rax, rcx
0x180004881  jnz     short loc_180004878
0x180004883  mov     r9, [rbx+18h]
0x180004887  test    r9, r9
0x18000488a  jz      short loc_1800048FB
0x18000488c  test    esi, esi
0x18000488e  jz      short loc_1800048C1
0x180004890  mov     rcx, r9
0x180004893  movzx   eax, word ptr [rbx+20h]
0x180004897  lea     rdx, [rax+rax*4]
0x18000489b  shl     rdx, 4
0x18000489f  add     rdx, r9
0x1800048a2  cmp     r9, rdx
0x1800048a5  jz      short loc_1800048C1
0x1800048a7  mov     r8d, [rbx+10h]
0x1800048ab  cmp     [rcx+4], r8d
0x1800048af  jbe     short loc_1800048B9
0x1800048b1  mov     eax, [rdi+8]
0x1800048b4  cmp     [rcx+8], eax
0x1800048b7  jz      short loc_1800048FB
0x1800048b9  add     rcx, rbp
0x1800048bc  cmp     rcx, rdx
0x1800048bf  jnz     short loc_1800048AB
0x1800048c1  movzx   eax, word ptr [rbx+22h]
0x1800048c5  inc     eax
0x1800048c7  movzx   ecx, word ptr [rbx+20h]
0x1800048cb  xor     edx, edx
0x1800048cd  div     ecx
0x1800048cf  mov     [rbx+22h], dx
0x1800048d3  mov     rax, [rbx+8]
0x1800048d7  mov     r8d, 1
0x1800048dd  lock xadd [rax], r8d
0x1800048e2  inc     r8d; unsigned int
0x1800048e5  movzx   eax, dx
0x1800048e8  lea     rcx, [rax+rax*4]
0x1800048ec  shl     rcx, 4
0x1800048f0  add     rcx, r9; this
0x1800048f3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800048f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800048fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004905  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000490c  add     rsp, 20h
0x180004910  pop     r14
0x180004912  pop     rdi
0x180004913  pop     rsi
0x180004914  pop     rbp
0x180004915  pop     rbx
0x180004916  retn
```
