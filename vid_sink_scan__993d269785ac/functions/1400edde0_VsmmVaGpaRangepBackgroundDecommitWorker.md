# VsmmVaGpaRangepBackgroundDecommitWorker

- ea: `0x1400edde0`
- end: `0x1400edefb`
- name: `VsmmVaGpaRangepBackgroundDecommitWorker`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000f96c`
- `0x14002e080`
- `0x14002eb60`
- `0x140031820`
- `0x1400edde0`
- `0x1400edf10`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400ededd`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400ededd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ede31`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ede31`

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
        if ( (*(_DWORD *)(v8 + 20) & 0x8000) != 0 )
        {
          VsmmGpaRangeListReleaseReadOnly(v5, v14);
          VsmmVaGpaRangepBackgroundDecommitCandidateRanges(v12);
          v5 = VsmmGpaRangeListAcquireReadOnly(a1, &v14);
        }
        v10 = v12[34];
        LOBYTE(v9) = 1;
        VsmmGpaRangeRelease(v8, v12, v9);
        v6 = v10 + 1;
      }
      VsmmGpaRangeListReleaseReadOnly(v5, v14);
      goto LABEL_2;
    }
  }
}

```

## disassembly

```asm
0x1400edde0  mov     [rsp+arg_10], rbx
0x1400edde5  push    rbp
0x1400edde6  push    rsi
0x1400edde7  push    rdi
0x1400edde8  push    r14
0x1400eddea  push    r15
0x1400eddec  sub     rsp, 30h
0x1400eddf0  mov     r14, rcx
0x1400eddf3  mov     [rsp+58h+arg_0], 0
0x1400eddfb  mov     [rsp+58h+arg_8], 0
0x1400ede04  xor     ebx, ebx
0x1400ede06  test    bl, 2
0x1400ede09  jz      short loc_1400EDE0F
0x1400ede0b  xor     eax, eax
0x1400ede0d  jmp     short loc_1400EDE1D
0x1400ede0f  mov     [rsp+58h+arg_8], 0FFFFFFFFEE1E5D00h
0x1400ede18  lea     rax, [rsp+58h+arg_8]
0x1400ede1d  xor     r9d, r9d; Alertable
0x1400ede20  mov     [rsp+58h+Timeout], rax; Timeout
0x1400ede25  xor     r8d, r8d; WaitMode
0x1400ede28  lea     rcx, [r14+22E0h]; Object
0x1400ede2f  xor     edx, edx; WaitReason
0x1400ede31  call    cs:__imp_KeWaitForSingleObject
0x1400ede38  nop     dword ptr [rax+rax+00h]
0x1400ede3d  mov     ebx, [r14+22F8h]
0x1400ede44  test    bl, 1
0x1400ede47  jnz     loc_1400EDEDB
0x1400ede4d  cmp     eax, 102h
0x1400ede52  jz      short loc_1400EDE59
0x1400ede54  test    bl, 2
0x1400ede57  jz      short loc_1400EDE0F
0x1400ede59  lea     rdx, [rsp+58h+arg_0]
0x1400ede5e  mov     rcx, r14
0x1400ede61  call    VsmmGpaRangeListAcquireReadOnly
0x1400ede66  mov     rbp, rax
0x1400ede69  xor     edx, edx
0x1400ede6b  mov     rcx, rax
0x1400ede6e  jmp     short loc_1400EDEBD
0x1400ede70  mov     rcx, [rsi+180h]
0x1400ede77  test    dword ptr [rcx+14h], 8000h
0x1400ede7e  jz      short loc_1400EDEA4
0x1400ede80  mov     edx, [rsp+58h+arg_0]
0x1400ede84  mov     rcx, rbp
0x1400ede87  call    VsmmGpaRangeListReleaseReadOnly
0x1400ede8c  mov     rcx, rsi
0x1400ede8f  call    VsmmVaGpaRangepBackgroundDecommitCandidateRanges
0x1400ede94  lea     rdx, [rsp+58h+arg_0]
0x1400ede99  mov     rcx, r14
0x1400ede9c  call    VsmmGpaRangeListAcquireReadOnly
0x1400edea1  mov     rbp, rax
0x1400edea4  mov     rdi, [rsi+110h]
0x1400edeab  mov     r8b, 1
0x1400edeae  mov     rdx, rsi
0x1400edeb1  call    VsmmGpaRangeRelease
0x1400edeb6  lea     rdx, [rdi+1]
0x1400edeba  mov     rcx, rbp
0x1400edebd  call    VsmmGpaRangeLookupLowerBoundPrimary
0x1400edec2  mov     rsi, rax
0x1400edec5  test    rax, rax
0x1400edec8  jnz     short loc_1400EDE70
0x1400edeca  mov     edx, [rsp+58h+arg_0]
0x1400edece  mov     rcx, rbp
0x1400eded1  call    VsmmGpaRangeListReleaseReadOnly
0x1400eded6  jmp     loc_1400EDE06
0x1400ededb  xor     ecx, ecx; ExitStatus
0x1400ededd  call    cs:__imp_PsTerminateSystemThread
0x1400edee4  nop     dword ptr [rax+rax+00h]
0x1400edee9  mov     rbx, [rsp+58h+arg_10]
0x1400edeee  add     rsp, 30h
0x1400edef2  pop     r15
0x1400edef4  pop     r14
0x1400edef6  pop     rdi
0x1400edef7  pop     rsi
0x1400edef8  pop     rbp
0x1400edef9  retn
```
