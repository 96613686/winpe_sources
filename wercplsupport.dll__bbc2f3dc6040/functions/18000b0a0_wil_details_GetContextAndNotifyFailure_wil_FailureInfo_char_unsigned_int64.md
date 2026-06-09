# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b0a0`
- end: `0x18000b2a6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000b0a0`
- `0x18000b784`
- `0x18000b868`
- `0x18000c354`
- `0x18000d9a4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b18b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b18b`

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
0x18000b0a0  push    rbx
0x18000b0a2  push    rbp
0x18000b0a3  push    rsi
0x18000b0a4  push    rdi
0x18000b0a5  push    r14
0x18000b0a7  sub     rsp, 20h
0x18000b0ab  mov     byte ptr [rdx], 0
0x18000b0ae  xor     bpl, bpl
0x18000b0b1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b0b8  mov     r14, r8
0x18000b0bb  mov     rsi, rdx
0x18000b0be  mov     rdi, rcx
0x18000b0c1  test    rbx, rbx
0x18000b0c4  jz      loc_18000B160
0x18000b0ca  call    cs:__imp_GetCurrentThreadId
0x18000b0d0  mov     r8d, eax
0x18000b0d3  mov     r9d, eax
0x18000b0d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b0e0  shr     r8, 2
0x18000b0e4  mul     r8
0x18000b0e7  shr     rdx, 3
0x18000b0eb  lea     rcx, [rdx+rdx*4]
0x18000b0ef  add     rcx, rcx
0x18000b0f2  sub     r8, rcx
0x18000b0f5  mov     rbx, [rbx+r8*8]
0x18000b0f9  jmp     short loc_18000B104
0x18000b0fb  cmp     [rbx], r9d
0x18000b0fe  jz      short loc_18000B17B
0x18000b100  mov     rbx, [rbx+8]
0x18000b104  test    rbx, rbx
0x18000b107  jnz     short loc_18000B0FB
0x18000b109  test    rbx, rbx
0x18000b10c  jz      short loc_18000B160
0x18000b10e  cmp     qword ptr [rbx], 0
0x18000b112  jz      short loc_18000B160
0x18000b114  mov     [rsi], bpl
0x18000b117  mov     r9, r14; unsigned __int64
0x18000b11a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b11d  mov     r8, rsi; char *
0x18000b120  mov     rcx, rdi; struct wil::FailureInfo *
0x18000b123  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b128  test    al, al
0x18000b12a  jz      short loc_18000B130
0x18000b12c  mov     [rdi+48h], rsi
0x18000b130  mov     rbx, [rbx]
0x18000b133  mov     al, [rbx+28h]
0x18000b136  mov     byte ptr [rbx+28h], 1
0x18000b13a  test    al, al
0x18000b13c  jnz     short loc_18000B157
0x18000b13e  mov     rcx, [rbx+8]
0x18000b142  mov     rdx, rdi
0x18000b145  mov     rax, [rcx]
0x18000b148  mov     rax, [rax]
0x18000b14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b150  or      bpl, al
0x18000b153  mov     byte ptr [rbx+28h], 0
0x18000b157  mov     rbx, [rbx+10h]
0x18000b15b  test    rbx, rbx
0x18000b15e  jnz     short loc_18000B133
0x18000b160  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b167  test    rax, rax
0x18000b16a  jz      short loc_18000B18B
0x18000b16c  test    bpl, bpl
0x18000b16f  jnz     short loc_18000B181
0x18000b171  test    byte ptr [rdi+4], 2
0x18000b175  jnz     short loc_18000B181
0x18000b177  xor     ecx, ecx
0x18000b179  jmp     short loc_18000B183
0x18000b17b  add     rbx, 10h
0x18000b17f  jmp     short loc_18000B109
0x18000b181  mov     cl, 1
0x18000b183  mov     rdx, rdi
0x18000b186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18b  call    cs:__imp_GetCurrentThreadId
0x18000b191  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b197  cmp     ecx, eax
0x18000b199  jz      loc_18000B29B
0x18000b19f  mov     ecx, 1
0x18000b1a4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b1ac  inc     ecx; this
0x18000b1ae  cmp     ecx, 4
0x18000b1b1  jge     loc_18000B294
0x18000b1b7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b1bd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b1c2  mov     rbx, rax
0x18000b1c5  test    rax, rax
0x18000b1c8  jz      loc_18000B28A
0x18000b1ce  cmp     qword ptr [rax+18h], 0
0x18000b1d3  mov     ebp, 50h ; 'P'
0x18000b1d8  mov     esi, [rax+10h]
0x18000b1db  jnz     short loc_18000B212
0x18000b1dd  test    esi, esi
0x18000b1df  jz      short loc_18000B212
0x18000b1e1  mov     edx, 190h; dwBytes
0x18000b1e6  lea     ecx, [rbp-48h]; dwFlags
0x18000b1e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b1ee  mov     [rbx+18h], rax
0x18000b1f2  test    rax, rax
0x18000b1f5  jz      short loc_18000B212
0x18000b1f7  mov     dword ptr [rbx+20h], 5
0x18000b1fe  lea     rcx, [rax+190h]
0x18000b205  jmp     short loc_18000B20D
0x18000b207  mov     [rax], bp
0x18000b20a  add     rax, rbp
0x18000b20d  cmp     rax, rcx
0x18000b210  jnz     short loc_18000B207
0x18000b212  mov     r9, [rbx+18h]
0x18000b216  test    r9, r9
0x18000b219  jz      short loc_18000B28A
0x18000b21b  test    esi, esi
0x18000b21d  jz      short loc_18000B250
0x18000b21f  movzx   eax, word ptr [rbx+20h]
0x18000b223  mov     rcx, r9
0x18000b226  lea     rdx, [rax+rax*4]
0x18000b22a  shl     rdx, 4
0x18000b22e  add     rdx, r9
0x18000b231  cmp     r9, rdx
0x18000b234  jz      short loc_18000B250
0x18000b236  mov     r8d, [rbx+10h]
0x18000b23a  cmp     [rcx+4], r8d
0x18000b23e  jbe     short loc_18000B248
0x18000b240  mov     eax, [rdi+8]
0x18000b243  cmp     [rcx+8], eax
0x18000b246  jz      short loc_18000B28A
0x18000b248  add     rcx, rbp
0x18000b24b  cmp     rcx, rdx
0x18000b24e  jnz     short loc_18000B23A
0x18000b250  movzx   eax, word ptr [rbx+22h]
0x18000b254  xor     edx, edx
0x18000b256  movzx   ecx, word ptr [rbx+20h]
0x18000b25a  inc     eax
0x18000b25c  div     ecx
0x18000b25e  mov     rax, [rbx+8]
0x18000b262  mov     r8d, 1
0x18000b268  mov     [rbx+22h], dx
0x18000b26c  lock xadd [rax], r8d
0x18000b271  movzx   eax, dx
0x18000b274  inc     r8d; unsigned int
0x18000b277  mov     rdx, rdi; struct wil::FailureInfo *
0x18000b27a  lea     rcx, [rax+rax*4]
0x18000b27e  shl     rcx, 4
0x18000b282  add     rcx, r9; this
0x18000b285  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b28a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b294  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b29b  add     rsp, 20h
0x18000b29f  pop     r14
0x18000b2a1  pop     rdi
0x18000b2a2  pop     rsi
0x18000b2a3  pop     rbp
0x18000b2a4  pop     rbx
0x18000b2a5  retn
```
