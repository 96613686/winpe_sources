# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000b7f0`
- end: `0x18000b937`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `327`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000b7f0`
- `0x18000c5ac`
- `0x18000c690`
- `0x180010b78`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000b81a`
- `KERNEL32!GetCurrentThreadId` at `0x18000b8dc`
- `KERNEL32!GetCurrentThreadId` at `0x18000b81a`
- `KERNEL32!GetCurrentThreadId` at `0x18000b8dc`

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
0x18000b7f0  push    rbx
0x18000b7f2  push    rbp
0x18000b7f3  push    rsi
0x18000b7f4  push    rdi
0x18000b7f5  push    r14
0x18000b7f7  sub     rsp, 20h
0x18000b7fb  mov     r14, r8
0x18000b7fe  mov     rsi, rdx
0x18000b801  mov     rdi, rcx
0x18000b804  mov     byte ptr [rdx], 0
0x18000b807  xor     bpl, bpl
0x18000b80a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b811  test    rbx, rbx
0x18000b814  jz      loc_18000B8B0
0x18000b81a  call    cs:__imp_GetCurrentThreadId
0x18000b820  mov     r9d, eax
0x18000b823  mov     r8d, eax
0x18000b826  shr     r8, 2
0x18000b82a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b834  mul     r8
0x18000b837  shr     rdx, 3
0x18000b83b  lea     rcx, [rdx+rdx*4]
0x18000b83f  add     rcx, rcx
0x18000b842  sub     r8, rcx
0x18000b845  mov     rbx, [rbx+r8*8]
0x18000b849  jmp     short loc_18000B854
0x18000b84b  cmp     [rbx], r9d
0x18000b84e  jz      short loc_18000B8CB
0x18000b850  mov     rbx, [rbx+8]
0x18000b854  test    rbx, rbx
0x18000b857  jnz     short loc_18000B84B
0x18000b859  test    rbx, rbx
0x18000b85c  jz      short loc_18000B8B0
0x18000b85e  cmp     qword ptr [rbx], 0
0x18000b862  jz      short loc_18000B8B0
0x18000b864  mov     [rsi], bpl
0x18000b867  mov     r9, r14; unsigned __int64
0x18000b86a  mov     r8, rsi; char *
0x18000b86d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b870  mov     rcx, rdi; struct wil::FailureInfo *
0x18000b873  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b878  test    al, al
0x18000b87a  jz      short loc_18000B880
0x18000b87c  mov     [rdi+48h], rsi
0x18000b880  mov     rbx, [rbx]
0x18000b883  mov     al, [rbx+28h]
0x18000b886  mov     byte ptr [rbx+28h], 1
0x18000b88a  test    al, al
0x18000b88c  jnz     short loc_18000B8A7
0x18000b88e  mov     rcx, [rbx+8]
0x18000b892  mov     rax, [rcx]
0x18000b895  mov     rdx, rdi
0x18000b898  mov     rax, [rax]
0x18000b89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a0  or      bpl, al
0x18000b8a3  mov     byte ptr [rbx+28h], 0
0x18000b8a7  mov     rbx, [rbx+10h]
0x18000b8ab  test    rbx, rbx
0x18000b8ae  jnz     short loc_18000B883
0x18000b8b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000b8b7  test    rax, rax
0x18000b8ba  jz      short loc_18000B8DC
0x18000b8bc  test    bpl, bpl
0x18000b8bf  jnz     short loc_18000B8D1
0x18000b8c1  test    byte ptr [rdi+4], 2
0x18000b8c5  jnz     short loc_18000B8D1
0x18000b8c7  xor     ecx, ecx
0x18000b8c9  jmp     short loc_18000B8D3
0x18000b8cb  add     rbx, 10h
0x18000b8cf  jmp     short loc_18000B859
0x18000b8d1  mov     cl, 1
0x18000b8d3  mov     rdx, rdi
0x18000b8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8db  nop
0x18000b8dc  call    cs:__imp_GetCurrentThreadId
0x18000b8e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b8e8  cmp     ecx, eax
0x18000b8ea  jz      short loc_18000B92C
0x18000b8ec  mov     ecx, 1
0x18000b8f1  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b8f9  inc     ecx; this
0x18000b8fb  cmp     ecx, 4
0x18000b8fe  jge     short loc_18000B925
0x18000b900  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b906  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000b90b  test    rax, rax
0x18000b90e  jz      short loc_18000B91B
0x18000b910  mov     rdx, rdi; struct wil::FailureInfo *
0x18000b913  mov     rcx, rax; this
0x18000b916  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000b91b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000b925  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000b92c  add     rsp, 20h
0x18000b930  pop     r14
0x18000b932  pop     rdi
0x18000b933  pop     rsi
0x18000b934  pop     rbp
0x18000b935  pop     rbx
0x18000b936  retn
```
