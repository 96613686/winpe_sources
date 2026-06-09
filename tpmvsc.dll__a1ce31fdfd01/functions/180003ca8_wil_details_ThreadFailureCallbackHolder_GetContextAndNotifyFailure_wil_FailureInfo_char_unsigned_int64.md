# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003ca8`
- end: `0x180003d62`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003d70`

## callees

- `0x180003ca8`
- `0x18000417c`
- `0x180004304`
- `0x180037010`

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
0x180003ca8  push    rbx
0x180003caa  push    rbp
0x180003cab  push    rsi
0x180003cac  push    rdi
0x180003cad  push    r14
0x180003caf  push    r15
0x180003cb1  sub     rsp, 28h
0x180003cb5  mov     r15, r8
0x180003cb8  mov     rsi, rdx
0x180003cbb  mov     rdi, rcx
0x180003cbe  mov     byte ptr [rdx], 0
0x180003cc1  xor     r14b, r14b
0x180003cc4  mov     bpl, 1
0x180003cc7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003ccf  jz      short loc_180003D30
0x180003cd1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180003cd6  mov     rbx, rax
0x180003cd9  test    rax, rax
0x180003cdc  jz      short loc_180003D30
0x180003cde  cmp     qword ptr [rax], 0
0x180003ce2  jz      short loc_180003D30
0x180003ce4  mov     [rsi], r14b
0x180003ce7  mov     r9, r15; unsigned __int64
0x180003cea  mov     r8, rsi; char *
0x180003ced  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180003cf0  mov     rcx, rdi; struct wil::FailureInfo *
0x180003cf3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003cf8  test    al, al
0x180003cfa  jz      short loc_180003D00
0x180003cfc  mov     [rdi+48h], rsi
0x180003d00  mov     rbx, [rbx]
0x180003d03  mov     al, [rbx+28h]
0x180003d06  mov     [rbx+28h], bpl
0x180003d0a  test    al, al
0x180003d0c  jnz     short loc_180003D27
0x180003d0e  mov     rcx, [rbx+8]
0x180003d12  mov     rax, [rcx]
0x180003d15  mov     rdx, rdi
0x180003d18  mov     rax, [rax]
0x180003d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d20  or      r14b, al
0x180003d23  mov     byte ptr [rbx+28h], 0
0x180003d27  mov     rbx, [rbx+10h]
0x180003d2b  test    rbx, rbx
0x180003d2e  jnz     short loc_180003D03
0x180003d30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003d37  test    rax, rax
0x180003d3a  jz      short loc_180003D55
0x180003d3c  test    r14b, r14b
0x180003d3f  jnz     short loc_180003D49
0x180003d41  test    byte ptr [rdi+4], 2
0x180003d45  jnz     short loc_180003D49
0x180003d47  xor     ebp, ebp
0x180003d49  mov     rdx, rdi
0x180003d4c  mov     cl, bpl
0x180003d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d54  nop
0x180003d55  add     rsp, 28h
0x180003d59  pop     r15
0x180003d5b  pop     r14
0x180003d5d  pop     rdi
0x180003d5e  pop     rsi
0x180003d5f  pop     rbp
0x180003d60  pop     rbx
0x180003d61  retn
```
