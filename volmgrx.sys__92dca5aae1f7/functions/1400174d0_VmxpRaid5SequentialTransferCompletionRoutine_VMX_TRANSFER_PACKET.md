# VmxpRaid5SequentialTransferCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x1400174d0`
- end: `0x1400178b8`
- name: `?VmxpRaid5SequentialTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `1000`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140003bd8`
- `0x140003cf0`
- `0x140007828`
- `0x14000d0dc`
- `0x14000ea38`
- `0x14000f068`
- `0x140010a30`
- `0x140010ac4`
- `0x140010c00`
- `0x1400174d0`
- `0x140018da4`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017599`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001777a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017599`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001777a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400175e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400177a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400177e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400175e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400177a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400177e9`
- `ntoskrnl!IoBuildPartialMdl` at `0x140017886`
- `ntoskrnl!IoBuildPartialMdl` at `0x140017886`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14001754a`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14001754a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140017682`
- `ntoskrnl!MmUnmapLockedPages` at `0x140017682`

## pseudocode

```c
void __fastcall VmxpRaid5SequentialTransferCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  NTSTATUS v1; // ebp
  __int64 v3; // rsi
  __int64 v4; // rdi
  NTSTATUS v5; // edx
  __int64 v6; // r8
  KIRQL v7; // al
  __int64 v8; // rdx
  KIRQL v9; // r11
  __int64 v10; // rcx
  int v11; // ebp
  unsigned __int64 v12; // r11
  char v13; // r14
  unsigned __int64 v14; // r8
  unsigned __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // r15
  __int64 v18; // r8
  unsigned int v19; // r9d
  __int64 v20; // r8
  unsigned __int64 v21; // r10
  _QWORD **v22; // rsi
  KIRQL v23; // al
  _QWORD *v24; // rbx
  _QWORD *v25; // rcx
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // rdx
  __int64 v28; // r9

  v1 = *((_DWORD *)a1 + 24);
  v3 = *((_QWORD *)a1 + 28);
  v4 = *((_QWORD *)a1 + 29);
  if ( v1 < 0 )
  {
    if ( *((_BYTE *)a1 + 82) && !*((_BYTE *)a1 + 264) && v1 != -2147483626 )
    {
      if ( FsRtlIsTotalDeviceFailure(v1) )
      {
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 24, v6, v4, v1);
        }
        v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
        v8 = *((unsigned int *)a1 + 60);
        v9 = v7;
        if ( *(_DWORD *)(*(_QWORD *)(v4 + 112) + 24 * v8 + 16) != 4
          && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v4, v8, 1) )
        {
          ++*(_DWORD *)(*((_QWORD *)a1 + 32) + 168LL);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v9);
        VMX_IO_RAID5::ReconstructStripe((VMX_IO_RAID5 *)v4, a1, 1u);
        return;
      }
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 25, v6, v4, v1);
      }
      if ( *((_QWORD *)a1 + 3) )
      {
        *((_BYTE *)a1 + 264) = 1;
        VMX_IO_RAID5::RecoverReadStripe((VMX_IO_RAID5 *)v4, a1, 1u);
        return;
      }
    }
    if ( VmxpIsWorseStatus(v1, *(_DWORD *)(v3 + 96)) )
    {
      *(_QWORD *)(v3 + 104) = 0;
LABEL_27:
      *(_DWORD *)(v3 + 96) = v1;
    }
  }
  else
  {
    v5 = *(_DWORD *)(v3 + 96);
    if ( v5 >= 0 )
      *(_QWORD *)(v3 + 104) += *((_QWORD *)a1 + 13);
    if ( *((_BYTE *)a1 + 264) && VmxpIsWorseStatus(v1, v5) )
      goto LABEL_27;
  }
  v10 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v10 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v10 + 24), *((PMDL *)a1 + 3));
  VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion((VMX_OVERLAPPED_IO_MANAGER *)(v4 + 136), a1);
  v11 = *(_DWORD *)(v4 + 124);
  v12 = *(unsigned int *)(v4 + 56);
  v13 = *(_BYTE *)(v4 + 260);
  v14 = *((_QWORD *)a1 + 2) >> v11;
  v15 = v14 % v12;
  if ( !v13 )
    LODWORD(v15) = v12 - v15 - 1;
  v16 = *((unsigned int *)a1 + 60);
  v17 = (unsigned int)(v12 - 1);
  v18 = v17 * v14;
  if ( v13 )
  {
    if ( (unsigned int)v16 >= (unsigned int)v15 )
      v16 = (unsigned int)(v16 - 1);
    goto LABEL_37;
  }
  v19 = v16 + ~(_DWORD)v15;
  if ( (unsigned int)v16 < (unsigned int)v15 )
  {
    v16 = (unsigned int)v12 + v19;
LABEL_37:
    v20 = v16 + v18;
    goto LABEL_39;
  }
  v20 = v19 + v18;
