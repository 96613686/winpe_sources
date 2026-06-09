# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140003558`
- end: `0x140003635`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e60`
- `0x140003558`

## callees

- `0x140003558`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000361f`
- `msvcrt!memcpy_s` at `0x14000361f`

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
0x140003558  push    rbx
0x14000355a  push    rbp
0x14000355b  push    rsi
0x14000355c  push    rdi
0x14000355d  sub     rsp, 28h
0x140003561  xor     al, al
0x140003563  mov     byte ptr [r8], 0
0x140003567  mov     rbp, r9
0x14000356a  mov     rdi, r8
0x14000356d  mov     rsi, rdx
0x140003570  mov     rbx, rcx
0x140003573  test    rdx, rdx
0x140003576  jz      loc_14000362C
0x14000357c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140003580  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140003585  mov     rdx, [rsi+20h]
0x140003589  test    rdx, rdx
0x14000358c  jz      loc_14000362C
0x140003592  cmp     dword ptr [rdx], 0
0x140003595  jnz     short loc_1400035A8
0x140003597  mov     eax, 1
0x14000359c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1400035a4  inc     eax
0x1400035a6  mov     [rdx], eax
0x1400035a8  cmp     dword ptr [rbx+50h], 0
0x1400035ac  jnz     short loc_1400035BF
0x1400035ae  movups  xmm0, xmmword ptr [rdx]
0x1400035b1  movups  xmmword ptr [rbx+50h], xmm0
0x1400035b5  movsd   xmm1, qword ptr [rdx+10h]
0x1400035ba  movsd   qword ptr [rbx+60h], xmm1
0x1400035bf  movups  xmm0, xmmword ptr [rdx]
0x1400035c2  lea     r10, [rdi+rbp]
0x1400035c6  movups  xmmword ptr [rbx+68h], xmm0
0x1400035ca  movsd   xmm1, qword ptr [rdx+10h]
0x1400035cf  movsd   qword ptr [rbx+78h], xmm1
0x1400035d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400035d8  mov     rax, rbx
0x1400035db  inc     rax
0x1400035de  cmp     byte ptr [rdi+rax], 0
0x1400035e2  jnz     short loc_1400035DB
0x1400035e4  lea     rcx, [rax+rdi]
0x1400035e8  mov     rax, r10
0x1400035eb  sub     rax, rcx
0x1400035ee  cmp     rax, 2
0x1400035f2  jle     short loc_14000362A
0x1400035f4  mov     byte ptr [rcx], 5Ch ; '\'
0x1400035f7  lea     rdi, [rcx+1]
0x1400035fb  mov     r8, [rdx+8]; Source
0x1400035ff  inc     rbx
0x140003602  cmp     byte ptr [r8+rbx], 0
0x140003607  jnz     short loc_1400035FF
0x140003609  sub     r10, rdi
0x14000360c  inc     rbx
0x14000360f  cmp     rbx, r10
0x140003612  mov     rdx, r10; DestinationSize
0x140003615  mov     rcx, rdi; Destination
0x140003618  cmovnb  rbx, r10
0x14000361c  mov     r9, rbx; SourceSize
0x14000361f  call    cs:__imp_memcpy_s
0x140003625  mov     byte ptr [rbx+rdi-1], 0
0x14000362a  mov     al, 1
0x14000362c  add     rsp, 28h
0x140003630  pop     rdi
0x140003631  pop     rsi
0x140003632  pop     rbp
0x140003633  pop     rbx
0x140003634  retn
```
