# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004d00`
- end: `0x180004ddc`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004474`
- `0x180004d00`

## callees

- `0x180004d00`
- `0x1800074c8`

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
0x180004d00  push    rbx
0x180004d02  push    rbp
0x180004d03  push    rsi
0x180004d04  push    rdi
0x180004d05  sub     rsp, 28h
0x180004d09  xor     al, al
0x180004d0b  mov     byte ptr [r8], 0
0x180004d0f  mov     rbp, r9
0x180004d12  mov     rdi, r8
0x180004d15  mov     rsi, rdx
0x180004d18  mov     rbx, rcx
0x180004d1b  test    rdx, rdx
0x180004d1e  jz      loc_180004DD3
0x180004d24  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d28  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d2d  mov     rdx, [rsi+20h]
0x180004d31  test    rdx, rdx
0x180004d34  jz      loc_180004DD3
0x180004d3a  cmp     dword ptr [rdx], 0
0x180004d3d  jnz     short loc_180004D50
0x180004d3f  mov     eax, 1
0x180004d44  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004d4c  inc     eax
0x180004d4e  mov     [rdx], eax
0x180004d50  cmp     dword ptr [rbx+50h], 0
0x180004d54  jnz     short loc_180004D67
0x180004d56  movups  xmm0, xmmword ptr [rdx]
0x180004d59  movups  xmmword ptr [rbx+50h], xmm0
0x180004d5d  movsd   xmm1, qword ptr [rdx+10h]
0x180004d62  movsd   qword ptr [rbx+60h], xmm1
0x180004d67  movups  xmm0, xmmword ptr [rdx]
0x180004d6a  lea     r10, [rdi+rbp]
0x180004d6e  movups  xmmword ptr [rbx+68h], xmm0
0x180004d72  movsd   xmm1, qword ptr [rdx+10h]
0x180004d77  movsd   qword ptr [rbx+78h], xmm1
0x180004d7c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004d80  mov     rax, rbx
0x180004d83  inc     rax
0x180004d86  cmp     byte ptr [rdi+rax], 0
0x180004d8a  jnz     short loc_180004D83
0x180004d8c  lea     rcx, [rax+rdi]
0x180004d90  mov     rax, r10
0x180004d93  sub     rax, rcx
0x180004d96  cmp     rax, 2
0x180004d9a  jle     short loc_180004DD1
0x180004d9c  mov     byte ptr [rcx], 5Ch ; '\'
0x180004d9f  lea     rdi, [rcx+1]
0x180004da3  mov     r8, [rdx+8]; Source
0x180004da7  inc     rbx
0x180004daa  cmp     byte ptr [r8+rbx], 0
0x180004daf  jnz     short loc_180004DA7
0x180004db1  sub     r10, rdi
0x180004db4  inc     rbx
0x180004db7  cmp     rbx, r10
0x180004dba  mov     rdx, r10; DestinationSize
0x180004dbd  mov     rcx, rdi; Destination
0x180004dc0  cmovnb  rbx, r10
0x180004dc4  mov     r9, rbx; SourceSize
0x180004dc7  call    memcpy_s
0x180004dcc  mov     byte ptr [rbx+rdi-1], 0
0x180004dd1  mov     al, 1
0x180004dd3  add     rsp, 28h
0x180004dd7  pop     rdi
0x180004dd8  pop     rsi
0x180004dd9  pop     rbp
0x180004dda  pop     rbx
0x180004ddb  retn
```
