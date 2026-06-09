# SIO_VDT::BuildChildPacketsRead(SC_PACKET *,unsigned __int64,ulong)

- ea: `0x14000bff0`
- end: `0x14000c408`
- name: `?BuildChildPacketsRead@SIO_VDT@@QEAAJPEAVSC_PACKET@@_KK@Z`
- size: `1048`
- prototype: `__int64 __fastcall(SIO_VDT *__hidden this, struct SC_PACKET *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14000bd50`
- `0x14000bfa0`

## callees

- `0x14000b170`
- `0x14000bd00`
- `0x14000bff0`
- `0x14000c410`
- `0x1400154c0`
- `0x14002f7e8`
- `0x140068000`
- `0x1400684c0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000c0f4`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000c0f4`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000c086`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000c086`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c336`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c3ee`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c336`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c3ee`

## pseudocode

```c
__int64 __fastcall SIO_VDT::BuildChildPacketsRead(
        SIO_VDT *this,
        struct SC_PACKET *a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  struct SC_PACKET *v4; // r13
  int v5; // r12d
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rbx
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r15
  KIRQL v13; // cl
  __int64 v14; // r14
  unsigned __int64 v15; // rax
  __int64 v16; // r9
  int i; // r8d
  unsigned __int64 v18; // r9
  unsigned __int64 v19; // rcx
  unsigned int v20; // eax
  int SetRun; // r8d
  unsigned int v22; // r12d
  SIO_CACHE_PACKET *v23; // rax
  SC_PACKET *v24; // rax
  SC_PACKET *v25; // r13
  struct SC_PACKET **v26; // rdx
  struct SC_PACKET *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r14
  char *v30; // rax
  unsigned __int64 v31; // r9
  unsigned __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // r10d
  char *v35; // rax
  unsigned __int64 v36; // r12
  SIO_CACHE_PACKET *v37; // rax
  SC_PACKET *v38; // rax
  __int64 v39; // rdx
  struct SC_PACKET *v40; // rdx
  int v41; // [rsp+30h] [rbp-50h]
  unsigned int v42; // [rsp+30h] [rbp-50h]
  __int64 v43; // [rsp+38h] [rbp-48h]
  unsigned int v44; // [rsp+40h] [rbp-40h]
  int v45; // [rsp+48h] [rbp-38h]
  __int64 v46; // [rsp+50h] [rbp-30h] BYREF
  __int64 v47; // [rsp+58h] [rbp-28h]
  __int64 v48; // [rsp+60h] [rbp-20h]
  __int64 v49; // [rsp+68h] [rbp-18h]
  unsigned __int64 v50; // [rsp+70h] [rbp-10h]
  unsigned __int64 v52; // [rsp+D0h] [rbp+50h]
  KIRQL v53; // [rsp+D8h] [rbp+58h]

  v4 = a2;
  v46 = 0;
  v5 = 0;
  v47 = 0;
  v6 = a3 + a4;
  v48 = 0;
  v7 = a3;
  v49 = 0;
  v50 = 0;
  while ( v7 < v6 )
  {
    v10 = *((_QWORD *)this + 40);
    v11 = v7 % v10;
    v12 = v10 - v7 % v10;
    v52 = v11;
    if ( v6 - v7 < v12 )
      LODWORD(v12) = v6 - v7;
    v53 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)this + 68);
    v13 = v53;
    v14 = 0;
    v15 = v7 / *((_QWORD *)this + 40);
    if ( v15 < *((_QWORD *)this + 32) )
    {
      v16 = *((_QWORD *)this + 24);
      for ( i = *((_DWORD *)this + 66);
            ;
            v16 = *(_QWORD *)(v16 + 8 * ((unsigned int)(*((_DWORD *)this + 61) - 1) & (v15 >> i)) + 24) )
      {
        i -= *((_DWORD *)this + 62);
        if ( i <= 0 )
          break;
        if ( !v16 )
        {
          v13 = v53;
          goto LABEL_11;
        }
      }
      v13 = v53;
      if ( v16 )
        v14 = *(_QWORD *)(v16 + 8LL * ((unsigned int)v15 & (*((_DWORD *)this + 61) - 1)) + 24);
    }
