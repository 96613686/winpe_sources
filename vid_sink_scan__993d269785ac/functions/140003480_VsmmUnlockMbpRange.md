# VsmmUnlockMbpRange

- ea: `0x140003480`
- end: `0x1400036e6`
- name: `VsmmUnlockMbpRange`
- size: `614`
- prototype: `void __fastcall(__int64, __int64, __int64, int, PMDL MemoryDescriptorList)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140027540`
- `0x1400ecb68`
- `0x1400ed060`
- `0x1400f9d70`

## callees

- `0x140003480`
- `0x1400036ec`
- `0x1400038b0`
- `0x14001d204`
- `0x14001d21c`
- `0x140021800`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140003680`
- `ntoskrnl!RtlRbRemoveNode` at `0x140003680`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000364f`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000364f`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003694`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003694`
- `ntoskrnl!KeSetEvent` at `0x1400035e6`
- `ntoskrnl!KeSetEvent` at `0x1400035e6`
- `ntoskrnl!MmUnlockPages` at `0x14000350e`
- `ntoskrnl!MmUnlockPages` at `0x1400036a4`
- `ntoskrnl!MmUnlockPages` at `0x14000350e`
- `ntoskrnl!MmUnlockPages` at `0x1400036a4`

## pseudocode

```c
void __fastcall VsmmUnlockMbpRange(__int64 a1, __int64 a2, __int64 a3, int a4, PMDL MemoryDescriptorList)
{
  __int64 v9; // r13
  int v10; // r12d
  struct _MDL *v11; // r14
  unsigned __int64 v12; // rbx
  unsigned int Page; // eax
  __int64 v14; // r15
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  int v17; // esi
  int v18; // eax
  unsigned __int64 v19; // rax
  KIRQL v20; // al
  unsigned __int64 *v21; // r13
  unsigned __int64 v22; // rsi
  _QWORD v23[22]; // [rsp+20h] [rbp-61h] BYREF
  KIRQL v24; // [rsp+F8h] [rbp+77h]
  volatile LONG *MemoryDescriptorLista; // [rsp+100h] [rbp+7Fh]

  memset(v23, 0, 0x68u);
  v9 = *(_QWORD *)(a1 + 8);
  v10 = 2;
  v11 = MemoryDescriptorList;
  v23[0] = v9;
  LODWORD(v23[1]) = 2;
  v23[3] = MemoryDescriptorList;
  HIDWORD(v23[1]) = a4;
  v23[5] = a3;
  v23[10] = a1;
  v23[11] = a2;
  v23[6] = 0;
  if ( a3 )
  {
    do
    {
      Page = VsmmpUnlockPrepareForNextPage(v23);
      VsmmMbpLockReleaseFast(v23[7], v23[8], Page);
      v12 = v23[9] + 1LL;
      ++v23[6];
      ++v23[9];
    }
    while ( v23[6] < v23[5] );
    a1 = v23[10];
    v11 = (struct _MDL *)v23[3];
    v10 = v23[1];
    v9 = v23[0];
  }
  else
  {
    v12 = v23[9];
  }
  if ( LOBYTE(v23[2]) || !v11 || (v23[4] & 2) == 0 )
    goto LABEL_8;
  if ( LODWORD(v23[4]) != 3 )
  {
    MmUnlockPages(v11);
    goto LABEL_8;
  }
  MemoryDescriptorLista = (volatile LONG *)(v9 + 12528);
  v20 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 12528));
  v21 = (unsigned __int64 *)(v9 + 12536);
  v24 = v20;
  v22 = v21[1];
  v16 = *v21;
  if ( (v22 & 1) == 0 )
  {
LABEL_26:
    v17 = v22 & 1;
    if ( !v16 )
      goto LABEL_37;
    while ( 1 )
    {
      v18 = VsmmpCompareHybridLockContext(v11, v16);
      if ( v18 >= 0 )
      {
        if ( v18 <= 0 )
          goto LABEL_38;
        v19 = *(_QWORD *)(v16 + 8);
        if ( v17 && v19 )
        {
LABEL_30:
          v16 ^= v19;
          goto LABEL_23;
        }
      }
      else
      {
        v19 = *(_QWORD *)v16;
        if ( v17 && v19 )
          goto LABEL_30;
      }
      v16 = v19;
LABEL_23:
      if ( !v16 )
        goto LABEL_37;
    }
  }
  if ( v16 )
  {
    v16 ^= (unsigned __int64)v21;
    goto LABEL_26;
  }
LABEL_37:
  __int2c();
LABEL_38:
  RtlRbRemoveNode(v21, v16);
  ExReleaseSpinLockExclusive(MemoryDescriptorLista, v24);
  MmUnlockPages(*(PMDL *)(v16 + 32));
  VsmmpFreeHybridLockContext((PVOID)v16);
