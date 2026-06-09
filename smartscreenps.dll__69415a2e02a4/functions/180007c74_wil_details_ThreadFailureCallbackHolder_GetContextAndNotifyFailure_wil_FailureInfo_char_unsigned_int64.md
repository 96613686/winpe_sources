# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007c74`
- end: `0x180007d2f`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007d40`

## callees

- `0x180007c74`
- `0x180008174`
- `0x180008310`
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
0x180007c74  push    rbx
0x180007c76  push    rbp
0x180007c77  push    rsi
0x180007c78  push    rdi
0x180007c79  push    r14
0x180007c7b  push    r15
0x180007c7d  sub     rsp, 28h
0x180007c81  mov     r15, r8
0x180007c84  mov     rsi, rdx
0x180007c87  mov     rdi, rcx
0x180007c8a  mov     byte ptr [rdx], 0
0x180007c8d  xor     r14b, r14b
0x180007c90  mov     bpl, 1
0x180007c93  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007c9b  jz      short loc_180007CFC
0x180007c9d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180007ca2  mov     rbx, rax
0x180007ca5  test    rax, rax
0x180007ca8  jz      short loc_180007CFC
0x180007caa  cmp     qword ptr [rax], 0
0x180007cae  jz      short loc_180007CFC
0x180007cb0  mov     [rsi], r14b
0x180007cb3  mov     r9, r15; unsigned __int64
0x180007cb6  mov     r8, rsi; char *
0x180007cb9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180007cbc  mov     rcx, rdi; struct wil::FailureInfo *
0x180007cbf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007cc4  test    al, al
0x180007cc6  jz      short loc_180007CCC
0x180007cc8  mov     [rdi+48h], rsi
0x180007ccc  mov     rbx, [rbx]
0x180007ccf  mov     al, [rbx+28h]
0x180007cd2  mov     [rbx+28h], bpl
0x180007cd6  test    al, al
0x180007cd8  jnz     short loc_180007CF3
0x180007cda  mov     rcx, [rbx+8]
0x180007cde  mov     rax, [rcx]
0x180007ce1  mov     rdx, rdi
0x180007ce4  mov     rax, [rax]
0x180007ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cec  or      r14b, al
0x180007cef  mov     byte ptr [rbx+28h], 0
0x180007cf3  mov     rbx, [rbx+10h]
0x180007cf7  test    rbx, rbx
0x180007cfa  jnz     short loc_180007CCF
0x180007cfc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007d03  test    rax, rax
0x180007d06  jz      short loc_180007D21
0x180007d08  test    r14b, r14b
0x180007d0b  jnz     short loc_180007D15
0x180007d0d  test    byte ptr [rdi+4], 2
0x180007d11  jnz     short loc_180007D15
0x180007d13  xor     ebp, ebp
0x180007d15  mov     rdx, rdi
0x180007d18  mov     cl, bpl
0x180007d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d20  nop
0x180007d21  add     rsp, 28h
0x180007d25  pop     r15
0x180007d27  pop     r14
0x180007d29  pop     rdi
0x180007d2a  pop     rsi
0x180007d2b  pop     rbp
0x180007d2c  pop     rbx
0x180007d2d  retn
```
