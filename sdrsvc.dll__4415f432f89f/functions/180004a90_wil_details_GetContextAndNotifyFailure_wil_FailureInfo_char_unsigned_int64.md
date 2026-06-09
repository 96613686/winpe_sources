# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004a90`
- end: `0x180004c96`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004a90`
- `0x180005188`
- `0x18000526c`
- `0x180005ce8`
- `0x1800072f8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004aba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004aba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b7b`

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
0x180004a90  push    rbx
0x180004a92  push    rbp
0x180004a93  push    rsi
0x180004a94  push    rdi
0x180004a95  push    r14
0x180004a97  sub     rsp, 20h
0x180004a9b  mov     byte ptr [rdx], 0
0x180004a9e  xor     bpl, bpl
0x180004aa1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004aa8  mov     r14, r8
0x180004aab  mov     rsi, rdx
0x180004aae  mov     rdi, rcx
0x180004ab1  test    rbx, rbx
0x180004ab4  jz      loc_180004B50
0x180004aba  call    cs:__imp_GetCurrentThreadId
0x180004ac0  mov     r8d, eax
0x180004ac3  mov     r9d, eax
0x180004ac6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004ad0  shr     r8, 2
0x180004ad4  mul     r8
0x180004ad7  shr     rdx, 3
0x180004adb  lea     rcx, [rdx+rdx*4]
0x180004adf  add     rcx, rcx
0x180004ae2  sub     r8, rcx
0x180004ae5  mov     rbx, [rbx+r8*8]
0x180004ae9  jmp     short loc_180004AF4
0x180004aeb  cmp     [rbx], r9d
0x180004aee  jz      short loc_180004B6B
0x180004af0  mov     rbx, [rbx+8]
0x180004af4  test    rbx, rbx
0x180004af7  jnz     short loc_180004AEB
0x180004af9  test    rbx, rbx
0x180004afc  jz      short loc_180004B50
0x180004afe  cmp     qword ptr [rbx], 0
0x180004b02  jz      short loc_180004B50
0x180004b04  mov     [rsi], bpl
0x180004b07  mov     r9, r14; unsigned __int64
0x180004b0a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004b0d  mov     r8, rsi; char *
0x180004b10  mov     rcx, rdi; struct wil::FailureInfo *
0x180004b13  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004b18  test    al, al
0x180004b1a  jz      short loc_180004B20
0x180004b1c  mov     [rdi+48h], rsi
0x180004b20  mov     rbx, [rbx]
0x180004b23  mov     al, [rbx+28h]
0x180004b26  mov     byte ptr [rbx+28h], 1
0x180004b2a  test    al, al
0x180004b2c  jnz     short loc_180004B47
0x180004b2e  mov     rcx, [rbx+8]
0x180004b32  mov     rdx, rdi
0x180004b35  mov     rax, [rcx]
0x180004b38  mov     rax, [rax]
0x180004b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b40  or      bpl, al
0x180004b43  mov     byte ptr [rbx+28h], 0
0x180004b47  mov     rbx, [rbx+10h]
0x180004b4b  test    rbx, rbx
0x180004b4e  jnz     short loc_180004B23
0x180004b50  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004b57  test    rax, rax
0x180004b5a  jz      short loc_180004B7B
0x180004b5c  test    bpl, bpl
0x180004b5f  jnz     short loc_180004B71
0x180004b61  test    byte ptr [rdi+4], 2
0x180004b65  jnz     short loc_180004B71
0x180004b67  xor     ecx, ecx
0x180004b69  jmp     short loc_180004B73
0x180004b6b  add     rbx, 10h
0x180004b6f  jmp     short loc_180004AF9
0x180004b71  mov     cl, 1
0x180004b73  mov     rdx, rdi
0x180004b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7b  call    cs:__imp_GetCurrentThreadId
0x180004b81  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b87  cmp     ecx, eax
0x180004b89  jz      loc_180004C8B
0x180004b8f  mov     ecx, 1
0x180004b94  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004b9c  inc     ecx; this
0x180004b9e  cmp     ecx, 4
0x180004ba1  jge     loc_180004C84
0x180004ba7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004bad  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004bb2  mov     rbx, rax
0x180004bb5  test    rax, rax
0x180004bb8  jz      loc_180004C7A
0x180004bbe  cmp     qword ptr [rax+18h], 0
0x180004bc3  mov     ebp, 50h ; 'P'
0x180004bc8  mov     esi, [rax+10h]
0x180004bcb  jnz     short loc_180004C02
0x180004bcd  test    esi, esi
0x180004bcf  jz      short loc_180004C02
0x180004bd1  mov     edx, 190h; dwBytes
0x180004bd6  lea     ecx, [rbp-48h]; dwFlags
0x180004bd9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004bde  mov     [rbx+18h], rax
0x180004be2  test    rax, rax
0x180004be5  jz      short loc_180004C02
0x180004be7  mov     dword ptr [rbx+20h], 5
0x180004bee  lea     rcx, [rax+190h]
0x180004bf5  jmp     short loc_180004BFD
0x180004bf7  mov     [rax], bp
0x180004bfa  add     rax, rbp
0x180004bfd  cmp     rax, rcx
0x180004c00  jnz     short loc_180004BF7
0x180004c02  mov     r9, [rbx+18h]
0x180004c06  test    r9, r9
0x180004c09  jz      short loc_180004C7A
0x180004c0b  test    esi, esi
0x180004c0d  jz      short loc_180004C40
0x180004c0f  movzx   eax, word ptr [rbx+20h]
0x180004c13  mov     rcx, r9
0x180004c16  lea     rdx, [rax+rax*4]
0x180004c1a  shl     rdx, 4
0x180004c1e  add     rdx, r9
0x180004c21  cmp     r9, rdx
0x180004c24  jz      short loc_180004C40
0x180004c26  mov     r8d, [rbx+10h]
0x180004c2a  cmp     [rcx+4], r8d
0x180004c2e  jbe     short loc_180004C38
0x180004c30  mov     eax, [rdi+8]
0x180004c33  cmp     [rcx+8], eax
0x180004c36  jz      short loc_180004C7A
0x180004c38  add     rcx, rbp
0x180004c3b  cmp     rcx, rdx
0x180004c3e  jnz     short loc_180004C2A
0x180004c40  movzx   eax, word ptr [rbx+22h]
0x180004c44  xor     edx, edx
0x180004c46  movzx   ecx, word ptr [rbx+20h]
0x180004c4a  inc     eax
0x180004c4c  div     ecx
0x180004c4e  mov     rax, [rbx+8]
0x180004c52  mov     r8d, 1
0x180004c58  mov     [rbx+22h], dx
0x180004c5c  lock xadd [rax], r8d
0x180004c61  movzx   eax, dx
0x180004c64  inc     r8d; unsigned int
0x180004c67  mov     rdx, rdi; struct wil::FailureInfo *
0x180004c6a  lea     rcx, [rax+rax*4]
0x180004c6e  shl     rcx, 4
0x180004c72  add     rcx, r9; this
0x180004c75  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004c7a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004c84  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004c8b  add     rsp, 20h
0x180004c8f  pop     r14
0x180004c91  pop     rdi
0x180004c92  pop     rsi
0x180004c93  pop     rbp
0x180004c94  pop     rbx
0x180004c95  retn
```
