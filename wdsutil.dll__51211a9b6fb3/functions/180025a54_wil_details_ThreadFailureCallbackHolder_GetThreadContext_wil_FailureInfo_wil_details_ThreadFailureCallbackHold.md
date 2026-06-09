# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180025a54`
- end: `0x180025b38`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800253b0`
- `0x180025a54`

## callees

- `0x180025a54`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180025b1b`
- `msvcrt!memcpy_s` at `0x180025b1b`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  char *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rcx
  char *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx
  void *v18; // rcx

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( (__int64)(a4 - v12) > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        v18 = v13 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v18, v16, v15, v17);
        v14[v17 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025a54  push    rbx
0x180025a56  push    rbp
0x180025a57  push    rsi
0x180025a58  push    rdi
0x180025a59  sub     rsp, 28h
0x180025a5d  xor     al, al
0x180025a5f  mov     byte ptr [r8], 0
0x180025a63  mov     rbp, r9
0x180025a66  mov     rdi, r8
0x180025a69  mov     rsi, rdx
0x180025a6c  mov     rbx, rcx
0x180025a6f  test    rdx, rdx
0x180025a72  jz      loc_180025B2E
0x180025a78  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180025a7c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180025a81  mov     rdx, [rsi+20h]
0x180025a85  test    rdx, rdx
0x180025a88  jz      loc_180025B2E
0x180025a8e  cmp     dword ptr [rdx], 0
0x180025a91  jnz     short loc_180025AA4
0x180025a93  mov     eax, 1
0x180025a98  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180025aa0  inc     eax
0x180025aa2  mov     [rdx], eax
0x180025aa4  cmp     dword ptr [rbx+50h], 0
0x180025aa8  jnz     short loc_180025ABB
0x180025aaa  movups  xmm0, xmmword ptr [rdx]
0x180025aad  movups  xmmword ptr [rbx+50h], xmm0
0x180025ab1  movsd   xmm1, qword ptr [rdx+10h]
0x180025ab6  movsd   qword ptr [rbx+60h], xmm1
0x180025abb  movups  xmm0, xmmword ptr [rdx]
0x180025abe  lea     r10, [rdi+rbp]
0x180025ac2  movups  xmmword ptr [rbx+68h], xmm0
0x180025ac6  movsd   xmm1, qword ptr [rdx+10h]
0x180025acb  movsd   qword ptr [rbx+78h], xmm1
0x180025ad0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025ad4  mov     rax, rbx
0x180025ad7  inc     rax
0x180025ada  cmp     byte ptr [rdi+rax], 0
0x180025ade  jnz     short loc_180025AD7
0x180025ae0  lea     rcx, [rax+rdi]
0x180025ae4  mov     rax, r10
0x180025ae7  sub     rax, rcx
0x180025aea  cmp     rax, 2
0x180025aee  jle     short loc_180025B2C
0x180025af0  mov     byte ptr [rcx], 5Ch ; '\'
0x180025af3  lea     rdi, [rcx+1]
0x180025af7  mov     r8, [rdx+8]; Source
0x180025afb  inc     rbx
0x180025afe  cmp     byte ptr [r8+rbx], 0
0x180025b03  jnz     short loc_180025AFB
0x180025b05  sub     r10, rdi
0x180025b08  inc     rbx
0x180025b0b  cmp     rbx, r10
0x180025b0e  mov     rdx, r10; DestinationSize
0x180025b11  mov     rcx, rdi; Destination
0x180025b14  cmovnb  rbx, r10
0x180025b18  mov     r9, rbx; SourceSize
0x180025b1b  call    cs:__imp_memcpy_s
0x180025b22  nop     dword ptr [rax+rax+00h]
0x180025b27  mov     byte ptr [rbx+rdi-1], 0
0x180025b2c  mov     al, 1
0x180025b2e  add     rsp, 28h
0x180025b32  pop     rdi
0x180025b33  pop     rsi
0x180025b34  pop     rbp
0x180025b35  pop     rbx
0x180025b36  retn
```
