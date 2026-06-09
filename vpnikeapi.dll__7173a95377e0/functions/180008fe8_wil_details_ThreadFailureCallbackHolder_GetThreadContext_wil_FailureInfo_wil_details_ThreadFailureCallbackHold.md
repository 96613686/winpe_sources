# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180008fe8`
- end: `0x1800090c5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008884`
- `0x180008fe8`

## callees

- `0x180008fe8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800090af`
- `msvcrt!memcpy_s` at `0x1800090af`

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
0x180008fe8  push    rbx
0x180008fea  push    rbp
0x180008feb  push    rsi
0x180008fec  push    rdi
0x180008fed  sub     rsp, 28h
0x180008ff1  xor     al, al
0x180008ff3  mov     byte ptr [r8], 0
0x180008ff7  mov     rbp, r9
0x180008ffa  mov     rdi, r8
0x180008ffd  mov     rsi, rdx
0x180009000  mov     rbx, rcx
0x180009003  test    rdx, rdx
0x180009006  jz      loc_1800090BC
0x18000900c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180009010  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009015  mov     rdx, [rsi+20h]
0x180009019  test    rdx, rdx
0x18000901c  jz      loc_1800090BC
0x180009022  cmp     dword ptr [rdx], 0
0x180009025  jnz     short loc_180009038
0x180009027  mov     eax, 1
0x18000902c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180009034  inc     eax
0x180009036  mov     [rdx], eax
0x180009038  cmp     dword ptr [rbx+50h], 0
0x18000903c  jnz     short loc_18000904F
0x18000903e  movups  xmm0, xmmword ptr [rdx]
0x180009041  movups  xmmword ptr [rbx+50h], xmm0
0x180009045  movsd   xmm1, qword ptr [rdx+10h]
0x18000904a  movsd   qword ptr [rbx+60h], xmm1
0x18000904f  movups  xmm0, xmmword ptr [rdx]
0x180009052  lea     r10, [rdi+rbp]
0x180009056  movups  xmmword ptr [rbx+68h], xmm0
0x18000905a  movsd   xmm1, qword ptr [rdx+10h]
0x18000905f  movsd   qword ptr [rbx+78h], xmm1
0x180009064  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009068  mov     rax, rbx
0x18000906b  inc     rax
0x18000906e  cmp     byte ptr [rdi+rax], 0
0x180009072  jnz     short loc_18000906B
0x180009074  lea     rcx, [rax+rdi]
0x180009078  mov     rax, r10
0x18000907b  sub     rax, rcx
0x18000907e  cmp     rax, 2
0x180009082  jle     short loc_1800090BA
0x180009084  mov     byte ptr [rcx], 5Ch ; '\'
0x180009087  lea     rdi, [rcx+1]
0x18000908b  mov     r8, [rdx+8]; Source
0x18000908f  inc     rbx
0x180009092  cmp     byte ptr [r8+rbx], 0
0x180009097  jnz     short loc_18000908F
0x180009099  sub     r10, rdi
0x18000909c  inc     rbx
0x18000909f  cmp     rbx, r10
0x1800090a2  mov     rdx, r10; DestinationSize
0x1800090a5  mov     rcx, rdi; Destination
0x1800090a8  cmovnb  rbx, r10
0x1800090ac  mov     r9, rbx; SourceSize
0x1800090af  call    cs:__imp_memcpy_s
0x1800090b5  mov     byte ptr [rbx+rdi-1], 0
0x1800090ba  mov     al, 1
0x1800090bc  add     rsp, 28h
0x1800090c0  pop     rdi
0x1800090c1  pop     rsi
0x1800090c2  pop     rbp
0x1800090c3  pop     rbx
0x1800090c4  retn
```
