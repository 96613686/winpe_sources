# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180014ae8`
- end: `0x180014ba1`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014ca0`

## callees

- `0x180014ae8`
- `0x180077df8`
- `0x180077f80`
- `0x180086010`

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
0x180014ae8  push    rbx
0x180014aea  push    rbp
0x180014aeb  push    rsi
0x180014aec  push    rdi
0x180014aed  push    r14
0x180014aef  push    r15
0x180014af1  sub     rsp, 28h
0x180014af5  xor     r14b, r14b
0x180014af8  mov     byte ptr [rdx], 0
0x180014afb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014b03  mov     r15, r8
0x180014b06  mov     rsi, rdx
0x180014b09  mov     rdi, rcx
0x180014b0c  mov     bpl, 1
0x180014b0f  jz      short loc_180014B70
0x180014b11  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180014b16  mov     rbx, rax
0x180014b19  test    rax, rax
0x180014b1c  jz      short loc_180014B70
0x180014b1e  cmp     qword ptr [rax], 0
0x180014b22  jz      short loc_180014B70
0x180014b24  mov     [rsi], r14b
0x180014b27  mov     r9, r15; unsigned __int64
0x180014b2a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180014b2d  mov     r8, rsi; char *
0x180014b30  mov     rcx, rdi; struct wil::FailureInfo *
0x180014b33  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180014b38  test    al, al
0x180014b3a  jz      short loc_180014B40
0x180014b3c  mov     [rdi+48h], rsi
0x180014b40  mov     rbx, [rbx]
0x180014b43  mov     al, [rbx+28h]
0x180014b46  mov     [rbx+28h], bpl
0x180014b4a  test    al, al
0x180014b4c  jnz     short loc_180014B67
0x180014b4e  mov     rcx, [rbx+8]
0x180014b52  mov     rdx, rdi
0x180014b55  mov     rax, [rcx]
0x180014b58  mov     rax, [rax]
0x180014b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b60  or      r14b, al
0x180014b63  mov     byte ptr [rbx+28h], 0
0x180014b67  mov     rbx, [rbx+10h]
0x180014b6b  test    rbx, rbx
0x180014b6e  jnz     short loc_180014B43
0x180014b70  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180014b77  test    rax, rax
0x180014b7a  jz      short loc_180014B94
0x180014b7c  test    r14b, r14b
0x180014b7f  jnz     short loc_180014B89
0x180014b81  test    byte ptr [rdi+4], 2
0x180014b85  jnz     short loc_180014B89
0x180014b87  xor     ebp, ebp
0x180014b89  mov     rdx, rdi
0x180014b8c  mov     cl, bpl
0x180014b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b94  add     rsp, 28h
0x180014b98  pop     r15
0x180014b9a  pop     r14
0x180014b9c  pop     rdi
0x180014b9d  pop     rsi
0x180014b9e  pop     rbp
0x180014b9f  pop     rbx
0x180014ba0  retn
```
