# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180008244`
- end: `0x180008320`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007be8`
- `0x180008244`

## callees

- `0x180008244`
- `0x180009dfc`

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
0x180008244  push    rbx
0x180008246  push    rbp
0x180008247  push    rsi
0x180008248  push    rdi
0x180008249  sub     rsp, 28h
0x18000824d  xor     al, al
0x18000824f  mov     byte ptr [r8], 0
0x180008253  mov     rbp, r9
0x180008256  mov     rdi, r8
0x180008259  mov     rsi, rdx
0x18000825c  mov     rbx, rcx
0x18000825f  test    rdx, rdx
0x180008262  jz      loc_180008317
0x180008268  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000826c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008271  mov     rdx, [rsi+20h]
0x180008275  test    rdx, rdx
0x180008278  jz      loc_180008317
0x18000827e  cmp     dword ptr [rdx], 0
0x180008281  jnz     short loc_180008294
0x180008283  mov     eax, 1
0x180008288  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180008290  inc     eax
0x180008292  mov     [rdx], eax
0x180008294  cmp     dword ptr [rbx+50h], 0
0x180008298  jnz     short loc_1800082AB
0x18000829a  movups  xmm0, xmmword ptr [rdx]
0x18000829d  movups  xmmword ptr [rbx+50h], xmm0
0x1800082a1  movsd   xmm1, qword ptr [rdx+10h]
0x1800082a6  movsd   qword ptr [rbx+60h], xmm1
0x1800082ab  movups  xmm0, xmmword ptr [rdx]
0x1800082ae  lea     r10, [rdi+rbp]
0x1800082b2  movups  xmmword ptr [rbx+68h], xmm0
0x1800082b6  movsd   xmm1, qword ptr [rdx+10h]
0x1800082bb  movsd   qword ptr [rbx+78h], xmm1
0x1800082c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800082c4  mov     rax, rbx
0x1800082c7  inc     rax
0x1800082ca  cmp     byte ptr [rdi+rax], 0
0x1800082ce  jnz     short loc_1800082C7
0x1800082d0  lea     rcx, [rax+rdi]
0x1800082d4  mov     rax, r10
0x1800082d7  sub     rax, rcx
0x1800082da  cmp     rax, 2
0x1800082de  jle     short loc_180008315
0x1800082e0  mov     byte ptr [rcx], 5Ch ; '\'
0x1800082e3  lea     rdi, [rcx+1]
0x1800082e7  mov     r8, [rdx+8]; Source
0x1800082eb  inc     rbx
0x1800082ee  cmp     byte ptr [r8+rbx], 0
0x1800082f3  jnz     short loc_1800082EB
0x1800082f5  sub     r10, rdi
0x1800082f8  inc     rbx
0x1800082fb  cmp     rbx, r10
0x1800082fe  mov     rdx, r10; DestinationSize
0x180008301  mov     rcx, rdi; Destination
0x180008304  cmovnb  rbx, r10
0x180008308  mov     r9, rbx; SourceSize
0x18000830b  call    memcpy_s
0x180008310  mov     byte ptr [rbx+rdi-1], 0
0x180008315  mov     al, 1
0x180008317  add     rsp, 28h
0x18000831b  pop     rdi
0x18000831c  pop     rsi
0x18000831d  pop     rbp
0x18000831e  pop     rbx
0x18000831f  retn
```
