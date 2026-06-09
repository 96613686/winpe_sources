# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000bf80`
- end: `0x18000c079`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `249`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b610`
- `0x18000bf80`

## callees

- `0x18000bf80`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c050`
- `msvcrt!memcpy_s` at `0x18000c050`

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
  char *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rdi
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
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v10 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v14, v16, v15, v17);
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
0x18000bf80  mov     [rsp+arg_0], rbx
0x18000bf85  mov     [rsp+arg_8], rbp
0x18000bf8a  mov     [rsp+arg_10], rsi
0x18000bf8f  push    rdi
0x18000bf90  sub     rsp, 20h
0x18000bf94  xor     al, al
0x18000bf96  mov     byte ptr [r8], 0
0x18000bf9a  mov     rbp, r9
0x18000bf9d  mov     rdi, r8
0x18000bfa0  mov     rsi, rdx
0x18000bfa3  mov     rbx, rcx
0x18000bfa6  test    rdx, rdx
0x18000bfa9  jz      loc_18000C063
0x18000bfaf  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000bfb3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000bfb8  mov     rdx, [rsi+20h]
0x18000bfbc  test    rdx, rdx
0x18000bfbf  jz      loc_18000C063
0x18000bfc5  cmp     dword ptr [rdx], 0
0x18000bfc8  jnz     short loc_18000BFDB
0x18000bfca  mov     eax, 1
0x18000bfcf  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000bfd7  inc     eax
0x18000bfd9  mov     [rdx], eax
0x18000bfdb  cmp     dword ptr [rbx+50h], 0
0x18000bfdf  jnz     short loc_18000BFF2
0x18000bfe1  movups  xmm0, xmmword ptr [rdx]
0x18000bfe4  movups  xmmword ptr [rbx+50h], xmm0
0x18000bfe8  movsd   xmm1, qword ptr [rdx+10h]
0x18000bfed  movsd   qword ptr [rbx+60h], xmm1
0x18000bff2  movups  xmm0, xmmword ptr [rdx]
0x18000bff5  lea     rcx, [rdi+rbp]
0x18000bff9  movups  xmmword ptr [rbx+68h], xmm0
0x18000bffd  movsd   xmm1, qword ptr [rdx+10h]
0x18000c002  movsd   qword ptr [rbx+78h], xmm1
0x18000c007  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c00b  mov     rax, rbx
0x18000c00e  inc     rax
0x18000c011  cmp     byte ptr [rdi+rax], 0
0x18000c015  jnz     short loc_18000C00E
0x18000c017  add     rdi, rax
0x18000c01a  mov     rax, rcx
0x18000c01d  sub     rax, rdi
0x18000c020  cmp     rax, 2
0x18000c024  jle     short loc_18000C061
0x18000c026  mov     byte ptr [rdi], 5Ch ; '\'
0x18000c029  inc     rdi
0x18000c02c  mov     r8, [rdx+8]; Source
0x18000c030  inc     rbx
0x18000c033  cmp     byte ptr [r8+rbx], 0
0x18000c038  jnz     short loc_18000C030
0x18000c03a  sub     rcx, rdi
0x18000c03d  inc     rbx
0x18000c040  cmp     rbx, rcx
0x18000c043  mov     rdx, rcx; DestinationSize
0x18000c046  cmovnb  rbx, rcx
0x18000c04a  mov     rcx, rdi; Destination
0x18000c04d  mov     r9, rbx; SourceSize
0x18000c050  call    cs:__imp_memcpy_s
0x18000c057  nop     dword ptr [rax+rax+00h]
0x18000c05c  mov     byte ptr [rbx+rdi-1], 0
0x18000c061  mov     al, 1
0x18000c063  mov     rbx, [rsp+28h+arg_0]
0x18000c068  mov     rbp, [rsp+28h+arg_8]
0x18000c06d  mov     rsi, [rsp+28h+arg_10]
0x18000c072  add     rsp, 20h
0x18000c076  pop     rdi
0x18000c077  retn
```
