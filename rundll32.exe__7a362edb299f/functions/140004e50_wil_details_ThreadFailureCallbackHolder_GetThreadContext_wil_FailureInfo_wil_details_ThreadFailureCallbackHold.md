# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004e50`
- end: `0x140004f2c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046f0`
- `0x140004e50`

## callees

- `0x140004e50`
- `0x140007708`

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
        memcpy_s_0(v18, v16, v15, v17);
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
0x140004e50  push    rbx
0x140004e52  push    rbp
0x140004e53  push    rsi
0x140004e54  push    rdi
0x140004e55  sub     rsp, 28h
0x140004e59  xor     al, al
0x140004e5b  mov     byte ptr [r8], 0
0x140004e5f  mov     rbp, r9
0x140004e62  mov     rdi, r8
0x140004e65  mov     rsi, rdx
0x140004e68  mov     rbx, rcx
0x140004e6b  test    rdx, rdx
0x140004e6e  jz      loc_140004F23
0x140004e74  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004e78  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004e7d  mov     rdx, [rsi+20h]
0x140004e81  test    rdx, rdx
0x140004e84  jz      loc_140004F23
0x140004e8a  cmp     dword ptr [rdx], 0
0x140004e8d  jnz     short loc_140004EA0
0x140004e8f  mov     eax, 1
0x140004e94  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004e9c  inc     eax
0x140004e9e  mov     [rdx], eax
0x140004ea0  cmp     dword ptr [rbx+50h], 0
0x140004ea4  jnz     short loc_140004EB7
0x140004ea6  movups  xmm0, xmmword ptr [rdx]
0x140004ea9  movups  xmmword ptr [rbx+50h], xmm0
0x140004ead  movsd   xmm1, qword ptr [rdx+10h]
0x140004eb2  movsd   qword ptr [rbx+60h], xmm1
0x140004eb7  movups  xmm0, xmmword ptr [rdx]
0x140004eba  lea     r10, [rdi+rbp]
0x140004ebe  movups  xmmword ptr [rbx+68h], xmm0
0x140004ec2  movsd   xmm1, qword ptr [rdx+10h]
0x140004ec7  movsd   qword ptr [rbx+78h], xmm1
0x140004ecc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004ed0  mov     rax, rbx
0x140004ed3  inc     rax
0x140004ed6  cmp     byte ptr [rdi+rax], 0
0x140004eda  jnz     short loc_140004ED3
0x140004edc  lea     rcx, [rax+rdi]
0x140004ee0  mov     rax, r10
0x140004ee3  sub     rax, rcx
0x140004ee6  cmp     rax, 2
0x140004eea  jle     short loc_140004F21
0x140004eec  mov     byte ptr [rcx], 5Ch ; '\'
0x140004eef  lea     rdi, [rcx+1]
0x140004ef3  mov     r8, [rdx+8]; Source
0x140004ef7  inc     rbx
0x140004efa  cmp     byte ptr [r8+rbx], 0
0x140004eff  jnz     short loc_140004EF7
0x140004f01  sub     r10, rdi
0x140004f04  inc     rbx
0x140004f07  cmp     rbx, r10
0x140004f0a  mov     rdx, r10; DestinationSize
0x140004f0d  mov     rcx, rdi; Destination
0x140004f10  cmovnb  rbx, r10
0x140004f14  mov     r9, rbx; SourceSize
0x140004f17  call    memcpy_s_0
0x140004f1c  mov     byte ptr [rbx+rdi-1], 0
0x140004f21  mov     al, 1
0x140004f23  add     rsp, 28h
0x140004f27  pop     rdi
0x140004f28  pop     rsi
0x140004f29  pop     rbp
0x140004f2a  pop     rbx
0x140004f2b  retn
```