LABEL_39:
  v21 = *((unsigned int *)a1 + 2) + (v20 << v11) + (*(unsigned int *)(v4 + 128) & *((_QWORD *)a1 + 2));
  if ( v21 == *(_QWORD *)(v3 + 16) + *(unsigned int *)(v3 + 8) )
  {
    if ( *(_DWORD *)(v3 + 168) )
    {
      *(_QWORD *)(v3 + 152) = VmxpRaid5LogDetachOperation;
      *(_QWORD *)(v3 + 160) = VmxpRaid5LogDetachCompletion;
      VMX_LOG::QueueLogPacket(*(VMX_LOG **)(v4 + 232), (struct VMX_LOG_TRANSFER_PACKET *)v3);
    }
    else
    {
      (*(void (__fastcall **)(__int64))(v3 + 40))(v3);
    }
    v22 = (_QWORD **)(v4 + 280);
    while ( 1 )
    {
      v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v24 = *v22;
      if ( *v22 == v22 )
        break;
      if ( (_QWORD **)v24[1] != v22 || (v25 = (_QWORD *)*v24, *(_QWORD **)(*v24 + 8LL) != v24) )
        __fastfail(3u);
      *v22 = v25;
      v25[1] = v22;
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v23);
      if ( !VMX_IO_RAID5::LaunchParallel((VMX_IO_RAID5 *)v4, (struct VMX_TRANSFER_PACKET *)(v24 - 14)) )
      {
        VMX_IO_RAID5::LaunchSequential((VMX_IO_RAID5 *)v4, (struct VMX_TRANSFER_PACKET *)(v24 - 14));
        return;
      }
    }
    *(_BYTE *)(v4 + 265) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v23);
  }
  else
  {
    v26 = (v21 >> v11) % v17;
    v27 = (v21 >> v11) / v17 % v12;
    if ( v13 )
    {
      if ( v26 >= (unsigned int)v27 )
        LODWORD(v26) = v26 + 1;
    }
    else
    {
      v26 = (v12 + v26 - v27) % v12;
    }
    *((_DWORD *)a1 + 60) = v26;
    *((_QWORD *)a1 + 2) = ((v21 >> v11) / v17) << *(_DWORD *)(v4 + 124);
    v28 = *(unsigned int *)(v4 + 120);
    *((_DWORD *)a1 + 2) = v28;
    if ( v21 + v28 > *(_QWORD *)(v3 + 16) + (unsigned __int64)*(unsigned int *)(v3 + 8) )
    {
      LODWORD(v28) = *(_DWORD *)(v3 + 8) - v21 + *(_DWORD *)(v3 + 16);
      *((_DWORD *)a1 + 2) = v28;
    }
    IoBuildPartialMdl(
      *(PMDL *)(v3 + 24),
      *((PMDL *)a1 + 3),
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v3 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v3 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(v21 - *(_DWORD *)(v3 + 16))),
      v28);
    if ( *((_BYTE *)a1 + 82) )
      VMX_IO_RAID5::ReadStripe((VMX_IO_RAID5 *)v4, a1);
    else
      VMX_IO_RAID5::WriteStripe((VMX_IO_RAID5 *)v4, a1);
  }
}

