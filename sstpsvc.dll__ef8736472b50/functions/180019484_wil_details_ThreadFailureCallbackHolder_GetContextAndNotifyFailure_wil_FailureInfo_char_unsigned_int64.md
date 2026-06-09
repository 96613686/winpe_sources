# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180019484`
- end: `0x18001953e`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `186`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019550`

## callees

- `0x180019484`
- `0x180019984`
- `0x180019c2c`
- `0x18001e010`

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
0x180019484  push    rbx
0x180019486  push    rbp
0x180019487  push    rsi
0x180019488  push    rdi
0x180019489  push    r14
0x18001948b  push    r15
0x18001948d  sub     rsp, 28h
0x180019491  xor     r14b, r14b
0x180019494  mov     byte ptr [rdx], 0
0x180019497  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001949f  mov     r15, r8
0x1800194a2  mov     rsi, rdx
0x1800194a5  mov     rdi, rcx
0x1800194a8  mov     bpl, 1
0x1800194ab  jz      short loc_18001950C
0x1800194ad  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x1800194b2  mov     rbx, rax
0x1800194b5  test    rax, rax
0x1800194b8  jz      short loc_18001950C
0x1800194ba  cmp     qword ptr [rax], 0
0x1800194be  jz      short loc_18001950C
0x1800194c0  mov     [rsi], r14b
0x1800194c3  mov     r9, r15; unsigned __int64
0x1800194c6  mov     rdx, [rax]; struct wil::details::ThreadFailureCallbackHolder *
0x1800194c9  mov     r8, rsi; char *
0x1800194cc  mov     rcx, rdi; struct wil::FailureInfo *
0x1800194cf  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800194d4  test    al, al
0x1800194d6  jz      short loc_1800194DC
0x1800194d8  mov     [rdi+48h], rsi
0x1800194dc  mov     rbx, [rbx]
0x1800194df  mov     al, [rbx+28h]
0x1800194e2  mov     [rbx+28h], bpl
0x1800194e6  test    al, al
0x1800194e8  jnz     short loc_180019503
0x1800194ea  mov     rcx, [rbx+8]
0x1800194ee  mov     rdx, rdi
0x1800194f1  mov     rax, [rcx]
0x1800194f4  mov     rax, [rax]
0x1800194f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194fc  or      r14b, al
0x1800194ff  mov     byte ptr [rbx+28h], 0
0x180019503  mov     rbx, [rbx+10h]
0x180019507  test    rbx, rbx
0x18001950a  jnz     short loc_1800194DF
0x18001950c  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180019513  test    rax, rax
0x180019516  jz      short loc_180019530
0x180019518  test    r14b, r14b
0x18001951b  jnz     short loc_180019525
0x18001951d  test    byte ptr [rdi+4], 2
0x180019521  jnz     short loc_180019525
0x180019523  xor     ebp, ebp
0x180019525  mov     rdx, rdi
0x180019528  mov     cl, bpl
0x18001952b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019530  add     rsp, 28h
0x180019534  pop     r15
0x180019536  pop     r14
0x180019538  pop     rdi
0x180019539  pop     rsi
0x18001953a  pop     rbp
0x18001953b  pop     rbx
0x18001953c  retn
```
