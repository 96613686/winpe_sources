# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006bd0`
- end: `0x180006cac`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000665c`
- `0x180006bd0`

## callees

- `0x180006bd0`
- `0x180009b1c`

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
0x180006bd0  push    rbx
0x180006bd2  push    rbp
0x180006bd3  push    rsi
0x180006bd4  push    rdi
0x180006bd5  sub     rsp, 28h
0x180006bd9  xor     al, al
0x180006bdb  mov     byte ptr [r8], 0
0x180006bdf  mov     rbp, r9
0x180006be2  mov     rdi, r8
0x180006be5  mov     rsi, rdx
0x180006be8  mov     rbx, rcx
0x180006beb  test    rdx, rdx
0x180006bee  jz      loc_180006CA3
0x180006bf4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006bf8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006bfd  mov     rdx, [rsi+20h]
0x180006c01  test    rdx, rdx
0x180006c04  jz      loc_180006CA3
0x180006c0a  cmp     dword ptr [rdx], 0
0x180006c0d  jnz     short loc_180006C20
0x180006c0f  mov     eax, 1
0x180006c14  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006c1c  inc     eax
0x180006c1e  mov     [rdx], eax
0x180006c20  cmp     dword ptr [rbx+50h], 0
0x180006c24  jnz     short loc_180006C37
0x180006c26  movups  xmm0, xmmword ptr [rdx]
0x180006c29  movups  xmmword ptr [rbx+50h], xmm0
0x180006c2d  movsd   xmm1, qword ptr [rdx+10h]
0x180006c32  movsd   qword ptr [rbx+60h], xmm1
0x180006c37  movups  xmm0, xmmword ptr [rdx]
0x180006c3a  lea     r10, [rdi+rbp]
0x180006c3e  movups  xmmword ptr [rbx+68h], xmm0
0x180006c42  movsd   xmm1, qword ptr [rdx+10h]
0x180006c47  movsd   qword ptr [rbx+78h], xmm1
0x180006c4c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006c50  mov     rax, rbx
0x180006c53  inc     rax
0x180006c56  cmp     byte ptr [rdi+rax], 0
0x180006c5a  jnz     short loc_180006C53
0x180006c5c  lea     rcx, [rax+rdi]
0x180006c60  mov     rax, r10
0x180006c63  sub     rax, rcx
0x180006c66  cmp     rax, 2
0x180006c6a  jle     short loc_180006CA1
0x180006c6c  mov     byte ptr [rcx], 5Ch ; '\'
0x180006c6f  lea     rdi, [rcx+1]
0x180006c73  mov     r8, [rdx+8]; Source
0x180006c77  inc     rbx
0x180006c7a  cmp     byte ptr [r8+rbx], 0
0x180006c7f  jnz     short loc_180006C77
0x180006c81  sub     r10, rdi
0x180006c84  inc     rbx
0x180006c87  cmp     rbx, r10
0x180006c8a  mov     rdx, r10; DestinationSize
0x180006c8d  mov     rcx, rdi; Destination
0x180006c90  cmovnb  rbx, r10
0x180006c94  mov     r9, rbx; SourceSize
0x180006c97  call    memcpy_s
0x180006c9c  mov     byte ptr [rbx+rdi-1], 0
0x180006ca1  mov     al, 1
0x180006ca3  add     rsp, 28h
0x180006ca7  pop     rdi
0x180006ca8  pop     rsi
0x180006ca9  pop     rbp
0x180006caa  pop     rbx
0x180006cab  retn
```
