# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180011e08`
- end: `0x180011ee5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011710`
- `0x180011e08`

## callees

- `0x180011e08`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011ecf`
- `msvcrt!memcpy_s` at `0x180011ecf`

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
0x180011e08  push    rbx
0x180011e0a  push    rbp
0x180011e0b  push    rsi
0x180011e0c  push    rdi
0x180011e0d  sub     rsp, 28h
0x180011e11  xor     al, al
0x180011e13  mov     byte ptr [r8], 0
0x180011e17  mov     rbp, r9
0x180011e1a  mov     rdi, r8
0x180011e1d  mov     rsi, rdx
0x180011e20  mov     rbx, rcx
0x180011e23  test    rdx, rdx
0x180011e26  jz      loc_180011EDC
0x180011e2c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180011e30  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180011e35  mov     rdx, [rsi+20h]
0x180011e39  test    rdx, rdx
0x180011e3c  jz      loc_180011EDC
0x180011e42  cmp     dword ptr [rdx], 0
0x180011e45  jnz     short loc_180011E58
0x180011e47  mov     eax, 1
0x180011e4c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180011e54  inc     eax
0x180011e56  mov     [rdx], eax
0x180011e58  cmp     dword ptr [rbx+50h], 0
0x180011e5c  jnz     short loc_180011E6F
0x180011e5e  movups  xmm0, xmmword ptr [rdx]
0x180011e61  movups  xmmword ptr [rbx+50h], xmm0
0x180011e65  movsd   xmm1, qword ptr [rdx+10h]
0x180011e6a  movsd   qword ptr [rbx+60h], xmm1
0x180011e6f  movups  xmm0, xmmword ptr [rdx]
0x180011e72  lea     r10, [rdi+rbp]
0x180011e76  movups  xmmword ptr [rbx+68h], xmm0
0x180011e7a  movsd   xmm1, qword ptr [rdx+10h]
0x180011e7f  movsd   qword ptr [rbx+78h], xmm1
0x180011e84  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011e88  mov     rax, rbx
0x180011e8b  inc     rax
0x180011e8e  cmp     byte ptr [rdi+rax], 0
0x180011e92  jnz     short loc_180011E8B
0x180011e94  lea     rcx, [rax+rdi]
0x180011e98  mov     rax, r10
0x180011e9b  sub     rax, rcx
0x180011e9e  cmp     rax, 2
0x180011ea2  jle     short loc_180011EDA
0x180011ea4  mov     byte ptr [rcx], 5Ch ; '\'
0x180011ea7  lea     rdi, [rcx+1]
0x180011eab  mov     r8, [rdx+8]; Source
0x180011eaf  inc     rbx
0x180011eb2  cmp     byte ptr [r8+rbx], 0
0x180011eb7  jnz     short loc_180011EAF
0x180011eb9  sub     r10, rdi
0x180011ebc  inc     rbx
0x180011ebf  cmp     rbx, r10
0x180011ec2  mov     rdx, r10; DestinationSize
0x180011ec5  mov     rcx, rdi; Destination
0x180011ec8  cmovnb  rbx, r10
0x180011ecc  mov     r9, rbx; SourceSize
0x180011ecf  call    cs:__imp_memcpy_s
0x180011ed5  mov     byte ptr [rbx+rdi-1], 0
0x180011eda  mov     al, 1
0x180011edc  add     rsp, 28h
0x180011ee0  pop     rdi
0x180011ee1  pop     rsi
0x180011ee2  pop     rbp
0x180011ee3  pop     rbx
0x180011ee4  retn
```
