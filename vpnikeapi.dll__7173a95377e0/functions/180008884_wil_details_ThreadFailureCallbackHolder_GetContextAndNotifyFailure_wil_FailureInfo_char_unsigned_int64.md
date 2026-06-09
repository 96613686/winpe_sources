# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008884`
- end: `0x18000893d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008950`

## callees

- `0x180008884`
- `0x180008d5c`
- `0x180008fe8`
- `0x18000e010`

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
0x180008884  push    rbx
0x180008886  push    rbp
0x180008887  push    rsi
0x180008888  push    rdi
0x180008889  push    r14
0x18000888b  push    r15
0x18000888d  sub     rsp, 28h
0x180008891  xor     r14b, r14b
0x180008894  mov     byte ptr [rdx], 0
0x180008897  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000889f  mov     r15, r8
0x1800088a2  mov     rsi, rdx
0x1800088a5  mov     rdi, rcx
0x1800088a8  mov     bpl, 1
0x1800088ab  jz      short loc_18000890C
0x1800088ad  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800088b2  mov     rbx, rax
0x1800088b5  test    rax, rax
0x1800088b8  jz      short loc_18000890C
0x1800088ba  cmp     qword ptr [rax], 0
0x1800088be  jz      short loc_18000890C
0x1800088c0  mov     [rsi], r14b
0x1800088c3  mov     r9, r15; unsigned __int64
0x1800088c6  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800088c9  mov     r8, rsi; char *
0x1800088cc  mov     rcx, rdi; struct wil::FailureInfo *
0x1800088cf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800088d4  test    al, al
0x1800088d6  jz      short loc_1800088DC
0x1800088d8  mov     [rdi+48h], rsi
0x1800088dc  mov     rbx, [rbx]
0x1800088df  mov     al, [rbx+28h]
0x1800088e2  mov     [rbx+28h], bpl
0x1800088e6  test    al, al
0x1800088e8  jnz     short loc_180008903
0x1800088ea  mov     rcx, [rbx+8]
0x1800088ee  mov     rdx, rdi
0x1800088f1  mov     rax, [rcx]
0x1800088f4  mov     rax, [rax]
0x1800088f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088fc  or      r14b, al
0x1800088ff  mov     byte ptr [rbx+28h], 0
0x180008903  mov     rbx, [rbx+10h]
0x180008907  test    rbx, rbx
0x18000890a  jnz     short loc_1800088DF
0x18000890c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180008913  test    rax, rax
0x180008916  jz      short loc_180008930
0x180008918  test    r14b, r14b
0x18000891b  jnz     short loc_180008925
0x18000891d  test    byte ptr [rdi+4], 2
0x180008921  jnz     short loc_180008925
0x180008923  xor     ebp, ebp
0x180008925  mov     rdx, rdi
0x180008928  mov     cl, bpl
0x18000892b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008930  add     rsp, 28h
0x180008934  pop     r15
0x180008936  pop     r14
0x180008938  pop     rdi
0x180008939  pop     rsi
0x18000893a  pop     rbp
0x18000893b  pop     rbx
0x18000893c  retn
```
