# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000e69c`
- end: `0x18000e779`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dcc8`
- `0x18000e69c`

## callees

- `0x18000e69c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e763`
- `msvcrt!memcpy_s` at `0x18000e763`

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
0x18000e69c  push    rbx
0x18000e69e  push    rbp
0x18000e69f  push    rsi
0x18000e6a0  push    rdi
0x18000e6a1  sub     rsp, 28h
0x18000e6a5  xor     al, al
0x18000e6a7  mov     byte ptr [r8], 0
0x18000e6ab  mov     rbp, r9
0x18000e6ae  mov     rdi, r8
0x18000e6b1  mov     rsi, rdx
0x18000e6b4  mov     rbx, rcx
0x18000e6b7  test    rdx, rdx
0x18000e6ba  jz      loc_18000E770
0x18000e6c0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000e6c4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000e6c9  mov     rdx, [rsi+20h]
0x18000e6cd  test    rdx, rdx
0x18000e6d0  jz      loc_18000E770
0x18000e6d6  cmp     dword ptr [rdx], 0
0x18000e6d9  jnz     short loc_18000E6EC
0x18000e6db  mov     eax, 1
0x18000e6e0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000e6e8  inc     eax
0x18000e6ea  mov     [rdx], eax
0x18000e6ec  cmp     dword ptr [rbx+50h], 0
0x18000e6f0  jnz     short loc_18000E703
0x18000e6f2  movups  xmm0, xmmword ptr [rdx]
0x18000e6f5  movups  xmmword ptr [rbx+50h], xmm0
0x18000e6f9  movsd   xmm1, qword ptr [rdx+10h]
0x18000e6fe  movsd   qword ptr [rbx+60h], xmm1
0x18000e703  movups  xmm0, xmmword ptr [rdx]
0x18000e706  lea     r10, [rdi+rbp]
0x18000e70a  movups  xmmword ptr [rbx+68h], xmm0
0x18000e70e  movsd   xmm1, qword ptr [rdx+10h]
0x18000e713  movsd   qword ptr [rbx+78h], xmm1
0x18000e718  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e71c  mov     rax, rbx
0x18000e71f  inc     rax
0x18000e722  cmp     byte ptr [rdi+rax], 0
0x18000e726  jnz     short loc_18000E71F
0x18000e728  lea     rcx, [rax+rdi]
0x18000e72c  mov     rax, r10
0x18000e72f  sub     rax, rcx
0x18000e732  cmp     rax, 2
0x18000e736  jle     short loc_18000E76E
0x18000e738  mov     byte ptr [rcx], 5Ch ; '\'
0x18000e73b  lea     rdi, [rcx+1]
0x18000e73f  mov     r8, [rdx+8]; Source
0x18000e743  inc     rbx
0x18000e746  cmp     byte ptr [r8+rbx], 0
0x18000e74b  jnz     short loc_18000E743
0x18000e74d  sub     r10, rdi
0x18000e750  inc     rbx
0x18000e753  cmp     rbx, r10
0x18000e756  mov     rdx, r10; DestinationSize
0x18000e759  mov     rcx, rdi; Destination
0x18000e75c  cmovnb  rbx, r10
0x18000e760  mov     r9, rbx; SourceSize
0x18000e763  call    cs:__imp_memcpy_s
0x18000e769  mov     byte ptr [rbx+rdi-1], 0
0x18000e76e  mov     al, 1
0x18000e770  add     rsp, 28h
0x18000e774  pop     rdi
0x18000e775  pop     rsi
0x18000e776  pop     rbp
0x18000e777  pop     rbx
0x18000e778  retn
```
