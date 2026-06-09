# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006350`
- end: `0x18000642d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a64`
- `0x180006350`

## callees

- `0x180006350`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006417`
- `msvcrt!memcpy_s` at `0x180006417`

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
0x180006350  push    rbx
0x180006352  push    rbp
0x180006353  push    rsi
0x180006354  push    rdi
0x180006355  sub     rsp, 28h
0x180006359  xor     al, al
0x18000635b  mov     byte ptr [r8], 0
0x18000635f  mov     rbp, r9
0x180006362  mov     rdi, r8
0x180006365  mov     rsi, rdx
0x180006368  mov     rbx, rcx
0x18000636b  test    rdx, rdx
0x18000636e  jz      loc_180006424
0x180006374  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006378  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000637d  mov     rdx, [rsi+20h]
0x180006381  test    rdx, rdx
0x180006384  jz      loc_180006424
0x18000638a  cmp     dword ptr [rdx], 0
0x18000638d  jnz     short loc_1800063A0
0x18000638f  mov     eax, 1
0x180006394  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000639c  inc     eax
0x18000639e  mov     [rdx], eax
0x1800063a0  cmp     dword ptr [rbx+50h], 0
0x1800063a4  jnz     short loc_1800063B7
0x1800063a6  movups  xmm0, xmmword ptr [rdx]
0x1800063a9  movups  xmmword ptr [rbx+50h], xmm0
0x1800063ad  movsd   xmm1, qword ptr [rdx+10h]
0x1800063b2  movsd   qword ptr [rbx+60h], xmm1
0x1800063b7  movups  xmm0, xmmword ptr [rdx]
0x1800063ba  lea     r10, [rdi+rbp]
0x1800063be  movups  xmmword ptr [rbx+68h], xmm0
0x1800063c2  movsd   xmm1, qword ptr [rdx+10h]
0x1800063c7  movsd   qword ptr [rbx+78h], xmm1
0x1800063cc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800063d0  mov     rax, rbx
0x1800063d3  inc     rax
0x1800063d6  cmp     byte ptr [rdi+rax], 0
0x1800063da  jnz     short loc_1800063D3
0x1800063dc  lea     rcx, [rax+rdi]
0x1800063e0  mov     rax, r10
0x1800063e3  sub     rax, rcx
0x1800063e6  cmp     rax, 2
0x1800063ea  jle     short loc_180006422
0x1800063ec  mov     byte ptr [rcx], 5Ch ; '\'
0x1800063ef  lea     rdi, [rcx+1]
0x1800063f3  mov     r8, [rdx+8]; Source
0x1800063f7  inc     rbx
0x1800063fa  cmp     byte ptr [r8+rbx], 0
0x1800063ff  jnz     short loc_1800063F7
0x180006401  sub     r10, rdi
0x180006404  inc     rbx
0x180006407  cmp     rbx, r10
0x18000640a  mov     rdx, r10; DestinationSize
0x18000640d  mov     rcx, rdi; Destination
0x180006410  cmovnb  rbx, r10
0x180006414  mov     r9, rbx; SourceSize
0x180006417  call    cs:__imp_memcpy_s
0x18000641d  mov     byte ptr [rbx+rdi-1], 0
0x180006422  mov     al, 1
0x180006424  add     rsp, 28h
0x180006428  pop     rdi
0x180006429  pop     rsi
0x18000642a  pop     rbp
0x18000642b  pop     rbx
0x18000642c  retn
```
