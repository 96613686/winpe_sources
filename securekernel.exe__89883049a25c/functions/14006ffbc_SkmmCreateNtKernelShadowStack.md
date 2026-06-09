# SkmmCreateNtKernelShadowStack

- ea: `0x14006ffbc`
- end: `0x140070646`
- name: `SkmmCreateNtKernelShadowStack`
- size: `1674`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x140003780`
- `0x140008ec4`
- `0x140009940`
- `0x14000c8d0`
- `0x14000e810`
- `0x14000ff70`
- `0x140011130`
- `0x140014c80`
- `0x140020360`
- `0x140020424`
- `0x140025024`
- `0x140029ff4`
- `0x14002b534`
- `0x140050ba4`
- `0x14006ffbc`
- `0x140076948`
- `0x140081290`
- `0x1400f04d0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCreateNtKernelShadowStack(
        unsigned __int64 a1,
        int a2,
        int a3,
        unsigned int a4,
        ULONG_PTR *a5,
        unsigned int a6,
        __int64 a7)
{
  unsigned __int64 v8; // r14
  __int64 result; // rax
  unsigned int v12; // r15d
  __int64 *v13; // r14
  __int64 PteTrace; // rax
  __int64 v15; // rdi
  PVOID *v16; // rbx
  ULONG v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // r13
  __int64 *v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdi
  PVOID *v25; // rbx
  PVOID StackBase; // rcx
  __int64 v27; // rcx
  unsigned __int64 v28; // rdi
  __int64 HyperspacePte; // rsi
  unsigned __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // r13
  PVOID *v34; // r14
  PVOID v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  int v41; // ecx
  __int64 v42; // rax
  int v43; // r9d
  __int64 v44; // r14
  PVOID *v45; // rbx
  PVOID v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  _QWORD *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  _QWORD *v52; // r14
  __int64 v53; // rax
  __int64 v54; // rsi
  PVOID *v55; // rbx
  PVOID v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rdx
  char v60; // [rsp+40h] [rbp-C0h]
  ULONG BackTraceHash[2]; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v62[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v63; // [rsp+58h] [rbp-A8h]
  __int64 *v64; // [rsp+60h] [rbp-A0h]
  _BYTE v65[256]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v66; // [rsp+170h] [rbp+70h]
  char v67; // [rsp+174h] [rbp+74h]
  char v68; // [rsp+175h] [rbp+75h]
  _UNKNOWN *retaddr; // [rsp+1B8h] [rbp+B8h]

  v8 = a4;
  memset_0(v65, 0, 0x108u);
  *(_QWORD *)v62 = 0;
  if ( (SkmiFlags & 0x80000) == 0 )
    return 3221225659LL;
  if ( !a3 )
    return 3221225485LL;
  if ( (a3 & 0xFFFFFFFC) != 0 )
    return 3221225485LL;
  if ( (unsigned int)__popcnt(v8) > 1 )
    return 3221225485LL;
  if ( (v8 & 0xFFFFFFF8) != 0 )
    return 3221225485LL;
  if ( a2 != 12288 )
    return 3221225485LL;
  v12 = a6;
  if ( a6 << 12 != 4096 )
    return 3221225485LL;
  result = SkmiReserveNar(a1, 12288, 0x40000, 2, 0, 0, (__int64)v62);
  if ( (int)result >= 0 )
  {
    v13 = (__int64 *)(((a1 >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL);
    v60 = SkAcquireSpinLockShared(&SkmiNteLock);
    PteTrace = SkmiGetPteTrace(0, (unsigned int)(a1 >> 9) & 0xFFFFFFF8, 0, 0, *v13);
    v15 = PteTrace;
    if ( PteTrace )
    {
      v16 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0
        && KeGetPcr()->NtTib.StackBase
        && !RtlCaptureStackBackTrace(v17, 8u, v16, BackTraceHash) )
      {
        *(_QWORD *)(v15 + 40) = retaddr;
        *v16 = (PVOID)SkmiGetInstructionPointer(v19, v18);
      }
    }
    v20 = a1 + 4096;
    *v13 = 0x4000000000000000LL;
    v63 = a1 + 4096;
    v64 = v13 + 1;
    v21 = &v13[a6 + 1];
    v22 = SkmiGetPteTrace(0, (_DWORD)v13 + 8 + 8 * a6, 0, 0, *v21);
    v24 = v22;
    if ( v22 )
    {
      v25 = (PVOID *)(v22 + 32);
      memset_0((void *)(v22 + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        StackBase = KeGetPcr()->NtTib.StackBase;
        if ( StackBase )
        {
          if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v25, BackTraceHash) )
          {
            *(_QWORD *)(v24 + 40) = retaddr;
            *v25 = (PVOID)SkmiGetInstructionPointer(v27, v23);
          }
        }
      }
    }
    v28 = 0x8000000000000061uLL;
    *v21 = 0x4000000000000000LL;
    if ( a6 )
    {
      while ( 1 )
      {
        *(_QWORD *)BackTraceHash = *a5;
        if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)BackTraceHash, 1, 0x8005u) )
          break;
        --v12;
        HyperspacePte = SkmiGetHyperspacePte();
        v31 = (*a5 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000063uLL;
        v32 = SkmiGetPteTrace(0, HyperspacePte, 0, (*(_DWORD *)a5 << 12) ^ 0x63u, *(_QWORD *)HyperspacePte);
        v33 = v32;
        if ( v32 )
        {
          v34 = (PVOID *)(v32 + 32);
          memset_0((void *)(v32 + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v35 = KeGetPcr()->NtTib.StackBase;
            if ( v35 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v35, 8u, v34, BackTraceHash) )
              {
                *(_QWORD *)(v33 + 40) = retaddr;
                *v34 = (PVOID)SkmiGetInstructionPointer(v37, v36);
              }
            }
          }
        }
        if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
          && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
        {
          v38 = KeGetPcr()->NtTib.StackBase;
          v39 = v38 ? v38[10] : 0LL;
          v40 = *(_QWORD *)(v39 + 232);
          if ( v40 )
          {
            v41 = SkiKvaShadowMode;
            *(_QWORD *)(v40 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v31;
            if ( v41 != 2 && (v31 & 1) != 0 )
              v31 |= 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)HyperspacePte = v31;
        SkeZeroPages(HyperspacePte << 25 >> 16, 4096);
        v20 = v63 + 4096;
        v63 += 4096LL;
        if ( !v12 )
          SkmiInitializeNtKernelShadowStack(v20, HyperspacePte << 25 >> 16, a3, a4, a7);
        v42 = SkmiGetPteTrace(0, HyperspacePte, 0, 0, *(_QWORD *)HyperspacePte);
        v44 = v42;
        if ( v42 )
        {
          v45 = (PVOID *)(v42 + 32);
          memset_0((void *)(v42 + 32), 0, (unsigned int)(v43 + 64));
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v46 = KeGetPcr()->NtTib.StackBase;
            if ( v46 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v46, 8u, v45, BackTraceHash) )
              {
                *(_QWORD *)(v44 + 40) = retaddr;
                *v45 = (PVOID)SkmiGetInstructionPointer(v48, v47);
              }
            }
          }
        }
        if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
          && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
        {
          v49 = KeGetPcr()->NtTib.StackBase;
          v50 = v49 ? v49[10] : 0LL;
          v51 = *(_QWORD *)(v50 + 232);
          if ( v51 )
            *(_QWORD *)(v51 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = 0;
        }
        *(_QWORD *)HyperspacePte = 0;
        SkmiReleaseHyperspacePte(HyperspacePte);
        SkmiProtectSinglePage(*a5);
        v52 = v64;
        v28 = (*a5 << 12) ^ ((*a5 << 12) ^ v28) & 0xFFF0000000000FFFuLL;
        v53 = SkmiGetPteTrace(0, (_DWORD)v64, 0, v28, *v64);
        v54 = v53;
        if ( v53 )
        {
          v55 = (PVOID *)(v53 + 32);
          memset_0((void *)(v53 + 32), 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v56 = KeGetPcr()->NtTib.StackBase;
            if ( v56 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v56, 8u, v55, BackTraceHash) )
              {
                *(_QWORD *)(v54 + 40) = retaddr;
                *v55 = (PVOID)SkmiGetInstructionPointer(v57, v23);
              }
            }
          }
        }
        *v52 = v28;
        ++a5;
        v64 = v52 + 1;
        if ( !v12 )
          goto LABEL_56;
      }
      SKMI_PAGE_SECURITY(3100, *a5, 0, 0);
      LOBYTE(v59) = v60;
      RtlpReleasePropStoreLockShared(&SkmiNteLock, v59);
      SkmiUnpinNar(*(_QWORD *)v62);
      SkmiReserveNar(0, 0, 1, 2, 0, v62[0], 0);
      return 3221225539LL;
    }
    else
    {
LABEL_56:
      LOBYTE(v23) = v60;
      RtlpReleasePropStoreLockShared(&SkmiNteLock, v23);
      if ( (SkmiFlags & 0x1000000) != 0 )
      {
        SkmiBatchFlushTbRange(v20, v12 + 2, v65);
        if ( v67 )
        {
          LOBYTE(v58) = v68;
          SkeFlushEntireTb(v58, 0);
        }
        else if ( v66 )
        {
          LOBYTE(v58) = v68;
          SkeFlushRangeListTb(v58, 0, v66, v65);
        }
      }
      SkmiUnpinNar(*(_QWORD *)v62);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14006ffbc  mov     [rsp-8+arg_0], rbx
0x14006ffc1  mov     [rsp-8+arg_18], r9d
0x14006ffc6  mov     [rsp-8+arg_10], r8d
0x14006ffcb  push    rbp
0x14006ffcc  push    rsi
0x14006ffcd  push    rdi
0x14006ffce  push    r12
0x14006ffd0  push    r13
0x14006ffd2  push    r14
0x14006ffd4  push    r15
0x14006ffd6  lea     rbp, [rsp-80h]
0x14006ffdb  sub     rsp, 180h
0x14006ffe2  mov     edi, r8d
0x14006ffe5  mov     r14d, r9d
0x14006ffe8  mov     ebx, edx
0x14006ffea  mov     rsi, rcx
0x14006ffed  xor     edx, edx; Val
0x14006ffef  lea     rcx, [rsp+1B0h+var_140]; void *
0x14006fff4  mov     r8d, 108h; Size
0x14006fffa  call    memset_0
0x14006ffff  xor     r12d, r12d
0x140070002  test    cs:SkmiFlags, 80000h
0x14007000c  mov     qword ptr [rsp+1B0h+var_160], r12
0x140070011  jnz     short loc_14007001D
0x140070013  mov     eax, 0C00000BBh
0x140070018  jmp     loc_14007062A
0x14007001d  test    edi, edi
0x14007001f  jz      loc_140070625
0x140070025  test    edi, 0FFFFFFFCh
0x14007002b  jnz     loc_140070625
0x140070031  popcnt  rcx, r14
0x140070036  cmp     ecx, 1
0x140070039  ja      loc_140070625
0x14007003f  test    r14d, 0FFFFFFF8h
0x140070046  jnz     loc_140070625
0x14007004c  mov     edx, 3000h; int
0x140070051  cmp     ebx, edx
0x140070053  jnz     loc_140070625
0x140070059  mov     r15d, [rbp+0B0h+arg_28]
0x140070060  mov     eax, r15d
0x140070063  shl     eax, 0Ch
0x140070066  cmp     eax, 1000h
0x14007006b  jnz     loc_140070625
0x140070071  lea     rax, [rsp+1B0h+var_160]
0x140070076  mov     r9d, 2; int
0x14007007c  mov     [rsp+1B0h+var_180], rax; __int64
0x140070081  mov     r8d, 40000h; int
0x140070087  mov     qword ptr [rsp+1B0h+var_188], r12; BackTraceHash
0x14007008c  mov     rcx, rsi; int
0x14007008f  mov     [rsp+1B0h+var_190], r12; __int64
0x140070094  call    SkmiReserveNar
0x140070099  test    eax, eax
0x14007009b  js      loc_14007062A
0x1400700a1  mov     r14, rsi
0x1400700a4  mov     rcx, 7FFFFFFFF8h
0x1400700ae  shr     r14, 9
0x1400700b2  and     r14, rcx
0x1400700b5  mov     rcx, 0FFFFF60000000000h
0x1400700bf  add     r14, rcx
0x1400700c2  lea     rcx, SkmiNteLock
0x1400700c9  call    SkAcquireSpinLockShared
0x1400700ce  mov     rcx, [r14]
0x1400700d1  mov     r9, 4000000000000000h
0x1400700db  mov     [rsp+1B0h+var_190], rcx
0x1400700e0  xor     r8d, r8d
0x1400700e3  xor     ecx, ecx
0x1400700e5  mov     [rsp+1B0h+var_170], al
0x1400700e9  mov     rdx, r14
0x1400700ec  call    SkmiGetPteTrace
0x1400700f1  mov     rdi, rax
0x1400700f4  test    rax, rax
0x1400700f7  jz      short loc_14007014F
0x1400700f9  xor     edx, edx; Val
0x1400700fb  lea     rbx, [rax+20h]
0x1400700ff  mov     rcx, rbx; void *
0x140070102  lea     r8d, [rdx+40h]; Size
0x140070106  call    memset_0
0x14007010b  test    cs:SkmiFlags, 400000h
0x140070115  jz      short loc_14007014F
0x140070117  mov     rax, gs:8
0x140070120  test    rax, rax
0x140070123  jz      short loc_14007014F
0x140070125  lea     r9, [rsp+1B0h+BackTraceHash]; BackTraceHash
0x14007012a  mov     r8, rbx; BackTrace
0x14007012d  mov     edx, 8; FramesToCapture
0x140070132  call    RtlCaptureStackBackTrace
0x140070137  test    ax, ax
0x14007013a  jnz     short loc_14007014F
0x14007013c  mov     rax, [rbp+0B8h]
0x140070143  mov     [rdi+28h], rax
0x140070147  call    SkmiGetInstructionPointer
0x14007014c  mov     [rbx], rax
0x14007014f  mov     rax, 4000000000000000h
0x140070159  lea     r13, [rsi+1000h]
0x140070160  mov     [r14], rax
0x140070163  mov     r9, 4000000000000000h
0x14007016d  add     r14, 8
0x140070171  mov     [rsp+1B0h+var_158], r13
0x140070176  xor     r8d, r8d
0x140070179  mov     [rsp+1B0h+var_150], r14
0x14007017e  xor     ecx, ecx
0x140070180  lea     rsi, [r14+r15*8]
0x140070184  mov     rax, [rsi]
0x140070187  mov     rdx, rsi
0x14007018a  mov     [rsp+1B0h+var_190], rax
0x14007018f  call    SkmiGetPteTrace
0x140070194  mov     rdi, rax
0x140070197  test    rax, rax
0x14007019a  jz      short loc_1400701F2
0x14007019c  xor     edx, edx; Val
0x14007019e  lea     rbx, [rax+20h]
0x1400701a2  mov     rcx, rbx; void *
0x1400701a5  lea     r8d, [rdx+40h]; Size
0x1400701a9  call    memset_0
0x1400701ae  test    cs:SkmiFlags, 400000h
0x1400701b8  jz      short loc_1400701F2
0x1400701ba  mov     rcx, gs:8; FramesToSkip
0x1400701c3  test    rcx, rcx
0x1400701c6  jz      short loc_1400701F2
0x1400701c8  lea     r9, [rsp+1B0h+BackTraceHash]; BackTraceHash
0x1400701cd  mov     r8, rbx; BackTrace
0x1400701d0  mov     edx, 8; FramesToCapture
0x1400701d5  call    RtlCaptureStackBackTrace
0x1400701da  test    ax, ax
0x1400701dd  jnz     short loc_1400701F2
0x1400701df  mov     rax, [rbp+0B8h]
0x1400701e6  mov     [rdi+28h], rax
0x1400701ea  call    SkmiGetInstructionPointer
0x1400701ef  mov     [rbx], rax
0x1400701f2  mov     rax, 4000000000000000h
0x1400701fc  mov     rdi, 8000000000000061h
0x140070206  mov     [rsi], rax
0x140070209  test    r15d, r15d
0x14007020c  jz      loc_140070564
0x140070212  mov     r12, [rbp+0B0h+arg_20]
0x140070219  xor     r14d, r14d
0x14007021c  mov     rax, [r12]
0x140070220  lea     rcx, [rsp+1B0h+BackTraceHash]
0x140070225  mov     ebx, 1
0x14007022a  mov     qword ptr [rsp+1B0h+BackTraceHash], rax
0x14007022f  mov     edx, ebx
0x140070231  mov     r8d, 8005h
0x140070237  call    SkmiClaimPhysicalPages
0x14007023c  test    eax, eax
0x14007023e  jz      loc_1400705A4
0x140070244  dec     r15d
0x140070247  call    SkmiGetHyperspacePte
0x14007024c  mov     rbx, [r12]
0x140070250  mov     rsi, rax
0x140070253  shl     rbx, 0Ch
0x140070257  mov     rax, 0FFFFFFFFFF000h
0x140070261  and     rbx, rax
0x140070264  xor     r8d, r8d
0x140070267  mov     rax, 8000000000000063h
0x140070271  mov     rdx, rsi
0x140070274  mov     rcx, [rsi]
0x140070277  xor     rbx, rax
0x14007027a  mov     [rsp+1B0h+var_190], rcx
0x14007027f  mov     r9, rbx
0x140070282  xor     ecx, ecx
0x140070284  call    SkmiGetPteTrace
0x140070289  mov     r13, rax
0x14007028c  test    rax, rax
0x14007028f  jz      short loc_1400702EA
0x140070291  xor     edx, edx; Val
0x140070293  lea     r14, [rax+20h]
0x140070297  mov     rcx, r14; void *
0x14007029a  lea     r8d, [rdx+40h]; Size
0x14007029e  call    memset_0
0x1400702a3  test    cs:SkmiFlags, 400000h
0x1400702ad  jz      short loc_1400702E7
0x1400702af  mov     rcx, gs:8; FramesToSkip
0x1400702b8  test    rcx, rcx
0x1400702bb  jz      short loc_1400702E7
0x1400702bd  lea     r9, [rsp+1B0h+BackTraceHash]; BackTraceHash
0x1400702c2  mov     r8, r14; BackTrace
0x1400702c5  mov     edx, 8; FramesToCapture
0x1400702ca  call    RtlCaptureStackBackTrace
0x1400702cf  test    ax, ax
0x1400702d2  jnz     short loc_1400702E7
0x1400702d4  mov     rax, [rbp+0B8h]
0x1400702db  mov     [r13+28h], rax
0x1400702df  call    SkmiGetInstructionPointer
0x1400702e4  mov     [r14], rax
0x1400702e7  xor     r14d, r14d
0x1400702ea  mov     rax, 0FFFFF6FB7DBED000h
0x1400702f4  mov     rax, rax
0x1400702f7  cmp     rsi, rax
0x1400702fa  jb      short loc_14007035E
0x1400702fc  mov     rax, 0FFFFF6FB7DBED800h
0x140070306  mov     rax, rax
0x140070309  cmp     rsi, rax
0x14007030c  jnb     short loc_14007035E
0x14007030e  mov     rax, gs:8
0x140070317  test    rax, rax
0x14007031a  jz      short loc_140070322
0x14007031c  mov     rcx, [rax+50h]
0x140070320  jmp     short loc_140070325
0x140070322  mov     rcx, r14
0x140070325  mov     rdx, [rcx+0E8h]
0x14007032c  test    rdx, rdx
0x14007032f  jz      short loc_14007035E
0x140070331  mov     ecx, cs:SkiKvaShadowMode
0x140070337  mov     rax, rsi
0x14007033a  sar     rax, 3
0x14007033e  and     eax, 1FFh
0x140070343  mov     [rdx+rax*8], rbx
0x140070347  cmp     ecx, 2
0x14007034a  jz      short loc_14007035E
0x14007034c  test    bl, 1
0x14007034f  jz      short loc_14007035E
0x140070351  mov     rax, 8000000000000000h
0x14007035b  or      rbx, rax
0x14007035e  mov     [rsi], rbx
0x140070361  mov     rbx, rsi
0x140070364  shl     rbx, 19h
0x140070368  mov     rax, 0FFFFF68000000000h
0x140070372  shl     rax, 19h
0x140070376  mov     edx, 1000h
0x14007037b  sub     rbx, rax
0x14007037e  sar     rbx, 10h
0x140070382  mov     rcx, rbx
0x140070385  call    SkeZeroPages
0x14007038a  mov     r13, [rsp+1B0h+var_158]
0x14007038f  add     r13, 1000h
0x140070396  mov     [rsp+1B0h+var_158], r13
0x14007039b  test    r15d, r15d
0x14007039e  jnz     short loc_1400703C5
0x1400703a0  mov     rax, [rbp+0B0h+arg_30]
0x1400703a7  mov     rdx, rbx
0x1400703aa  mov     r9d, [rbp+0B0h+arg_18]
0x1400703b1  mov     rcx, r13
0x1400703b4  mov     r8d, [rbp+0B0h+arg_10]
0x1400703bb  mov     [rsp+1B0h+var_190], rax
0x1400703c0  call    SkmiInitializeNtKernelShadowStack
0x1400703c5  mov     rax, [rsi]
0x1400703c8  xor     r9d, r9d
0x1400703cb  xor     r8d, r8d
0x1400703ce  mov     [rsp+1B0h+var_190], rax
0x1400703d3  mov     rdx, rsi
0x1400703d6  xor     ecx, ecx
0x1400703d8  call    SkmiGetPteTrace
0x1400703dd  xor     ebx, ebx
0x1400703df  mov     r14, rax
0x1400703e2  test    rax, rax
0x1400703e5  jz      short loc_14007043F
0x1400703e7  lea     rbx, [rax+20h]
0x1400703eb  xor     edx, edx; Val
0x1400703ed  mov     rcx, rbx; void *
0x1400703f0  lea     r8d, [r9+40h]; Size
0x1400703f4  call    memset_0
0x1400703f9  test    cs:SkmiFlags, 400000h
0x140070403  jz      short loc_14007043D
0x140070405  mov     rcx, gs:8; FramesToSkip
0x14007040e  test    rcx, rcx
0x140070411  jz      short loc_14007043D
0x140070413  lea     r9, [rsp+1B0h+BackTraceHash]; BackTraceHash
0x140070418  mov     r8, rbx; BackTrace
0x14007041b  mov     edx, 8; FramesToCapture
0x140070420  call    RtlCaptureStackBackTrace
0x140070425  test    ax, ax
0x140070428  jnz     short loc_14007043D
0x14007042a  mov     rax, [rbp+0B8h]
0x140070431  mov     [r14+28h], rax
0x140070435  call    SkmiGetInstructionPointer
0x14007043a  mov     [rbx], rax
0x14007043d  xor     ebx, ebx
0x14007043f  mov     rax, 0FFFFF6FB7DBED000h
0x140070449  mov     rax, rax
0x14007044c  cmp     rsi, rax
0x14007044f  jb      short loc_140070496
0x140070451  mov     rax, 0FFFFF6FB7DBED800h
0x14007045b  mov     rax, rax
0x14007045e  cmp     rsi, rax
0x140070461  jnb     short loc_140070496
0x140070463  mov     rax, gs:8
0x14007046c  test    rax, rax
0x14007046f  jz      short loc_140070477
0x140070471  mov     rcx, [rax+50h]
0x140070475  jmp     short loc_14007047A
0x140070477  mov     rcx, rbx
0x14007047a  mov     rdx, [rcx+0E8h]
0x140070481  test    rdx, rdx
0x140070484  jz      short loc_140070496
0x140070486  mov     rax, rsi
0x140070489  sar     rax, 3
0x14007048d  and     eax, 1FFh
0x140070492  mov     [rdx+rax*8], rbx
0x140070496  mov     rcx, rsi
0x140070499  mov     [rsi], rbx
0x14007049c  call    SkmiReleaseHyperspacePte
0x1400704a1  mov     rcx, [r12]; BugCheckParameter3
0x1400704a5  mov     edx, 3
0x1400704aa  call    SkmiProtectSinglePage
0x1400704af  mov     rcx, [r12]
0x1400704b3  mov     rdx, 0FFF0000000000FFFh
0x1400704bd  mov     r14, [rsp+1B0h+var_150]
0x1400704c2  xor     r8d, r8d
0x1400704c5  shl     rcx, 0Ch
0x1400704c9  xor     rdi, rcx
  ... truncated ...
```
