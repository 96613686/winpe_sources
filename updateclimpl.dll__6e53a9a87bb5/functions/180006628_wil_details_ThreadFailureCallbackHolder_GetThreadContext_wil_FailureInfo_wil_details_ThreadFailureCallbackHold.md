# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006628`
- end: `0x18000671d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `245`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006628`
- `0x180006730`

## callees

- `0x180004348`
- `0x180006628`

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
0x180006628  mov     [rsp+arg_0], rbx
0x18000662d  mov     [rsp+arg_8], rbp
0x180006632  mov     [rsp+arg_10], rsi
0x180006637  push    rdi
0x180006638  sub     rsp, 20h
0x18000663c  xor     al, al
0x18000663e  mov     byte ptr [r8], 0
0x180006642  mov     rbp, r9
0x180006645  mov     rbx, r8
0x180006648  mov     rsi, rdx
0x18000664b  mov     rdi, rcx
0x18000664e  test    rdx, rdx
0x180006651  jz      loc_180006708
0x180006657  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18000665b  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006660  mov     rdx, [rsi+20h]
0x180006664  test    rdx, rdx
0x180006667  jz      loc_180006708
0x18000666d  cmp     dword ptr [rdx], 0
0x180006670  jnz     short loc_180006683
0x180006672  mov     eax, 1
0x180006677  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000667f  inc     eax
0x180006681  mov     [rdx], eax
0x180006683  cmp     dword ptr [rdi+50h], 0
0x180006687  jnz     short loc_18000669A
0x180006689  movups  xmm0, xmmword ptr [rdx]
0x18000668c  movups  xmmword ptr [rdi+50h], xmm0
0x180006690  movsd   xmm1, qword ptr [rdx+10h]
0x180006695  movsd   qword ptr [rdi+60h], xmm1
0x18000669a  movups  xmm0, xmmword ptr [rdx]
0x18000669d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800066a1  lea     r10, [rbx+rbp]
0x1800066a5  mov     rax, rcx
0x1800066a8  movups  xmmword ptr [rdi+68h], xmm0
0x1800066ac  movsd   xmm1, qword ptr [rdx+10h]
0x1800066b1  movsd   qword ptr [rdi+78h], xmm1
0x1800066b6  inc     rax
0x1800066b9  cmp     byte ptr [rbx+rax], 0
0x1800066bd  jnz     short loc_1800066B6
0x1800066bf  add     rbx, rax
0x1800066c2  mov     rax, r10
0x1800066c5  sub     rax, rbx
0x1800066c8  cmp     rax, 2
0x1800066cc  jle     short loc_180006706
0x1800066ce  mov     byte ptr [rbx], 5Ch ; '\'
0x1800066d1  lea     rdi, [rbx+1]
0x1800066d5  mov     r8, [rdx+8]; Source
0x1800066d9  inc     rcx
0x1800066dc  cmp     byte ptr [r8+rcx], 0
0x1800066e1  jnz     short loc_1800066D9
0x1800066e3  inc     rcx
0x1800066e6  sub     r10, rdi
0x1800066e9  cmp     rcx, r10
0x1800066ec  mov     rbx, r10
0x1800066ef  mov     rdx, r10; DestinationSize
0x1800066f2  cmovb   rbx, rcx
0x1800066f6  mov     rcx, rdi; Destination
0x1800066f9  mov     r9, rbx; SourceSize
0x1800066fc  call    memcpy_s
0x180006701  mov     byte ptr [rbx+rdi-1], 0
0x180006706  mov     al, 1
0x180006708  mov     rbx, [rsp+28h+arg_0]
0x18000670d  mov     rbp, [rsp+28h+arg_8]
0x180006712  mov     rsi, [rsp+28h+arg_10]
0x180006717  add     rsp, 20h
0x18000671b  pop     rdi
0x18000671c  retn
```
