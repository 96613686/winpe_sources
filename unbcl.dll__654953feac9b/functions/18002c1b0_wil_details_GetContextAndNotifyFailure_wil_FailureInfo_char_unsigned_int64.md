# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002c1b0`
- end: `0x18002c2ff`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `335`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002c1b0`
- `0x18002d3b4`
- `0x18002d498`
- `0x18003038c`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002c1e3`
- `KERNEL32!GetCurrentThreadId` at `0x18002c2a4`
- `KERNEL32!GetCurrentThreadId` at `0x18002c1e3`
- `KERNEL32!GetCurrentThreadId` at `0x18002c2a4`

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
0x18002c1b0  push    rbx
0x18002c1b2  push    rbp
0x18002c1b3  push    rsi
0x18002c1b4  push    rdi
0x18002c1b5  push    r14
0x18002c1b7  sub     rsp, 30h
0x18002c1bb  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18002c1c4  mov     r14, r8
0x18002c1c7  mov     rsi, rdx
0x18002c1ca  mov     rdi, rcx
0x18002c1cd  mov     byte ptr [rdx], 0
0x18002c1d0  xor     bpl, bpl
0x18002c1d3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002c1da  test    rbx, rbx
0x18002c1dd  jz      loc_18002C279
0x18002c1e3  call    cs:__imp_GetCurrentThreadId
0x18002c1e9  mov     r9d, eax
0x18002c1ec  mov     r8d, eax
0x18002c1ef  shr     r8, 2
0x18002c1f3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002c1fd  mul     r8
0x18002c200  shr     rdx, 3
0x18002c204  lea     rcx, [rdx+rdx*4]
0x18002c208  add     rcx, rcx
0x18002c20b  sub     r8, rcx
0x18002c20e  mov     rbx, [rbx+r8*8]
0x18002c212  jmp     short loc_18002C21D
0x18002c214  cmp     [rbx], r9d
0x18002c217  jz      short loc_18002C294
0x18002c219  mov     rbx, [rbx+8]
0x18002c21d  test    rbx, rbx
0x18002c220  jnz     short loc_18002C214
0x18002c222  test    rbx, rbx
0x18002c225  jz      short loc_18002C279
0x18002c227  cmp     qword ptr [rbx], 0
0x18002c22b  jz      short loc_18002C279
0x18002c22d  mov     [rsi], bpl
0x18002c230  mov     r9, r14; unsigned __int64
0x18002c233  mov     r8, rsi; char *
0x18002c236  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002c239  mov     rcx, rdi; struct wil::FailureInfo *
0x18002c23c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002c241  test    al, al
0x18002c243  jz      short loc_18002C249
0x18002c245  mov     [rdi+48h], rsi
0x18002c249  mov     rbx, [rbx]
0x18002c24c  mov     al, [rbx+28h]
0x18002c24f  mov     byte ptr [rbx+28h], 1
0x18002c253  test    al, al
0x18002c255  jnz     short loc_18002C270
0x18002c257  mov     rcx, [rbx+8]
0x18002c25b  mov     rax, [rcx]
0x18002c25e  mov     rdx, rdi
0x18002c261  mov     rax, [rax]
0x18002c264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c269  or      bpl, al
0x18002c26c  mov     byte ptr [rbx+28h], 0
0x18002c270  mov     rbx, [rbx+10h]
0x18002c274  test    rbx, rbx
0x18002c277  jnz     short loc_18002C24C
0x18002c279  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002c280  test    rax, rax
0x18002c283  jz      short loc_18002C2A4
0x18002c285  test    bpl, bpl
0x18002c288  jnz     short loc_18002C29A
0x18002c28a  test    byte ptr [rdi+4], 2
0x18002c28e  jnz     short loc_18002C29A
0x18002c290  xor     ecx, ecx
0x18002c292  jmp     short loc_18002C29C
0x18002c294  add     rbx, 10h
0x18002c298  jmp     short loc_18002C222
0x18002c29a  mov     cl, 1
0x18002c29c  mov     rdx, rdi
0x18002c29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2a4  call    cs:__imp_GetCurrentThreadId
0x18002c2aa  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002c2b0  cmp     ecx, eax
0x18002c2b2  jz      short loc_18002C2F4
0x18002c2b4  mov     ecx, 1
0x18002c2b9  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002c2c1  inc     ecx; this
0x18002c2c3  cmp     ecx, 4
0x18002c2c6  jge     short loc_18002C2ED
0x18002c2c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002c2ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18002c2d3  test    rax, rax
0x18002c2d6  jz      short loc_18002C2E3
0x18002c2d8  mov     rdx, rdi; struct wil::FailureInfo *
0x18002c2db  mov     rcx, rax; this
0x18002c2de  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18002c2e3  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002c2ed  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002c2f4  add     rsp, 30h
0x18002c2f8  pop     r14
0x18002c2fa  pop     rdi
0x18002c2fb  pop     rsi
0x18002c2fc  pop     rbp
0x18002c2fd  pop     rbx
0x18002c2fe  retn
```
