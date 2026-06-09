# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007be8`
- end: `0x180007ca2`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007cb0`

## callees

- `0x180007be8`
- `0x1800080bc`
- `0x180008244`
- `0x18000e010`

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
0x180007be8  push    rbx
0x180007bea  push    rbp
0x180007beb  push    rsi
0x180007bec  push    rdi
0x180007bed  push    r14
0x180007bef  push    r15
0x180007bf1  sub     rsp, 28h
0x180007bf5  mov     r15, r8
0x180007bf8  mov     rsi, rdx
0x180007bfb  mov     rdi, rcx
0x180007bfe  mov     byte ptr [rdx], 0
0x180007c01  xor     r14b, r14b
0x180007c04  mov     bpl, 1
0x180007c07  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007c0f  jz      short loc_180007C70
0x180007c11  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180007c16  mov     rbx, rax
0x180007c19  test    rax, rax
0x180007c1c  jz      short loc_180007C70
0x180007c1e  cmp     qword ptr [rax], 0
0x180007c22  jz      short loc_180007C70
0x180007c24  mov     [rsi], r14b
0x180007c27  mov     r9, r15; unsigned __int64
0x180007c2a  mov     r8, rsi; char *
0x180007c2d  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180007c30  mov     rcx, rdi; struct wil::FailureInfo *
0x180007c33  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007c38  test    al, al
0x180007c3a  jz      short loc_180007C40
0x180007c3c  mov     [rdi+48h], rsi
0x180007c40  mov     rbx, [rbx]
0x180007c43  mov     al, [rbx+28h]
0x180007c46  mov     [rbx+28h], bpl
0x180007c4a  test    al, al
0x180007c4c  jnz     short loc_180007C67
0x180007c4e  mov     rcx, [rbx+8]
0x180007c52  mov     rax, [rcx]
0x180007c55  mov     rdx, rdi
0x180007c58  mov     rax, [rax]
0x180007c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c60  or      r14b, al
0x180007c63  mov     byte ptr [rbx+28h], 0
0x180007c67  mov     rbx, [rbx+10h]
0x180007c6b  test    rbx, rbx
0x180007c6e  jnz     short loc_180007C43
0x180007c70  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007c77  test    rax, rax
0x180007c7a  jz      short loc_180007C95
0x180007c7c  test    r14b, r14b
0x180007c7f  jnz     short loc_180007C89
0x180007c81  test    byte ptr [rdi+4], 2
0x180007c85  jnz     short loc_180007C89
0x180007c87  xor     ebp, ebp
0x180007c89  mov     rdx, rdi
0x180007c8c  mov     cl, bpl
0x180007c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c94  nop
0x180007c95  add     rsp, 28h
0x180007c99  pop     r15
0x180007c9b  pop     r14
0x180007c9d  pop     rdi
0x180007c9e  pop     rsi
0x180007c9f  pop     rbp
0x180007ca0  pop     rbx
0x180007ca1  retn
```
