# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000665c`
- end: `0x180006718`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `188`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006720`

## callees

- `0x18000665c`
- `0x180006b2c`
- `0x180006bd0`
- `0x180012010`

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
                                                                   a1,
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
0x18000665c  push    rbx
0x18000665e  push    rbp
0x18000665f  push    rsi
0x180006660  push    rdi
0x180006661  push    r14
0x180006663  push    r15
0x180006665  sub     rsp, 28h
0x180006669  mov     r15, r8
0x18000666c  mov     rsi, rdx
0x18000666f  mov     rdi, rcx
0x180006672  mov     byte ptr [rdx], 0
0x180006675  xor     r14b, r14b
0x180006678  mov     bpl, 1
0x18000667b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006683  jz      short loc_1800066E6
0x180006685  xor     edx, edx
0x180006687  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000668c  mov     rbx, rax
0x18000668f  test    rax, rax
0x180006692  jz      short loc_1800066E6
0x180006694  cmp     qword ptr [rax], 0
0x180006698  jz      short loc_1800066E6
0x18000669a  mov     [rsi], r14b
0x18000669d  mov     r9, r15; unsigned __int64
0x1800066a0  mov     r8, rsi; char *
0x1800066a3  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800066a6  mov     rcx, rdi; struct wil::FailureInfo *
0x1800066a9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800066ae  test    al, al
0x1800066b0  jz      short loc_1800066B6
0x1800066b2  mov     [rdi+48h], rsi
0x1800066b6  mov     rbx, [rbx]
0x1800066b9  mov     al, [rbx+28h]
0x1800066bc  mov     [rbx+28h], bpl
0x1800066c0  test    al, al
0x1800066c2  jnz     short loc_1800066DD
0x1800066c4  mov     rcx, [rbx+8]
0x1800066c8  mov     rax, [rcx]
0x1800066cb  mov     rdx, rdi
0x1800066ce  mov     rax, [rax]
0x1800066d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d6  or      r14b, al
0x1800066d9  mov     byte ptr [rbx+28h], 0
0x1800066dd  mov     rbx, [rbx+10h]
0x1800066e1  test    rbx, rbx
0x1800066e4  jnz     short loc_1800066B9
0x1800066e6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800066ed  test    rax, rax
0x1800066f0  jz      short loc_18000670B
0x1800066f2  test    r14b, r14b
0x1800066f5  jnz     short loc_1800066FF
0x1800066f7  test    byte ptr [rdi+4], 2
0x1800066fb  jnz     short loc_1800066FF
0x1800066fd  xor     ebp, ebp
0x1800066ff  mov     rdx, rdi
0x180006702  mov     cl, bpl
0x180006705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670a  nop
0x18000670b  add     rsp, 28h
0x18000670f  pop     r15
0x180006711  pop     r14
0x180006713  pop     rdi
0x180006714  pop     rsi
0x180006715  pop     rbp
0x180006716  pop     rbx
0x180006717  retn
```
