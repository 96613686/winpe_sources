# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180019c2c`
- end: `0x180019d10`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019484`
- `0x180019c2c`

## callees

- `0x180019c2c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180019cf3`
- `msvcrt!memcpy_s` at `0x180019cf3`

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
0x180019c2c  push    rbx
0x180019c2e  push    rbp
0x180019c2f  push    rsi
0x180019c30  push    rdi
0x180019c31  sub     rsp, 28h
0x180019c35  xor     al, al
0x180019c37  mov     byte ptr [r8], 0
0x180019c3b  mov     rbp, r9
0x180019c3e  mov     rdi, r8
0x180019c41  mov     rsi, rdx
0x180019c44  mov     rbx, rcx
0x180019c47  test    rdx, rdx
0x180019c4a  jz      loc_180019D06
0x180019c50  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180019c54  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180019c59  mov     rdx, [rsi+20h]
0x180019c5d  test    rdx, rdx
0x180019c60  jz      loc_180019D06
0x180019c66  cmp     dword ptr [rdx], 0
0x180019c69  jnz     short loc_180019C7C
0x180019c6b  mov     eax, 1
0x180019c70  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180019c78  inc     eax
0x180019c7a  mov     [rdx], eax
0x180019c7c  cmp     dword ptr [rbx+50h], 0
0x180019c80  jnz     short loc_180019C93
0x180019c82  movups  xmm0, xmmword ptr [rdx]
0x180019c85  movups  xmmword ptr [rbx+50h], xmm0
0x180019c89  movsd   xmm1, qword ptr [rdx+10h]
0x180019c8e  movsd   qword ptr [rbx+60h], xmm1
0x180019c93  movups  xmm0, xmmword ptr [rdx]
0x180019c96  lea     r10, [rdi+rbp]
0x180019c9a  movups  xmmword ptr [rbx+68h], xmm0
0x180019c9e  movsd   xmm1, qword ptr [rdx+10h]
0x180019ca3  movsd   qword ptr [rbx+78h], xmm1
0x180019ca8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019cac  mov     rax, rbx
0x180019caf  inc     rax
0x180019cb2  cmp     byte ptr [rdi+rax], 0
0x180019cb6  jnz     short loc_180019CAF
0x180019cb8  lea     rcx, [rax+rdi]
0x180019cbc  mov     rax, r10
0x180019cbf  sub     rax, rcx
0x180019cc2  cmp     rax, 2
0x180019cc6  jle     short loc_180019D04
0x180019cc8  mov     byte ptr [rcx], 5Ch ; '\'
0x180019ccb  lea     rdi, [rcx+1]
0x180019ccf  mov     r8, [rdx+8]; Source
0x180019cd3  inc     rbx
0x180019cd6  cmp     byte ptr [r8+rbx], 0
0x180019cdb  jnz     short loc_180019CD3
0x180019cdd  sub     r10, rdi
0x180019ce0  inc     rbx
0x180019ce3  cmp     rbx, r10
0x180019ce6  mov     rdx, r10; DestinationSize
0x180019ce9  mov     rcx, rdi; Destination
0x180019cec  cmovnb  rbx, r10
0x180019cf0  mov     r9, rbx; SourceSize
0x180019cf3  call    cs:__imp_memcpy_s
0x180019cfa  nop     dword ptr [rax+rax+00h]
0x180019cff  mov     byte ptr [rbx+rdi-1], 0
0x180019d04  mov     al, 1
0x180019d06  add     rsp, 28h
0x180019d0a  pop     rdi
0x180019d0b  pop     rsi
0x180019d0c  pop     rbp
0x180019d0d  pop     rbx
0x180019d0e  retn
```
