# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004474`
- end: `0x18000452e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004540`

## callees

- `0x180004474`
- `0x180004b78`
- `0x180004d00`
- `0x180008010`

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
0x180004474  push    rbx
0x180004476  push    rbp
0x180004477  push    rsi
0x180004478  push    rdi
0x180004479  push    r14
0x18000447b  push    r15
0x18000447d  sub     rsp, 28h
0x180004481  mov     r15, r8
0x180004484  mov     rsi, rdx
0x180004487  mov     rdi, rcx
0x18000448a  mov     byte ptr [rdx], 0
0x18000448d  xor     r14b, r14b
0x180004490  mov     bpl, 1
0x180004493  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000449b  jz      short loc_1800044FC
0x18000449d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800044a2  mov     rbx, rax
0x1800044a5  test    rax, rax
0x1800044a8  jz      short loc_1800044FC
0x1800044aa  cmp     qword ptr [rax], 0
0x1800044ae  jz      short loc_1800044FC
0x1800044b0  mov     [rsi], r14b
0x1800044b3  mov     r9, r15; unsigned __int64
0x1800044b6  mov     r8, rsi; char *
0x1800044b9  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800044bc  mov     rcx, rdi; struct wil::FailureInfo *
0x1800044bf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800044c4  test    al, al
0x1800044c6  jz      short loc_1800044CC
0x1800044c8  mov     [rdi+48h], rsi
0x1800044cc  mov     rbx, [rbx]
0x1800044cf  mov     al, [rbx+28h]
0x1800044d2  mov     [rbx+28h], bpl
0x1800044d6  test    al, al
0x1800044d8  jnz     short loc_1800044F3
0x1800044da  mov     rcx, [rbx+8]
0x1800044de  mov     rax, [rcx]
0x1800044e1  mov     rdx, rdi
0x1800044e4  mov     rax, [rax]
0x1800044e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ec  or      r14b, al
0x1800044ef  mov     byte ptr [rbx+28h], 0
0x1800044f3  mov     rbx, [rbx+10h]
0x1800044f7  test    rbx, rbx
0x1800044fa  jnz     short loc_1800044CF
0x1800044fc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004503  test    rax, rax
0x180004506  jz      short loc_180004521
0x180004508  test    r14b, r14b
0x18000450b  jnz     short loc_180004515
0x18000450d  test    byte ptr [rdi+4], 2
0x180004511  jnz     short loc_180004515
0x180004513  xor     ebp, ebp
0x180004515  mov     rdx, rdi
0x180004518  mov     cl, bpl
0x18000451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004520  nop
0x180004521  add     rsp, 28h
0x180004525  pop     r15
0x180004527  pop     r14
0x180004529  pop     rdi
0x18000452a  pop     rsi
0x18000452b  pop     rbp
0x18000452c  pop     rbx
0x18000452d  retn
```
