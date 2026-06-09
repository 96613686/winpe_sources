# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180024248`
- end: `0x180024303`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024310`

## callees

- `0x18001bcdc`
- `0x180024248`
- `0x180024848`
- `0x18002b010`

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
    Local = (struct wil::details::ThreadFailureCallbackHolder **)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                                                                   (__int64)a1,
                                                                   0);
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
0x180024248  push    rbx
0x18002424a  push    rbp
0x18002424b  push    rsi
0x18002424c  push    rdi
0x18002424d  push    r14
0x18002424f  push    r15
0x180024251  sub     rsp, 28h
0x180024255  xor     r14b, r14b
0x180024258  mov     byte ptr [rdx], 0
0x18002425b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180024263  mov     r15, r8
0x180024266  mov     rsi, rdx
0x180024269  mov     rdi, rcx
0x18002426c  mov     bpl, 1
0x18002426f  jz      short loc_1800242D2
0x180024271  xor     edx, edx
0x180024273  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180024278  mov     rbx, rax
0x18002427b  test    rax, rax
0x18002427e  jz      short loc_1800242D2
0x180024280  cmp     qword ptr [rax], 0
0x180024284  jz      short loc_1800242D2
0x180024286  mov     [rsi], r14b
0x180024289  mov     r9, r15; unsigned __int64
0x18002428c  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18002428f  mov     r8, rsi; char *
0x180024292  mov     rcx, rdi; struct wil::FailureInfo *
0x180024295  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18002429a  test    al, al
0x18002429c  jz      short loc_1800242A2
0x18002429e  mov     [rdi+48h], rsi
0x1800242a2  mov     rbx, [rbx]
0x1800242a5  mov     al, [rbx+28h]
0x1800242a8  mov     [rbx+28h], bpl
0x1800242ac  test    al, al
0x1800242ae  jnz     short loc_1800242C9
0x1800242b0  mov     rcx, [rbx+8]
0x1800242b4  mov     rdx, rdi
0x1800242b7  mov     rax, [rcx]
0x1800242ba  mov     rax, [rax]
0x1800242bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242c2  or      r14b, al
0x1800242c5  mov     byte ptr [rbx+28h], 0
0x1800242c9  mov     rbx, [rbx+10h]
0x1800242cd  test    rbx, rbx
0x1800242d0  jnz     short loc_1800242A5
0x1800242d2  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800242d9  test    rax, rax
0x1800242dc  jz      short loc_1800242F6
0x1800242de  test    r14b, r14b
0x1800242e1  jnz     short loc_1800242EB
0x1800242e3  test    byte ptr [rdi+4], 2
0x1800242e7  jnz     short loc_1800242EB
0x1800242e9  xor     ebp, ebp
0x1800242eb  mov     rdx, rdi
0x1800242ee  mov     cl, bpl
0x1800242f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242f6  add     rsp, 28h
0x1800242fa  pop     r15
0x1800242fc  pop     r14
0x1800242fe  pop     rdi
0x1800242ff  pop     rsi
0x180024300  pop     rbp
0x180024301  pop     rbx
0x180024302  retn
```
