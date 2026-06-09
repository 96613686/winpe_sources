# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800057f8`
- end: `0x1800058d4`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005100`
- `0x1800057f8`

## callees

- `0x180001f8c`
- `0x1800057f8`

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
0x1800057f8  push    rbx
0x1800057fa  push    rbp
0x1800057fb  push    rsi
0x1800057fc  push    rdi
0x1800057fd  sub     rsp, 28h
0x180005801  xor     al, al
0x180005803  mov     byte ptr [r8], 0
0x180005807  mov     rbp, r9
0x18000580a  mov     rdi, r8
0x18000580d  mov     rsi, rdx
0x180005810  mov     rbx, rcx
0x180005813  test    rdx, rdx
0x180005816  jz      loc_1800058CB
0x18000581c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005820  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005825  mov     rdx, [rsi+20h]
0x180005829  test    rdx, rdx
0x18000582c  jz      loc_1800058CB
0x180005832  cmp     dword ptr [rdx], 0
0x180005835  jnz     short loc_180005848
0x180005837  mov     eax, 1
0x18000583c  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005844  inc     eax
0x180005846  mov     [rdx], eax
0x180005848  cmp     dword ptr [rbx+50h], 0
0x18000584c  jnz     short loc_18000585F
0x18000584e  movups  xmm0, xmmword ptr [rdx]
0x180005851  movups  xmmword ptr [rbx+50h], xmm0
0x180005855  movsd   xmm1, qword ptr [rdx+10h]
0x18000585a  movsd   qword ptr [rbx+60h], xmm1
0x18000585f  movups  xmm0, xmmword ptr [rdx]
0x180005862  lea     r10, [rdi+rbp]
0x180005866  movups  xmmword ptr [rbx+68h], xmm0
0x18000586a  movsd   xmm1, qword ptr [rdx+10h]
0x18000586f  movsd   qword ptr [rbx+78h], xmm1
0x180005874  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005878  mov     rax, rbx
0x18000587b  inc     rax
0x18000587e  cmp     byte ptr [rdi+rax], 0
0x180005882  jnz     short loc_18000587B
0x180005884  lea     rcx, [rax+rdi]
0x180005888  mov     rax, r10
0x18000588b  sub     rax, rcx
0x18000588e  cmp     rax, 2
0x180005892  jle     short loc_1800058C9
0x180005894  mov     byte ptr [rcx], 5Ch ; '\'
0x180005897  lea     rdi, [rcx+1]
0x18000589b  mov     r8, [rdx+8]; Source
0x18000589f  inc     rbx
0x1800058a2  cmp     byte ptr [r8+rbx], 0
0x1800058a7  jnz     short loc_18000589F
0x1800058a9  sub     r10, rdi
0x1800058ac  inc     rbx
0x1800058af  cmp     rbx, r10
0x1800058b2  mov     rdx, r10; DestinationSize
0x1800058b5  mov     rcx, rdi; Destination
0x1800058b8  cmovnb  rbx, r10
0x1800058bc  mov     r9, rbx; SourceSize
0x1800058bf  call    memcpy_s
0x1800058c4  mov     byte ptr [rbx+rdi-1], 0
0x1800058c9  mov     al, 1
0x1800058cb  add     rsp, 28h
0x1800058cf  pop     rdi
0x1800058d0  pop     rsi
0x1800058d1  pop     rbp
0x1800058d2  pop     rbx
0x1800058d3  retn
```
