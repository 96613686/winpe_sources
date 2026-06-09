# SioRaidOverlapRoutineRead(_SIO_OVERLAP_TYPE,SIO_TABLE_ROW *,SIO_RANGE *,ulong,unsigned __int64,void *)

- ea: `0x140007be0`
- end: `0x140007f90`
- name: `?SioRaidOverlapRoutineRead@@YAJW4_SIO_OVERLAP_TYPE@@PEAVSIO_TABLE_ROW@@PEAVSIO_RANGE@@K_KPEAX@Z`
- size: `944`
- prototype: `int __high(enum _SIO_OVERLAP_TYPE, struct SIO_TABLE_ROW *, struct SIO_RANGE *, unsigned int, unsigned __int64, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140007a00`

## callees

- `0x140005eb0`
- `0x140006220`
- `0x140007be0`
- `0x140007fa0`
- `0x14000b170`
- `0x1400133a0`
- `0x1400154c0`
- `0x140015da0`
- `0x14002f7e8`
- `0x140068000`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140007c59`
- `ntoskrnl!IoAllocateMdl` at `0x140007c59`
- `ntoskrnl!IoBuildPartialMdl` at `0x140007c96`
- `ntoskrnl!IoBuildPartialMdl` at `0x140007c96`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007eec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007f36`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007eec`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007f36`

## pseudocode

