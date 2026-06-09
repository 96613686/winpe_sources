# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800142ec`
- end: `0x1800143a6`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800143b0`

## callees

- `0x1800142ec`
- `0x180014850`
- `0x180014a50`
- `0x180021010`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // r14
  char v7; // bp
  struct wil::details::ThreadFailureCallbackHolder **Local; // rax
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v5 = a1;
  *a2 = 0;
  v6 = 0;
  v7 = 1;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal();
    v9 = Local;
    if ( Local )
    {
      if ( *Local )
      {
        *a2 = 0;
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *Local, a2, a3) )
          *((_QWORD *)v5 + 9) = a2;
        v10 = *v9;
        do
        {
          v11 = *((_BYTE *)v10 + 40);
          *((_BYTE *)v10 + 40) = 1;
          if ( !v11 )
          {
            v6 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
            *((_BYTE *)v10 + 40) = 0;
          }
          v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
        }
        while ( v10 );
      }
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
0x1800142ec  push    rbx
0x1800142ee  push    rbp
0x1800142ef  push    rsi
0x1800142f0  push    rdi
0x1800142f1  push    r14
0x1800142f3  push    r15
0x1800142f5  sub     rsp, 28h
0x1800142f9  mov     r15, r8
0x1800142fc  mov     rsi, rdx
0x1800142ff  mov     rdi, rcx
0x180014302  mov     byte ptr [rdx], 0
0x180014305  xor     r14b, r14b
0x180014308  mov     bpl, 1
0x18001430b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014313  jz      short loc_180014374
0x180014315  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001431a  mov     rbx, rax
0x18001431d  test    rax, rax
0x180014320  jz      short loc_180014374
0x180014322  cmp     qword ptr [rax], 0
0x180014326  jz      short loc_180014374
0x180014328  mov     [rsi], r14b
0x18001432b  mov     r9, r15; unsigned __int64
0x18001432e  mov     r8, rsi; char *
0x180014331  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180014334  mov     rcx, rdi; struct wil::FailureInfo *
0x180014337  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001433c  test    al, al
0x18001433e  jz      short loc_180014344
0x180014340  mov     [rdi+48h], rsi
0x180014344  mov     rbx, [rbx]
0x180014347  mov     al, [rbx+28h]
0x18001434a  mov     [rbx+28h], bpl
0x18001434e  test    al, al
0x180014350  jnz     short loc_18001436B
0x180014352  mov     rcx, [rbx+8]
0x180014356  mov     rax, [rcx]
0x180014359  mov     rdx, rdi
0x18001435c  mov     rax, [rax]
0x18001435f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014364  or      r14b, al
0x180014367  mov     byte ptr [rbx+28h], 0
0x18001436b  mov     rbx, [rbx+10h]
0x18001436f  test    rbx, rbx
0x180014372  jnz     short loc_180014347
0x180014374  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001437b  test    rax, rax
0x18001437e  jz      short loc_180014399
0x180014380  test    r14b, r14b
0x180014383  jnz     short loc_18001438D
0x180014385  test    byte ptr [rdi+4], 2
0x180014389  jnz     short loc_18001438D
0x18001438b  xor     ebp, ebp
0x18001438d  mov     rdx, rdi
0x180014390  mov     cl, bpl
0x180014393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014398  nop
0x180014399  add     rsp, 28h
0x18001439d  pop     r15
0x18001439f  pop     r14
0x1800143a1  pop     rdi
0x1800143a2  pop     rsi
0x1800143a3  pop     rbp
0x1800143a4  pop     rbx
0x1800143a5  retn
```
