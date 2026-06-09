# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180014b58`
- end: `0x180014c11`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180014c20`

## callees

- `0x180014b58`
- `0x180014f90`
- `0x180015170`
- `0x180038010`

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
0x180014b58  push    rbx
0x180014b5a  push    rbp
0x180014b5b  push    rsi
0x180014b5c  push    rdi
0x180014b5d  push    r14
0x180014b5f  push    r15
0x180014b61  sub     rsp, 28h
0x180014b65  xor     r14b, r14b
0x180014b68  mov     byte ptr [rdx], 0
0x180014b6b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014b73  mov     r15, r8
0x180014b76  mov     rsi, rdx
0x180014b79  mov     rdi, rcx
0x180014b7c  mov     bpl, 1
0x180014b7f  jz      short loc_180014BE0
0x180014b81  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180014b86  mov     rbx, rax
0x180014b89  test    rax, rax
0x180014b8c  jz      short loc_180014BE0
0x180014b8e  cmp     qword ptr [rax], 0
0x180014b92  jz      short loc_180014BE0
0x180014b94  mov     [rsi], r14b
0x180014b97  mov     r9, r15; unsigned __int64
0x180014b9a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180014b9d  mov     r8, rsi; char *
0x180014ba0  mov     rcx, rdi; struct wil::FailureInfo *
0x180014ba3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180014ba8  test    al, al
0x180014baa  jz      short loc_180014BB0
0x180014bac  mov     [rdi+48h], rsi
0x180014bb0  mov     rbx, [rbx]
0x180014bb3  mov     al, [rbx+28h]
0x180014bb6  mov     [rbx+28h], bpl
0x180014bba  test    al, al
0x180014bbc  jnz     short loc_180014BD7
0x180014bbe  mov     rcx, [rbx+8]
0x180014bc2  mov     rdx, rdi
0x180014bc5  mov     rax, [rcx]
0x180014bc8  mov     rax, [rax]
0x180014bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bd0  or      r14b, al
0x180014bd3  mov     byte ptr [rbx+28h], 0
0x180014bd7  mov     rbx, [rbx+10h]
0x180014bdb  test    rbx, rbx
0x180014bde  jnz     short loc_180014BB3
0x180014be0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180014be7  test    rax, rax
0x180014bea  jz      short loc_180014C04
0x180014bec  test    r14b, r14b
0x180014bef  jnz     short loc_180014BF9
0x180014bf1  test    byte ptr [rdi+4], 2
0x180014bf5  jnz     short loc_180014BF9
0x180014bf7  xor     ebp, ebp
0x180014bf9  mov     rdx, rdi
0x180014bfc  mov     cl, bpl
0x180014bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c04  add     rsp, 28h
0x180014c08  pop     r15
0x180014c0a  pop     r14
0x180014c0c  pop     rdi
0x180014c0d  pop     rsi
0x180014c0e  pop     rbp
0x180014c0f  pop     rbx
0x180014c10  retn
```
