# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004010`
- end: `0x18000421a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000215c`
- `0x180003bb0`
- `0x180003e50`
- `0x180003f10`
- `0x180004010`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040f7`

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
  struct wil::details::ThreadFailureCallbackHolder **v10; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
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
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * (CurrentThreadId % 0xA)); ; i = *(_QWORD *)(i + 8) )
    {
      if ( !i )
      {
        v10 = 0;
        goto LABEL_7;
      }
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
        break;
    }
    v10 = (struct wil::details::ThreadFailureCallbackHolder **)(i + 16);
LABEL_7:
    if ( v10 && *v10 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v10, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v11 = *v10;
      do
      {
        v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (LOBYTE(this) = 0, (*((_BYTE *)v5 + 4) & 2) != 0) )
      LOBYTE(this) = 1;
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
LABEL_34:
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
                goto LABEL_34;
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
0x180004010  mov     [rsp+arg_18], rbx
0x180004015  push    rbp
0x180004016  push    rsi
0x180004017  push    rdi
0x180004018  push    r14
0x18000401a  push    r15
0x18000401c  sub     rsp, 20h
0x180004020  mov     r14, r8
0x180004023  mov     rsi, rdx
0x180004026  mov     rdi, rcx
0x180004029  xor     r15d, r15d
0x18000402c  mov     [rdx], r15b
0x18000402f  mov     bpl, r15b
0x180004032  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004039  test    rbx, rbx
0x18000403c  jz      loc_1800040CB
0x180004042  call    cs:__imp_GetCurrentThreadId
0x180004048  mov     r9d, eax
0x18000404b  mov     r8d, eax
0x18000404e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004058  mul     r9
0x18000405b  shr     rdx, 3
0x18000405f  lea     rcx, [rdx+rdx*4]
0x180004063  add     rcx, rcx
0x180004066  sub     r8, rcx
0x180004069  mov     rbx, [rbx+r8*8]
0x18000406d  jmp     short loc_18000407C
0x18000406f  cmp     [rbx], r9d
0x180004072  jz      loc_180004171
0x180004078  mov     rbx, [rbx+8]
0x18000407c  test    rbx, rbx
0x18000407f  jnz     short loc_18000406F
0x180004081  mov     rbx, r15
0x180004084  test    rbx, rbx
0x180004087  jz      short loc_1800040CB
0x180004089  cmp     [rbx], r15
0x18000408c  jz      short loc_1800040CB
0x18000408e  mov     [rsi], r15b
0x180004091  mov     r9, r14; unsigned __int64
0x180004094  mov     r8, rsi; char *
0x180004097  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000409a  mov     rcx, rdi; struct wil::FailureInfo *
0x18000409d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800040a2  test    al, al
0x1800040a4  jz      short loc_1800040AA
0x1800040a6  mov     [rdi+48h], rsi
0x1800040aa  mov     rbx, [rbx]
0x1800040ad  mov     rcx, [rbx+8]
0x1800040b1  mov     rax, [rcx]
0x1800040b4  mov     rdx, rdi
0x1800040b7  mov     rax, [rax]
0x1800040ba  call    _guard_dispatch_icall
0x1800040bf  or      bpl, al
0x1800040c2  mov     rbx, [rbx+10h]
0x1800040c6  test    rbx, rbx
0x1800040c9  jnz     short loc_1800040AD
0x1800040cb  mov     r14d, 1
0x1800040d1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800040d8  test    rax, rax
0x1800040db  jz      short loc_1800040F7
0x1800040dd  test    bpl, bpl
0x1800040e0  jnz     short loc_1800040EB
0x1800040e2  test    byte ptr [rdi+4], 2
0x1800040e6  mov     cl, r15b
0x1800040e9  jz      short loc_1800040EE
0x1800040eb  mov     cl, r14b
0x1800040ee  mov     rdx, rdi
0x1800040f1  call    _guard_dispatch_icall
0x1800040f6  nop
0x1800040f7  call    cs:__imp_GetCurrentThreadId
0x1800040fd  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004103  cmp     ecx, eax
0x180004105  jz      loc_180004209
0x18000410b  mov     ecx, r14d
0x18000410e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004116  add     ecx, r14d; this
0x180004119  cmp     ecx, 4
0x18000411c  jge     loc_180004202
0x180004122  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004128  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000412d  mov     rbx, rax
0x180004130  test    rax, rax
0x180004133  jz      loc_1800041FB
0x180004139  mov     esi, [rax+10h]
0x18000413c  mov     ebp, 50h ; 'P'
0x180004141  cmp     [rax+18h], r15
0x180004145  jnz     short loc_180004185
0x180004147  test    esi, esi
0x180004149  jz      short loc_180004185
0x18000414b  mov     edx, 190h; dwBytes
0x180004150  lea     ecx, [rbp-48h]; dwFlags
0x180004153  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004158  mov     [rbx+18h], rax
0x18000415c  test    rax, rax
0x18000415f  jz      short loc_180004185
0x180004161  mov     dword ptr [rbx+20h], 5
0x180004168  lea     rcx, [rax+190h]
0x18000416f  jmp     short loc_180004180
0x180004171  add     rbx, 10h
0x180004175  jmp     loc_180004084
0x18000417a  mov     [rax], bp
0x18000417d  add     rax, rbp
0x180004180  cmp     rax, rcx
0x180004183  jnz     short loc_18000417A
0x180004185  mov     r9, [rbx+18h]
0x180004189  test    r9, r9
0x18000418c  jz      short loc_1800041FB
0x18000418e  test    esi, esi
0x180004190  jz      short loc_1800041C3
0x180004192  mov     rcx, r9
0x180004195  movzx   eax, word ptr [rbx+20h]
0x180004199  lea     rdx, [rax+rax*4]
0x18000419d  shl     rdx, 4
0x1800041a1  add     rdx, r9
0x1800041a4  cmp     r9, rdx
0x1800041a7  jz      short loc_1800041C3
0x1800041a9  mov     r8d, [rbx+10h]
0x1800041ad  cmp     [rcx+4], r8d
0x1800041b1  jbe     short loc_1800041BB
0x1800041b3  mov     eax, [rdi+8]
0x1800041b6  cmp     [rcx+8], eax
0x1800041b9  jz      short loc_1800041FB
0x1800041bb  add     rcx, rbp
0x1800041be  cmp     rcx, rdx
0x1800041c1  jnz     short loc_1800041AD
0x1800041c3  movzx   eax, word ptr [rbx+22h]
0x1800041c7  add     eax, r14d
0x1800041ca  movzx   ecx, word ptr [rbx+20h]
0x1800041ce  xor     edx, edx
0x1800041d0  div     ecx
0x1800041d2  mov     [rbx+22h], dx
0x1800041d6  mov     rax, [rbx+8]
0x1800041da  mov     r8d, r14d
0x1800041dd  lock xadd [rax], r8d
0x1800041e2  add     r8d, r14d; unsigned int
0x1800041e5  movzx   eax, dx
0x1800041e8  lea     rcx, [rax+rax*4]
0x1800041ec  shl     rcx, 4
0x1800041f0  add     rcx, r9; this
0x1800041f3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800041f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800041fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004202  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004209  mov     rbx, [rsp+48h+arg_18]
0x18000420e  add     rsp, 20h
0x180004212  pop     r15
0x180004214  pop     r14
0x180004216  pop     rdi
0x180004217  pop     rsi
0x180004218  pop     rbp
0x180004219  retn
```
