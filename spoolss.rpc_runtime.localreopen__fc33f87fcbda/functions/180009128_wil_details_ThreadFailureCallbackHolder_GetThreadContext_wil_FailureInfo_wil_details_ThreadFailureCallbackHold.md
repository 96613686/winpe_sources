# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180009128`
- end: `0x180009205`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008810`
- `0x180009128`

## callees

- `0x180009128`
- `0x18001028c`

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
0x180009128  push    rbx
0x18000912a  push    rbp
0x18000912b  push    rsi
0x18000912c  push    rdi
0x18000912d  sub     rsp, 28h
0x180009131  xor     al, al
0x180009133  mov     byte ptr [r8], 0
0x180009137  mov     rbp, r9
0x18000913a  mov     rdi, r8
0x18000913d  mov     rsi, rdx
0x180009140  mov     rbx, rcx
0x180009143  test    rdx, rdx
0x180009146  jz      loc_1800091FB
0x18000914c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180009150  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009155  mov     rdx, [rsi+20h]
0x180009159  test    rdx, rdx
0x18000915c  jz      loc_1800091FB
0x180009162  cmp     dword ptr [rdx], 0
0x180009165  jnz     short loc_180009178
0x180009167  mov     eax, 1
0x18000916c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180009174  inc     eax
0x180009176  mov     [rdx], eax
0x180009178  cmp     dword ptr [rbx+50h], 0
0x18000917c  jnz     short loc_18000918F
0x18000917e  movups  xmm0, xmmword ptr [rdx]
0x180009181  movups  xmmword ptr [rbx+50h], xmm0
0x180009185  movsd   xmm1, qword ptr [rdx+10h]
0x18000918a  movsd   qword ptr [rbx+60h], xmm1
0x18000918f  movups  xmm0, xmmword ptr [rdx]
0x180009192  lea     r10, [rdi+rbp]
0x180009196  movups  xmmword ptr [rbx+68h], xmm0
0x18000919a  movsd   xmm1, qword ptr [rdx+10h]
0x18000919f  movsd   qword ptr [rbx+78h], xmm1
0x1800091a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800091a8  mov     rax, rbx
0x1800091ab  inc     rax
0x1800091ae  cmp     byte ptr [rdi+rax], 0
0x1800091b2  jnz     short loc_1800091AB
0x1800091b4  lea     rcx, [rax+rdi]
0x1800091b8  mov     rax, r10
0x1800091bb  sub     rax, rcx
0x1800091be  cmp     rax, 2
0x1800091c2  jle     short loc_1800091F9
0x1800091c4  mov     byte ptr [rcx], 5Ch ; '\'
0x1800091c7  lea     rdi, [rcx+1]
0x1800091cb  mov     r8, [rdx+8]; Source
0x1800091cf  inc     rbx
0x1800091d2  cmp     byte ptr [r8+rbx], 0
0x1800091d7  jnz     short loc_1800091CF
0x1800091d9  sub     r10, rdi
0x1800091dc  inc     rbx
0x1800091df  cmp     rbx, r10
0x1800091e2  mov     rdx, r10; DestinationSize
0x1800091e5  mov     rcx, rdi; Destination
0x1800091e8  cmovnb  rbx, r10
0x1800091ec  mov     r9, rbx; SourceSize
0x1800091ef  call    memcpy_s
0x1800091f4  mov     byte ptr [rbx+rdi-1], 0
0x1800091f9  mov     al, 1
0x1800091fb  add     rsp, 28h
0x1800091ff  pop     rdi
0x180009200  pop     rsi
0x180009201  pop     rbp
0x180009202  pop     rbx
0x180009203  retn
```
