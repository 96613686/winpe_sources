# SkmiQuerySecurePteAccessState

- ea: `0x14001f578`
- end: `0x14001fa5a`
- name: `SkmiQuerySecurePteAccessState`
- size: `1250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x140002410`
- `0x140002ef0`
- `0x140003780`
- `0x140009890`
- `0x14000e130`
- `0x14000e460`
- `0x14000ff70`
- `0x1400117d4`
- `0x14001f578`
- `0x1400202b0`
- `0x1400202ec`
- `0x140020360`
- `0x140020424`
- `0x140024fac`
- `0x14002b534`
- `0x1400801fc`
- `0x140081290`
- `0x1400a1950`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiQuerySecurePteAccessState(unsigned __int64 a1, char a2, __int64 a3)
{
  __int64 v3; // r15
  char v5; // r13
  __int64 result; // rax
  __int64 DataTraceEntry; // rcx
  _DWORD *v8; // r14
  __int64 v9; // rdi
  __int64 v10; // rsi
  char v11; // bl
  __int64 v12; // r9
  unsigned int v13; // r12d
  __int64 v14; // rax
  __int64 *v15; // r15
  int v16; // edx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rcx
  __int64 Address; // rax
  unsigned __int64 *ValidPteAddress; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int64 v23; // r11
  volatile signed __int64 *v24; // r10
  unsigned __int64 v25; // rsi
  signed __int64 v26; // r9
  signed __int64 v27; // rax
  unsigned __int64 v28; // rbx
  __int64 PteTrace; // rax
  USHORT v30; // ax
  __int64 v31; // rdx
  unsigned __int64 v32; // rax
  __int64 InstructionPointer; // rax
  int v34; // edx
  unsigned __int64 v35; // rsi
  __int64 v36; // rdx
  __int64 v37; // rdx
  int v38; // [rsp+30h] [rbp-D0h]
  __int64 v39; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v40; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v41; // [rsp+48h] [rbp-B8h]
  unsigned __int8 CurrentIrql; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  ULONG BackTraceHash[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v45[256]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v46; // [rsp+170h] [rbp+70h]
  __int16 v47; // [rsp+174h] [rbp+74h]
  _UNKNOWN *retaddr; // [rsp+1B8h] [rbp+B8h]
  _DWORD *v51; // [rsp+1D8h] [rbp+D8h] BYREF

  v3 = a3;
  memset_0(v45, 0, 0x108u);
  v5 = -1;
  v51 = 0;
  HIBYTE(v47) = -1;
  result = SkobReferenceObjectByHandle(a1, 0, 1, (__int64)&SkpsProcessType, &v51, 0);
  if ( (int)result < 0 )
    return result;
  v8 = v51;
  v9 = 0;
  if ( (*v51 & 0x400) != 0 )
    v10 = 1;
  else
    v10 = SkiAttachProcess(v51);
  v39 = v10;
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(2u);
  if ( (*v8 & 0x400) == 0 )
  {
    SkAcquireSpinLockSharedAtDpcLevel(v8 + 2);
    SkAcquireSpinLockExclusiveAtDpcLevel(v8 + 48);
  }
  v11 = v47;
  LODWORD(v12) = 0;
  v13 = v46;
  v14 = 0;
  v38 = 0;
  LOBYTE(v51) = v47;
  while ( 1 )
  {
    v15 = (__int64 *)(v3 + 8 * v14);
    if ( !*v15 )
      break;
    if ( (*v8 & 0x400) == 0 )
      goto LABEL_26;
    if ( !v9 )
      goto LABEL_20;
    v16 = *(_DWORD *)(v9 + 568);
    v17 = (unsigned __int64)*v15 >> 12;
    v18 = *(unsigned int *)(v9 + 560) | ((unsigned __int64)(v16 & 0xFFF) << 32);
    if ( v17 >= v18 && v17 <= (*(unsigned int *)(v9 + 564) | ((unsigned __int64)(v16 & 0xFFF000) << 20)) )
      goto LABEL_26;
    if ( v11 )
    {
      LOBYTE(v18) = v5;
      SkeFlushEntireTb(v18, v9);
LABEL_18:
      LODWORD(v12) = 0;
      goto LABEL_19;
    }
    if ( v13 )
    {
      LOBYTE(v18) = v5;
      SkeFlushRangeListTb(v18, v9, v13, v45);
      goto LABEL_18;
    }
LABEL_19:
    *(_DWORD *)(v9 + 192) = v12;
    SkTrackSpinLockRelease();
    _InterlockedDecrement((volatile signed __int32 *)(v9 + 8));
    SkTrackSpinLockRelease();
    SkiAttachProcess(v10);
    SkobDereferenceObject(v9);
    v13 = 0;
    v47 = -256;
    v11 = 0;
    v46 = 0;
    LOBYTE(v51) = 0;
    v5 = -1;
LABEL_20:
    SkAcquireSpinLockExclusiveAtDpcLevel(v8 + 30);
    Address = SkmiLocateAddress(v8, (unsigned __int64)*v15 >> 12);
    if ( Address )
    {
      v9 = Address - 536;
      SkobReferenceObject(Address - 536);
    }
    else
    {
      v9 = 0;
    }
    v8[30] = 0;
    SkTrackSpinLockRelease();
    LODWORD(v12) = 0;
    if ( !v9 )
    {
      *v15 |= 2uLL;
      goto LABEL_54;
    }
    v39 = SkiAttachProcess(v9);
    SkAcquireSpinLockSharedAtDpcLevel(v9 + 8);
    SkAcquireSpinLockExclusiveAtDpcLevel(v9 + 192);
LABEL_26:
    v41 = *v15 & 0xFFFFFFFFFFFFF000uLL;
    ValidPteAddress = (unsigned __int64 *)SkmiGetValidPteAddress(v41, 0);
    v40 = ValidPteAddress;
    v24 = (volatile signed __int64 *)ValidPteAddress;
    if ( !ValidPteAddress )
    {
      *v15 = v22 | 2;
LABEL_28:
      LODWORD(v12) = 0;
      goto LABEL_54;
    }
    v25 = *ValidPteAddress;
    v12 = 0;
    if ( a2 )
    {
      while ( (v25 & 1) != 0 && (v25 & 0x20) != 0 )
      {
        DataTraceEntry = SkmiAllocateDataTraceEntry(0, v24, v21, v25 & 0xFFFFFFFFFFFFFFDFuLL);
        v27 = _InterlockedCompareExchange64(v24, v26, v25);
        v28 = v27;
        if ( DataTraceEntry && v27 == v25 )
        {
          PteTrace = SkmiGetPteTrace(DataTraceEntry, (_DWORD)v24, 0, v26, v25);
          v12 = 0;
          v43 = PteTrace;
          if ( PteTrace )
          {
            memset_0((void *)(PteTrace + 32), 0, 0x40u);
            v12 = 0;
            if ( (SkmiFlags & 0x400000) != 0 )
            {
              DataTraceEntry = (__int64)KeGetPcr()->NtTib.StackBase;
              if ( DataTraceEntry )
              {
                v30 = RtlCaptureStackBackTrace(DataTraceEntry, 8u, (PVOID *)(v43 + 32), BackTraceHash);
                v12 = 0;
                if ( !v30 )
                {
                  *(_QWORD *)(v43 + 40) = retaddr;
                  InstructionPointer = SkmiGetInstructionPointer(v43, v31);
                  *(_QWORD *)(DataTraceEntry + 32) = InstructionPointer;
                  v25 = v28;
LABEL_43:
                  v23 = v41;
                  v34 = 1;
                  goto LABEL_46;
                }
              }
            }
            v24 = (volatile signed __int64 *)v40;
          }
        }
        else
        {
          v12 = 0;
        }
        v32 = v25;
        v25 = v28;
        if ( v28 == v32 )
          goto LABEL_43;
      }
      v23 = v41;
    }
    v34 = 0;
LABEL_46:
    if ( (v25 & 1) != 0 )
    {
      v35 = *v15 & 0xFFFFFFFFFFFFFFFEuLL | (v25 >> 5) & 1;
    }
    else
    {
      DataTraceEntry = *v15;
      if ( (v25 & 2) != 0 )
        v35 = DataTraceEntry | 2;
      else
        v35 = (v25 >> 14) ^ (DataTraceEntry ^ (v25 >> 14)) & 0xFFFFFFFFFFFFFFFEuLL;
    }
    *v15 = v35;
    if ( v34 )
    {
      SkmiBatchFlushSingleTb(v23, v45, v21, v12);
      v5 = HIBYTE(v47);
      v11 = v47;
      v13 = v46;
      LOBYTE(v51) = v47;
      goto LABEL_28;
    }
    v11 = (char)v51;
LABEL_54:
    v3 = a3;
    v14 = (unsigned int)(v38 + 1);
    v38 = v14;
    if ( (unsigned int)v14 >= 0xB )
      break;
    v10 = v39;
  }
  if ( !v9 )
  {
    if ( (*v8 & 0x400) != 0 )
    {
      LOBYTE(DataTraceEntry) = CurrentIrql;
      SkeLowerIrql(DataTraceEntry);
      goto LABEL_70;
    }
    if ( v11 )
    {
      LOBYTE(DataTraceEntry) = v5;
      SkeFlushEntireTb(DataTraceEntry, v8);
    }
    else
    {
      if ( !v13 )
      {
LABEL_68:
        v8[48] = v12;
        SkTrackSpinLockRelease();
        LOBYTE(v37) = CurrentIrql;
        RtlpReleasePropStoreLockShared(v8 + 2, v37);
        SkiAttachProcess(v39);
        goto LABEL_70;
      }
      LOBYTE(DataTraceEntry) = v5;
      SkeFlushRangeListTb(DataTraceEntry, v8, v13, v45);
    }
    LODWORD(v12) = 0;
    goto LABEL_68;
  }
  if ( v11 )
  {
    LOBYTE(DataTraceEntry) = v5;
    SkeFlushEntireTb(DataTraceEntry, v9);
    goto LABEL_60;
  }
  if ( v13 )
  {
    LOBYTE(DataTraceEntry) = v5;
    SkeFlushRangeListTb(DataTraceEntry, v9, v13, v45);
LABEL_60:
    LODWORD(v12) = 0;
  }
  *(_DWORD *)(v9 + 192) = v12;
  SkTrackSpinLockRelease();
  LOBYTE(v36) = CurrentIrql;
  RtlpReleasePropStoreLockShared(v9 + 8, v36);
  SkiAttachProcess(v39);
  SkobDereferenceObject(v9);
LABEL_70:
  SkobDereferenceObject((__int64)v8);
  return 0;
}

```

## disassembly

```asm
0x14001f578  mov     [rsp-8+arg_0], rbx
0x14001f57d  mov     [rsp-8+arg_10], r8
0x14001f582  mov     [rsp-8+arg_8], dl
0x14001f586  push    rbp
0x14001f587  push    rsi
0x14001f588  push    rdi
0x14001f589  push    r12
0x14001f58b  push    r13
0x14001f58d  push    r14
0x14001f58f  push    r15
0x14001f591  lea     rbp, [rsp-80h]
0x14001f596  sub     rsp, 180h
0x14001f59d  mov     r15, r8
0x14001f5a0  mov     rbx, rcx
0x14001f5a3  mov     r8d, 108h; Size
0x14001f5a9  lea     rcx, [rsp+1B0h+var_140]; void *
0x14001f5ae  xor     edx, edx; Val
0x14001f5b0  call    memset_0
0x14001f5b5  lea     rax, [rbp+0B0h+arg_18]
0x14001f5bc  mov     [rsp+1B0h+var_188], 0
0x14001f5c5  mov     r13b, 0FFh
0x14001f5c8  mov     [rsp+1B0h+var_190], rax
0x14001f5cd  lea     r9, SkpsProcessType
0x14001f5d4  mov     [rbp+0B0h+arg_18], 0
0x14001f5df  mov     r8b, 1
0x14001f5e2  mov     byte ptr [rbp+0B0h+var_3C+1], r13b
0x14001f5e6  xor     edx, edx
0x14001f5e8  mov     rcx, rbx
0x14001f5eb  call    SkobReferenceObjectByHandle
0x14001f5f0  test    eax, eax
0x14001f5f2  js      loc_14001FA3E
0x14001f5f8  mov     r14, [rbp+0B0h+arg_18]
0x14001f5ff  xor     edi, edi
0x14001f601  test    dword ptr [r14], 400h
0x14001f608  jz      short loc_14001F60F
0x14001f60a  lea     esi, [rdi+1]
0x14001f60d  jmp     short loc_14001F61A
0x14001f60f  mov     rcx, r14
0x14001f612  call    SkiAttachProcess
0x14001f617  mov     rsi, rax
0x14001f61a  mov     [rsp+1B0h+var_178], rsi
0x14001f61f  mov     rax, cr8
0x14001f623  mov     [rsp+1B0h+var_160], rax
0x14001f628  mov     r10d, 2
0x14001f62e  mov     cr8, r10
0x14001f632  test    dword ptr [r14], 400h
0x14001f639  jnz     short loc_14001F650
0x14001f63b  lea     rcx, [r14+8]
0x14001f63f  call    SkAcquireSpinLockSharedAtDpcLevel
0x14001f644  lea     rcx, [r14+0C0h]
0x14001f64b  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14001f650  mov     bl, byte ptr [rbp+0B0h+var_3C]
0x14001f653  xor     r9d, r9d
0x14001f656  mov     r12d, [rbp+0B0h+var_40]
0x14001f65a  mov     eax, r9d
0x14001f65d  mov     [rsp+1B0h+var_180], eax
0x14001f661  mov     byte ptr [rbp+0B0h+arg_18], bl
0x14001f667  jmp     short loc_14001F66E
0x14001f669  mov     rsi, [rsp+1B0h+var_178]
0x14001f66e  lea     r15, [r15+rax*8]
0x14001f672  mov     r8, [r15]
0x14001f675  test    r8, r8
0x14001f678  jz      loc_14001F973
0x14001f67e  test    dword ptr [r14], 400h
0x14001f685  jz      loc_14001F7AD
0x14001f68b  test    rdi, rdi
0x14001f68e  jz      loc_14001F73D
0x14001f694  mov     edx, [rdi+238h]
0x14001f69a  mov     eax, [rdi+230h]
0x14001f6a0  mov     ecx, edx
0x14001f6a2  and     ecx, 0FFFh
0x14001f6a8  shr     r8, 0Ch
0x14001f6ac  shl     rcx, 20h
0x14001f6b0  or      rcx, rax
0x14001f6b3  cmp     r8, rcx
0x14001f6b6  jb      short loc_14001F6D4
0x14001f6b8  mov     eax, [rdi+234h]
0x14001f6be  and     edx, 0FFF000h
0x14001f6c4  shl     rdx, 14h
0x14001f6c8  or      rdx, rax
0x14001f6cb  cmp     r8, rdx
0x14001f6ce  jbe     loc_14001F7AD
0x14001f6d4  test    bl, bl
0x14001f6d6  jz      short loc_14001F6E5
0x14001f6d8  mov     rdx, rdi
0x14001f6db  mov     cl, r13b
0x14001f6de  call    SkeFlushEntireTb
0x14001f6e3  jmp     short loc_14001F6FD
0x14001f6e5  test    r12d, r12d
0x14001f6e8  jz      short loc_14001F700
0x14001f6ea  lea     r9, [rsp+1B0h+var_140]
0x14001f6ef  mov     r8d, r12d
0x14001f6f2  mov     rdx, rdi
0x14001f6f5  mov     cl, r13b
0x14001f6f8  call    SkeFlushRangeListTb
0x14001f6fd  xor     r9d, r9d
0x14001f700  mov     [rdi+0C0h], r9d
0x14001f707  call    SkTrackSpinLockRelease
0x14001f70c  lock dec dword ptr [rdi+8]
0x14001f710  call    SkTrackSpinLockRelease
0x14001f715  mov     rcx, rsi
0x14001f718  call    SkiAttachProcess
0x14001f71d  mov     rcx, rdi
0x14001f720  call    SkobDereferenceObject
0x14001f725  xor     r12d, r12d
0x14001f728  mov     [rbp+0B0h+var_3C], 0FF00h
0x14001f72e  xor     bl, bl
0x14001f730  mov     [rbp+0B0h+var_40], r12d
0x14001f734  mov     byte ptr [rbp+0B0h+arg_18], bl
0x14001f73a  mov     r13b, 0FFh
0x14001f73d  lea     rcx, [r14+78h]
0x14001f741  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14001f746  mov     rdx, [r15]
0x14001f749  mov     rcx, r14
0x14001f74c  shr     rdx, 0Ch
0x14001f750  call    SkmiLocateAddress
0x14001f755  test    rax, rax
0x14001f758  jnz     short loc_14001F75E
0x14001f75a  xor     edi, edi
0x14001f75c  jmp     short loc_14001F76D
0x14001f75e  lea     rdi, [rax-218h]
0x14001f765  mov     rcx, rdi
0x14001f768  call    SkobReferenceObject
0x14001f76d  mov     dword ptr [r14+78h], 0
0x14001f775  call    SkTrackSpinLockRelease
0x14001f77a  xor     r9d, r9d
0x14001f77d  test    rdi, rdi
0x14001f780  jnz     short loc_14001F78B
0x14001f782  or      qword ptr [r15], 2
0x14001f786  jmp     loc_14001F959
0x14001f78b  mov     rcx, rdi
0x14001f78e  call    SkiAttachProcess
0x14001f793  lea     rcx, [rdi+8]
0x14001f797  mov     [rsp+1B0h+var_178], rax
0x14001f79c  call    SkAcquireSpinLockSharedAtDpcLevel
0x14001f7a1  lea     rcx, [rdi+0C0h]
0x14001f7a8  call    SkAcquireSpinLockExclusiveAtDpcLevel
0x14001f7ad  mov     r9, [r15]
0x14001f7b0  xor     edx, edx
0x14001f7b2  mov     r11, r9
0x14001f7b5  and     r11, 0FFFFFFFFFFFFF000h
0x14001f7bc  mov     rcx, r11
0x14001f7bf  mov     [rsp+1B0h+var_168], r11
0x14001f7c4  call    SkmiGetValidPteAddress
0x14001f7c9  mov     [rsp+1B0h+var_170], rax
0x14001f7ce  mov     r10, rax
0x14001f7d1  test    rax, rax
0x14001f7d4  jnz     short loc_14001F7E5
0x14001f7d6  or      r9, 2
0x14001f7da  mov     [r15], r9
0x14001f7dd  xor     r9d, r9d
0x14001f7e0  jmp     loc_14001F959
0x14001f7e5  mov     rsi, [rax]
0x14001f7e8  xor     r9d, r9d
0x14001f7eb  cmp     [rbp+0B0h+arg_8], r9b
0x14001f7f2  jz      loc_14001F8E6
0x14001f7f8  test    sil, 1
0x14001f7fc  jz      loc_14001F8E1
0x14001f802  test    sil, 20h
0x14001f806  jz      loc_14001F8E1
0x14001f80c  mov     r9, rsi
0x14001f80f  mov     rdx, r10
0x14001f812  and     r9, 0FFFFFFFFFFFFFFDFh
0x14001f816  xor     ecx, ecx
0x14001f818  call    SkmiAllocateDataTraceEntry
0x14001f81d  mov     rcx, rax
0x14001f820  mov     rax, rsi
0x14001f823  lock cmpxchg [r10], r9
0x14001f828  mov     rbx, rax
0x14001f82b  test    rcx, rcx
0x14001f82e  jz      short loc_14001F8A5
0x14001f830  cmp     rax, rsi
0x14001f833  jnz     short loc_14001F8A5
0x14001f835  xor     r8d, r8d
0x14001f838  mov     [rsp+1B0h+var_190], rsi
0x14001f83d  mov     rdx, r10
0x14001f840  call    SkmiGetPteTrace
0x14001f845  xor     r9d, r9d
0x14001f848  mov     [rsp+1B0h+var_158], rax
0x14001f84d  test    rax, rax
0x14001f850  jz      short loc_14001F8A8
0x14001f852  lea     rcx, [rax+20h]; void *
0x14001f856  xor     edx, edx; Val
0x14001f858  lea     r8d, [r9+40h]; Size
0x14001f85c  call    memset_0
0x14001f861  xor     r9d, r9d
0x14001f864  test    cs:SkmiFlags, 400000h
0x14001f86e  jz      short loc_14001F89E
0x14001f870  mov     rcx, gs:8; FramesToSkip
0x14001f879  test    rcx, rcx
0x14001f87c  jz      short loc_14001F89E
0x14001f87e  mov     r8, [rsp+1B0h+var_158]
0x14001f883  lea     r9, [rsp+1B0h+BackTraceHash]; BackTraceHash
0x14001f888  add     r8, 20h ; ' '; BackTrace
0x14001f88c  mov     edx, 8; FramesToCapture
0x14001f891  call    RtlCaptureStackBackTrace
0x14001f896  xor     r9d, r9d
0x14001f899  test    ax, ax
0x14001f89c  jz      short loc_14001F8B9
0x14001f89e  mov     r10, [rsp+1B0h+var_170]
0x14001f8a3  jmp     short loc_14001F8A8
0x14001f8a5  xor     r9d, r9d
0x14001f8a8  mov     rax, rsi
0x14001f8ab  mov     rsi, rbx
0x14001f8ae  cmp     rbx, rax
0x14001f8b1  jnz     loc_14001F7F8
0x14001f8b7  jmp     short loc_14001F8D5
0x14001f8b9  mov     rax, [rbp+0B8h]
0x14001f8c0  mov     rcx, [rsp+1B0h+var_158]
0x14001f8c5  mov     [rcx+28h], rax
0x14001f8c9  call    SkmiGetInstructionPointer
0x14001f8ce  mov     [rcx+20h], rax
0x14001f8d2  mov     rsi, rbx
0x14001f8d5  mov     r11, [rsp+1B0h+var_168]
0x14001f8da  mov     edx, 1
0x14001f8df  jmp     short loc_14001F8E9
0x14001f8e1  mov     r11, [rsp+1B0h+var_168]
0x14001f8e6  mov     edx, r9d
0x14001f8e9  test    sil, 1
0x14001f8ed  jz      short loc_14001F902
0x14001f8ef  mov     rax, [r15]
0x14001f8f2  shr     rsi, 5
0x14001f8f6  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001f8fa  and     esi, 1
0x14001f8fd  or      rsi, rax
0x14001f900  jmp     short loc_14001F929
0x14001f902  mov     rcx, [r15]
0x14001f905  mov     r10d, 2
0x14001f90b  test    r10b, sil
0x14001f90e  jnz     short loc_14001F923
0x14001f910  shr     rsi, 0Eh
0x14001f914  mov     rax, rsi
0x14001f917  xor     rsi, rcx
0x14001f91a  and     rsi, 0FFFFFFFFFFFFFFFEh
0x14001f91e  xor     rsi, rax
0x14001f921  jmp     short loc_14001F929
0x14001f923  mov     rsi, rcx
0x14001f926  or      rsi, r10
0x14001f929  mov     [r15], rsi
0x14001f92c  test    edx, edx
0x14001f92e  jz      short loc_14001F953
0x14001f930  lea     rdx, [rsp+1B0h+var_140]
0x14001f935  mov     rcx, r11
0x14001f938  call    SkmiBatchFlushSingleTb
0x14001f93d  mov     bl, byte ptr [rbp+0B0h+var_3C]
0x14001f940  mov     r13b, byte ptr [rbp+0B0h+var_3C+1]
0x14001f944  mov     r12d, [rbp+0B0h+var_40]
0x14001f948  mov     byte ptr [rbp+0B0h+arg_18], bl
0x14001f94e  jmp     loc_14001F7DD
0x14001f953  mov     bl, byte ptr [rbp+0B0h+arg_18]
0x14001f959  mov     eax, [rsp+1B0h+var_180]
0x14001f95d  mov     r15, [rbp+0B0h+arg_10]
0x14001f964  inc     eax
0x14001f966  mov     [rsp+1B0h+var_180], eax
0x14001f96a  cmp     eax, 0Bh
0x14001f96d  jb      loc_14001F669
0x14001f973  test    rdi, rdi
0x14001f976  jz      short loc_14001F9D1
0x14001f978  test    bl, bl
0x14001f97a  jz      short loc_14001F989
0x14001f97c  mov     rdx, rdi
0x14001f97f  mov     cl, r13b
0x14001f982  call    SkeFlushEntireTb
0x14001f987  jmp     short loc_14001F9A1
0x14001f989  test    r12d, r12d
0x14001f98c  jz      short loc_14001F9A4
0x14001f98e  lea     r9, [rsp+1B0h+var_140]
0x14001f993  mov     r8d, r12d
0x14001f996  mov     rdx, rdi
0x14001f999  mov     cl, r13b
0x14001f99c  call    SkeFlushRangeListTb
0x14001f9a1  xor     r9d, r9d
0x14001f9a4  mov     [rdi+0C0h], r9d
0x14001f9ab  call    SkTrackSpinLockRelease
0x14001f9b0  mov     dl, byte ptr [rsp+1B0h+var_160]
0x14001f9b4  lea     rcx, [rdi+8]
0x14001f9b8  call    RtlpReleasePropStoreLockShared
0x14001f9bd  mov     rcx, [rsp+1B0h+var_178]
0x14001f9c2  call    SkiAttachProcess
0x14001f9c7  mov     rcx, rdi
0x14001f9ca  call    SkobDereferenceObject
0x14001f9cf  jmp     short loc_14001FA34
0x14001f9d1  test    dword ptr [r14], 400h
0x14001f9d8  jnz     short loc_14001FA2B
0x14001f9da  test    bl, bl
0x14001f9dc  jz      short loc_14001F9EB
0x14001f9de  mov     rdx, r14
0x14001f9e1  mov     cl, r13b
0x14001f9e4  call    SkeFlushEntireTb
0x14001f9e9  jmp     short loc_14001FA03
0x14001f9eb  test    r12d, r12d
0x14001f9ee  jz      short loc_14001FA06
0x14001f9f0  lea     r9, [rsp+1B0h+var_140]
0x14001f9f5  mov     r8d, r12d
0x14001f9f8  mov     rdx, r14
0x14001f9fb  mov     cl, r13b
0x14001f9fe  call    SkeFlushRangeListTb
0x14001fa03  xor     r9d, r9d
0x14001fa06  mov     [r14+0C0h], r9d
0x14001fa0d  call    SkTrackSpinLockRelease
  ... truncated ...
```
