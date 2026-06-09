# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18001ba18`
- end: `0x18001bad1`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `185`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001bae0`

## callees

- `0x18001ba18`
- `0x18001c694`
- `0x18001c980`
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
0x18001ba18  push    rbx
0x18001ba1a  push    rbp
0x18001ba1b  push    rsi
0x18001ba1c  push    rdi
0x18001ba1d  push    r14
0x18001ba1f  push    r15
0x18001ba21  sub     rsp, 28h
0x18001ba25  xor     r14b, r14b
0x18001ba28  mov     byte ptr [rdx], 0
0x18001ba2b  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001ba33  mov     r15, r8
0x18001ba36  mov     rsi, rdx
0x18001ba39  mov     rdi, rcx
0x18001ba3c  mov     bpl, 1
0x18001ba3f  jz      short loc_18001BAA0
0x18001ba41  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001ba46  mov     rbx, rax
0x18001ba49  test    rax, rax
0x18001ba4c  jz      short loc_18001BAA0
0x18001ba4e  cmp     qword ptr [rax], 0
0x18001ba52  jz      short loc_18001BAA0
0x18001ba54  mov     [rsi], r14b
0x18001ba57  mov     r9, r15; unsigned __int64
0x18001ba5a  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x18001ba5d  mov     r8, rsi; char *
0x18001ba60  mov     rcx, rdi; struct wil::FailureInfo *
0x18001ba63  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001ba68  test    al, al
0x18001ba6a  jz      short loc_18001BA70
0x18001ba6c  mov     [rdi+48h], rsi
0x18001ba70  mov     rbx, [rbx]
0x18001ba73  mov     al, [rbx+28h]
0x18001ba76  mov     [rbx+28h], bpl
0x18001ba7a  test    al, al
0x18001ba7c  jnz     short loc_18001BA97
0x18001ba7e  mov     rcx, [rbx+8]
0x18001ba82  mov     rdx, rdi
0x18001ba85  mov     rax, [rcx]
0x18001ba88  mov     rax, [rax]
0x18001ba8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba90  or      r14b, al
0x18001ba93  mov     byte ptr [rbx+28h], 0
0x18001ba97  mov     rbx, [rbx+10h]
0x18001ba9b  test    rbx, rbx
0x18001ba9e  jnz     short loc_18001BA73
0x18001baa0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001baa7  test    rax, rax
0x18001baaa  jz      short loc_18001BAC4
0x18001baac  test    r14b, r14b
0x18001baaf  jnz     short loc_18001BAB9
0x18001bab1  test    byte ptr [rdi+4], 2
0x18001bab5  jnz     short loc_18001BAB9
0x18001bab7  xor     ebp, ebp
0x18001bab9  mov     rdx, rdi
0x18001babc  mov     cl, bpl
0x18001babf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bac4  add     rsp, 28h
0x18001bac8  pop     r15
0x18001baca  pop     r14
0x18001bacc  pop     rdi
0x18001bacd  pop     rsi
0x18001bace  pop     rbp
0x18001bacf  pop     rbx
0x18001bad0  retn
```
