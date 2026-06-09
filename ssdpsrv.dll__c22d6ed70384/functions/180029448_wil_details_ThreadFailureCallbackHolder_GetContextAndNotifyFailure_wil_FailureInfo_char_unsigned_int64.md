# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180029448`
- end: `0x180029542`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `250`
- prototype: `void __fastcall(unsigned __int64, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029550`

## callees

- `0x180029448`
- `0x1800299dc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029477`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3)
{
  char v3; // r14
  __int64 v4; // rbx
  struct wil::FailureInfo *v7; // rdi
  char v8; // bp
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v11; // rbx
  char v12; // al

  *a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (struct wil::FailureInfo *)a1;
  v8 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = 10 * ((CurrentThreadId >> 2) / 0xA);
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
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             a2,
             a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v11 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v12 = *((_BYTE *)v11 + 40);
        *((_BYTE *)v11 + 40) = 1;
        if ( !v12 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v11 + 1))(*((_QWORD *)v11 + 1), v7);
          *((_BYTE *)v11 + 40) = 0;
        }
        v11 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v11 + 2);
      }
      while ( v11 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( !v3 && (*((_BYTE *)v7 + 4) & 2) == 0 )
      v8 = 0;
    LOBYTE(a1) = v8;
    wil::details::g_pfnTelemetryCallback(a1, v7);
  }
}

```

## disassembly

```asm
0x180029448  push    rbx
0x18002944a  push    rbp
0x18002944b  push    rsi
0x18002944c  push    rdi
0x18002944d  push    r14
0x18002944f  push    r15
0x180029451  sub     rsp, 28h
0x180029455  mov     byte ptr [rdx], 0
0x180029458  xor     r14b, r14b
0x18002945b  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180029462  mov     r15, r8
0x180029465  mov     rsi, rdx
0x180029468  mov     rdi, rcx
0x18002946b  mov     bpl, 1
0x18002946e  test    rbx, rbx
0x180029471  jz      loc_180029511
0x180029477  call    cs:__imp_GetCurrentThreadId
0x18002947d  mov     r8d, eax
0x180029480  mov     r9d, eax
0x180029483  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002948d  shr     r8, 2
0x180029491  mul     r8
0x180029494  shr     rdx, 3
0x180029498  lea     rcx, [rdx+rdx*4]
0x18002949c  add     rcx, rcx
0x18002949f  sub     r8, rcx
0x1800294a2  mov     rbx, [rbx+r8*8]
0x1800294a6  test    rbx, rbx
0x1800294a9  jz      short loc_1800294BA
0x1800294ab  cmp     [rbx], r9d
0x1800294ae  jz      short loc_1800294B6
0x1800294b0  mov     rbx, [rbx+8]
0x1800294b4  jmp     short loc_1800294A6
0x1800294b6  add     rbx, 10h
0x1800294ba  test    rbx, rbx
0x1800294bd  jz      short loc_180029511
0x1800294bf  cmp     qword ptr [rbx], 0
0x1800294c3  jz      short loc_180029511
0x1800294c5  mov     [rsi], r14b
0x1800294c8  mov     r9, r15; unsigned __int64
0x1800294cb  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800294ce  mov     r8, rsi; char *
0x1800294d1  mov     rcx, rdi; struct wil::FailureInfo *
0x1800294d4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800294d9  test    al, al
0x1800294db  jz      short loc_1800294E1
0x1800294dd  mov     [rdi+48h], rsi
0x1800294e1  mov     rbx, [rbx]
0x1800294e4  mov     al, [rbx+28h]
0x1800294e7  mov     [rbx+28h], bpl
0x1800294eb  test    al, al
0x1800294ed  jnz     short loc_180029508
0x1800294ef  mov     rcx, [rbx+8]
0x1800294f3  mov     rdx, rdi
0x1800294f6  mov     rax, [rcx]
0x1800294f9  mov     rax, [rax]
0x1800294fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029501  or      r14b, al
0x180029504  mov     byte ptr [rbx+28h], 0
0x180029508  mov     rbx, [rbx+10h]
0x18002950c  test    rbx, rbx
0x18002950f  jnz     short loc_1800294E4
0x180029511  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180029518  test    rax, rax
0x18002951b  jz      short loc_180029535
0x18002951d  test    r14b, r14b
0x180029520  jnz     short loc_18002952A
0x180029522  test    byte ptr [rdi+4], 2
0x180029526  jnz     short loc_18002952A
0x180029528  xor     ebp, ebp
0x18002952a  mov     rdx, rdi
0x18002952d  mov     cl, bpl
0x180029530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029535  add     rsp, 28h
0x180029539  pop     r15
0x18002953b  pop     r14
0x18002953d  pop     rdi
0x18002953e  pop     rsi
0x18002953f  pop     rbp
0x180029540  pop     rbx
0x180029541  retn
```
