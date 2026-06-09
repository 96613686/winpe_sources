# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000d124`
- end: `0x18000d1df`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d1f0`

## callees

- `0x18000d124`
- `0x18000d320`
- `0x18000d524`
- `0x18001e010`

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
0x18000d124  push    rbx
0x18000d126  push    rbp
0x18000d127  push    rsi
0x18000d128  push    rdi
0x18000d129  push    r14
0x18000d12b  push    r15
0x18000d12d  sub     rsp, 28h
0x18000d131  mov     r15, r8
0x18000d134  mov     rsi, rdx
0x18000d137  mov     rdi, rcx
0x18000d13a  mov     byte ptr [rdx], 0
0x18000d13d  xor     r14b, r14b
0x18000d140  mov     bpl, 1
0x18000d143  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d14b  jz      short loc_18000D1AC
0x18000d14d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000d152  mov     rbx, rax
0x18000d155  test    rax, rax
0x18000d158  jz      short loc_18000D1AC
0x18000d15a  cmp     qword ptr [rax], 0
0x18000d15e  jz      short loc_18000D1AC
0x18000d160  mov     [rsi], r14b
0x18000d163  mov     r9, r15; unsigned __int64
0x18000d166  mov     r8, rsi; char *
0x18000d169  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d16c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000d16f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d174  test    al, al
0x18000d176  jz      short loc_18000D17C
0x18000d178  mov     [rdi+48h], rsi
0x18000d17c  mov     rbx, [rbx]
0x18000d17f  mov     al, [rbx+28h]
0x18000d182  mov     [rbx+28h], bpl
0x18000d186  test    al, al
0x18000d188  jnz     short loc_18000D1A3
0x18000d18a  mov     rcx, [rbx+8]
0x18000d18e  mov     rax, [rcx]
0x18000d191  mov     rdx, rdi
0x18000d194  mov     rax, [rax]
0x18000d197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19c  or      r14b, al
0x18000d19f  mov     byte ptr [rbx+28h], 0
0x18000d1a3  mov     rbx, [rbx+10h]
0x18000d1a7  test    rbx, rbx
0x18000d1aa  jnz     short loc_18000D17F
0x18000d1ac  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d1b3  test    rax, rax
0x18000d1b6  jz      short loc_18000D1D1
0x18000d1b8  test    r14b, r14b
0x18000d1bb  jnz     short loc_18000D1C5
0x18000d1bd  test    byte ptr [rdi+4], 2
0x18000d1c1  jnz     short loc_18000D1C5
0x18000d1c3  xor     ebp, ebp
0x18000d1c5  mov     rdx, rdi
0x18000d1c8  mov     cl, bpl
0x18000d1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d0  nop
0x18000d1d1  add     rsp, 28h
0x18000d1d5  pop     r15
0x18000d1d7  pop     r14
0x18000d1d9  pop     rdi
0x18000d1da  pop     rsi
0x18000d1db  pop     rbp
0x18000d1dc  pop     rbx
0x18000d1dd  retn
```
