# VsmmVaGpaRangepBackgroundDecommitWorker

- ea: `0x1400f0910`
- end: `0x1400f0a2e`
- name: `VsmmVaGpaRangepBackgroundDecommitWorker`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000f7bc`
- `0x14002e270`
- `0x14002ed60`
- `0x140031a20`
- `0x1400f0910`
- `0x1400f0a40`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400f0a10`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400f0a10`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f0961`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400f0961`

## pseudocode

```c
NTSTATUS __fastcall VsmmVaGpaRangepBackgroundDecommitWorker(__int64 a1)
{
  int v2; // ebx
  union _LARGE_INTEGER *Timeout; // rax
  NTSTATUS v4; // eax
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 i; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdi
  __int64 v11; // rax
  _QWORD *v12; // rsi
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+10h] BYREF

  v14 = 0;
  v15 = 0;
  LOBYTE(v2) = 0;
LABEL_2:
  if ( (v2 & 2) != 0 )
  {
    Timeout = 0;
    goto LABEL_5;
  }
  while ( 1 )
  {
    v15 = -300000000;
    Timeout = (union _LARGE_INTEGER *)&v15;
LABEL_5:
    v4 = KeWaitForSingleObject((PVOID)(a1 + 8928), Executive, 0, 0, Timeout);
    v2 = *(_DWORD *)(a1 + 8952);
    if ( (v2 & 1) != 0 )
      return PsTerminateSystemThread(0);
    if ( v4 == 258 || (v2 & 2) != 0 )
    {
      v5 = VsmmGpaRangeListAcquireReadOnly(a1, &v14);
      v6 = 0;
      for ( i = v5; ; i = v5 )
      {
        v11 = VsmmGpaRangeLookupLowerBoundPrimary(i, v6);
        v12 = (_QWORD *)v11;
        if ( !v11 )
          break;
        v8 = *(_QWORD *)(v11 + 384);
        if ( (*(_DWORD *)(v8 + 264) & 0x8000) != 0 )
        {
          VsmmGpaRangeListReleaseReadOnly(v5, v14, v9);
          VsmmVaGpaRangepBackgroundDecommitCandidateRanges(v12);
          v5 = VsmmGpaRangeListAcquireReadOnly(a1, &v14);
        }
        v10 = v12[34];
        LOBYTE(v9) = 1;
        VsmmGpaRangeRelease(v8, v12, v9);
        v6 = v10 + 1;
      }
      VsmmGpaRangeListReleaseReadOnly(v5, v14, v9);
      goto LABEL_2;
    }
  }
}

```

## disassembly

```asm
0x1400f0910  mov     [rsp+arg_10], rbx
0x1400f0915  push    rbp
0x1400f0916  push    rsi
0x1400f0917  push    rdi
0x1400f0918  push    r14
0x1400f091a  push    r15
0x1400f091c  sub     rsp, 30h
0x1400f0920  mov     r14, rcx
0x1400f0923  mov     [rsp+58h+arg_0], 0
0x1400f092b  mov     [rsp+58h+arg_8], 0
0x1400f0934  xor     ebx, ebx
0x1400f0936  test    bl, 2
0x1400f0939  jz      short loc_1400F093F
0x1400f093b  xor     eax, eax
0x1400f093d  jmp     short loc_1400F094D
0x1400f093f  mov     [rsp+58h+arg_8], 0FFFFFFFFEE1E5D00h
0x1400f0948  lea     rax, [rsp+58h+arg_8]
0x1400f094d  xor     r9d, r9d; Alertable
0x1400f0950  mov     [rsp+58h+Timeout], rax; Timeout
0x1400f0955  xor     r8d, r8d; WaitMode
0x1400f0958  lea     rcx, [r14+22E0h]; Object
0x1400f095f  xor     edx, edx; WaitReason
0x1400f0961  call    cs:__imp_KeWaitForSingleObject
0x1400f0968  nop     dword ptr [rax+rax+00h]
0x1400f096d  mov     ebx, [r14+22F8h]
0x1400f0974  test    bl, 1
0x1400f0977  jnz     loc_1400F0A0E
0x1400f097d  cmp     eax, 102h
0x1400f0982  jz      short loc_1400F0989
0x1400f0984  test    bl, 2
0x1400f0987  jz      short loc_1400F093F
0x1400f0989  lea     rdx, [rsp+58h+arg_0]
0x1400f098e  mov     rcx, r14
0x1400f0991  call    VsmmGpaRangeListAcquireReadOnly
0x1400f0996  mov     rbp, rax
0x1400f0999  xor     edx, edx
0x1400f099b  mov     rcx, rax
0x1400f099e  jmp     short loc_1400F09F0
0x1400f09a0  mov     rcx, [rsi+180h]
0x1400f09a7  test    dword ptr [rcx+108h], 8000h
0x1400f09b1  jz      short loc_1400F09D7
0x1400f09b3  mov     edx, [rsp+58h+arg_0]
0x1400f09b7  mov     rcx, rbp
0x1400f09ba  call    VsmmGpaRangeListReleaseReadOnly
0x1400f09bf  mov     rcx, rsi
0x1400f09c2  call    VsmmVaGpaRangepBackgroundDecommitCandidateRanges
0x1400f09c7  lea     rdx, [rsp+58h+arg_0]
0x1400f09cc  mov     rcx, r14
0x1400f09cf  call    VsmmGpaRangeListAcquireReadOnly
0x1400f09d4  mov     rbp, rax
0x1400f09d7  mov     rdi, [rsi+110h]
0x1400f09de  mov     r8b, 1
0x1400f09e1  mov     rdx, rsi
0x1400f09e4  call    VsmmGpaRangeRelease
0x1400f09e9  lea     rdx, [rdi+1]
0x1400f09ed  mov     rcx, rbp
0x1400f09f0  call    VsmmGpaRangeLookupLowerBoundPrimary
0x1400f09f5  mov     rsi, rax
0x1400f09f8  test    rax, rax
0x1400f09fb  jnz     short loc_1400F09A0
0x1400f09fd  mov     edx, [rsp+58h+arg_0]
0x1400f0a01  mov     rcx, rbp
0x1400f0a04  call    VsmmGpaRangeListReleaseReadOnly
0x1400f0a09  jmp     loc_1400F0936
0x1400f0a0e  xor     ecx, ecx; ExitStatus
0x1400f0a10  call    cs:__imp_PsTerminateSystemThread
0x1400f0a17  nop     dword ptr [rax+rax+00h]
0x1400f0a1c  mov     rbx, [rsp+58h+arg_10]
0x1400f0a21  add     rsp, 30h
0x1400f0a25  pop     r15
0x1400f0a27  pop     r14
0x1400f0a29  pop     rdi
0x1400f0a2a  pop     rsi
0x1400f0a2b  pop     rbp
0x1400f0a2c  retn
```
