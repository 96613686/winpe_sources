# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004698`
- end: `0x180004775`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fa0`
- `0x180004698`

## callees

- `0x180004698`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000475f`
- `msvcrt!memcpy_s` at `0x18000475f`

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
0x180004698  push    rbx
0x18000469a  push    rbp
0x18000469b  push    rsi
0x18000469c  push    rdi
0x18000469d  sub     rsp, 28h
0x1800046a1  xor     al, al
0x1800046a3  mov     byte ptr [r8], 0
0x1800046a7  mov     rbp, r9
0x1800046aa  mov     rdi, r8
0x1800046ad  mov     rsi, rdx
0x1800046b0  mov     rbx, rcx
0x1800046b3  test    rdx, rdx
0x1800046b6  jz      loc_18000476C
0x1800046bc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800046c0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800046c5  mov     rdx, [rsi+20h]
0x1800046c9  test    rdx, rdx
0x1800046cc  jz      loc_18000476C
0x1800046d2  cmp     dword ptr [rdx], 0
0x1800046d5  jnz     short loc_1800046E8
0x1800046d7  mov     eax, 1
0x1800046dc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800046e4  inc     eax
0x1800046e6  mov     [rdx], eax
0x1800046e8  cmp     dword ptr [rbx+50h], 0
0x1800046ec  jnz     short loc_1800046FF
0x1800046ee  movups  xmm0, xmmword ptr [rdx]
0x1800046f1  movups  xmmword ptr [rbx+50h], xmm0
0x1800046f5  movsd   xmm1, qword ptr [rdx+10h]
0x1800046fa  movsd   qword ptr [rbx+60h], xmm1
0x1800046ff  movups  xmm0, xmmword ptr [rdx]
0x180004702  lea     r10, [rdi+rbp]
0x180004706  movups  xmmword ptr [rbx+68h], xmm0
0x18000470a  movsd   xmm1, qword ptr [rdx+10h]
0x18000470f  movsd   qword ptr [rbx+78h], xmm1
0x180004714  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004718  mov     rax, rbx
0x18000471b  inc     rax
0x18000471e  cmp     byte ptr [rdi+rax], 0
0x180004722  jnz     short loc_18000471B
0x180004724  lea     rcx, [rax+rdi]
0x180004728  mov     rax, r10
0x18000472b  sub     rax, rcx
0x18000472e  cmp     rax, 2
0x180004732  jle     short loc_18000476A
0x180004734  mov     byte ptr [rcx], 5Ch ; '\'
0x180004737  lea     rdi, [rcx+1]
0x18000473b  mov     r8, [rdx+8]; Source
0x18000473f  inc     rbx
0x180004742  cmp     byte ptr [r8+rbx], 0
0x180004747  jnz     short loc_18000473F
0x180004749  sub     r10, rdi
0x18000474c  inc     rbx
0x18000474f  cmp     rbx, r10
0x180004752  mov     rdx, r10; DestinationSize
0x180004755  mov     rcx, rdi; Destination
0x180004758  cmovnb  rbx, r10
0x18000475c  mov     r9, rbx; SourceSize
0x18000475f  call    cs:__imp_memcpy_s
0x180004765  mov     byte ptr [rbx+rdi-1], 0
0x18000476a  mov     al, 1
0x18000476c  add     rsp, 28h
0x180004770  pop     rdi
0x180004771  pop     rsi
0x180004772  pop     rbp
0x180004773  pop     rbx
0x180004774  retn
```
