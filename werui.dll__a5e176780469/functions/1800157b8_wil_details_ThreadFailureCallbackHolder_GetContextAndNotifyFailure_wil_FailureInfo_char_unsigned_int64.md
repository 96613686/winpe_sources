# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800157b8`
- end: `0x180015871`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015880`

## callees

- `0x1800157b8`
- `0x180015988`
- `0x1800159e4`
- `0x180018010`

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
0x1800157b8  push    rbx
0x1800157ba  push    rbp
0x1800157bb  push    rsi
0x1800157bc  push    rdi
0x1800157bd  push    r14
0x1800157bf  push    r15
0x1800157c1  sub     rsp, 28h
0x1800157c5  xor     r14b, r14b
0x1800157c8  mov     byte ptr [rdx], 0
0x1800157cb  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800157d3  mov     r15, r8
0x1800157d6  mov     rsi, rdx
0x1800157d9  mov     rdi, rcx
0x1800157dc  mov     bpl, 1
0x1800157df  jz      short loc_180015840
0x1800157e1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800157e6  mov     rbx, rax
0x1800157e9  test    rax, rax
0x1800157ec  jz      short loc_180015840
0x1800157ee  cmp     qword ptr [rax], 0
0x1800157f2  jz      short loc_180015840
0x1800157f4  mov     [rsi], r14b
0x1800157f7  mov     r9, r15; unsigned __int64
0x1800157fa  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800157fd  mov     r8, rsi; char *
0x180015800  mov     rcx, rdi; struct wil::FailureInfo *
0x180015803  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180015808  test    al, al
0x18001580a  jz      short loc_180015810
0x18001580c  mov     [rdi+48h], rsi
0x180015810  mov     rbx, [rbx]
0x180015813  mov     al, [rbx+28h]
0x180015816  mov     [rbx+28h], bpl
0x18001581a  test    al, al
0x18001581c  jnz     short loc_180015837
0x18001581e  mov     rcx, [rbx+8]
0x180015822  mov     rdx, rdi
0x180015825  mov     rax, [rcx]
0x180015828  mov     rax, [rax]
0x18001582b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015830  or      r14b, al
0x180015833  mov     byte ptr [rbx+28h], 0
0x180015837  mov     rbx, [rbx+10h]
0x18001583b  test    rbx, rbx
0x18001583e  jnz     short loc_180015813
0x180015840  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180015847  test    rax, rax
0x18001584a  jz      short loc_180015864
0x18001584c  test    r14b, r14b
0x18001584f  jnz     short loc_180015859
0x180015851  test    byte ptr [rdi+4], 2
0x180015855  jnz     short loc_180015859
0x180015857  xor     ebp, ebp
0x180015859  mov     rdx, rdi
0x18001585c  mov     cl, bpl
0x18001585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015864  add     rsp, 28h
0x180015868  pop     r15
0x18001586a  pop     r14
0x18001586c  pop     rdi
0x18001586d  pop     rsi
0x18001586e  pop     rbp
0x18001586f  pop     rbx
0x180015870  retn
```
