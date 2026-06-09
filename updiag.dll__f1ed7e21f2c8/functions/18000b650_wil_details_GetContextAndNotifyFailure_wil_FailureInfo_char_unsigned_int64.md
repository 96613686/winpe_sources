# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b650`
- end: `0x18000b85a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a438`
- `0x18000b1a4`
- `0x18000b444`
- `0x18000b504`
- `0x18000b650`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b682`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b682`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b737`

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
0x18000b650  mov     [rsp+arg_18], rbx
0x18000b655  push    rbp
0x18000b656  push    rsi
0x18000b657  push    rdi
0x18000b658  push    r14
0x18000b65a  push    r15
0x18000b65c  sub     rsp, 20h
0x18000b660  mov     r14, r8
0x18000b663  mov     rsi, rdx
0x18000b666  mov     rdi, rcx
0x18000b669  xor     r15d, r15d
0x18000b66c  mov     [rdx], r15b
0x18000b66f  mov     bpl, r15b
0x18000b672  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b679  test    rbx, rbx
0x18000b67c  jz      loc_18000B70B
0x18000b682  call    cs:__imp_GetCurrentThreadId
0x18000b688  mov     r9d, eax
0x18000b68b  mov     r8d, eax
0x18000b68e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b698  mul     r9
0x18000b69b  shr     rdx, 3
0x18000b69f  lea     rcx, [rdx+rdx*4]
0x18000b6a3  add     rcx, rcx
0x18000b6a6  sub     r8, rcx
0x18000b6a9  mov     rbx, [rbx+r8*8]
0x18000b6ad  jmp     short loc_18000B6BC
0x18000b6af  cmp     [rbx], r9d
0x18000b6b2  jz      loc_18000B7B1
0x18000b6b8  mov     rbx, [rbx+8]
0x18000b6bc  test    rbx, rbx
0x18000b6bf  jnz     short loc_18000B6AF
0x18000b6c1  mov     rbx, r15
0x18000b6c4  test    rbx, rbx
0x18000b6c7  jz      short loc_18000B70B
0x18000b6c9  cmp     [rbx], r15
0x18000b6cc  jz      short loc_18000B70B
0x18000b6ce  mov     [rsi], r15b
0x18000b6d1  mov     r9, r14; unsigned __int64
0x18000b6d4  mov     r8, rsi; char *
0x18000b6d7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b6da  mov     rcx, rdi; struct wil::FailureInfo *
0x18000b6dd  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b6e2  test    al, al
0x18000b6e4  jz      short loc_18000B6EA
0x18000b6e6  mov     [rdi+48h], rsi
0x18000b6ea  mov     rbx, [rbx]
0x18000b6ed  mov     rcx, [rbx+8]
0x18000b6f1  mov     rax, [rcx]
0x18000b6f4  mov     rdx, rdi
0x18000b6f7  mov     rax, [rax]
0x18000b6fa  call    _guard_dispatch_icall
0x18000b6ff  or      bpl, al
0x18000b702  mov     rbx, [rbx+10h]
0x18000b706  test    rbx, rbx
0x18000b709  jnz     short loc_18000B6ED
0x18000b70b  mov     r14d, 1
0x18000b711  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b718  test    rax, rax
0x18000b71b  jz      short loc_18000B737
0x18000b71d  test    bpl, bpl
0x18000b720  jnz     short loc_18000B72B
0x18000b722  test    byte ptr [rdi+4], 2
0x18000b726  mov     cl, r15b
0x18000b729  jz      short loc_18000B72E
0x18000b72b  mov     cl, r14b
0x18000b72e  mov     rdx, rdi
0x18000b731  call    _guard_dispatch_icall
0x18000b736  nop
0x18000b737  call    cs:__imp_GetCurrentThreadId
0x18000b73d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b743  cmp     ecx, eax
0x18000b745  jz      loc_18000B849
0x18000b74b  mov     ecx, r14d
0x18000b74e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b756  add     ecx, r14d; this
0x18000b759  cmp     ecx, 4
0x18000b75c  jge     loc_18000B842
0x18000b762  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b768  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b76d  mov     rbx, rax
0x18000b770  test    rax, rax
0x18000b773  jz      loc_18000B83B
0x18000b779  mov     esi, [rax+10h]
0x18000b77c  mov     ebp, 50h ; 'P'
0x18000b781  cmp     [rax+18h], r15
0x18000b785  jnz     short loc_18000B7C5
0x18000b787  test    esi, esi
0x18000b789  jz      short loc_18000B7C5
0x18000b78b  mov     edx, 190h; dwBytes
0x18000b790  lea     ecx, [rbp-48h]; dwFlags
0x18000b793  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b798  mov     [rbx+18h], rax
0x18000b79c  test    rax, rax
0x18000b79f  jz      short loc_18000B7C5
0x18000b7a1  mov     dword ptr [rbx+20h], 5
0x18000b7a8  lea     rcx, [rax+190h]
0x18000b7af  jmp     short loc_18000B7C0
0x18000b7b1  add     rbx, 10h
0x18000b7b5  jmp     loc_18000B6C4
0x18000b7ba  mov     [rax], bp
0x18000b7bd  add     rax, rbp
0x18000b7c0  cmp     rax, rcx
0x18000b7c3  jnz     short loc_18000B7BA
0x18000b7c5  mov     r9, [rbx+18h]
0x18000b7c9  test    r9, r9
0x18000b7cc  jz      short loc_18000B83B
0x18000b7ce  test    esi, esi
0x18000b7d0  jz      short loc_18000B803
0x18000b7d2  mov     rcx, r9
0x18000b7d5  movzx   eax, word ptr [rbx+20h]
0x18000b7d9  lea     rdx, [rax+rax*4]
0x18000b7dd  shl     rdx, 4
0x18000b7e1  add     rdx, r9
0x18000b7e4  cmp     r9, rdx
0x18000b7e7  jz      short loc_18000B803
0x18000b7e9  mov     r8d, [rbx+10h]
0x18000b7ed  cmp     [rcx+4], r8d
0x18000b7f1  jbe     short loc_18000B7FB
0x18000b7f3  mov     eax, [rdi+8]
0x18000b7f6  cmp     [rcx+8], eax
0x18000b7f9  jz      short loc_18000B83B
0x18000b7fb  add     rcx, rbp
0x18000b7fe  cmp     rcx, rdx
0x18000b801  jnz     short loc_18000B7ED
0x18000b803  movzx   eax, word ptr [rbx+22h]
0x18000b807  add     eax, r14d
0x18000b80a  movzx   ecx, word ptr [rbx+20h]
0x18000b80e  xor     edx, edx
0x18000b810  div     ecx
0x18000b812  mov     [rbx+22h], dx
0x18000b816  mov     rax, [rbx+8]
0x18000b81a  mov     r8d, r14d
0x18000b81d  lock xadd [rax], r8d
0x18000b822  add     r8d, r14d; unsigned int
0x18000b825  movzx   eax, dx
0x18000b828  lea     rcx, [rax+rax*4]
0x18000b82c  shl     rcx, 4
0x18000b830  add     rcx, r9; this
0x18000b833  mov     rdx, rdi; struct wil::FailureInfo *
0x18000b836  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b83b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b842  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b849  mov     rbx, [rsp+48h+arg_18]
0x18000b84e  add     rsp, 20h
0x18000b852  pop     r15
0x18000b854  pop     r14
0x18000b856  pop     rdi
0x18000b857  pop     rsi
0x18000b858  pop     rbp
0x18000b859  retn
```
