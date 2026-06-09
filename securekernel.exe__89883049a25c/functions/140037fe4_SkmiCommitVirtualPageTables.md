# SkmiCommitVirtualPageTables

- ea: `0x140037fe4`
- end: `0x140038580`
- name: `SkmiCommitVirtualPageTables`
- size: `1436`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `7`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14001c554`
- `0x1400280b0`
- `0x14005bbe8`
- `0x1400603cc`
- `0x140065d00`
- `0x140066464`
- `0x14006a4b8`

## callees

- `0x140002410`
- `0x140003780`
- `0x14000ff70`
- `0x1400202b0`
- `0x1400202ec`
- `0x140020360`
- `0x140020424`
- `0x14002b534`
- `0x140037fe4`
- `0x140038588`
- `0x14007fd10`
- `0x1400801c0`
- `0x140080338`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCommitVirtualPageTables(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 *v10; // rax
  __int64 *v11; // rcx
  unsigned __int16 v12; // r15
  __int64 v13; // rdi
  bool v14; // zf
  __int64 v15; // rsi
  unsigned __int64 v16; // rdi
  __int64 v17; // r13
  int v18; // r12d
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 PteTrace; // rax
  __int64 v22; // r13
  PVOID *v23; // r12
  PVOID StackBase; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  int v31; // edx
  __int64 v32; // rdx
  __int64 v33; // rcx
  unsigned __int64 v35; // r15
  __int64 v36; // rax
  int v37; // r9d
  __int64 v38; // r13
  PVOID *v39; // r15
  PVOID v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  _QWORD *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rcx
  unsigned __int64 v48; // [rsp+30h] [rbp-D0h]
  unsigned __int8 CurrentIrql; // [rsp+38h] [rbp-C8h]
  ULONG BackTraceHash; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 *v51; // [rsp+48h] [rbp-B8h]
  __int64 v52; // [rsp+50h] [rbp-B0h]
  __int64 v53; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v54; // [rsp+60h] [rbp-A0h]
  _QWORD *v55; // [rsp+68h] [rbp-98h]
  _BYTE v56[256]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v57; // [rsp+170h] [rbp+70h]
  __int16 v58; // [rsp+174h] [rbp+74h]
  __int64 *v59; // [rsp+180h] [rbp+80h] BYREF
  __int128 v60; // [rsp+188h] [rbp+88h]
  __int64 v61; // [rsp+198h] [rbp+98h]
  __int64 v62; // [rsp+1A0h] [rbp+A0h]
  _UNKNOWN *retaddr; // [rsp+1E8h] [rbp+E8h]

  v55 = a6;
  memset_0(v56, 0, 0x108u);
  v10 = *(__int64 **)(a1 + 72);
  v11 = SkmiSystemPartition;
  v61 = 0;
  v52 = 0;
  if ( v10 )
    v11 = v10;
  v51 = 0;
  v59 = v11;
  v60 = 0;
  v12 = 0;
  v62 = 0;
  v13 = a2 & 0xFFFFFFFFFLL;
  v48 = 8 * v13 - 0x98000000000LL;
  v14 = (*(_DWORD *)a1 & 0x200) == 0;
  v54 = 8 * (a3 & 0xFFFFFFFFFLL) - 0x98000000000LL;
  v15 = 0;
  v53 = 0;
  if ( !v14 )
  {
    v15 = *(_QWORD *)(a1 + 624);
    v53 = v15;
  }
  v16 = 8 * v13 - 0x98000000000LL;
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(2u);
LABEL_6:
  v17 = a1 + 8;
LABEL_7:
  v18 = SkmiPreparePteAllocation(&v59);
  if ( v15 )
    SkAcquireSpinLockSharedAtDpcLevel(v15 + 192);
  SkAcquireSpinLockExclusiveAtDpcLevel(v17);
  if ( v18 >= 0 )
  {
    while ( 1 )
    {
      if ( v16 > v54 )
      {
        if ( v12 )
          *v51 = (*v51 + v12) ^ (*v51 ^ (*v51 + v12)) & 0xFFFFF00000000000uLL;
        *(_DWORD *)(a1 + 8) = 0;
        SkTrackSpinLockRelease();
        if ( v15 )
        {
          LOBYTE(v32) = CurrentIrql;
          RtlpReleasePropStoreLockShared(v15 + 192, v32);
        }
        else
        {
          LOBYTE(v33) = CurrentIrql;
          SkeLowerIrql(v33);
        }
        SkmiFreePteAllocation(&v59);
        if ( v55 )
          *v55 = v52;
        return 0;
      }
      if ( v16 != v48 && (v16 & 0xFF8) != 0 )
        break;
      if ( v12 )
      {
        v20 = v12;
        v12 = 0;
        *v51 = (*v51 + v20) ^ (*v51 ^ (*v51 + v20)) & 0xFFFFF00000000000uLL;
      }
      if ( !(unsigned int)SkmiCommitPte(v16, &v59, a1) )
      {
        *(_DWORD *)(a1 + 8) = 0;
        SkTrackSpinLockRelease();
        v17 = a1 + 8;
        if ( !v15 )
          goto LABEL_7;
        _InterlockedDecrement((volatile signed __int32 *)(v15 + 192));
        SkTrackSpinLockRelease();
        goto LABEL_6;
      }
      v51 = (unsigned __int64 *)(8
                               * ((*(_QWORD *)(((v16 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL) >> 12) & 0xFFFFFFFFFFLL)
                               - 0x180000000000LL);
      if ( !*(_QWORD *)v16 )
      {
        --v12;
LABEL_20:
        PteTrace = SkmiGetPteTrace(0, v16, 0, a4, *(_QWORD *)v16);
        v22 = PteTrace;
        if ( PteTrace )
        {
          v23 = (PVOID *)(PteTrace + 32);
          memset_0((void *)(PteTrace + 32), 0, 0x40u);
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
        }
        v27 = a4;
        if ( v16 >= 0xFFFFF6FB7DBED000uLL && v16 < 0xFFFFF6FB7DBED800uLL )
        {
          v28 = KeGetPcr()->NtTib.StackBase;
          if ( v28 )
            v29 = v28[10];
          else
            v29 = 0;
          v30 = *(_QWORD *)(v29 + 232);
          if ( v30 )
          {
            v31 = SkiKvaShadowMode;
            *(_QWORD *)(v30 + 8 * (((__int64)v16 >> 3) & 0x1FF)) = a4;
            if ( v31 != 2 && (a4 & 1) != 0 )
              v27 = a4 | 0x8000000000000000uLL;
          }
        }
        *(_QWORD *)v16 = v27;
        ++v52;
        ++v12;
      }
LABEL_35:
      v16 += 8LL;
    }
    if ( *(_QWORD *)v16 )
      goto LABEL_35;
    goto LABEL_20;
  }
  v35 = v48;
  v57 = 0;
  v58 = -256;
  if ( v16 > v48 )
  {
    do
    {
      v16 -= 8LL;
      if ( *(_QWORD *)v16 == a4 )
      {
        v36 = SkmiGetPteTrace(0, v16, 0, 0, *(_QWORD *)v16);
        v38 = v36;
        if ( v36 )
        {
          v39 = (PVOID *)(v36 + 32);
          memset_0((void *)(v36 + 32), 0, (unsigned int)(v37 + 64));
          if ( (SkmiFlags & 0x400000) != 0 )
          {
            v40 = KeGetPcr()->NtTib.StackBase;
            if ( v40 )
            {
              if ( !RtlCaptureStackBackTrace((ULONG)v40, 8u, v39, &BackTraceHash) )
              {
                *(_QWORD *)(v38 + 40) = retaddr;
                *v39 = (PVOID)SkmiGetInstructionPointer(v42, v41);
              }
            }
          }
          v35 = v48;
        }
        if ( v16 >= 0xFFFFF6FB7DBED000uLL && v16 < 0xFFFFF6FB7DBED800uLL )
        {
          v43 = KeGetPcr()->NtTib.StackBase;
          v44 = v43 ? v43[10] : 0LL;
          v45 = *(_QWORD *)(v44 + 232);
          if ( v45 )
            *(_QWORD *)(v45 + 8 * (((__int64)v16 >> 3) & 0x1FF)) = 0;
        }
        *(_QWORD *)v16 = 0;
        SkmiReleasePte(v16, a1, v56);
      }
    }
    while ( v16 > v35 );
    v15 = v53;
    if ( (_BYTE)v58 )
    {
      LOBYTE(v19) = HIBYTE(v58);
      SkeFlushEntireTb(v19, a1);
    }
    else if ( v57 )
    {
      LOBYTE(v19) = HIBYTE(v58);
      SkeFlushRangeListTb(v19, a1, v57, v56);
    }
  }
  *(_DWORD *)(a1 + 8) = 0;
  SkTrackSpinLockRelease();
  if ( v15 )
  {
    LOBYTE(v46) = CurrentIrql;
    RtlpReleasePropStoreLockShared(v15 + 192, v46);
  }
  else
  {
    LOBYTE(v47) = CurrentIrql;
    SkeLowerIrql(v47);
  }
  SkmiFreePteAllocation(&v59);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140037fe4  mov     [rsp-8+arg_10], rbx
0x140037fe9  push    rbp
0x140037fea  push    rsi
0x140037feb  push    rdi
0x140037fec  push    r12
0x140037fee  push    r13
0x140037ff0  push    r14
0x140037ff2  push    r15
0x140037ff4  lea     rbp, [rsp-0B0h]
0x140037ffc  sub     rsp, 1B0h
0x140038003  mov     rax, cs:__security_cookie
0x14003800a  xor     rax, rsp
0x14003800d  mov     [rbp+0E0h+var_38], rax
0x140038014  mov     rax, [rbp+0E0h+arg_28]
0x14003801b  mov     rsi, r8
0x14003801e  mov     rdi, rdx
0x140038021  mov     [rsp+1E0h+var_178], rax
0x140038026  mov     r14, rcx
0x140038029  xor     edx, edx; Val
0x14003802b  mov     r8d, 108h; Size
0x140038031  lea     rcx, [rsp+1E0h+var_170]; void *
0x140038036  mov     rbx, r9
0x140038039  call    memset_0
0x14003803e  mov     rax, [r14+48h]
0x140038042  lea     rcx, SkmiSystemPartition
0x140038049  xor     r8d, r8d
0x14003804c  mov     r9, 0FFFFF68000000000h
0x140038056  test    rax, rax
0x140038059  mov     [rbp+0E0h+var_48], r8
0x140038060  xorps   xmm0, xmm0
0x140038063  mov     [rsp+1E0h+var_190], r8
0x140038068  cmovnz  rcx, rax
0x14003806c  mov     [rsp+1E0h+var_198], r8
0x140038071  mov     rdx, 0FFFFFFFFFh
0x14003807b  mov     [rbp+0E0h+var_60], rcx
0x140038082  movdqu  [rbp+0E0h+var_58], xmm0
0x14003808a  mov     r15d, r8d
0x14003808d  mov     [rbp+0E0h+var_40], r8
0x140038094  and     rdi, rdx
0x140038097  mov     rax, r9
0x14003809a  lea     rcx, [rax+rdi*8]
0x14003809e  and     rsi, rdx
0x1400380a1  mov     [rsp+1E0h+var_1B0], rcx
0x1400380a6  mov     rax, r9
0x1400380a9  test    dword ptr [r14], 200h
0x1400380b0  lea     rax, [rax+rsi*8]
0x1400380b4  mov     [rsp+1E0h+var_180], rax
0x1400380b9  mov     esi, r8d
0x1400380bc  mov     [rsp+1E0h+var_188], r8
0x1400380c1  jz      short loc_1400380CF
0x1400380c3  mov     rsi, [r14+270h]
0x1400380ca  mov     [rsp+1E0h+var_188], rsi
0x1400380cf  mov     rdi, rcx
0x1400380d2  mov     r13, cr8
0x1400380d6  mov     [rsp+1E0h+var_1A8], r13
0x1400380db  mov     eax, 2
0x1400380e0  mov     cr8, rax
0x1400380e4  lea     r13, [r14+8]
0x1400380e8  lea     rcx, [rbp+0E0h+var_60]
0x1400380ef  call    SkmiPreparePteAllocation
0x1400380f4  mov     r12d, eax
0x1400380f7  test    rsi, rsi
0x1400380fa  jz      short loc_140038108
0x1400380fc  lea     rcx, [rsi+0C0h]
0x140038103  call    SkAcquireSpinLockSharedAtDpcLevel
0x140038108  mov     rcx, r13
0x14003810b  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x140038110  xor     r13d, r13d
0x140038113  test    r12d, r12d
0x140038116  js      loc_1400383CC
0x14003811c  cmp     rdi, [rsp+1E0h+var_180]
0x140038121  ja      loc_140038350
0x140038127  cmp     rdi, [rsp+1E0h+var_1B0]
0x14003812c  jz      short loc_140038148
0x14003812e  test    rdi, 0FF8h
0x140038135  jz      short loc_140038148
0x140038137  mov     rax, [rdi]
0x14003813a  test    rax, rax
0x14003813d  jnz     loc_140038319
0x140038143  jmp     loc_140038211
0x140038148  test    r15w, r15w
0x14003814c  jz      short loc_140038179
0x14003814e  mov     r8, [rsp+1E0h+var_198]
0x140038153  movzx   edx, r15w
0x140038157  mov     r15d, r13d
0x14003815a  mov     rcx, [r8]
0x14003815d  add     rdx, rcx
0x140038160  mov     rax, rdx
0x140038163  xor     rax, rcx
0x140038166  mov     rcx, 0FFFFF00000000000h
0x140038170  and     rax, rcx
0x140038173  xor     rax, rdx
0x140038176  mov     [r8], rax
0x140038179  mov     r8, r14
0x14003817c  lea     rdx, [rbp+0E0h+var_60]
0x140038183  mov     rcx, rdi
0x140038186  call    SkmiCommitPte
0x14003818b  test    eax, eax
0x14003818d  jz      loc_140038322
0x140038193  mov     rax, 7FFFFFFFF8h
0x14003819d  mov     rcx, rdi
0x1400381a0  shr     rcx, 9
0x1400381a4  and     rcx, rax
0x1400381a7  mov     rax, 0FFFFF68000000000h
0x1400381b1  mov     rax, rax
0x1400381b4  mov     rdx, [rcx+rax]
0x1400381b8  mov     rax, 0FFFFFFFFFFh
0x1400381c2  shr     rdx, 0Ch
0x1400381c6  and     rdx, rax
0x1400381c9  mov     rcx, 0FFFFEFFFFFFFFFFFh
0x1400381d3  mov     r8, 0FFFFE80000000000h
0x1400381dd  mov     rax, r8
0x1400381e0  sub     rcx, rax
0x1400381e3  sar     rcx, 3
0x1400381e7  cmp     rdx, rcx
0x1400381ea  ja      loc_140038349
0x1400381f0  mov     rax, r8
0x1400381f3  lea     rax, [rax+rdx*8]
0x1400381f7  mov     [rsp+1E0h+var_198], rax
0x1400381fc  mov     rax, [rdi]
0x1400381ff  test    rax, rax
0x140038202  jnz     loc_140038319
0x140038208  mov     eax, 0FFFFh
0x14003820d  add     r15w, ax
0x140038211  mov     rax, [rdi]
0x140038214  mov     r9, rbx
0x140038217  xor     r8d, r8d
0x14003821a  mov     [rsp+1E0h+var_1C0], rax
0x14003821f  mov     rdx, rdi
0x140038222  xor     ecx, ecx
0x140038224  call    SkmiGetPteTrace
0x140038229  mov     r13, rax
0x14003822c  test    rax, rax
0x14003822f  jz      short loc_140038288
0x140038231  xor     edx, edx; Val
0x140038233  lea     r12, [rax+20h]
0x140038237  mov     rcx, r12; void *
0x14003823a  lea     r8d, [rdx+40h]; Size
0x14003823e  call    memset_0
0x140038243  test    cs:SkmiFlags, 400000h
0x14003824d  jz      short loc_140038288
0x14003824f  mov     rcx, gs:8; FramesToSkip
0x140038258  test    rcx, rcx
0x14003825b  jz      short loc_140038288
0x14003825d  lea     r9, [rsp+1E0h+BackTraceHash]; BackTraceHash
0x140038262  mov     r8, r12; BackTrace
0x140038265  mov     edx, 8; FramesToCapture
0x14003826a  call    RtlCaptureStackBackTrace
0x14003826f  test    ax, ax
0x140038272  jnz     short loc_140038288
0x140038274  mov     rax, [rbp+0E8h]
0x14003827b  mov     [r13+28h], rax
0x14003827f  call    SkmiGetInstructionPointer
0x140038284  mov     [r12], rax
0x140038288  mov     rax, rbx
0x14003828b  mov     rcx, 0FFFFF6FB7DBED000h
0x140038295  mov     rcx, rcx
0x140038298  cmp     rdi, rcx
0x14003829b  jb      short loc_140038305
0x14003829d  mov     rcx, 0FFFFF6FB7DBED800h
0x1400382a7  mov     rcx, rcx
0x1400382aa  xor     r13d, r13d
0x1400382ad  cmp     rdi, rcx
0x1400382b0  jnb     short loc_140038308
0x1400382b2  mov     rcx, gs:8
0x1400382bb  test    rcx, rcx
0x1400382be  jz      short loc_1400382C6
0x1400382c0  mov     rdx, [rcx+50h]
0x1400382c4  jmp     short loc_1400382C9
0x1400382c6  mov     rdx, r13
0x1400382c9  mov     r8, [rdx+0E8h]
0x1400382d0  test    r8, r8
0x1400382d3  jz      short loc_140038308
0x1400382d5  mov     edx, cs:SkiKvaShadowMode
0x1400382db  mov     rcx, rdi
0x1400382de  sar     rcx, 3
0x1400382e2  and     ecx, 1FFh
0x1400382e8  mov     [r8+rcx*8], rbx
0x1400382ec  cmp     edx, 2
0x1400382ef  jz      short loc_140038308
0x1400382f1  test    bl, 1
0x1400382f4  jz      short loc_140038308
0x1400382f6  mov     rcx, 8000000000000000h
0x140038300  or      rax, rcx
0x140038303  jmp     short loc_140038308
0x140038305  xor     r13d, r13d
0x140038308  mov     [rdi], rax
0x14003830b  mov     eax, 1
0x140038310  add     [rsp+1E0h+var_190], rax
0x140038315  add     r15w, ax
0x140038319  add     rdi, 8
0x14003831d  jmp     loc_14003811C
0x140038322  mov     [r14+8], r13d
0x140038326  call    SkTrackSpinLockRelease
0x14003832b  lea     r13, [r14+8]
0x14003832f  test    rsi, rsi
0x140038332  jz      loc_1400380E8
0x140038338  lock dec dword ptr [rsi+0C0h]
0x14003833f  call    SkTrackSpinLockRelease
0x140038344  jmp     loc_1400380E4
0x140038349  mov     ecx, 3Fh ; '?'
0x14003834e  int     29h; Win8: RtlFailFast(ecx)
0x140038350  test    r15w, r15w
0x140038354  jz      short loc_14003837E
0x140038356  mov     rdx, [rsp+1E0h+var_198]
0x14003835b  movzx   r8d, r15w
0x14003835f  mov     rcx, [rdx]
0x140038362  add     r8, rcx
0x140038365  mov     rax, r8
0x140038368  xor     rax, rcx
0x14003836b  mov     rcx, 0FFFFF00000000000h
0x140038375  and     rax, rcx
0x140038378  xor     rax, r8
0x14003837b  mov     [rdx], rax
0x14003837e  mov     [r14+8], r13d
0x140038382  call    SkTrackSpinLockRelease
0x140038387  test    rsi, rsi
0x14003838a  jz      short loc_14003839E
0x14003838c  mov     dl, byte ptr [rsp+1E0h+var_1A8]
0x140038390  lea     rcx, [rsi+0C0h]
0x140038397  call    RtlpReleasePropStoreLockShared
0x14003839c  jmp     short loc_1400383A7
0x14003839e  mov     cl, byte ptr [rsp+1E0h+var_1A8]
0x1400383a2  call    SkeLowerIrql
0x1400383a7  lea     rcx, [rbp+0E0h+var_60]
0x1400383ae  call    SkmiFreePteAllocation
0x1400383b3  mov     rcx, [rsp+1E0h+var_178]
0x1400383b8  test    rcx, rcx
0x1400383bb  jz      short loc_1400383C5
0x1400383bd  mov     rax, [rsp+1E0h+var_190]
0x1400383c2  mov     [rcx], rax
0x1400383c5  xor     eax, eax
0x1400383c7  jmp     loc_140038555
0x1400383cc  mov     r15, [rsp+1E0h+var_1B0]
0x1400383d1  mov     [rbp+0E0h+var_70], r13d
0x1400383d5  mov     [rbp+0E0h+var_6C], 0FF00h
0x1400383db  cmp     rdi, r15
0x1400383de  jbe     loc_14003851B
0x1400383e4  mov     rsi, 0FFFFF6FB7DBED000h
0x1400383ee  sub     rdi, 8
0x1400383f2  mov     rax, [rdi]
0x1400383f5  cmp     rax, rbx
0x1400383f8  jnz     loc_1400384E1
0x1400383fe  mov     rax, [rdi]
0x140038401  xor     r9d, r9d
0x140038404  xor     r8d, r8d
0x140038407  mov     [rsp+1E0h+var_1C0], rax
0x14003840c  mov     rdx, rdi
0x14003840f  xor     ecx, ecx
0x140038411  call    SkmiGetPteTrace
0x140038416  mov     r13, rax
0x140038419  test    rax, rax
0x14003841c  jz      short loc_140038479
0x14003841e  lea     r15, [rax+20h]
0x140038422  xor     edx, edx; Val
0x140038424  mov     rcx, r15; void *
0x140038427  lea     r8d, [r9+40h]; Size
0x14003842b  call    memset_0
0x140038430  test    cs:SkmiFlags, 400000h
0x14003843a  jz      short loc_140038474
0x14003843c  mov     rcx, gs:8; FramesToSkip
0x140038445  test    rcx, rcx
0x140038448  jz      short loc_140038474
0x14003844a  lea     r9, [rsp+1E0h+BackTraceHash]; BackTraceHash
0x14003844f  mov     r8, r15; BackTrace
0x140038452  mov     edx, 8; FramesToCapture
0x140038457  call    RtlCaptureStackBackTrace
0x14003845c  test    ax, ax
0x14003845f  jnz     short loc_140038474
0x140038461  mov     rax, [rbp+0E8h]
0x140038468  mov     [r13+28h], rax
0x14003846c  call    SkmiGetInstructionPointer
0x140038471  mov     [r15], rax
0x140038474  mov     r15, [rsp+1E0h+var_1B0]
0x140038479  mov     rax, rsi
0x14003847c  cmp     rdi, rax
0x14003847f  jb      short loc_1400384CB
0x140038481  mov     rax, 0FFFFF6FB7DBED800h
0x14003848b  mov     rax, rax
0x14003848e  xor     r13d, r13d
0x140038491  cmp     rdi, rax
0x140038494  jnb     short loc_1400384CE
0x140038496  mov     rax, gs:8
0x14003849f  test    rax, rax
0x1400384a2  jz      short loc_1400384AA
0x1400384a4  mov     rcx, [rax+50h]
0x1400384a8  jmp     short loc_1400384AD
0x1400384aa  mov     rcx, r13
0x1400384ad  mov     rdx, [rcx+0E8h]
0x1400384b4  test    rdx, rdx
0x1400384b7  jz      short loc_1400384CE
0x1400384b9  mov     rax, rdi
0x1400384bc  sar     rax, 3
0x1400384c0  and     eax, 1FFh
0x1400384c5  mov     [rdx+rax*8], r13
0x1400384c9  jmp     short loc_1400384CE
0x1400384cb  xor     r13d, r13d
0x1400384ce  lea     r8, [rsp+1E0h+var_170]
0x1400384d3  mov     [rdi], r13
0x1400384d6  mov     rdx, r14
  ... truncated ...
```
