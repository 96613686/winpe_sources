# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800097c8`
- end: `0x1800098c1`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `249`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009020`
- `0x1800097c8`

## callees

- `0x1800097c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009898`
- `msvcrt!memcpy_s` at `0x180009898`

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
0x1800097c8  mov     [rsp+arg_0], rbx
0x1800097cd  mov     [rsp+arg_8], rbp
0x1800097d2  mov     [rsp+arg_10], rsi
0x1800097d7  push    rdi
0x1800097d8  sub     rsp, 20h
0x1800097dc  xor     al, al
0x1800097de  mov     byte ptr [r8], 0
0x1800097e2  mov     rbp, r9
0x1800097e5  mov     rdi, r8
0x1800097e8  mov     rsi, rdx
0x1800097eb  mov     rbx, rcx
0x1800097ee  test    rdx, rdx
0x1800097f1  jz      loc_1800098AB
0x1800097f7  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800097fb  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009800  mov     rdx, [rsi+20h]
0x180009804  test    rdx, rdx
0x180009807  jz      loc_1800098AB
0x18000980d  cmp     dword ptr [rdx], 0
0x180009810  jnz     short loc_180009823
0x180009812  mov     eax, 1
0x180009817  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000981f  inc     eax
0x180009821  mov     [rdx], eax
0x180009823  cmp     dword ptr [rbx+50h], 0
0x180009827  jnz     short loc_18000983A
0x180009829  movups  xmm0, xmmword ptr [rdx]
0x18000982c  movups  xmmword ptr [rbx+50h], xmm0
0x180009830  movsd   xmm1, qword ptr [rdx+10h]
0x180009835  movsd   qword ptr [rbx+60h], xmm1
0x18000983a  movups  xmm0, xmmword ptr [rdx]
0x18000983d  lea     rcx, [rdi+rbp]
0x180009841  movups  xmmword ptr [rbx+68h], xmm0
0x180009845  movsd   xmm1, qword ptr [rdx+10h]
0x18000984a  movsd   qword ptr [rbx+78h], xmm1
0x18000984f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009853  mov     rax, rbx
0x180009856  inc     rax
0x180009859  cmp     byte ptr [rdi+rax], 0
0x18000985d  jnz     short loc_180009856
0x18000985f  add     rdi, rax
0x180009862  mov     rax, rcx
0x180009865  sub     rax, rdi
0x180009868  cmp     rax, 2
0x18000986c  jle     short loc_1800098A9
0x18000986e  mov     byte ptr [rdi], 5Ch ; '\'
0x180009871  inc     rdi
0x180009874  mov     r8, [rdx+8]; Source
0x180009878  inc     rbx
0x18000987b  cmp     byte ptr [r8+rbx], 0
0x180009880  jnz     short loc_180009878
0x180009882  sub     rcx, rdi
0x180009885  inc     rbx
0x180009888  cmp     rbx, rcx
0x18000988b  mov     rdx, rcx; DestinationSize
0x18000988e  cmovnb  rbx, rcx
0x180009892  mov     rcx, rdi; Destination
0x180009895  mov     r9, rbx; SourceSize
0x180009898  call    cs:__imp_memcpy_s
0x18000989f  nop     dword ptr [rax+rax+00h]
0x1800098a4  mov     byte ptr [rbx+rdi-1], 0
0x1800098a9  mov     al, 1
0x1800098ab  mov     rbx, [rsp+28h+arg_0]
0x1800098b0  mov     rbp, [rsp+28h+arg_8]
0x1800098b5  mov     rsi, [rsp+28h+arg_10]
0x1800098ba  add     rsp, 20h
0x1800098be  pop     rdi
0x1800098bf  retn
```
