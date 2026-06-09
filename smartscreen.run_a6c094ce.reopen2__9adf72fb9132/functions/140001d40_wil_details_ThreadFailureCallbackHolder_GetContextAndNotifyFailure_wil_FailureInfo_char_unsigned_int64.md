# wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140001d40`
- end: `0x140001e48`
- name: `?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z`
- size: `264`
- prototype: `void __fastcall(struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001cc0`

## callees

- `0x140001d40`
- `0x14002f0e4`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001d6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001d6a`

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
0x140001d40  push    rbx
0x140001d42  push    rbp
0x140001d43  push    rsi
0x140001d44  push    rdi
0x140001d45  push    r14
0x140001d47  sub     rsp, 20h
0x140001d4b  mov     rbp, r8
0x140001d4e  mov     r14, rdx
0x140001d51  mov     rdi, rcx
0x140001d54  mov     byte ptr [rdx], 0
0x140001d57  xor     sil, sil
0x140001d5a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140001d61  test    rbx, rbx
0x140001d64  jz      loc_140001E10
0x140001d6a  call    cs:__imp_GetCurrentThreadId
0x140001d71  nop     dword ptr [rax+rax+00h]
0x140001d76  mov     r10d, eax
0x140001d79  mov     r9d, eax
0x140001d7c  shr     r9, 2
0x140001d80  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140001d8a  mul     r9
0x140001d8d  shr     rdx, 3
0x140001d91  lea     rcx, [rdx+rdx*4]
0x140001d95  add     rcx, rcx
0x140001d98  sub     r9, rcx
0x140001d9b  mov     rcx, [rbx+r9*8]
0x140001d9f  test    rcx, rcx
0x140001da2  jz      short loc_140001DB6
0x140001da4  cmp     [rcx], r10d
0x140001da7  jz      loc_140001E2B
0x140001dad  mov     rcx, [rcx+8]
0x140001db1  test    rcx, rcx
0x140001db4  jnz     short loc_140001DA4
0x140001db6  xor     ebx, ebx
0x140001db8  test    rbx, rbx
0x140001dbb  jz      short loc_140001E10
0x140001dbd  cmp     qword ptr [rbx], 0
0x140001dc1  jz      short loc_140001E10
0x140001dc3  mov     [r14], sil
0x140001dc6  mov     r9, rbp; unsigned __int64
0x140001dc9  mov     r8, r14; char *
0x140001dcc  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140001dcf  mov     rcx, rdi; struct wil::FailureInfo *
0x140001dd2  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140001dd7  test    al, al
0x140001dd9  jz      short loc_140001DDF
0x140001ddb  mov     [rdi+48h], r14
0x140001ddf  mov     rbx, [rbx]
0x140001de2  movzx   eax, byte ptr [rbx+28h]
0x140001de6  mov     byte ptr [rbx+28h], 1
0x140001dea  test    al, al
0x140001dec  jnz     short loc_140001E07
0x140001dee  mov     rcx, [rbx+8]
0x140001df2  mov     rax, [rcx]
0x140001df5  mov     rdx, rdi
0x140001df8  mov     rax, [rax]
0x140001dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e00  or      sil, al
0x140001e03  mov     byte ptr [rbx+28h], 0
0x140001e07  mov     rbx, [rbx+10h]
0x140001e0b  test    rbx, rbx
0x140001e0e  jnz     short loc_140001DE2
0x140001e10  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140001e17  test    rax, rax
0x140001e1a  jz      short loc_140001E3C
0x140001e1c  test    sil, sil
0x140001e1f  jnz     short loc_140001E31
0x140001e21  test    byte ptr [rdi+4], 2
0x140001e25  jnz     short loc_140001E31
0x140001e27  xor     ecx, ecx
0x140001e29  jmp     short loc_140001E33
0x140001e2b  lea     rbx, [rcx+10h]
0x140001e2f  jmp     short loc_140001DB8
0x140001e31  mov     cl, 1
0x140001e33  mov     rdx, rdi
0x140001e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e3b  nop
0x140001e3c  add     rsp, 20h
0x140001e40  pop     r14
0x140001e42  pop     rdi
0x140001e43  pop     rsi
0x140001e44  pop     rbp
0x140001e45  pop     rbx
0x140001e46  retn
```
