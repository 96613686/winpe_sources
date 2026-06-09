# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006898`
- end: `0x180006991`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `249`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006120`
- `0x180006898`

## callees

- `0x180006898`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006968`
- `msvcrt!memcpy_s` at `0x180006968`

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
0x180006898  mov     [rsp+arg_0], rbx
0x18000689d  mov     [rsp+arg_8], rbp
0x1800068a2  mov     [rsp+arg_10], rsi
0x1800068a7  push    rdi
0x1800068a8  sub     rsp, 20h
0x1800068ac  xor     al, al
0x1800068ae  mov     byte ptr [r8], 0
0x1800068b2  mov     rbp, r9
0x1800068b5  mov     rdi, r8
0x1800068b8  mov     rsi, rdx
0x1800068bb  mov     rbx, rcx
0x1800068be  test    rdx, rdx
0x1800068c1  jz      loc_18000697B
0x1800068c7  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800068cb  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800068d0  mov     rdx, [rsi+20h]
0x1800068d4  test    rdx, rdx
0x1800068d7  jz      loc_18000697B
0x1800068dd  cmp     dword ptr [rdx], 0
0x1800068e0  jnz     short loc_1800068F3
0x1800068e2  mov     eax, 1
0x1800068e7  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800068ef  inc     eax
0x1800068f1  mov     [rdx], eax
0x1800068f3  cmp     dword ptr [rbx+50h], 0
0x1800068f7  jnz     short loc_18000690A
0x1800068f9  movups  xmm0, xmmword ptr [rdx]
0x1800068fc  movups  xmmword ptr [rbx+50h], xmm0
0x180006900  movsd   xmm1, qword ptr [rdx+10h]
0x180006905  movsd   qword ptr [rbx+60h], xmm1
0x18000690a  movups  xmm0, xmmword ptr [rdx]
0x18000690d  lea     rcx, [rdi+rbp]
0x180006911  movups  xmmword ptr [rbx+68h], xmm0
0x180006915  movsd   xmm1, qword ptr [rdx+10h]
0x18000691a  movsd   qword ptr [rbx+78h], xmm1
0x18000691f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006923  mov     rax, rbx
0x180006926  inc     rax
0x180006929  cmp     byte ptr [rdi+rax], 0
0x18000692d  jnz     short loc_180006926
0x18000692f  add     rdi, rax
0x180006932  mov     rax, rcx
0x180006935  sub     rax, rdi
0x180006938  cmp     rax, 2
0x18000693c  jle     short loc_180006979
0x18000693e  mov     byte ptr [rdi], 5Ch ; '\'
0x180006941  inc     rdi
0x180006944  mov     r8, [rdx+8]; Source
0x180006948  inc     rbx
0x18000694b  cmp     byte ptr [r8+rbx], 0
0x180006950  jnz     short loc_180006948
0x180006952  sub     rcx, rdi
0x180006955  inc     rbx
0x180006958  cmp     rbx, rcx
0x18000695b  mov     rdx, rcx; DestinationSize
0x18000695e  cmovnb  rbx, rcx
0x180006962  mov     rcx, rdi; Destination
0x180006965  mov     r9, rbx; SourceSize
0x180006968  call    cs:__imp_memcpy_s
0x18000696f  nop     dword ptr [rax+rax+00h]
0x180006974  mov     byte ptr [rbx+rdi-1], 0
0x180006979  mov     al, 1
0x18000697b  mov     rbx, [rsp+28h+arg_0]
0x180006980  mov     rbp, [rsp+28h+arg_8]
0x180006985  mov     rsi, [rsp+28h+arg_10]
0x18000698a  add     rsp, 20h
0x18000698e  pop     rdi
0x18000698f  retn
```
