# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004974`
- end: `0x140004a51`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004190`
- `0x140004974`

## callees

- `0x140004974`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140004a3b`
- `msvcrt!memcpy_s` at `0x140004a3b`

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
0x140004974  push    rbx
0x140004976  push    rbp
0x140004977  push    rsi
0x140004978  push    rdi
0x140004979  sub     rsp, 28h
0x14000497d  xor     al, al
0x14000497f  mov     byte ptr [r8], 0
0x140004983  mov     rbp, r9
0x140004986  mov     rdi, r8
0x140004989  mov     rsi, rdx
0x14000498c  mov     rbx, rcx
0x14000498f  test    rdx, rdx
0x140004992  jz      loc_140004A48
0x140004998  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000499c  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400049a1  mov     rdx, [rsi+20h]
0x1400049a5  test    rdx, rdx
0x1400049a8  jz      loc_140004A48
0x1400049ae  cmp     dword ptr [rdx], 0
0x1400049b1  jnz     short loc_1400049C4
0x1400049b3  mov     eax, 1
0x1400049b8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400049c0  inc     eax
0x1400049c2  mov     [rdx], eax
0x1400049c4  cmp     dword ptr [rbx+50h], 0
0x1400049c8  jnz     short loc_1400049DB
0x1400049ca  movups  xmm0, xmmword ptr [rdx]
0x1400049cd  movups  xmmword ptr [rbx+50h], xmm0
0x1400049d1  movsd   xmm1, qword ptr [rdx+10h]
0x1400049d6  movsd   qword ptr [rbx+60h], xmm1
0x1400049db  movups  xmm0, xmmword ptr [rdx]
0x1400049de  lea     r10, [rdi+rbp]
0x1400049e2  movups  xmmword ptr [rbx+68h], xmm0
0x1400049e6  movsd   xmm1, qword ptr [rdx+10h]
0x1400049eb  movsd   qword ptr [rbx+78h], xmm1
0x1400049f0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400049f4  mov     rax, rbx
0x1400049f7  inc     rax
0x1400049fa  cmp     byte ptr [rdi+rax], 0
0x1400049fe  jnz     short loc_1400049F7
0x140004a00  lea     rcx, [rax+rdi]
0x140004a04  mov     rax, r10
0x140004a07  sub     rax, rcx
0x140004a0a  cmp     rax, 2
0x140004a0e  jle     short loc_140004A46
0x140004a10  mov     byte ptr [rcx], 5Ch ; '\'
0x140004a13  lea     rdi, [rcx+1]
0x140004a17  mov     r8, [rdx+8]; Source
0x140004a1b  inc     rbx
0x140004a1e  cmp     byte ptr [r8+rbx], 0
0x140004a23  jnz     short loc_140004A1B
0x140004a25  sub     r10, rdi
0x140004a28  inc     rbx
0x140004a2b  cmp     rbx, r10
0x140004a2e  mov     rdx, r10; DestinationSize
0x140004a31  mov     rcx, rdi; Destination
0x140004a34  cmovnb  rbx, r10
0x140004a38  mov     r9, rbx; SourceSize
0x140004a3b  call    cs:__imp_memcpy_s
0x140004a41  mov     byte ptr [rbx+rdi-1], 0
0x140004a46  mov     al, 1
0x140004a48  add     rsp, 28h
0x140004a4c  pop     rdi
0x140004a4d  pop     rsi
0x140004a4e  pop     rbp
0x140004a4f  pop     rbx
0x140004a50  retn
```
