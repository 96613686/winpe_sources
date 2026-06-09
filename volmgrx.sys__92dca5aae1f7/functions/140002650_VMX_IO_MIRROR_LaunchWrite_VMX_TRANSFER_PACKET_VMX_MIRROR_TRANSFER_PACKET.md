# VMX_IO_MIRROR::LaunchWrite(VMX_TRANSFER_PACKET *,VMX_MIRROR_TRANSFER_PACKET * *)

- ea: `0x140002650`
- end: `0x140002b62`
- name: `?LaunchWrite@VMX_IO_MIRROR@@QEAAEPEAVVMX_TRANSFER_PACKET@@PEAPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z`
- size: `1298`
- prototype: `unsigned __int8 __fastcall(VMX_IO_MIRROR *this, KSPIN_LOCK *, struct VMX_MIRROR_TRANSFER_PACKET **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001ab0`
- `0x140003774`

## callees

- `0x140002650`
- `0x140003bd8`
- `0x14000d078`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002852`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002852`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002728`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002899`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000294d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ad4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002728`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002899`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000294d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002a17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ad4`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400027ce`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400027ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x140002671`
- `ntoskrnl!KeInitializeSpinLock` at `0x140002671`

## pseudocode

```c
unsigned __int8 __fastcall VMX_IO_MIRROR::LaunchWrite(
        VMX_IO_MIRROR *this,
        KSPIN_LOCK *a2,
        struct VMX_MIRROR_TRANSFER_PACKET **a3)
{
  KSPIN_LOCK *v6; // rsi
  _QWORD *v7; // r15
  _QWORD *v8; // r12
  KIRQL v9; // al
  KIRQL v10; // bp
  unsigned int v11; // edx
  __int64 i; // r8
  unsigned int v13; // esi
  PMDL *v14; // r13
  struct VMX_MIRROR_TRANSFER_PACKET *v15; // rbp
  KSPIN_LOCK v16; // rax
  __int64 v17; // rcx
  struct _MDL *v18; // rdx
  unsigned int v19; // eax
  int v20; // ecx
  _QWORD *v21; // rsi
  unsigned int *v22; // rbx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rdx
  __int64 v25; // rdi
  KSPIN_LOCK *v26; // rbp
  KIRQL v27; // al
  _QWORD *v28; // rcx
  _QWORD *j; // rbx
  struct VMX_MIRROR_TRANSFER_PACKET *v31; // rcx
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // r9
  char *v34; // rbx
  char **v35; // rcx
  VMX_IO_MIRROR **v36; // rdx
  char v37; // al
  __int64 v38; // r13
  unsigned int v39; // esi
  bool v40; // zf
  char v41; // [rsp+60h] [rbp+8h]

