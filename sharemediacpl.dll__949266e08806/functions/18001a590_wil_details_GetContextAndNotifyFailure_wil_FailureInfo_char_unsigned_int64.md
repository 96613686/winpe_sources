# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001a590`
- end: `0x18001a796`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001a590`
- `0x18001ad68`
- `0x18001ae4c`
- `0x18001ba20`
- `0x18001c370`
- `0x18001e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a5ba`
- `KERNEL32!GetCurrentThreadId` at `0x18001a67b`
- `KERNEL32!GetCurrentThreadId` at `0x18001a5ba`
- `KERNEL32!GetCurrentThreadId` at `0x18001a67b`

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
0x18001a590  push    rbx
0x18001a592  push    rbp
0x18001a593  push    rsi
0x18001a594  push    rdi
0x18001a595  push    r14
0x18001a597  sub     rsp, 20h
0x18001a59b  mov     byte ptr [rdx], 0
0x18001a59e  xor     bpl, bpl
0x18001a5a1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001a5a8  mov     r14, r8
0x18001a5ab  mov     rsi, rdx
0x18001a5ae  mov     rdi, rcx
0x18001a5b1  test    rbx, rbx
0x18001a5b4  jz      loc_18001A650
0x18001a5ba  call    cs:__imp_GetCurrentThreadId
0x18001a5c0  mov     r8d, eax
0x18001a5c3  mov     r9d, eax
0x18001a5c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001a5d0  shr     r8, 2
0x18001a5d4  mul     r8
0x18001a5d7  shr     rdx, 3
0x18001a5db  lea     rcx, [rdx+rdx*4]
0x18001a5df  add     rcx, rcx
0x18001a5e2  sub     r8, rcx
0x18001a5e5  mov     rbx, [rbx+r8*8]
0x18001a5e9  jmp     short loc_18001A5F4
0x18001a5eb  cmp     [rbx], r9d
0x18001a5ee  jz      short loc_18001A66B
0x18001a5f0  mov     rbx, [rbx+8]
0x18001a5f4  test    rbx, rbx
0x18001a5f7  jnz     short loc_18001A5EB
0x18001a5f9  test    rbx, rbx
0x18001a5fc  jz      short loc_18001A650
0x18001a5fe  cmp     qword ptr [rbx], 0
0x18001a602  jz      short loc_18001A650
0x18001a604  mov     [rsi], bpl
0x18001a607  mov     r9, r14; unsigned __int64
0x18001a60a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18001a60d  mov     r8, rsi; char *
0x18001a610  mov     rcx, rdi; struct wil::FailureInfo *
0x18001a613  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001a618  test    al, al
0x18001a61a  jz      short loc_18001A620
0x18001a61c  mov     [rdi+48h], rsi
0x18001a620  mov     rbx, [rbx]
0x18001a623  mov     al, [rbx+28h]
0x18001a626  mov     byte ptr [rbx+28h], 1
0x18001a62a  test    al, al
0x18001a62c  jnz     short loc_18001A647
0x18001a62e  mov     rcx, [rbx+8]
0x18001a632  mov     rdx, rdi
0x18001a635  mov     rax, [rcx]
0x18001a638  mov     rax, [rax]
0x18001a63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a640  or      bpl, al
0x18001a643  mov     byte ptr [rbx+28h], 0
0x18001a647  mov     rbx, [rbx+10h]
0x18001a64b  test    rbx, rbx
0x18001a64e  jnz     short loc_18001A623
0x18001a650  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001a657  test    rax, rax
0x18001a65a  jz      short loc_18001A67B
0x18001a65c  test    bpl, bpl
0x18001a65f  jnz     short loc_18001A671
0x18001a661  test    byte ptr [rdi+4], 2
0x18001a665  jnz     short loc_18001A671
0x18001a667  xor     ecx, ecx
0x18001a669  jmp     short loc_18001A673
0x18001a66b  add     rbx, 10h
0x18001a66f  jmp     short loc_18001A5F9
0x18001a671  mov     cl, 1
0x18001a673  mov     rdx, rdi
0x18001a676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a67b  call    cs:__imp_GetCurrentThreadId
0x18001a681  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001a687  cmp     ecx, eax
0x18001a689  jz      loc_18001A78B
0x18001a68f  mov     ecx, 1
0x18001a694  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001a69c  inc     ecx; this
0x18001a69e  cmp     ecx, 4
0x18001a6a1  jge     loc_18001A784
0x18001a6a7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001a6ad  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18001a6b2  mov     rbx, rax
0x18001a6b5  test    rax, rax
0x18001a6b8  jz      loc_18001A77A
0x18001a6be  cmp     qword ptr [rax+18h], 0
0x18001a6c3  mov     ebp, 50h ; 'P'
0x18001a6c8  mov     esi, [rax+10h]
0x18001a6cb  jnz     short loc_18001A702
0x18001a6cd  test    esi, esi
0x18001a6cf  jz      short loc_18001A702
0x18001a6d1  mov     edx, 190h; dwBytes
0x18001a6d6  lea     ecx, [rbp-48h]; dwFlags
0x18001a6d9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001a6de  mov     [rbx+18h], rax
0x18001a6e2  test    rax, rax
0x18001a6e5  jz      short loc_18001A702
0x18001a6e7  mov     dword ptr [rbx+20h], 5
0x18001a6ee  lea     rcx, [rax+190h]
0x18001a6f5  jmp     short loc_18001A6FD
0x18001a6f7  mov     [rax], bp
0x18001a6fa  add     rax, rbp
0x18001a6fd  cmp     rax, rcx
0x18001a700  jnz     short loc_18001A6F7
0x18001a702  mov     r9, [rbx+18h]
0x18001a706  test    r9, r9
0x18001a709  jz      short loc_18001A77A
0x18001a70b  test    esi, esi
0x18001a70d  jz      short loc_18001A740
0x18001a70f  movzx   eax, word ptr [rbx+20h]
0x18001a713  mov     rcx, r9
0x18001a716  lea     rdx, [rax+rax*4]
0x18001a71a  shl     rdx, 4
0x18001a71e  add     rdx, r9
0x18001a721  cmp     r9, rdx
0x18001a724  jz      short loc_18001A740
0x18001a726  mov     r8d, [rbx+10h]
0x18001a72a  cmp     [rcx+4], r8d
0x18001a72e  jbe     short loc_18001A738
0x18001a730  mov     eax, [rdi+8]
0x18001a733  cmp     [rcx+8], eax
0x18001a736  jz      short loc_18001A77A
0x18001a738  add     rcx, rbp
0x18001a73b  cmp     rcx, rdx
0x18001a73e  jnz     short loc_18001A72A
0x18001a740  movzx   eax, word ptr [rbx+22h]
0x18001a744  xor     edx, edx
0x18001a746  movzx   ecx, word ptr [rbx+20h]
0x18001a74a  inc     eax
0x18001a74c  div     ecx
0x18001a74e  mov     rax, [rbx+8]
0x18001a752  mov     r8d, 1
0x18001a758  mov     [rbx+22h], dx
0x18001a75c  lock xadd [rax], r8d
0x18001a761  movzx   eax, dx
0x18001a764  inc     r8d; unsigned int
0x18001a767  mov     rdx, rdi; struct wil::FailureInfo *
0x18001a76a  lea     rcx, [rax+rax*4]
0x18001a76e  shl     rcx, 4
0x18001a772  add     rcx, r9; this
0x18001a775  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001a77a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001a784  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001a78b  add     rsp, 20h
0x18001a78f  pop     r14
0x18001a791  pop     rdi
0x18001a792  pop     rsi
0x18001a793  pop     rbp
0x18001a794  pop     rbx
0x18001a795  retn
```
