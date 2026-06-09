# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004280`
- end: `0x1400043d0`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `336`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004280`
- `0x1400048ec`
- `0x1400049d0`
- `0x140006584`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400042b3`
- `KERNEL32!GetCurrentThreadId` at `0x140004375`
- `KERNEL32!GetCurrentThreadId` at `0x1400042b3`
- `KERNEL32!GetCurrentThreadId` at `0x140004375`

## pseudocode

```c
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
0x140004280  push    rbx
0x140004282  push    rbp
0x140004283  push    rsi
0x140004284  push    rdi
0x140004285  push    r14
0x140004287  sub     rsp, 30h
0x14000428b  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x140004294  mov     r14, r8
0x140004297  mov     rsi, rdx
0x14000429a  mov     rdi, rcx
0x14000429d  mov     byte ptr [rdx], 0
0x1400042a0  xor     bpl, bpl
0x1400042a3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400042aa  test    rbx, rbx
0x1400042ad  jz      loc_140004349
0x1400042b3  call    cs:__imp_GetCurrentThreadId
0x1400042b9  mov     r9d, eax
0x1400042bc  mov     r8d, eax
0x1400042bf  shr     r8, 2
0x1400042c3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400042cd  mul     r8
0x1400042d0  shr     rdx, 3
0x1400042d4  lea     rcx, [rdx+rdx*4]
0x1400042d8  add     rcx, rcx
0x1400042db  sub     r8, rcx
0x1400042de  mov     rbx, [rbx+r8*8]
0x1400042e2  jmp     short loc_1400042ED
0x1400042e4  cmp     [rbx], r9d
0x1400042e7  jz      short loc_140004364
0x1400042e9  mov     rbx, [rbx+8]
0x1400042ed  test    rbx, rbx
0x1400042f0  jnz     short loc_1400042E4
0x1400042f2  test    rbx, rbx
0x1400042f5  jz      short loc_140004349
0x1400042f7  cmp     qword ptr [rbx], 0
0x1400042fb  jz      short loc_140004349
0x1400042fd  mov     [rsi], bpl
0x140004300  mov     r9, r14; unsigned __int64
0x140004303  mov     r8, rsi; char *
0x140004306  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004309  mov     rcx, rdi; struct wil::FailureInfo *
0x14000430c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004311  test    al, al
0x140004313  jz      short loc_140004319
0x140004315  mov     [rdi+48h], rsi
0x140004319  mov     rbx, [rbx]
0x14000431c  mov     al, [rbx+28h]
0x14000431f  mov     byte ptr [rbx+28h], 1
0x140004323  test    al, al
0x140004325  jnz     short loc_140004340
0x140004327  mov     rcx, [rbx+8]
0x14000432b  mov     rax, [rcx]
0x14000432e  mov     rdx, rdi
0x140004331  mov     rax, [rax]
0x140004334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004339  or      bpl, al
0x14000433c  mov     byte ptr [rbx+28h], 0
0x140004340  mov     rbx, [rbx+10h]
0x140004344  test    rbx, rbx
0x140004347  jnz     short loc_14000431C
0x140004349  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004350  test    rax, rax
0x140004353  jz      short loc_140004375
0x140004355  test    bpl, bpl
0x140004358  jnz     short loc_14000436A
0x14000435a  test    byte ptr [rdi+4], 2
0x14000435e  jnz     short loc_14000436A
0x140004360  xor     ecx, ecx
0x140004362  jmp     short loc_14000436C
0x140004364  add     rbx, 10h
0x140004368  jmp     short loc_1400042F2
0x14000436a  mov     cl, 1
0x14000436c  mov     rdx, rdi
0x14000436f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004374  nop
0x140004375  call    cs:__imp_GetCurrentThreadId
0x14000437b  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004381  cmp     ecx, eax
0x140004383  jz      short loc_1400043C5
0x140004385  mov     ecx, 1
0x14000438a  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004392  inc     ecx; this
0x140004394  cmp     ecx, 4
0x140004397  jge     short loc_1400043BE
0x140004399  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000439f  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1400043a4  test    rax, rax
0x1400043a7  jz      short loc_1400043B4
0x1400043a9  mov     rdx, rdi; struct wil::FailureInfo *
0x1400043ac  mov     rcx, rax; this
0x1400043af  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1400043b4  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1400043be  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1400043c5  add     rsp, 30h
0x1400043c9  pop     r14
0x1400043cb  pop     rdi
0x1400043cc  pop     rsi
0x1400043cd  pop     rbp
0x1400043ce  pop     rbx
0x1400043cf  retn
```
