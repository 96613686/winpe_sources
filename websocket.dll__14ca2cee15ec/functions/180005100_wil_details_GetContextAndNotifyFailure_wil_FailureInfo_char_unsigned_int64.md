# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005100`
- end: `0x180005306`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005100`
- `0x1800057f8`
- `0x1800058dc`
- `0x180006678`
- `0x180007c88`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000512a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000512a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051eb`

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
0x180005100  push    rbx
0x180005102  push    rbp
0x180005103  push    rsi
0x180005104  push    rdi
0x180005105  push    r14
0x180005107  sub     rsp, 20h
0x18000510b  mov     byte ptr [rdx], 0
0x18000510e  xor     bpl, bpl
0x180005111  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005118  mov     r14, r8
0x18000511b  mov     rsi, rdx
0x18000511e  mov     rdi, rcx
0x180005121  test    rbx, rbx
0x180005124  jz      loc_1800051C0
0x18000512a  call    cs:__imp_GetCurrentThreadId
0x180005130  mov     r8d, eax
0x180005133  mov     r9d, eax
0x180005136  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005140  shr     r8, 2
0x180005144  mul     r8
0x180005147  shr     rdx, 3
0x18000514b  lea     rcx, [rdx+rdx*4]
0x18000514f  add     rcx, rcx
0x180005152  sub     r8, rcx
0x180005155  mov     rbx, [rbx+r8*8]
0x180005159  jmp     short loc_180005164
0x18000515b  cmp     [rbx], r9d
0x18000515e  jz      short loc_1800051DB
0x180005160  mov     rbx, [rbx+8]
0x180005164  test    rbx, rbx
0x180005167  jnz     short loc_18000515B
0x180005169  test    rbx, rbx
0x18000516c  jz      short loc_1800051C0
0x18000516e  cmp     qword ptr [rbx], 0
0x180005172  jz      short loc_1800051C0
0x180005174  mov     [rsi], bpl
0x180005177  mov     r9, r14; unsigned __int64
0x18000517a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000517d  mov     r8, rsi; char *
0x180005180  mov     rcx, rdi; struct wil::FailureInfo *
0x180005183  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005188  test    al, al
0x18000518a  jz      short loc_180005190
0x18000518c  mov     [rdi+48h], rsi
0x180005190  mov     rbx, [rbx]
0x180005193  mov     al, [rbx+28h]
0x180005196  mov     byte ptr [rbx+28h], 1
0x18000519a  test    al, al
0x18000519c  jnz     short loc_1800051B7
0x18000519e  mov     rcx, [rbx+8]
0x1800051a2  mov     rdx, rdi
0x1800051a5  mov     rax, [rcx]
0x1800051a8  mov     rax, [rax]
0x1800051ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b0  or      bpl, al
0x1800051b3  mov     byte ptr [rbx+28h], 0
0x1800051b7  mov     rbx, [rbx+10h]
0x1800051bb  test    rbx, rbx
0x1800051be  jnz     short loc_180005193
0x1800051c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800051c7  test    rax, rax
0x1800051ca  jz      short loc_1800051EB
0x1800051cc  test    bpl, bpl
0x1800051cf  jnz     short loc_1800051E1
0x1800051d1  test    byte ptr [rdi+4], 2
0x1800051d5  jnz     short loc_1800051E1
0x1800051d7  xor     ecx, ecx
0x1800051d9  jmp     short loc_1800051E3
0x1800051db  add     rbx, 10h
0x1800051df  jmp     short loc_180005169
0x1800051e1  mov     cl, 1
0x1800051e3  mov     rdx, rdi
0x1800051e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051eb  call    cs:__imp_GetCurrentThreadId
0x1800051f1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800051f7  cmp     ecx, eax
0x1800051f9  jz      loc_1800052FB
0x1800051ff  mov     ecx, 1
0x180005204  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000520c  inc     ecx; this
0x18000520e  cmp     ecx, 4
0x180005211  jge     loc_1800052F4
0x180005217  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000521d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005222  mov     rbx, rax
0x180005225  test    rax, rax
0x180005228  jz      loc_1800052EA
0x18000522e  cmp     qword ptr [rax+18h], 0
0x180005233  mov     ebp, 50h ; 'P'
0x180005238  mov     esi, [rax+10h]
0x18000523b  jnz     short loc_180005272
0x18000523d  test    esi, esi
0x18000523f  jz      short loc_180005272
0x180005241  mov     edx, 190h; dwBytes
0x180005246  lea     ecx, [rbp-48h]; dwFlags
0x180005249  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000524e  mov     [rbx+18h], rax
0x180005252  test    rax, rax
0x180005255  jz      short loc_180005272
0x180005257  mov     dword ptr [rbx+20h], 5
0x18000525e  lea     rcx, [rax+190h]
0x180005265  jmp     short loc_18000526D
0x180005267  mov     [rax], bp
0x18000526a  add     rax, rbp
0x18000526d  cmp     rax, rcx
0x180005270  jnz     short loc_180005267
0x180005272  mov     r9, [rbx+18h]
0x180005276  test    r9, r9
0x180005279  jz      short loc_1800052EA
0x18000527b  test    esi, esi
0x18000527d  jz      short loc_1800052B0
0x18000527f  movzx   eax, word ptr [rbx+20h]
0x180005283  mov     rcx, r9
0x180005286  lea     rdx, [rax+rax*4]
0x18000528a  shl     rdx, 4
0x18000528e  add     rdx, r9
0x180005291  cmp     r9, rdx
0x180005294  jz      short loc_1800052B0
0x180005296  mov     r8d, [rbx+10h]
0x18000529a  cmp     [rcx+4], r8d
0x18000529e  jbe     short loc_1800052A8
0x1800052a0  mov     eax, [rdi+8]
0x1800052a3  cmp     [rcx+8], eax
0x1800052a6  jz      short loc_1800052EA
0x1800052a8  add     rcx, rbp
0x1800052ab  cmp     rcx, rdx
0x1800052ae  jnz     short loc_18000529A
0x1800052b0  movzx   eax, word ptr [rbx+22h]
0x1800052b4  xor     edx, edx
0x1800052b6  movzx   ecx, word ptr [rbx+20h]
0x1800052ba  inc     eax
0x1800052bc  div     ecx
0x1800052be  mov     rax, [rbx+8]
0x1800052c2  mov     r8d, 1
0x1800052c8  mov     [rbx+22h], dx
0x1800052cc  lock xadd [rax], r8d
0x1800052d1  movzx   eax, dx
0x1800052d4  inc     r8d; unsigned int
0x1800052d7  mov     rdx, rdi; struct wil::FailureInfo *
0x1800052da  lea     rcx, [rax+rax*4]
0x1800052de  shl     rcx, 4
0x1800052e2  add     rcx, r9; this
0x1800052e5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800052ea  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800052f4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800052fb  add     rsp, 20h
0x1800052ff  pop     r14
0x180005301  pop     rdi
0x180005302  pop     rsi
0x180005303  pop     rbp
0x180005304  pop     rbx
0x180005305  retn
```
