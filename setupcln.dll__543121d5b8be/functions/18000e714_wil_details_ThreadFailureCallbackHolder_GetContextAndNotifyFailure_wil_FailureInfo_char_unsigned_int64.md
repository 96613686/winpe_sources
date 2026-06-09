# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000e714`
- end: `0x18000e7ce`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e7e0`

## callees

- `0x18000e714`
- `0x18000ebec`
- `0x18000f0c8`
- `0x180014010`

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
0x18000e714  push    rbx
0x18000e716  push    rbp
0x18000e717  push    rsi
0x18000e718  push    rdi
0x18000e719  push    r14
0x18000e71b  push    r15
0x18000e71d  sub     rsp, 28h
0x18000e721  mov     r15, r8
0x18000e724  mov     rsi, rdx
0x18000e727  mov     rdi, rcx
0x18000e72a  mov     byte ptr [rdx], 0
0x18000e72d  xor     r14b, r14b
0x18000e730  mov     bpl, 1
0x18000e733  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e73b  jz      short loc_18000E79C
0x18000e73d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000e742  mov     rbx, rax
0x18000e745  test    rax, rax
0x18000e748  jz      short loc_18000E79C
0x18000e74a  cmp     qword ptr [rax], 0
0x18000e74e  jz      short loc_18000E79C
0x18000e750  mov     [rsi], r14b
0x18000e753  mov     r9, r15; unsigned __int64
0x18000e756  mov     r8, rsi; char *
0x18000e759  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000e75c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000e75f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000e764  test    al, al
0x18000e766  jz      short loc_18000E76C
0x18000e768  mov     [rdi+48h], rsi
0x18000e76c  mov     rbx, [rbx]
0x18000e76f  mov     al, [rbx+28h]
0x18000e772  mov     [rbx+28h], bpl
0x18000e776  test    al, al
0x18000e778  jnz     short loc_18000E793
0x18000e77a  mov     rcx, [rbx+8]
0x18000e77e  mov     rax, [rcx]
0x18000e781  mov     rdx, rdi
0x18000e784  mov     rax, [rax]
0x18000e787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e78c  or      r14b, al
0x18000e78f  mov     byte ptr [rbx+28h], 0
0x18000e793  mov     rbx, [rbx+10h]
0x18000e797  test    rbx, rbx
0x18000e79a  jnz     short loc_18000E76F
0x18000e79c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000e7a3  test    rax, rax
0x18000e7a6  jz      short loc_18000E7C1
0x18000e7a8  test    r14b, r14b
0x18000e7ab  jnz     short loc_18000E7B5
0x18000e7ad  test    byte ptr [rdi+4], 2
0x18000e7b1  jnz     short loc_18000E7B5
0x18000e7b3  xor     ebp, ebp
0x18000e7b5  mov     rdx, rdi
0x18000e7b8  mov     cl, bpl
0x18000e7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c0  nop
0x18000e7c1  add     rsp, 28h
0x18000e7c5  pop     r15
0x18000e7c7  pop     r14
0x18000e7c9  pop     rdi
0x18000e7ca  pop     rsi
0x18000e7cb  pop     rbp
0x18000e7cc  pop     rbx
0x18000e7cd  retn
```
