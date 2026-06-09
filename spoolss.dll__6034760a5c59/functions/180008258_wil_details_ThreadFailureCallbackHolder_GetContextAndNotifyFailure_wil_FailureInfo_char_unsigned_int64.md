# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008258`
- end: `0x180008312`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008320`

## callees

- `0x180008258`
- `0x180008870`
- `0x180008a54`
- `0x180016010`

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
0x180008258  push    rbx
0x18000825a  push    rbp
0x18000825b  push    rsi
0x18000825c  push    rdi
0x18000825d  push    r14
0x18000825f  push    r15
0x180008261  sub     rsp, 28h
0x180008265  mov     r15, r8
0x180008268  mov     rsi, rdx
0x18000826b  mov     rdi, rcx
0x18000826e  mov     byte ptr [rdx], 0
0x180008271  xor     r14b, r14b
0x180008274  mov     bpl, 1
0x180008277  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000827f  jz      short loc_1800082E0
0x180008281  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180008286  mov     rbx, rax
0x180008289  test    rax, rax
0x18000828c  jz      short loc_1800082E0
0x18000828e  cmp     qword ptr [rax], 0
0x180008292  jz      short loc_1800082E0
0x180008294  mov     [rsi], r14b
0x180008297  mov     r9, r15; unsigned __int64
0x18000829a  mov     r8, rsi; char *
0x18000829d  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800082a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800082a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800082a8  test    al, al
0x1800082aa  jz      short loc_1800082B0
0x1800082ac  mov     [rdi+48h], rsi
0x1800082b0  mov     rbx, [rbx]
0x1800082b3  mov     al, [rbx+28h]
0x1800082b6  mov     [rbx+28h], bpl
0x1800082ba  test    al, al
0x1800082bc  jnz     short loc_1800082D7
0x1800082be  mov     rcx, [rbx+8]
0x1800082c2  mov     rax, [rcx]
0x1800082c5  mov     rdx, rdi
0x1800082c8  mov     rax, [rax]
0x1800082cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d0  or      r14b, al
0x1800082d3  mov     byte ptr [rbx+28h], 0
0x1800082d7  mov     rbx, [rbx+10h]
0x1800082db  test    rbx, rbx
0x1800082de  jnz     short loc_1800082B3
0x1800082e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800082e7  test    rax, rax
0x1800082ea  jz      short loc_180008305
0x1800082ec  test    r14b, r14b
0x1800082ef  jnz     short loc_1800082F9
0x1800082f1  test    byte ptr [rdi+4], 2
0x1800082f5  jnz     short loc_1800082F9
0x1800082f7  xor     ebp, ebp
0x1800082f9  mov     rdx, rdi
0x1800082fc  mov     cl, bpl
0x1800082ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008304  nop
0x180008305  add     rsp, 28h
0x180008309  pop     r15
0x18000830b  pop     r14
0x18000830d  pop     rdi
0x18000830e  pop     rsi
0x18000830f  pop     rbp
0x180008310  pop     rbx
0x180008311  retn
```
