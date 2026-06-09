# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180015170`
- end: `0x18001524c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014b58`
- `0x180015170`

## callees

- `0x18000f770`
- `0x180015170`

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
0x180015170  push    rbx
0x180015172  push    rbp
0x180015173  push    rsi
0x180015174  push    rdi
0x180015175  sub     rsp, 28h
0x180015179  xor     al, al
0x18001517b  mov     byte ptr [r8], 0
0x18001517f  mov     rbp, r9
0x180015182  mov     rdi, r8
0x180015185  mov     rsi, rdx
0x180015188  mov     rbx, rcx
0x18001518b  test    rdx, rdx
0x18001518e  jz      loc_180015243
0x180015194  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180015198  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001519d  mov     rdx, [rsi+20h]
0x1800151a1  test    rdx, rdx
0x1800151a4  jz      loc_180015243
0x1800151aa  cmp     dword ptr [rdx], 0
0x1800151ad  jnz     short loc_1800151C0
0x1800151af  mov     eax, 1
0x1800151b4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800151bc  inc     eax
0x1800151be  mov     [rdx], eax
0x1800151c0  cmp     dword ptr [rbx+50h], 0
0x1800151c4  jnz     short loc_1800151D7
0x1800151c6  movups  xmm0, xmmword ptr [rdx]
0x1800151c9  movups  xmmword ptr [rbx+50h], xmm0
0x1800151cd  movsd   xmm1, qword ptr [rdx+10h]
0x1800151d2  movsd   qword ptr [rbx+60h], xmm1
0x1800151d7  movups  xmm0, xmmword ptr [rdx]
0x1800151da  lea     r10, [rdi+rbp]
0x1800151de  movups  xmmword ptr [rbx+68h], xmm0
0x1800151e2  movsd   xmm1, qword ptr [rdx+10h]
0x1800151e7  movsd   qword ptr [rbx+78h], xmm1
0x1800151ec  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800151f0  mov     rax, rbx
0x1800151f3  inc     rax
0x1800151f6  cmp     byte ptr [rdi+rax], 0
0x1800151fa  jnz     short loc_1800151F3
0x1800151fc  lea     rcx, [rax+rdi]
0x180015200  mov     rax, r10
0x180015203  sub     rax, rcx
0x180015206  cmp     rax, 2
0x18001520a  jle     short loc_180015241
0x18001520c  mov     byte ptr [rcx], 5Ch ; '\'
0x18001520f  lea     rdi, [rcx+1]
0x180015213  mov     r8, [rdx+8]; Source
0x180015217  inc     rbx
0x18001521a  cmp     byte ptr [r8+rbx], 0
0x18001521f  jnz     short loc_180015217
0x180015221  sub     r10, rdi
0x180015224  inc     rbx
0x180015227  cmp     rbx, r10
0x18001522a  mov     rdx, r10; DestinationSize
0x18001522d  mov     rcx, rdi; Destination
0x180015230  cmovnb  rbx, r10
0x180015234  mov     r9, rbx; SourceSize
0x180015237  call    memcpy_s
0x18001523c  mov     byte ptr [rbx+rdi-1], 0
0x180015241  mov     al, 1
0x180015243  add     rsp, 28h
0x180015247  pop     rdi
0x180015248  pop     rsi
0x180015249  pop     rbp
0x18001524a  pop     rbx
0x18001524b  retn
```
