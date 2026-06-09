# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004220`
- end: `0x18000442a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000234c`
- `0x180003dc0`
- `0x180004060`
- `0x180004120`
- `0x180004220`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004307`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004307`

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
0x180004220  mov     [rsp+arg_18], rbx
0x180004225  push    rbp
0x180004226  push    rsi
0x180004227  push    rdi
0x180004228  push    r14
0x18000422a  push    r15
0x18000422c  sub     rsp, 20h
0x180004230  mov     r14, r8
0x180004233  mov     rsi, rdx
0x180004236  mov     rdi, rcx
0x180004239  xor     r15d, r15d
0x18000423c  mov     [rdx], r15b
0x18000423f  mov     bpl, r15b
0x180004242  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004249  test    rbx, rbx
0x18000424c  jz      loc_1800042DB
0x180004252  call    cs:__imp_GetCurrentThreadId
0x180004258  mov     r9d, eax
0x18000425b  mov     r8d, eax
0x18000425e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004268  mul     r9
0x18000426b  shr     rdx, 3
0x18000426f  lea     rcx, [rdx+rdx*4]
0x180004273  add     rcx, rcx
0x180004276  sub     r8, rcx
0x180004279  mov     rbx, [rbx+r8*8]
0x18000427d  jmp     short loc_18000428C
0x18000427f  cmp     [rbx], r9d
0x180004282  jz      loc_180004381
0x180004288  mov     rbx, [rbx+8]
0x18000428c  test    rbx, rbx
0x18000428f  jnz     short loc_18000427F
0x180004291  mov     rbx, r15
0x180004294  test    rbx, rbx
0x180004297  jz      short loc_1800042DB
0x180004299  cmp     [rbx], r15
0x18000429c  jz      short loc_1800042DB
0x18000429e  mov     [rsi], r15b
0x1800042a1  mov     r9, r14; unsigned __int64
0x1800042a4  mov     r8, rsi; char *
0x1800042a7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800042aa  mov     rcx, rdi; struct wil::FailureInfo *
0x1800042ad  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800042b2  test    al, al
0x1800042b4  jz      short loc_1800042BA
0x1800042b6  mov     [rdi+48h], rsi
0x1800042ba  mov     rbx, [rbx]
0x1800042bd  mov     rcx, [rbx+8]
0x1800042c1  mov     rax, [rcx]
0x1800042c4  mov     rdx, rdi
0x1800042c7  mov     rax, [rax]
0x1800042ca  call    _guard_dispatch_icall
0x1800042cf  or      bpl, al
0x1800042d2  mov     rbx, [rbx+10h]
0x1800042d6  test    rbx, rbx
0x1800042d9  jnz     short loc_1800042BD
0x1800042db  mov     r14d, 1
0x1800042e1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800042e8  test    rax, rax
0x1800042eb  jz      short loc_180004307
0x1800042ed  test    bpl, bpl
0x1800042f0  jnz     short loc_1800042FB
0x1800042f2  test    byte ptr [rdi+4], 2
0x1800042f6  mov     cl, r15b
0x1800042f9  jz      short loc_1800042FE
0x1800042fb  mov     cl, r14b
0x1800042fe  mov     rdx, rdi
0x180004301  call    _guard_dispatch_icall
0x180004306  nop
0x180004307  call    cs:__imp_GetCurrentThreadId
0x18000430d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004313  cmp     ecx, eax
0x180004315  jz      loc_180004419
0x18000431b  mov     ecx, r14d
0x18000431e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004326  add     ecx, r14d; this
0x180004329  cmp     ecx, 4
0x18000432c  jge     loc_180004412
0x180004332  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004338  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000433d  mov     rbx, rax
0x180004340  test    rax, rax
0x180004343  jz      loc_18000440B
0x180004349  mov     esi, [rax+10h]
0x18000434c  mov     ebp, 50h ; 'P'
0x180004351  cmp     [rax+18h], r15
0x180004355  jnz     short loc_180004395
0x180004357  test    esi, esi
0x180004359  jz      short loc_180004395
0x18000435b  mov     edx, 190h; dwBytes
0x180004360  lea     ecx, [rbp-48h]; dwFlags
0x180004363  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004368  mov     [rbx+18h], rax
0x18000436c  test    rax, rax
0x18000436f  jz      short loc_180004395
0x180004371  mov     dword ptr [rbx+20h], 5
0x180004378  lea     rcx, [rax+190h]
0x18000437f  jmp     short loc_180004390
0x180004381  add     rbx, 10h
0x180004385  jmp     loc_180004294
0x18000438a  mov     [rax], bp
0x18000438d  add     rax, rbp
0x180004390  cmp     rax, rcx
0x180004393  jnz     short loc_18000438A
0x180004395  mov     r9, [rbx+18h]
0x180004399  test    r9, r9
0x18000439c  jz      short loc_18000440B
0x18000439e  test    esi, esi
0x1800043a0  jz      short loc_1800043D3
0x1800043a2  mov     rcx, r9
0x1800043a5  movzx   eax, word ptr [rbx+20h]
0x1800043a9  lea     rdx, [rax+rax*4]
0x1800043ad  shl     rdx, 4
0x1800043b1  add     rdx, r9
0x1800043b4  cmp     r9, rdx
0x1800043b7  jz      short loc_1800043D3
0x1800043b9  mov     r8d, [rbx+10h]
0x1800043bd  cmp     [rcx+4], r8d
0x1800043c1  jbe     short loc_1800043CB
0x1800043c3  mov     eax, [rdi+8]
0x1800043c6  cmp     [rcx+8], eax
0x1800043c9  jz      short loc_18000440B
0x1800043cb  add     rcx, rbp
0x1800043ce  cmp     rcx, rdx
0x1800043d1  jnz     short loc_1800043BD
0x1800043d3  movzx   eax, word ptr [rbx+22h]
0x1800043d7  add     eax, r14d
0x1800043da  movzx   ecx, word ptr [rbx+20h]
0x1800043de  xor     edx, edx
0x1800043e0  div     ecx
0x1800043e2  mov     [rbx+22h], dx
0x1800043e6  mov     rax, [rbx+8]
0x1800043ea  mov     r8d, r14d
0x1800043ed  lock xadd [rax], r8d
0x1800043f2  add     r8d, r14d; unsigned int
0x1800043f5  movzx   eax, dx
0x1800043f8  lea     rcx, [rax+rax*4]
0x1800043fc  shl     rcx, 4
0x180004400  add     rcx, r9; this
0x180004403  mov     rdx, rdi; struct wil::FailureInfo *
0x180004406  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000440b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004412  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004419  mov     rbx, [rsp+48h+arg_18]
0x18000441e  add     rsp, 20h
0x180004422  pop     r15
0x180004424  pop     r14
0x180004426  pop     rdi
0x180004427  pop     rsi
0x180004428  pop     rbp
0x180004429  retn
```
