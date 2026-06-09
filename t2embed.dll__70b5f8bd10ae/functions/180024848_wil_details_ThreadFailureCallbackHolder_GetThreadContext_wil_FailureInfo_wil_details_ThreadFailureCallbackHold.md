# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180024848`
- end: `0x180024925`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180024248`
- `0x180024848`

## callees

- `0x180024848`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002490f`
- `msvcrt!memcpy_s` at `0x18002490f`

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
0x180024848  push    rbx
0x18002484a  push    rbp
0x18002484b  push    rsi
0x18002484c  push    rdi
0x18002484d  sub     rsp, 28h
0x180024851  xor     al, al
0x180024853  mov     byte ptr [r8], 0
0x180024857  mov     rbp, r9
0x18002485a  mov     rdi, r8
0x18002485d  mov     rsi, rdx
0x180024860  mov     rbx, rcx
0x180024863  test    rdx, rdx
0x180024866  jz      loc_18002491C
0x18002486c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180024870  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180024875  mov     rdx, [rsi+20h]
0x180024879  test    rdx, rdx
0x18002487c  jz      loc_18002491C
0x180024882  cmp     dword ptr [rdx], 0
0x180024885  jnz     short loc_180024898
0x180024887  mov     eax, 1
0x18002488c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180024894  inc     eax
0x180024896  mov     [rdx], eax
0x180024898  cmp     dword ptr [rbx+50h], 0
0x18002489c  jnz     short loc_1800248AF
0x18002489e  movups  xmm0, xmmword ptr [rdx]
0x1800248a1  movups  xmmword ptr [rbx+50h], xmm0
0x1800248a5  movsd   xmm1, qword ptr [rdx+10h]
0x1800248aa  movsd   qword ptr [rbx+60h], xmm1
0x1800248af  movups  xmm0, xmmword ptr [rdx]
0x1800248b2  lea     r10, [rdi+rbp]
0x1800248b6  movups  xmmword ptr [rbx+68h], xmm0
0x1800248ba  movsd   xmm1, qword ptr [rdx+10h]
0x1800248bf  movsd   qword ptr [rbx+78h], xmm1
0x1800248c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800248c8  mov     rax, rbx
0x1800248cb  inc     rax
0x1800248ce  cmp     byte ptr [rdi+rax], 0
0x1800248d2  jnz     short loc_1800248CB
0x1800248d4  lea     rcx, [rax+rdi]
0x1800248d8  mov     rax, r10
0x1800248db  sub     rax, rcx
0x1800248de  cmp     rax, 2
0x1800248e2  jle     short loc_18002491A
0x1800248e4  mov     byte ptr [rcx], 5Ch ; '\'
0x1800248e7  lea     rdi, [rcx+1]
0x1800248eb  mov     r8, [rdx+8]; Source
0x1800248ef  inc     rbx
0x1800248f2  cmp     byte ptr [r8+rbx], 0
0x1800248f7  jnz     short loc_1800248EF
0x1800248f9  sub     r10, rdi
0x1800248fc  inc     rbx
0x1800248ff  cmp     rbx, r10
0x180024902  mov     rdx, r10; DestinationSize
0x180024905  mov     rcx, rdi; Destination
0x180024908  cmovnb  rbx, r10
0x18002490c  mov     r9, rbx; SourceSize
0x18002490f  call    cs:__imp_memcpy_s
0x180024915  mov     byte ptr [rbx+rdi-1], 0
0x18002491a  mov     al, 1
0x18002491c  add     rsp, 28h
0x180024920  pop     rdi
0x180024921  pop     rsi
0x180024922  pop     rbp
0x180024923  pop     rbx
0x180024924  retn
```
