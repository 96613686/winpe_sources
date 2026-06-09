# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180007c60`
- end: `0x180007d44`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800054e0`
- `0x180007c60`

## callees

- `0x180007c60`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007d27`
- `msvcrt!memcpy_s` at `0x180007d27`

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
0x180007c60  push    rbx
0x180007c62  push    rbp
0x180007c63  push    rsi
0x180007c64  push    rdi
0x180007c65  sub     rsp, 28h
0x180007c69  xor     al, al
0x180007c6b  mov     byte ptr [r8], 0
0x180007c6f  mov     rbp, r9
0x180007c72  mov     rdi, r8
0x180007c75  mov     rsi, rdx
0x180007c78  mov     rbx, rcx
0x180007c7b  test    rdx, rdx
0x180007c7e  jz      loc_180007D3A
0x180007c84  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180007c88  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007c8d  mov     rdx, [rsi+20h]
0x180007c91  test    rdx, rdx
0x180007c94  jz      loc_180007D3A
0x180007c9a  cmp     dword ptr [rdx], 0
0x180007c9d  jnz     short loc_180007CB0
0x180007c9f  mov     eax, 1
0x180007ca4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180007cac  inc     eax
0x180007cae  mov     [rdx], eax
0x180007cb0  cmp     dword ptr [rbx+50h], 0
0x180007cb4  jnz     short loc_180007CC7
0x180007cb6  movups  xmm0, xmmword ptr [rdx]
0x180007cb9  movups  xmmword ptr [rbx+50h], xmm0
0x180007cbd  movsd   xmm1, qword ptr [rdx+10h]
0x180007cc2  movsd   qword ptr [rbx+60h], xmm1
0x180007cc7  movups  xmm0, xmmword ptr [rdx]
0x180007cca  lea     r10, [rdi+rbp]
0x180007cce  movups  xmmword ptr [rbx+68h], xmm0
0x180007cd2  movsd   xmm1, qword ptr [rdx+10h]
0x180007cd7  movsd   qword ptr [rbx+78h], xmm1
0x180007cdc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007ce0  mov     rax, rbx
0x180007ce3  inc     rax
0x180007ce6  cmp     byte ptr [rdi+rax], 0
0x180007cea  jnz     short loc_180007CE3
0x180007cec  lea     rcx, [rax+rdi]
0x180007cf0  mov     rax, r10
0x180007cf3  sub     rax, rcx
0x180007cf6  cmp     rax, 2
0x180007cfa  jle     short loc_180007D38
0x180007cfc  mov     byte ptr [rcx], 5Ch ; '\'
0x180007cff  lea     rdi, [rcx+1]
0x180007d03  mov     r8, [rdx+8]; Source
0x180007d07  inc     rbx
0x180007d0a  cmp     byte ptr [r8+rbx], 0
0x180007d0f  jnz     short loc_180007D07
0x180007d11  sub     r10, rdi
0x180007d14  inc     rbx
0x180007d17  cmp     rbx, r10
0x180007d1a  mov     rdx, r10; DestinationSize
0x180007d1d  mov     rcx, rdi; Destination
0x180007d20  cmovnb  rbx, r10
0x180007d24  mov     r9, rbx; SourceSize
0x180007d27  call    cs:__imp_memcpy_s
0x180007d2e  nop     dword ptr [rax+rax+00h]
0x180007d33  mov     byte ptr [rbx+rdi-1], 0
0x180007d38  mov     al, 1
0x180007d3a  add     rsp, 28h
0x180007d3e  pop     rdi
0x180007d3f  pop     rsi
0x180007d40  pop     rbp
0x180007d41  pop     rbx
0x180007d42  retn
```
