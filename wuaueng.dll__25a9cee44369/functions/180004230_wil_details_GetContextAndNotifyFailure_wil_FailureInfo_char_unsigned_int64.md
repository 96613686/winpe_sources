# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004230`
- end: `0x18000443a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000215c`
- `0x180003dd0`
- `0x180004070`
- `0x180004130`
- `0x180004230`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004262`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004262`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004317`

## pseudocode

```c
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
0x180004230  mov     [rsp+arg_18], rbx
0x180004235  push    rbp
0x180004236  push    rsi
0x180004237  push    rdi
0x180004238  push    r14
0x18000423a  push    r15
0x18000423c  sub     rsp, 20h
0x180004240  mov     r14, r8
0x180004243  mov     rsi, rdx
0x180004246  mov     rdi, rcx
0x180004249  xor     r15d, r15d
0x18000424c  mov     [rdx], r15b
0x18000424f  mov     bpl, r15b
0x180004252  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004259  test    rbx, rbx
0x18000425c  jz      loc_1800042EB
0x180004262  call    cs:__imp_GetCurrentThreadId
0x180004268  mov     r9d, eax
0x18000426b  mov     r8d, eax
0x18000426e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004278  mul     r9
0x18000427b  shr     rdx, 3
0x18000427f  lea     rcx, [rdx+rdx*4]
0x180004283  add     rcx, rcx
0x180004286  sub     r8, rcx
0x180004289  mov     rbx, [rbx+r8*8]
0x18000428d  jmp     short loc_18000429C
0x18000428f  cmp     [rbx], r9d
0x180004292  jz      loc_180004391
0x180004298  mov     rbx, [rbx+8]
0x18000429c  test    rbx, rbx
0x18000429f  jnz     short loc_18000428F
0x1800042a1  mov     rbx, r15
0x1800042a4  test    rbx, rbx
0x1800042a7  jz      short loc_1800042EB
0x1800042a9  cmp     [rbx], r15
0x1800042ac  jz      short loc_1800042EB
0x1800042ae  mov     [rsi], r15b
0x1800042b1  mov     r9, r14; unsigned __int64
0x1800042b4  mov     r8, rsi; char *
0x1800042b7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800042ba  mov     rcx, rdi; struct wil::FailureInfo *
0x1800042bd  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800042c2  test    al, al
0x1800042c4  jz      short loc_1800042CA
0x1800042c6  mov     [rdi+48h], rsi
0x1800042ca  mov     rbx, [rbx]
0x1800042cd  mov     rcx, [rbx+8]
0x1800042d1  mov     rax, [rcx]
0x1800042d4  mov     rdx, rdi
0x1800042d7  mov     rax, [rax]
0x1800042da  call    _guard_dispatch_icall
0x1800042df  or      bpl, al
0x1800042e2  mov     rbx, [rbx+10h]
0x1800042e6  test    rbx, rbx
0x1800042e9  jnz     short loc_1800042CD
0x1800042eb  mov     r14d, 1
0x1800042f1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800042f8  test    rax, rax
0x1800042fb  jz      short loc_180004317
0x1800042fd  test    bpl, bpl
0x180004300  jnz     short loc_18000430B
0x180004302  test    byte ptr [rdi+4], 2
0x180004306  mov     cl, r15b
0x180004309  jz      short loc_18000430E
0x18000430b  mov     cl, r14b
0x18000430e  mov     rdx, rdi
0x180004311  call    _guard_dispatch_icall
0x180004316  nop
0x180004317  call    cs:__imp_GetCurrentThreadId
0x18000431d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004323  cmp     ecx, eax
0x180004325  jz      loc_180004429
0x18000432b  mov     ecx, r14d
0x18000432e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004336  add     ecx, r14d; this
0x180004339  cmp     ecx, 4
0x18000433c  jge     loc_180004422
0x180004342  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004348  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000434d  mov     rbx, rax
0x180004350  test    rax, rax
0x180004353  jz      loc_18000441B
0x180004359  mov     esi, [rax+10h]
0x18000435c  mov     ebp, 50h ; 'P'
0x180004361  cmp     [rax+18h], r15
0x180004365  jnz     short loc_1800043A5
0x180004367  test    esi, esi
0x180004369  jz      short loc_1800043A5
0x18000436b  mov     edx, 190h; dwBytes
0x180004370  lea     ecx, [rbp-48h]; dwFlags
0x180004373  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004378  mov     [rbx+18h], rax
0x18000437c  test    rax, rax
0x18000437f  jz      short loc_1800043A5
0x180004381  mov     dword ptr [rbx+20h], 5
0x180004388  lea     rcx, [rax+190h]
0x18000438f  jmp     short loc_1800043A0
0x180004391  add     rbx, 10h
0x180004395  jmp     loc_1800042A4
0x18000439a  mov     [rax], bp
0x18000439d  add     rax, rbp
0x1800043a0  cmp     rax, rcx
0x1800043a3  jnz     short loc_18000439A
0x1800043a5  mov     r9, [rbx+18h]
0x1800043a9  test    r9, r9
0x1800043ac  jz      short loc_18000441B
0x1800043ae  test    esi, esi
0x1800043b0  jz      short loc_1800043E3
0x1800043b2  mov     rcx, r9
0x1800043b5  movzx   eax, word ptr [rbx+20h]
0x1800043b9  lea     rdx, [rax+rax*4]
0x1800043bd  shl     rdx, 4
0x1800043c1  add     rdx, r9
0x1800043c4  cmp     r9, rdx
0x1800043c7  jz      short loc_1800043E3
0x1800043c9  mov     r8d, [rbx+10h]
0x1800043cd  cmp     [rcx+4], r8d
0x1800043d1  jbe     short loc_1800043DB
0x1800043d3  mov     eax, [rdi+8]
0x1800043d6  cmp     [rcx+8], eax
0x1800043d9  jz      short loc_18000441B
0x1800043db  add     rcx, rbp
0x1800043de  cmp     rcx, rdx
0x1800043e1  jnz     short loc_1800043CD
0x1800043e3  movzx   eax, word ptr [rbx+22h]
0x1800043e7  add     eax, r14d
0x1800043ea  movzx   ecx, word ptr [rbx+20h]
0x1800043ee  xor     edx, edx
0x1800043f0  div     ecx
0x1800043f2  mov     [rbx+22h], dx
0x1800043f6  mov     rax, [rbx+8]
0x1800043fa  mov     r8d, r14d
0x1800043fd  lock xadd [rax], r8d
0x180004402  add     r8d, r14d; unsigned int
0x180004405  movzx   eax, dx
0x180004408  lea     rcx, [rax+rax*4]
0x18000440c  shl     rcx, 4
0x180004410  add     rcx, r9; this
0x180004413  mov     rdx, rdi; struct wil::FailureInfo *
0x180004416  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000441b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004422  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004429  mov     rbx, [rsp+48h+arg_18]
0x18000442e  add     rsp, 20h
0x180004432  pop     r15
0x180004434  pop     r14
0x180004436  pop     rdi
0x180004437  pop     rsi
0x180004438  pop     rbp
0x180004439  retn
```
