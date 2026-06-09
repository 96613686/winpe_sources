# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180007470`
- end: `0x18000754c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800071a0`
- `0x180007470`

## callees

- `0x180003a28`
- `0x180007470`

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
0x180007470  push    rbx
0x180007472  push    rbp
0x180007473  push    rsi
0x180007474  push    rdi
0x180007475  sub     rsp, 28h
0x180007479  xor     al, al
0x18000747b  mov     byte ptr [r8], 0
0x18000747f  mov     rbp, r9
0x180007482  mov     rdi, r8
0x180007485  mov     rsi, rdx
0x180007488  mov     rbx, rcx
0x18000748b  test    rdx, rdx
0x18000748e  jz      loc_180007543
0x180007494  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180007498  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000749d  mov     rdx, [rsi+20h]
0x1800074a1  test    rdx, rdx
0x1800074a4  jz      loc_180007543
0x1800074aa  cmp     dword ptr [rdx], 0
0x1800074ad  jnz     short loc_1800074C0
0x1800074af  mov     eax, 1
0x1800074b4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800074bc  inc     eax
0x1800074be  mov     [rdx], eax
0x1800074c0  cmp     dword ptr [rbx+50h], 0
0x1800074c4  jnz     short loc_1800074D7
0x1800074c6  movups  xmm0, xmmword ptr [rdx]
0x1800074c9  movups  xmmword ptr [rbx+50h], xmm0
0x1800074cd  movsd   xmm1, qword ptr [rdx+10h]
0x1800074d2  movsd   qword ptr [rbx+60h], xmm1
0x1800074d7  movups  xmm0, xmmword ptr [rdx]
0x1800074da  lea     r10, [rdi+rbp]
0x1800074de  movups  xmmword ptr [rbx+68h], xmm0
0x1800074e2  movsd   xmm1, qword ptr [rdx+10h]
0x1800074e7  movsd   qword ptr [rbx+78h], xmm1
0x1800074ec  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800074f0  mov     rax, rbx
0x1800074f3  inc     rax
0x1800074f6  cmp     byte ptr [rdi+rax], 0
0x1800074fa  jnz     short loc_1800074F3
0x1800074fc  lea     rcx, [rax+rdi]
0x180007500  mov     rax, r10
0x180007503  sub     rax, rcx
0x180007506  cmp     rax, 2
0x18000750a  jle     short loc_180007541
0x18000750c  mov     byte ptr [rcx], 5Ch ; '\'
0x18000750f  lea     rdi, [rcx+1]
0x180007513  mov     r8, [rdx+8]; Source
0x180007517  inc     rbx
0x18000751a  cmp     byte ptr [r8+rbx], 0
0x18000751f  jnz     short loc_180007517
0x180007521  sub     r10, rdi
0x180007524  inc     rbx
0x180007527  cmp     rbx, r10
0x18000752a  mov     rdx, r10; DestinationSize
0x18000752d  mov     rcx, rdi; Destination
0x180007530  cmovnb  rbx, r10
0x180007534  mov     r9, rbx; SourceSize
0x180007537  call    memcpy_s
0x18000753c  mov     byte ptr [rbx+rdi-1], 0
0x180007541  mov     al, 1
0x180007543  add     rsp, 28h
0x180007547  pop     rdi
0x180007548  pop     rsi
0x180007549  pop     rbp
0x18000754a  pop     rbx
0x18000754b  retn
```
