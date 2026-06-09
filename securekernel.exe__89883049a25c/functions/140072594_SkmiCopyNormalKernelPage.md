# SkmiCopyNormalKernelPage

- ea: `0x140072594`
- end: `0x14007287c`
- name: `SkmiCopyNormalKernelPage`
- size: `744`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter3@<rcx>, ULONG BackTraceHash, char)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400111d0`

## callees

- `0x140003780`
- `0x140008ec4`
- `0x1400091e0`
- `0x14000b980`
- `0x14000d020`
- `0x14000e810`
- `0x14000ff70`
- `0x140010b90`
- `0x1400130a0`
- `0x140013bf8`
- `0x140014c80`
- `0x1400202b0`
- `0x1400276d8`
- `0x14002b534`
- `0x140050ba4`
- `0x140072594`
- `0x14007357c`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCopyNormalKernelPage(
        ULONG_PTR BugCheckParameter3,
        __int64 a2,
        ULONG_PTR a3,
        __int64 a4,
        __int64 BackTraceHash,
        char a6)
{
  __int64 v6; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  char v14; // r12
  volatile signed __int64 *ValidNteAddress; // rax
  volatile signed __int64 *v16; // r14
  __int64 *p_BackTraceHash; // r9
  __int64 v18; // r8
  __int64 v19; // rdx
  unsigned int v20; // edi
  unsigned __int64 v21; // rsi
  __int64 v22; // rcx
  bool v23; // zf
  signed __int64 v24; // rax
  unsigned int v25; // r8d
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int64 v29; // rdi
  __int64 PteTrace; // rax
  __int64 v31; // rdx
  PVOID StackBase; // rcx
  __int64 v33; // r13
  PVOID *v34; // rsi
  __int64 v35; // rcx
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v6 = BackTraceHash;
  if ( BackTraceHash )
  {
    BackTraceHash >>= 12;
    if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&BackTraceHash, 1, 0x8001u) )
    {
      SKMI_PAGE_SECURITY(322, v6 >> 12, 0, 0);
      return 3221225539LL;
    }
  }
  v14 = SkAcquireSpinLockShared(&SkmiNteLock);
  if ( a4 == a2 && a6 )
  {
    ValidNteAddress = (volatile signed __int64 *)SkmiGetValidNteAddress(a2, v12, v13);
    v16 = ValidNteAddress;
    if ( ValidNteAddress )
    {
      _m_prefetchw((const void *)ValidNteAddress);
LABEL_10:
      v21 = *v16;
      BackTraceHash = *v16;
      do
      {
        if ( (v21 & 0x801) != 1 && (v21 & 0x100) == 0
          || (v21 & 0x200) == 0
          || ((v21 >> 12) & 0xFFFFFFFFFFLL) != BugCheckParameter3 )
        {
          p_BackTraceHash = &BackTraceHash;
          v18 = (__int64)v16;
          goto LABEL_8;
        }
        if ( (v21 & 0x400) != 0 )
        {
          _mm_pause();
          goto LABEL_10;
        }
        v22 = v21 | 0x400;
        v24 = _InterlockedCompareExchange64(v16, v21 | 0x400, v21);
        v23 = v21 == v24;
        v21 = v24;
        BackTraceHash = v24;
      }
      while ( !v23 );
      _InterlockedDecrement(&SkmiNteLock);
      SkTrackSpinLockRelease(v22, 1024);
      if ( (v21 & 0x800) != 0 && (v21 & 0x100) != 0 )
        v25 = 1;
      else
        v25 = 5;
      BackTraceHash = a3;
      SkmiClaimPhysicalPages((ULONG_PTR)&BackTraceHash, 1, v25);
      SkmiCopyPhysicalPage(BugCheckParameter3, a3);
      if ( (SkmiFlags & 0x10) != 0 && ((v21 & 0x800) == 0 || (v21 & 0x100) == 0) )
        SkmiProtectSinglePage(a3);
      v29 = (a3 << 12) ^ (v21 ^ (a3 << 12)) & 0xFFF0000000000FFFuLL;
      SkmiAcquireNteAssertionLock(0xFFF0000000000FFFuLL, v26, v27, v28);
      PteTrace = SkmiGetPteTrace(0, (_DWORD)v16, 0, ((_DWORD)a3 << 12) ^ (v21 ^ ((_DWORD)a3 << 12)) & 0xFFF, *v16);
      v33 = PteTrace;
      if ( PteTrace )
      {
        v34 = (PVOID *)(PteTrace + 32);
        memset_0((void *)(PteTrace + 32), 0, 0x40u);
        if ( (SkmiFlags & 0x400000) != 0 )
        {
          StackBase = KeGetPcr()->NtTib.StackBase;
          if ( StackBase )
          {
            if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v34, (PULONG)&BackTraceHash) )
            {
              *(_QWORD *)(v33 + 40) = retaddr;
              *v34 = (PVOID)SkmiGetInstructionPointer(StackBase, v31);
            }
          }
        }
      }
      *v16 = v29;
      if ( v6 )
        SkmiUpdateNormalPte(v6, v31, a3);
      LOBYTE(StackBase) = 2;
      SkmiReleaseNteAssertionLock(StackBase);
      if ( (v29 & 0x900) == 0x900 )
        SkmiDecrementPageReferenceCount(BugCheckParameter3);
      else
        SkmiReleasePhysicalPage(BugCheckParameter3);
      v20 = 0;
      if ( v14 != -1 )
      {
        LOBYTE(v35) = v14;
        SkeLowerIrql(v35);
      }
      goto LABEL_41;
    }
    p_BackTraceHash = 0;
    v18 = 0;
LABEL_8:
    SKMI_PAGE_SECURITY(259, BugCheckParameter3, v18, p_BackTraceHash);
    v20 = -1073741819;
  }
  else
  {
    SKMI_SECURITY(282);
    v20 = -1073741811;
  }
  LOBYTE(v19) = v14;
  RtlpReleasePropStoreLockShared(&SkmiNteLock, v19);
LABEL_41:
  if ( v6 )
    SkmiDecrementPageReferenceCount(v6 >> 12);
  return v20;
}

```

