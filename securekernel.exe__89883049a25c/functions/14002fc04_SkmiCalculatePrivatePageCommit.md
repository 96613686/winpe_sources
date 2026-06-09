# SkmiCalculatePrivatePageCommit

- ea: `0x14002fc04`
- end: `0x14002fe82`
- name: `SkmiCalculatePrivatePageCommit`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400661e4`

## callees

- `0x140003780`
- `0x140008118`
- `0x14000e810`
- `0x14000ff70`
- `0x14002b534`
- `0x14002fc04`
- `0x140030f10`
- `0x1400345b4`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCalculatePrivatePageCommit(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  unsigned int *v4; // rdi
  __int64 v5; // r14
  __int64 v6; // r12
  __int64 v7; // r15
  __int64 NextSetBit; // rbp
  unsigned __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rbx
  char v12; // r14
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdi
  __int64 PteTrace; // rax
  __int64 v17; // r10
  __int64 v18; // r15
  PVOID *v19; // r14
  ULONG v20; // ecx
  USHORT v21; // ax
  __int64 v22; // rcx
  _QWORD *StackBase; // rax
  __int64 v24; // rcx
  int v25; // ecx
  ULONG BackTraceHash[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v28; // [rsp+38h] [rbp-60h]
  unsigned __int64 v29; // [rsp+40h] [rbp-58h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+0h]
  char v34; // [rsp+B8h] [rbp+20h]

  v3 = a1;
  v4 = (unsigned int *)a2;
  v5 = a3;
  v6 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 56) + 8LL);
  v28 = v7;
  NextSetBit = SkmiFindNextSetBit(a3, 0);
  v9 = 8 * ((v4[6] | ((unsigned __int64)v4[8] << 32)) & 0xFFFFFFFFFLL) - 0x98000000000LL;
  v29 = v9;
  while ( NextSetBit != -1 )
  {
    v10 = v9 + 8 * NextSetBit;
    v11 = *(_QWORD *)v10;
    if ( !*(_QWORD *)v10 || (v11 & 3) != 0 )
      goto LABEL_22;
    v34 = SkAcquireSpinLockShared(v3 + 8);
    v12 = v34;
    v13 = SkmiLockFaultChain(v10);
    v11 = v13;
    if ( v13 )
    {
      *(_QWORD *)BackTraceHash = v13;
      v15 = v13;
      SKMI_UNSWIZZLE_INVALID_PTE(BackTraceHash);
      v11 = *(_QWORD *)((*(__int64 *)BackTraceHash >> 16) + SkmiState + 16);
      PteTrace = SkmiGetPteTrace(0, v10, 0, v15, *(_QWORD *)v10);
      v18 = PteTrace;
      if ( PteTrace )
      {
        v19 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, (unsigned int)(v17 + 64));
        v17 = 0;
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          if ( KeGetPcr()->NtTib.StackBase )
          {
            v21 = RtlCaptureStackBackTrace(v20, 8u, v19, BackTraceHash);
            v17 = 0;
            if ( !v21 )
            {
              *(_QWORD *)(v18 + 40) = retaddr;
              *v19 = (PVOID)SkmiGetInstructionPointer(v22, v14);
            }
          }
        }
        v12 = v34;
      }
      if ( (unsigned __int64)v10 >= 0xFFFFF6FB7DBED000uLL && (unsigned __int64)v10 < 0xFFFFF6FB7DBED800uLL )
      {
        StackBase = KeGetPcr()->NtTib.StackBase;
        v24 = StackBase ? StackBase[10] : v17;
        v14 = *(_QWORD *)(v24 + 232);
        if ( v14 )
        {
          v25 = SkiKvaShadowMode;
          *(_QWORD *)(v14 + 8 * ((v10 >> 3) & 0x1FF)) = v15;
          if ( v25 != 2 && (v15 & 1) != 0 )
            v15 |= 0x8000000000000000uLL;
        }
      }
      v7 = v28;
      *(_QWORD *)v10 = v15;
      v4 = (unsigned int *)a2;
    }
    LOBYTE(v14) = v12;
    RtlpReleasePropStoreLockShared(v3 + 8, v14);
    v5 = a3;
    if ( v11 )
    {
LABEL_22:
      if ( (v11 & 1) != 0 )
      {
        if ( (v11 & 0x80000000000000LL) != 0 && (v11 & 0x200) == 0 )
        {
LABEL_30:
          if ( (v4[17] & 1) == 0 || (*(_DWORD *)(v7 + 8 * NextSetBit) & 0x400LL) == 0 )
            ++v6;
        }
      }
      else if ( (v11 & 0x800) == 0 && v11 && (v11 & 0x400) != 0 && (v11 & 0xA0) != 0xA0 )
      {
        goto LABEL_30;
      }
      NextSetBit = SkmiFindNextSetBit(v5, NextSetBit + 1);
    }
    v9 = v29;
    v3 = a1;
  }
  return v6;
}

```

