# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800180a4`
- end: `0x18001815d`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018170`

## callees

- `0x1800180a4`
- `0x18001857c`
- `0x180018808`
- `0x18001d010`

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
0x1800180a4  push    rbx
0x1800180a6  push    rbp
0x1800180a7  push    rsi
0x1800180a8  push    rdi
0x1800180a9  push    r14
0x1800180ab  push    r15
0x1800180ad  sub     rsp, 28h
0x1800180b1  xor     r14b, r14b
0x1800180b4  mov     byte ptr [rdx], 0
0x1800180b7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800180bf  mov     r15, r8
0x1800180c2  mov     rsi, rdx
0x1800180c5  mov     rdi, rcx
0x1800180c8  mov     bpl, 1
0x1800180cb  jz      short loc_18001812C
0x1800180cd  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800180d2  mov     rbx, rax
0x1800180d5  test    rax, rax
0x1800180d8  jz      short loc_18001812C
0x1800180da  cmp     qword ptr [rax], 0
0x1800180de  jz      short loc_18001812C
0x1800180e0  mov     [rsi], r14b
0x1800180e3  mov     r9, r15; unsigned __int64
0x1800180e6  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800180e9  mov     r8, rsi; char *
0x1800180ec  mov     rcx, rdi; struct wil::FailureInfo *
0x1800180ef  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800180f4  test    al, al
0x1800180f6  jz      short loc_1800180FC
0x1800180f8  mov     [rdi+48h], rsi
0x1800180fc  mov     rbx, [rbx]
0x1800180ff  mov     al, [rbx+28h]
0x180018102  mov     [rbx+28h], bpl
0x180018106  test    al, al
0x180018108  jnz     short loc_180018123
0x18001810a  mov     rcx, [rbx+8]
0x18001810e  mov     rdx, rdi
0x180018111  mov     rax, [rcx]
0x180018114  mov     rax, [rax]
0x180018117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001811c  or      r14b, al
0x18001811f  mov     byte ptr [rbx+28h], 0
0x180018123  mov     rbx, [rbx+10h]
0x180018127  test    rbx, rbx
0x18001812a  jnz     short loc_1800180FF
0x18001812c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180018133  test    rax, rax
0x180018136  jz      short loc_180018150
0x180018138  test    r14b, r14b
0x18001813b  jnz     short loc_180018145
0x18001813d  test    byte ptr [rdi+4], 2
0x180018141  jnz     short loc_180018145
0x180018143  xor     ebp, ebp
0x180018145  mov     rdx, rdi
0x180018148  mov     cl, bpl
0x18001814b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018150  add     rsp, 28h
0x180018154  pop     r15
0x180018156  pop     r14
0x180018158  pop     rdi
0x180018159  pop     rsi
0x18001815a  pop     rbp
0x18001815b  pop     rbx
0x18001815c  retn
```
