# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140006cd8`
- end: `0x140006db5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400065e0`
- `0x140006cd8`

## callees

- `0x140006cd8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006d9f`
- `msvcrt!memcpy_s` at `0x140006d9f`

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
0x140006cd8  push    rbx
0x140006cda  push    rbp
0x140006cdb  push    rsi
0x140006cdc  push    rdi
0x140006cdd  sub     rsp, 28h
0x140006ce1  xor     al, al
0x140006ce3  mov     byte ptr [r8], 0
0x140006ce7  mov     rbp, r9
0x140006cea  mov     rdi, r8
0x140006ced  mov     rsi, rdx
0x140006cf0  mov     rbx, rcx
0x140006cf3  test    rdx, rdx
0x140006cf6  jz      loc_140006DAC
0x140006cfc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140006d00  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006d05  mov     rdx, [rsi+20h]
0x140006d09  test    rdx, rdx
0x140006d0c  jz      loc_140006DAC
0x140006d12  cmp     dword ptr [rdx], 0
0x140006d15  jnz     short loc_140006D28
0x140006d17  mov     eax, 1
0x140006d1c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140006d24  inc     eax
0x140006d26  mov     [rdx], eax
0x140006d28  cmp     dword ptr [rbx+50h], 0
0x140006d2c  jnz     short loc_140006D3F
0x140006d2e  movups  xmm0, xmmword ptr [rdx]
0x140006d31  movups  xmmword ptr [rbx+50h], xmm0
0x140006d35  movsd   xmm1, qword ptr [rdx+10h]
0x140006d3a  movsd   qword ptr [rbx+60h], xmm1
0x140006d3f  movups  xmm0, xmmword ptr [rdx]
0x140006d42  lea     r10, [rdi+rbp]
0x140006d46  movups  xmmword ptr [rbx+68h], xmm0
0x140006d4a  movsd   xmm1, qword ptr [rdx+10h]
0x140006d4f  movsd   qword ptr [rbx+78h], xmm1
0x140006d54  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140006d58  mov     rax, rbx
0x140006d5b  inc     rax
0x140006d5e  cmp     byte ptr [rdi+rax], 0
0x140006d62  jnz     short loc_140006D5B
0x140006d64  lea     rcx, [rax+rdi]
0x140006d68  mov     rax, r10
0x140006d6b  sub     rax, rcx
0x140006d6e  cmp     rax, 2
0x140006d72  jle     short loc_140006DAA
0x140006d74  mov     byte ptr [rcx], 5Ch ; '\'
0x140006d77  lea     rdi, [rcx+1]
0x140006d7b  mov     r8, [rdx+8]; Source
0x140006d7f  inc     rbx
0x140006d82  cmp     byte ptr [r8+rbx], 0
0x140006d87  jnz     short loc_140006D7F
0x140006d89  sub     r10, rdi
0x140006d8c  inc     rbx
0x140006d8f  cmp     rbx, r10
0x140006d92  mov     rdx, r10; DestinationSize
0x140006d95  mov     rcx, rdi; Destination
0x140006d98  cmovnb  rbx, r10
0x140006d9c  mov     r9, rbx; SourceSize
0x140006d9f  call    cs:__imp_memcpy_s
0x140006da5  mov     byte ptr [rbx+rdi-1], 0
0x140006daa  mov     al, 1
0x140006dac  add     rsp, 28h
0x140006db0  pop     rdi
0x140006db1  pop     rsi
0x140006db2  pop     rbp
0x140006db3  pop     rbx
0x140006db4  retn
```