LABEL_11:
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)this + 68, v13);
    if ( v14 )
    {
      if ( (unsigned __int64)(v14 - 1) <= 1 )
      {
        v22 = v7 - *((_DWORD *)a2 + 34);
        v23 = (SIO_CACHE_PACKET *)SC_PACKET::operator new(0x128u, *((struct SC_PACKET **)a2 + 1));
        if ( !v23 )
          return (unsigned int)-1073741670;
        v24 = SIO_CACHE_PACKET::SIO_CACHE_PACKET(v23);
        if ( (v25 = v24) == 0 )
          return (unsigned int)-1073741670;
        v5 = SC_PACKET::Split(v24, a2, v22, v12, 0);
        if ( v5 < 0 )
        {
LABEL_35:
          (**(void (__fastcall ***)(SC_PACKET *, __int64))v25)(v25, 1);
          return (unsigned int)v5;
        }
        *((_QWORD *)v25 + 17) = v7;
        *((_DWORD *)v25 + 36) = v12;
        *((_DWORD *)v25 + 38) = *((_DWORD *)a2 + 38);
        *((_BYTE *)v25 + 168) = 3;
        *((_BYTE *)v25 + 170) = 1;
        *((_QWORD *)v25 + 30) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
        *((_QWORD *)v25 + 1) = *((_QWORD *)a2 + 1);
        *((_QWORD *)v25 + 2) = a2;
        v26 = (struct SC_PACKET **)*((_QWORD *)a2 + 6);
        if ( *v26 != (struct SC_PACKET *)((char *)a2 + 40) )
          __fastfail(3u);
        v27 = (SC_PACKET *)((char *)v25 + 56);
        v4 = a2;
        *(_QWORD *)v27 = (char *)a2 + 40;
        *((_QWORD *)v27 + 1) = v26;
        *v26 = v27;
        *((_QWORD *)a2 + 6) = v27;
        ++*((_DWORD *)a2 + 18);
      }
      else
      {
        v50 = *((unsigned int *)this + 78);
        v43 = (unsigned int)v12 + v52;
        v46 = v14 + 48;
        v18 = (v52 - v52 % v50) / v50;
        LODWORD(v47) = v18;
        v48 = (unsigned int)v18;
        v19 = (v50 + (unsigned int)v12 - (v52 + (unsigned int)v12 + v50 - 1) % v50 + v52 - 1) / v50;
        HIDWORD(v47) = v19;
        HIDWORD(v49) = 0;
        v20 = v18;
        while ( 1 )
        {
          LODWORD(v49) = v20;
          if ( v20 >= (unsigned int)v19 || v20 == -1 || v20 < (unsigned int)v18 )
            break;
          SetRun = SC_ITERATOR_BITMAP::GetSetRun((SC_ITERATOR_BITMAP *)&v46);
          if ( SetRun )
          {
            v36 = SetRun - (unsigned int)(v52 % *((unsigned int *)this + 78));
            if ( v36 >= v43 - v52 )
              LODWORD(v36) = v43 - v52;
            v44 = *(_DWORD *)(v14 + 16) + v52 - *((_DWORD *)v4 + 34);
            v42 = v36;
            v37 = (SIO_CACHE_PACKET *)SC_PACKET::operator new(0x128u, *((struct SC_PACKET **)v4 + 1));
            if ( !v37 )
              return (unsigned int)-1073741670;
            v38 = SIO_CACHE_PACKET::SIO_CACHE_PACKET(v37);
            v25 = v38;
            if ( !v38 )
              return (unsigned int)-1073741670;
            v5 = SC_PACKET::Split(v38, a2, v44, v36, 0);
            if ( v5 < 0 )
              goto LABEL_35;
            v39 = *(_QWORD *)(v14 + 16) + v52;
            *((_DWORD *)v25 + 36) = v42;
            *((_QWORD *)v25 + 17) = v39;
            *((_DWORD *)v25 + 38) = *((_DWORD *)a2 + 38);
            *((_BYTE *)v25 + 168) = 3;
            *((_BYTE *)v25 + 170) = 1;
            *((_QWORD *)v25 + 30) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
            v40 = v25;
            v4 = a2;
            SC_PACKET::Attach(a2, v40, 0);
            v52 += v42;
          }
          if ( HIDWORD(v48) * (_DWORD)v50 )
          {
            v31 = v52;
            v32 = HIDWORD(v48) * (_DWORD)v50 - (unsigned int)(v52 % *((unsigned int *)this + 78));
            if ( v32 >= v43 - v52 )
              LODWORD(v32) = v43 - v52;
            v33 = *((_QWORD *)v4 + 15);
            v34 = v52 + *(_DWORD *)(v14 + 16) - *((_DWORD *)v4 + 34);
            v41 = v32;
            v45 = v34;
            if ( (*(_BYTE *)(v33 + 10) & 5) != 0 )
            {
              v35 = *(char **)(v33 + 24);
            }
            else
            {
              v35 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v33, 0, MmCached, 0, 0, 0x40000020u);
              v31 = v52;
              LODWORD(v32) = v41;
              v34 = v45;
            }
            if ( v35 )
            {
              memset(&v35[v34], 0, (unsigned int)v32);
              v31 = v52;
              LODWORD(v32) = v41;
            }
            v52 = (unsigned int)v32 + v31;
          }
          LODWORD(v19) = HIDWORD(v47);
          v20 = HIDWORD(v48) + HIDWORD(v49) + v49;
          LODWORD(v18) = v47;
        }
      }
    }
    else
    {
      v28 = *((_QWORD *)v4 + 15);
      v29 = (unsigned int)(v7 - *((_DWORD *)v4 + 34));
      if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
        v30 = *(char **)(v28 + 24);
      else
        v30 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000020u);
      if ( v30 )
        memset(&v30[v29], 0, (unsigned int)v12);
    }
    v7 += (unsigned int)v12;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000bff0  mov     [rsp-38h+arg_8], rdx