  KeInitializeSpinLock(a2 + 11);
  v6 = (KSPIN_LOCK *)((char *)this + 24);
  *((_DWORD *)a2 + 24) = 0;
  a2[13] = 0;
  v7 = *a3;
  v8 = (_QWORD *)*((_QWORD *)this + 21);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 3);
  v10 = v9;
  if ( *((_BYTE *)this + 158) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)this + 3, v9);
    *((_DWORD *)a2 + 24) = -1073741435;
    a2[13] = 0;
    goto LABEL_33;
  }
  if ( *((_DWORD *)this + 38) )
  {
    v34 = (char *)this + 136;
    v35 = (char **)*((_QWORD *)v34 + 1);
    if ( *v35 == v34 )
    {
      a2[15] = (KSPIN_LOCK)v35;
      a2[14] = (KSPIN_LOCK)v34;
      *v35 = (char *)(a2 + 14);
      *((_QWORD *)v34 + 1) = a2 + 14;
      KeReleaseSpinLock(v6, v9);
      return 0;
    }
    goto LABEL_58;
  }
  if ( !*((_BYTE *)this + 157) && a2[3] )
  {
    *((_DWORD *)this + 38) = 1;
    v36 = (VMX_IO_MIRROR **)*((_QWORD *)this + 18);
    if ( *v36 == (VMX_IO_MIRROR *)((char *)this + 136) )
    {
      a2[14] = (KSPIN_LOCK)this + 136;
      a2[15] = (KSPIN_LOCK)v36;
      *v36 = (VMX_IO_MIRROR *)(a2 + 14);
      *((_QWORD *)this + 18) = a2 + 14;
      KeReleaseSpinLock((PKSPIN_LOCK)this + 3, v9);
      a2[19] = (KSPIN_LOCK)VmxpMirrorLogDirtyOperation;
      a2[20] = (KSPIN_LOCK)VmxpMirrorLogDirtyCompletion;
      VMX_LOG::QueueLogPacket(*((VMX_LOG **)this + 16), (struct VMX_LOG_TRANSFER_PACKET *)a2);
      return 0;
    }
LABEL_58:
    __fastfail(3u);
  }
  if ( *((_BYTE *)this + 159) )
  {
    v37 = 1;
    v38 = *((_QWORD *)this + 12);
    v41 = 1;
    if ( !*((_DWORD *)this + 14) )
      goto LABEL_54;
    v39 = 0;
    do
    {
      if ( *(_BYTE *)(v38 + 20) && *(_DWORD *)(v38 + 16) != 4 )
      {
        if ( VMX_IO_MIRROR::DetachFaultTolerantMember(this, v39, 1u) )
        {
          ++*((_DWORD *)a2 + 42);
          v37 = v41;
        }
        else
        {
          v37 = 0;
          v41 = 0;
        }
      }
      ++v39;
      v38 += 40;
    }
    while ( v39 < *((_DWORD *)this + 14) );
    v6 = (KSPIN_LOCK *)((char *)this + 24);
    if ( v37 )
    {
LABEL_54:
      *((_BYTE *)this + 159) = 0;
      goto LABEL_5;
    }
    *((_BYTE *)this + 158) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)this + 3, v10);
    v40 = *((_DWORD *)a2 + 42) == 0;
    *((_DWORD *)a2 + 24) = -1073741435;
    a2[13] = 0;
    if ( !v40 )
    {
      a2[19] = (KSPIN_LOCK)VmxpMirrorLogDetachOperation;
      a2[20] = (KSPIN_LOCK)VmxpMirrorLogDetachCompletion;
      VMX_LOG::QueueLogPacket(*((VMX_LOG **)this + 16), (struct VMX_LOG_TRANSFER_PACKET *)a2);
      return 0;
    }
LABEL_33:
    ((void (__fastcall *)(KSPIN_LOCK *))a2[5])(a2);
    return 0;
  }
