# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800253b0`
- end: `0x18002550d`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `349`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800253b0`
- `0x180025a54`
- `0x180025b40`
- `0x1800277c4`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800253e3`
- `KERNEL32!GetCurrentThreadId` at `0x1800254ab`
- `KERNEL32!GetCurrentThreadId` at `0x1800253e3`
- `KERNEL32!GetCurrentThreadId` at `0x1800254ab`

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
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800253b0  push    rbx
0x1800253b2  push    rbp
0x1800253b3  push    rsi
0x1800253b4  push    rdi
0x1800253b5  push    r14
0x1800253b7  sub     rsp, 30h
0x1800253bb  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800253c4  mov     r14, r8
0x1800253c7  mov     rsi, rdx
0x1800253ca  mov     rdi, rcx
0x1800253cd  mov     byte ptr [rdx], 0
0x1800253d0  xor     bpl, bpl
0x1800253d3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800253da  test    rbx, rbx
0x1800253dd  jz      loc_18002547F
0x1800253e3  call    cs:__imp_GetCurrentThreadId
0x1800253ea  nop     dword ptr [rax+rax+00h]
0x1800253ef  mov     r9d, eax
0x1800253f2  mov     r8d, eax
0x1800253f5  shr     r8, 2
0x1800253f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025403  mul     r8
0x180025406  shr     rdx, 3
0x18002540a  lea     rcx, [rdx+rdx*4]
0x18002540e  add     rcx, rcx
0x180025411  sub     r8, rcx
0x180025414  mov     rbx, [rbx+r8*8]
0x180025418  jmp     short loc_180025423
0x18002541a  cmp     [rbx], r9d
0x18002541d  jz      short loc_18002549A
0x18002541f  mov     rbx, [rbx+8]
0x180025423  test    rbx, rbx
0x180025426  jnz     short loc_18002541A
0x180025428  test    rbx, rbx
0x18002542b  jz      short loc_18002547F
0x18002542d  cmp     qword ptr [rbx], 0
0x180025431  jz      short loc_18002547F
0x180025433  mov     [rsi], bpl
0x180025436  mov     r9, r14; unsigned __int64
0x180025439  mov     r8, rsi; char *
0x18002543c  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002543f  mov     rcx, rdi; struct wil::FailureInfo *
0x180025442  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180025447  test    al, al
0x180025449  jz      short loc_18002544F
0x18002544b  mov     [rdi+48h], rsi
0x18002544f  mov     rbx, [rbx]
0x180025452  mov     al, [rbx+28h]
0x180025455  mov     byte ptr [rbx+28h], 1
0x180025459  test    al, al
0x18002545b  jnz     short loc_180025476
0x18002545d  mov     rcx, [rbx+8]
0x180025461  mov     rax, [rcx]
0x180025464  mov     rdx, rdi
0x180025467  mov     rax, [rax]
0x18002546a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002546f  or      bpl, al
0x180025472  mov     byte ptr [rbx+28h], 0
0x180025476  mov     rbx, [rbx+10h]
0x18002547a  test    rbx, rbx
0x18002547d  jnz     short loc_180025452
0x18002547f  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180025486  test    rax, rax
0x180025489  jz      short loc_1800254AB
0x18002548b  test    bpl, bpl
0x18002548e  jnz     short loc_1800254A0
0x180025490  test    byte ptr [rdi+4], 2
0x180025494  jnz     short loc_1800254A0
0x180025496  xor     ecx, ecx
0x180025498  jmp     short loc_1800254A2
0x18002549a  add     rbx, 10h
0x18002549e  jmp     short loc_180025428
0x1800254a0  mov     cl, 1
0x1800254a2  mov     rdx, rdi
0x1800254a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254aa  nop
0x1800254ab  call    cs:__imp_GetCurrentThreadId
0x1800254b2  nop     dword ptr [rax+rax+00h]
0x1800254b7  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800254bd  cmp     ecx, eax
0x1800254bf  jz      short loc_180025501
0x1800254c1  mov     ecx, 1
0x1800254c6  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800254ce  inc     ecx; this
0x1800254d0  cmp     ecx, 4
0x1800254d3  jge     short loc_1800254FA
0x1800254d5  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800254db  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800254e0  test    rax, rax
0x1800254e3  jz      short loc_1800254F0
0x1800254e5  mov     rdx, rdi; struct wil::FailureInfo *
0x1800254e8  mov     rcx, rax; this
0x1800254eb  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1800254f0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800254fa  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180025501  add     rsp, 30h
0x180025505  pop     r14
0x180025507  pop     rdi
0x180025508  pop     rsi
0x180025509  pop     rbp
0x18002550a  pop     rbx
0x18002550b  retn
```
