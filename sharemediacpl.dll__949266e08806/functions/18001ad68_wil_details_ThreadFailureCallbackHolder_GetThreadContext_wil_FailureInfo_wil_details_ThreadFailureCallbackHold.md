# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001ad68`
- end: `0x18001ae44`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a590`
- `0x18001ad68`

## callees

- `0x180002906`
- `0x18001ad68`

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
0x18001ad68  push    rbx
0x18001ad6a  push    rbp
0x18001ad6b  push    rsi
0x18001ad6c  push    rdi
0x18001ad6d  sub     rsp, 28h
0x18001ad71  xor     al, al
0x18001ad73  mov     byte ptr [r8], 0
0x18001ad77  mov     rbp, r9
0x18001ad7a  mov     rdi, r8
0x18001ad7d  mov     rsi, rdx
0x18001ad80  mov     rbx, rcx
0x18001ad83  test    rdx, rdx
0x18001ad86  jz      loc_18001AE3B
0x18001ad8c  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001ad90  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001ad95  mov     rdx, [rsi+20h]
0x18001ad99  test    rdx, rdx
0x18001ad9c  jz      loc_18001AE3B
0x18001ada2  cmp     dword ptr [rdx], 0
0x18001ada5  jnz     short loc_18001ADB8
0x18001ada7  mov     eax, 1
0x18001adac  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001adb4  inc     eax
0x18001adb6  mov     [rdx], eax
0x18001adb8  cmp     dword ptr [rbx+50h], 0
0x18001adbc  jnz     short loc_18001ADCF
0x18001adbe  movups  xmm0, xmmword ptr [rdx]
0x18001adc1  movups  xmmword ptr [rbx+50h], xmm0
0x18001adc5  movsd   xmm1, qword ptr [rdx+10h]
0x18001adca  movsd   qword ptr [rbx+60h], xmm1
0x18001adcf  movups  xmm0, xmmword ptr [rdx]
0x18001add2  lea     r10, [rdi+rbp]
0x18001add6  movups  xmmword ptr [rbx+68h], xmm0
0x18001adda  movsd   xmm1, qword ptr [rdx+10h]
0x18001addf  movsd   qword ptr [rbx+78h], xmm1
0x18001ade4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ade8  mov     rax, rbx
0x18001adeb  inc     rax
0x18001adee  cmp     byte ptr [rdi+rax], 0
0x18001adf2  jnz     short loc_18001ADEB
0x18001adf4  lea     rcx, [rax+rdi]
0x18001adf8  mov     rax, r10
0x18001adfb  sub     rax, rcx
0x18001adfe  cmp     rax, 2
0x18001ae02  jle     short loc_18001AE39
0x18001ae04  mov     byte ptr [rcx], 5Ch ; '\'
0x18001ae07  lea     rdi, [rcx+1]
0x18001ae0b  mov     r8, [rdx+8]; Source
0x18001ae0f  inc     rbx
0x18001ae12  cmp     byte ptr [r8+rbx], 0
0x18001ae17  jnz     short loc_18001AE0F
0x18001ae19  sub     r10, rdi
0x18001ae1c  inc     rbx
0x18001ae1f  cmp     rbx, r10
0x18001ae22  mov     rdx, r10; DestinationSize
0x18001ae25  mov     rcx, rdi; Destination
0x18001ae28  cmovnb  rbx, r10
0x18001ae2c  mov     r9, rbx; SourceSize
0x18001ae2f  call    memcpy_s
0x18001ae34  mov     byte ptr [rbx+rdi-1], 0
0x18001ae39  mov     al, 1
0x18001ae3b  add     rsp, 28h
0x18001ae3f  pop     rdi
0x18001ae40  pop     rsi
0x18001ae41  pop     rbp
0x18001ae42  pop     rbx
0x18001ae43  retn
```
