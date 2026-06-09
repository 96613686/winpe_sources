# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000c99c`
- end: `0x18000ca55`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ca60`

## callees

- `0x18000c99c`
- `0x18000ce6c`
- `0x18000cff4`
- `0x180016010`

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
0x18000c99c  push    rbx
0x18000c99e  push    rbp
0x18000c99f  push    rsi
0x18000c9a0  push    rdi
0x18000c9a1  push    r14
0x18000c9a3  push    r15
0x18000c9a5  sub     rsp, 28h
0x18000c9a9  xor     r14b, r14b
0x18000c9ac  mov     byte ptr [rdx], 0
0x18000c9af  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c9b7  mov     r15, r8
0x18000c9ba  mov     rsi, rdx
0x18000c9bd  mov     rdi, rcx
0x18000c9c0  mov     bpl, 1
0x18000c9c3  jz      short loc_18000CA24
0x18000c9c5  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000c9ca  mov     rbx, rax
0x18000c9cd  test    rax, rax
0x18000c9d0  jz      short loc_18000CA24
0x18000c9d2  cmp     qword ptr [rax], 0
0x18000c9d6  jz      short loc_18000CA24
0x18000c9d8  mov     [rsi], r14b
0x18000c9db  mov     r9, r15; unsigned __int64
0x18000c9de  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000c9e1  mov     r8, rsi; char *
0x18000c9e4  mov     rcx, rdi; struct wil::FailureInfo *
0x18000c9e7  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000c9ec  test    al, al
0x18000c9ee  jz      short loc_18000C9F4
0x18000c9f0  mov     [rdi+48h], rsi
0x18000c9f4  mov     rbx, [rbx]
0x18000c9f7  mov     al, [rbx+28h]
0x18000c9fa  mov     [rbx+28h], bpl
0x18000c9fe  test    al, al
0x18000ca00  jnz     short loc_18000CA1B
0x18000ca02  mov     rcx, [rbx+8]
0x18000ca06  mov     rdx, rdi
0x18000ca09  mov     rax, [rcx]
0x18000ca0c  mov     rax, [rax]
0x18000ca0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca14  or      r14b, al
0x18000ca17  mov     byte ptr [rbx+28h], 0
0x18000ca1b  mov     rbx, [rbx+10h]
0x18000ca1f  test    rbx, rbx
0x18000ca22  jnz     short loc_18000C9F7
0x18000ca24  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000ca2b  test    rax, rax
0x18000ca2e  jz      short loc_18000CA48
0x18000ca30  test    r14b, r14b
0x18000ca33  jnz     short loc_18000CA3D
0x18000ca35  test    byte ptr [rdi+4], 2
0x18000ca39  jnz     short loc_18000CA3D
0x18000ca3b  xor     ebp, ebp
0x18000ca3d  mov     rdx, rdi
0x18000ca40  mov     cl, bpl
0x18000ca43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca48  add     rsp, 28h
0x18000ca4c  pop     r15
0x18000ca4e  pop     r14
0x18000ca50  pop     rdi
0x18000ca51  pop     rsi
0x18000ca52  pop     rbp
0x18000ca53  pop     rbx
0x18000ca54  retn
```