LABEL_5:
  *((_DWORD *)a2 + 32) = 0;
  v11 = 0;
  for ( i = *((_QWORD *)this + 12); v11 < *((_DWORD *)this + 14); i += 40 )
  {
    if ( (*(_DWORD *)(i + 16) & 0xFFFFFFFD) == 0 )
    {
      *((_DWORD *)a3[(*((_DWORD *)a2 + 32))++] + 60) = v11;
      if ( v7 == v8 )
        break;
    }
    ++v11;
  }
  KeReleaseSpinLock(v6, v10);
  v13 = 0;
  if ( *((_DWORD *)a2 + 32) )
  {
    v14 = (PMDL *)(a2 + 3);
    do
    {
      v15 = a3[v13];
      *((_DWORD *)v15 + 2) = *((_DWORD *)a2 + 2);
      v16 = a2[2];
      *((_QWORD *)v15 + 5) = VmxpMirrorWritePhase1;
      v17 = *((unsigned int *)v15 + 60);
      *((_QWORD *)v15 + 2) = v16;
      *((_QWORD *)v15 + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v17);
      *((_QWORD *)v15 + 7) = a2[7];
      *((_DWORD *)v15 + 16) = *((_DWORD *)a2 + 16);
      *((_QWORD *)v15 + 9) = a2[9];
      *(_WORD *)((char *)v15 + 81) = *((unsigned __int8 *)a2 + 81);
      *((_QWORD *)v15 + 28) = a2;
      *((_QWORD *)v15 + 29) = this;
      if ( v7 == v8 )
      {
        v14 = (PMDL *)(a2 + 3);
        *((_QWORD *)v15 + 3) = a2[3];
        v19 = 0;
        v20 = 0;
        *((_QWORD *)v15 + 31) = 0;
      }
      else
      {
        v18 = (struct _MDL *)*((_QWORD *)v15 + 3);
        if ( v18 )
          IoBuildPartialMdl(*v14, v18, (char *)(*v14)->StartVa + (*v14)->ByteOffset, (*v14)->ByteCount);
        else
          v14 = (PMDL *)(a2 + 3);
        *((_QWORD *)v15 + 31) = a3;
        v19 = v13;
        v20 = *((_DWORD *)a2 + 32);
      }
      *((_DWORD *)v15 + 64) = v20;
      ++v13;
      *((_DWORD *)v15 + 65) = v19;
    }
    while ( v13 < *((_DWORD *)a2 + 32) );
  }
  if ( v7 != v8 && v13 < *((_DWORD *)this + 14) )
  {
    do
    {
      v31 = a3[v13];
      if ( v31 )
        (**(void (__fastcall ***)(struct VMX_MIRROR_TRANSFER_PACKET *, __int64))v31)(v31, 1);
      ++v13;
    }
    while ( v13 < *((_DWORD *)this + 14) );
  }
  v21 = *a3;
  v22 = (unsigned int *)((char *)this + 104);
  v23 = *((_QWORD *)*a3 + 2);
  *((_BYTE *)v21 + 176) = 1;
  v21[27] = v22;
  v24 = v23 / v22[1] % *v22;
  v25 = *((_QWORD *)v22 + 2) + 16LL * (unsigned int)v24;
  v26 = (KSPIN_LOCK *)(*((_QWORD *)v22 + 1) + 8LL * (unsigned int)v24);
  v27 = KeAcquireSpinLockRaiseToDpc(v26);
  v28 = *(_QWORD **)(v25 + 8);
  for ( j = v28; j != (_QWORD *)v25; j = (_QWORD *)j[1] )
  {
    if ( *((_BYTE *)v21 + 176) || *((_BYTE *)j - 8) || *(j - 17) == v21[6] )
    {
      v32 = v21[2];
      v33 = *(j - 21);
      if ( v33 < v32 + *((unsigned int *)v21 + 2) && v32 < v33 + *((unsigned int *)j - 44) )
        break;
    }
  }
  if ( *v28 != v25 )
    goto LABEL_58;
  v21[24] = v28;
  v21[23] = v25;
  *v28 = v21 + 23;
  *(_QWORD *)(v25 + 8) = v21 + 23;
  *((_BYTE *)v21 + 177) = 1;
  KeReleaseSpinLock(v26, v27);
  if ( j == (_QWORD *)v25 )
    ((void (__fastcall *)(_QWORD *))v21[5])(v21);
  return 1;
}

