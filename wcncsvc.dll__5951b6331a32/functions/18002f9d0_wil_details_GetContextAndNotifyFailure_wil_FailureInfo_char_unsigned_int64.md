# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002f9d0`
- end: `0x18002fb17`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002f9d0`
- `0x18003032c`
- `0x180030410`
- `0x180032ec4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f9fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fabc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f9fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fabc`

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
0x18002f9d0  push    rbx
0x18002f9d2  push    rbp
0x18002f9d3  push    rsi
0x18002f9d4  push    rdi
0x18002f9d5  push    r14
0x18002f9d7  sub     rsp, 20h
0x18002f9db  mov     r14, r8
0x18002f9de  mov     rsi, rdx
0x18002f9e1  mov     rdi, rcx
0x18002f9e4  mov     byte ptr [rdx], 0
0x18002f9e7  xor     bpl, bpl
0x18002f9ea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002f9f1  test    rbx, rbx
0x18002f9f4  jz      loc_18002FA90
0x18002f9fa  call    cs:__imp_GetCurrentThreadId
0x18002fa00  mov     r9d, eax
0x18002fa03  mov     r8d, eax
0x18002fa06  shr     r8, 2
0x18002fa0a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002fa14  mul     r8
0x18002fa17  shr     rdx, 3
0x18002fa1b  lea     rcx, [rdx+rdx*4]
0x18002fa1f  add     rcx, rcx
0x18002fa22  sub     r8, rcx
0x18002fa25  mov     rbx, [rbx+r8*8]
0x18002fa29  jmp     short loc_18002FA34
0x18002fa2b  cmp     [rbx], r9d
0x18002fa2e  jz      short loc_18002FAAB
0x18002fa30  mov     rbx, [rbx+8]
0x18002fa34  test    rbx, rbx
0x18002fa37  jnz     short loc_18002FA2B
0x18002fa39  test    rbx, rbx
0x18002fa3c  jz      short loc_18002FA90
0x18002fa3e  cmp     qword ptr [rbx], 0
0x18002fa42  jz      short loc_18002FA90
0x18002fa44  mov     [rsi], bpl
0x18002fa47  mov     r9, r14; unsigned __int64
0x18002fa4a  mov     r8, rsi; char *
0x18002fa4d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002fa50  mov     rcx, rdi; struct wil::FailureInfo *
0x18002fa53  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002fa58  test    al, al
0x18002fa5a  jz      short loc_18002FA60
0x18002fa5c  mov     [rdi+48h], rsi
0x18002fa60  mov     rbx, [rbx]
0x18002fa63  mov     al, [rbx+28h]
0x18002fa66  mov     byte ptr [rbx+28h], 1
0x18002fa6a  test    al, al
0x18002fa6c  jnz     short loc_18002FA87
0x18002fa6e  mov     rcx, [rbx+8]
0x18002fa72  mov     rax, [rcx]
0x18002fa75  mov     rdx, rdi
0x18002fa78  mov     rax, [rax]
0x18002fa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa80  or      bpl, al
0x18002fa83  mov     byte ptr [rbx+28h], 0
0x18002fa87  mov     rbx, [rbx+10h]
0x18002fa8b  test    rbx, rbx
0x18002fa8e  jnz     short loc_18002FA63
0x18002fa90  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002fa97  test    rax, rax
0x18002fa9a  jz      short loc_18002FABC
0x18002fa9c  test    bpl, bpl
0x18002fa9f  jnz     short loc_18002FAB1
0x18002faa1  test    byte ptr [rdi+4], 2
0x18002faa5  jnz     short loc_18002FAB1
0x18002faa7  xor     ecx, ecx
0x18002faa9  jmp     short loc_18002FAB3
0x18002faab  add     rbx, 10h
0x18002faaf  jmp     short loc_18002FA39
0x18002fab1  mov     cl, 1
0x18002fab3  mov     rdx, rdi
0x18002fab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fabb  nop
0x18002fabc  call    cs:__imp_GetCurrentThreadId
0x18002fac2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002fac8  cmp     ecx, eax
0x18002faca  jz      short loc_18002FB0C
0x18002facc  mov     ecx, 1
0x18002fad1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002fad9  inc     ecx; this
0x18002fadb  cmp     ecx, 4
0x18002fade  jge     short loc_18002FB05
0x18002fae0  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002fae6  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18002faeb  test    rax, rax
0x18002faee  jz      short loc_18002FAFB
0x18002faf0  mov     rdx, rdi; struct wil::FailureInfo *
0x18002faf3  mov     rcx, rax; this
0x18002faf6  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18002fafb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002fb05  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002fb0c  add     rsp, 20h
0x18002fb10  pop     r14
0x18002fb12  pop     rdi
0x18002fb13  pop     rsi
0x18002fb14  pop     rbp
0x18002fb15  pop     rbx
0x18002fb16  retn
```
