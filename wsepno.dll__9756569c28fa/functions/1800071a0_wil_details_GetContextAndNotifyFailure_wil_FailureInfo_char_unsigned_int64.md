# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800071a0`
- end: `0x1800073a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800071a0`
- `0x180007470`
- `0x180007554`
- `0x1800083d0`
- `0x18000a398`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000728c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000728c`

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
0x1800071a0  push    rbx
0x1800071a2  push    rbp
0x1800071a3  push    rsi
0x1800071a4  push    rdi
0x1800071a5  push    r14
0x1800071a7  sub     rsp, 20h
0x1800071ab  mov     r14, r8
0x1800071ae  mov     rsi, rdx
0x1800071b1  mov     rdi, rcx
0x1800071b4  mov     byte ptr [rdx], 0
0x1800071b7  xor     bpl, bpl
0x1800071ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800071c1  test    rbx, rbx
0x1800071c4  jz      loc_180007260
0x1800071ca  call    cs:__imp_GetCurrentThreadId
0x1800071d0  mov     r9d, eax
0x1800071d3  mov     r8d, eax
0x1800071d6  shr     r8, 2
0x1800071da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800071e4  mul     r8
0x1800071e7  shr     rdx, 3
0x1800071eb  lea     rcx, [rdx+rdx*4]
0x1800071ef  add     rcx, rcx
0x1800071f2  sub     r8, rcx
0x1800071f5  mov     rbx, [rbx+r8*8]
0x1800071f9  jmp     short loc_180007204
0x1800071fb  cmp     [rbx], r9d
0x1800071fe  jz      short loc_18000727B
0x180007200  mov     rbx, [rbx+8]
0x180007204  test    rbx, rbx
0x180007207  jnz     short loc_1800071FB
0x180007209  test    rbx, rbx
0x18000720c  jz      short loc_180007260
0x18000720e  cmp     qword ptr [rbx], 0
0x180007212  jz      short loc_180007260
0x180007214  mov     [rsi], bpl
0x180007217  mov     r9, r14; unsigned __int64
0x18000721a  mov     r8, rsi; char *
0x18000721d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007220  mov     rcx, rdi; struct wil::FailureInfo *
0x180007223  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007228  test    al, al
0x18000722a  jz      short loc_180007230
0x18000722c  mov     [rdi+48h], rsi
0x180007230  mov     rbx, [rbx]
0x180007233  mov     al, [rbx+28h]
0x180007236  mov     byte ptr [rbx+28h], 1
0x18000723a  test    al, al
0x18000723c  jnz     short loc_180007257
0x18000723e  mov     rcx, [rbx+8]
0x180007242  mov     rax, [rcx]
0x180007245  mov     rdx, rdi
0x180007248  mov     rax, [rax]
0x18000724b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007250  or      bpl, al
0x180007253  mov     byte ptr [rbx+28h], 0
0x180007257  mov     rbx, [rbx+10h]
0x18000725b  test    rbx, rbx
0x18000725e  jnz     short loc_180007233
0x180007260  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007267  test    rax, rax
0x18000726a  jz      short loc_18000728C
0x18000726c  test    bpl, bpl
0x18000726f  jnz     short loc_180007281
0x180007271  test    byte ptr [rdi+4], 2
0x180007275  jnz     short loc_180007281
0x180007277  xor     ecx, ecx
0x180007279  jmp     short loc_180007283
0x18000727b  add     rbx, 10h
0x18000727f  jmp     short loc_180007209
0x180007281  mov     cl, 1
0x180007283  mov     rdx, rdi
0x180007286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000728b  nop
0x18000728c  call    cs:__imp_GetCurrentThreadId
0x180007292  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007298  cmp     ecx, eax
0x18000729a  jz      loc_18000739C
0x1800072a0  mov     ecx, 1
0x1800072a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800072ad  inc     ecx; this
0x1800072af  cmp     ecx, 4
0x1800072b2  jge     loc_180007395
0x1800072b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800072be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800072c3  mov     rbx, rax
0x1800072c6  test    rax, rax
0x1800072c9  jz      loc_18000738B
0x1800072cf  mov     esi, [rax+10h]
0x1800072d2  mov     ebp, 50h ; 'P'
0x1800072d7  cmp     qword ptr [rax+18h], 0
0x1800072dc  jnz     short loc_180007313
0x1800072de  test    esi, esi
0x1800072e0  jz      short loc_180007313
0x1800072e2  mov     edx, 190h; dwBytes
0x1800072e7  lea     ecx, [rbp-48h]; dwFlags
0x1800072ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800072ef  mov     [rbx+18h], rax
0x1800072f3  test    rax, rax
0x1800072f6  jz      short loc_180007313
0x1800072f8  mov     dword ptr [rbx+20h], 5
0x1800072ff  lea     rcx, [rax+190h]
0x180007306  jmp     short loc_18000730E
0x180007308  mov     [rax], bp
0x18000730b  add     rax, rbp
0x18000730e  cmp     rax, rcx
0x180007311  jnz     short loc_180007308
0x180007313  mov     r9, [rbx+18h]
0x180007317  test    r9, r9
0x18000731a  jz      short loc_18000738B
0x18000731c  test    esi, esi
0x18000731e  jz      short loc_180007351
0x180007320  mov     rcx, r9
0x180007323  movzx   eax, word ptr [rbx+20h]
0x180007327  lea     rdx, [rax+rax*4]
0x18000732b  shl     rdx, 4
0x18000732f  add     rdx, r9
0x180007332  cmp     r9, rdx
0x180007335  jz      short loc_180007351
0x180007337  mov     r8d, [rbx+10h]
0x18000733b  cmp     [rcx+4], r8d
0x18000733f  jbe     short loc_180007349
0x180007341  mov     eax, [rdi+8]
0x180007344  cmp     [rcx+8], eax
0x180007347  jz      short loc_18000738B
0x180007349  add     rcx, rbp
0x18000734c  cmp     rcx, rdx
0x18000734f  jnz     short loc_18000733B
0x180007351  movzx   eax, word ptr [rbx+22h]
0x180007355  inc     eax
0x180007357  movzx   ecx, word ptr [rbx+20h]
0x18000735b  xor     edx, edx
0x18000735d  div     ecx
0x18000735f  mov     [rbx+22h], dx
0x180007363  mov     rax, [rbx+8]
0x180007367  mov     r8d, 1
0x18000736d  lock xadd [rax], r8d
0x180007372  inc     r8d; unsigned int
0x180007375  movzx   eax, dx
0x180007378  lea     rcx, [rax+rax*4]
0x18000737c  shl     rcx, 4
0x180007380  add     rcx, r9; this
0x180007383  mov     rdx, rdi; struct wil::FailureInfo *
0x180007386  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000738b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007395  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000739c  add     rsp, 20h
0x1800073a0  pop     r14
0x1800073a2  pop     rdi
0x1800073a3  pop     rsi
0x1800073a4  pop     rbp
0x1800073a5  pop     rbx
0x1800073a6  retn
```
