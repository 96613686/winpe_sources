# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000df44`
- end: `0x18000dffd`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e010`

## callees

- `0x18000df44`
- `0x18000e380`
- `0x18000e594`
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
0x18000df44  push    rbx
0x18000df46  push    rbp
0x18000df47  push    rsi
0x18000df48  push    rdi
0x18000df49  push    r14
0x18000df4b  push    r15
0x18000df4d  sub     rsp, 28h
0x18000df51  xor     r14b, r14b
0x18000df54  mov     byte ptr [rdx], 0
0x18000df57  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000df5f  mov     r15, r8
0x18000df62  mov     rsi, rdx
0x18000df65  mov     rdi, rcx
0x18000df68  mov     bpl, 1
0x18000df6b  jz      short loc_18000DFCC
0x18000df6d  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000df72  mov     rbx, rax
0x18000df75  test    rax, rax
0x18000df78  jz      short loc_18000DFCC
0x18000df7a  cmp     qword ptr [rax], 0
0x18000df7e  jz      short loc_18000DFCC
0x18000df80  mov     [rsi], r14b
0x18000df83  mov     r9, r15; unsigned __int64
0x18000df86  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000df89  mov     r8, rsi; char *
0x18000df8c  mov     rcx, rdi; struct wil::FailureInfo *
0x18000df8f  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000df94  test    al, al
0x18000df96  jz      short loc_18000DF9C
0x18000df98  mov     [rdi+48h], rsi
0x18000df9c  mov     rbx, [rbx]
0x18000df9f  mov     al, [rbx+28h]
0x18000dfa2  mov     [rbx+28h], bpl
0x18000dfa6  test    al, al
0x18000dfa8  jnz     short loc_18000DFC3
0x18000dfaa  mov     rcx, [rbx+8]
0x18000dfae  mov     rdx, rdi
0x18000dfb1  mov     rax, [rcx]
0x18000dfb4  mov     rax, [rax]
0x18000dfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfbc  or      r14b, al
0x18000dfbf  mov     byte ptr [rbx+28h], 0
0x18000dfc3  mov     rbx, [rbx+10h]
0x18000dfc7  test    rbx, rbx
0x18000dfca  jnz     short loc_18000DF9F
0x18000dfcc  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000dfd3  test    rax, rax
0x18000dfd6  jz      short loc_18000DFF0
0x18000dfd8  test    r14b, r14b
0x18000dfdb  jnz     short loc_18000DFE5
0x18000dfdd  test    byte ptr [rdi+4], 2
0x18000dfe1  jnz     short loc_18000DFE5
0x18000dfe3  xor     ebp, ebp
0x18000dfe5  mov     rdx, rdi
0x18000dfe8  mov     cl, bpl
0x18000dfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff0  add     rsp, 28h
0x18000dff4  pop     r15
0x18000dff6  pop     r14
0x18000dff8  pop     rdi
0x18000dff9  pop     rsi
0x18000dffa  pop     rbp
0x18000dffb  pop     rbx
0x18000dffc  retn
```