0x14000bff5  push    rbp
0x14000bff6  push    rbx
0x14000bff7  push    rsi
0x14000bff8  push    rdi
0x14000bff9  push    r12
0x14000bffb  push    r13
0x14000bffd  push    r14
0x14000bfff  mov     rbp, rsp
0x14000c002  sub     rsp, 80h
0x14000c009  mov     r13, rdx
0x14000c00c  mov     edi, r9d
0x14000c00f  xor     edx, edx
0x14000c011  mov     [rsp+80h+arg_0], r15
0x14000c019  mov     [rbp+var_30], rdx
0x14000c01d  mov     r12d, edx
0x14000c020  mov     [rbp+var_28], rdx
0x14000c024  add     rdi, r8
0x14000c027  mov     [rbp+var_20], rdx
0x14000c02b  mov     rbx, r8
0x14000c02e  mov     [rbp+var_18], rdx
0x14000c032  mov     rsi, rcx
0x14000c035  mov     [rbp+var_10], rdx
0x14000c039  cmp     rbx, rdi
0x14000c03c  jb      short loc_14000C05C
0x14000c03e  mov     r15, [rsp+80h+arg_0]
0x14000c046  mov     eax, r12d
0x14000c049  add     rsp, 80h
0x14000c050  pop     r14
0x14000c052  pop     r13
0x14000c054  pop     r12
0x14000c056  pop     rdi
0x14000c057  pop     rsi
0x14000c058  pop     rbx
0x14000c059  pop     rbp
0x14000c05a  retn
0x14000c05c  mov     r15, [rsi+140h]
0x14000c063  lea     rcx, [rsi+110h]; SpinLock
0x14000c06a  xor     edx, edx
0x14000c06c  mov     rax, rbx
0x14000c06f  div     r15
0x14000c072  mov     rax, rdi
0x14000c075  sub     r15, rdx
0x14000c078  mov     [rbp+arg_10], rdx
0x14000c07c  sub     rax, rbx
0x14000c07f  cmp     rax, r15
0x14000c082  cmovb   r15, rax
0x14000c086  call    cs:__imp_ExAcquireSpinLockShared
0x14000c08d  nop     dword ptr [rax+rax+00h]
0x14000c092  mov     [rbp+arg_18], al
0x14000c095  xor     edx, edx
0x14000c097  movzx   ecx, al
0x14000c09a  xor     r14d, r14d
0x14000c09d  mov     rax, rbx
0x14000c0a0  div     qword ptr [rsi+140h]
0x14000c0a7  cmp     rax, [rsi+100h]
0x14000c0ae  jnb     short loc_14000C0EA
0x14000c0b0  mov     r9, [rsi+0C0h]
0x14000c0b7  mov     r10d, [rsi+0F8h]
0x14000c0be  mov     r8d, [rsi+108h]
0x14000c0c5  sub     r8d, r10d
0x14000c0c8  test    r8d, r8d
0x14000c0cb  jg      loc_14000C2EF
0x14000c0d1  movzx   ecx, [rbp+arg_18]
0x14000c0d5  test    r9, r9
0x14000c0d8  jz      short loc_14000C0EA
0x14000c0da  mov     edx, [rsi+0F4h]
0x14000c0e0  dec     edx
0x14000c0e2  and     rdx, rax
0x14000c0e5  mov     r14, [r9+rdx*8+18h]
0x14000c0ea  movzx   edx, cl; OldIrql
0x14000c0ed  lea     rcx, [rsi+110h]; SpinLock
0x14000c0f4  call    cs:__imp_ExReleaseSpinLockShared
0x14000c0fb  nop     dword ptr [rax+rax+00h]
0x14000c100  test    r14, r14
0x14000c103  jz      loc_14000C2BB
0x14000c109  lea     rax, [r14-1]
0x14000c10d  cmp     rax, 1
0x14000c111  jbe     loc_14000C1DF
0x14000c117  mov     r8d, [rsi+138h]
0x14000c11e  xor     edx, edx
0x14000c120  mov     r10, [rbp+arg_10]
0x14000c124  mov     ecx, r15d
0x14000c127  mov     [rbp+var_10], r8
0x14000c12b  lea     rax, [rcx+r10]
0x14000c12f  mov     [rbp+var_48], rax
0x14000c133  lea     rax, [r14+30h]
0x14000c137  mov     [rbp+var_30], rax
0x14000c13b  mov     rax, r10
0x14000c13e  div     r8
0x14000c141  mov     rax, r10
0x14000c144  sub     rax, rdx
0x14000c147  xor     edx, edx
0x14000c149  div     r8
0x14000c14c  xor     edx, edx
0x14000c14e  mov     r9, rax
0x14000c151  lea     rax, [r8-1]
0x14000c155  add     rax, rcx
0x14000c158  mov     dword ptr [rbp+var_28], r9d
0x14000c15c  add     rax, r10
0x14000c15f  mov     dword ptr [rbp+var_20], r9d
0x14000c163  div     r8
0x14000c166  lea     rax, [r10-1]
0x14000c16a  sub     rcx, rdx
0x14000c16d  xor     edx, edx
0x14000c16f  add     rcx, r8
0x14000c172  add     rax, rcx
0x14000c175  div     r8
0x14000c178  mov     rcx, rax
0x14000c17b  mov     dword ptr [rbp+var_28+4], eax
0x14000c17e  xor     eax, eax
0x14000c180  mov     dword ptr [rbp+var_20+4], eax
0x14000c183  mov     dword ptr [rbp+var_18+4], eax
0x14000c186  mov     eax, r9d
0x14000c189  mov     dword ptr [rbp+var_18], eax
0x14000c18c  cmp     eax, ecx
0x14000c18e  jb      short loc_14000C19B
0x14000c190  mov     eax, r15d
0x14000c193  add     rbx, rax
0x14000c196  jmp     loc_14000C039
0x14000c19b  cmp     eax, 0FFFFFFFFh
0x14000c19e  jz      short loc_14000C190
0x14000c1a0  cmp     eax, r9d
0x14000c1a3  jb      short loc_14000C190
0x14000c1a5  lea     rcx, [rbp+var_30]; this
0x14000c1a9  call    ?GetSetRun@SC_ITERATOR_BITMAP@@QEAA_KXZ; SC_ITERATOR_BITMAP::GetSetRun(void)
0x14000c1ae  mov     r8, rax
0x14000c1b1  test    eax, eax
0x14000c1b3  jnz     loc_14006927A
0x14000c1b9  mov     r8d, dword ptr [rbp+var_10]
0x14000c1bd  imul    r8d, dword ptr [rbp+var_20+4]
0x14000c1c2  test    r8d, r8d
0x14000c1c5  jnz     loc_14000C364
0x14000c1cb  mov     edx, dword ptr [rbp+var_18+4]
0x14000c1ce  add     edx, dword ptr [rbp+var_20+4]
0x14000c1d1  mov     eax, dword ptr [rbp+var_18]
0x14000c1d4  mov     ecx, dword ptr [rbp+var_28+4]
0x14000c1d7  add     eax, edx
0x14000c1d9  mov     r9d, dword ptr [rbp+var_28]
0x14000c1dd  jmp     short loc_14000C189
0x14000c1df  mov     r14, [rbp+arg_8]
0x14000c1e3  mov     r12d, ebx
0x14000c1e6  mov     ecx, 128h; unsigned __int64
0x14000c1eb  mov     rdx, [r14+8]; struct SC_PACKET *
0x14000c1ef  sub     r12d, [r14+88h]
0x14000c1f6  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x14000c1fb  test    rax, rax
0x14000c1fe  jnz     short loc_14000C20B
0x14000c200  mov     r12d, 0C000009Ah
0x14000c206  jmp     loc_14000C03E
0x14000c20b  mov     rcx, rax; this
0x14000c20e  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x14000c213  mov     r13, rax
0x14000c216  test    rax, rax
0x14000c219  jz      short loc_14000C200
0x14000c21b  mov     r9d, r15d; unsigned int
0x14000c21e  mov     byte ptr [rsp+80h+BugCheckOnFailure], 0; unsigned __int8
0x14000c223  mov     r8d, r12d; unsigned int
0x14000c226  mov     rdx, r14; struct SC_PACKET *
0x14000c229  mov     rcx, rax; this
0x14000c22c  call    ?Split@SC_PACKET@@QEAAJPEAV1@KKE@Z; SC_PACKET::Split(SC_PACKET *,ulong,ulong,uchar)
0x14000c231  mov     r12d, eax
0x14000c234  test    eax, eax
0x14000c236  js      loc_14000C344
0x14000c23c  mov     [r13+88h], rbx
0x14000c243  mov     [r13+90h], r15d
0x14000c24a  mov     eax, [r14+98h]
0x14000c251  mov     [r13+98h], eax
0x14000c258  mov     byte ptr [r13+0A8h], 3
0x14000c260  mov     byte ptr [r13+0AAh], 1
0x14000c268  mov     rcx, [rsi+8]
0x14000c26c  mov     rax, [rcx]
0x14000c26f  mov     rax, [rax+50h]
0x14000c273  call    _guard_dispatch_icall
0x14000c278  mov     [r13+0F0h], rax
0x14000c27f  lea     rcx, [r14+28h]
0x14000c283  mov     rax, [r14+8]
0x14000c287  mov     [r13+8], rax
0x14000c28b  mov     [r13+10h], r14
0x14000c28f  mov     rdx, [rcx+8]
0x14000c293  cmp     [rdx], rcx
0x14000c296  jnz     loc_14000C35D
0x14000c29c  lea     rax, [r13+38h]
0x14000c2a0  mov     r13, [rbp+arg_8]
0x14000c2a4  mov     [rax], rcx
0x14000c2a7  mov     [rax+8], rdx
0x14000c2ab  mov     [rdx], rax
0x14000c2ae  mov     [rcx+8], rax
0x14000c2b2  inc     dword ptr [r14+48h]
0x14000c2b6  jmp     loc_14000C190
0x14000c2bb  mov     rcx, [r13+78h]; MemoryDescriptorList
0x14000c2bf  mov     r14d, ebx
0x14000c2c2  sub     r14d, [r13+88h]
0x14000c2c9  test    byte ptr [rcx+0Ah], 5
0x14000c2cd  jz      short loc_14000C31B
0x14000c2cf  mov     rax, [rcx+18h]
0x14000c2d3  test    rax, rax
0x14000c2d6  jz      loc_14000C190
0x14000c2dc  mov     r8d, r15d; Size
0x14000c2df  lea     rcx, [rax+r14]; void *
0x14000c2e3  xor     edx, edx; Val
0x14000c2e5  call    memset
0x14000c2ea  jmp     loc_14000C190
0x14000c2ef  test    r9, r9
0x14000c2f2  jz      short loc_14000C312
0x14000c2f4  mov     ecx, r8d
0x14000c2f7  mov     rdx, rax
0x14000c2fa  shr     rdx, cl
0x14000c2fd  mov     ecx, [rsi+0F4h]
0x14000c303  dec     ecx
0x14000c305  and     rdx, rcx
0x14000c308  mov     r9, [r9+rdx*8+18h]
0x14000c30d  jmp     loc_14000C0C5
0x14000c312  movzx   ecx, [rbp+arg_18]
0x14000c316  jmp     loc_14000C0EA
0x14000c31b  mov     [rsp+80h+Priority], 40000020h; Priority
0x14000c323  xor     r9d, r9d; RequestedAddress
0x14000c326  xor     edx, edx; AccessMode
0x14000c328  mov     [rsp+80h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000c330  mov     r8d, 1; CacheType
0x14000c336  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c33d  nop     dword ptr [rax+rax+00h]
0x14000c342  jmp     short loc_14000C2D3
0x14000c344  mov     rax, [r13+0]
0x14000c348  mov     edx, 1
0x14000c34d  mov     rcx, r13
0x14000c350  mov     rax, [rax]
0x14000c353  call    _guard_dispatch_icall
0x14000c358  jmp     loc_14000C03E
0x14000c35d  mov     ecx, 3
0x14000c362  int     29h; Win8: RtlFailFast(ecx)
0x14000c364  mov     r9, [rbp+arg_10]
0x14000c368  xor     edx, edx
0x14000c36a  mov     ecx, [rsi+138h]
0x14000c370  mov     rax, r9
0x14000c373  mov     r10d, [r14+10h]
0x14000c377  div     rcx
0x14000c37a  mov     rcx, [rbp+var_48]
0x14000c37e  sub     r8d, edx
0x14000c381  sub     rcx, r9
0x14000c384  mov     edx, r8d
0x14000c387  cmp     rdx, rcx
0x14000c38a  cmovnb  edx, ecx
0x14000c38d  sub     r10d, [r13+88h]
0x14000c394  mov     rcx, [r13+78h]; MemoryDescriptorList
0x14000c398  add     r10d, r9d
0x14000c39b  mov     [rbp+var_50], rdx
0x14000c39f  mov     [rbp+var_38], r10
0x14000c3a3  test    byte ptr [rcx+0Ah], 5
0x14000c3a7  jz      short loc_14000C3D3
0x14000c3a9  mov     rax, [rcx+18h]
0x14000c3ad  test    rax, rax
0x14000c3b0  jz      loc_140069374
0x14000c3b6  mov     ecx, r10d
0x14000c3b9  mov     r8d, edx; Size
0x14000c3bc  add     rcx, rax; void *
0x14000c3bf  xor     edx, edx; Val
0x14000c3c1  call    memset
0x14000c3c6  mov     r9, [rbp+arg_10]
0x14000c3ca  mov     rdx, [rbp+var_50]
0x14000c3ce  jmp     loc_140069374
0x14000c3d3  mov     [rsp+80h+Priority], 40000020h; Priority
0x14000c3db  xor     r9d, r9d; RequestedAddress
0x14000c3de  xor     edx, edx; AccessMode
0x14000c3e0  mov     [rsp+80h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000c3e8  mov     r8d, 1; CacheType
0x14000c3ee  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c3f5  nop     dword ptr [rax+rax+00h]
0x14000c3fa  mov     r9, [rbp+arg_10]
0x14000c3fe  mov     rdx, [rbp+var_50]
0x14000c402  mov     r10, [rbp+var_38]
0x14000c406  jmp     short loc_14000C3AD
0x14006927a  mov     r9, [rbp+arg_10]
0x14006927e  xor     edx, edx
0x140069280  mov     ecx, [rsi+138h]
0x140069286  mov     rax, r9
0x140069289  div     rcx
0x14006928c  mov     rcx, [rbp+var_48]
0x140069290  mov     eax, r9d
0x140069293  sub     r8d, edx
0x140069296  sub     rcx, r9
0x140069299  mov     rdx, [r13+8]; struct SC_PACKET *
0x14006929d  mov     r12d, r8d
0x1400692a0  cmp     r12, rcx
0x1400692a3  cmovnb  r12d, ecx
0x1400692a7  sub     eax, [r13+88h]
0x1400692ae  add     eax, [r14+10h]
0x1400692b2  mov     ecx, 128h; unsigned __int64
0x1400692b7  mov     [rbp+var_40], eax
0x1400692ba  mov     [rbp+var_50], r12
0x1400692be  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x1400692c3  test    rax, rax
0x1400692c6  jz      loc_14000C200
0x1400692cc  mov     rcx, rax; this
0x1400692cf  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x1400692d4  mov     r13, rax
0x1400692d7  test    rax, rax
0x1400692da  jz      loc_14000C200
0x1400692e0  mov     r8d, [rbp+var_40]; unsigned int
0x1400692e4  mov     r9d, r12d; unsigned int
  ... truncated ...
```
