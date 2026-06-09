# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180003f10`
- end: `0x180004005`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `245`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f10`
- `0x180004010`

## callees

- `0x180001ab4`
- `0x180003f10`

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
  __int64 v10; // rcx
  char *v11; // r10
  __int64 v12; // rax
  char *v13; // rbx
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // rcx
  rsize_t v17; // rbx

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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v11 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v10;
        while ( v15[v10] );
        v16 = v10 + 1;
        v17 = v11 - v14;
        if ( v16 < v11 - v14 )
          v17 = v16;
        memcpy_s(v14, v11 - v14, v15, v17);
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
0x180003f10  mov     [rsp+arg_0], rbx
0x180003f15  mov     [rsp+arg_8], rbp
0x180003f1a  mov     [rsp+arg_10], rsi
0x180003f1f  push    rdi
0x180003f20  sub     rsp, 20h
0x180003f24  xor     al, al
0x180003f26  mov     byte ptr [r8], 0
0x180003f2a  mov     rbp, r9
0x180003f2d  mov     rbx, r8
0x180003f30  mov     rsi, rdx
0x180003f33  mov     rdi, rcx
0x180003f36  test    rdx, rdx
0x180003f39  jz      loc_180003FF0
0x180003f3f  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180003f43  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003f48  mov     rdx, [rsi+20h]
0x180003f4c  test    rdx, rdx
0x180003f4f  jz      loc_180003FF0
0x180003f55  cmp     dword ptr [rdx], 0
0x180003f58  jnz     short loc_180003F6B
0x180003f5a  mov     eax, 1
0x180003f5f  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180003f67  inc     eax
0x180003f69  mov     [rdx], eax
0x180003f6b  cmp     dword ptr [rdi+50h], 0
0x180003f6f  jnz     short loc_180003F82
0x180003f71  movups  xmm0, xmmword ptr [rdx]
0x180003f74  movups  xmmword ptr [rdi+50h], xmm0
0x180003f78  movsd   xmm1, qword ptr [rdx+10h]
0x180003f7d  movsd   qword ptr [rdi+60h], xmm1
0x180003f82  movups  xmm0, xmmword ptr [rdx]
0x180003f85  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003f89  lea     r10, [rbx+rbp]
0x180003f8d  mov     rax, rcx
0x180003f90  movups  xmmword ptr [rdi+68h], xmm0
0x180003f94  movsd   xmm1, qword ptr [rdx+10h]
0x180003f99  movsd   qword ptr [rdi+78h], xmm1
0x180003f9e  inc     rax
0x180003fa1  cmp     byte ptr [rbx+rax], 0
0x180003fa5  jnz     short loc_180003F9E
0x180003fa7  add     rbx, rax
0x180003faa  mov     rax, r10
0x180003fad  sub     rax, rbx
0x180003fb0  cmp     rax, 2
0x180003fb4  jle     short loc_180003FEE
0x180003fb6  mov     byte ptr [rbx], 5Ch ; '\'
0x180003fb9  lea     rdi, [rbx+1]
0x180003fbd  mov     r8, [rdx+8]; Source
0x180003fc1  inc     rcx
0x180003fc4  cmp     byte ptr [r8+rcx], 0
0x180003fc9  jnz     short loc_180003FC1
0x180003fcb  inc     rcx
0x180003fce  sub     r10, rdi
0x180003fd1  cmp     rcx, r10
0x180003fd4  mov     rbx, r10
0x180003fd7  mov     rdx, r10; DestinationSize
0x180003fda  cmovb   rbx, rcx
0x180003fde  mov     rcx, rdi; Destination
0x180003fe1  mov     r9, rbx; SourceSize
0x180003fe4  call    memcpy_s
0x180003fe9  mov     byte ptr [rbx+rdi-1], 0
0x180003fee  mov     al, 1
0x180003ff0  mov     rbx, [rsp+28h+arg_0]
0x180003ff5  mov     rbp, [rsp+28h+arg_8]
0x180003ffa  mov     rsi, [rsp+28h+arg_10]
0x180003fff  add     rsp, 20h
0x180004003  pop     rdi
0x180004004  retn
```
