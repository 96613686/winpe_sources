# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800119e0`
- end: `0x180011a9c`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011ab0`

## callees

- `0x1800119e0`
- `0x180011fc0`
- `0x180012b94`
- `0x18002c010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   (__int64)a1,
                                                                   0);
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
0x1800119e0  push    rbx
0x1800119e2  push    rbp
0x1800119e3  push    rsi
0x1800119e4  push    rdi
0x1800119e5  push    r14
0x1800119e7  push    r15
0x1800119e9  sub     rsp, 28h
0x1800119ed  mov     r15, r8
0x1800119f0  mov     rsi, rdx
0x1800119f3  mov     rdi, rcx
0x1800119f6  mov     byte ptr [rdx], 0
0x1800119f9  xor     r14b, r14b
0x1800119fc  mov     bpl, 1
0x1800119ff  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011a07  jz      short loc_180011A6A
0x180011a09  xor     edx, edx
0x180011a0b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180011a10  mov     rbx, rax
0x180011a13  test    rax, rax
0x180011a16  jz      short loc_180011A6A
0x180011a18  cmp     qword ptr [rax], 0
0x180011a1c  jz      short loc_180011A6A
0x180011a1e  mov     [rsi], r14b
0x180011a21  mov     r9, r15; unsigned __int64
0x180011a24  mov     r8, rsi; char *
0x180011a27  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180011a2a  mov     rcx, rdi; struct wil::FailureInfo *
0x180011a2d  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180011a32  test    al, al
0x180011a34  jz      short loc_180011A3A
0x180011a36  mov     [rdi+48h], rsi
0x180011a3a  mov     rbx, [rbx]
0x180011a3d  mov     al, [rbx+28h]
0x180011a40  mov     [rbx+28h], bpl
0x180011a44  test    al, al
0x180011a46  jnz     short loc_180011A61
0x180011a48  mov     rcx, [rbx+8]
0x180011a4c  mov     rax, [rcx]
0x180011a4f  mov     rdx, rdi
0x180011a52  mov     rax, [rax]
0x180011a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a5a  or      r14b, al
0x180011a5d  mov     byte ptr [rbx+28h], 0
0x180011a61  mov     rbx, [rbx+10h]
0x180011a65  test    rbx, rbx
0x180011a68  jnz     short loc_180011A3D
0x180011a6a  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180011a71  test    rax, rax
0x180011a74  jz      short loc_180011A8F
0x180011a76  test    r14b, r14b
0x180011a79  jnz     short loc_180011A83
0x180011a7b  test    byte ptr [rdi+4], 2
0x180011a7f  jnz     short loc_180011A83
0x180011a81  xor     ebp, ebp
0x180011a83  mov     rdx, rdi
0x180011a86  mov     cl, bpl
0x180011a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a8e  nop
0x180011a8f  add     rsp, 28h
0x180011a93  pop     r15
0x180011a95  pop     r14
0x180011a97  pop     rdi
0x180011a98  pop     rsi
0x180011a99  pop     rbp
0x180011a9a  pop     rbx
0x180011a9b  retn
```
