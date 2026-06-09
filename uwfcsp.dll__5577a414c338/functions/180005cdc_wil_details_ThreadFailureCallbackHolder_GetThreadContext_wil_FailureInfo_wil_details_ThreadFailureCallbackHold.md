# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180005cdc`
- end: `0x180005db9`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005600`
- `0x180005cdc`

## callees

- `0x180005cdc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005da3`
- `msvcrt!memcpy_s` at `0x180005da3`

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
0x180005cdc  push    rbx
0x180005cde  push    rbp
0x180005cdf  push    rsi
0x180005ce0  push    rdi
0x180005ce1  sub     rsp, 28h
0x180005ce5  xor     al, al
0x180005ce7  mov     byte ptr [r8], 0
0x180005ceb  mov     rbp, r9
0x180005cee  mov     rdi, r8
0x180005cf1  mov     rsi, rdx
0x180005cf4  mov     rbx, rcx
0x180005cf7  test    rdx, rdx
0x180005cfa  jz      loc_180005DB0
0x180005d00  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005d04  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005d09  mov     rdx, [rsi+20h]
0x180005d0d  test    rdx, rdx
0x180005d10  jz      loc_180005DB0
0x180005d16  cmp     dword ptr [rdx], 0
0x180005d19  jnz     short loc_180005D2C
0x180005d1b  mov     eax, 1
0x180005d20  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005d28  inc     eax
0x180005d2a  mov     [rdx], eax
0x180005d2c  cmp     dword ptr [rbx+50h], 0
0x180005d30  jnz     short loc_180005D43
0x180005d32  movups  xmm0, xmmword ptr [rdx]
0x180005d35  movups  xmmword ptr [rbx+50h], xmm0
0x180005d39  movsd   xmm1, qword ptr [rdx+10h]
0x180005d3e  movsd   qword ptr [rbx+60h], xmm1
0x180005d43  movups  xmm0, xmmword ptr [rdx]
0x180005d46  lea     r10, [rdi+rbp]
0x180005d4a  movups  xmmword ptr [rbx+68h], xmm0
0x180005d4e  movsd   xmm1, qword ptr [rdx+10h]
0x180005d53  movsd   qword ptr [rbx+78h], xmm1
0x180005d58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005d5c  mov     rax, rbx
0x180005d5f  inc     rax
0x180005d62  cmp     byte ptr [rdi+rax], 0
0x180005d66  jnz     short loc_180005D5F
0x180005d68  lea     rcx, [rax+rdi]
0x180005d6c  mov     rax, r10
0x180005d6f  sub     rax, rcx
0x180005d72  cmp     rax, 2
0x180005d76  jle     short loc_180005DAE
0x180005d78  mov     byte ptr [rcx], 5Ch ; '\'
0x180005d7b  lea     rdi, [rcx+1]
0x180005d7f  mov     r8, [rdx+8]; Source
0x180005d83  inc     rbx
0x180005d86  cmp     byte ptr [r8+rbx], 0
0x180005d8b  jnz     short loc_180005D83
0x180005d8d  sub     r10, rdi
0x180005d90  inc     rbx
0x180005d93  cmp     rbx, r10
0x180005d96  mov     rdx, r10; DestinationSize
0x180005d99  mov     rcx, rdi; Destination
0x180005d9c  cmovnb  rbx, r10
0x180005da0  mov     r9, rbx; SourceSize
0x180005da3  call    cs:__imp_memcpy_s
0x180005da9  mov     byte ptr [rbx+rdi-1], 0
0x180005dae  mov     al, 1
0x180005db0  add     rsp, 28h
0x180005db4  pop     rdi
0x180005db5  pop     rsi
0x180005db6  pop     rbp
0x180005db7  pop     rbx
0x180005db8  retn
```