```

## disassembly

```asm
0x140002650  mov     [rsp+arg_10], rbx
0x140002655  push    rbp
0x140002656  push    rsi
0x140002657  push    rdi
0x140002658  push    r12
0x14000265a  push    r13
0x14000265c  push    r14
0x14000265e  push    r15
0x140002660  sub     rsp, 20h
0x140002664  mov     rbx, rcx
0x140002667  mov     r14, r8
0x14000266a  lea     rcx, [rdx+58h]; SpinLock
0x14000266e  mov     rdi, rdx
0x140002671  call    cs:__imp_KeInitializeSpinLock
0x140002678  nop     dword ptr [rax+rax+00h]
0x14000267d  xor     r13d, r13d
0x140002680  lea     rsi, [rbx+18h]
0x140002684  mov     [rdi+60h], r13d
0x140002688  mov     rcx, rsi; SpinLock
0x14000268b  mov     [rdi+68h], r13
0x14000268f  mov     r15, [r14]
0x140002692  mov     r12, [rbx+0A8h]
0x140002699  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400026a0  nop     dword ptr [rax+rax+00h]
0x1400026a5  movzx   ebp, al
0x1400026a8  cmp     [rbx+9Eh], r13b
0x1400026af  jnz     loc_140002946
0x1400026b5  cmp     [rbx+98h], r13d
0x1400026bc  jnz     loc_1400029A0
0x1400026c2  cmp     [rbx+9Dh], r13b
0x1400026c9  jz      loc_140002A55
0x1400026cf  cmp     [rbx+9Fh], r13b
0x1400026d6  jnz     loc_140002A64
0x1400026dc  mov     [rdi+80h], r13d
0x1400026e3  mov     edx, r13d
0x1400026e6  cmp     dword ptr [rbx+38h], 0
0x1400026ea  mov     r8, [rbx+60h]
0x1400026ee  jbe     short loc_140002721
0x1400026f0  test    dword ptr [r8+10h], 0FFFFFFFDh
0x1400026f8  jnz     short loc_140002716
0x1400026fa  movsxd  rax, dword ptr [rdi+80h]
0x140002701  mov     rcx, [r14+rax*8]
0x140002705  mov     [rcx+0F0h], edx
0x14000270b  inc     dword ptr [rdi+80h]
0x140002711  cmp     r15, r12
0x140002714  jz      short loc_140002721
0x140002716  inc     edx
0x140002718  add     r8, 28h ; '('
0x14000271c  cmp     edx, [rbx+38h]
0x14000271f  jb      short loc_1400026F0
0x140002721  movzx   edx, bpl; NewIrql
0x140002725  mov     rcx, rsi; SpinLock
0x140002728  call    cs:__imp_KeReleaseSpinLock
0x14000272f  nop     dword ptr [rax+rax+00h]
0x140002734  cmp     dword ptr [rdi+80h], 0
0x14000273b  mov     esi, r13d
0x14000273e  jbe     loc_14000280A
0x140002744  lea     r13, [rdi+18h]
0x140002748  lea     rcx, ?VmxpMirrorWritePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorWritePhase1(VMX_TRANSFER_PACKET *)
0x14000274f  mov     eax, esi
0x140002751  mov     rbp, [r14+rax*8]
0x140002755  mov     eax, [rdi+8]
0x140002758  mov     [rbp+8], eax
0x14000275b  mov     rax, [rdi+10h]
0x14000275f  mov     [rbp+28h], rcx
0x140002763  mov     ecx, [rbp+0F0h]
0x140002769  mov     [rbp+10h], rax
0x14000276d  mov     rax, [rbx+30h]
0x140002771  mov     rcx, [rax+rcx*8]
0x140002775  mov     [rbp+30h], rcx
0x140002779  mov     rax, [rdi+38h]
0x14000277d  mov     [rbp+38h], rax
0x140002781  mov     eax, [rdi+40h]
0x140002784  mov     [rbp+40h], eax
0x140002787  mov     rax, [rdi+48h]
0x14000278b  mov     [rbp+48h], rax
0x14000278f  movzx   eax, byte ptr [rdi+51h]
0x140002793  mov     [rbp+51h], al
0x140002796  mov     byte ptr [rbp+52h], 0
0x14000279a  mov     [rbp+0E0h], rdi
0x1400027a1  mov     [rbp+0E8h], rbx
0x1400027a8  cmp     r15, r12
0x1400027ab  jz      loc_140002980
0x1400027b1  mov     rdx, [rbp+18h]; TargetMdl
0x1400027b5  test    rdx, rdx
0x1400027b8  jz      loc_140002977
0x1400027be  mov     rcx, [r13+0]; SourceMdl
0x1400027c2  mov     r8d, [rcx+2Ch]
0x1400027c6  add     r8, [rcx+20h]; VirtualAddress
0x1400027ca  mov     r9d, [rcx+28h]; Length
0x1400027ce  call    cs:__imp_IoBuildPartialMdl
0x1400027d5  nop     dword ptr [rax+rax+00h]
0x1400027da  mov     [rbp+0F8h], r14
0x1400027e1  mov     eax, esi
0x1400027e3  mov     ecx, [rdi+80h]
0x1400027e9  mov     [rbp+100h], ecx
0x1400027ef  inc     esi
0x1400027f1  mov     [rbp+104h], eax
0x1400027f7  lea     rcx, ?VmxpMirrorWritePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorWritePhase1(VMX_TRANSFER_PACKET *)
0x1400027fe  cmp     esi, [rdi+80h]
0x140002804  jb      loc_14000274F
0x14000280a  cmp     r15, r12
0x14000280d  jnz     loc_1400028CE
0x140002813  mov     rsi, [r14]
0x140002816  add     rbx, 68h ; 'h'
0x14000281a  xor     edx, edx
0x14000281c  mov     rax, [rsi+10h]
0x140002820  mov     byte ptr [rsi+0B0h], 1
0x140002827  mov     [rsi+0D8h], rbx
0x14000282e  mov     ecx, [rbx+4]
0x140002831  div     rcx
0x140002834  mov     ecx, [rbx]
0x140002836  xor     edx, edx
0x140002838  div     rcx
0x14000283b  mov     rax, [rbx+8]
0x14000283f  mov     ecx, edx
0x140002841  mov     edi, edx
0x140002843  shl     rdi, 4
0x140002847  add     rdi, [rbx+10h]
0x14000284b  lea     rbp, [rax+rcx*8]
0x14000284f  mov     rcx, rbp; SpinLock
0x140002852  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002859  nop     dword ptr [rax+rax+00h]
0x14000285e  mov     rcx, [rdi+8]
0x140002862  movzx   edx, al; NewIrql
0x140002865  mov     rbx, rcx
0x140002868  cmp     rcx, rdi
0x14000286b  jnz     loc_1400028FF
0x140002871  cmp     [rcx], rdi
0x140002874  jnz     loc_140002B5B
0x14000287a  lea     rax, [rsi+0B8h]
0x140002881  mov     [rax+8], rcx
0x140002885  mov     [rax], rdi
0x140002888  mov     [rcx], rax
0x14000288b  mov     rcx, rbp; SpinLock
0x14000288e  mov     [rdi+8], rax
0x140002892  mov     byte ptr [rsi+0B1h], 1
0x140002899  call    cs:__imp_KeReleaseSpinLock
0x1400028a0  nop     dword ptr [rax+rax+00h]
0x1400028a5  cmp     rbx, rdi
0x1400028a8  jnz     short loc_1400028B6
0x1400028aa  mov     rax, [rsi+28h]
0x1400028ae  mov     rcx, rsi
0x1400028b1  call    _guard_dispatch_icall
0x1400028b6  mov     al, 1
0x1400028b8  mov     rbx, [rsp+58h+arg_10]
0x1400028bd  add     rsp, 20h
0x1400028c1  pop     r15
0x1400028c3  pop     r14
0x1400028c5  pop     r13
0x1400028c7  pop     r12
0x1400028c9  pop     rdi
0x1400028ca  pop     rsi
0x1400028cb  pop     rbp
0x1400028cc  retn
0x1400028ce  cmp     esi, [rbx+38h]
0x1400028d1  jnb     loc_140002813
0x1400028d7  mov     eax, esi
0x1400028d9  mov     rcx, [r14+rax*8]
0x1400028dd  test    rcx, rcx
0x1400028e0  jz      short loc_1400028F2
0x1400028e2  mov     rax, [rcx]
0x1400028e5  mov     edx, 1
0x1400028ea  mov     rax, [rax]
0x1400028ed  call    _guard_dispatch_icall
0x1400028f2  inc     esi
0x1400028f4  cmp     esi, [rbx+38h]
0x1400028f7  jnb     loc_140002813
0x1400028fd  jmp     short loc_1400028D7
0x1400028ff  movzx   r10d, byte ptr [rsi+0B0h]
0x140002907  test    r10b, r10b
0x14000290a  jz      loc_140002B3B
0x140002910  mov     r8, [rsi+10h]
0x140002914  mov     eax, [rsi+8]
0x140002917  mov     r9, [rbx-0A8h]
0x14000291e  add     rax, r8
0x140002921  cmp     r9, rax
0x140002924  jnb     short loc_140002938
0x140002926  mov     eax, [rbx-0B0h]
0x14000292c  add     rax, r9
0x14000292f  cmp     r8, rax
0x140002932  jb      loc_140002871
0x140002938  mov     rbx, [rbx+8]
0x14000293c  cmp     rbx, rdi
0x14000293f  jnz     short loc_140002907
0x140002941  jmp     loc_140002871
0x140002946  movzx   edx, bpl; NewIrql
0x14000294a  mov     rcx, rsi; SpinLock
0x14000294d  call    cs:__imp_KeReleaseSpinLock
0x140002954  nop     dword ptr [rax+rax+00h]
0x140002959  mov     dword ptr [rdi+60h], 0C0000185h
0x140002960  mov     [rdi+68h], r13
0x140002964  mov     rax, [rdi+28h]
0x140002968  mov     rcx, rdi
0x14000296b  call    _guard_dispatch_icall
0x140002970  xor     al, al
0x140002972  jmp     loc_1400028B8
0x140002977  lea     r13, [rdi+18h]
0x14000297b  jmp     loc_1400027DA
0x140002980  mov     rax, [rdi+18h]
0x140002984  lea     r13, [rdi+18h]
0x140002988  mov     [rbp+18h], rax
0x14000298c  xor     eax, eax
0x14000298e  xor     ecx, ecx
0x140002990  mov     qword ptr [rbp+0F8h], 0
0x14000299b  jmp     loc_1400027E9
0x1400029a0  add     rbx, 88h
0x1400029a7  mov     rcx, [rbx+8]
0x1400029ab  cmp     [rcx], rbx
0x1400029ae  jnz     loc_140002B5B
0x1400029b4  lea     rax, [rdi+70h]
0x1400029b8  movzx   edx, bpl; NewIrql
0x1400029bc  mov     [rax+8], rcx
0x1400029c0  mov     [rax], rbx
0x1400029c3  mov     [rcx], rax
0x1400029c6  mov     rcx, rsi; SpinLock
0x1400029c9  mov     [rbx+8], rax
0x1400029cd  call    cs:__imp_KeReleaseSpinLock
0x1400029d4  nop     dword ptr [rax+rax+00h]
0x1400029d9  xor     al, al
0x1400029db  jmp     loc_1400028B8
0x1400029e0  lea     rcx, [rbx+88h]
0x1400029e7  mov     dword ptr [rbx+98h], 1
0x1400029f1  mov     rdx, [rcx+8]
0x1400029f5  cmp     [rdx], rcx
0x1400029f8  jnz     loc_140002B5B
0x1400029fe  lea     rax, [rdi+70h]
0x140002a02  mov     [rax], rcx
0x140002a05  mov     [rax+8], rdx
0x140002a09  mov     [rdx], rax
0x140002a0c  movzx   edx, bpl; NewIrql
0x140002a10  mov     [rcx+8], rax
0x140002a14  mov     rcx, rsi; SpinLock
0x140002a17  call    cs:__imp_KeReleaseSpinLock
0x140002a1e  nop     dword ptr [rax+rax+00h]
0x140002a23  lea     rax, ?VmxpMirrorLogDirtyOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpMirrorLogDirtyOperation(VMX_LOG_TRANSFER_PACKET *)
0x140002a2a  mov     rdx, rdi; struct VMX_LOG_TRANSFER_PACKET *
0x140002a2d  mov     [rdi+98h], rax
0x140002a34  lea     rax, ?VmxpMirrorLogDirtyCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpMirrorLogDirtyCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x140002a3b  mov     [rdi+0A0h], rax
0x140002a42  mov     rcx, [rbx+80h]; this
0x140002a49  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140002a4e  xor     al, al
0x140002a50  jmp     loc_1400028B8
0x140002a55  cmp     [rdi+18h], r13
0x140002a59  jz      loc_1400026CF
0x140002a5f  jmp     loc_1400029E0
0x140002a64  cmp     dword ptr [rbx+38h], 0
0x140002a68  mov     al, 1
0x140002a6a  mov     [rsp+58h+arg_8], r13d
0x140002a6f  mov     r13, [rbx+60h]
0x140002a73  mov     [rsp+58h+arg_0], al
0x140002a77  jbe     loc_140002B2C
0x140002a7d  mov     esi, [rsp+58h+arg_8]
0x140002a81  cmp     byte ptr [r13+14h], 0
0x140002a86  jz      short loc_140002AB3
0x140002a88  cmp     dword ptr [r13+10h], 4
0x140002a8d  jz      short loc_140002AB3
0x140002a8f  mov     r8b, 1; unsigned __int8
0x140002a92  mov     edx, esi; unsigned int
0x140002a94  mov     rcx, rbx; this
0x140002a97  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x140002a9c  test    al, al
0x140002a9e  jz      short loc_140002AAD
0x140002aa0  inc     dword ptr [rdi+0A8h]
0x140002aa6  movzx   eax, [rsp+58h+arg_0]
0x140002aab  jmp     short loc_140002AB3
0x140002aad  xor     al, al
0x140002aaf  mov     [rsp+58h+arg_0], al
0x140002ab3  inc     esi
0x140002ab5  add     r13, 28h ; '('
0x140002ab9  cmp     esi, [rbx+38h]
0x140002abc  jb      short loc_140002A81
0x140002abe  lea     rsi, [rbx+18h]
0x140002ac2  test    al, al
0x140002ac4  jnz     short loc_140002B2C
0x140002ac6  movzx   edx, bpl; NewIrql
0x140002aca  mov     byte ptr [rbx+9Eh], 1
0x140002ad1  mov     rcx, rsi; SpinLock
0x140002ad4  call    cs:__imp_KeReleaseSpinLock
0x140002adb  nop     dword ptr [rax+rax+00h]
0x140002ae0  cmp     dword ptr [rdi+0A8h], 0
0x140002ae7  mov     dword ptr [rdi+60h], 0C0000185h
0x140002aee  mov     qword ptr [rdi+68h], 0
0x140002af6  jbe     loc_140002964
0x140002afc  lea     rax, ?VmxpMirrorLogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpMirrorLogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x140002b03  mov     rdx, rdi; struct VMX_LOG_TRANSFER_PACKET *
0x140002b06  mov     [rdi+98h], rax
0x140002b0d  lea     rax, ?VmxpMirrorLogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpMirrorLogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x140002b14  mov     [rdi+0A0h], rax
0x140002b1b  mov     rcx, [rbx+80h]; this
0x140002b22  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140002b27  jmp     loc_140002970
0x140002b2c  mov     byte ptr [rbx+9Fh], 0
0x140002b33  xor     r13d, r13d
0x140002b36  jmp     loc_1400026DC
0x140002b3b  cmp     byte ptr [rbx-8], 0
0x140002b3f  jnz     loc_140002910
0x140002b45  mov     rax, [rsi+30h]
0x140002b49  cmp     [rbx-88h], rax
  ... truncated ...
```
