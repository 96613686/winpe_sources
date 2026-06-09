# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008b28`
- end: `0x180008be1`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008bf0`

## callees

- `0x180008b28`
- `0x180008f60`
- `0x1800090a4`
- `0x180010010`

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
0x180008b28  push    rbx
0x180008b2a  push    rbp
0x180008b2b  push    rsi
0x180008b2c  push    rdi
0x180008b2d  push    r14
0x180008b2f  push    r15
0x180008b31  sub     rsp, 28h
0x180008b35  xor     r14b, r14b
0x180008b38  mov     byte ptr [rdx], 0
0x180008b3b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008b43  mov     r15, r8
0x180008b46  mov     rsi, rdx
0x180008b49  mov     rdi, rcx
0x180008b4c  mov     bpl, 1
0x180008b4f  jz      short loc_180008BB0
0x180008b51  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008b56  mov     rbx, rax
0x180008b59  test    rax, rax
0x180008b5c  jz      short loc_180008BB0
0x180008b5e  cmp     qword ptr [rax], 0
0x180008b62  jz      short loc_180008BB0
0x180008b64  mov     [rsi], r14b
0x180008b67  mov     r9, r15; unsigned __int64
0x180008b6a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180008b6d  mov     r8, rsi; char *
0x180008b70  mov     rcx, rdi; struct wil::FailureInfo *
0x180008b73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008b78  test    al, al
0x180008b7a  jz      short loc_180008B80
0x180008b7c  mov     [rdi+48h], rsi
0x180008b80  mov     rbx, [rbx]
0x180008b83  mov     al, [rbx+28h]
0x180008b86  mov     [rbx+28h], bpl
0x180008b8a  test    al, al
0x180008b8c  jnz     short loc_180008BA7
0x180008b8e  mov     rcx, [rbx+8]
0x180008b92  mov     rdx, rdi
0x180008b95  mov     rax, [rcx]
0x180008b98  mov     rax, [rax]
0x180008b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba0  or      r14b, al
0x180008ba3  mov     byte ptr [rbx+28h], 0
0x180008ba7  mov     rbx, [rbx+10h]
0x180008bab  test    rbx, rbx
0x180008bae  jnz     short loc_180008B83
0x180008bb0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008bb7  test    rax, rax
0x180008bba  jz      short loc_180008BD4
0x180008bbc  test    r14b, r14b
0x180008bbf  jnz     short loc_180008BC9
0x180008bc1  test    byte ptr [rdi+4], 2
0x180008bc5  jnz     short loc_180008BC9
0x180008bc7  xor     ebp, ebp
0x180008bc9  mov     rdx, rdi
0x180008bcc  mov     cl, bpl
0x180008bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd4  add     rsp, 28h
0x180008bd8  pop     r15
0x180008bda  pop     r14
0x180008bdc  pop     rdi
0x180008bdd  pop     rsi
0x180008bde  pop     rbp
0x180008bdf  pop     rbx
0x180008be0  retn
```
