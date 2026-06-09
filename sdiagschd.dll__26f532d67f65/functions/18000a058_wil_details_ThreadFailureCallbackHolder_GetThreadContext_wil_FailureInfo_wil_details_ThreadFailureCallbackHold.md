# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000a058`
- end: `0x18000a151`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `249`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800099c0`
- `0x18000a058`

## callees

- `0x18000a058`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a128`
- `msvcrt!memcpy_s` at `0x18000a128`

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
0x18000a058  mov     [rsp+arg_0], rbx
0x18000a05d  mov     [rsp+arg_8], rbp
0x18000a062  mov     [rsp+arg_10], rsi
0x18000a067  push    rdi
0x18000a068  sub     rsp, 20h
0x18000a06c  xor     al, al
0x18000a06e  mov     byte ptr [r8], 0
0x18000a072  mov     rbp, r9
0x18000a075  mov     rdi, r8
0x18000a078  mov     rsi, rdx
0x18000a07b  mov     rbx, rcx
0x18000a07e  test    rdx, rdx
0x18000a081  jz      loc_18000A13B
0x18000a087  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000a08b  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000a090  mov     rdx, [rsi+20h]
0x18000a094  test    rdx, rdx
0x18000a097  jz      loc_18000A13B
0x18000a09d  cmp     dword ptr [rdx], 0
0x18000a0a0  jnz     short loc_18000A0B3
0x18000a0a2  mov     eax, 1
0x18000a0a7  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000a0af  inc     eax
0x18000a0b1  mov     [rdx], eax
0x18000a0b3  cmp     dword ptr [rbx+50h], 0
0x18000a0b7  jnz     short loc_18000A0CA
0x18000a0b9  movups  xmm0, xmmword ptr [rdx]
0x18000a0bc  movups  xmmword ptr [rbx+50h], xmm0
0x18000a0c0  movsd   xmm1, qword ptr [rdx+10h]
0x18000a0c5  movsd   qword ptr [rbx+60h], xmm1
0x18000a0ca  movups  xmm0, xmmword ptr [rdx]
0x18000a0cd  lea     rcx, [rdi+rbp]
0x18000a0d1  movups  xmmword ptr [rbx+68h], xmm0
0x18000a0d5  movsd   xmm1, qword ptr [rdx+10h]
0x18000a0da  movsd   qword ptr [rbx+78h], xmm1
0x18000a0df  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a0e3  mov     rax, rbx
0x18000a0e6  inc     rax
0x18000a0e9  cmp     byte ptr [rdi+rax], 0
0x18000a0ed  jnz     short loc_18000A0E6
0x18000a0ef  add     rdi, rax
0x18000a0f2  mov     rax, rcx
0x18000a0f5  sub     rax, rdi
0x18000a0f8  cmp     rax, 2
0x18000a0fc  jle     short loc_18000A139
0x18000a0fe  mov     byte ptr [rdi], 5Ch ; '\'
0x18000a101  inc     rdi
0x18000a104  mov     r8, [rdx+8]; Source
0x18000a108  inc     rbx
0x18000a10b  cmp     byte ptr [r8+rbx], 0
0x18000a110  jnz     short loc_18000A108
0x18000a112  sub     rcx, rdi
0x18000a115  inc     rbx
0x18000a118  cmp     rbx, rcx
0x18000a11b  mov     rdx, rcx; DestinationSize
0x18000a11e  cmovnb  rbx, rcx
0x18000a122  mov     rcx, rdi; Destination
0x18000a125  mov     r9, rbx; SourceSize
0x18000a128  call    cs:__imp_memcpy_s
0x18000a12f  nop     dword ptr [rax+rax+00h]
0x18000a134  mov     byte ptr [rbx+rdi-1], 0
0x18000a139  mov     al, 1
0x18000a13b  mov     rbx, [rsp+28h+arg_0]
0x18000a140  mov     rbp, [rsp+28h+arg_8]
0x18000a145  mov     rsi, [rsp+28h+arg_10]
0x18000a14a  add     rsp, 20h
0x18000a14e  pop     rdi
0x18000a14f  retn
```
