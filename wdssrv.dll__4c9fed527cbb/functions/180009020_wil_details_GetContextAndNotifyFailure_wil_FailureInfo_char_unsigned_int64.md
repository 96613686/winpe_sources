# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009020`
- end: `0x18000917e`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `350`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009020`
- `0x1800097c8`
- `0x1800098c8`
- `0x18000d27c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009058`
- `KERNEL32!GetCurrentThreadId` at `0x18000910c`
- `KERNEL32!GetCurrentThreadId` at `0x180009058`
- `KERNEL32!GetCurrentThreadId` at `0x18000910c`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
  unsigned __int64 CurrentThreadId; // r10
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * (CurrentThreadId / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
        v11 = (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        v3 |= v11;
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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v7);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x180009020  mov     rax, rsp
0x180009023  mov     [rax+8], rbx
0x180009027  mov     [rax+10h], rbp
0x18000902b  mov     [rax+18h], rsi
0x18000902f  mov     [rax+20h], rdi
0x180009033  push    r14
0x180009035  sub     rsp, 20h
0x180009039  mov     byte ptr [rdx], 0
0x18000903c  xor     bpl, bpl
0x18000903f  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009046  mov     r14, r8
0x180009049  mov     rsi, rdx
0x18000904c  mov     rdi, rcx
0x18000904f  test    rbx, rbx
0x180009052  jz      loc_1800090E1
0x180009058  call    cs:__imp_GetCurrentThreadId
0x18000905f  nop     dword ptr [rax+rax+00h]
0x180009064  mov     r9d, eax
0x180009067  mov     r10d, eax
0x18000906a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009074  mul     r10
0x180009077  shr     rdx, 3
0x18000907b  lea     rcx, [rdx+rdx*4]
0x18000907f  add     rcx, rcx
0x180009082  sub     r9, rcx
0x180009085  mov     rbx, [rbx+r9*8]
0x180009089  jmp     short loc_180009094
0x18000908b  cmp     [rbx], r10d
0x18000908e  jz      short loc_1800090FC
0x180009090  mov     rbx, [rbx+8]
0x180009094  test    rbx, rbx
0x180009097  jnz     short loc_18000908B
0x180009099  test    rbx, rbx
0x18000909c  jz      short loc_1800090E1
0x18000909e  cmp     qword ptr [rbx], 0
0x1800090a2  jz      short loc_1800090E1
0x1800090a4  mov     [rsi], bpl
0x1800090a7  mov     r9, r14; unsigned __int64
0x1800090aa  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800090ad  mov     r8, rsi; char *
0x1800090b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800090b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800090b8  test    al, al
0x1800090ba  jz      short loc_1800090C0
0x1800090bc  mov     [rdi+48h], rsi
0x1800090c0  mov     rbx, [rbx]
0x1800090c3  mov     rcx, [rbx+8]
0x1800090c7  mov     rdx, rdi
0x1800090ca  mov     rax, [rcx]
0x1800090cd  mov     rax, [rax]
0x1800090d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d5  mov     rbx, [rbx+10h]
0x1800090d9  or      bpl, al
0x1800090dc  test    rbx, rbx
0x1800090df  jnz     short loc_1800090C3
0x1800090e1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800090e8  test    rax, rax
0x1800090eb  jz      short loc_18000910C
0x1800090ed  test    bpl, bpl
0x1800090f0  jnz     short loc_180009102
0x1800090f2  test    byte ptr [rdi+4], 2
0x1800090f6  jnz     short loc_180009102
0x1800090f8  xor     ecx, ecx
0x1800090fa  jmp     short loc_180009104
0x1800090fc  add     rbx, 10h
0x180009100  jmp     short loc_180009099
0x180009102  mov     cl, 1
0x180009104  mov     rdx, rdi
0x180009107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000910c  call    cs:__imp_GetCurrentThreadId
0x180009113  nop     dword ptr [rax+rax+00h]
0x180009118  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000911e  cmp     ecx, eax
0x180009120  jz      short loc_180009162
0x180009122  mov     ecx, 1
0x180009127  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000912f  inc     ecx; this
0x180009131  cmp     ecx, 4
0x180009134  jge     short loc_18000915B
0x180009136  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000913c  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180009141  test    rax, rax
0x180009144  jz      short loc_180009151
0x180009146  mov     rdx, rdi; struct wil::FailureInfo *
0x180009149  mov     rcx, rax; this
0x18000914c  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180009151  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000915b  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009162  mov     rbx, [rsp+28h+arg_0]
0x180009167  mov     rbp, [rsp+28h+arg_8]
0x18000916c  mov     rsi, [rsp+28h+arg_10]
0x180009171  mov     rdi, [rsp+28h+arg_18]
0x180009176  add     rsp, 20h
0x18000917a  pop     r14
0x18000917c  retn
```
