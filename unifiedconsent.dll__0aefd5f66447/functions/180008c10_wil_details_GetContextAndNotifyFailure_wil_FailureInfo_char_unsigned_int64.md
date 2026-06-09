# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008c10`
- end: `0x180008e17`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008c10`
- `0x180009830`
- `0x180009914`
- `0x18000a2ec`
- `0x18000c874`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008cfc`

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
0x180008c10  push    rbx
0x180008c12  push    rbp
0x180008c13  push    rsi
0x180008c14  push    rdi
0x180008c15  push    r14
0x180008c17  sub     rsp, 20h
0x180008c1b  mov     r14, r8
0x180008c1e  mov     rsi, rdx
0x180008c21  mov     rdi, rcx
0x180008c24  mov     byte ptr [rdx], 0
0x180008c27  xor     bpl, bpl
0x180008c2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008c31  test    rbx, rbx
0x180008c34  jz      loc_180008CD0
0x180008c3a  call    cs:__imp_GetCurrentThreadId
0x180008c40  mov     r9d, eax
0x180008c43  mov     r8d, eax
0x180008c46  shr     r8, 2
0x180008c4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008c54  mul     r8
0x180008c57  shr     rdx, 3
0x180008c5b  lea     rcx, [rdx+rdx*4]
0x180008c5f  add     rcx, rcx
0x180008c62  sub     r8, rcx
0x180008c65  mov     rbx, [rbx+r8*8]
0x180008c69  jmp     short loc_180008C74
0x180008c6b  cmp     [rbx], r9d
0x180008c6e  jz      short loc_180008CEB
0x180008c70  mov     rbx, [rbx+8]
0x180008c74  test    rbx, rbx
0x180008c77  jnz     short loc_180008C6B
0x180008c79  test    rbx, rbx
0x180008c7c  jz      short loc_180008CD0
0x180008c7e  cmp     qword ptr [rbx], 0
0x180008c82  jz      short loc_180008CD0
0x180008c84  mov     [rsi], bpl
0x180008c87  mov     r9, r14; unsigned __int64
0x180008c8a  mov     r8, rsi; char *
0x180008c8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008c90  mov     rcx, rdi; struct wil::FailureInfo *
0x180008c93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008c98  test    al, al
0x180008c9a  jz      short loc_180008CA0
0x180008c9c  mov     [rdi+48h], rsi
0x180008ca0  mov     rbx, [rbx]
0x180008ca3  mov     al, [rbx+28h]
0x180008ca6  mov     byte ptr [rbx+28h], 1
0x180008caa  test    al, al
0x180008cac  jnz     short loc_180008CC7
0x180008cae  mov     rcx, [rbx+8]
0x180008cb2  mov     rax, [rcx]
0x180008cb5  mov     rdx, rdi
0x180008cb8  mov     rax, [rax]
0x180008cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc0  or      bpl, al
0x180008cc3  mov     byte ptr [rbx+28h], 0
0x180008cc7  mov     rbx, [rbx+10h]
0x180008ccb  test    rbx, rbx
0x180008cce  jnz     short loc_180008CA3
0x180008cd0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008cd7  test    rax, rax
0x180008cda  jz      short loc_180008CFC
0x180008cdc  test    bpl, bpl
0x180008cdf  jnz     short loc_180008CF1
0x180008ce1  test    byte ptr [rdi+4], 2
0x180008ce5  jnz     short loc_180008CF1
0x180008ce7  xor     ecx, ecx
0x180008ce9  jmp     short loc_180008CF3
0x180008ceb  add     rbx, 10h
0x180008cef  jmp     short loc_180008C79
0x180008cf1  mov     cl, 1
0x180008cf3  mov     rdx, rdi
0x180008cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfb  nop
0x180008cfc  call    cs:__imp_GetCurrentThreadId
0x180008d02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008d08  cmp     ecx, eax
0x180008d0a  jz      loc_180008E0C
0x180008d10  mov     ecx, 1
0x180008d15  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008d1d  inc     ecx; this
0x180008d1f  cmp     ecx, 4
0x180008d22  jge     loc_180008E05
0x180008d28  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008d2e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008d33  mov     rbx, rax
0x180008d36  test    rax, rax
0x180008d39  jz      loc_180008DFB
0x180008d3f  mov     esi, [rax+10h]
0x180008d42  mov     ebp, 50h ; 'P'
0x180008d47  cmp     qword ptr [rax+18h], 0
0x180008d4c  jnz     short loc_180008D83
0x180008d4e  test    esi, esi
0x180008d50  jz      short loc_180008D83
0x180008d52  mov     edx, 190h; dwBytes
0x180008d57  lea     ecx, [rbp-48h]; dwFlags
0x180008d5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008d5f  mov     [rbx+18h], rax
0x180008d63  test    rax, rax
0x180008d66  jz      short loc_180008D83
0x180008d68  mov     dword ptr [rbx+20h], 5
0x180008d6f  lea     rcx, [rax+190h]
0x180008d76  jmp     short loc_180008D7E
0x180008d78  mov     [rax], bp
0x180008d7b  add     rax, rbp
0x180008d7e  cmp     rax, rcx
0x180008d81  jnz     short loc_180008D78
0x180008d83  mov     r9, [rbx+18h]
0x180008d87  test    r9, r9
0x180008d8a  jz      short loc_180008DFB
0x180008d8c  test    esi, esi
0x180008d8e  jz      short loc_180008DC1
0x180008d90  mov     rcx, r9
0x180008d93  movzx   eax, word ptr [rbx+20h]
0x180008d97  lea     rdx, [rax+rax*4]
0x180008d9b  shl     rdx, 4
0x180008d9f  add     rdx, r9
0x180008da2  cmp     r9, rdx
0x180008da5  jz      short loc_180008DC1
0x180008da7  mov     r8d, [rbx+10h]
0x180008dab  cmp     [rcx+4], r8d
0x180008daf  jbe     short loc_180008DB9
0x180008db1  mov     eax, [rdi+8]
0x180008db4  cmp     [rcx+8], eax
0x180008db7  jz      short loc_180008DFB
0x180008db9  add     rcx, rbp
0x180008dbc  cmp     rcx, rdx
0x180008dbf  jnz     short loc_180008DAB
0x180008dc1  movzx   eax, word ptr [rbx+22h]
0x180008dc5  inc     eax
0x180008dc7  movzx   ecx, word ptr [rbx+20h]
0x180008dcb  xor     edx, edx
0x180008dcd  div     ecx
0x180008dcf  mov     [rbx+22h], dx
0x180008dd3  mov     rax, [rbx+8]
0x180008dd7  mov     r8d, 1
0x180008ddd  lock xadd [rax], r8d
0x180008de2  inc     r8d; unsigned int
0x180008de5  movzx   eax, dx
0x180008de8  lea     rcx, [rax+rax*4]
0x180008dec  shl     rcx, 4
0x180008df0  add     rcx, r9; this
0x180008df3  mov     rdx, rdi; struct wil::FailureInfo *
0x180008df6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008dfb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008e05  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008e0c  add     rsp, 20h
0x180008e10  pop     r14
0x180008e12  pop     rdi
0x180008e13  pop     rsi
0x180008e14  pop     rbp
0x180008e15  pop     rbx
0x180008e16  retn
```
