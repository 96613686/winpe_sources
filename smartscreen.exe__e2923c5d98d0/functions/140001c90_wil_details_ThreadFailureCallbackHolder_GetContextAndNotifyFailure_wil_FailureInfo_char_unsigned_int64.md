# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140001c90`
- end: `0x140001d95`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `261`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001c20`

## callees

- `0x140001c90`
- `0x14002dee0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001cba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001cba`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
        struct wil::FailureInfo *a1,
        char *a2,
        unsigned __int64 a3)
{
  struct wil::FailureInfo *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r10
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al

  v5 = a1;
  *a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    a1 = *(struct wil::FailureInfo **)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA));
    if ( a1 )
    {
      while ( *(_DWORD *)a1 != (_DWORD)CurrentThreadId )
      {
        a1 = (struct wil::FailureInfo *)*((_QWORD *)a1 + 1);
        if ( !a1 )
          goto LABEL_5;
      }
      v9 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)a1 + 16);
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v9, a2, a3) )
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
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(a1) = 1;
    else
      a1 = 0;
    wil::details::g_pfnTelemetryCallback(a1, v5);
  }
}

```

## disassembly

```asm
0x140001c90  push    rbx
0x140001c92  push    rbp
0x140001c93  push    rsi
0x140001c94  push    rdi
0x140001c95  push    r14
0x140001c97  sub     rsp, 20h
0x140001c9b  mov     rbp, r8
0x140001c9e  mov     r14, rdx
0x140001ca1  mov     rdi, rcx
0x140001ca4  mov     byte ptr [rdx], 0
0x140001ca7  xor     sil, sil
0x140001caa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140001cb1  test    rbx, rbx
0x140001cb4  jz      loc_140001D5E
0x140001cba  call    cs:__imp_GetCurrentThreadId
0x140001cc0  mov     r10d, eax
0x140001cc3  mov     r9d, eax
0x140001cc6  shr     r9, 2
0x140001cca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140001cd4  mul     r9
0x140001cd7  shr     rdx, 3
0x140001cdb  lea     rcx, [rdx+rdx*4]
0x140001cdf  add     rcx, rcx
0x140001ce2  sub     r9, rcx
0x140001ce5  mov     rcx, [rbx+r9*8]
0x140001ce9  test    rcx, rcx
0x140001cec  jz      short loc_140001D02
0x140001cee  xchg    ax, ax
0x140001cf0  cmp     [rcx], r10d
0x140001cf3  jz      loc_140001D79
0x140001cf9  mov     rcx, [rcx+8]
0x140001cfd  test    rcx, rcx
0x140001d00  jnz     short loc_140001CF0
0x140001d02  xor     ebx, ebx
0x140001d04  test    rbx, rbx
0x140001d07  jz      short loc_140001D5E
0x140001d09  cmp     qword ptr [rbx], 0
0x140001d0d  jz      short loc_140001D5E
0x140001d0f  mov     [r14], sil
0x140001d12  mov     r9, rbp; unsigned __int64
0x140001d15  mov     r8, r14; char *
0x140001d18  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140001d1b  mov     rcx, rdi; struct wil::FailureInfo *
0x140001d1e  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140001d23  test    al, al
0x140001d25  jz      short loc_140001D2B
0x140001d27  mov     [rdi+48h], r14
0x140001d2b  mov     rbx, [rbx]
0x140001d2e  xchg    ax, ax
0x140001d30  movzx   eax, byte ptr [rbx+28h]
0x140001d34  mov     byte ptr [rbx+28h], 1
0x140001d38  test    al, al
0x140001d3a  jnz     short loc_140001D55
0x140001d3c  mov     rcx, [rbx+8]
0x140001d40  mov     rax, [rcx]
0x140001d43  mov     rdx, rdi
0x140001d46  mov     rax, [rax]
0x140001d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d4e  or      sil, al
0x140001d51  mov     byte ptr [rbx+28h], 0
0x140001d55  mov     rbx, [rbx+10h]
0x140001d59  test    rbx, rbx
0x140001d5c  jnz     short loc_140001D30
0x140001d5e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140001d65  test    rax, rax
0x140001d68  jz      short loc_140001D8A
0x140001d6a  test    sil, sil
0x140001d6d  jnz     short loc_140001D7F
0x140001d6f  test    byte ptr [rdi+4], 2
0x140001d73  jnz     short loc_140001D7F
0x140001d75  xor     ecx, ecx
0x140001d77  jmp     short loc_140001D81
0x140001d79  lea     rbx, [rcx+10h]
0x140001d7d  jmp     short loc_140001D04
0x140001d7f  mov     cl, 1
0x140001d81  mov     rdx, rdi
0x140001d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d89  nop
0x140001d8a  add     rsp, 20h
0x140001d8e  pop     r14
0x140001d90  pop     rdi
0x140001d91  pop     rsi
0x140001d92  pop     rbp
0x140001d93  pop     rbx
0x140001d94  retn
```
