# IumCreateSecureSectionSpecifyPages

- ea: `0x14005c1e0`
- end: `0x14005c72d`
- name: `IumCreateSecureSectionSpecifyPages`
- size: `1357`
- prototype: `__int64 __fastcall(_QWORD *, __int64, void *, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `23`
- tags: ``

## callees

- `0x140002ef0`
- `0x140003780`
- `0x140009940`
- `0x14000c8d0`
- `0x14000f0f0`
- `0x140027540`
- `0x14002b534`
- `0x140033a00`
- `0x14003492c`
- `0x140037e68`
- `0x140037e84`
- `0x140040c7c`
- `0x14005443c`
- `0x14005c1e0`
- `0x14005d8f4`
- `0x140081290`
- `0x1400a1128`
- `0x1400a18a0`
- `0x1400d4e8c`
- `0x1400f2fc0`
- `0x1400f9a80`
- `0x1400fc664`
- `0x1400fc7c0`

## pseudocode

```c
__int64 __fastcall IumCreateSecureSectionSpecifyPages(
        _QWORD *a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7)
{
  void *v7; // r13
  char v9; // r10
  _QWORD *StackBase; // rax
  __int64 v11; // rax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  void *Pool; // r14
  __int64 ULong64FromUser; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rax
  int inited; // r15d
  __int64 v21; // rsi
  __int16 ProtectionMask; // ax
  __int64 v23; // rcx
  int v24; // r8d
  int v25; // eax
  int v26; // r12d
  unsigned __int64 v27; // rbx
  __int64 CurrentIrql; // rax
  __int64 v29; // rcx
  unsigned int v30; // r13d
  __int64 v31; // rcx
  __int64 HyperspacePte; // r12
  __int64 PteTrace; // rax
  PVOID v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 InstructionPointer; // rax
  __int64 v38; // rcx
  unsigned __int64 v39; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  int v43; // edx
  char v44; // [rsp+30h] [rbp-88h]
  bool v45; // [rsp+34h] [rbp-84h]
  ULONG BackTraceHash; // [rsp+38h] [rbp-80h] BYREF
  _OWORD *v47; // [rsp+40h] [rbp-78h] BYREF
  __int64 v48; // [rsp+48h] [rbp-70h] BYREF
  __int64 v49; // [rsp+50h] [rbp-68h]
  void *v50; // [rsp+60h] [rbp-58h]
  __int64 v51; // [rsp+68h] [rbp-50h]
  __int64 v52; // [rsp+70h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+0h]

  v7 = a3;
  v48 = 0;
  v44 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  v9 = v44;
  v47 = 0;
  if ( v44 )
  {
    StackBase = KeGetPcr()->NtTib.StackBase;
    v11 = StackBase ? StackBase[10] : 0LL;
    if ( *(char *)(v11 + 400) >= 0 )
      return 3221225506LL;
  }
  if ( !a4 )
    return 3221225714LL;
  if ( ((a5 - 1) & 0xFFFFFFFC) != 0 )
    return 3221225541LL;
  if ( a5 == 3 )
    return 3221225541LL;
  v13 = a6 - 1;
  if ( (unsigned int)v13 > 0x3F )
    return 3221225541LL;
  v14 = 0x800000008000000BuLL;
  if ( !_bittest64((const __int64 *)&v14, v13) )
    return 3221225541LL;
  if ( (a7 & 0xFFFFFFF0) != 0 || (a7 & 2) != 0 && (a7 & 1) == 0 )
    return 3221225717LL;
  BackTraceHash = a7 & 4;
  if ( (a7 & 4) != 0 && (a7 & 2) == 0 )
    return 3221225717LL;
  v45 = 0;
  v52 = a4;
  if ( v44 )
  {
    v15 = 8LL * a4;
    Pool = (void *)SkAllocatePool(512, v15);
    v50 = Pool;
    if ( !Pool )
      return 3221225626LL;
    ULong64FromUser = RtlReadULong64FromUser(a1);
    RtlWriteULong64ToUser(a1, ULong64FromUser);
    if ( v15 && ((unsigned __int8)v7 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(Pool, v7, v15);
    v9 = v44;
  }
  else
  {
    Pool = a3;
    v50 = a3;
    v19 = KeGetPcr()->NtTib.StackBase;
    if ( v19 )
      v18 = v19[10];
    else
      v18 = 0;
    v45 = v18 == PsIumSystemProcess;
  }
  LOBYTE(v18) = v9;
  inited = SkobCreateObjectEx(v18, &SkmiSectionType, a2, &v47);
  v21 = (__int64)v47;
  if ( inited >= 0 )
  {
    *v47 = 0;
    *(_OWORD *)(v21 + 16) = 0;
    *(_QWORD *)(v21 + 32) = 0;
    *(_DWORD *)v21 = 0x2000;
    *(_DWORD *)v21 = 2 * (SkmiMakeProtectionMask(a5) & 0xF ^ 0x1000);
    ProtectionMask = SkmiMakeProtectionMask(a6);
    v25 = v24 ^ ((unsigned __int16)v24 ^ (unsigned __int16)(ProtectionMask << 9)) & 0x1E00;
    *(_DWORD *)v21 = v25;
    if ( (a7 & 2) != 0 )
    {
      v25 |= 0x20000u;
      v26 = 5;
    }
    else
    {
      if ( (a7 & 1) != 0 )
      {
        v26 = 1;
LABEL_35:
        if ( BackTraceHash )
        {
          v25 |= 0x10000u;
          *(_DWORD *)v21 = v25;
        }
        if ( (a7 & 8) != 0 )
        {
          v26 |= 8u;
          *(_DWORD *)v21 = v25 | 0x200000;
        }
        LOBYTE(v23) = v45;
        inited = SkobReserveHandle(v23, &v48);
        if ( inited >= 0 )
        {
          inited = SkmiInitSpecifyPagesSectionProtoPtes(v21, (_DWORD)Pool, a4, v48, v26);
          if ( inited >= 0 )
          {
            if ( (*(_DWORD *)v21 & 0x10000) != 0 )
            {
              v27 = 0x800000000000007BuLL;
              CurrentIrql = KeGetCurrentIrql();
              v51 = CurrentIrql;
              v29 = 2;
              __writecr8(2u);
              BackTraceHash = 0;
              if ( a4 )
              {
                v30 = 0;
                do
                {
                  v31 = *((_QWORD *)Pool + v30) << 12;
                  v27 = v31 ^ (v31 ^ v27) & 0xFFF0000000000FFFuLL;
                  HyperspacePte = SkmiGetHyperspacePte();
                  PteTrace = SkmiGetPteTrace(0, HyperspacePte, 0, v27, *(_QWORD *)HyperspacePte);
                  v49 = PteTrace;
                  if ( PteTrace )
                  {
                    memset_0((void *)(PteTrace + 32), 0, 0x40u);
                    if ( (SkmiFlags & 0x400000) != 0 )
                    {
                      v34 = KeGetPcr()->NtTib.StackBase;
                      if ( v34 )
                      {
                        if ( !RtlCaptureStackBackTrace((ULONG)v34, 8u, (PVOID *)(v49 + 32), &BackTraceHash) )
                        {
                          v36 = v49;
                          *(_QWORD *)(v49 + 40) = retaddr;
                          InstructionPointer = SkmiGetInstructionPointer(v36, v35);
                          *(_QWORD *)(v38 + 32) = InstructionPointer;
                        }
                      }
                    }
                  }
                  v39 = v27;
                  if ( (unsigned __int64)HyperspacePte >= 0xFFFFF6FB7DBED000uLL
                    && (unsigned __int64)HyperspacePte < 0xFFFFF6FB7DBED800uLL )
                  {
                    v40 = KeGetPcr()->NtTib.StackBase;
                    v41 = v40 ? v40[10] : 0LL;
                    v42 = *(_QWORD *)(v41 + 232);
                    if ( v42 )
                    {
                      v43 = SkiKvaShadowMode;
                      *(_QWORD *)(v42 + 8 * ((HyperspacePte >> 3) & 0x1FF)) = v27;
                      if ( v43 != 2 && (v27 & 1) != 0 )
                        v39 = v27 | 0x8000000000000000uLL;
                    }
                  }
                  *(_QWORD *)HyperspacePte = v39;
                  SkeCacheInvalidatePage(HyperspacePte << 25 >> 16);
                  SkmiReleaseHyperspacePte(HyperspacePte);
                  ++v30;
                }
                while ( v30 < a4 );
                v21 = (__int64)v47;
                v7 = a3;
                LOBYTE(CurrentIrql) = v51;
              }
              LOBYTE(v29) = CurrentIrql;
              SkeLowerIrql(v29);
            }
            if ( (*(_DWORD *)v21 & 0x8000) == 0 )
              SkmiProtectPhysicalPages((ULONG_PTR)Pool);
            if ( v44 )
              RtlWriteULong64ToUser(a1, v48);
            else
              *a1 = v48;
            SkobMakeReservedHandleValid(v48, v21, 0);
            v48 = 0;
          }
        }
        goto LABEL_67;
      }
      v26 = 0;
      v25 |= 0x8000u;
    }
    *(_DWORD *)v21 = v25;
    goto LABEL_35;
  }
LABEL_67:
  if ( v48 )
    SkobDeleteReservedHandle();
  if ( Pool && Pool != v7 )
    SkFreePool(512, Pool);
  if ( v21 )
    SkobDereferenceObject(v21);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14005c1e0  mov     r11, rsp
0x14005c1e3  mov     [r11+20h], r9d
0x14005c1e7  mov     [r11+18h], r8
0x14005c1eb  mov     [r11+8], rcx
0x14005c1ef  push    rbx
0x14005c1f0  push    rsi
0x14005c1f1  push    rdi
0x14005c1f2  push    r12
0x14005c1f4  push    r13
0x14005c1f6  push    r14
0x14005c1f8  push    r15
0x14005c1fa  sub     rsp, 80h
0x14005c201  mov     r13, r8
0x14005c204  mov     r15, rdx
0x14005c207  xor     edi, edi
0x14005c209  mov     [r11-70h], rdi
0x14005c20d  mov     rax, gs:8
0x14005c216  mov     r10b, [rax+60h]
0x14005c21a  mov     [rsp+0B8h+var_88], r10b
0x14005c21f  mov     [r11-78h], rdi
0x14005c223  test    r10b, r10b
0x14005c226  jz      short loc_14005C253
0x14005c228  mov     rax, gs:8
0x14005c231  test    rax, rax
0x14005c234  jz      short loc_14005C23C
0x14005c236  mov     rax, [rax+50h]
0x14005c23a  jmp     short loc_14005C23F
0x14005c23c  mov     rax, rdi
0x14005c23f  mov     al, [rax+190h]
0x14005c245  test    al, al
0x14005c247  js      short loc_14005C253
0x14005c249  mov     eax, 0C0000022h
0x14005c24e  jmp     loc_14005C712
0x14005c253  test    r9d, r9d
0x14005c256  jnz     short loc_14005C262
0x14005c258  mov     eax, 0C00000F2h
0x14005c25d  jmp     loc_14005C712
0x14005c262  mov     ecx, [rsp+0B8h+arg_20]
0x14005c269  lea     eax, [rcx-1]
0x14005c26c  test    eax, 0FFFFFFFCh
0x14005c271  jnz     loc_14005C70D
0x14005c277  cmp     ecx, 3
0x14005c27a  jz      loc_14005C70D
0x14005c280  mov     eax, [rsp+0B8h+arg_28]
0x14005c287  dec     eax
0x14005c289  cmp     eax, 3Fh ; '?'
0x14005c28c  ja      loc_14005C70D
0x14005c292  mov     rcx, 800000008000000Bh
0x14005c29c  bt      rcx, rax
0x14005c2a0  jnb     loc_14005C70D
0x14005c2a6  mov     ebx, [rsp+0B8h+arg_30]
0x14005c2ad  test    ebx, 0FFFFFFF0h
0x14005c2b3  jnz     loc_14005C706
0x14005c2b9  mov     r12d, ebx
0x14005c2bc  and     r12d, 2
0x14005c2c0  mov     edx, 1
0x14005c2c5  jz      short loc_14005C2CF
0x14005c2c7  test    dl, bl
0x14005c2c9  jz      loc_14005C706
0x14005c2cf  mov     eax, ebx
0x14005c2d1  and     eax, 4
0x14005c2d4  mov     [rsp+0B8h+BackTraceHash], eax
0x14005c2d8  jz      short loc_14005C2E3
0x14005c2da  test    r12d, r12d
0x14005c2dd  jz      loc_14005C706
0x14005c2e3  mov     r8b, dil
0x14005c2e6  mov     [rsp+0B8h+var_84], r8d
0x14005c2eb  mov     eax, r9d
0x14005c2ee  mov     [rsp+0B8h+var_48], rax
0x14005c2f3  test    r10b, r10b
0x14005c2f6  jz      loc_14005C389
0x14005c2fc  lea     rsi, ds:0[rax*8]
0x14005c304  mov     r8d, 6E506D4Dh
0x14005c30a  mov     rdx, rsi
0x14005c30d  mov     ecx, 200h
0x14005c312  call    SkAllocatePool
0x14005c317  mov     r14, rax
0x14005c31a  mov     [rsp+0B8h+var_58], rax
0x14005c31f  test    rax, rax
0x14005c322  jnz     short loc_14005C32E
0x14005c324  mov     eax, 0C000009Ah
0x14005c329  jmp     loc_14005C712
0x14005c32e  mov     rcx, [rsp+0B8h+arg_0]
0x14005c336  call    RtlReadULong64FromUser
0x14005c33b  mov     rdx, rax
0x14005c33e  mov     rcx, [rsp+0B8h+arg_0]
0x14005c346  call    RtlWriteULong64ToUser
0x14005c34b  test    rsi, rsi
0x14005c34e  jz      short loc_14005C35A
0x14005c350  test    r13b, 3
0x14005c354  jnz     loc_14005C726
0x14005c35a  mov     r8, rsi; Size
0x14005c35d  mov     rdx, r13; Src
0x14005c360  mov     rcx, r14; void *
0x14005c363  call    RtlCopyFromUser
0x14005c368  mov     r10b, [rsp+0B8h+var_88]
0x14005c36d  jmp     short loc_14005C3BC
0x14005c36f  mov     r15d, eax
0x14005c372  mov     r13, [rsp+0B8h+arg_10]
0x14005c37a  mov     r14, [rsp+0B8h+var_58]
0x14005c37f  mov     rsi, [rsp+0B8h+var_78]
0x14005c384  jmp     loc_14005C6CE
0x14005c389  mov     r14, r13
0x14005c38c  mov     [rsp+0B8h+var_58], r13
0x14005c391  mov     rax, gs:8
0x14005c39a  test    rax, rax
0x14005c39d  jz      short loc_14005C3A5
0x14005c39f  mov     rcx, [rax+50h]
0x14005c3a3  jmp     short loc_14005C3A8
0x14005c3a5  mov     rcx, rdi
0x14005c3a8  movzx   r8d, r8b
0x14005c3ac  cmp     rcx, cs:PsIumSystemProcess
0x14005c3b3  cmovz   r8d, edx
0x14005c3b7  mov     [rsp+0B8h+var_84], r8d
0x14005c3bc  lea     r9, [rsp+0B8h+var_78]
0x14005c3c1  mov     r8, r15
0x14005c3c4  lea     rdx, SkmiSectionType
0x14005c3cb  mov     cl, r10b
0x14005c3ce  call    SkobCreateObjectEx
0x14005c3d3  mov     r15d, eax
0x14005c3d6  mov     rsi, [rsp+0B8h+var_78]
0x14005c3db  test    eax, eax
0x14005c3dd  js      loc_14005C6CE
0x14005c3e3  xorps   xmm0, xmm0
0x14005c3e6  xor     eax, eax
0x14005c3e8  movups  xmmword ptr [rsi], xmm0
0x14005c3eb  movups  xmmword ptr [rsi+10h], xmm0
0x14005c3ef  mov     [rsi+20h], rax
0x14005c3f3  mov     dword ptr [rsi], 2000h
0x14005c3f9  mov     ecx, [rsp+0B8h+arg_20]
0x14005c400  call    SkmiMakeProtectionMask
0x14005c405  and     eax, 0Fh
0x14005c408  btc     eax, 0Ch
0x14005c40c  lea     r8d, [rax+rax]
0x14005c410  mov     [rsi], r8d
0x14005c413  mov     ecx, [rsp+0B8h+arg_28]
0x14005c41a  call    SkmiMakeProtectionMask
0x14005c41f  shl     eax, 9
0x14005c422  xor     eax, r8d
0x14005c425  and     eax, 1E00h
0x14005c42a  xor     eax, r8d
0x14005c42d  mov     [rsi], eax
0x14005c42f  test    r12d, r12d
0x14005c432  jz      short loc_14005C440
0x14005c434  bts     eax, 11h
0x14005c438  mov     r12d, 5
0x14005c43e  jmp     short loc_14005C454
0x14005c440  test    bl, 1
0x14005c443  jz      short loc_14005C44D
0x14005c445  mov     r12d, 1
0x14005c44b  jmp     short loc_14005C456
0x14005c44d  mov     r12d, edi
0x14005c450  bts     eax, 0Fh
0x14005c454  mov     [rsi], eax
0x14005c456  cmp     [rsp+0B8h+BackTraceHash], edi
0x14005c45a  jz      short loc_14005C462
0x14005c45c  bts     eax, 10h
0x14005c460  mov     [rsi], eax
0x14005c462  test    bl, 8
0x14005c465  jz      short loc_14005C471
0x14005c467  or      r12d, 8
0x14005c46b  bts     eax, 15h
0x14005c46f  mov     [rsi], eax
0x14005c471  lea     rdx, [rsp+0B8h+var_70]
0x14005c476  mov     cl, byte ptr [rsp+0B8h+var_84]
0x14005c47a  call    SkobReserveHandle
0x14005c47f  mov     r15d, eax
0x14005c482  test    eax, eax
0x14005c484  js      loc_14005C6CE
0x14005c48a  mov     dword ptr [rsp+0B8h+var_98], r12d
0x14005c48f  mov     r9, [rsp+0B8h+var_70]
0x14005c494  mov     r12d, [rsp+0B8h+arg_18]
0x14005c49c  mov     r8d, r12d
0x14005c49f  mov     rdx, r14
0x14005c4a2  mov     rcx, rsi
0x14005c4a5  call    SkmiInitSpecifyPagesSectionProtoPtes
0x14005c4aa  mov     r15d, eax
0x14005c4ad  mov     [rsp+0B8h+var_84], eax
0x14005c4b1  test    eax, eax
0x14005c4b3  js      loc_14005C6CE
0x14005c4b9  test    dword ptr [rsi], 10000h
0x14005c4bf  jz      loc_14005C668
0x14005c4c5  mov     rbx, 800000000000007Bh
0x14005c4cf  mov     rax, cr8
0x14005c4d3  mov     [rsp+0B8h+var_50], rax
0x14005c4d8  mov     ecx, 2
0x14005c4dd  mov     cr8, rcx
0x14005c4e1  mov     [rsp+0B8h+BackTraceHash], edi
0x14005c4e5  test    r12d, r12d
0x14005c4e8  jz      loc_14005C661
0x14005c4ee  mov     rax, 0FFFFF68000000000h
0x14005c4f8  shl     rax, 19h
0x14005c4fc  mov     rsi, rax
0x14005c4ff  mov     r13d, edi
0x14005c502  mov     r15d, r12d
0x14005c505  mov     eax, r13d
0x14005c508  mov     rcx, [r14+rax*8]
0x14005c50c  shl     rcx, 0Ch
0x14005c510  xor     rbx, rcx
0x14005c513  mov     rdx, 0FFF0000000000FFFh
0x14005c51d  and     rbx, rdx
0x14005c520  xor     rbx, rcx
0x14005c523  call    SkmiGetHyperspacePte
0x14005c528  mov     r12, rax
0x14005c52b  mov     rcx, [rax]
0x14005c52e  mov     [rsp+0B8h+var_98], rcx
0x14005c533  mov     r9, rbx
0x14005c536  xor     r8d, r8d
0x14005c539  mov     rdx, rax
0x14005c53c  xor     ecx, ecx
0x14005c53e  call    SkmiGetPteTrace
0x14005c543  mov     [rsp+0B8h+var_68], rax
0x14005c548  test    rax, rax
0x14005c54b  jz      short loc_14005C5AD
0x14005c54d  lea     rcx, [rax+20h]; void *
0x14005c551  xor     edx, edx; Val
0x14005c553  lea     r8d, [rdx+40h]; Size
0x14005c557  call    memset_0
0x14005c55c  test    cs:SkmiFlags, 400000h
0x14005c566  jz      short loc_14005C5AD
0x14005c568  mov     rcx, gs:8; FramesToSkip
0x14005c571  test    rcx, rcx
0x14005c574  jz      short loc_14005C5AD
0x14005c576  lea     r9, [rsp+0B8h+BackTraceHash]; BackTraceHash
0x14005c57b  mov     r8, [rsp+0B8h+var_68]
0x14005c580  add     r8, 20h ; ' '; BackTrace
0x14005c584  mov     edx, 8; FramesToCapture
0x14005c589  call    RtlCaptureStackBackTrace
0x14005c58e  test    ax, ax
0x14005c591  jnz     short loc_14005C5AD
0x14005c593  mov     rax, [rsp+0B8h]
0x14005c59b  mov     rcx, [rsp+0B8h+var_68]
0x14005c5a0  mov     [rcx+28h], rax
0x14005c5a4  call    SkmiGetInstructionPointer
0x14005c5a9  mov     [rcx+20h], rax
0x14005c5ad  mov     rax, rbx
0x14005c5b0  mov     rcx, 0FFFFF6FB7DBED000h
0x14005c5ba  cmp     r12, rcx
0x14005c5bd  jb      short loc_14005C61F
0x14005c5bf  mov     rcx, 0FFFFF6FB7DBED800h
0x14005c5c9  cmp     r12, rcx
0x14005c5cc  jnb     short loc_14005C61F
0x14005c5ce  mov     rcx, gs:8
0x14005c5d7  test    rcx, rcx
0x14005c5da  jz      short loc_14005C5E2
0x14005c5dc  mov     rdx, [rcx+50h]
0x14005c5e0  jmp     short loc_14005C5E5
0x14005c5e2  mov     rdx, rdi
0x14005c5e5  mov     r8, [rdx+0E8h]
0x14005c5ec  test    r8, r8
0x14005c5ef  jz      short loc_14005C61F
0x14005c5f1  mov     edx, cs:SkiKvaShadowMode
0x14005c5f7  mov     rcx, r12
0x14005c5fa  sar     rcx, 3
0x14005c5fe  and     ecx, 1FFh
0x14005c604  mov     [r8+rcx*8], rbx
0x14005c608  cmp     edx, 2
0x14005c60b  jz      short loc_14005C61F
0x14005c60d  test    bl, 1
0x14005c610  jz      short loc_14005C61F
0x14005c612  mov     rcx, 8000000000000000h
0x14005c61c  or      rax, rcx
0x14005c61f  mov     [r12], rax
0x14005c623  mov     rcx, r12
0x14005c626  shl     rcx, 19h
0x14005c62a  sub     rcx, rsi
0x14005c62d  sar     rcx, 10h
0x14005c631  call    SkeCacheInvalidatePage
0x14005c636  mov     rcx, r12
0x14005c639  call    SkmiReleaseHyperspacePte
0x14005c63e  inc     r13d
0x14005c641  cmp     r13d, r15d
0x14005c644  jb      loc_14005C505
0x14005c64a  mov     rsi, [rsp+0B8h+var_78]
0x14005c64f  mov     r15d, [rsp+0B8h+var_84]
0x14005c654  mov     r13, [rsp+0B8h+arg_10]
0x14005c65c  mov     rax, [rsp+0B8h+var_50]
0x14005c661  mov     cl, al
0x14005c663  call    SkeLowerIrql
0x14005c668  test    dword ptr [rsi], 8000h
0x14005c66e  jnz     short loc_14005C681
0x14005c670  xor     r8d, r8d
0x14005c673  mov     rdx, [rsp+0B8h+var_48]
0x14005c678  mov     rcx, r14; BugCheckParameter3
0x14005c67b  call    SkmiProtectPhysicalPages
0x14005c680  nop
0x14005c681  mov     rax, [rsp+0B8h+var_70]
0x14005c686  mov     rcx, [rsp+0B8h+arg_0]
0x14005c68e  cmp     [rsp+0B8h+var_88], dil
0x14005c693  jz      short loc_14005C69F
0x14005c695  mov     rdx, rax
0x14005c698  call    RtlWriteULong64ToUser
0x14005c69d  jmp     short loc_14005C6A2
0x14005c69f  mov     [rcx], rax
0x14005c6a2  xor     r8d, r8d
0x14005c6a5  mov     rdx, rsi
0x14005c6a8  mov     rcx, [rsp+0B8h+var_70]
0x14005c6ad  call    SkobMakeReservedHandleValid
0x14005c6b2  mov     [rsp+0B8h+var_70], rdi
0x14005c6b7  jmp     short loc_14005C6CE
  ... truncated ...
```
