# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000cff4`
- end: `0x18000d0d1`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c99c`
- `0x18000cff4`

## callees

- `0x18000cff4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d0bb`
- `msvcrt!memcpy_s` at `0x18000d0bb`

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
0x18000cff4  push    rbx
0x18000cff6  push    rbp
0x18000cff7  push    rsi
0x18000cff8  push    rdi
0x18000cff9  sub     rsp, 28h
0x18000cffd  xor     al, al
0x18000cfff  mov     byte ptr [r8], 0
0x18000d003  mov     rbp, r9
0x18000d006  mov     rdi, r8
0x18000d009  mov     rsi, rdx
0x18000d00c  mov     rbx, rcx
0x18000d00f  test    rdx, rdx
0x18000d012  jz      loc_18000D0C8
0x18000d018  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000d01c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000d021  mov     rdx, [rsi+20h]
0x18000d025  test    rdx, rdx
0x18000d028  jz      loc_18000D0C8
0x18000d02e  cmp     dword ptr [rdx], 0
0x18000d031  jnz     short loc_18000D044
0x18000d033  mov     eax, 1
0x18000d038  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000d040  inc     eax
0x18000d042  mov     [rdx], eax
0x18000d044  cmp     dword ptr [rbx+50h], 0
0x18000d048  jnz     short loc_18000D05B
0x18000d04a  movups  xmm0, xmmword ptr [rdx]
0x18000d04d  movups  xmmword ptr [rbx+50h], xmm0
0x18000d051  movsd   xmm1, qword ptr [rdx+10h]
0x18000d056  movsd   qword ptr [rbx+60h], xmm1
0x18000d05b  movups  xmm0, xmmword ptr [rdx]
0x18000d05e  lea     r10, [rdi+rbp]
0x18000d062  movups  xmmword ptr [rbx+68h], xmm0
0x18000d066  movsd   xmm1, qword ptr [rdx+10h]
0x18000d06b  movsd   qword ptr [rbx+78h], xmm1
0x18000d070  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d074  mov     rax, rbx
0x18000d077  inc     rax
0x18000d07a  cmp     byte ptr [rdi+rax], 0
0x18000d07e  jnz     short loc_18000D077
0x18000d080  lea     rcx, [rax+rdi]
0x18000d084  mov     rax, r10
0x18000d087  sub     rax, rcx
0x18000d08a  cmp     rax, 2
0x18000d08e  jle     short loc_18000D0C6
0x18000d090  mov     byte ptr [rcx], 5Ch ; '\'
0x18000d093  lea     rdi, [rcx+1]
0x18000d097  mov     r8, [rdx+8]; Source
0x18000d09b  inc     rbx
0x18000d09e  cmp     byte ptr [r8+rbx], 0
0x18000d0a3  jnz     short loc_18000D09B
0x18000d0a5  sub     r10, rdi
0x18000d0a8  inc     rbx
0x18000d0ab  cmp     rbx, r10
0x18000d0ae  mov     rdx, r10; DestinationSize
0x18000d0b1  mov     rcx, rdi; Destination
0x18000d0b4  cmovnb  rbx, r10
0x18000d0b8  mov     r9, rbx; SourceSize
0x18000d0bb  call    cs:__imp_memcpy_s
0x18000d0c1  mov     byte ptr [rbx+rdi-1], 0
0x18000d0c6  mov     al, 1
0x18000d0c8  add     rsp, 28h
0x18000d0cc  pop     rdi
0x18000d0cd  pop     rsi
0x18000d0ce  pop     rbp
0x18000d0cf  pop     rbx
0x18000d0d0  retn
```
