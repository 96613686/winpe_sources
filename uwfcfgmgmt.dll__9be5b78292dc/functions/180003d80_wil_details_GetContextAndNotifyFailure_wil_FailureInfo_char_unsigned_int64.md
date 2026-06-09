# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003d80`
- end: `0x180003f86`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003d80`
- `0x180004478`
- `0x18000455c`
- `0x180004dd8`
- `0x180005188`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003daa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003daa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e6b`

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
0x180003d80  push    rbx
0x180003d82  push    rbp
0x180003d83  push    rsi
0x180003d84  push    rdi
0x180003d85  push    r14
0x180003d87  sub     rsp, 20h
0x180003d8b  mov     byte ptr [rdx], 0
0x180003d8e  xor     bpl, bpl
0x180003d91  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003d98  mov     r14, r8
0x180003d9b  mov     rsi, rdx
0x180003d9e  mov     rdi, rcx
0x180003da1  test    rbx, rbx
0x180003da4  jz      loc_180003E40
0x180003daa  call    cs:__imp_GetCurrentThreadId
0x180003db0  mov     r8d, eax
0x180003db3  mov     r9d, eax
0x180003db6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003dc0  shr     r8, 2
0x180003dc4  mul     r8
0x180003dc7  shr     rdx, 3
0x180003dcb  lea     rcx, [rdx+rdx*4]
0x180003dcf  add     rcx, rcx
0x180003dd2  sub     r8, rcx
0x180003dd5  mov     rbx, [rbx+r8*8]
0x180003dd9  jmp     short loc_180003DE4
0x180003ddb  cmp     [rbx], r9d
0x180003dde  jz      short loc_180003E5B
0x180003de0  mov     rbx, [rbx+8]
0x180003de4  test    rbx, rbx
0x180003de7  jnz     short loc_180003DDB
0x180003de9  test    rbx, rbx
0x180003dec  jz      short loc_180003E40
0x180003dee  cmp     qword ptr [rbx], 0
0x180003df2  jz      short loc_180003E40
0x180003df4  mov     [rsi], bpl
0x180003df7  mov     r9, r14; unsigned __int64
0x180003dfa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003dfd  mov     r8, rsi; char *
0x180003e00  mov     rcx, rdi; struct wil::FailureInfo *
0x180003e03  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003e08  test    al, al
0x180003e0a  jz      short loc_180003E10
0x180003e0c  mov     [rdi+48h], rsi
0x180003e10  mov     rbx, [rbx]
0x180003e13  mov     al, [rbx+28h]
0x180003e16  mov     byte ptr [rbx+28h], 1
0x180003e1a  test    al, al
0x180003e1c  jnz     short loc_180003E37
0x180003e1e  mov     rcx, [rbx+8]
0x180003e22  mov     rdx, rdi
0x180003e25  mov     rax, [rcx]
0x180003e28  mov     rax, [rax]
0x180003e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e30  or      bpl, al
0x180003e33  mov     byte ptr [rbx+28h], 0
0x180003e37  mov     rbx, [rbx+10h]
0x180003e3b  test    rbx, rbx
0x180003e3e  jnz     short loc_180003E13
0x180003e40  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003e47  test    rax, rax
0x180003e4a  jz      short loc_180003E6B
0x180003e4c  test    bpl, bpl
0x180003e4f  jnz     short loc_180003E61
0x180003e51  test    byte ptr [rdi+4], 2
0x180003e55  jnz     short loc_180003E61
0x180003e57  xor     ecx, ecx
0x180003e59  jmp     short loc_180003E63
0x180003e5b  add     rbx, 10h
0x180003e5f  jmp     short loc_180003DE9
0x180003e61  mov     cl, 1
0x180003e63  mov     rdx, rdi
0x180003e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e6b  call    cs:__imp_GetCurrentThreadId
0x180003e71  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003e77  cmp     ecx, eax
0x180003e79  jz      loc_180003F7B
0x180003e7f  mov     ecx, 1
0x180003e84  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003e8c  inc     ecx; this
0x180003e8e  cmp     ecx, 4
0x180003e91  jge     loc_180003F74
0x180003e97  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003e9d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003ea2  mov     rbx, rax
0x180003ea5  test    rax, rax
0x180003ea8  jz      loc_180003F6A
0x180003eae  cmp     qword ptr [rax+18h], 0
0x180003eb3  mov     ebp, 50h ; 'P'
0x180003eb8  mov     esi, [rax+10h]
0x180003ebb  jnz     short loc_180003EF2
0x180003ebd  test    esi, esi
0x180003ebf  jz      short loc_180003EF2
0x180003ec1  mov     edx, 190h; dwBytes
0x180003ec6  lea     ecx, [rbp-48h]; dwFlags
0x180003ec9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003ece  mov     [rbx+18h], rax
0x180003ed2  test    rax, rax
0x180003ed5  jz      short loc_180003EF2
0x180003ed7  mov     dword ptr [rbx+20h], 5
0x180003ede  lea     rcx, [rax+190h]
0x180003ee5  jmp     short loc_180003EED
0x180003ee7  mov     [rax], bp
0x180003eea  add     rax, rbp
0x180003eed  cmp     rax, rcx
0x180003ef0  jnz     short loc_180003EE7
0x180003ef2  mov     r9, [rbx+18h]
0x180003ef6  test    r9, r9
0x180003ef9  jz      short loc_180003F6A
0x180003efb  test    esi, esi
0x180003efd  jz      short loc_180003F30
0x180003eff  movzx   eax, word ptr [rbx+20h]
0x180003f03  mov     rcx, r9
0x180003f06  lea     rdx, [rax+rax*4]
0x180003f0a  shl     rdx, 4
0x180003f0e  add     rdx, r9
0x180003f11  cmp     r9, rdx
0x180003f14  jz      short loc_180003F30
0x180003f16  mov     r8d, [rbx+10h]
0x180003f1a  cmp     [rcx+4], r8d
0x180003f1e  jbe     short loc_180003F28
0x180003f20  mov     eax, [rdi+8]
0x180003f23  cmp     [rcx+8], eax
0x180003f26  jz      short loc_180003F6A
0x180003f28  add     rcx, rbp
0x180003f2b  cmp     rcx, rdx
0x180003f2e  jnz     short loc_180003F1A
0x180003f30  movzx   eax, word ptr [rbx+22h]
0x180003f34  xor     edx, edx
0x180003f36  movzx   ecx, word ptr [rbx+20h]
0x180003f3a  inc     eax
0x180003f3c  div     ecx
0x180003f3e  mov     rax, [rbx+8]
0x180003f42  mov     r8d, 1
0x180003f48  mov     [rbx+22h], dx
0x180003f4c  lock xadd [rax], r8d
0x180003f51  movzx   eax, dx
0x180003f54  inc     r8d; unsigned int
0x180003f57  mov     rdx, rdi; struct wil::FailureInfo *
0x180003f5a  lea     rcx, [rax+rax*4]
0x180003f5e  shl     rcx, 4
0x180003f62  add     rcx, r9; this
0x180003f65  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180003f6a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003f74  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003f7b  add     rsp, 20h
0x180003f7f  pop     r14
0x180003f81  pop     rdi
0x180003f82  pop     rsi
0x180003f83  pop     rbp
0x180003f84  pop     rbx
0x180003f85  retn
```
