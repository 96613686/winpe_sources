# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000d524`
- end: `0x18000d601`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d124`
- `0x18000d524`

## callees

- `0x18000aaf4`
- `0x18000d524`

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
0x18000d524  push    rbx
0x18000d526  push    rbp
0x18000d527  push    rsi
0x18000d528  push    rdi
0x18000d529  sub     rsp, 28h
0x18000d52d  xor     al, al
0x18000d52f  mov     byte ptr [r8], 0
0x18000d533  mov     rbp, r9
0x18000d536  mov     rdi, r8
0x18000d539  mov     rsi, rdx
0x18000d53c  mov     rbx, rcx
0x18000d53f  test    rdx, rdx
0x18000d542  jz      loc_18000D5F7
0x18000d548  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d54c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d551  mov     rdx, [rsi+20h]
0x18000d555  test    rdx, rdx
0x18000d558  jz      loc_18000D5F7
0x18000d55e  cmp     dword ptr [rdx], 0
0x18000d561  jnz     short loc_18000D574
0x18000d563  mov     eax, 1
0x18000d568  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000d570  inc     eax
0x18000d572  mov     [rdx], eax
0x18000d574  cmp     dword ptr [rbx+50h], 0
0x18000d578  jnz     short loc_18000D58B
0x18000d57a  movups  xmm0, xmmword ptr [rdx]
0x18000d57d  movups  xmmword ptr [rbx+50h], xmm0
0x18000d581  movsd   xmm1, qword ptr [rdx+10h]
0x18000d586  movsd   qword ptr [rbx+60h], xmm1
0x18000d58b  movups  xmm0, xmmword ptr [rdx]
0x18000d58e  lea     r10, [rdi+rbp]
0x18000d592  movups  xmmword ptr [rbx+68h], xmm0
0x18000d596  movsd   xmm1, qword ptr [rdx+10h]
0x18000d59b  movsd   qword ptr [rbx+78h], xmm1
0x18000d5a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d5a4  mov     rax, rbx
0x18000d5a7  inc     rax
0x18000d5aa  cmp     byte ptr [rdi+rax], 0
0x18000d5ae  jnz     short loc_18000D5A7
0x18000d5b0  lea     rcx, [rax+rdi]
0x18000d5b4  mov     rax, r10
0x18000d5b7  sub     rax, rcx
0x18000d5ba  cmp     rax, 2
0x18000d5be  jle     short loc_18000D5F5
0x18000d5c0  mov     byte ptr [rcx], 5Ch ; '\'
0x18000d5c3  lea     rdi, [rcx+1]
0x18000d5c7  mov     r8, [rdx+8]; Source
0x18000d5cb  inc     rbx
0x18000d5ce  cmp     byte ptr [r8+rbx], 0
0x18000d5d3  jnz     short loc_18000D5CB
0x18000d5d5  sub     r10, rdi
0x18000d5d8  inc     rbx
0x18000d5db  cmp     rbx, r10
0x18000d5de  mov     rdx, r10; DestinationSize
0x18000d5e1  mov     rcx, rdi; Destination
0x18000d5e4  cmovnb  rbx, r10
0x18000d5e8  mov     r9, rbx; SourceSize
0x18000d5eb  call    memcpy_s
0x18000d5f0  mov     byte ptr [rbx+rdi-1], 0
0x18000d5f5  mov     al, 1
0x18000d5f7  add     rsp, 28h
0x18000d5fb  pop     rdi
0x18000d5fc  pop     rsi
0x18000d5fd  pop     rbp
0x18000d5fe  pop     rbx
0x18000d5ff  retn
```
