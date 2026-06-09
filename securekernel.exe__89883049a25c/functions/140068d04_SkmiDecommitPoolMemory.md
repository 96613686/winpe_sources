# SkmiDecommitPoolMemory

- ea: `0x140068d04`
- end: `0x14006924b`
- name: `SkmiDecommitPoolMemory`
- size: `1351`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14006962c`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140003780`
- `0x14000b980`
- `0x140010b90`
- `0x1400130a0`
- `0x140020360`
- `0x140020424`
- `0x140024724`
- `0x140024fac`
- `0x14002b534`
- `0x140068d04`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiDecommitPoolMemory(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  __int64 v5; // r13
  unsigned __int64 v6; // r14
  _QWORD *v7; // rbp
  __int64 v8; // r12
  __int64 *v9; // rsi
  __int64 v10; // rdi
  char v11; // bl
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rsi
  unsigned __int64 v17; // rbx
  __int64 PteTrace; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned __int64 v21; // r10
  __int64 v22; // r13
  PVOID *v23; // rbp
  PVOID StackBase; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // r13
  PVOID *v32; // rbp
  PVOID v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rbp
  PVOID *v40; // rbx
  PVOID v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rcx
  _QWORD *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 BugCheckParameter3; // [rsp+30h] [rbp-178h]
  __int64 v50; // [rsp+38h] [rbp-170h]
  unsigned __int64 v51; // [rsp+40h] [rbp-168h]
  _BYTE v52[256]; // [rsp+50h] [rbp-158h] BYREF
  unsigned int v53; // [rsp+150h] [rbp-58h]
  char v54; // [rsp+154h] [rbp-54h]
  char v55; // [rsp+155h] [rbp-53h]
  _UNKNOWN *retaddr; // [rsp+1A8h] [rbp+0h]
  char v58; // [rsp+1B8h] [rbp+10h]
  ULONG BackTraceHash; // [rsp+1C0h] [rbp+18h] BYREF
  _QWORD *v60; // [rsp+1C8h] [rbp+20h]

  v5 = a1;
  memset_0(v52, 0, 0x108u);
  v6 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
  v7 = (_QWORD *)(v5 + 56);
  BugCheckParameter3 = 0;
  v8 = 0;
  v60 = (_QWORD *)(v5 + 56);
  v51 = v6 + 8 * ((a3 >> 12) - 1);
  if ( (*(_DWORD *)(v5 + 4) & 2) != 0 )
  {
    v9 = (__int64 *)((((a2 + *v7) >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL);
    v50 = 8;
    v10 = 0x4000000000000000LL;
  }
  else
  {
    v10 = 0;
    v50 = 0;
    v9 = 0;
    v60 = (_QWORD *)(v5 + 56);
  }
  v11 = -1;
  v55 = -1;
  v58 = SkAcquireSpinLockExclusive(v5);
  if ( v6 <= v51 )
  {
    while ( 1 )
    {
      v8 &= -(__int64)((v6 & 0xFF8) != 0);
      if ( v8 )
        goto LABEL_11;
      v14 = 0xFFFFF68000000000uLL;
      v12 = 0x7FFFFFFFF8LL;
      v8 = ((v6 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
      if ( (*(_QWORD *)v8 & 1) != 0 )
        break;
      v6 = (v6 + 4096) & 0xFFFFFFFFFFFFF000uLL;
      a2 = (__int64)(v6 << 25) >> 16;
      if ( v9 )
      {
        v16 = ((a2 + *v7) >> 9) & 0x7FFFFFFFF8LL;
        goto LABEL_9;
      }
LABEL_49:
      v15 = 0xFFFFFFFFFFLL;
      if ( v6 > v51 )
      {
        v11 = v55;
        v5 = a1;
        goto LABEL_51;
      }
    }
    BugCheckParameter3 = (*(_QWORD *)v8 >> 12) & 0xFFFFFFFFFFLL;
LABEL_11:
    v17 = *(_QWORD *)v6;
    if ( (*(_QWORD *)v6 & 1) == 0 )
      goto LABEL_48;
    PteTrace = SkmiGetPteTrace(0, v6, 0, 0, *(_QWORD *)v6);
    v22 = PteTrace;
    if ( PteTrace )
    {
      v23 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, (unsigned int)(v20 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        StackBase = KeGetPcr()->NtTib.StackBase;
        if ( StackBase )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v23, &BackTraceHash) )
          {
            *(_QWORD *)(v22 + 40) = retaddr;
            *v23 = (PVOID)SkmiGetInstructionPointer(v26, v25);
          }
        }
      }
      v21 = 0xFFFFF6FB7DBED800uLL;
    }
    if ( v6 >= 0xFFFFF6FB7DBED000uLL && v6 < v21 )
    {
      v27 = KeGetPcr()->NtTib.StackBase;
      v28 = v27 ? v27[10] : 0LL;
      v29 = *(_QWORD *)(v28 + 232);
      if ( v29 )
        *(_QWORD *)(v29 + 8 * (((__int64)v6 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)v6 = 0;
    SkmiBatchFlushSingleTb(a2, v52, v19, v20);
    if ( v9 )
    {
      v30 = SkmiGetPteTrace(0, (_DWORD)v9, 0, v10, *v9);
      v31 = v30;
      if ( v30 )
      {
        v32 = (PVOID *)(v30 + 32);
        memset_0((void *)(v30 + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          v33 = KeGetPcr()->NtTib.StackBase;
          if ( v33 )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)v33, 8u, v32, &BackTraceHash) )
            {
              *(_QWORD *)(v31 + 40) = retaddr;
              *v32 = (PVOID)SkmiGetInstructionPointer(v35, v34);
            }
          }
        }
      }
      *v9 = v10;
    }
    SkmiFreePhysicalPage(0, (v17 >> 12) & 0xFFFFFFFFFFLL);
    if ( !(unsigned int)SkmiDecrementPageReferenceCount(BugCheckParameter3) )
    {
      v7 = v60;
LABEL_48:
      a2 += 4096LL;
      v6 += 8LL;
      v9 = (__int64 *)((char *)v9 + v50);
      goto LABEL_49;
    }
    v36 = SkmiGetPteTrace(0, v8, 0, 0, *(_QWORD *)v8);
    v39 = v36;
    if ( v36 )
    {
      v40 = (PVOID *)(v36 + 32);
      memset_0((void *)(v36 + 32), 0, (unsigned int)(v38 + 64));
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        v41 = KeGetPcr()->NtTib.StackBase;
        if ( v41 )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)v41, 8u, v40, &BackTraceHash) )
          {
            *(_QWORD *)(v39 + 40) = retaddr;
            *v40 = (PVOID)SkmiGetInstructionPointer(v43, v42);
          }
        }
      }
    }
    if ( (unsigned __int64)v8 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v8 < 0xFFFFF6FB7DBED800uLL )
    {
      v44 = KeGetPcr()->NtTib.StackBase;
      v45 = v44 ? v44[10] : 0LL;
      v46 = *(_QWORD *)(v45 + 232);
      if ( v46 )
        *(_QWORD *)(v46 + 8 * ((v8 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)v8 = 0;
    SkmiBatchFlushSingleTb(v8 << 25 >> 16, v52, v37, v38);
    SkmiFreePhysicalPage(0, BugCheckParameter3);
    v7 = v60;
    v6 = (v6 + 4096) & 0xFFFFFFFFFFFFF000uLL;
    a2 = (__int64)(v6 << 25) >> 16;
    if ( !v9 )
      goto LABEL_49;
    v16 = ((a2 + *v60) >> 9) & 0x7FFFFFFFF8LL;
LABEL_9:
    v9 = (__int64 *)(v16 - 0xA0000000000LL);
    goto LABEL_49;
  }
LABEL_51:
  if ( v9 )
  {
    LOBYTE(v47) = SkmiAcquireNteAssertionLock(v13, v12, v14, v15);
    SkmiReleaseNteAssertionLock(v47);
  }
  if ( v54 )
  {
    LOBYTE(v13) = v11;
    SkeFlushEntireTb(v13, 0);
  }
  else if ( v53 )
  {
    LOBYTE(v13) = v11;
    SkeFlushRangeListTb(v13, 0, v53, v52);
  }
  LOBYTE(v12) = v58;
  return SkReleaseSpinLockExclusive(v5, v12);
}

```

## disassembly

```asm
0x140068d04  mov     [rsp+arg_0], rcx
0x140068d09  push    rbx
0x140068d0a  push    rbp
0x140068d0b  push    rsi
0x140068d0c  push    rdi
0x140068d0d  push    r12
0x140068d0f  push    r13
0x140068d11  push    r14
0x140068d13  push    r15
0x140068d15  sub     rsp, 168h
0x140068d1c  mov     rbx, r8
0x140068d1f  mov     r15, rdx
0x140068d22  mov     r13, rcx
0x140068d25  xor     edx, edx; Val
0x140068d27  mov     r8d, 108h; Size
0x140068d2d  lea     rcx, [rsp+1A8h+var_158]; void *
0x140068d32  call    memset_0
0x140068d37  mov     r14, r15
0x140068d3a  mov     rax, 0FFFFF68000000000h
0x140068d44  shr     r14, 9
0x140068d48  mov     rdx, 7FFFFFFFF8h
0x140068d52  and     r14, rdx
0x140068d55  mov     rax, rax
0x140068d58  add     r14, rax
0x140068d5b  shr     rbx, 0Ch
0x140068d5f  xor     ecx, ecx
0x140068d61  mov     r8, 0FFFFF60000000000h
0x140068d6b  lea     rbp, [r13+38h]
0x140068d6f  mov     [rsp+1A8h+BugCheckParameter3], rcx
0x140068d74  mov     r12d, ecx
0x140068d77  mov     [rsp+1A8h+arg_18], rbp
0x140068d7f  lea     rax, [rbx-1]
0x140068d83  lea     rax, [r14+rax*8]
0x140068d87  mov     [rsp+1A8h+var_168], rax
0x140068d8c  mov     eax, [r13+4]
0x140068d90  test    al, 2
0x140068d92  jz      short loc_140068DBD
0x140068d94  mov     rsi, [rbp+0]
0x140068d98  add     rsi, r15
0x140068d9b  shr     rsi, 9
0x140068d9f  and     rsi, rdx
0x140068da2  mov     rax, r8
0x140068da5  add     rsi, rax
0x140068da8  mov     [rsp+1A8h+var_170], 8
0x140068db1  mov     rdi, 4000000000000000h
0x140068dbb  jmp     short loc_140068DD0
0x140068dbd  mov     rdi, rcx
0x140068dc0  mov     [rsp+1A8h+var_170], rcx
0x140068dc5  mov     rsi, rcx
0x140068dc8  mov     [rsp+1A8h+arg_18], rbp
0x140068dd0  mov     bl, 0FFh
0x140068dd2  mov     rcx, r13
0x140068dd5  mov     [rsp+1A8h+var_53], bl
0x140068ddc  call    SkAcquireSpinLockExclusive
0x140068de1  mov     [rsp+1A8h+arg_8], al
0x140068de8  cmp     r14, [rsp+1A8h+var_168]
0x140068ded  ja      loc_1400691E4
0x140068df3  mov     r9, 0FFFFFFFFFFh
0x140068dfd  mov     r10, 0FFFFF6FB7DBED800h
0x140068e07  mov     rax, r14
0x140068e0a  and     eax, 0FF8h
0x140068e0f  neg     rax
0x140068e12  sbb     rax, rax
0x140068e15  and     r12, rax
0x140068e18  jnz     loc_140068EA8
0x140068e1e  mov     r12, r14
0x140068e21  mov     r8, 0FFFFF68000000000h
0x140068e2b  shr     r12, 9
0x140068e2f  mov     rdx, 7FFFFFFFF8h
0x140068e39  and     r12, rdx
0x140068e3c  mov     rax, r8
0x140068e3f  add     r12, rax
0x140068e42  mov     rax, [r12]
0x140068e46  test    al, 1
0x140068e48  jnz     short loc_140068E99
0x140068e4a  lea     r15, [r14+1000h]
0x140068e51  and     r15, 0FFFFFFFFFFFFF000h
0x140068e58  mov     r14, r15
0x140068e5b  shl     r15, 19h
0x140068e5f  mov     rax, r8
0x140068e62  shl     rax, 19h
0x140068e66  sub     r15, rax
0x140068e69  sar     r15, 10h
0x140068e6d  test    rsi, rsi
0x140068e70  jz      loc_1400691B6
0x140068e76  mov     rsi, [rbp+0]
0x140068e7a  add     rsi, r15
0x140068e7d  shr     rsi, 9
0x140068e81  and     rsi, rdx
0x140068e84  mov     rax, 0FFFFF60000000000h
0x140068e8e  mov     rax, rax
0x140068e91  add     rsi, rax
0x140068e94  jmp     loc_1400691B6
0x140068e99  mov     r13, rax
0x140068e9c  shr     r13, 0Ch
0x140068ea0  and     r13, r9
0x140068ea3  mov     [rsp+1A8h+BugCheckParameter3], r13
0x140068ea8  mov     rbx, [r14]
0x140068eab  test    bl, 1
0x140068eae  jz      loc_1400691A6
0x140068eb4  mov     rax, [r14]
0x140068eb7  xor     r9d, r9d
0x140068eba  xor     r8d, r8d
0x140068ebd  mov     [rsp+1A8h+var_188], rax
0x140068ec2  mov     rdx, r14
0x140068ec5  xor     ecx, ecx
0x140068ec7  call    SkmiGetPteTrace
0x140068ecc  mov     r13, rax
0x140068ecf  test    rax, rax
0x140068ed2  jz      short loc_140068F39
0x140068ed4  lea     rbp, [rax+20h]
0x140068ed8  xor     edx, edx; Val
0x140068eda  mov     rcx, rbp; void *
0x140068edd  lea     r8d, [r9+40h]; Size
0x140068ee1  call    memset_0
0x140068ee6  test    cs:SkmiFlags, 400000h
0x140068ef0  jz      short loc_140068F2F
0x140068ef2  mov     rcx, gs:8; FramesToSkip
0x140068efb  test    rcx, rcx
0x140068efe  jz      short loc_140068F2F
0x140068f00  lea     r9, [rsp+1A8h+BackTraceHash]; BackTraceHash
0x140068f08  mov     r8, rbp; BackTrace
0x140068f0b  mov     edx, 8; FramesToCapture
0x140068f10  call    RtlCaptureStackBackTrace
0x140068f15  test    ax, ax
0x140068f18  jnz     short loc_140068F2F
0x140068f1a  mov     rax, [rsp+1A8h]
0x140068f22  mov     [r13+28h], rax
0x140068f26  call    SkmiGetInstructionPointer
0x140068f2b  mov     [rbp+0], rax
0x140068f2f  mov     r10, 0FFFFF6FB7DBED800h
0x140068f39  mov     rax, 0FFFFF6FB7DBED000h
0x140068f43  mov     rax, rax
0x140068f46  cmp     r14, rax
0x140068f49  jb      short loc_140068F89
0x140068f4b  mov     rax, r10
0x140068f4e  cmp     r14, rax
0x140068f51  jnb     short loc_140068F89
0x140068f53  mov     rax, gs:8
0x140068f5c  test    rax, rax
0x140068f5f  jz      short loc_140068F67
0x140068f61  mov     rcx, [rax+50h]
0x140068f65  jmp     short loc_140068F69
0x140068f67  xor     ecx, ecx
0x140068f69  mov     rdx, [rcx+0E8h]
0x140068f70  test    rdx, rdx
0x140068f73  jz      short loc_140068F89
0x140068f75  mov     rax, r14
0x140068f78  sar     rax, 3
0x140068f7c  and     eax, 1FFh
0x140068f81  mov     qword ptr [rdx+rax*8], 0
0x140068f89  lea     rdx, [rsp+1A8h+var_158]
0x140068f8e  mov     qword ptr [r14], 0
0x140068f95  mov     rcx, r15
0x140068f98  call    SkmiBatchFlushSingleTb
0x140068f9d  test    rsi, rsi
0x140068fa0  jz      short loc_140069020
0x140068fa2  mov     rax, [rsi]
0x140068fa5  mov     r9, rdi
0x140068fa8  xor     r8d, r8d
0x140068fab  mov     [rsp+1A8h+var_188], rax
0x140068fb0  mov     rdx, rsi
0x140068fb3  xor     ecx, ecx
0x140068fb5  call    SkmiGetPteTrace
0x140068fba  mov     r13, rax
0x140068fbd  test    rax, rax
0x140068fc0  jz      short loc_14006901D
0x140068fc2  xor     edx, edx; Val
0x140068fc4  lea     rbp, [rax+20h]
0x140068fc8  mov     rcx, rbp; void *
0x140068fcb  lea     r8d, [rdx+40h]; Size
0x140068fcf  call    memset_0
0x140068fd4  test    cs:SkmiFlags, 400000h
0x140068fde  jz      short loc_14006901D
0x140068fe0  mov     rcx, gs:8; FramesToSkip
0x140068fe9  test    rcx, rcx
0x140068fec  jz      short loc_14006901D
0x140068fee  lea     r9, [rsp+1A8h+BackTraceHash]; BackTraceHash
0x140068ff6  mov     r8, rbp; BackTrace
0x140068ff9  mov     edx, 8; FramesToCapture
0x140068ffe  call    RtlCaptureStackBackTrace
0x140069003  test    ax, ax
0x140069006  jnz     short loc_14006901D
0x140069008  mov     rax, [rsp+1A8h]
0x140069010  mov     [r13+28h], rax
0x140069014  call    SkmiGetInstructionPointer
0x140069019  mov     [rbp+0], rax
0x14006901d  mov     [rsi], rdi
0x140069020  shr     rbx, 0Ch
0x140069024  mov     rdx, 0FFFFFFFFFFh
0x14006902e  and     rdx, rbx
0x140069031  xor     ecx, ecx
0x140069033  call    SkmiFreePhysicalPage
0x140069038  mov     r13, [rsp+1A8h+BugCheckParameter3]
0x14006903d  mov     rcx, r13; BugCheckParameter3
0x140069040  call    SkmiDecrementPageReferenceCount
0x140069045  test    eax, eax
0x140069047  jz      loc_14006919E
0x14006904d  mov     rax, [r12]
0x140069051  xor     r9d, r9d
0x140069054  xor     r8d, r8d
0x140069057  mov     [rsp+1A8h+var_188], rax
0x14006905c  mov     rdx, r12
0x14006905f  xor     ecx, ecx
0x140069061  call    SkmiGetPteTrace
0x140069066  xor     r15d, r15d
0x140069069  mov     rbp, rax
0x14006906c  test    rax, rax
0x14006906f  jz      short loc_1400690CA
0x140069071  lea     rbx, [rax+20h]
0x140069075  xor     edx, edx; Val
0x140069077  mov     rcx, rbx; void *
0x14006907a  lea     r8d, [r9+40h]; Size
0x14006907e  call    memset_0
0x140069083  test    cs:SkmiFlags, 400000h
0x14006908d  jz      short loc_1400690CA
0x14006908f  mov     rcx, gs:8; FramesToSkip
0x140069098  test    rcx, rcx
0x14006909b  jz      short loc_1400690CA
0x14006909d  lea     r9, [rsp+1A8h+BackTraceHash]; BackTraceHash
0x1400690a5  mov     r8, rbx; BackTrace
0x1400690a8  lea     edx, [r15+8]; FramesToCapture
0x1400690ac  call    RtlCaptureStackBackTrace
0x1400690b1  test    ax, ax
0x1400690b4  jnz     short loc_1400690CA
0x1400690b6  mov     rax, [rsp+1A8h]
0x1400690be  mov     [rbp+28h], rax
0x1400690c2  call    SkmiGetInstructionPointer
0x1400690c7  mov     [rbx], rax
0x1400690ca  mov     rax, 0FFFFF6FB7DBED000h
0x1400690d4  mov     rax, rax
0x1400690d7  cmp     r12, rax
0x1400690da  jb      short loc_140069121
0x1400690dc  mov     rax, 0FFFFF6FB7DBED800h
0x1400690e6  mov     rax, rax
0x1400690e9  cmp     r12, rax
0x1400690ec  jnb     short loc_140069121
0x1400690ee  mov     rax, gs:8
0x1400690f7  test    rax, rax
0x1400690fa  jz      short loc_140069102
0x1400690fc  mov     rcx, [rax+50h]
0x140069100  jmp     short loc_140069105
0x140069102  mov     rcx, r15
0x140069105  mov     rdx, [rcx+0E8h]
0x14006910c  test    rdx, rdx
0x14006910f  jz      short loc_140069121
0x140069111  mov     rax, r12
0x140069114  sar     rax, 3
0x140069118  and     eax, 1FFh
0x14006911d  mov     [rdx+rax*8], r15
0x140069121  mov     [r12], r15
0x140069125  mov     rax, 0FFFFF68000000000h
0x14006912f  mov     rbx, rax
0x140069132  mov     rcx, r12
0x140069135  shl     rbx, 19h
0x140069139  shl     rcx, 19h
0x14006913d  lea     rdx, [rsp+1A8h+var_158]
0x140069142  sub     rcx, rbx
0x140069145  sar     rcx, 10h
0x140069149  call    SkmiBatchFlushSingleTb
0x14006914e  xor     ecx, ecx
0x140069150  mov     rdx, r13
0x140069153  call    SkmiFreePhysicalPage
0x140069158  mov     rbp, [rsp+1A8h+arg_18]
0x140069160  lea     r15, [r14+1000h]
0x140069167  and     r15, 0FFFFFFFFFFFFF000h
0x14006916e  mov     r14, r15
0x140069171  shl     r15, 19h
0x140069175  sub     r15, rbx
0x140069178  sar     r15, 10h
0x14006917c  test    rsi, rsi
0x14006917f  jz      short loc_1400691B6
0x140069181  mov     rsi, [rbp+0]
0x140069185  mov     rax, 7FFFFFFFF8h
0x14006918f  add     rsi, r15
0x140069192  shr     rsi, 9
0x140069196  and     rsi, rax
0x140069199  jmp     loc_140068E84
0x14006919e  mov     rbp, [rsp+1A8h+arg_18]
0x1400691a6  add     r15, 1000h
0x1400691ad  add     r14, 8
0x1400691b1  add     rsi, [rsp+1A8h+var_170]
0x1400691b6  mov     r9, 0FFFFFFFFFFh
0x1400691c0  mov     r10, 0FFFFF6FB7DBED800h
0x1400691ca  cmp     r14, [rsp+1A8h+var_168]
0x1400691cf  jbe     loc_140068E07
0x1400691d5  mov     bl, [rsp+1A8h+var_53]
0x1400691dc  mov     r13, [rsp+1A8h+arg_0]
0x1400691e4  xor     edi, edi
0x1400691e6  test    rsi, rsi
0x1400691e9  jz      short loc_1400691F7
0x1400691eb  call    SkmiAcquireNteAssertionLock
0x1400691f0  mov     cl, al
0x1400691f2  call    SkmiReleaseNteAssertionLock
0x1400691f7  cmp     [rsp+1A8h+var_54], dil
0x1400691ff  jz      short loc_14006920C
0x140069201  xor     edx, edx
0x140069203  mov     cl, bl
0x140069205  call    SkeFlushEntireTb
0x14006920a  jmp     short loc_140069227
  ... truncated ...
```
