# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18002b308`
- end: `0x18002b409`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `257`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b410`

## callees

- `0x18002b308`
- `0x18002b8c8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b337`

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
0x18002b308  push    rbx
0x18002b30a  push    rbp
0x18002b30b  push    rsi
0x18002b30c  push    rdi
0x18002b30d  push    r14
0x18002b30f  push    r15
0x18002b311  sub     rsp, 28h
0x18002b315  mov     byte ptr [rdx], 0
0x18002b318  xor     r14b, r14b
0x18002b31b  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002b322  mov     r15, r8
0x18002b325  mov     rsi, rdx
0x18002b328  mov     rdi, rcx
0x18002b32b  mov     bpl, 1
0x18002b32e  test    rbx, rbx
0x18002b331  jz      loc_18002B3D7
0x18002b337  call    cs:__imp_GetCurrentThreadId
0x18002b33e  nop     dword ptr [rax+rax+00h]
0x18002b343  mov     r8d, eax
0x18002b346  mov     r9d, eax
0x18002b349  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002b353  shr     r8, 2
0x18002b357  mul     r8
0x18002b35a  shr     rdx, 3
0x18002b35e  lea     rcx, [rdx+rdx*4]
0x18002b362  add     rcx, rcx
0x18002b365  sub     r8, rcx
0x18002b368  mov     rbx, [rbx+r8*8]
0x18002b36c  test    rbx, rbx
0x18002b36f  jz      short loc_18002B380
0x18002b371  cmp     [rbx], r9d
0x18002b374  jz      short loc_18002B37C
0x18002b376  mov     rbx, [rbx+8]
0x18002b37a  jmp     short loc_18002B36C
0x18002b37c  add     rbx, 10h
0x18002b380  test    rbx, rbx
0x18002b383  jz      short loc_18002B3D7
0x18002b385  cmp     qword ptr [rbx], 0
0x18002b389  jz      short loc_18002B3D7
0x18002b38b  mov     [rsi], r14b
0x18002b38e  mov     r9, r15; unsigned __int64
0x18002b391  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002b394  mov     r8, rsi; char *
0x18002b397  mov     rcx, rdi; struct wil::FailureInfo *
0x18002b39a  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002b39f  test    al, al
0x18002b3a1  jz      short loc_18002B3A7
0x18002b3a3  mov     [rdi+48h], rsi
0x18002b3a7  mov     rbx, [rbx]
0x18002b3aa  mov     al, [rbx+28h]
0x18002b3ad  mov     [rbx+28h], bpl
0x18002b3b1  test    al, al
0x18002b3b3  jnz     short loc_18002B3CE
0x18002b3b5  mov     rcx, [rbx+8]
0x18002b3b9  mov     rdx, rdi
0x18002b3bc  mov     rax, [rcx]
0x18002b3bf  mov     rax, [rax]
0x18002b3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3c7  or      r14b, al
0x18002b3ca  mov     byte ptr [rbx+28h], 0
0x18002b3ce  mov     rbx, [rbx+10h]
0x18002b3d2  test    rbx, rbx
0x18002b3d5  jnz     short loc_18002B3AA
0x18002b3d7  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18002b3de  test    rax, rax
0x18002b3e1  jz      short loc_18002B3FB
0x18002b3e3  test    r14b, r14b
0x18002b3e6  jnz     short loc_18002B3F0
0x18002b3e8  test    byte ptr [rdi+4], 2
0x18002b3ec  jnz     short loc_18002B3F0
0x18002b3ee  xor     ebp, ebp
0x18002b3f0  mov     rdx, rdi
0x18002b3f3  mov     cl, bpl
0x18002b3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3fb  add     rsp, 28h
0x18002b3ff  pop     r15
0x18002b401  pop     r14
0x18002b403  pop     rdi
0x18002b404  pop     rsi
0x18002b405  pop     rbp
0x18002b406  pop     rbx
0x18002b407  retn
```
