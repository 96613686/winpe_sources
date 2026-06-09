# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004720`
- end: `0x180004927`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004720`
- `0x1800049f0`
- `0x180004b1c`
- `0x18000502c`
- `0x1800052f0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000474a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000480c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000474a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000480c`

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
0x180004720  push    rbx
0x180004722  push    rbp
0x180004723  push    rsi
0x180004724  push    rdi
0x180004725  push    r14
0x180004727  sub     rsp, 20h
0x18000472b  mov     r14, r8
0x18000472e  mov     rsi, rdx
0x180004731  mov     rdi, rcx
0x180004734  mov     byte ptr [rdx], 0
0x180004737  xor     bpl, bpl
0x18000473a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004741  test    rbx, rbx
0x180004744  jz      loc_1800047E0
0x18000474a  call    cs:__imp_GetCurrentThreadId
0x180004750  mov     r9d, eax
0x180004753  mov     r8d, eax
0x180004756  shr     r8, 2
0x18000475a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004764  mul     r8
0x180004767  shr     rdx, 3
0x18000476b  lea     rcx, [rdx+rdx*4]
0x18000476f  add     rcx, rcx
0x180004772  sub     r8, rcx
0x180004775  mov     rbx, [rbx+r8*8]
0x180004779  jmp     short loc_180004784
0x18000477b  cmp     [rbx], r9d
0x18000477e  jz      short loc_1800047FB
0x180004780  mov     rbx, [rbx+8]
0x180004784  test    rbx, rbx
0x180004787  jnz     short loc_18000477B
0x180004789  test    rbx, rbx
0x18000478c  jz      short loc_1800047E0
0x18000478e  cmp     qword ptr [rbx], 0
0x180004792  jz      short loc_1800047E0
0x180004794  mov     [rsi], bpl
0x180004797  mov     r9, r14; unsigned __int64
0x18000479a  mov     r8, rsi; char *
0x18000479d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800047a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800047a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800047a8  test    al, al
0x1800047aa  jz      short loc_1800047B0
0x1800047ac  mov     [rdi+48h], rsi
0x1800047b0  mov     rbx, [rbx]
0x1800047b3  mov     al, [rbx+28h]
0x1800047b6  mov     byte ptr [rbx+28h], 1
0x1800047ba  test    al, al
0x1800047bc  jnz     short loc_1800047D7
0x1800047be  mov     rcx, [rbx+8]
0x1800047c2  mov     rax, [rcx]
0x1800047c5  mov     rdx, rdi
0x1800047c8  mov     rax, [rax]
0x1800047cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d0  or      bpl, al
0x1800047d3  mov     byte ptr [rbx+28h], 0
0x1800047d7  mov     rbx, [rbx+10h]
0x1800047db  test    rbx, rbx
0x1800047de  jnz     short loc_1800047B3
0x1800047e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800047e7  test    rax, rax
0x1800047ea  jz      short loc_18000480C
0x1800047ec  test    bpl, bpl
0x1800047ef  jnz     short loc_180004801
0x1800047f1  test    byte ptr [rdi+4], 2
0x1800047f5  jnz     short loc_180004801
0x1800047f7  xor     ecx, ecx
0x1800047f9  jmp     short loc_180004803
0x1800047fb  add     rbx, 10h
0x1800047ff  jmp     short loc_180004789
0x180004801  mov     cl, 1
0x180004803  mov     rdx, rdi
0x180004806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000480b  nop
0x18000480c  call    cs:__imp_GetCurrentThreadId
0x180004812  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004818  cmp     ecx, eax
0x18000481a  jz      loc_18000491C
0x180004820  mov     ecx, 1
0x180004825  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000482d  inc     ecx; this
0x18000482f  cmp     ecx, 4
0x180004832  jge     loc_180004915
0x180004838  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000483e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004843  mov     rbx, rax
0x180004846  test    rax, rax
0x180004849  jz      loc_18000490B
0x18000484f  mov     esi, [rax+10h]
0x180004852  mov     ebp, 50h ; 'P'
0x180004857  cmp     qword ptr [rax+18h], 0
0x18000485c  jnz     short loc_180004893
0x18000485e  test    esi, esi
0x180004860  jz      short loc_180004893
0x180004862  mov     edx, 190h; dwBytes
0x180004867  lea     ecx, [rbp-48h]; dwFlags
0x18000486a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000486f  mov     [rbx+18h], rax
0x180004873  test    rax, rax
0x180004876  jz      short loc_180004893
0x180004878  mov     dword ptr [rbx+20h], 5
0x18000487f  lea     rcx, [rax+190h]
0x180004886  jmp     short loc_18000488E
0x180004888  mov     [rax], bp
0x18000488b  add     rax, rbp
0x18000488e  cmp     rax, rcx
0x180004891  jnz     short loc_180004888
0x180004893  mov     r9, [rbx+18h]
0x180004897  test    r9, r9
0x18000489a  jz      short loc_18000490B
0x18000489c  test    esi, esi
0x18000489e  jz      short loc_1800048D1
0x1800048a0  mov     rcx, r9
0x1800048a3  movzx   eax, word ptr [rbx+20h]
0x1800048a7  lea     rdx, [rax+rax*4]
0x1800048ab  shl     rdx, 4
0x1800048af  add     rdx, r9
0x1800048b2  cmp     r9, rdx
0x1800048b5  jz      short loc_1800048D1
0x1800048b7  mov     r8d, [rbx+10h]
0x1800048bb  cmp     [rcx+4], r8d
0x1800048bf  jbe     short loc_1800048C9
0x1800048c1  mov     eax, [rdi+8]
0x1800048c4  cmp     [rcx+8], eax
0x1800048c7  jz      short loc_18000490B
0x1800048c9  add     rcx, rbp
0x1800048cc  cmp     rcx, rdx
0x1800048cf  jnz     short loc_1800048BB
0x1800048d1  movzx   eax, word ptr [rbx+22h]
0x1800048d5  inc     eax
0x1800048d7  movzx   ecx, word ptr [rbx+20h]
0x1800048db  xor     edx, edx
0x1800048dd  div     ecx
0x1800048df  mov     [rbx+22h], dx
0x1800048e3  mov     rax, [rbx+8]
0x1800048e7  mov     r8d, 1
0x1800048ed  lock xadd [rax], r8d
0x1800048f2  inc     r8d; unsigned int
0x1800048f5  movzx   eax, dx
0x1800048f8  lea     rcx, [rax+rax*4]
0x1800048fc  shl     rcx, 4
0x180004900  add     rcx, r9; this
0x180004903  mov     rdx, rdi; struct wil::FailureInfo *
0x180004906  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000490b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004915  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000491c  add     rsp, 20h
0x180004920  pop     r14
0x180004922  pop     rdi
0x180004923  pop     rsi
0x180004924  pop     rbp
0x180004925  pop     rbx
0x180004926  retn
```