```

## disassembly

```asm
0x1400174d0  push    rbx
0x1400174d2  push    rbp
0x1400174d3  push    rsi
0x1400174d4  push    rdi
0x1400174d5  push    r14
0x1400174d7  push    r15
0x1400174d9  sub     rsp, 38h
0x1400174dd  mov     ebp, [rcx+60h]
0x1400174e0  mov     rbx, rcx
0x1400174e3  mov     rsi, [rcx+0E0h]
0x1400174ea  mov     rdi, [rcx+0E8h]
0x1400174f1  test    ebp, ebp
0x1400174f3  js      short loc_140017525
0x1400174f5  mov     edx, [rsi+60h]; NTSTATUS
0x1400174f8  test    edx, edx
0x1400174fa  js      short loc_140017504
0x1400174fc  mov     rax, [rcx+68h]
0x140017500  add     [rsi+68h], rax
0x140017504  cmp     byte ptr [rcx+108h], 0
0x14001750b  jz      loc_140017671
0x140017511  mov     ecx, ebp; Status
0x140017513  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x140017518  test    al, al
0x14001751a  jz      loc_140017671
0x140017520  jmp     loc_14001766E
0x140017525  cmp     byte ptr [rcx+52h], 0
0x140017529  jz      loc_140017658
0x14001752f  cmp     byte ptr [rcx+108h], 0
0x140017536  jnz     loc_140017658
0x14001753c  cmp     ebp, 80000016h
0x140017542  jz      loc_140017658
0x140017548  mov     ecx, ebp; Status
0x14001754a  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140017551  nop     dword ptr [rax+rax+00h]
0x140017556  test    al, al
0x140017558  jz      loc_140017600
0x14001755e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017565  lea     rax, WPP_GLOBAL_Control
0x14001756c  cmp     rcx, rax
0x14001756f  jz      short loc_140017595
0x140017571  test    dword ptr [rcx+2Ch], 1000h
0x140017578  jz      short loc_140017595
0x14001757a  cmp     byte ptr [rcx+29h], 3
0x14001757e  jb      short loc_140017595
0x140017580  mov     rcx, [rcx+18h]
0x140017584  mov     edx, 18h
0x140017589  mov     r9, rdi
0x14001758c  mov     [rsp+68h+var_48], ebp
0x140017590  call    WPP_SF_qd
0x140017595  lea     rcx, [rdi+18h]; SpinLock
0x140017599  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400175a0  nop     dword ptr [rax+rax+00h]
0x1400175a5  mov     edx, [rbx+0F0h]; unsigned int
0x1400175ab  mov     r11b, al
0x1400175ae  mov     rcx, [rdi+70h]
0x1400175b2  lea     r8, [rdx+rdx*2]
0x1400175b6  cmp     dword ptr [rcx+r8*8+10h], 4
0x1400175bc  jz      short loc_1400175DA
0x1400175be  mov     r8b, 1; unsigned __int8
0x1400175c1  mov     rcx, rdi; this
0x1400175c4  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x1400175c9  test    al, al
0x1400175cb  jz      short loc_1400175DA
0x1400175cd  mov     rax, [rbx+100h]
0x1400175d4  inc     dword ptr [rax+0A8h]
0x1400175da  mov     dl, r11b; NewIrql
0x1400175dd  lea     rcx, [rdi+18h]; SpinLock
0x1400175e1  call    cs:__imp_KeReleaseSpinLock
0x1400175e8  nop     dword ptr [rax+rax+00h]
0x1400175ed  mov     r8b, 1; unsigned __int8
0x1400175f0  mov     rdx, rbx; struct VMX_RAID5_TRANSFER_PACKET *
0x1400175f3  mov     rcx, rdi; this
0x1400175f6  call    ?ReconstructStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::ReconstructStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x1400175fb  jmp     loc_1400178AA
0x140017600  mov     rcx, cs:WPP_GLOBAL_Control
0x140017607  lea     rax, WPP_GLOBAL_Control
0x14001760e  cmp     rcx, rax
0x140017611  jz      short loc_140017637
0x140017613  test    dword ptr [rcx+2Ch], 1000h
0x14001761a  jz      short loc_140017637
0x14001761c  cmp     byte ptr [rcx+29h], 3
0x140017620  jb      short loc_140017637
0x140017622  mov     rcx, [rcx+18h]
0x140017626  mov     edx, 19h
0x14001762b  mov     r9, rdi
0x14001762e  mov     [rsp+68h+var_48], ebp
0x140017632  call    WPP_SF_qd
0x140017637  cmp     qword ptr [rbx+18h], 0
0x14001763c  jz      short loc_140017658
0x14001763e  mov     r8b, 1; unsigned __int8
0x140017641  mov     byte ptr [rbx+108h], 1
0x140017648  mov     rdx, rbx; struct VMX_RAID5_TRANSFER_PACKET *
0x14001764b  mov     rcx, rdi; this
0x14001764e  call    ?RecoverReadStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::RecoverReadStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140017653  jmp     loc_1400178AA
0x140017658  mov     edx, [rsi+60h]; NTSTATUS
0x14001765b  mov     ecx, ebp; Status
0x14001765d  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x140017662  test    al, al
0x140017664  jz      short loc_140017671
0x140017666  mov     qword ptr [rsi+68h], 0
0x14001766e  mov     [rsi+60h], ebp
0x140017671  mov     rcx, [rbx+18h]
0x140017675  test    byte ptr [rcx+0Ah], 20h
0x140017679  jz      short loc_14001768E
0x14001767b  mov     rdx, rcx; MemoryDescriptorList
0x14001767e  mov     rcx, [rcx+18h]; BaseAddress
0x140017682  call    cs:__imp_MmUnmapLockedPages
0x140017689  nop     dword ptr [rax+rax+00h]
0x14001768e  lea     rcx, [rdi+88h]; this
0x140017695  mov     rdx, rbx; struct VMX_OVERLAP_TRANSFER_PACKET *
0x140017698  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x14001769d  mov     r10, [rbx+10h]
0x1400176a1  xor     edx, edx
0x1400176a3  mov     ebp, [rdi+7Ch]
0x1400176a6  mov     r8, r10
0x1400176a9  mov     r11d, [rdi+38h]
0x1400176ad  mov     ecx, ebp
0x1400176af  mov     r14b, [rdi+104h]
0x1400176b6  shr     r8, cl
0x1400176b9  mov     rax, r8
0x1400176bc  div     r11
0x1400176bf  test    r14b, r14b
0x1400176c2  jnz     short loc_1400176CC
0x1400176c4  mov     eax, r11d
0x1400176c7  sub     eax, edx
0x1400176c9  lea     edx, [rax-1]
0x1400176cc  mov     ecx, [rbx+0F0h]
0x1400176d2  lea     r15d, [r11-1]
0x1400176d6  imul    r8, r15
0x1400176da  test    r14b, r14b
0x1400176dd  jz      short loc_1400176E7
0x1400176df  cmp     ecx, edx
0x1400176e1  jb      short loc_1400176F8
0x1400176e3  dec     ecx
0x1400176e5  jmp     short loc_1400176F8
0x1400176e7  mov     r9d, edx
0x1400176ea  not     r9d
0x1400176ed  add     r9d, ecx
0x1400176f0  cmp     ecx, edx
0x1400176f2  jnb     short loc_1400176FD
0x1400176f4  lea     ecx, [r11+r9]
0x1400176f8  add     r8, rcx
0x1400176fb  jmp     short loc_140017703
0x1400176fd  mov     eax, r9d
0x140017700  add     r8, rax
0x140017703  mov     eax, [rbx+8]
0x140017706  mov     ecx, ebp
0x140017708  mov     edx, [rdi+80h]
0x14001770e  and     r10, rdx
0x140017711  shl     r8, cl
0x140017714  add     r10, r8
0x140017717  add     r10, rax
0x14001771a  mov     eax, [rsi+8]
0x14001771d  add     rax, [rsi+10h]
0x140017721  cmp     r10, rax
0x140017724  jnz     loc_1400177FA
0x14001772a  cmp     dword ptr [rsi+0A8h], 0
0x140017731  jbe     short loc_140017760
0x140017733  lea     rax, ?VmxpRaid5LogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpRaid5LogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x14001773a  mov     rdx, rsi; struct VMX_LOG_TRANSFER_PACKET *
0x14001773d  mov     [rsi+98h], rax
0x140017744  lea     rax, ?VmxpRaid5LogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpRaid5LogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x14001774b  mov     [rsi+0A0h], rax
0x140017752  mov     rcx, [rdi+0E8h]; this
0x140017759  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x14001775e  jmp     short loc_14001776C
0x140017760  mov     rax, [rsi+28h]
0x140017764  mov     rcx, rsi
0x140017767  call    _guard_dispatch_icall
0x14001776c  lea     rbp, [rdi+18h]
0x140017770  lea     rsi, [rdi+118h]
0x140017777  mov     rcx, rbp; SpinLock
0x14001777a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017781  nop     dword ptr [rax+rax+00h]
0x140017786  mov     rbx, [rsi]
0x140017789  cmp     rbx, rsi
0x14001778c  jz      short loc_1400177DD
0x14001778e  cmp     [rbx+8], rsi
0x140017792  jnz     short loc_1400177D6
0x140017794  mov     rcx, [rbx]
0x140017797  cmp     [rcx+8], rbx
0x14001779b  jnz     short loc_1400177D6
0x14001779d  mov     [rsi], rcx
0x1400177a0  mov     dl, al; NewIrql
0x1400177a2  mov     [rcx+8], rsi
0x1400177a6  mov     rcx, rbp; SpinLock
0x1400177a9  call    cs:__imp_KeReleaseSpinLock
0x1400177b0  nop     dword ptr [rax+rax+00h]
0x1400177b5  lea     rdx, [rbx-70h]; struct VMX_TRANSFER_PACKET *
0x1400177b9  mov     rcx, rdi; this
0x1400177bc  call    ?LaunchParallel@VMX_IO_RAID5@@QEAAEPEAVVMX_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::LaunchParallel(VMX_TRANSFER_PACKET *)
0x1400177c1  test    al, al
0x1400177c3  jnz     short loc_140017777
0x1400177c5  lea     rdx, [rbx-70h]; struct VMX_TRANSFER_PACKET *
0x1400177c9  mov     rcx, rdi; this
0x1400177cc  call    ?LaunchSequential@VMX_IO_RAID5@@QEAAXPEAVVMX_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::LaunchSequential(VMX_TRANSFER_PACKET *)
0x1400177d1  jmp     loc_1400178AA
0x1400177d6  mov     ecx, 3
0x1400177db  int     29h; Win8: RtlFailFast(ecx)
0x1400177dd  mov     dl, al; NewIrql
0x1400177df  mov     byte ptr [rdi+109h], 0
0x1400177e6  mov     rcx, rbp; SpinLock
0x1400177e9  call    cs:__imp_KeReleaseSpinLock
0x1400177f0  nop     dword ptr [rax+rax+00h]
0x1400177f5  jmp     loc_1400178AA
0x1400177fa  xor     edx, edx
0x1400177fc  mov     rax, r10
0x1400177ff  shr     rax, cl
0x140017802  div     r15
0x140017805  mov     r9, rdx
0x140017808  mov     rbp, rax
0x14001780b  xor     edx, edx
0x14001780d  div     r11
0x140017810  test    r14b, r14b
0x140017813  jz      short loc_140017825
0x140017815  mov     r8d, edx
0x140017818  lea     rcx, [r9+1]
0x14001781c  cmp     r9, r8
0x14001781f  cmovnb  r9, rcx
0x140017823  jmp     short loc_140017834
0x140017825  sub     r9, rdx
0x140017828  xor     edx, edx
0x14001782a  lea     rax, [r11+r9]
0x14001782e  div     r11
0x140017831  mov     r9, rdx
0x140017834  mov     [rbx+0F0h], r9d
0x14001783b  mov     ecx, [rdi+7Ch]
0x14001783e  shl     rbp, cl
0x140017841  mov     [rbx+10h], rbp
0x140017845  mov     r9d, [rdi+78h]
0x140017849  mov     [rbx+8], r9d
0x14001784d  mov     edx, [rsi+8]
0x140017850  mov     eax, edx
0x140017852  add     rax, [rsi+10h]
0x140017856  lea     rcx, [r10+r9]
0x14001785a  cmp     rcx, rax
0x14001785d  jbe     short loc_14001786D
0x14001785f  mov     r9d, [rsi+10h]
0x140017863  sub     edx, r10d
0x140017866  add     r9d, edx; Length
0x140017869  mov     [rbx+8], r9d
0x14001786d  mov     rcx, [rsi+18h]; SourceMdl
0x140017871  sub     r10d, [rsi+10h]
0x140017875  mov     rdx, [rbx+18h]; TargetMdl
0x140017879  mov     r8d, r10d
0x14001787c  mov     eax, [rcx+2Ch]
0x14001787f  add     r8, rax
0x140017882  add     r8, [rcx+20h]; VirtualAddress
0x140017886  call    cs:__imp_IoBuildPartialMdl
0x14001788d  nop     dword ptr [rax+rax+00h]
0x140017892  cmp     byte ptr [rbx+52h], 0
0x140017896  mov     rdx, rbx; struct VMX_RAID5_WRITE_TRANSFER_PACKET *
0x140017899  mov     rcx, rdi; this
0x14001789c  jz      short loc_1400178A5
0x14001789e  call    ?ReadStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::ReadStripe(VMX_RAID5_TRANSFER_PACKET *)
0x1400178a3  jmp     short loc_1400178AA
0x1400178a5  call    ?WriteStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_WRITE_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::WriteStripe(VMX_RAID5_WRITE_TRANSFER_PACKET *)
0x1400178aa  add     rsp, 38h
0x1400178ae  pop     r15
0x1400178b0  pop     r14
0x1400178b2  pop     rdi
0x1400178b3  pop     rsi
0x1400178b4  pop     rbp
0x1400178b5  pop     rbx
0x1400178b6  retn
```