```c
__int64 __fastcall SioRaidOverlapRoutineRead(int a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, __int64 *a6)
{
  SIO_LOG_PACKET *v7; // r14
  int v8; // ebp
  int v11; // eax
  unsigned int *v12; // rsi
  __int64 v13; // r12
  __int64 v14; // rcx
  struct _MDL *Mdl; // rax
  int v16; // eax
  int v17; // eax
  unsigned int *v18; // rcx
  _QWORD *v19; // r8
  __int64 v21; // r9
  __int64 v22; // r15
  int v23; // ecx
  int v24; // ecx
  int v25; // edi
  int v26; // r12d
  __int64 v27; // rax
  unsigned int v28; // r12d
  SIO_LOG_PACKET *v29; // rax
  SIO_LOG_PACKET *v30; // rax
  ULONG v31; // edi
  unsigned int v32; // eax
  unsigned int v33; // r9d
  __int64 v34; // rax
  PVOID v35; // rax
  __int64 v36; // rcx
  PVOID v37; // rax
  char v38; // cl
  SIO_LOG_PACKET *v39; // rax
  int v40; // edi
  unsigned int v41; // ebp
  unsigned int v42; // [rsp+90h] [rbp+18h]
  __int64 v43; // [rsp+A8h] [rbp+30h]

  v7 = 0;
  v8 = 0;
  if ( a1 == 1 )
    goto LABEL_2;
  v21 = *a6;
  v22 = a6[1];
  v43 = *a6;
  v23 = a1 - 2;
  if ( v23 )
  {
    v24 = v23 - 1;
    if ( !v24 )
    {
LABEL_2:
      v11 = *((_DWORD *)a6 + 9);
      v12 = (unsigned int *)a6 + 9;
      v13 = a5;
LABEL_3:
      if ( !v11 )
        a6[5] = v13;
      *v12 = a4 + v11;
      goto LABEL_16;
    }
    if ( v24 != 1 )
    {
      v8 = -1073741811;
      goto LABEL_16;
    }
    v11 = *((_DWORD *)a6 + 9);
    v12 = (unsigned int *)a6 + 9;
LABEL_28:
    v18 = v12;
    if ( !v11 )
    {
LABEL_15:
      a6[5] = 0;
      v7 = 0;
      *v18 = 0;
      goto LABEL_16;
    }
    v25 = *(_DWORD *)(v22 + 136);
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v21 + 136LL))(
            v21,
            *((unsigned int *)a6 + 6),
            a6[5]);
    v27 = a6[2];
    v28 = v26 - v25;
    if ( v27 )
    {
      v7 = *(SIO_LOG_PACKET **)v27;
      v32 = *(_DWORD *)(v27 + 40);
      v33 = *v12;
      if ( *v12 >= v32 )
        v33 = v32;
      *v12 = v33;
      SC_PACKET::SplitSequential(v7, (struct SC_PACKET *)v22, v28, v33);
      v18 = v12;
LABEL_13:
      *((_QWORD *)v7 + 17) = a6[5];
      *((_DWORD *)v7 + 36) = *v12;
      *((_DWORD *)v7 + 37) = *((_DWORD *)a6 + 6);
      *((_DWORD *)v7 + 38) = *(_DWORD *)(v22 + 152);
      *((_BYTE *)v7 + 168) = 3;
      *((_BYTE *)v7 + 170) = 1;
      *((_QWORD *)v7 + 30) = v43;
      *((_DWORD *)v7 + 69) = 1;
      *((_QWORD *)v7 + 1) = *(_QWORD *)(v22 + 8);
      *((_QWORD *)v7 + 2) = v22;
      v19 = *(_QWORD **)(v22 + 48);
      if ( *v19 != v22 + 40 )
        __fastfail(3u);
      *((_QWORD *)v7 + 7) = v22 + 40;
      *((_QWORD *)v7 + 8) = v19;
      *v19 = (char *)v7 + 56;
      *(_QWORD *)(v22 + 48) = (char *)v7 + 56;
      ++*(_DWORD *)(v22 + 72);
      if ( a6[2] )
      {
        v7 = 0;
        v8 = 15138818;
        goto LABEL_16;
      }
      goto LABEL_15;
    }
    v29 = (SIO_LOG_PACKET *)SC_PACKET::operator new(0x118u, *(struct SC_PACKET **)(v22 + 8));
    if ( v29 )
    {
      v30 = SIO_LOG_PACKET::SIO_LOG_PACKET(v29);
      v7 = v30;
      if ( v30 )
      {
        v31 = *v12;
        if ( *v12 == *(_DWORD *)(v22 + 144) )
        {
          *((_DWORD *)v30 + 19) |= *(_DWORD *)(v22 + 76) & 4;
          *((_DWORD *)v30 + 28) = 1;
          *((_QWORD *)v30 + 15) = *(_QWORD *)(v22 + 120);
          v17 = *(_DWORD *)(v22 + 164);
          if ( v17 == -1 )
            goto LABEL_12;
        }
        else
        {
          v14 = v28 + *(_QWORD *)(*(_QWORD *)(v22 + 120) + 32LL) + *(unsigned int *)(*(_QWORD *)(v22 + 120) + 44LL);
          if ( !v14 )
            v14 = 4095;
          Mdl = IoAllocateMdl((PVOID)v14, v31, 0, 0, 0);
          *((_QWORD *)v7 + 15) = Mdl;
          if ( !Mdl )
          {
            v8 = -1073741670;
            goto LABEL_16;
          }
          *((_DWORD *)v7 + 28) = 2;
          *((_WORD *)v7 + 58) = -1;
          IoBuildPartialMdl(
            *(PMDL *)(v22 + 120),
            Mdl,
            (PVOID)(v28 + *(_QWORD *)(*(_QWORD *)(v22 + 120) + 32LL) + *(unsigned int *)(*(_QWORD *)(v22 + 120) + 44LL)),
            v31);
          v16 = *(_DWORD *)(v22 + 164);
          if ( v16 == -1 )
            goto LABEL_12;
          v17 = v28 + v16;
        }
        *((_DWORD *)v7 + 41) = v17;
LABEL_12:
        v8 = 0;
        v18 = (unsigned int *)a6 + 9;
        goto LABEL_13;
      }
    }
    else
    {
      v7 = 0;
    }
    v8 = -1073741670;
    goto LABEL_16;
  }
  v13 = a5;
  if ( *(_DWORD *)(a3 + 32) != 1 )
  {
    if ( *(_DWORD *)(a3 + 32) != 2 )
    {
      v8 = -1073741811;
      goto LABEL_16;
    }
    v38 = 1;
LABEL_27:
    v11 = *((_DWORD *)a6 + 9);
    v12 = (unsigned int *)a6 + 9;
    if ( v38 )
      goto LABEL_3;
    goto LABEL_28;
  }
  if ( *((_DWORD *)a6 + 9) )
  {
    if ( a6[2] )
    {
LABEL_57:
      v38 = 0;
      goto LABEL_27;
    }
  }
  else if ( a6[2] )
  {
LABEL_59:
    v8 = -1073741670;
    goto LABEL_16;
  }
  v39 = (SIO_LOG_PACKET *)SC_PACKET::operator new(0x118u, *(struct SC_PACKET **)(v22 + 8));
  if ( !v39 )
    goto LABEL_59;
  v7 = SIO_LOG_PACKET::SIO_LOG_PACKET(v39);
  if ( !v7 )
    goto LABEL_59;
  v40 = *(_DWORD *)(v22 + 136);
  v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v43 + 136LL))(
          v43,
          *((unsigned int *)a6 + 6),
          a5)
      - v40;
  v42 = v41;
  if ( SC_BUFFER::IsStable((SC_BUFFER *)(v22 + 112)) )
  {
    v8 = SC_PACKET::Split(v7, (struct SC_PACKET *)v22, v41, a4, 0);
    if ( v8 < 0 )
      goto LABEL_16;
    v34 = *((_QWORD *)v7 + 15);
    if ( (*(_BYTE *)(v34 + 10) & 5) != 0 )
      v35 = *(PVOID *)(v34 + 24);
    else
      v35 = MmMapLockedPagesSpecifyCache((PMDL)v34, 0, MmCached, 0, 0, 0x40000020u);
    if ( !v35 )
    {
      v8 = -1073741670;
      goto LABEL_16;
    }
    goto LABEL_70;
  }
  if ( a4 == *(_DWORD *)(v22 + 144) )
    *((_DWORD *)v7 + 19) |= *(_DWORD *)(v22 + 76) & 4;
  v8 = SC_BUFFER::Initialize((char *)v7 + 112, 3, 0, a4);
  if ( v8 >= 0 )
  {
    v36 = *(_QWORD *)(v22 + 120);
    if ( (*(_BYTE *)(v36 + 10) & 5) != 0 )
      v37 = *(PVOID *)(v36 + 24);
    else
      v37 = MmMapLockedPagesSpecifyCache((PMDL)v36, 0, MmCached, 0, 0, 0x40000020u);
    if ( !v37 )
    {
      v8 = -1073741670;
      goto LABEL_16;
    }
    *((_DWORD *)v7 + 19) |= 0x40000000u;
    SC_PACKET::SetTrackedOffset(v7, (struct SC_PACKET *)v22, v42);
LABEL_70:
    *((_QWORD *)v7 + 17) = a5;
    *((_DWORD *)v7 + 36) = a4;
    *((_DWORD *)v7 + 37) = *((_DWORD *)a6 + 6);
    *((_DWORD *)v7 + 38) = *(_DWORD *)(v22 + 152);
    *((_DWORD *)v7 + 39) = *(_DWORD *)(a3 + 60);
    *((_BYTE *)v7 + 168) = 3;
    *((_BYTE *)v7 + 170) = 8;
    *((_QWORD *)v7 + 30) = v43;
    *((_QWORD *)v7 + 31) = *(_QWORD *)(a3 + 48);
    *((_QWORD *)v7 + 32) = a5 - *(_QWORD *)(a3 + 40);
    *((_DWORD *)v7 + 66) = *(_DWORD *)(a3 + 56);
    *((_DWORD *)v7 + 68) = 0;
    *((_DWORD *)v7 + 69) = 4;
    SC_PACKET::Attach((SC_PACKET *)v22, v7, 0);
    v7 = 0;
    if ( a6[2] )
    {
      v8 = 15138818;
      goto LABEL_16;
    }
    goto LABEL_57;
  }
LABEL_16:
  if ( !a6[2] && v7 )
    (**(void (__fastcall ***)(SIO_LOG_PACKET *, __int64))v7)(v7, 1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140007be0  push    rbx
0x140007be2  push    rbp
0x140007be3  push    rsi
0x140007be4  push    rdi
0x140007be5  push    r12
0x140007be7  push    r13
0x140007be9  push    r14
0x140007beb  push    r15
0x140007bed  sub     rsp, 38h
0x140007bf1  mov     rbx, [rsp+78h+arg_28]
0x140007bf9  xor     r14d, r14d
0x140007bfc  xor     ebp, ebp
0x140007bfe  mov     r13d, r9d
0x140007c01  mov     rsi, r8
0x140007c04  cmp     ecx, 1
0x140007c07  jnz     loc_140007D8A
0x140007c0d  mov     eax, [rbx+24h]
0x140007c10  lea     rsi, [rbx+24h]
0x140007c14  mov     r12, [rsp+78h+arg_20]
0x140007c1c  test    eax, eax
0x140007c1e  jnz     short loc_140007C24
0x140007c20  mov     [rbx+28h], r12
0x140007c24  add     eax, r13d
0x140007c27  mov     [rsi], eax
0x140007c29  jmp     loc_140007D5F
0x140007c2e  mov     rax, [r15+78h]
0x140007c32  mov     edx, edi; Length
0x140007c34  mov     ebp, r12d
0x140007c37  mov     [rsp+78h+Irp], 0; Irp
0x140007c40  mov     ecx, [rax+2Ch]
0x140007c43  add     rcx, [rax+20h]
0x140007c47  mov     eax, 0FFFh
0x140007c4c  add     rcx, rbp
0x140007c4f  cmovz   rcx, rax; VirtualAddress
0x140007c53  xor     r9d, r9d; ChargeQuota
0x140007c56  xor     r8d, r8d; SecondaryBuffer
0x140007c59  call    cs:__imp_IoAllocateMdl
0x140007c60  nop     dword ptr [rax+rax+00h]
0x140007c65  mov     [r14+78h], rax
0x140007c69  test    rax, rax
0x140007c6c  jz      loc_140007D83
0x140007c72  mov     dword ptr [r14+70h], 2
0x140007c7a  mov     r9d, edi; Length
0x140007c7d  mov     word ptr [r14+74h], 0FFFFh
0x140007c84  mov     rdx, rax; TargetMdl
0x140007c87  mov     rcx, [r15+78h]; SourceMdl
0x140007c8b  mov     r8d, [rcx+2Ch]
0x140007c8f  add     r8, [rcx+20h]
0x140007c93  add     r8, rbp; VirtualAddress
0x140007c96  call    cs:__imp_IoBuildPartialMdl
0x140007c9d  nop     dword ptr [rax+rax+00h]
0x140007ca2  mov     eax, [r15+0A4h]
0x140007ca9  cmp     eax, 0FFFFFFFFh
0x140007cac  jz      short loc_140007CB8
0x140007cae  add     eax, r12d
0x140007cb1  mov     [r14+0A4h], eax
0x140007cb8  xor     ebp, ebp
0x140007cba  lea     rcx, [rbx+24h]
0x140007cbe  mov     rax, [rbx+28h]
0x140007cc2  lea     rdx, [r15+28h]
0x140007cc6  mov     r9, [rsp+78h+arg_28]
0x140007cce  mov     [r14+88h], rax
0x140007cd5  mov     eax, [rsi]
0x140007cd7  mov     [r14+90h], eax
0x140007cde  mov     eax, [rbx+18h]
0x140007ce1  mov     [r14+94h], eax
0x140007ce8  mov     eax, [r15+98h]
0x140007cef  mov     [r14+98h], eax
0x140007cf6  mov     byte ptr [r14+0A8h], 3
0x140007cfe  mov     byte ptr [r14+0AAh], 1
0x140007d06  mov     [r14+0F0h], r9
0x140007d0d  mov     dword ptr [r14+114h], 1
0x140007d18  mov     rax, [r15+8]
0x140007d1c  mov     [r14+8], rax
0x140007d20  mov     [r14+10h], r15
0x140007d24  mov     r8, [rdx+8]
0x140007d28  cmp     [r8], rdx
0x140007d2b  jnz     loc_140007DC5
0x140007d31  lea     rax, [r14+38h]
0x140007d35  mov     [rax], rdx
0x140007d38  mov     [rax+8], r8
0x140007d3c  mov     [r8], rax
0x140007d3f  mov     [rdx+8], rax
0x140007d43  inc     dword ptr [r15+48h]
0x140007d47  cmp     qword ptr [rbx+10h], 0
0x140007d4c  jnz     short loc_140007DBB
0x140007d4e  mov     qword ptr [rbx+28h], 0
0x140007d56  xor     r14d, r14d
0x140007d59  mov     dword ptr [rcx], 0
0x140007d5f  cmp     qword ptr [rbx+10h], 0
0x140007d64  jnz     short loc_140007D6F
0x140007d66  test    r14, r14
0x140007d69  jnz     loc_140007F78
0x140007d6f  mov     eax, ebp
0x140007d71  add     rsp, 38h
0x140007d75  pop     r15
0x140007d77  pop     r14
0x140007d79  pop     r13
0x140007d7b  pop     r12
0x140007d7d  pop     rdi
0x140007d7e  pop     rsi
0x140007d7f  pop     rbp
0x140007d80  pop     rbx
0x140007d81  retn
0x140007d83  mov     ebp, 0C000009Ah
0x140007d88  jmp     short loc_140007D5F
0x140007d8a  mov     r9, [rbx]
0x140007d8d  mov     r15, [rbx+8]
0x140007d91  mov     [rsp+78h+arg_28], r9
0x140007d99  sub     ecx, 2
0x140007d9c  jz      loc_140007F50
0x140007da2  sub     ecx, 1
0x140007da5  jz      loc_140007C0D
0x140007dab  cmp     ecx, 1
0x140007dae  jz      loc_140007F44
0x140007db4  mov     ebp, 0C000000Dh
0x140007db9  jmp     short loc_140007D5F
0x140007dbb  xor     r14d, r14d
0x140007dbe  mov     ebp, 0E70002h
0x140007dc3  jmp     short loc_140007D5F
0x140007dc5  mov     ecx, 3
0x140007dca  int     29h; Win8: RtlFailFast(ecx)
0x140007dcc  mov     eax, [rbx+24h]
0x140007dcf  lea     rsi, [rbx+24h]
0x140007dd3  test    cl, cl
0x140007dd5  jnz     loc_140007C1C
0x140007ddb  mov     rcx, rsi
0x140007dde  test    eax, eax
0x140007de0  jz      loc_140007D4E
0x140007de6  mov     rax, [r9]
0x140007de9  mov     rcx, r9
0x140007dec  mov     r8, [rbx+28h]
0x140007df0  mov     edx, [rbx+18h]
0x140007df3  mov     edi, [r15+88h]
0x140007dfa  mov     rax, [rax+88h]
0x140007e01  call    _guard_dispatch_icall
0x140007e06  mov     r12, rax
0x140007e09  mov     rax, [rbx+10h]
0x140007e0d  sub     r12d, edi
0x140007e10  test    rax, rax
0x140007e13  jnz     short loc_140007E84
0x140007e15  mov     rdx, [r15+8]; struct SC_PACKET *
0x140007e19  mov     ecx, 118h; unsigned __int64
0x140007e1e  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x140007e23  test    rax, rax
0x140007e26  jz      short loc_140007E77
0x140007e28  mov     rcx, rax; this
0x140007e2b  call    ??0SIO_LOG_PACKET@@QEAA@XZ; SIO_LOG_PACKET::SIO_LOG_PACKET(void)
0x140007e30  mov     r14, rax
0x140007e33  test    rax, rax
0x140007e36  jz      short loc_140007E7A
0x140007e38  mov     edi, [rsi]
0x140007e3a  cmp     edi, [r15+90h]
0x140007e41  jnz     loc_140007C2E
0x140007e47  mov     eax, [r15+4Ch]
0x140007e4b  and     eax, 4
0x140007e4e  or      [r14+4Ch], eax
0x140007e52  mov     dword ptr [r14+70h], 1
0x140007e5a  mov     rax, [r15+78h]
0x140007e5e  mov     [r14+78h], rax
0x140007e62  mov     eax, [r15+0A4h]
0x140007e69  cmp     eax, 0FFFFFFFFh
0x140007e6c  jnz     loc_140007CB1
0x140007e72  jmp     loc_140007CB8
0x140007e77  xor     r14d, r14d
0x140007e7a  mov     ebp, 0C000009Ah
0x140007e7f  jmp     loc_140007D5F
0x140007e84  mov     r14, [rax]
0x140007e87  mov     r8d, r12d; unsigned int
0x140007e8a  mov     eax, [rax+28h]
0x140007e8d  mov     rdx, r15; struct SC_PACKET *
0x140007e90  mov     r9d, [rsi]
0x140007e93  mov     rcx, r14; this
0x140007e96  cmp     r9d, eax
0x140007e99  cmovnb  r9d, eax; unsigned int
0x140007e9d  mov     [rsi], r9d
0x140007ea0  call    ?SplitSequential@SC_PACKET@@QEAAXPEAV1@KK@Z; SC_PACKET::SplitSequential(SC_PACKET *,ulong,ulong)
0x140007ea5  mov     rcx, rsi
0x140007ea8  jmp     loc_140007CBE
0x140007ead  mov     rax, [r14+78h]
0x140007eb1  test    byte ptr [rax+0Ah], 5
0x140007eb5  jz      short loc_140007ECE
0x140007eb7  mov     rax, [rax+18h]
0x140007ebb  test    rax, rax
0x140007ebe  jnz     loc_140068CB4
0x140007ec4  mov     ebp, 0C000009Ah
0x140007ec9  jmp     loc_140007D5F
0x140007ece  mov     [rsp+78h+Priority], 40000020h; Priority
0x140007ed6  xor     r9d, r9d; RequestedAddress
0x140007ed9  xor     edx, edx; AccessMode
0x140007edb  mov     dword ptr [rsp+78h+Irp], 0; BugCheckOnFailure
0x140007ee3  mov     r8d, 1; CacheType
0x140007ee9  mov     rcx, rax; MemoryDescriptorList
0x140007eec  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140007ef3  nop     dword ptr [rax+rax+00h]
0x140007ef8  jmp     short loc_140007EBB
0x140007efa  mov     rcx, [r15+78h]; MemoryDescriptorList
0x140007efe  test    byte ptr [rcx+0Ah], 5
0x140007f02  jz      short loc_140007F1B
0x140007f04  mov     rax, [rcx+18h]
0x140007f08  test    rax, rax
0x140007f0b  jnz     loc_140068C99
0x140007f11  mov     ebp, 0C000009Ah
0x140007f16  jmp     loc_140007D5F
0x140007f1b  mov     [rsp+78h+Priority], 40000020h; Priority
0x140007f23  xor     r9d, r9d; RequestedAddress
0x140007f26  xor     edx, edx; AccessMode
0x140007f28  mov     dword ptr [rsp+78h+Irp], 0; BugCheckOnFailure
0x140007f30  mov     r8d, 1; CacheType
0x140007f36  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140007f3d  nop     dword ptr [rax+rax+00h]
0x140007f42  jmp     short loc_140007F08
0x140007f44  mov     eax, [rbx+24h]
0x140007f47  lea     rsi, [rbx+24h]
0x140007f4b  jmp     loc_140007DDB
0x140007f50  mov     ecx, [r8+20h]
0x140007f54  mov     r12, [rsp+78h+arg_20]
0x140007f5c  sub     ecx, 1
0x140007f5f  jz      loc_140068BB7
0x140007f65  cmp     ecx, 1
0x140007f68  jz      loc_140068BB0
0x140007f6e  mov     ebp, 0C000000Dh
0x140007f73  jmp     loc_140007D5F
0x140007f78  mov     rax, [r14]
0x140007f7b  mov     edx, 1
0x140007f80  mov     rcx, r14
0x140007f83  mov     rax, [rax]
0x140007f86  call    _guard_dispatch_icall
0x140007f8b  jmp     loc_140007D6F
0x140068bb0  mov     cl, 1
0x140068bb2  jmp     loc_140007DCC
0x140068bb7  cmp     [rbx+24h], ebp
0x140068bba  jz      short loc_140068BC9
0x140068bbc  cmp     [rbx+10h], rbp
0x140068bc0  jz      short loc_140068BD9
0x140068bc2  xor     cl, cl
0x140068bc4  jmp     loc_140007DCC
0x140068bc9  cmp     [rbx+10h], rbp
0x140068bcd  jz      short loc_140068BD9
0x140068bcf  mov     ebp, 0C000009Ah
0x140068bd4  jmp     loc_140007D5F
0x140068bd9  mov     rdx, [r15+8]; struct SC_PACKET *
0x140068bdd  mov     ecx, 118h; unsigned __int64
0x140068be2  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x140068be7  test    rax, rax
0x140068bea  jz      short loc_140068BCF
0x140068bec  mov     rcx, rax; this
0x140068bef  call    ??0SIO_LOG_PACKET@@QEAA@XZ; SIO_LOG_PACKET::SIO_LOG_PACKET(void)
0x140068bf4  mov     r14, rax
0x140068bf7  test    rax, rax
0x140068bfa  jz      short loc_140068BCF
0x140068bfc  mov     r9, [rsp+78h+arg_28]
0x140068c04  mov     r8, r12
0x140068c07  mov     edx, [rbx+18h]
0x140068c0a  mov     edi, [r15+88h]
0x140068c11  mov     rcx, [r9]
0x140068c14  mov     rax, [rcx+88h]
0x140068c1b  mov     rcx, r9
0x140068c1e  call    _guard_dispatch_icall
0x140068c23  mov     rbp, rax
0x140068c26  lea     rcx, [r15+70h]; this
0x140068c2a  sub     ebp, edi
0x140068c2c  mov     qword ptr [rsp+78h+arg_10], rbp
0x140068c34  call    ?IsStable@SC_BUFFER@@QEAAEXZ; SC_BUFFER::IsStable(void)
0x140068c39  test    al, al
0x140068c3b  jz      short loc_140068C62
0x140068c3d  mov     r9d, r13d; unsigned int
0x140068c40  mov     byte ptr [rsp+78h+Irp], 0; unsigned __int8
0x140068c45  mov     r8d, ebp; unsigned int
0x140068c48  mov     rdx, r15; struct SC_PACKET *
0x140068c4b  mov     rcx, r14; this
0x140068c4e  call    ?Split@SC_PACKET@@QEAAJPEAV1@KKE@Z; SC_PACKET::Split(SC_PACKET *,ulong,ulong,uchar)
0x140068c53  mov     ebp, eax
0x140068c55  test    eax, eax
0x140068c57  js      loc_140007D5F
0x140068c5d  jmp     loc_140007EAD
0x140068c62  cmp     r13d, [r15+90h]
0x140068c69  jnz     short loc_140068C76
0x140068c6b  mov     eax, [r15+4Ch]
0x140068c6f  and     eax, 4
0x140068c72  or      [r14+4Ch], eax
0x140068c76  lea     rcx, [r14+70h]
0x140068c7a  mov     r9d, r13d
0x140068c7d  xor     r8d, r8d
0x140068c80  mov     edx, 3
0x140068c85  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x140068c8a  mov     ebp, eax
0x140068c8c  test    eax, eax
0x140068c8e  js      loc_140007D5F
0x140068c94  jmp     loc_140007EFA
0x140068c99  or      dword ptr [r14+4Ch], 40000000h
0x140068ca1  mov     rdx, r15; struct SC_PACKET *
0x140068ca4  mov     r8d, [rsp+78h+arg_10]; unsigned int
0x140068cac  mov     rcx, r14; this
0x140068caf  call    ?SetTrackedOffset@SC_PACKET@@QEAAXPEAV1@K@Z; SC_PACKET::SetTrackedOffset(SC_PACKET *,ulong)
0x140068cb4  mov     r9, [rsp+78h+arg_28]
0x140068cbc  xor     r8d, r8d; unsigned __int8
0x140068cbf  mov     [r14+88h], r12
0x140068cc6  mov     rdx, r14; struct SC_PACKET *
0x140068cc9  mov     [r14+90h], r13d
  ... truncated ...
```
