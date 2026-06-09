# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x140004610`
- end: `0x140004705`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `245`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004610`
- `0x140004710`

## callees

- `0x140002ba0`
- `0x140004610`

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
  __int64 v10; // rcx
  char *v11; // r10
  __int64 v12; // rax
  char *v13; // rbx
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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v11 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v10;
        while ( v15[v10] );
        v16 = v10 + 1;
        v17 = v11 - v14;
        if ( v16 < v11 - v14 )
          v17 = v16;
        memcpy_s(v14, v11 - v14, v15, v17);
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
0x140004610  mov     [rsp+arg_0], rbx
0x140004615  mov     [rsp+arg_8], rbp
0x14000461a  mov     [rsp+arg_10], rsi
0x14000461f  push    rdi
0x140004620  sub     rsp, 20h
0x140004624  xor     al, al
0x140004626  mov     byte ptr [r8], 0
0x14000462a  mov     rbp, r9
0x14000462d  mov     rbx, r8
0x140004630  mov     rsi, rdx
0x140004633  mov     rdi, rcx
0x140004636  test    rdx, rdx
0x140004639  jz      loc_1400046F0
0x14000463f  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x140004643  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004648  mov     rdx, [rsi+20h]
0x14000464c  test    rdx, rdx
0x14000464f  jz      loc_1400046F0
0x140004655  cmp     dword ptr [rdx], 0
0x140004658  jnz     short loc_14000466B
0x14000465a  mov     eax, 1
0x14000465f  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x140004667  inc     eax
0x140004669  mov     [rdx], eax
0x14000466b  cmp     dword ptr [rdi+50h], 0
0x14000466f  jnz     short loc_140004682
0x140004671  movups  xmm0, xmmword ptr [rdx]
0x140004674  movups  xmmword ptr [rdi+50h], xmm0
0x140004678  movsd   xmm1, qword ptr [rdx+10h]
0x14000467d  movsd   qword ptr [rdi+60h], xmm1
0x140004682  movups  xmm0, xmmword ptr [rdx]
0x140004685  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140004689  lea     r10, [rbx+rbp]
0x14000468d  mov     rax, rcx
0x140004690  movups  xmmword ptr [rdi+68h], xmm0
0x140004694  movsd   xmm1, qword ptr [rdx+10h]
0x140004699  movsd   qword ptr [rdi+78h], xmm1
0x14000469e  inc     rax
0x1400046a1  cmp     byte ptr [rbx+rax], 0
0x1400046a5  jnz     short loc_14000469E
0x1400046a7  add     rbx, rax
0x1400046aa  mov     rax, r10
0x1400046ad  sub     rax, rbx
0x1400046b0  cmp     rax, 2
0x1400046b4  jle     short loc_1400046EE
0x1400046b6  mov     byte ptr [rbx], 5Ch ; '\'
0x1400046b9  lea     rdi, [rbx+1]
0x1400046bd  mov     r8, [rdx+8]; Source
0x1400046c1  inc     rcx
0x1400046c4  cmp     byte ptr [r8+rcx], 0
0x1400046c9  jnz     short loc_1400046C1
0x1400046cb  inc     rcx
0x1400046ce  sub     r10, rdi
0x1400046d1  cmp     rcx, r10
0x1400046d4  mov     rbx, r10
0x1400046d7  mov     rdx, r10; DestinationSize
0x1400046da  cmovb   rbx, rcx
0x1400046de  mov     rcx, rdi; Destination
0x1400046e1  mov     r9, rbx; SourceSize
0x1400046e4  call    memcpy_s
0x1400046e9  mov     byte ptr [rbx+rdi-1], 0
0x1400046ee  mov     al, 1
0x1400046f0  mov     rbx, [rsp+28h+arg_0]
0x1400046f5  mov     rbp, [rsp+28h+arg_8]
0x1400046fa  mov     rsi, [rsp+28h+arg_10]
0x1400046ff  add     rsp, 20h
0x140004703  pop     rdi
0x140004704  retn
```
