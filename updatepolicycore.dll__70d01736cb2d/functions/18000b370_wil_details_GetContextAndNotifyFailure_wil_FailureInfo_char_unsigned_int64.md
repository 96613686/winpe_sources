# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b370`
- end: `0x18000b57a`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `522`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800094bc`
- `0x18000af08`
- `0x18000b1a8`
- `0x18000b268`
- `0x18000b370`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b457`

## pseudocode

```c
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
0x18000b370  mov     [rsp+arg_18], rbx
0x18000b375  push    rbp
0x18000b376  push    rsi
0x18000b377  push    rdi
0x18000b378  push    r14
0x18000b37a  push    r15
0x18000b37c  sub     rsp, 20h
0x18000b380  mov     r14, r8
0x18000b383  mov     rsi, rdx
0x18000b386  mov     rdi, rcx
0x18000b389  xor     r15d, r15d
0x18000b38c  mov     [rdx], r15b
0x18000b38f  mov     bpl, r15b
0x18000b392  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b399  test    rbx, rbx
0x18000b39c  jz      loc_18000B42B
0x18000b3a2  call    cs:__imp_GetCurrentThreadId
0x18000b3a8  mov     r9d, eax
0x18000b3ab  mov     r8d, eax
0x18000b3ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b3b8  mul     r9
0x18000b3bb  shr     rdx, 3
0x18000b3bf  lea     rcx, [rdx+rdx*4]
0x18000b3c3  add     rcx, rcx
0x18000b3c6  sub     r8, rcx
0x18000b3c9  mov     rbx, [rbx+r8*8]
0x18000b3cd  jmp     short loc_18000B3DC
0x18000b3cf  cmp     [rbx], r9d
0x18000b3d2  jz      loc_18000B4D1
0x18000b3d8  mov     rbx, [rbx+8]
0x18000b3dc  test    rbx, rbx
0x18000b3df  jnz     short loc_18000B3CF
0x18000b3e1  mov     rbx, r15
0x18000b3e4  test    rbx, rbx
0x18000b3e7  jz      short loc_18000B42B
0x18000b3e9  cmp     [rbx], r15
0x18000b3ec  jz      short loc_18000B42B
0x18000b3ee  mov     [rsi], r15b
0x18000b3f1  mov     r9, r14; unsigned __int64
0x18000b3f4  mov     r8, rsi; char *
0x18000b3f7  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b3fa  mov     rcx, rdi; struct wil::FailureInfo *
0x18000b3fd  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b402  test    al, al
0x18000b404  jz      short loc_18000B40A
0x18000b406  mov     [rdi+48h], rsi
0x18000b40a  mov     rbx, [rbx]
0x18000b40d  mov     rcx, [rbx+8]
0x18000b411  mov     rax, [rcx]
0x18000b414  mov     rdx, rdi
0x18000b417  mov     rax, [rax]
0x18000b41a  call    _guard_dispatch_icall
0x18000b41f  or      bpl, al
0x18000b422  mov     rbx, [rbx+10h]
0x18000b426  test    rbx, rbx
0x18000b429  jnz     short loc_18000B40D
0x18000b42b  mov     r14d, 1
0x18000b431  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b438  test    rax, rax
0x18000b43b  jz      short loc_18000B457
0x18000b43d  test    bpl, bpl
0x18000b440  jnz     short loc_18000B44B
0x18000b442  test    byte ptr [rdi+4], 2
0x18000b446  mov     cl, r15b
0x18000b449  jz      short loc_18000B44E
0x18000b44b  mov     cl, r14b
0x18000b44e  mov     rdx, rdi
0x18000b451  call    _guard_dispatch_icall
0x18000b456  nop
0x18000b457  call    cs:__imp_GetCurrentThreadId
0x18000b45d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b463  cmp     ecx, eax
0x18000b465  jz      loc_18000B569
0x18000b46b  mov     ecx, r14d
0x18000b46e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b476  add     ecx, r14d; this
0x18000b479  cmp     ecx, 4
0x18000b47c  jge     loc_18000B562
0x18000b482  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b488  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b48d  mov     rbx, rax
0x18000b490  test    rax, rax
0x18000b493  jz      loc_18000B55B
0x18000b499  mov     esi, [rax+10h]
0x18000b49c  mov     ebp, 50h ; 'P'
0x18000b4a1  cmp     [rax+18h], r15
0x18000b4a5  jnz     short loc_18000B4E5
0x18000b4a7  test    esi, esi
0x18000b4a9  jz      short loc_18000B4E5
0x18000b4ab  mov     edx, 190h; dwBytes
0x18000b4b0  lea     ecx, [rbp-48h]; dwFlags
0x18000b4b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b4b8  mov     [rbx+18h], rax
0x18000b4bc  test    rax, rax
0x18000b4bf  jz      short loc_18000B4E5
0x18000b4c1  mov     dword ptr [rbx+20h], 5
0x18000b4c8  lea     rcx, [rax+190h]
0x18000b4cf  jmp     short loc_18000B4E0
0x18000b4d1  add     rbx, 10h
0x18000b4d5  jmp     loc_18000B3E4
0x18000b4da  mov     [rax], bp
0x18000b4dd  add     rax, rbp
0x18000b4e0  cmp     rax, rcx
0x18000b4e3  jnz     short loc_18000B4DA
0x18000b4e5  mov     r9, [rbx+18h]
0x18000b4e9  test    r9, r9
0x18000b4ec  jz      short loc_18000B55B
0x18000b4ee  test    esi, esi
0x18000b4f0  jz      short loc_18000B523
0x18000b4f2  mov     rcx, r9
0x18000b4f5  movzx   eax, word ptr [rbx+20h]
0x18000b4f9  lea     rdx, [rax+rax*4]
0x18000b4fd  shl     rdx, 4
0x18000b501  add     rdx, r9
0x18000b504  cmp     r9, rdx
0x18000b507  jz      short loc_18000B523
0x18000b509  mov     r8d, [rbx+10h]
0x18000b50d  cmp     [rcx+4], r8d
0x18000b511  jbe     short loc_18000B51B
0x18000b513  mov     eax, [rdi+8]
0x18000b516  cmp     [rcx+8], eax
0x18000b519  jz      short loc_18000B55B
0x18000b51b  add     rcx, rbp
0x18000b51e  cmp     rcx, rdx
0x18000b521  jnz     short loc_18000B50D
0x18000b523  movzx   eax, word ptr [rbx+22h]
0x18000b527  add     eax, r14d
0x18000b52a  movzx   ecx, word ptr [rbx+20h]
0x18000b52e  xor     edx, edx
0x18000b530  div     ecx
0x18000b532  mov     [rbx+22h], dx
0x18000b536  mov     rax, [rbx+8]
0x18000b53a  mov     r8d, r14d
0x18000b53d  lock xadd [rax], r8d
0x18000b542  add     r8d, r14d; unsigned int
0x18000b545  movzx   eax, dx
0x18000b548  lea     rcx, [rax+rax*4]
0x18000b54c  shl     rcx, 4
0x18000b550  add     rcx, r9; this
0x18000b553  mov     rdx, rdi; struct wil::FailureInfo *
0x18000b556  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b55b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, r15d; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b562  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b569  mov     rbx, [rsp+48h+arg_18]
0x18000b56e  add     rsp, 20h
0x18000b572  pop     r15
0x18000b574  pop     r14
0x18000b576  pop     rdi
0x18000b577  pop     rsi
0x18000b578  pop     rbp
0x18000b579  retn
```
