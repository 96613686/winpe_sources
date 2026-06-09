# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180036a08`
- end: `0x180036ac2`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036ad0`

## callees

- `0x180036a08`
- `0x180036e60`
- `0x180037030`
- `0x18004d010`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  char v3; // r14
  struct wil::FailureInfo *v6; // rdi
  char v7; // bp
  struct wil::details::ThreadFailureCallbackHolder **Local; // rax
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v3 = 0;
  *a2 = 0;
  v6 = a1;
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
        if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v6, *Local, a2, a3) )
          *((_QWORD *)v6 + 9) = a2;
        v10 = *v9;
        do
        {
          v11 = *((_BYTE *)v10 + 40);
          *((_BYTE *)v10 + 40) = 1;
          if ( !v11 )
          {
            v3 |= (***((__int64 (__fastcall ****)(_QWORD, struct wil::FailureInfo *))v10 + 1))(*((_QWORD *)v10 + 1), v6);
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
    if ( !v3 && (*((_BYTE *)v6 + 4) & 2) == 0 )
      v7 = 0;
    LOBYTE(a1) = v7;
    wil::details::g_pfnTelemetryCallback(a1, v6);
  }
}

```

## disassembly

```asm
0x180036a08  push    rbx
0x180036a0a  push    rbp
0x180036a0b  push    rsi
0x180036a0c  push    rdi
0x180036a0d  push    r14
0x180036a0f  push    r15
0x180036a11  sub     rsp, 28h
0x180036a15  xor     r14b, r14b
0x180036a18  mov     byte ptr [rdx], 0
0x180036a1b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180036a23  mov     r15, r8
0x180036a26  mov     rsi, rdx
0x180036a29  mov     rdi, rcx
0x180036a2c  mov     bpl, 1
0x180036a2f  jz      short loc_180036A90
0x180036a31  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180036a36  mov     rbx, rax
0x180036a39  test    rax, rax
0x180036a3c  jz      short loc_180036A90
0x180036a3e  cmp     qword ptr [rax], 0
0x180036a42  jz      short loc_180036A90
0x180036a44  mov     [rsi], r14b
0x180036a47  mov     r9, r15; unsigned __int64
0x180036a4a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180036a4d  mov     r8, rsi; char *
0x180036a50  mov     rcx, rdi; struct wil::FailureInfo *
0x180036a53  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180036a58  test    al, al
0x180036a5a  jz      short loc_180036A60
0x180036a5c  mov     [rdi+48h], rsi
0x180036a60  mov     rbx, [rbx]
0x180036a63  mov     al, [rbx+28h]
0x180036a66  mov     [rbx+28h], bpl
0x180036a6a  test    al, al
0x180036a6c  jnz     short loc_180036A87
0x180036a6e  mov     rcx, [rbx+8]
0x180036a72  mov     rdx, rdi
0x180036a75  mov     rax, [rcx]
0x180036a78  mov     rax, [rax]
0x180036a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a80  or      r14b, al
0x180036a83  mov     byte ptr [rbx+28h], 0
0x180036a87  mov     rbx, [rbx+10h]
0x180036a8b  test    rbx, rbx
0x180036a8e  jnz     short loc_180036A63
0x180036a90  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180036a97  test    rax, rax
0x180036a9a  jz      short loc_180036AB4
0x180036a9c  test    r14b, r14b
0x180036a9f  jnz     short loc_180036AA9
0x180036aa1  test    byte ptr [rdi+4], 2
0x180036aa5  jnz     short loc_180036AA9
0x180036aa7  xor     ebp, ebp
0x180036aa9  mov     rdx, rdi
0x180036aac  mov     cl, bpl
0x180036aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ab4  add     rsp, 28h
0x180036ab8  pop     r15
0x180036aba  pop     r14
0x180036abc  pop     rdi
0x180036abd  pop     rsi
0x180036abe  pop     rbp
0x180036abf  pop     rbx
0x180036ac0  retn
```
