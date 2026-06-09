# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005a64`
- end: `0x180005b1e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005b30`

## callees

- `0x180005a64`
- `0x18000613c`
- `0x180006350`
- `0x18001d010`

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
0x180005a64  push    rbx
0x180005a66  push    rbp
0x180005a67  push    rsi
0x180005a68  push    rdi
0x180005a69  push    r14
0x180005a6b  push    r15
0x180005a6d  sub     rsp, 28h
0x180005a71  mov     r15, r8
0x180005a74  mov     rsi, rdx
0x180005a77  mov     rdi, rcx
0x180005a7a  mov     byte ptr [rdx], 0
0x180005a7d  xor     r14b, r14b
0x180005a80  mov     bpl, 1
0x180005a83  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005a8b  jz      short loc_180005AEC
0x180005a8d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180005a92  mov     rbx, rax
0x180005a95  test    rax, rax
0x180005a98  jz      short loc_180005AEC
0x180005a9a  cmp     qword ptr [rax], 0
0x180005a9e  jz      short loc_180005AEC
0x180005aa0  mov     [rsi], r14b
0x180005aa3  mov     r9, r15; unsigned __int64
0x180005aa6  mov     r8, rsi; char *
0x180005aa9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180005aac  mov     rcx, rdi; struct wil::FailureInfo *
0x180005aaf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005ab4  test    al, al
0x180005ab6  jz      short loc_180005ABC
0x180005ab8  mov     [rdi+48h], rsi
0x180005abc  mov     rbx, [rbx]
0x180005abf  mov     al, [rbx+28h]
0x180005ac2  mov     [rbx+28h], bpl
0x180005ac6  test    al, al
0x180005ac8  jnz     short loc_180005AE3
0x180005aca  mov     rcx, [rbx+8]
0x180005ace  mov     rax, [rcx]
0x180005ad1  mov     rdx, rdi
0x180005ad4  mov     rax, [rax]
0x180005ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005adc  or      r14b, al
0x180005adf  mov     byte ptr [rbx+28h], 0
0x180005ae3  mov     rbx, [rbx+10h]
0x180005ae7  test    rbx, rbx
0x180005aea  jnz     short loc_180005ABF
0x180005aec  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005af3  test    rax, rax
0x180005af6  jz      short loc_180005B11
0x180005af8  test    r14b, r14b
0x180005afb  jnz     short loc_180005B05
0x180005afd  test    byte ptr [rdi+4], 2
0x180005b01  jnz     short loc_180005B05
0x180005b03  xor     ebp, ebp
0x180005b05  mov     rdx, rdi
0x180005b08  mov     cl, bpl
0x180005b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b10  nop
0x180005b11  add     rsp, 28h
0x180005b15  pop     r15
0x180005b17  pop     r14
0x180005b19  pop     rdi
0x180005b1a  pop     rsi
0x180005b1b  pop     rbp
0x180005b1c  pop     rbx
0x180005b1d  retn
```
