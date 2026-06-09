# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000a4f0`
- end: `0x18000a6f7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a4f0`
- `0x18000a7c0`
- `0x18000a8a4`
- `0x18000ae30`
- `0x18000cb34`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a51a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a51a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a5dc`

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
0x18000a4f0  push    rbx
0x18000a4f2  push    rbp
0x18000a4f3  push    rsi
0x18000a4f4  push    rdi
0x18000a4f5  push    r14
0x18000a4f7  sub     rsp, 20h
0x18000a4fb  mov     r14, r8
0x18000a4fe  mov     rsi, rdx
0x18000a501  mov     rdi, rcx
0x18000a504  mov     byte ptr [rdx], 0
0x18000a507  xor     bpl, bpl
0x18000a50a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a511  test    rbx, rbx
0x18000a514  jz      loc_18000A5B0
0x18000a51a  call    cs:__imp_GetCurrentThreadId
0x18000a520  mov     r9d, eax
0x18000a523  mov     r8d, eax
0x18000a526  shr     r8, 2
0x18000a52a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a534  mul     r8
0x18000a537  shr     rdx, 3
0x18000a53b  lea     rcx, [rdx+rdx*4]
0x18000a53f  add     rcx, rcx
0x18000a542  sub     r8, rcx
0x18000a545  mov     rbx, [rbx+r8*8]
0x18000a549  jmp     short loc_18000A554
0x18000a54b  cmp     [rbx], r9d
0x18000a54e  jz      short loc_18000A5CB
0x18000a550  mov     rbx, [rbx+8]
0x18000a554  test    rbx, rbx
0x18000a557  jnz     short loc_18000A54B
0x18000a559  test    rbx, rbx
0x18000a55c  jz      short loc_18000A5B0
0x18000a55e  cmp     qword ptr [rbx], 0
0x18000a562  jz      short loc_18000A5B0
0x18000a564  mov     [rsi], bpl
0x18000a567  mov     r9, r14; unsigned __int64
0x18000a56a  mov     r8, rsi; char *
0x18000a56d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000a570  mov     rcx, rdi; struct wil::FailureInfo *
0x18000a573  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000a578  test    al, al
0x18000a57a  jz      short loc_18000A580
0x18000a57c  mov     [rdi+48h], rsi
0x18000a580  mov     rbx, [rbx]
0x18000a583  mov     al, [rbx+28h]
0x18000a586  mov     byte ptr [rbx+28h], 1
0x18000a58a  test    al, al
0x18000a58c  jnz     short loc_18000A5A7
0x18000a58e  mov     rcx, [rbx+8]
0x18000a592  mov     rax, [rcx]
0x18000a595  mov     rdx, rdi
0x18000a598  mov     rax, [rax]
0x18000a59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a0  or      bpl, al
0x18000a5a3  mov     byte ptr [rbx+28h], 0
0x18000a5a7  mov     rbx, [rbx+10h]
0x18000a5ab  test    rbx, rbx
0x18000a5ae  jnz     short loc_18000A583
0x18000a5b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000a5b7  test    rax, rax
0x18000a5ba  jz      short loc_18000A5DC
0x18000a5bc  test    bpl, bpl
0x18000a5bf  jnz     short loc_18000A5D1
0x18000a5c1  test    byte ptr [rdi+4], 2
0x18000a5c5  jnz     short loc_18000A5D1
0x18000a5c7  xor     ecx, ecx
0x18000a5c9  jmp     short loc_18000A5D3
0x18000a5cb  add     rbx, 10h
0x18000a5cf  jmp     short loc_18000A559
0x18000a5d1  mov     cl, 1
0x18000a5d3  mov     rdx, rdi
0x18000a5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5db  nop
0x18000a5dc  call    cs:__imp_GetCurrentThreadId
0x18000a5e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a5e8  cmp     ecx, eax
0x18000a5ea  jz      loc_18000A6EC
0x18000a5f0  mov     ecx, 1
0x18000a5f5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000a5fd  inc     ecx; this
0x18000a5ff  cmp     ecx, 4
0x18000a602  jge     loc_18000A6E5
0x18000a608  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a60e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000a613  mov     rbx, rax
0x18000a616  test    rax, rax
0x18000a619  jz      loc_18000A6DB
0x18000a61f  mov     esi, [rax+10h]
0x18000a622  mov     ebp, 50h ; 'P'
0x18000a627  cmp     qword ptr [rax+18h], 0
0x18000a62c  jnz     short loc_18000A663
0x18000a62e  test    esi, esi
0x18000a630  jz      short loc_18000A663
0x18000a632  mov     edx, 190h; dwBytes
0x18000a637  lea     ecx, [rbp-48h]; dwFlags
0x18000a63a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a63f  mov     [rbx+18h], rax
0x18000a643  test    rax, rax
0x18000a646  jz      short loc_18000A663
0x18000a648  mov     dword ptr [rbx+20h], 5
0x18000a64f  lea     rcx, [rax+190h]
0x18000a656  jmp     short loc_18000A65E
0x18000a658  mov     [rax], bp
0x18000a65b  add     rax, rbp
0x18000a65e  cmp     rax, rcx
0x18000a661  jnz     short loc_18000A658
0x18000a663  mov     r9, [rbx+18h]
0x18000a667  test    r9, r9
0x18000a66a  jz      short loc_18000A6DB
0x18000a66c  test    esi, esi
0x18000a66e  jz      short loc_18000A6A1
0x18000a670  mov     rcx, r9
0x18000a673  movzx   eax, word ptr [rbx+20h]
0x18000a677  lea     rdx, [rax+rax*4]
0x18000a67b  shl     rdx, 4
0x18000a67f  add     rdx, r9
0x18000a682  cmp     r9, rdx
0x18000a685  jz      short loc_18000A6A1
0x18000a687  mov     r8d, [rbx+10h]
0x18000a68b  cmp     [rcx+4], r8d
0x18000a68f  jbe     short loc_18000A699
0x18000a691  mov     eax, [rdi+8]
0x18000a694  cmp     [rcx+8], eax
0x18000a697  jz      short loc_18000A6DB
0x18000a699  add     rcx, rbp
0x18000a69c  cmp     rcx, rdx
0x18000a69f  jnz     short loc_18000A68B
0x18000a6a1  movzx   eax, word ptr [rbx+22h]
0x18000a6a5  inc     eax
0x18000a6a7  movzx   ecx, word ptr [rbx+20h]
0x18000a6ab  xor     edx, edx
0x18000a6ad  div     ecx
0x18000a6af  mov     [rbx+22h], dx
0x18000a6b3  mov     rax, [rbx+8]
0x18000a6b7  mov     r8d, 1
0x18000a6bd  lock xadd [rax], r8d
0x18000a6c2  inc     r8d; unsigned int
0x18000a6c5  movzx   eax, dx
0x18000a6c8  lea     rcx, [rax+rax*4]
0x18000a6cc  shl     rcx, 4
0x18000a6d0  add     rcx, r9; this
0x18000a6d3  mov     rdx, rdi; struct wil::FailureInfo *
0x18000a6d6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000a6db  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a6e5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000a6ec  add     rsp, 20h
0x18000a6f0  pop     r14
0x18000a6f2  pop     rdi
0x18000a6f3  pop     rsi
0x18000a6f4  pop     rbp
0x18000a6f5  pop     rbx
0x18000a6f6  retn
```
