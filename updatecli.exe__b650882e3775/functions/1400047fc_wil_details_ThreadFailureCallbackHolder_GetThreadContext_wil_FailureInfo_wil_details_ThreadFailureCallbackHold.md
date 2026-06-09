# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1400047fc`
- end: `0x1400048d8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004100`
- `0x1400047fc`

## callees

- `0x1400047fc`
- `0x1400064a8`

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
0x1400047fc  push    rbx
0x1400047fe  push    rbp
0x1400047ff  push    rsi
0x140004800  push    rdi
0x140004801  sub     rsp, 28h
0x140004805  xor     al, al
0x140004807  mov     byte ptr [r8], 0
0x14000480b  mov     rbp, r9
0x14000480e  mov     rdi, r8
0x140004811  mov     rsi, rdx
0x140004814  mov     rbx, rcx
0x140004817  test    rdx, rdx
0x14000481a  jz      loc_1400048CF
0x140004820  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004824  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004829  mov     rdx, [rsi+20h]
0x14000482d  test    rdx, rdx
0x140004830  jz      loc_1400048CF
0x140004836  cmp     dword ptr [rdx], 0
0x140004839  jnz     short loc_14000484C
0x14000483b  mov     eax, 1
0x140004840  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004848  inc     eax
0x14000484a  mov     [rdx], eax
0x14000484c  cmp     dword ptr [rbx+50h], 0
0x140004850  jnz     short loc_140004863
0x140004852  movups  xmm0, xmmword ptr [rdx]
0x140004855  movups  xmmword ptr [rbx+50h], xmm0
0x140004859  movsd   xmm1, qword ptr [rdx+10h]
0x14000485e  movsd   qword ptr [rbx+60h], xmm1
0x140004863  movups  xmm0, xmmword ptr [rdx]
0x140004866  lea     r10, [rdi+rbp]
0x14000486a  movups  xmmword ptr [rbx+68h], xmm0
0x14000486e  movsd   xmm1, qword ptr [rdx+10h]
0x140004873  movsd   qword ptr [rbx+78h], xmm1
0x140004878  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000487c  mov     rax, rbx
0x14000487f  inc     rax
0x140004882  cmp     byte ptr [rdi+rax], 0
0x140004886  jnz     short loc_14000487F
0x140004888  lea     rcx, [rax+rdi]
0x14000488c  mov     rax, r10
0x14000488f  sub     rax, rcx
0x140004892  cmp     rax, 2
0x140004896  jle     short loc_1400048CD
0x140004898  mov     byte ptr [rcx], 5Ch ; '\'
0x14000489b  lea     rdi, [rcx+1]
0x14000489f  mov     r8, [rdx+8]; Source
0x1400048a3  inc     rbx
0x1400048a6  cmp     byte ptr [r8+rbx], 0
0x1400048ab  jnz     short loc_1400048A3
0x1400048ad  sub     r10, rdi
0x1400048b0  inc     rbx
0x1400048b3  cmp     rbx, r10
0x1400048b6  mov     rdx, r10; DestinationSize
0x1400048b9  mov     rcx, rdi; Destination
0x1400048bc  cmovnb  rbx, r10
0x1400048c0  mov     r9, rbx; SourceSize
0x1400048c3  call    memcpy_s
0x1400048c8  mov     byte ptr [rbx+rdi-1], 0
0x1400048cd  mov     al, 1
0x1400048cf  add     rsp, 28h
0x1400048d3  pop     rdi
0x1400048d4  pop     rsi
0x1400048d5  pop     rbp
0x1400048d6  pop     rbx
0x1400048d7  retn
```
