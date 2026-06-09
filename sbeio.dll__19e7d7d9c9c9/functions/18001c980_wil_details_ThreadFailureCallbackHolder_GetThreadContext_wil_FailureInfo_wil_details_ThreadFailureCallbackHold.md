# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001c980`
- end: `0x18001ca5c`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ba18`
- `0x18001c980`

## callees

- `0x18001c980`
- `0x180027394`

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
0x18001c980  push    rbx
0x18001c982  push    rbp
0x18001c983  push    rsi
0x18001c984  push    rdi
0x18001c985  sub     rsp, 28h
0x18001c989  xor     al, al
0x18001c98b  mov     byte ptr [r8], 0
0x18001c98f  mov     rbp, r9
0x18001c992  mov     rdi, r8
0x18001c995  mov     rsi, rdx
0x18001c998  mov     rbx, rcx
0x18001c99b  test    rdx, rdx
0x18001c99e  jz      loc_18001CA53
0x18001c9a4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001c9a8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001c9ad  mov     rdx, [rsi+20h]
0x18001c9b1  test    rdx, rdx
0x18001c9b4  jz      loc_18001CA53
0x18001c9ba  cmp     dword ptr [rdx], 0
0x18001c9bd  jnz     short loc_18001C9D0
0x18001c9bf  mov     eax, 1
0x18001c9c4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001c9cc  inc     eax
0x18001c9ce  mov     [rdx], eax
0x18001c9d0  cmp     dword ptr [rbx+50h], 0
0x18001c9d4  jnz     short loc_18001C9E7
0x18001c9d6  movups  xmm0, xmmword ptr [rdx]
0x18001c9d9  movups  xmmword ptr [rbx+50h], xmm0
0x18001c9dd  movsd   xmm1, qword ptr [rdx+10h]
0x18001c9e2  movsd   qword ptr [rbx+60h], xmm1
0x18001c9e7  movups  xmm0, xmmword ptr [rdx]
0x18001c9ea  lea     r10, [rdi+rbp]
0x18001c9ee  movups  xmmword ptr [rbx+68h], xmm0
0x18001c9f2  movsd   xmm1, qword ptr [rdx+10h]
0x18001c9f7  movsd   qword ptr [rbx+78h], xmm1
0x18001c9fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ca00  mov     rax, rbx
0x18001ca03  inc     rax
0x18001ca06  cmp     byte ptr [rdi+rax], 0
0x18001ca0a  jnz     short loc_18001CA03
0x18001ca0c  lea     rcx, [rax+rdi]
0x18001ca10  mov     rax, r10
0x18001ca13  sub     rax, rcx
0x18001ca16  cmp     rax, 2
0x18001ca1a  jle     short loc_18001CA51
0x18001ca1c  mov     byte ptr [rcx], 5Ch ; '\'
0x18001ca1f  lea     rdi, [rcx+1]
0x18001ca23  mov     r8, [rdx+8]; Source
0x18001ca27  inc     rbx
0x18001ca2a  cmp     byte ptr [r8+rbx], 0
0x18001ca2f  jnz     short loc_18001CA27
0x18001ca31  sub     r10, rdi
0x18001ca34  inc     rbx
0x18001ca37  cmp     rbx, r10
0x18001ca3a  mov     rdx, r10; DestinationSize
0x18001ca3d  mov     rcx, rdi; Destination
0x18001ca40  cmovnb  rbx, r10
0x18001ca44  mov     r9, rbx; SourceSize
0x18001ca47  call    memcpy_s
0x18001ca4c  mov     byte ptr [rbx+rdi-1], 0
0x18001ca51  mov     al, 1
0x18001ca53  add     rsp, 28h
0x18001ca57  pop     rdi
0x18001ca58  pop     rsi
0x18001ca59  pop     rbp
0x18001ca5a  pop     rbx
0x18001ca5b  retn
```
