# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000c5ac`
- end: `0x18000c689`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b7f0`
- `0x18000c5ac`

## callees

- `0x18000c5ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c673`
- `msvcrt!memcpy_s` at `0x18000c673`

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
0x18000c5ac  push    rbx
0x18000c5ae  push    rbp
0x18000c5af  push    rsi
0x18000c5b0  push    rdi
0x18000c5b1  sub     rsp, 28h
0x18000c5b5  xor     al, al
0x18000c5b7  mov     byte ptr [r8], 0
0x18000c5bb  mov     rbp, r9
0x18000c5be  mov     rdi, r8
0x18000c5c1  mov     rsi, rdx
0x18000c5c4  mov     rbx, rcx
0x18000c5c7  test    rdx, rdx
0x18000c5ca  jz      loc_18000C680
0x18000c5d0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000c5d4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000c5d9  mov     rdx, [rsi+20h]
0x18000c5dd  test    rdx, rdx
0x18000c5e0  jz      loc_18000C680
0x18000c5e6  cmp     dword ptr [rdx], 0
0x18000c5e9  jnz     short loc_18000C5FC
0x18000c5eb  mov     eax, 1
0x18000c5f0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000c5f8  inc     eax
0x18000c5fa  mov     [rdx], eax
0x18000c5fc  cmp     dword ptr [rbx+50h], 0
0x18000c600  jnz     short loc_18000C613
0x18000c602  movups  xmm0, xmmword ptr [rdx]
0x18000c605  movups  xmmword ptr [rbx+50h], xmm0
0x18000c609  movsd   xmm1, qword ptr [rdx+10h]
0x18000c60e  movsd   qword ptr [rbx+60h], xmm1
0x18000c613  movups  xmm0, xmmword ptr [rdx]
0x18000c616  lea     r10, [rdi+rbp]
0x18000c61a  movups  xmmword ptr [rbx+68h], xmm0
0x18000c61e  movsd   xmm1, qword ptr [rdx+10h]
0x18000c623  movsd   qword ptr [rbx+78h], xmm1
0x18000c628  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c62c  mov     rax, rbx
0x18000c62f  inc     rax
0x18000c632  cmp     byte ptr [rdi+rax], 0
0x18000c636  jnz     short loc_18000C62F
0x18000c638  lea     rcx, [rax+rdi]
0x18000c63c  mov     rax, r10
0x18000c63f  sub     rax, rcx
0x18000c642  cmp     rax, 2
0x18000c646  jle     short loc_18000C67E
0x18000c648  mov     byte ptr [rcx], 5Ch ; '\'
0x18000c64b  lea     rdi, [rcx+1]
0x18000c64f  mov     r8, [rdx+8]; Source
0x18000c653  inc     rbx
0x18000c656  cmp     byte ptr [r8+rbx], 0
0x18000c65b  jnz     short loc_18000C653
0x18000c65d  sub     r10, rdi
0x18000c660  inc     rbx
0x18000c663  cmp     rbx, r10
0x18000c666  mov     rdx, r10; DestinationSize
0x18000c669  mov     rcx, rdi; Destination
0x18000c66c  cmovnb  rbx, r10
0x18000c670  mov     r9, rbx; SourceSize
0x18000c673  call    cs:__imp_memcpy_s
0x18000c679  mov     byte ptr [rbx+rdi-1], 0
0x18000c67e  mov     al, 1
0x18000c680  add     rsp, 28h
0x18000c684  pop     rdi
0x18000c685  pop     rsi
0x18000c686  pop     rbp
0x18000c687  pop     rbx
0x18000c688  retn
```
