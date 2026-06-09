# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002a73c`
- end: `0x18002a837`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a840`

## callees

- `0x18002a73c`
- `0x18002ad10`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a76b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a76b`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  __int64 v8; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  v5 = (struct wil::FailureInfo *)a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  v8 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v8 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v5);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v6 && (*((_BYTE *)v5 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v5);
  }
}

```

## disassembly

```asm
0x18002a73c  push    rbx
0x18002a73e  push    rbp
0x18002a73f  push    rsi
0x18002a740  push    rdi
0x18002a741  push    r14
0x18002a743  push    r15
0x18002a745  sub     rsp, 28h
0x18002a749  mov     r15, r8
0x18002a74c  mov     rsi, rdx
0x18002a74f  mov     rdi, rcx
0x18002a752  mov     byte ptr [rdx], 0
0x18002a755  xor     r14b, r14b
0x18002a758  mov     bpl, 1
0x18002a75b  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a762  test    rbx, rbx
0x18002a765  jz      loc_18002A805
0x18002a76b  call    cs:__imp_GetCurrentThreadId
0x18002a771  mov     r9d, eax
0x18002a774  mov     r8d, eax
0x18002a777  shr     r8, 2
0x18002a77b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002a785  mul     r8
0x18002a788  shr     rdx, 3
0x18002a78c  lea     rcx, [rdx+rdx*4]
0x18002a790  add     rcx, rcx
0x18002a793  sub     r8, rcx
0x18002a796  mov     rbx, [rbx+r8*8]
0x18002a79a  test    rbx, rbx
0x18002a79d  jz      short loc_18002A7AE
0x18002a79f  cmp     [rbx], r9d
0x18002a7a2  jz      short loc_18002A7AA
0x18002a7a4  mov     rbx, [rbx+8]
0x18002a7a8  jmp     short loc_18002A79A
0x18002a7aa  add     rbx, 10h
0x18002a7ae  test    rbx, rbx
0x18002a7b1  jz      short loc_18002A805
0x18002a7b3  cmp     qword ptr [rbx], 0
0x18002a7b7  jz      short loc_18002A805
0x18002a7b9  mov     [rsi], r14b
0x18002a7bc  mov     r9, r15; unsigned __int64
0x18002a7bf  mov     r8, rsi; char *
0x18002a7c2  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002a7c5  mov     rcx, rdi; struct wil::FailureInfo *
0x18002a7c8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002a7cd  test    al, al
0x18002a7cf  jz      short loc_18002A7D5
0x18002a7d1  mov     [rdi+48h], rsi
0x18002a7d5  mov     rbx, [rbx]
0x18002a7d8  mov     al, [rbx+28h]
0x18002a7db  mov     [rbx+28h], bpl
0x18002a7df  test    al, al
0x18002a7e1  jnz     short loc_18002A7FC
0x18002a7e3  mov     rcx, [rbx+8]
0x18002a7e7  mov     rax, [rcx]
0x18002a7ea  mov     rdx, rdi
0x18002a7ed  mov     rax, [rax]
0x18002a7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7f5  or      r14b, al
0x18002a7f8  mov     byte ptr [rbx+28h], 0
0x18002a7fc  mov     rbx, [rbx+10h]
0x18002a800  test    rbx, rbx
0x18002a803  jnz     short loc_18002A7D8
0x18002a805  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002a80c  test    rax, rax
0x18002a80f  jz      short loc_18002A82A
0x18002a811  test    r14b, r14b
0x18002a814  jnz     short loc_18002A81E
0x18002a816  test    byte ptr [rdi+4], 2
0x18002a81a  jnz     short loc_18002A81E
0x18002a81c  xor     ebp, ebp
0x18002a81e  mov     rdx, rdi
0x18002a821  mov     cl, bpl
0x18002a824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a829  nop
0x18002a82a  add     rsp, 28h
0x18002a82e  pop     r15
0x18002a830  pop     r14
0x18002a832  pop     rdi
0x18002a833  pop     rsi
0x18002a834  pop     rbp
0x18002a835  pop     rbx
0x18002a836  retn
```
