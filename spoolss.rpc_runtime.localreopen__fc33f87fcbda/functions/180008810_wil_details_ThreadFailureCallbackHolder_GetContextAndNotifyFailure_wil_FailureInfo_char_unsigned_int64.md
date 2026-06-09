# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008810`
- end: `0x1800088cb`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `187`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800088e0`

## callees

- `0x180008810`
- `0x180008f30`
- `0x180009128`
- `0x180017010`

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
0x180008810  push    rbx
0x180008812  push    rbp
0x180008813  push    rsi
0x180008814  push    rdi
0x180008815  push    r14
0x180008817  push    r15
0x180008819  sub     rsp, 28h
0x18000881d  mov     r15, r8
0x180008820  mov     rsi, rdx
0x180008823  mov     rdi, rcx
0x180008826  mov     byte ptr [rdx], 0
0x180008829  xor     r14b, r14b
0x18000882c  mov     bpl, 1
0x18000882f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008837  jz      short loc_180008898
0x180008839  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000883e  mov     rbx, rax
0x180008841  test    rax, rax
0x180008844  jz      short loc_180008898
0x180008846  cmp     qword ptr [rax], 0
0x18000884a  jz      short loc_180008898
0x18000884c  mov     [rsi], r14b
0x18000884f  mov     r9, r15; unsigned __int64
0x180008852  mov     r8, rsi; char *
0x180008855  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x180008858  mov     rcx, rdi; struct wil::FailureInfo *
0x18000885b  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008860  test    al, al
0x180008862  jz      short loc_180008868
0x180008864  mov     [rdi+48h], rsi
0x180008868  mov     rbx, [rbx]
0x18000886b  mov     al, [rbx+28h]
0x18000886e  mov     [rbx+28h], bpl
0x180008872  test    al, al
0x180008874  jnz     short loc_18000888F
0x180008876  mov     rcx, [rbx+8]
0x18000887a  mov     rax, [rcx]
0x18000887d  mov     rdx, rdi
0x180008880  mov     rax, [rax]
0x180008883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008888  or      r14b, al
0x18000888b  mov     byte ptr [rbx+28h], 0
0x18000888f  mov     rbx, [rbx+10h]
0x180008893  test    rbx, rbx
0x180008896  jnz     short loc_18000886B
0x180008898  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000889f  test    rax, rax
0x1800088a2  jz      short loc_1800088BD
0x1800088a4  test    r14b, r14b
0x1800088a7  jnz     short loc_1800088B1
0x1800088a9  test    byte ptr [rdi+4], 2
0x1800088ad  jnz     short loc_1800088B1
0x1800088af  xor     ebp, ebp
0x1800088b1  mov     rdx, rdi
0x1800088b4  mov     cl, bpl
0x1800088b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088bc  nop
0x1800088bd  add     rsp, 28h
0x1800088c1  pop     r15
0x1800088c3  pop     r14
0x1800088c5  pop     rdi
0x1800088c6  pop     rsi
0x1800088c7  pop     rbp
0x1800088c8  pop     rbx
0x1800088c9  retn
```