## disassembly

```asm
0x140072594  mov     rax, rsp
0x140072597  push    rbx
0x140072598  push    rbp
0x140072599  push    rsi
0x14007259a  push    rdi
0x14007259b  push    r12
0x14007259d  push    r13
0x14007259f  push    r14
0x1400725a1  push    r15
0x1400725a3  sub     rsp, 38h
0x1400725a7  mov     rbx, [rsp+78h+BackTraceHash]
0x1400725af  xor     r13d, r13d
0x1400725b2  mov     r14, r9
0x1400725b5  mov     r15, r8
0x1400725b8  mov     rsi, rdx
0x1400725bb  mov     rbp, rcx
0x1400725be  test    rbx, rbx
0x1400725c1  jz      short loc_140072602
0x1400725c3  mov     rdi, rbx
0x1400725c6  lea     edx, [r13+1]
0x1400725ca  sar     rdi, 0Ch
0x1400725ce  lea     rcx, [rax+28h]
0x1400725d2  mov     r8d, 8001h
0x1400725d8  mov     [rax+28h], rdi
0x1400725dc  call    SkmiClaimPhysicalPages
0x1400725e1  test    eax, eax
0x1400725e3  jnz     short loc_140072602
0x1400725e5  xor     r9d, r9d
0x1400725e8  xor     r8d, r8d
0x1400725eb  mov     rdx, rdi
0x1400725ee  mov     ecx, 142h
0x1400725f3  call    SKMI_PAGE_SECURITY
0x1400725f8  mov     eax, 0C0000043h
0x1400725fd  jmp     loc_14007286A
0x140072602  lea     rcx, SkmiNteLock
0x140072609  call    SkAcquireSpinLockShared
0x14007260e  mov     r12b, al
0x140072611  cmp     r14, rsi
0x140072614  jnz     loc_140072839
0x14007261a  cmp     [rsp+78h+arg_28], r13b
0x140072622  jz      loc_140072839
0x140072628  mov     rcx, rsi
0x14007262b  call    SkmiGetValidNteAddress
0x140072630  mov     r14, rax
0x140072633  test    rax, rax
0x140072636  jnz     short loc_140072655
0x140072638  xor     r9d, r9d
0x14007263b  xor     r8d, r8d
0x14007263e  mov     rdx, rbp
0x140072641  mov     ecx, 103h
0x140072646  call    SKMI_PAGE_SECURITY
0x14007264b  mov     edi, 0C0000005h
0x140072650  jmp     loc_140072848
0x140072655  prefetchw byte ptr [rax]
0x140072658  mov     edx, 400h
0x14007265d  mov     rsi, [r14]
0x140072660  mov     [rsp+78h+BackTraceHash], rsi
0x140072668  mov     rax, rsi
0x14007266b  and     eax, 801h
0x140072670  cmp     rax, 1
0x140072674  jz      short loc_140072681
0x140072676  bt      rsi, 8
0x14007267b  jnb     loc_140072829
0x140072681  bt      rsi, 9
0x140072686  jnb     loc_140072829
0x14007268c  mov     rcx, rsi
0x14007268f  mov     rax, 0FFFFFFFFFFh
0x140072699  shr     rcx, 0Ch
0x14007269d  and     rcx, rax
0x1400726a0  cmp     rcx, rbp
0x1400726a3  jnz     loc_140072829
0x1400726a9  test    rdx, rsi
0x1400726ac  jnz     short loc_1400726F1
0x1400726ae  mov     rcx, rsi
0x1400726b1  mov     rax, rsi
0x1400726b4  or      rcx, rdx
0x1400726b7  lock cmpxchg [r14], rcx
0x1400726bc  mov     rsi, rax
0x1400726bf  mov     [rsp+78h+BackTraceHash], rax
0x1400726c7  jnz     short loc_140072668
0x1400726c9  lock dec cs:SkmiNteLock
0x1400726d0  call    SkTrackSpinLockRelease
0x1400726d5  mov     rdi, rsi
0x1400726d8  and     edi, 800h
0x1400726de  jz      short loc_1400726F8
0x1400726e0  bt      rsi, 8
0x1400726e5  jnb     short loc_1400726F8
0x1400726e7  mov     edx, 1
0x1400726ec  mov     r8d, edx
0x1400726ef  jmp     short loc_140072701
0x1400726f1  pause
0x1400726f3  jmp     loc_14007265D
0x1400726f8  mov     edx, 1
0x1400726fd  lea     r8d, [rdx+4]
0x140072701  lea     rcx, [rsp+78h+BackTraceHash]
0x140072709  mov     [rsp+78h+BackTraceHash], r15
0x140072711  call    SkmiClaimPhysicalPages
0x140072716  mov     rdx, r15
0x140072719  mov     rcx, rbp
0x14007271c  call    SkmiCopyPhysicalPage
0x140072721  mov     eax, cs:SkmiFlags
0x140072727  test    al, 10h
0x140072729  jz      short loc_140072744
0x14007272b  test    rdi, rdi
0x14007272e  jz      short loc_140072737
0x140072730  bt      rsi, 8
0x140072735  jb      short loc_140072744
0x140072737  mov     edx, 2
0x14007273c  mov     rcx, r15; BugCheckParameter3
0x14007273f  call    SkmiProtectSinglePage
0x140072744  mov     rcx, 0FFF0000000000FFFh
0x14007274e  mov     rax, r15
0x140072751  shl     rax, 0Ch
0x140072755  mov     rdi, rax
0x140072758  xor     rdi, rsi
0x14007275b  and     rdi, rcx
0x14007275e  xor     rdi, rax
0x140072761  call    SkmiAcquireNteAssertionLock
0x140072766  mov     rax, [r14]
0x140072769  mov     r9, rdi
0x14007276c  xor     r8d, r8d
0x14007276f  mov     [rsp+78h+var_58], rax
0x140072774  mov     rdx, r14
0x140072777  xor     ecx, ecx
0x140072779  call    SkmiGetPteTrace
0x14007277e  mov     r13, rax
0x140072781  test    rax, rax
0x140072784  jz      short loc_1400727DD
0x140072786  xor     edx, edx; Val
0x140072788  lea     rsi, [rax+20h]
0x14007278c  mov     rcx, rsi; void *
0x14007278f  lea     r8d, [rdx+40h]; Size
0x140072793  call    memset_0
0x140072798  test    cs:SkmiFlags, 400000h
0x1400727a2  jz      short loc_1400727DD
0x1400727a4  mov     rcx, gs:8; FramesToSkip
0x1400727ad  test    rcx, rcx
0x1400727b0  jz      short loc_1400727DD
0x1400727b2  lea     r9, [rsp+78h+BackTraceHash]; BackTraceHash
0x1400727ba  mov     r8, rsi; BackTrace
0x1400727bd  mov     edx, 8; FramesToCapture
0x1400727c2  call    RtlCaptureStackBackTrace
0x1400727c7  test    ax, ax
0x1400727ca  jnz     short loc_1400727DD
0x1400727cc  mov     rax, [rsp+78h]
0x1400727d1  mov     [r13+28h], rax
0x1400727d5  call    SkmiGetInstructionPointer
0x1400727da  mov     [rsi], rax
0x1400727dd  xor     r13d, r13d
0x1400727e0  mov     [r14], rdi
0x1400727e3  test    rbx, rbx
0x1400727e6  jz      short loc_1400727F3
0x1400727e8  mov     r8, r15
0x1400727eb  mov     rcx, rbx
0x1400727ee  call    SkmiUpdateNormalPte
0x1400727f3  mov     cl, 2
0x1400727f5  call    SkmiReleaseNteAssertionLock
0x1400727fa  mov     eax, 900h
0x1400727ff  mov     rcx, rbp; BugCheckParameter3
0x140072802  and     rdi, rax
0x140072805  cmp     rdi, rax
0x140072808  jnz     short loc_140072811
0x14007280a  call    SkmiDecrementPageReferenceCount
0x14007280f  jmp     short loc_140072816
0x140072811  call    SkmiReleasePhysicalPage
0x140072816  mov     edi, r13d
0x140072819  cmp     r12b, 0FFh
0x14007281d  jz      short loc_140072857
0x14007281f  mov     cl, r12b
0x140072822  call    SkeLowerIrql
0x140072827  jmp     short loc_140072857
0x140072829  lea     r9, [rsp+78h+BackTraceHash]
0x140072831  mov     r8, r14
0x140072834  jmp     loc_14007263E
0x140072839  mov     ecx, 11Ah
0x14007283e  call    SKMI_SECURITY
0x140072843  mov     edi, 0C000000Dh
0x140072848  mov     dl, r12b
0x14007284b  lea     rcx, SkmiNteLock
0x140072852  call    RtlpReleasePropStoreLockShared
0x140072857  test    rbx, rbx
0x14007285a  jz      short loc_140072868
0x14007285c  sar     rbx, 0Ch
0x140072860  mov     rcx, rbx; BugCheckParameter3
0x140072863  call    SkmiDecrementPageReferenceCount
0x140072868  mov     eax, edi
0x14007286a  add     rsp, 38h
0x14007286e  pop     r15
0x140072870  pop     r14
0x140072872  pop     r13
0x140072874  pop     r12
0x140072876  pop     rdi
0x140072877  pop     rsi
0x140072878  pop     rbp
0x140072879  pop     rbx
0x14007287a  retn
```
