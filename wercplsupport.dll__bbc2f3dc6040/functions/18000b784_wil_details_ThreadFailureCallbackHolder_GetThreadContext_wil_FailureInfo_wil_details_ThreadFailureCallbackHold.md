# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000b784`
- end: `0x18000b861`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b0a0`
- `0x18000b784`

## callees

- `0x18000b784`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b84b`
- `msvcrt!memcpy_s` at `0x18000b84b`

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
0x18000b784  push    rbx
0x18000b786  push    rbp
0x18000b787  push    rsi
0x18000b788  push    rdi
0x18000b789  sub     rsp, 28h
0x18000b78d  xor     al, al
0x18000b78f  mov     byte ptr [r8], 0
0x18000b793  mov     rbp, r9
0x18000b796  mov     rdi, r8
0x18000b799  mov     rsi, rdx
0x18000b79c  mov     rbx, rcx
0x18000b79f  test    rdx, rdx
0x18000b7a2  jz      loc_18000B858
0x18000b7a8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000b7ac  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000b7b1  mov     rdx, [rsi+20h]
0x18000b7b5  test    rdx, rdx
0x18000b7b8  jz      loc_18000B858
0x18000b7be  cmp     dword ptr [rdx], 0
0x18000b7c1  jnz     short loc_18000B7D4
0x18000b7c3  mov     eax, 1
0x18000b7c8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000b7d0  inc     eax
0x18000b7d2  mov     [rdx], eax
0x18000b7d4  cmp     dword ptr [rbx+50h], 0
0x18000b7d8  jnz     short loc_18000B7EB
0x18000b7da  movups  xmm0, xmmword ptr [rdx]
0x18000b7dd  movups  xmmword ptr [rbx+50h], xmm0
0x18000b7e1  movsd   xmm1, qword ptr [rdx+10h]
0x18000b7e6  movsd   qword ptr [rbx+60h], xmm1
0x18000b7eb  movups  xmm0, xmmword ptr [rdx]
0x18000b7ee  lea     r10, [rdi+rbp]
0x18000b7f2  movups  xmmword ptr [rbx+68h], xmm0
0x18000b7f6  movsd   xmm1, qword ptr [rdx+10h]
0x18000b7fb  movsd   qword ptr [rbx+78h], xmm1
0x18000b800  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000b804  mov     rax, rbx
0x18000b807  inc     rax
0x18000b80a  cmp     byte ptr [rdi+rax], 0
0x18000b80e  jnz     short loc_18000B807
0x18000b810  lea     rcx, [rax+rdi]
0x18000b814  mov     rax, r10
0x18000b817  sub     rax, rcx
0x18000b81a  cmp     rax, 2
0x18000b81e  jle     short loc_18000B856
0x18000b820  mov     byte ptr [rcx], 5Ch ; '\'
0x18000b823  lea     rdi, [rcx+1]
0x18000b827  mov     r8, [rdx+8]; Source
0x18000b82b  inc     rbx
0x18000b82e  cmp     byte ptr [r8+rbx], 0
0x18000b833  jnz     short loc_18000B82B
0x18000b835  sub     r10, rdi
0x18000b838  inc     rbx
0x18000b83b  cmp     rbx, r10
0x18000b83e  mov     rdx, r10; DestinationSize
0x18000b841  mov     rcx, rdi; Destination
0x18000b844  cmovnb  rbx, r10
0x18000b848  mov     r9, rbx; SourceSize
0x18000b84b  call    cs:__imp_memcpy_s
0x18000b851  mov     byte ptr [rbx+rdi-1], 0
0x18000b856  mov     al, 1
0x18000b858  add     rsp, 28h
0x18000b85c  pop     rdi
0x18000b85d  pop     rsi
0x18000b85e  pop     rbp
0x18000b85f  pop     rbx
0x18000b860  retn
```
