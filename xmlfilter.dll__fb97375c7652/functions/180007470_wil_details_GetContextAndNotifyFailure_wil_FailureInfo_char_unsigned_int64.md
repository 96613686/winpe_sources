# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007470`
- end: `0x180007677`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007470`
- `0x180008508`
- `0x1800085ec`
- `0x180009870`
- `0x18000b834`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000749a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000755c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000749a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000755c`

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
0x180007470  push    rbx
0x180007472  push    rbp
0x180007473  push    rsi
0x180007474  push    rdi
0x180007475  push    r14
0x180007477  sub     rsp, 20h
0x18000747b  mov     r14, r8
0x18000747e  mov     rsi, rdx
0x180007481  mov     rdi, rcx
0x180007484  mov     byte ptr [rdx], 0
0x180007487  xor     bpl, bpl
0x18000748a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007491  test    rbx, rbx
0x180007494  jz      loc_180007530
0x18000749a  call    cs:__imp_GetCurrentThreadId
0x1800074a0  mov     r9d, eax
0x1800074a3  mov     r8d, eax
0x1800074a6  shr     r8, 2
0x1800074aa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800074b4  mul     r8
0x1800074b7  shr     rdx, 3
0x1800074bb  lea     rcx, [rdx+rdx*4]
0x1800074bf  add     rcx, rcx
0x1800074c2  sub     r8, rcx
0x1800074c5  mov     rbx, [rbx+r8*8]
0x1800074c9  jmp     short loc_1800074D4
0x1800074cb  cmp     [rbx], r9d
0x1800074ce  jz      short loc_18000754B
0x1800074d0  mov     rbx, [rbx+8]
0x1800074d4  test    rbx, rbx
0x1800074d7  jnz     short loc_1800074CB
0x1800074d9  test    rbx, rbx
0x1800074dc  jz      short loc_180007530
0x1800074de  cmp     qword ptr [rbx], 0
0x1800074e2  jz      short loc_180007530
0x1800074e4  mov     [rsi], bpl
0x1800074e7  mov     r9, r14; unsigned __int64
0x1800074ea  mov     r8, rsi; char *
0x1800074ed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800074f0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800074f3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800074f8  test    al, al
0x1800074fa  jz      short loc_180007500
0x1800074fc  mov     [rdi+48h], rsi
0x180007500  mov     rbx, [rbx]
0x180007503  mov     al, [rbx+28h]
0x180007506  mov     byte ptr [rbx+28h], 1
0x18000750a  test    al, al
0x18000750c  jnz     short loc_180007527
0x18000750e  mov     rcx, [rbx+8]
0x180007512  mov     rax, [rcx]
0x180007515  mov     rdx, rdi
0x180007518  mov     rax, [rax]
0x18000751b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007520  or      bpl, al
0x180007523  mov     byte ptr [rbx+28h], 0
0x180007527  mov     rbx, [rbx+10h]
0x18000752b  test    rbx, rbx
0x18000752e  jnz     short loc_180007503
0x180007530  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007537  test    rax, rax
0x18000753a  jz      short loc_18000755C
0x18000753c  test    bpl, bpl
0x18000753f  jnz     short loc_180007551
0x180007541  test    byte ptr [rdi+4], 2
0x180007545  jnz     short loc_180007551
0x180007547  xor     ecx, ecx
0x180007549  jmp     short loc_180007553
0x18000754b  add     rbx, 10h
0x18000754f  jmp     short loc_1800074D9
0x180007551  mov     cl, 1
0x180007553  mov     rdx, rdi
0x180007556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000755b  nop
0x18000755c  call    cs:__imp_GetCurrentThreadId
0x180007562  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007568  cmp     ecx, eax
0x18000756a  jz      loc_18000766C
0x180007570  mov     ecx, 1
0x180007575  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000757d  inc     ecx; this
0x18000757f  cmp     ecx, 4
0x180007582  jge     loc_180007665
0x180007588  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000758e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007593  mov     rbx, rax
0x180007596  test    rax, rax
0x180007599  jz      loc_18000765B
0x18000759f  mov     esi, [rax+10h]
0x1800075a2  mov     ebp, 50h ; 'P'
0x1800075a7  cmp     qword ptr [rax+18h], 0
0x1800075ac  jnz     short loc_1800075E3
0x1800075ae  test    esi, esi
0x1800075b0  jz      short loc_1800075E3
0x1800075b2  mov     edx, 190h; dwBytes
0x1800075b7  lea     ecx, [rbp-48h]; dwFlags
0x1800075ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800075bf  mov     [rbx+18h], rax
0x1800075c3  test    rax, rax
0x1800075c6  jz      short loc_1800075E3
0x1800075c8  mov     dword ptr [rbx+20h], 5
0x1800075cf  lea     rcx, [rax+190h]
0x1800075d6  jmp     short loc_1800075DE
0x1800075d8  mov     [rax], bp
0x1800075db  add     rax, rbp
0x1800075de  cmp     rax, rcx
0x1800075e1  jnz     short loc_1800075D8
0x1800075e3  mov     r9, [rbx+18h]
0x1800075e7  test    r9, r9
0x1800075ea  jz      short loc_18000765B
0x1800075ec  test    esi, esi
0x1800075ee  jz      short loc_180007621
0x1800075f0  mov     rcx, r9
0x1800075f3  movzx   eax, word ptr [rbx+20h]
0x1800075f7  lea     rdx, [rax+rax*4]
0x1800075fb  shl     rdx, 4
0x1800075ff  add     rdx, r9
0x180007602  cmp     r9, rdx
0x180007605  jz      short loc_180007621
0x180007607  mov     r8d, [rbx+10h]
0x18000760b  cmp     [rcx+4], r8d
0x18000760f  jbe     short loc_180007619
0x180007611  mov     eax, [rdi+8]
0x180007614  cmp     [rcx+8], eax
0x180007617  jz      short loc_18000765B
0x180007619  add     rcx, rbp
0x18000761c  cmp     rcx, rdx
0x18000761f  jnz     short loc_18000760B
0x180007621  movzx   eax, word ptr [rbx+22h]
0x180007625  inc     eax
0x180007627  movzx   ecx, word ptr [rbx+20h]
0x18000762b  xor     edx, edx
0x18000762d  div     ecx
0x18000762f  mov     [rbx+22h], dx
0x180007633  mov     rax, [rbx+8]
0x180007637  mov     r8d, 1
0x18000763d  lock xadd [rax], r8d
0x180007642  inc     r8d; unsigned int
0x180007645  movzx   eax, dx
0x180007648  lea     rcx, [rax+rax*4]
0x18000764c  shl     rcx, 4
0x180007650  add     rcx, r9; this
0x180007653  mov     rdx, rdi; struct wil::FailureInfo *
0x180007656  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000765b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007665  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000766c  add     rsp, 20h
0x180007670  pop     r14
0x180007672  pop     rdi
0x180007673  pop     rsi
0x180007674  pop     rbp
0x180007675  pop     rbx
0x180007676  retn
```
