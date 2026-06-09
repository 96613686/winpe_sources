# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003a18`
- end: `0x180003b13`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `251`
- prototype: `void __fastcall(unsigned __int64, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b20`

## callees

- `0x180003a18`
- `0x180004058`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a47`

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
0x180003a18  push    rbx
0x180003a1a  push    rbp
0x180003a1b  push    rsi
0x180003a1c  push    rdi
0x180003a1d  push    r14
0x180003a1f  push    r15
0x180003a21  sub     rsp, 28h
0x180003a25  mov     r15, r8
0x180003a28  mov     rsi, rdx
0x180003a2b  mov     rdi, rcx
0x180003a2e  mov     byte ptr [rdx], 0
0x180003a31  xor     r14b, r14b
0x180003a34  mov     bpl, 1
0x180003a37  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003a3e  test    rbx, rbx
0x180003a41  jz      loc_180003AE1
0x180003a47  call    cs:__imp_GetCurrentThreadId
0x180003a4d  mov     r9d, eax
0x180003a50  mov     r8d, eax
0x180003a53  shr     r8, 2
0x180003a57  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003a61  mul     r8
0x180003a64  shr     rdx, 3
0x180003a68  lea     rcx, [rdx+rdx*4]
0x180003a6c  add     rcx, rcx
0x180003a6f  sub     r8, rcx
0x180003a72  mov     rbx, [rbx+r8*8]
0x180003a76  test    rbx, rbx
0x180003a79  jz      short loc_180003A8A
0x180003a7b  cmp     [rbx], r9d
0x180003a7e  jz      short loc_180003A86
0x180003a80  mov     rbx, [rbx+8]
0x180003a84  jmp     short loc_180003A76
0x180003a86  add     rbx, 10h
0x180003a8a  test    rbx, rbx
0x180003a8d  jz      short loc_180003AE1
0x180003a8f  cmp     qword ptr [rbx], 0
0x180003a93  jz      short loc_180003AE1
0x180003a95  mov     [rsi], r14b
0x180003a98  mov     r9, r15; unsigned __int64
0x180003a9b  mov     r8, rsi; char *
0x180003a9e  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003aa1  mov     rcx, rdi; struct wil::FailureInfo *
0x180003aa4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003aa9  test    al, al
0x180003aab  jz      short loc_180003AB1
0x180003aad  mov     [rdi+48h], rsi
0x180003ab1  mov     rbx, [rbx]
0x180003ab4  mov     al, [rbx+28h]
0x180003ab7  mov     [rbx+28h], bpl
0x180003abb  test    al, al
0x180003abd  jnz     short loc_180003AD8
0x180003abf  mov     rcx, [rbx+8]
0x180003ac3  mov     rax, [rcx]
0x180003ac6  mov     rdx, rdi
0x180003ac9  mov     rax, [rax]
0x180003acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ad1  or      r14b, al
0x180003ad4  mov     byte ptr [rbx+28h], 0
0x180003ad8  mov     rbx, [rbx+10h]
0x180003adc  test    rbx, rbx
0x180003adf  jnz     short loc_180003AB4
0x180003ae1  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003ae8  test    rax, rax
0x180003aeb  jz      short loc_180003B06
0x180003aed  test    r14b, r14b
0x180003af0  jnz     short loc_180003AFA
0x180003af2  test    byte ptr [rdi+4], 2
0x180003af6  jnz     short loc_180003AFA
0x180003af8  xor     ebp, ebp
0x180003afa  mov     rdx, rdi
0x180003afd  mov     cl, bpl
0x180003b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b05  nop
0x180003b06  add     rsp, 28h
0x180003b0a  pop     r15
0x180003b0c  pop     r14
0x180003b0e  pop     rdi
0x180003b0f  pop     rsi
0x180003b10  pop     rbp
0x180003b11  pop     rbx
0x180003b12  retn
```
