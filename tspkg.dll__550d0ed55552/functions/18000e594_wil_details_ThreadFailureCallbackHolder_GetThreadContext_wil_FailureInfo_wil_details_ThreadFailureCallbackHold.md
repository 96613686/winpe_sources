# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000e594`
- end: `0x18000e670`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000df44`
- `0x18000e594`

## callees

- `0x18000e594`
- `0x180010e4c`

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
0x18000e594  push    rbx
0x18000e596  push    rbp
0x18000e597  push    rsi
0x18000e598  push    rdi
0x18000e599  sub     rsp, 28h
0x18000e59d  xor     al, al
0x18000e59f  mov     byte ptr [r8], 0
0x18000e5a3  mov     rbp, r9
0x18000e5a6  mov     rdi, r8
0x18000e5a9  mov     rsi, rdx
0x18000e5ac  mov     rbx, rcx
0x18000e5af  test    rdx, rdx
0x18000e5b2  jz      loc_18000E667
0x18000e5b8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000e5bc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000e5c1  mov     rdx, [rsi+20h]
0x18000e5c5  test    rdx, rdx
0x18000e5c8  jz      loc_18000E667
0x18000e5ce  cmp     dword ptr [rdx], 0
0x18000e5d1  jnz     short loc_18000E5E4
0x18000e5d3  mov     eax, 1
0x18000e5d8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000e5e0  inc     eax
0x18000e5e2  mov     [rdx], eax
0x18000e5e4  cmp     dword ptr [rbx+50h], 0
0x18000e5e8  jnz     short loc_18000E5FB
0x18000e5ea  movups  xmm0, xmmword ptr [rdx]
0x18000e5ed  movups  xmmword ptr [rbx+50h], xmm0
0x18000e5f1  movsd   xmm1, qword ptr [rdx+10h]
0x18000e5f6  movsd   qword ptr [rbx+60h], xmm1
0x18000e5fb  movups  xmm0, xmmword ptr [rdx]
0x18000e5fe  lea     r10, [rdi+rbp]
0x18000e602  movups  xmmword ptr [rbx+68h], xmm0
0x18000e606  movsd   xmm1, qword ptr [rdx+10h]
0x18000e60b  movsd   qword ptr [rbx+78h], xmm1
0x18000e610  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e614  mov     rax, rbx
0x18000e617  inc     rax
0x18000e61a  cmp     byte ptr [rdi+rax], 0
0x18000e61e  jnz     short loc_18000E617
0x18000e620  lea     rcx, [rax+rdi]
0x18000e624  mov     rax, r10
0x18000e627  sub     rax, rcx
0x18000e62a  cmp     rax, 2
0x18000e62e  jle     short loc_18000E665
0x18000e630  mov     byte ptr [rcx], 5Ch ; '\'
0x18000e633  lea     rdi, [rcx+1]
0x18000e637  mov     r8, [rdx+8]; Source
0x18000e63b  inc     rbx
0x18000e63e  cmp     byte ptr [r8+rbx], 0
0x18000e643  jnz     short loc_18000E63B
0x18000e645  sub     r10, rdi
0x18000e648  inc     rbx
0x18000e64b  cmp     rbx, r10
0x18000e64e  mov     rdx, r10; DestinationSize
0x18000e651  mov     rcx, rdi; Destination
0x18000e654  cmovnb  rbx, r10
0x18000e658  mov     r9, rbx; SourceSize
0x18000e65b  call    memcpy_s
0x18000e660  mov     byte ptr [rbx+rdi-1], 0
0x18000e665  mov     al, 1
0x18000e667  add     rsp, 28h
0x18000e66b  pop     rdi
0x18000e66c  pop     rsi
0x18000e66d  pop     rbp
0x18000e66e  pop     rbx
0x18000e66f  retn
```
