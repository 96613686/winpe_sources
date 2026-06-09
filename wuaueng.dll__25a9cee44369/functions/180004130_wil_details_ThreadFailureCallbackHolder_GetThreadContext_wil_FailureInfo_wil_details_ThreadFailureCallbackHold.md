# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004130`
- end: `0x180004225`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `245`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004130`
- `0x180004230`

## callees

- `0x180001ab4`
- `0x180004130`

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
0x180004130  mov     [rsp+arg_0], rbx
0x180004135  mov     [rsp+arg_8], rbp
0x18000413a  mov     [rsp+arg_10], rsi
0x18000413f  push    rdi
0x180004140  sub     rsp, 20h
0x180004144  xor     al, al
0x180004146  mov     byte ptr [r8], 0
0x18000414a  mov     rbp, r9
0x18000414d  mov     rbx, r8
0x180004150  mov     rsi, rdx
0x180004153  mov     rdi, rcx
0x180004156  test    rdx, rdx
0x180004159  jz      loc_180004210
0x18000415f  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004163  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004168  mov     rdx, [rsi+20h]
0x18000416c  test    rdx, rdx
0x18000416f  jz      loc_180004210
0x180004175  cmp     dword ptr [rdx], 0
0x180004178  jnz     short loc_18000418B
0x18000417a  mov     eax, 1
0x18000417f  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004187  inc     eax
0x180004189  mov     [rdx], eax
0x18000418b  cmp     dword ptr [rdi+50h], 0
0x18000418f  jnz     short loc_1800041A2
0x180004191  movups  xmm0, xmmword ptr [rdx]
0x180004194  movups  xmmword ptr [rdi+50h], xmm0
0x180004198  movsd   xmm1, qword ptr [rdx+10h]
0x18000419d  movsd   qword ptr [rdi+60h], xmm1
0x1800041a2  movups  xmm0, xmmword ptr [rdx]
0x1800041a5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800041a9  lea     r10, [rbx+rbp]
0x1800041ad  mov     rax, rcx
0x1800041b0  movups  xmmword ptr [rdi+68h], xmm0
0x1800041b4  movsd   xmm1, qword ptr [rdx+10h]
0x1800041b9  movsd   qword ptr [rdi+78h], xmm1
0x1800041be  inc     rax
0x1800041c1  cmp     byte ptr [rbx+rax], 0
0x1800041c5  jnz     short loc_1800041BE
0x1800041c7  add     rbx, rax
0x1800041ca  mov     rax, r10
0x1800041cd  sub     rax, rbx
0x1800041d0  cmp     rax, 2
0x1800041d4  jle     short loc_18000420E
0x1800041d6  mov     byte ptr [rbx], 5Ch ; '\'
0x1800041d9  lea     rdi, [rbx+1]
0x1800041dd  mov     r8, [rdx+8]; Source
0x1800041e1  inc     rcx
0x1800041e4  cmp     byte ptr [r8+rcx], 0
0x1800041e9  jnz     short loc_1800041E1
0x1800041eb  inc     rcx
0x1800041ee  sub     r10, rdi
0x1800041f1  cmp     rcx, r10
0x1800041f4  mov     rbx, r10
0x1800041f7  mov     rdx, r10; DestinationSize
0x1800041fa  cmovb   rbx, rcx
0x1800041fe  mov     rcx, rdi; Destination
0x180004201  mov     r9, rbx; SourceSize
0x180004204  call    memcpy_s
0x180004209  mov     byte ptr [rbx+rdi-1], 0
0x18000420e  mov     al, 1
0x180004210  mov     rbx, [rsp+28h+arg_0]
0x180004215  mov     rbp, [rsp+28h+arg_8]
0x18000421a  mov     rsi, [rsp+28h+arg_10]
0x18000421f  add     rsp, 20h
0x180004223  pop     rdi
0x180004224  retn
```
