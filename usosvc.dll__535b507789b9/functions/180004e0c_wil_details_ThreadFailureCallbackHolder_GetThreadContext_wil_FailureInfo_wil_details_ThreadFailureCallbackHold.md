# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004e0c`
- end: `0x180004ee8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004710`
- `0x180004e0c`

## callees

- `0x180004e0c`
- `0x180006a98`

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
0x180004e0c  push    rbx
0x180004e0e  push    rbp
0x180004e0f  push    rsi
0x180004e10  push    rdi
0x180004e11  sub     rsp, 28h
0x180004e15  xor     al, al
0x180004e17  mov     byte ptr [r8], 0
0x180004e1b  mov     rbp, r9
0x180004e1e  mov     rdi, r8
0x180004e21  mov     rsi, rdx
0x180004e24  mov     rbx, rcx
0x180004e27  test    rdx, rdx
0x180004e2a  jz      loc_180004EDF
0x180004e30  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004e34  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004e39  mov     rdx, [rsi+20h]
0x180004e3d  test    rdx, rdx
0x180004e40  jz      loc_180004EDF
0x180004e46  cmp     dword ptr [rdx], 0
0x180004e49  jnz     short loc_180004E5C
0x180004e4b  mov     eax, 1
0x180004e50  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004e58  inc     eax
0x180004e5a  mov     [rdx], eax
0x180004e5c  cmp     dword ptr [rbx+50h], 0
0x180004e60  jnz     short loc_180004E73
0x180004e62  movups  xmm0, xmmword ptr [rdx]
0x180004e65  movups  xmmword ptr [rbx+50h], xmm0
0x180004e69  movsd   xmm1, qword ptr [rdx+10h]
0x180004e6e  movsd   qword ptr [rbx+60h], xmm1
0x180004e73  movups  xmm0, xmmword ptr [rdx]
0x180004e76  lea     r10, [rdi+rbp]
0x180004e7a  movups  xmmword ptr [rbx+68h], xmm0
0x180004e7e  movsd   xmm1, qword ptr [rdx+10h]
0x180004e83  movsd   qword ptr [rbx+78h], xmm1
0x180004e88  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004e8c  mov     rax, rbx
0x180004e8f  inc     rax
0x180004e92  cmp     byte ptr [rdi+rax], 0
0x180004e96  jnz     short loc_180004E8F
0x180004e98  lea     rcx, [rax+rdi]
0x180004e9c  mov     rax, r10
0x180004e9f  sub     rax, rcx
0x180004ea2  cmp     rax, 2
0x180004ea6  jle     short loc_180004EDD
0x180004ea8  mov     byte ptr [rcx], 5Ch ; '\'
0x180004eab  lea     rdi, [rcx+1]
0x180004eaf  mov     r8, [rdx+8]; Source
0x180004eb3  inc     rbx
0x180004eb6  cmp     byte ptr [r8+rbx], 0
0x180004ebb  jnz     short loc_180004EB3
0x180004ebd  sub     r10, rdi
0x180004ec0  inc     rbx
0x180004ec3  cmp     rbx, r10
0x180004ec6  mov     rdx, r10; DestinationSize
0x180004ec9  mov     rcx, rdi; Destination
0x180004ecc  cmovnb  rbx, r10
0x180004ed0  mov     r9, rbx; SourceSize
0x180004ed3  call    memcpy_s
0x180004ed8  mov     byte ptr [rbx+rdi-1], 0
0x180004edd  mov     al, 1
0x180004edf  add     rsp, 28h
0x180004ee3  pop     rdi
0x180004ee4  pop     rsi
0x180004ee5  pop     rbp
0x180004ee6  pop     rbx
0x180004ee7  retn
```