LABEL_8:
  if ( !v12 )
    return;
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      v14 = a1 + 64;
      goto LABEL_15;
    }
  }
  else
  {
    a1 = v23[12];
  }
  v14 = a1 + 448;
LABEL_15:
  if ( *(_QWORD *)(v14 + 8) )
  {
    v15 = *(_QWORD *)v14;
  }
  else
  {
    v15 = _InterlockedExchangeAdd64((volatile signed __int64 *)v14, -(__int64)v12);
    if ( (v15 & 0x7FFFFFFFFFFFFFFFuLL) < v12 )
      __int2c();
  }
  if ( v15 < 0 && (*(_QWORD *)(v14 + 8) || (v15 & 0x7FFFFFFFFFFFFFFFLL) == v12) )
    KeSetEvent((PRKEVENT)(v14 + 16), 0, 0);
}

```

## disassembly

```asm
0x140003480  push    rbp
0x140003482  push    rbx
0x140003483  push    rsi
0x140003484  push    rdi
0x140003485  push    r12
0x140003487  push    r13
0x140003489  push    r14
0x14000348b  push    r15
0x14000348d  lea     rbp, [rsp-17h]
0x140003492  sub     rsp, 98h
0x140003499  mov     rsi, r8
0x14000349c  mov     rdi, rdx
0x14000349f  mov     r15, rcx
0x1400034a2  xor     edx, edx; Val
0x1400034a4  mov     r8d, 68h ; 'h'; Size
0x1400034aa  lea     rcx, [rbp+4Fh+var_B0]; void *
0x1400034ae  mov     ebx, r9d
0x1400034b1  call    memset
0x1400034b6  mov     r13, [r15+8]
0x1400034ba  mov     r12d, 2
0x1400034c0  mov     r14, [rbp+4Fh+MemoryDescriptorList]
0x1400034c4  mov     [rbp+4Fh+var_B0], r13
0x1400034c8  mov     [rbp+4Fh+var_A8], r12d
0x1400034cc  mov     [rbp+4Fh+var_98], r14
0x1400034d0  mov     [rbp+4Fh+var_A4], ebx
0x1400034d3  mov     [rbp+4Fh+var_88], rsi
0x1400034d7  mov     [rbp+4Fh+var_60], r15
0x1400034db  mov     [rbp+4Fh+var_58], rdi
0x1400034df  mov     [rbp+4Fh+var_80], 0
0x1400034e7  test    rsi, rsi
0x1400034ea  jnz     short loc_140003534
0x1400034ec  mov     rbx, [rbp+4Fh+var_68]
0x1400034f0  cmp     [rbp+4Fh+var_A0], 0
0x1400034f4  jnz     short loc_14000351A
0x1400034f6  test    r14, r14
0x1400034f9  jz      short loc_14000351A
0x1400034fb  mov     eax, [rbp+4Fh+var_90]
0x1400034fe  test    al, 2
0x140003500  jz      short loc_14000351A
0x140003502  cmp     eax, 3
0x140003505  jz      loc_140003641
0x14000350b  mov     rcx, r14; MemoryDescriptorList
0x14000350e  call    cs:__imp_MmUnlockPages
0x140003515  nop     dword ptr [rax+rax+00h]
0x14000351a  test    rbx, rbx
0x14000351d  jnz     short loc_14000357E
0x14000351f  add     rsp, 98h
0x140003526  pop     r15
0x140003528  pop     r14
0x14000352a  pop     r13
0x14000352c  pop     r12
0x14000352e  pop     rdi
0x14000352f  pop     rsi
0x140003530  pop     rbx
0x140003531  pop     rbp
0x140003532  retn
0x140003534  lea     rcx, [rbp+4Fh+var_B0]
0x140003538  call    VsmmpUnlockPrepareForNextPage
0x14000353d  mov     rdx, [rbp+4Fh+var_70]
0x140003541  mov     r8d, eax
0x140003544  mov     rcx, [rbp+4Fh+var_78]
0x140003548  call    VsmmMbpLockReleaseFast
0x14000354d  mov     rax, [rbp+4Fh+var_80]
0x140003551  mov     rbx, [rbp+4Fh+var_68]
0x140003555  inc     rax
0x140003558  inc     rbx
0x14000355b  mov     [rbp+4Fh+var_80], rax
0x14000355f  mov     [rbp+4Fh+var_68], rbx
0x140003563  cmp     rax, [rbp+4Fh+var_88]
0x140003567  jb      short loc_140003534
0x140003569  mov     r15, [rbp+4Fh+var_60]
0x14000356d  mov     r14, [rbp+4Fh+var_98]
0x140003571  mov     r12d, [rbp+4Fh+var_A8]
0x140003575  mov     r13, [rbp+4Fh+var_B0]
0x140003579  jmp     loc_1400034F0
0x14000357e  test    r12d, r12d
0x140003581  jnz     loc_1400036C4
0x140003587  mov     r15, [rbp+4Fh+var_50]
0x14000358b  add     r15, 1C0h
0x140003592  cmp     qword ptr [r15+8], 0
0x140003597  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1400035a1  jnz     loc_1400036D7
0x1400035a7  mov     rax, rbx
0x1400035aa  neg     rax
0x1400035ad  lock xadd [r15], rax
0x1400035b2  mov     rcx, rax
0x1400035b5  and     rcx, rdx
0x1400035b8  cmp     rcx, rbx
0x1400035bb  jb      loc_1400036DF
0x1400035c1  test    rax, rax
0x1400035c4  jns     loc_14000351F
0x1400035ca  cmp     qword ptr [r15+8], 0
0x1400035cf  jnz     short loc_1400035DD
0x1400035d1  and     rax, rdx
0x1400035d4  cmp     rax, rbx
0x1400035d7  jnz     loc_14000351F
0x1400035dd  lea     rcx, [r15+10h]; Event
0x1400035e1  xor     r8d, r8d; Wait
0x1400035e4  xor     edx, edx; Increment
0x1400035e6  call    cs:__imp_KeSetEvent
0x1400035ed  nop     dword ptr [rax+rax+00h]
0x1400035f2  jmp     loc_14000351F
0x1400035f7  mov     rdi, rax
0x1400035fa  test    rdi, rdi
0x1400035fd  jz      short loc_140003678
0x1400035ff  jmp     short loc_14000360C
0x140003601  xor     rdi, r13
0x140003604  and     esi, 1
0x140003607  test    rdi, rdi
0x14000360a  jz      short loc_140003678
0x14000360c  mov     rdx, rdi
0x14000360f  mov     rcx, r14
0x140003612  call    VsmmpCompareHybridLockContext
0x140003617  test    eax, eax
0x140003619  jns     short loc_14000362C
0x14000361b  mov     rax, [rdi]
0x14000361e  test    esi, esi
0x140003620  jz      short loc_1400035F7
0x140003622  test    rax, rax
0x140003625  jz      short loc_1400035F7
0x140003627  xor     rdi, rax
0x14000362a  jmp     short loc_1400035FA
0x14000362c  jle     loc_1400036BD
0x140003632  mov     rax, [rdi+8]
0x140003636  test    esi, esi
0x140003638  jz      short loc_1400035F7
0x14000363a  test    rax, rax
0x14000363d  jz      short loc_1400035F7
0x14000363f  jmp     short loc_140003627
0x140003641  lea     rax, [r13+30F0h]
0x140003648  mov     rcx, rax; SpinLock
0x14000364b  mov     [rbp+4Fh+MemoryDescriptorList], rax
0x14000364f  call    cs:__imp_ExAcquireSpinLockExclusive
0x140003656  nop     dword ptr [rax+rax+00h]
0x14000365b  add     r13, 30F8h
0x140003662  mov     [rbp+4Fh+arg_18], al
0x140003665  mov     rsi, [r13+8]
0x140003669  mov     rdi, [r13+0]
0x14000366d  test    sil, 1
0x140003671  jz      short loc_140003604
0x140003673  test    rdi, rdi
0x140003676  jnz     short loc_140003601
0x140003678  int     2Ch; Windows NT - assertion failure
0x14000367a  mov     rdx, rdi
0x14000367d  mov     rcx, r13
0x140003680  call    cs:__imp_RtlRbRemoveNode
0x140003687  nop     dword ptr [rax+rax+00h]
0x14000368c  movzx   edx, [rbp+4Fh+arg_18]; OldIrql
0x140003690  mov     rcx, [rbp+4Fh+MemoryDescriptorList]; SpinLock
0x140003694  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000369b  nop     dword ptr [rax+rax+00h]
0x1400036a0  mov     rcx, [rdi+20h]; MemoryDescriptorList
0x1400036a4  call    cs:__imp_MmUnlockPages
0x1400036ab  nop     dword ptr [rax+rax+00h]
0x1400036b0  mov     rcx, rdi; P
0x1400036b3  call    VsmmpFreeHybridLockContext
0x1400036b8  jmp     loc_14000351A
0x1400036bd  test    rdi, rdi
0x1400036c0  jnz     short loc_14000367A
0x1400036c2  jmp     short loc_140003678
0x1400036c4  cmp     r12d, 1
0x1400036c8  jz      loc_14000358B
0x1400036ce  add     r15, 40h ; '@'
0x1400036d2  jmp     loc_140003592
0x1400036d7  mov     rax, [r15]
0x1400036da  jmp     loc_1400035C1
0x1400036df  int     2Ch; Windows NT - assertion failure
0x1400036e1  jmp     loc_1400035C1
```
