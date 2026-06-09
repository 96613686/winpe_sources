# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180008310`
- end: `0x1800083ed`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007c74`
- `0x180008310`

## callees

- `0x180008310`
- `0x18000a028`

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
0x180008310  push    rbx
0x180008312  push    rbp
0x180008313  push    rsi
0x180008314  push    rdi
0x180008315  sub     rsp, 28h
0x180008319  xor     al, al
0x18000831b  mov     byte ptr [r8], 0
0x18000831f  mov     rbp, r9
0x180008322  mov     rdi, r8
0x180008325  mov     rsi, rdx
0x180008328  mov     rbx, rcx
0x18000832b  test    rdx, rdx
0x18000832e  jz      loc_1800083E3
0x180008334  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180008338  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000833d  mov     rdx, [rsi+20h]
0x180008341  test    rdx, rdx
0x180008344  jz      loc_1800083E3
0x18000834a  cmp     dword ptr [rdx], 0
0x18000834d  jnz     short loc_180008360
0x18000834f  mov     eax, 1
0x180008354  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000835c  inc     eax
0x18000835e  mov     [rdx], eax
0x180008360  cmp     dword ptr [rbx+50h], 0
0x180008364  jnz     short loc_180008377
0x180008366  movups  xmm0, xmmword ptr [rdx]
0x180008369  movups  xmmword ptr [rbx+50h], xmm0
0x18000836d  movsd   xmm1, qword ptr [rdx+10h]
0x180008372  movsd   qword ptr [rbx+60h], xmm1
0x180008377  movups  xmm0, xmmword ptr [rdx]
0x18000837a  lea     r10, [rdi+rbp]
0x18000837e  movups  xmmword ptr [rbx+68h], xmm0
0x180008382  movsd   xmm1, qword ptr [rdx+10h]
0x180008387  movsd   qword ptr [rbx+78h], xmm1
0x18000838c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008390  mov     rax, rbx
0x180008393  inc     rax
0x180008396  cmp     byte ptr [rdi+rax], 0
0x18000839a  jnz     short loc_180008393
0x18000839c  lea     rcx, [rax+rdi]
0x1800083a0  mov     rax, r10
0x1800083a3  sub     rax, rcx
0x1800083a6  cmp     rax, 2
0x1800083aa  jle     short loc_1800083E1
0x1800083ac  mov     byte ptr [rcx], 5Ch ; '\'
0x1800083af  lea     rdi, [rcx+1]
0x1800083b3  mov     r8, [rdx+8]; Source
0x1800083b7  inc     rbx
0x1800083ba  cmp     byte ptr [r8+rbx], 0
0x1800083bf  jnz     short loc_1800083B7
0x1800083c1  sub     r10, rdi
0x1800083c4  inc     rbx
0x1800083c7  cmp     rbx, r10
0x1800083ca  mov     rdx, r10; DestinationSize
0x1800083cd  mov     rcx, rdi; Destination
0x1800083d0  cmovnb  rbx, r10
0x1800083d4  mov     r9, rbx; SourceSize
0x1800083d7  call    memcpy_s
0x1800083dc  mov     byte ptr [rbx+rdi-1], 0
0x1800083e1  mov     al, 1
0x1800083e3  add     rsp, 28h
0x1800083e7  pop     rdi
0x1800083e8  pop     rsi
0x1800083e9  pop     rbp
0x1800083ea  pop     rbx
0x1800083eb  retn
```
