# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001e990`
- end: `0x18001ea6d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e37c`
- `0x18001e990`

## callees

- `0x18001e990`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001ea57`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001ea57`

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
0x18001e990  push    rbx
0x18001e992  push    rbp
0x18001e993  push    rsi
0x18001e994  push    rdi
0x18001e995  sub     rsp, 28h
0x18001e999  xor     al, al
0x18001e99b  mov     byte ptr [r8], 0
0x18001e99f  mov     rbp, r9
0x18001e9a2  mov     rdi, r8
0x18001e9a5  mov     rsi, rdx
0x18001e9a8  mov     rbx, rcx
0x18001e9ab  test    rdx, rdx
0x18001e9ae  jz      loc_18001EA64
0x18001e9b4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001e9b8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001e9bd  mov     rdx, [rsi+20h]
0x18001e9c1  test    rdx, rdx
0x18001e9c4  jz      loc_18001EA64
0x18001e9ca  cmp     dword ptr [rdx], 0
0x18001e9cd  jnz     short loc_18001E9E0
0x18001e9cf  mov     eax, 1
0x18001e9d4  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001e9dc  inc     eax
0x18001e9de  mov     [rdx], eax
0x18001e9e0  cmp     dword ptr [rbx+50h], 0
0x18001e9e4  jnz     short loc_18001E9F7
0x18001e9e6  movups  xmm0, xmmword ptr [rdx]
0x18001e9e9  movups  xmmword ptr [rbx+50h], xmm0
0x18001e9ed  movsd   xmm1, qword ptr [rdx+10h]
0x18001e9f2  movsd   qword ptr [rbx+60h], xmm1
0x18001e9f7  movups  xmm0, xmmword ptr [rdx]
0x18001e9fa  lea     r10, [rdi+rbp]
0x18001e9fe  movups  xmmword ptr [rbx+68h], xmm0
0x18001ea02  movsd   xmm1, qword ptr [rdx+10h]
0x18001ea07  movsd   qword ptr [rbx+78h], xmm1
0x18001ea0c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ea10  mov     rax, rbx
0x18001ea13  inc     rax
0x18001ea16  cmp     byte ptr [rdi+rax], 0
0x18001ea1a  jnz     short loc_18001EA13
0x18001ea1c  lea     rcx, [rax+rdi]
0x18001ea20  mov     rax, r10
0x18001ea23  sub     rax, rcx
0x18001ea26  cmp     rax, 2
0x18001ea2a  jle     short loc_18001EA62
0x18001ea2c  mov     byte ptr [rcx], 5Ch ; '\'
0x18001ea2f  lea     rdi, [rcx+1]
0x18001ea33  mov     r8, [rdx+8]; Source
0x18001ea37  inc     rbx
0x18001ea3a  cmp     byte ptr [r8+rbx], 0
0x18001ea3f  jnz     short loc_18001EA37
0x18001ea41  sub     r10, rdi
0x18001ea44  inc     rbx
0x18001ea47  cmp     rbx, r10
0x18001ea4a  mov     rdx, r10; DestinationSize
0x18001ea4d  mov     rcx, rdi; Destination
0x18001ea50  cmovnb  rbx, r10
0x18001ea54  mov     r9, rbx; SourceSize
0x18001ea57  call    cs:__imp_memcpy_s
0x18001ea5d  mov     byte ptr [rbx+rdi-1], 0
0x18001ea62  mov     al, 1
0x18001ea64  add     rsp, 28h
0x18001ea68  pop     rdi
0x18001ea69  pop     rsi
0x18001ea6a  pop     rbp
0x18001ea6b  pop     rbx
0x18001ea6c  retn
```
