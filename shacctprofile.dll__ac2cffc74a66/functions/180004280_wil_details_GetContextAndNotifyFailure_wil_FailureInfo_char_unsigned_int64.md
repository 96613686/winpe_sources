# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004280`
- end: `0x180004486`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004280`
- `0x180004978`
- `0x180004a5c`
- `0x1800052c8`
- `0x180005610`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000436b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000436b`

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
0x180004280  push    rbx
0x180004282  push    rbp
0x180004283  push    rsi
0x180004284  push    rdi
0x180004285  push    r14
0x180004287  sub     rsp, 20h
0x18000428b  mov     byte ptr [rdx], 0
0x18000428e  xor     bpl, bpl
0x180004291  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004298  mov     r14, r8
0x18000429b  mov     rsi, rdx
0x18000429e  mov     rdi, rcx
0x1800042a1  test    rbx, rbx
0x1800042a4  jz      loc_180004340
0x1800042aa  call    cs:__imp_GetCurrentThreadId
0x1800042b0  mov     r8d, eax
0x1800042b3  mov     r9d, eax
0x1800042b6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800042c0  shr     r8, 2
0x1800042c4  mul     r8
0x1800042c7  shr     rdx, 3
0x1800042cb  lea     rcx, [rdx+rdx*4]
0x1800042cf  add     rcx, rcx
0x1800042d2  sub     r8, rcx
0x1800042d5  mov     rbx, [rbx+r8*8]
0x1800042d9  jmp     short loc_1800042E4
0x1800042db  cmp     [rbx], r9d
0x1800042de  jz      short loc_18000435B
0x1800042e0  mov     rbx, [rbx+8]
0x1800042e4  test    rbx, rbx
0x1800042e7  jnz     short loc_1800042DB
0x1800042e9  test    rbx, rbx
0x1800042ec  jz      short loc_180004340
0x1800042ee  cmp     qword ptr [rbx], 0
0x1800042f2  jz      short loc_180004340
0x1800042f4  mov     [rsi], bpl
0x1800042f7  mov     r9, r14; unsigned __int64
0x1800042fa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800042fd  mov     r8, rsi; char *
0x180004300  mov     rcx, rdi; struct wil::FailureInfo *
0x180004303  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004308  test    al, al
0x18000430a  jz      short loc_180004310
0x18000430c  mov     [rdi+48h], rsi
0x180004310  mov     rbx, [rbx]
0x180004313  mov     al, [rbx+28h]
0x180004316  mov     byte ptr [rbx+28h], 1
0x18000431a  test    al, al
0x18000431c  jnz     short loc_180004337
0x18000431e  mov     rcx, [rbx+8]
0x180004322  mov     rdx, rdi
0x180004325  mov     rax, [rcx]
0x180004328  mov     rax, [rax]
0x18000432b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004330  or      bpl, al
0x180004333  mov     byte ptr [rbx+28h], 0
0x180004337  mov     rbx, [rbx+10h]
0x18000433b  test    rbx, rbx
0x18000433e  jnz     short loc_180004313
0x180004340  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004347  test    rax, rax
0x18000434a  jz      short loc_18000436B
0x18000434c  test    bpl, bpl
0x18000434f  jnz     short loc_180004361
0x180004351  test    byte ptr [rdi+4], 2
0x180004355  jnz     short loc_180004361
0x180004357  xor     ecx, ecx
0x180004359  jmp     short loc_180004363
0x18000435b  add     rbx, 10h
0x18000435f  jmp     short loc_1800042E9
0x180004361  mov     cl, 1
0x180004363  mov     rdx, rdi
0x180004366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436b  call    cs:__imp_GetCurrentThreadId
0x180004371  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004377  cmp     ecx, eax
0x180004379  jz      loc_18000447B
0x18000437f  mov     ecx, 1
0x180004384  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000438c  inc     ecx; this
0x18000438e  cmp     ecx, 4
0x180004391  jge     loc_180004474
0x180004397  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000439d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800043a2  mov     rbx, rax
0x1800043a5  test    rax, rax
0x1800043a8  jz      loc_18000446A
0x1800043ae  cmp     qword ptr [rax+18h], 0
0x1800043b3  mov     ebp, 50h ; 'P'
0x1800043b8  mov     esi, [rax+10h]
0x1800043bb  jnz     short loc_1800043F2
0x1800043bd  test    esi, esi
0x1800043bf  jz      short loc_1800043F2
0x1800043c1  mov     edx, 190h; dwBytes
0x1800043c6  lea     ecx, [rbp-48h]; dwFlags
0x1800043c9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800043ce  mov     [rbx+18h], rax
0x1800043d2  test    rax, rax
0x1800043d5  jz      short loc_1800043F2
0x1800043d7  mov     dword ptr [rbx+20h], 5
0x1800043de  lea     rcx, [rax+190h]
0x1800043e5  jmp     short loc_1800043ED
0x1800043e7  mov     [rax], bp
0x1800043ea  add     rax, rbp
0x1800043ed  cmp     rax, rcx
0x1800043f0  jnz     short loc_1800043E7
0x1800043f2  mov     r9, [rbx+18h]
0x1800043f6  test    r9, r9
0x1800043f9  jz      short loc_18000446A
0x1800043fb  test    esi, esi
0x1800043fd  jz      short loc_180004430
0x1800043ff  movzx   eax, word ptr [rbx+20h]
0x180004403  mov     rcx, r9
0x180004406  lea     rdx, [rax+rax*4]
0x18000440a  shl     rdx, 4
0x18000440e  add     rdx, r9
0x180004411  cmp     r9, rdx
0x180004414  jz      short loc_180004430
0x180004416  mov     r8d, [rbx+10h]
0x18000441a  cmp     [rcx+4], r8d
0x18000441e  jbe     short loc_180004428
0x180004420  mov     eax, [rdi+8]
0x180004423  cmp     [rcx+8], eax
0x180004426  jz      short loc_18000446A
0x180004428  add     rcx, rbp
0x18000442b  cmp     rcx, rdx
0x18000442e  jnz     short loc_18000441A
0x180004430  movzx   eax, word ptr [rbx+22h]
0x180004434  xor     edx, edx
0x180004436  movzx   ecx, word ptr [rbx+20h]
0x18000443a  inc     eax
0x18000443c  div     ecx
0x18000443e  mov     rax, [rbx+8]
0x180004442  mov     r8d, 1
0x180004448  mov     [rbx+22h], dx
0x18000444c  lock xadd [rax], r8d
0x180004451  movzx   eax, dx
0x180004454  inc     r8d; unsigned int
0x180004457  mov     rdx, rdi; struct wil::FailureInfo *
0x18000445a  lea     rcx, [rax+rax*4]
0x18000445e  shl     rcx, 4
0x180004462  add     rcx, r9; this
0x180004465  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000446a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004474  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000447b  add     rsp, 20h
0x18000447f  pop     r14
0x180004481  pop     rdi
0x180004482  pop     rsi
0x180004483  pop     rbp
0x180004484  pop     rbx
0x180004485  retn
```