## disassembly

```asm
0x14002fc04  mov     [rsp+arg_10], r8
0x14002fc09  mov     [rsp+arg_8], rdx
0x14002fc0e  mov     [rsp+arg_0], rcx
0x14002fc13  push    rbx
0x14002fc14  push    rbp
0x14002fc15  push    rsi
0x14002fc16  push    rdi
0x14002fc17  push    r12
0x14002fc19  push    r13
0x14002fc1b  push    r14
0x14002fc1d  push    r15
0x14002fc1f  sub     rsp, 58h
0x14002fc23  mov     rax, [rdx+38h]
0x14002fc27  mov     r13, rcx
0x14002fc2a  mov     rdi, rdx
0x14002fc2d  mov     rcx, r8
0x14002fc30  xor     edx, edx
0x14002fc32  mov     r14, r8
0x14002fc35  xor     r12d, r12d
0x14002fc38  mov     r15, [rax+8]
0x14002fc3c  mov     [rsp+98h+var_60], r15
0x14002fc41  call    SkmiFindNextSetBit
0x14002fc46  mov     r9d, [rdi+20h]
0x14002fc4a  mov     rbp, rax
0x14002fc4d  mov     eax, [rdi+18h]
0x14002fc50  shl     r9, 20h
0x14002fc54  or      r9, rax
0x14002fc57  mov     rax, 0FFFFFFFFFh
0x14002fc61  and     r9, rax
0x14002fc64  mov     rax, 0FFFFF68000000000h
0x14002fc6e  lea     rax, [rax+r9*8]
0x14002fc72  mov     [rsp+98h+var_58], rax
0x14002fc77  jmp     loc_14002FE63
0x14002fc7c  lea     rsi, [rax+rbp*8]
0x14002fc80  mov     rbx, [rsi]
0x14002fc83  test    rbx, rbx
0x14002fc86  jz      loc_14002FE02
0x14002fc8c  test    bl, 3
0x14002fc8f  jnz     loc_14002FE02
0x14002fc95  lea     rcx, [r13+8]
0x14002fc99  call    SkAcquireSpinLockShared
0x14002fc9e  mov     rcx, rsi
0x14002fca1  mov     [rsp+98h+arg_18], al
0x14002fca8  mov     r14b, al
0x14002fcab  call    SkmiLockFaultChain
0x14002fcb0  xor     r10d, r10d
0x14002fcb3  mov     rbx, rax
0x14002fcb6  test    rax, rax
0x14002fcb9  jz      loc_14002FDE9
0x14002fcbf  lea     rcx, [rsp+98h+BackTraceHash]
0x14002fcc4  mov     qword ptr [rsp+98h+BackTraceHash], rax
0x14002fcc9  mov     rdi, rax
0x14002fccc  call    SKMI_UNSWIZZLE_INVALID_PTE
0x14002fcd1  mov     rbx, cs:SkmiState
0x14002fcd8  mov     r9, rdi
0x14002fcdb  mov     rax, [rsi]
0x14002fcde  xor     r8d, r8d
0x14002fce1  mov     rcx, qword ptr [rsp+98h+BackTraceHash]
0x14002fce6  mov     rdx, rsi
0x14002fce9  sar     rcx, 10h
0x14002fced  mov     [rsp+98h+var_78], rax
0x14002fcf2  mov     rbx, [rcx+rbx+10h]
0x14002fcf7  xor     ecx, ecx
0x14002fcf9  call    SkmiGetPteTrace
0x14002fcfe  mov     r15, rax
0x14002fd01  test    rax, rax
0x14002fd04  jz      short loc_14002FD6A
0x14002fd06  lea     r14, [rax+20h]
0x14002fd0a  xor     edx, edx; Val
0x14002fd0c  mov     rcx, r14; void *
0x14002fd0f  lea     r8d, [r10+40h]; Size
0x14002fd13  call    memset_0
0x14002fd18  xor     r10d, r10d
0x14002fd1b  test    cs:SkmiFlags, 400000h
0x14002fd25  jz      short loc_14002FD62
0x14002fd27  mov     rax, gs:8
0x14002fd30  test    rax, rax
0x14002fd33  jz      short loc_14002FD62
0x14002fd35  lea     r9, [rsp+98h+BackTraceHash]; BackTraceHash
0x14002fd3a  mov     r8, r14; BackTrace
0x14002fd3d  lea     edx, [r10+8]; FramesToCapture
0x14002fd41  call    RtlCaptureStackBackTrace
0x14002fd46  xor     r10d, r10d
0x14002fd49  test    ax, ax
0x14002fd4c  jnz     short loc_14002FD62
0x14002fd4e  mov     rax, [rsp+98h]
0x14002fd56  mov     [r15+28h], rax
0x14002fd5a  call    SkmiGetInstructionPointer
0x14002fd5f  mov     [r14], rax
0x14002fd62  mov     r14b, [rsp+98h+arg_18]
0x14002fd6a  mov     rax, 0FFFFF6FB7DBED000h
0x14002fd74  cmp     rsi, rax
0x14002fd77  jb      short loc_14002FDD9
0x14002fd79  mov     rax, 0FFFFF6FB7DBED800h
0x14002fd83  cmp     rsi, rax
0x14002fd86  jnb     short loc_14002FDD9
0x14002fd88  mov     rax, gs:8
0x14002fd91  test    rax, rax
0x14002fd94  jz      short loc_14002FD9C
0x14002fd96  mov     rcx, [rax+50h]
0x14002fd9a  jmp     short loc_14002FD9F
0x14002fd9c  mov     rcx, r10
0x14002fd9f  mov     rdx, [rcx+0E8h]
0x14002fda6  test    rdx, rdx
0x14002fda9  jz      short loc_14002FDD9
0x14002fdab  mov     ecx, cs:SkiKvaShadowMode
0x14002fdb1  mov     rax, rsi
0x14002fdb4  sar     rax, 3
0x14002fdb8  and     eax, 1FFh
0x14002fdbd  mov     [rdx+rax*8], rdi
0x14002fdc1  cmp     ecx, 2
0x14002fdc4  jz      short loc_14002FDD9
0x14002fdc6  test    dil, 1
0x14002fdca  jz      short loc_14002FDD9
0x14002fdcc  mov     rax, 8000000000000000h
0x14002fdd6  or      rdi, rax
0x14002fdd9  mov     r15, [rsp+98h+var_60]
0x14002fdde  mov     [rsi], rdi
0x14002fde1  mov     rdi, [rsp+98h+arg_8]
0x14002fde9  mov     dl, r14b
0x14002fdec  lea     rcx, [r13+8]
0x14002fdf0  call    RtlpReleasePropStoreLockShared
0x14002fdf5  mov     r14, [rsp+98h+arg_10]
0x14002fdfd  test    rbx, rbx
0x14002fe00  jz      short loc_14002FE56
0x14002fe02  test    bl, 1
0x14002fe05  jz      short loc_14002FE17
0x14002fe07  bt      rbx, 37h ; '7'
0x14002fe0c  jnb     short loc_14002FE47
0x14002fe0e  bt      rbx, 9
0x14002fe13  jb      short loc_14002FE47
0x14002fe15  jmp     short loc_14002FE32
0x14002fe17  bt      rbx, 0Bh
0x14002fe1c  jb      short loc_14002FE47
0x14002fe1e  test    rbx, rbx
0x14002fe21  jz      short loc_14002FE47
0x14002fe23  bt      rbx, 0Ah
0x14002fe28  jnb     short loc_14002FE47
0x14002fe2a  and     bl, 0A0h
0x14002fe2d  cmp     bl, 0A0h
0x14002fe30  jz      short loc_14002FE47
0x14002fe32  mov     eax, [rdi+44h]
0x14002fe35  test    al, 1
0x14002fe37  jz      short loc_14002FE44
0x14002fe39  mov     eax, [r15+rbp*8]
0x14002fe3d  bt      rax, 0Ah
0x14002fe42  jb      short loc_14002FE47
0x14002fe44  inc     r12
0x14002fe47  lea     rdx, [rbp+1]
0x14002fe4b  mov     rcx, r14
0x14002fe4e  call    SkmiFindNextSetBit
0x14002fe53  mov     rbp, rax
0x14002fe56  mov     rax, [rsp+98h+var_58]
0x14002fe5b  mov     r13, [rsp+98h+arg_0]
0x14002fe63  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14002fe67  jnz     loc_14002FC7C
0x14002fe6d  mov     rax, r12
0x14002fe70  add     rsp, 58h
0x14002fe74  pop     r15
0x14002fe76  pop     r14
0x14002fe78  pop     r13
0x14002fe7a  pop     r12
0x14002fe7c  pop     rdi
0x14002fe7d  pop     rsi
0x14002fe7e  pop     rbp
0x14002fe7f  pop     rbx
0x14002fe80  retn
```
