# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003fa0`
- end: `0x1800041a6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003fa0`
- `0x180004698`
- `0x18000477c`
- `0x180004fe8`
- `0x180005328`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000408b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000408b`

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
0x180003fa0  push    rbx
0x180003fa2  push    rbp
0x180003fa3  push    rsi
0x180003fa4  push    rdi
0x180003fa5  push    r14
0x180003fa7  sub     rsp, 20h
0x180003fab  mov     byte ptr [rdx], 0
0x180003fae  xor     bpl, bpl
0x180003fb1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003fb8  mov     r14, r8
0x180003fbb  mov     rsi, rdx
0x180003fbe  mov     rdi, rcx
0x180003fc1  test    rbx, rbx
0x180003fc4  jz      loc_180004060
0x180003fca  call    cs:__imp_GetCurrentThreadId
0x180003fd0  mov     r8d, eax
0x180003fd3  mov     r9d, eax
0x180003fd6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003fe0  shr     r8, 2
0x180003fe4  mul     r8
0x180003fe7  shr     rdx, 3
0x180003feb  lea     rcx, [rdx+rdx*4]
0x180003fef  add     rcx, rcx
0x180003ff2  sub     r8, rcx
0x180003ff5  mov     rbx, [rbx+r8*8]
0x180003ff9  jmp     short loc_180004004
0x180003ffb  cmp     [rbx], r9d
0x180003ffe  jz      short loc_18000407B
0x180004000  mov     rbx, [rbx+8]
0x180004004  test    rbx, rbx
0x180004007  jnz     short loc_180003FFB
0x180004009  test    rbx, rbx
0x18000400c  jz      short loc_180004060
0x18000400e  cmp     qword ptr [rbx], 0
0x180004012  jz      short loc_180004060
0x180004014  mov     [rsi], bpl
0x180004017  mov     r9, r14; unsigned __int64
0x18000401a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000401d  mov     r8, rsi; char *
0x180004020  mov     rcx, rdi; struct wil::FailureInfo *
0x180004023  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004028  test    al, al
0x18000402a  jz      short loc_180004030
0x18000402c  mov     [rdi+48h], rsi
0x180004030  mov     rbx, [rbx]
0x180004033  mov     al, [rbx+28h]
0x180004036  mov     byte ptr [rbx+28h], 1
0x18000403a  test    al, al
0x18000403c  jnz     short loc_180004057
0x18000403e  mov     rcx, [rbx+8]
0x180004042  mov     rdx, rdi
0x180004045  mov     rax, [rcx]
0x180004048  mov     rax, [rax]
0x18000404b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004050  or      bpl, al
0x180004053  mov     byte ptr [rbx+28h], 0
0x180004057  mov     rbx, [rbx+10h]
0x18000405b  test    rbx, rbx
0x18000405e  jnz     short loc_180004033
0x180004060  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004067  test    rax, rax
0x18000406a  jz      short loc_18000408B
0x18000406c  test    bpl, bpl
0x18000406f  jnz     short loc_180004081
0x180004071  test    byte ptr [rdi+4], 2
0x180004075  jnz     short loc_180004081
0x180004077  xor     ecx, ecx
0x180004079  jmp     short loc_180004083
0x18000407b  add     rbx, 10h
0x18000407f  jmp     short loc_180004009
0x180004081  mov     cl, 1
0x180004083  mov     rdx, rdi
0x180004086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000408b  call    cs:__imp_GetCurrentThreadId
0x180004091  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004097  cmp     ecx, eax
0x180004099  jz      loc_18000419B
0x18000409f  mov     ecx, 1
0x1800040a4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800040ac  inc     ecx; this
0x1800040ae  cmp     ecx, 4
0x1800040b1  jge     loc_180004194
0x1800040b7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800040bd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800040c2  mov     rbx, rax
0x1800040c5  test    rax, rax
0x1800040c8  jz      loc_18000418A
0x1800040ce  cmp     qword ptr [rax+18h], 0
0x1800040d3  mov     ebp, 50h ; 'P'
0x1800040d8  mov     esi, [rax+10h]
0x1800040db  jnz     short loc_180004112
0x1800040dd  test    esi, esi
0x1800040df  jz      short loc_180004112
0x1800040e1  mov     edx, 190h; dwBytes
0x1800040e6  lea     ecx, [rbp-48h]; dwFlags
0x1800040e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800040ee  mov     [rbx+18h], rax
0x1800040f2  test    rax, rax
0x1800040f5  jz      short loc_180004112
0x1800040f7  mov     dword ptr [rbx+20h], 5
0x1800040fe  lea     rcx, [rax+190h]
0x180004105  jmp     short loc_18000410D
0x180004107  mov     [rax], bp
0x18000410a  add     rax, rbp
0x18000410d  cmp     rax, rcx
0x180004110  jnz     short loc_180004107
0x180004112  mov     r9, [rbx+18h]
0x180004116  test    r9, r9
0x180004119  jz      short loc_18000418A
0x18000411b  test    esi, esi
0x18000411d  jz      short loc_180004150
0x18000411f  movzx   eax, word ptr [rbx+20h]
0x180004123  mov     rcx, r9
0x180004126  lea     rdx, [rax+rax*4]
0x18000412a  shl     rdx, 4
0x18000412e  add     rdx, r9
0x180004131  cmp     r9, rdx
0x180004134  jz      short loc_180004150
0x180004136  mov     r8d, [rbx+10h]
0x18000413a  cmp     [rcx+4], r8d
0x18000413e  jbe     short loc_180004148
0x180004140  mov     eax, [rdi+8]
0x180004143  cmp     [rcx+8], eax
0x180004146  jz      short loc_18000418A
0x180004148  add     rcx, rbp
0x18000414b  cmp     rcx, rdx
0x18000414e  jnz     short loc_18000413A
0x180004150  movzx   eax, word ptr [rbx+22h]
0x180004154  xor     edx, edx
0x180004156  movzx   ecx, word ptr [rbx+20h]
0x18000415a  inc     eax
0x18000415c  div     ecx
0x18000415e  mov     rax, [rbx+8]
0x180004162  mov     r8d, 1
0x180004168  mov     [rbx+22h], dx
0x18000416c  lock xadd [rax], r8d
0x180004171  movzx   eax, dx
0x180004174  inc     r8d; unsigned int
0x180004177  mov     rdx, rdi; struct wil::FailureInfo *
0x18000417a  lea     rcx, [rax+rax*4]
0x18000417e  shl     rcx, 4
0x180004182  add     rcx, r9; this
0x180004185  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000418a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004194  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000419b  add     rsp, 20h
0x18000419f  pop     r14
0x1800041a1  pop     rdi
0x1800041a2  pop     rsi
0x1800041a3  pop     rbp
0x1800041a4  pop     rbx
0x1800041a5  retn
```
