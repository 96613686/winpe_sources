# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000bdd8`
- end: `0x18000be92`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000bea0`

## callees

- `0x18000bdd8`
- `0x18000c224`
- `0x18000c3ac`
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
0x18000bdd8  push    rbx
0x18000bdda  push    rbp
0x18000bddb  push    rsi
0x18000bddc  push    rdi
0x18000bddd  push    r14
0x18000bddf  push    r15
0x18000bde1  sub     rsp, 28h
0x18000bde5  mov     r15, r8
0x18000bde8  mov     rsi, rdx
0x18000bdeb  mov     rdi, rcx
0x18000bdee  mov     byte ptr [rdx], 0
0x18000bdf1  xor     r14b, r14b
0x18000bdf4  mov     bpl, 1
0x18000bdf7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000bdff  jz      short loc_18000BE60
0x18000be01  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000be06  mov     rbx, rax
0x18000be09  test    rax, rax
0x18000be0c  jz      short loc_18000BE60
0x18000be0e  cmp     qword ptr [rax], 0
0x18000be12  jz      short loc_18000BE60
0x18000be14  mov     [rsi], r14b
0x18000be17  mov     r9, r15; unsigned __int64
0x18000be1a  mov     r8, rsi; char *
0x18000be1d  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18000be20  mov     rcx, rdi; struct wil::FailureInfo *
0x18000be23  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000be28  test    al, al
0x18000be2a  jz      short loc_18000BE30
0x18000be2c  mov     [rdi+48h], rsi
0x18000be30  mov     rbx, [rbx]
0x18000be33  mov     al, [rbx+28h]
0x18000be36  mov     [rbx+28h], bpl
0x18000be3a  test    al, al
0x18000be3c  jnz     short loc_18000BE57
0x18000be3e  mov     rcx, [rbx+8]
0x18000be42  mov     rax, [rcx]
0x18000be45  mov     rdx, rdi
0x18000be48  mov     rax, [rax]
0x18000be4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be50  or      r14b, al
0x18000be53  mov     byte ptr [rbx+28h], 0
0x18000be57  mov     rbx, [rbx+10h]
0x18000be5b  test    rbx, rbx
0x18000be5e  jnz     short loc_18000BE33
0x18000be60  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000be67  test    rax, rax
0x18000be6a  jz      short loc_18000BE85
0x18000be6c  test    r14b, r14b
0x18000be6f  jnz     short loc_18000BE79
0x18000be71  test    byte ptr [rdi+4], 2
0x18000be75  jnz     short loc_18000BE79
0x18000be77  xor     ebp, ebp
0x18000be79  mov     rdx, rdi
0x18000be7c  mov     cl, bpl
0x18000be7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be84  nop
0x18000be85  add     rsp, 28h
0x18000be89  pop     r15
0x18000be8b  pop     r14
0x18000be8d  pop     rdi
0x18000be8e  pop     rsi
0x18000be8f  pop     rbp
0x18000be90  pop     rbx
0x18000be91  retn
```
