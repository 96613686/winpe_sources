# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800089b8`
- end: `0x180008a95`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800086a0`
- `0x1800089b8`

## callees

- `0x1800089b8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008a7f`
- `msvcrt!memcpy_s` at `0x180008a7f`

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
0x1800089b8  push    rbx
0x1800089ba  push    rbp
0x1800089bb  push    rsi
0x1800089bc  push    rdi
0x1800089bd  sub     rsp, 28h
0x1800089c1  xor     al, al
0x1800089c3  mov     byte ptr [r8], 0
0x1800089c7  mov     rbp, r9
0x1800089ca  mov     rdi, r8
0x1800089cd  mov     rsi, rdx
0x1800089d0  mov     rbx, rcx
0x1800089d3  test    rdx, rdx
0x1800089d6  jz      loc_180008A8C
0x1800089dc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800089e0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800089e5  mov     rdx, [rsi+20h]
0x1800089e9  test    rdx, rdx
0x1800089ec  jz      loc_180008A8C
0x1800089f2  cmp     dword ptr [rdx], 0
0x1800089f5  jnz     short loc_180008A08
0x1800089f7  mov     eax, 1
0x1800089fc  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180008a04  inc     eax
0x180008a06  mov     [rdx], eax
0x180008a08  cmp     dword ptr [rbx+50h], 0
0x180008a0c  jnz     short loc_180008A1F
0x180008a0e  movups  xmm0, xmmword ptr [rdx]
0x180008a11  movups  xmmword ptr [rbx+50h], xmm0
0x180008a15  movsd   xmm1, qword ptr [rdx+10h]
0x180008a1a  movsd   qword ptr [rbx+60h], xmm1
0x180008a1f  movups  xmm0, xmmword ptr [rdx]
0x180008a22  lea     r10, [rdi+rbp]
0x180008a26  movups  xmmword ptr [rbx+68h], xmm0
0x180008a2a  movsd   xmm1, qword ptr [rdx+10h]
0x180008a2f  movsd   qword ptr [rbx+78h], xmm1
0x180008a34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008a38  mov     rax, rbx
0x180008a3b  inc     rax
0x180008a3e  cmp     byte ptr [rdi+rax], 0
0x180008a42  jnz     short loc_180008A3B
0x180008a44  lea     rcx, [rax+rdi]
0x180008a48  mov     rax, r10
0x180008a4b  sub     rax, rcx
0x180008a4e  cmp     rax, 2
0x180008a52  jle     short loc_180008A8A
0x180008a54  mov     byte ptr [rcx], 5Ch ; '\'
0x180008a57  lea     rdi, [rcx+1]
0x180008a5b  mov     r8, [rdx+8]; Source
0x180008a5f  inc     rbx
0x180008a62  cmp     byte ptr [r8+rbx], 0
0x180008a67  jnz     short loc_180008A5F
0x180008a69  sub     r10, rdi
0x180008a6c  inc     rbx
0x180008a6f  cmp     rbx, r10
0x180008a72  mov     rdx, r10; DestinationSize
0x180008a75  mov     rcx, rdi; Destination
0x180008a78  cmovnb  rbx, r10
0x180008a7c  mov     r9, rbx; SourceSize
0x180008a7f  call    cs:__imp_memcpy_s
0x180008a85  mov     byte ptr [rbx+rdi-1], 0
0x180008a8a  mov     al, 1
0x180008a8c  add     rsp, 28h
0x180008a90  pop     rdi
0x180008a91  pop     rsi
0x180008a92  pop     rbp
0x180008a93  pop     rbx
0x180008a94  retn
```
