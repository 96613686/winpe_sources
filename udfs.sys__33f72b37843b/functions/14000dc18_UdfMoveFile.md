# UdfMoveFile

- ea: `0x14000dc18`
- end: `0x14000e432`
- name: `UdfMoveFile`
- size: `2074`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x140004340`
- `0x1400050d8`
- `0x14000dc18`
- `0x14000e438`
- `0x14000e5d8`
- `0x1400103d8`
- `0x140010dd0`
- `0x140017498`
- `0x14001c080`
- `0x140045f10`
- `0x1400473c0`
- `0x140049bb0`
- `0x14004ce50`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e110`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e110`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e044`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e0bd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e29b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e3a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e3be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d11b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d178`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d193`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e044`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e0bd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e29b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e3a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e3be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d11b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d178`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d193`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14000e1ed`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14000e1ed`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14000e20e`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14000e20e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e2b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e36d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d136`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e2b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000e36d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001d136`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000dfcf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e2e7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e38e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d163`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000dfcf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e2e7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000e38e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d163`
- `ntoskrnl!IoIs32bitProcess` at `0x14000dcba`
- `ntoskrnl!IoIs32bitProcess` at `0x14000dcba`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000dd58`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000dd58`
- `ntoskrnl!IoFileObjectType` at `0x14000dd49`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3d2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3e6`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d1bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3d2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3e6`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d1bb`

## pseudocode

```c
__int64 __fastcall UdfMoveFile(__int64 a1, IRP *a2)
{
  PVOID v4; // r15
  __int64 v5; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int Options; // ebx
  struct _IRP *MasterIrp; // rcx
  void *v9; // r10
  struct _IRP *v10; // r12
  NTSTATUS v11; // r14d
  int v13; // eax
  __int64 v14; // rbx
  LONG IrpCount; // r8d
  unsigned int Flags; // eax
  LONG v17; // edx
  __int64 v18; // r8
  unsigned int MdlAddress; // r9d
  int v20; // ecx
  unsigned int v21; // r15d
  __int64 v22; // rcx
  unsigned int v23; // r9d
  __int64 v24; // rcx
  PVOID v25; // rdx
  PVOID PoolWithTag; // rax
  __int64 v27; // r8
  LARGE_MCB *v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // r15d
  int v31; // ebx
  POBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+28h] [rbp-100h]
  int v33; // [rsp+30h] [rbp-F8h]
  int v34; // [rsp+30h] [rbp-F8h]
  unsigned int v35; // [rsp+44h] [rbp-E4h] BYREF
  LONGLONG Lbn; // [rsp+48h] [rbp-E0h]
  LONGLONG SectorCount; // [rsp+50h] [rbp-D8h] BYREF
  unsigned int v38; // [rsp+58h] [rbp-D0h]
  char v39; // [rsp+5Ch] [rbp-CCh]
  unsigned int v40; // [rsp+60h] [rbp-C8h] BYREF
  int v41; // [rsp+64h] [rbp-C4h] BYREF
  LONG v42; // [rsp+68h] [rbp-C0h]
  PVOID v43; // [rsp+70h] [rbp-B8h]
  __int64 v44; // [rsp+78h] [rbp-B0h] BYREF
  int v45; // [rsp+80h] [rbp-A8h] BYREF
  unsigned int v46; // [rsp+84h] [rbp-A4h]
  PVOID Object; // [rsp+88h] [rbp-A0h] BYREF
  PVOID v48; // [rsp+90h] [rbp-98h] BYREF
  size_t Size; // [rsp+98h] [rbp-90h]
  size_t v50; // [rsp+A0h] [rbp-88h] BYREF
  PLARGE_MCB Mcb; // [rsp+A8h] [rbp-80h]
  __int64 v52; // [rsp+B0h] [rbp-78h]
  unsigned int v53; // [rsp+B8h] [rbp-70h]
  int v54; // [rsp+BCh] [rbp-6Ch]
  int v55; // [rsp+C0h] [rbp-68h]
  __int128 v56; // [rsp+C8h] [rbp-60h] BYREF
  __int128 v57; // [rsp+D8h] [rbp-50h]
  char v58; // [rsp+138h] [rbp+10h] BYREF
  char v59; // [rsp+140h] [rbp+18h]
  char v60; // [rsp+148h] [rbp+20h] BYREF

  v4 = 0;
  Object = 0;
  v5 = *(_QWORD *)(a1 + 16);
  v52 = v5;
  v44 = 0;
  SectorCount = 0;
  v41 = 0;
  v40 = 0;
  v45 = 0;
  v50 = 0;
  v58 = 0;
  v60 = 0;
  v56 = 0;
  v57 = 0;
  *(_DWORD *)(a1 + 28) |= 4u;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned int)UdfDecodeFileObject(CurrentStackLocation->FileObject, &v44, &SectorCount) == 2
    && (*(_DWORD *)(v5 + 48) & 0x10) == 0 )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    if ( IoIs32bitProcess(a2) )
    {
      if ( Options < 0x20 )
        goto LABEL_7;
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      DWORD2(v57) = MasterIrp->AssociatedIrp.IrpCount;
      v9 = (void *)*(int *)&MasterIrp->Type;
      *(_QWORD *)&v56 = v9;
      *(_QWORD *)&v57 = *(_QWORD *)&MasterIrp->Flags;
      *((_QWORD *)&v56 + 1) = MasterIrp->MdlAddress;
      v10 = (struct _IRP *)&v56;
    }
    else
    {
      if ( Options < 0x20 )
        goto LABEL_7;
      v10 = a2->AssociatedIrp.MasterIrp;
      v9 = *(void **)&v10->Type;
    }
    v11 = ObReferenceObjectByHandle(v9, 0, (POBJECT_TYPE)IoFileObjectType, a2->RequestorMode, &Object, 0);
    if ( v11 < 0 )
      goto LABEL_8;
    v13 = UdfDecodeFileObject(Object, &v44, &SectorCount);
    if ( *((_QWORD *)Object + 2) == *(_QWORD *)(v5 + 8) && (unsigned int)(v13 - 3) <= 1 )
    {
      v14 = v44;
      if ( (v13 != 3 || (*(_DWORD *)(v44 + 212) & 0x8000000) == 0) && !HIDWORD(v10->MdlAddress) && !*(&v10->Flags + 1) )
      {
        IrpCount = v10->AssociatedIrp.IrpCount;
        if ( (unsigned int)(IrpCount + LODWORD(v10->MdlAddress)) >= LODWORD(v10->MdlAddress) )
        {
          Flags = v10->Flags;
          if ( Flags + IrpCount >= Flags && Flags + IrpCount <= *(_DWORD *)(v5 + 664) )
          {
            v46 = 0;
            v59 = 0;
            v43 = 0;
            v48 = 0;
            v38 = 0;
            LODWORD(Lbn) = 0;
            UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v44 + 136) + 80LL) + 8LL, 0, 0);
            UdfAcquireResource(a1, *(_QWORD *)(v14 + 16), 0, 0);
            UdfVerifyScbOperation(a1, v14, SectorCount);
            v17 = v10->AssociatedIrp.IrpCount;
            LODWORD(SectorCount) = v17;
            v42 = v17;
            if ( (*(_DWORD *)(v14 + 212) & 2) == 0 )
            {
              v18 = *(_QWORD *)(v14 + 24) >> *(_DWORD *)(v5 + 72);
              MdlAddress = (unsigned int)v10->MdlAddress;
              if ( v17 + MdlAddress <= (unsigned int)v18 )
                goto LABEL_24;
              if ( MdlAddress < (unsigned int)v18 )
              {
                v17 = v18 - MdlAddress;
                LODWORD(SectorCount) = v18 - MdlAddress;
                v42 = v18 - MdlAddress;
LABEL_24:
                while ( v17 )
                {
                  v20 = *(_DWORD *)(v5 + 72);
                  v35 = v17 << v20;
                  UdfLookupAllocation(
                    a1,
                    v14,
                    (unsigned __int64)MdlAddress << v20,
                    (unsigned int)&v50,
                    (__int64)&v35,
                    1,
                    (__int64)&v58,
                    (__int64)&v60);
                  v21 = v35 >> *(_DWORD *)(v5 + 72);
                  v35 = v21;
                  if ( v21 > (unsigned int)SectorCount )
                    v21 = SectorCount;
                  v35 = v21;
                  if ( v60 )
                  {
                    if ( v58 )
                    {
                      if ( v21 > 0x20 )
                        v21 = 32;
                      v35 = v21;
                    }
                    if ( !v59 )
                    {
                      v46 = (unsigned int)v10->MdlAddress;
                      v53 = v46;
                      v59 = 1;
                      v39 = 1;
                    }
                    UdfPrepareForAllocationChange(a1, v5, 0, v21);
                    *(_DWORD *)(v5 + 668) -= v21;
                    v38 = v21;
                    *(_QWORD *)(v5 + 1640) = 0;
                    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 1584));
                    UdfAcquireResource(a1, v5 + 552, 0, 0);
                    UdfFindFreeBitmapBlocksInRange(
                      a1,
                      0,
                      v21,
                      v10->Flags,
                      v21 + v10->Flags - 1,
                      (__int64)&v41,
                      (__int64)&v40);
                    if ( v41 != v10->Flags )
                    {
                      UdfUnpinCurrentBitmapPage(v22, v5, 0);
                      ExReleaseResourceLite((PERESOURCE)(v5 + 552));
                      v11 = -1073741811;
                      v54 = -1073741811;
                      break;
                    }
                    LODWORD(Lbn) = v41 + *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL);
                    v23 = v40;
                    if ( v40 > v21 )
                      v23 = v21;
                    v40 = v23;
                    UdfChangeOrVerifyBitmapRun(a1, 0, v41, v23, 0, 0, (__int64)&v45);
                    UdfUnpinCurrentBitmapPage(v24, v5, 0);
                    ExReleaseResourceLite((PERESOURCE)(v5 + 552));
                    v38 = 0;
                    if ( v58 )
                    {
                      v25 = v43;
                      if ( !v43 )
                      {
                        Size = (unsigned int)(32 << *(_DWORD *)(v5 + 72));
                        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, Size, 0x62666455u);
                        v43 = PoolWithTag;
                        if ( !ExPoolZeroingNativelySupported && PoolWithTag )
                        {
                          memset(PoolWithTag, 0, Size);
                          PoolWithTag = v43;
                        }
                        v48 = PoolWithTag;
                        v25 = v43;
                      }
                      v27 = v21 << *(_DWORD *)(v5 + 72);
                      LOBYTE(v33) = 0;
                      HandleInformation = *(POBJECT_HANDLE_INFORMATION *)(v5 + 24);
                      Size = v50;
                      UdfReadWriteSectors(a1, v50, v27, 0, v25, HandleInformation, v33);
                      LOBYTE(v34) = 1;
                      UdfReadWriteSectors(
                        a1,
                        (unsigned __int64)(unsigned int)Lbn << *(_DWORD *)(v5 + 72),
                        v21 << *(_DWORD *)(v5 + 72),
                        0,
                        v43,
                        *(_QWORD *)(v5 + 24),
                        v34);
                      v28 = (LARGE_MCB *)(v14 + 232);
                    }
                    else
                    {
                      v28 = (LARGE_MCB *)(v14 + 264);
                      Size = v50;
                    }
                    Mcb = v28;
                    FsRtlRemoveLargeMcbEntry(v28, (LONGLONG)v10->MdlAddress, v21);
                    FsRtlAddLargeMcbEntry(Mcb, (LONGLONG)v10->MdlAddress, (unsigned int)Lbn, v21);
                    LODWORD(Lbn) = v21 + LODWORD(v10->MdlAddress);
                    v55 = Lbn;
                    UdfAcquireResource(a1, v5 + 552, 0, 0);
                    v41 = (Size >> *(_DWORD *)(v5 + 72)) - *(_DWORD *)(*(_QWORD *)(a1 + 16) + 656LL);
                    UdfChangeOrVerifyBitmapRun(a1, 0, v41, v21, 1, 0, (__int64)&v45);
                    UdfUnpinCurrentBitmapPage(v29, v5, 0);
                    ExReleaseResourceLite((PERESOURCE)(v5 + 552));
                    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 1584));
                    *(_QWORD *)(v5 + 1640) = KeGetCurrentThread();
                    *(_DWORD *)(v5 + 668) += v21;
                    *(_QWORD *)(v5 + 1640) = 0;
                    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 1584));
                    v10->Flags += v21;
                    LODWORD(v10->MdlAddress) += v21;
                    MdlAddress = (unsigned int)v10->MdlAddress;
                    v17 = SectorCount - v21;
                    LODWORD(SectorCount) = v17;
                    v42 = v17;
                    v14 = v44;
                  }
                  else
                  {
                    v17 = SectorCount - v21;
                    LODWORD(SectorCount) = v17;
                    v42 = v17;
                    LODWORD(v10->MdlAddress) += v21;
                    MdlAddress = (unsigned int)v10->MdlAddress;
                  }
                }
                if ( v59 )
                  UdfUpdateAdsFromScb(a1, v14, v46, (unsigned int)Lbn);
                v4 = v43;
              }
            }
            if ( v4 )
              UdfFreePool(&v48);
            v30 = v38;
            if ( v38 )
            {
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 1584));
              *(_DWORD *)(v5 + 668) += v30;
              *(_QWORD *)(v5 + 1640) = 0;
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 1584));
              v14 = v44;
            }
            ExReleaseResourceLite(*(PERESOURCE *)(v14 + 16));
            ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v14 + 136) + 80LL) + 8LL));
            ObfDereferenceObject(Object);
            goto LABEL_8;
          }
        }
      }
    }
    ObfDereferenceObject(Object);
LABEL_7:
    v11 = -1073741811;
LABEL_8:
    UdfCompleteRequest(a1, a2, (unsigned int)v11);
    return (unsigned int)v11;
  }
  v31 = (*(_DWORD *)(v5 + 48) & 0x20) != 0 ? 0x7E4 : 0;
  UdfCompleteRequest(a1, a2, (unsigned int)(v31 - 1073741790));
  return (unsigned int)(v31 - 1073741790);
}

```

## disassembly

```asm
0x14000dc18  mov     rax, rsp
0x14000dc1b  mov     [rax+8], rcx
0x14000dc1f  push    rbx
0x14000dc20  push    rsi
0x14000dc21  push    rdi
0x14000dc22  push    r12
0x14000dc24  push    r13
0x14000dc26  push    r14
0x14000dc28  push    r15
0x14000dc2a  sub     rsp, 0F0h
0x14000dc31  mov     r13, rdx
0x14000dc34  mov     rdi, rcx
0x14000dc37  xor     r15d, r15d
0x14000dc3a  mov     [rax-0A0h], r15
0x14000dc41  mov     rsi, [rcx+10h]
0x14000dc45  mov     [rsp+128h+var_78], rsi
0x14000dc4d  mov     [rsp+128h+var_B0], r15
0x14000dc52  mov     [rsp+128h+SectorCount], r15
0x14000dc57  mov     [rsp+128h+var_C4], r15d
0x14000dc5c  mov     [rsp+128h+var_C8], r15d
0x14000dc61  mov     [rax-0A8h], r15d
0x14000dc68  mov     [rax-88h], r15
0x14000dc6f  mov     [rax+10h], r15b
0x14000dc73  mov     [rax+20h], r15b
0x14000dc77  xorps   xmm0, xmm0
0x14000dc7a  movups  xmmword ptr [rax-60h], xmm0
0x14000dc7e  movups  xmmword ptr [rax-50h], xmm0
0x14000dc82  or      dword ptr [rcx+1Ch], 4
0x14000dc86  mov     rbx, [rdx+0B8h]
0x14000dc8d  lea     r8, [rsp+128h+SectorCount]
0x14000dc92  lea     rdx, [rsp+128h+var_B0]
0x14000dc97  mov     rcx, [rbx+30h]
0x14000dc9b  call    UdfDecodeFileObject
0x14000dca0  cmp     eax, 2
0x14000dca3  jnz     loc_14000E3F7
0x14000dca9  mov     eax, [rsi+30h]
0x14000dcac  test    al, 10h
0x14000dcae  jnz     loc_14000E3F7
0x14000dcb4  mov     ebx, [rbx+10h]
0x14000dcb7  mov     rcx, r13; Irp
0x14000dcba  call    cs:__imp_IoIs32bitProcess
0x14000dcc1  nop     dword ptr [rax+rax+00h]
0x14000dcc6  test    al, al
0x14000dcc8  jz      short loc_14000DD0A
0x14000dcca  cmp     ebx, 20h ; ' '
0x14000dccd  jb      short loc_14000DD0F
0x14000dccf  mov     rcx, [r13+18h]
0x14000dcd3  mov     eax, [rcx+18h]
0x14000dcd6  mov     [rsp+128h+var_48], eax
0x14000dcdd  movsxd  r10, dword ptr [rcx]
0x14000dce0  mov     [rsp+128h+var_60], r10
0x14000dce8  mov     rax, [rcx+10h]
0x14000dcec  mov     [rsp+128h+var_50], rax
0x14000dcf4  mov     rax, [rcx+8]
0x14000dcf8  mov     [rsp+128h+var_58], rax
0x14000dd00  lea     r12, [rsp+128h+var_60]
0x14000dd08  jmp     short loc_14000DD33
0x14000dd0a  cmp     ebx, 20h ; ' '
0x14000dd0d  jnb     short loc_14000DD2B
0x14000dd0f  mov     r14d, 0C000000Dh
0x14000dd15  mov     r8d, r14d
0x14000dd18  mov     rdx, r13
0x14000dd1b  mov     rcx, rdi
0x14000dd1e  call    UdfCompleteRequest
0x14000dd23  mov     eax, r14d
0x14000dd26  jmp     loc_14000E41E
0x14000dd2b  mov     r12, [r13+18h]
0x14000dd2f  mov     r10, [r12]
0x14000dd33  mov     [rsp+128h+HandleInformation], r15; HandleInformation
0x14000dd38  lea     rax, [rsp+128h+var_A0]
0x14000dd40  mov     [rsp+128h+Object], rax; Object
0x14000dd45  mov     r9b, [r13+40h]; AccessMode
0x14000dd49  mov     r8, cs:__imp_IoFileObjectType
0x14000dd50  mov     r8, [r8]; ObjectType
0x14000dd53  xor     edx, edx; DesiredAccess
0x14000dd55  mov     rcx, r10; Handle
0x14000dd58  call    cs:__imp_ObReferenceObjectByHandle
0x14000dd5f  nop     dword ptr [rax+rax+00h]
0x14000dd64  mov     r14d, eax
0x14000dd67  test    eax, eax
0x14000dd69  js      short loc_14000DD15
0x14000dd6b  lea     r8, [rsp+128h+SectorCount]
0x14000dd70  lea     rdx, [rsp+128h+var_B0]
0x14000dd75  mov     rcx, [rsp+128h+var_A0]
0x14000dd7d  call    UdfDecodeFileObject
0x14000dd82  mov     rcx, [rsi+8]
0x14000dd86  mov     rdx, [rsp+128h+var_A0]
0x14000dd8e  cmp     [rdx+10h], rcx
0x14000dd92  jnz     loc_14000E3E3
0x14000dd98  lea     ecx, [rax-3]
0x14000dd9b  cmp     ecx, 1
0x14000dd9e  ja      loc_14000E3E3
0x14000dda4  mov     rbx, [rsp+128h+var_B0]
0x14000dda9  cmp     eax, 3
0x14000ddac  jnz     short loc_14000DDBE
0x14000ddae  test    dword ptr [rbx+0D4h], 8000000h
0x14000ddb8  jnz     loc_14000E3E3
0x14000ddbe  cmp     [r12+0Ch], r15d
0x14000ddc3  jnz     loc_14000E3E3
0x14000ddc9  cmp     [r12+14h], r15d
0x14000ddce  jnz     loc_14000E3E3
0x14000ddd4  mov     ecx, [r12+8]
0x14000ddd9  mov     r8d, [r12+18h]
0x14000ddde  lea     eax, [r8+rcx]
0x14000dde2  cmp     eax, ecx
0x14000dde4  jb      loc_14000E3E3
0x14000ddea  mov     eax, [r12+10h]
0x14000ddef  lea     ecx, [rax+r8]
0x14000ddf3  cmp     ecx, eax
0x14000ddf5  jb      loc_14000E3E3
0x14000ddfb  cmp     ecx, [rsi+298h]
0x14000de01  ja      loc_14000E3E3
0x14000de07  mov     [rsp+128h+var_A4], r15d
0x14000de0f  mov     [rsp+128h+var_E8], r15b
0x14000de14  mov     [rsp+128h+var_E7], r15b
0x14000de19  mov     [rsp+128h+arg_10], r15b
0x14000de21  mov     [rsp+128h+var_B8], r15
0x14000de26  mov     [rsp+128h+var_98], r15
0x14000de2e  mov     [rsp+128h+var_D0], r15d
0x14000de33  mov     dword ptr [rsp+128h+Lbn], r15d
0x14000de38  mov     rax, [rbx+88h]
0x14000de3f  mov     rdx, [rax+50h]
0x14000de43  add     rdx, 8
0x14000de47  xor     r9d, r9d
0x14000de4a  xor     r8d, r8d
0x14000de4d  mov     rcx, rdi
0x14000de50  call    UdfAcquireResource
0x14000de55  xor     r9d, r9d
0x14000de58  xor     r8d, r8d
0x14000de5b  mov     rdx, [rbx+10h]
0x14000de5f  mov     rcx, rdi
0x14000de62  call    UdfAcquireResource
0x14000de67  nop
0x14000de68  mov     r8, [rsp+128h+SectorCount]
0x14000de6d  mov     rdx, rbx
0x14000de70  mov     rcx, rdi
0x14000de73  call    UdfVerifyScbOperation
0x14000de78  mov     edx, [r12+18h]
0x14000de7d  mov     dword ptr [rsp+128h+SectorCount], edx
0x14000de81  mov     [rsp+128h+var_C0], edx
0x14000de85  mov     eax, [rbx+0D4h]
0x14000de8b  test    al, 2
0x14000de8d  jnz     loc_14000E347
0x14000de93  mov     r8, [rbx+18h]
0x14000de97  mov     ecx, [rsi+48h]
0x14000de9a  shr     r8, cl
0x14000de9d  mov     r9d, [r12+8]
0x14000dea2  lea     eax, [rdx+r9]
0x14000dea6  cmp     eax, r8d
0x14000dea9  jbe     short loc_14000DEC2
0x14000deab  cmp     r9d, r8d
0x14000deae  jnb     loc_14000E347
0x14000deb4  mov     edx, r8d
0x14000deb7  sub     edx, r9d
0x14000deba  mov     dword ptr [rsp+128h+SectorCount], edx
0x14000debe  mov     [rsp+128h+var_C0], edx
0x14000dec2  test    edx, edx
0x14000dec4  jz      loc_14000E320
0x14000deca  mov     ecx, [rsi+48h]
0x14000decd  mov     eax, edx
0x14000decf  shl     eax, cl
0x14000ded1  mov     [rsp+128h+var_E4], eax
0x14000ded5  mov     r8d, r9d
0x14000ded8  shl     r8, cl
0x14000dedb  lea     rax, [rsp+128h+arg_18]
0x14000dee3  mov     [rsp+128h+var_F0], rax
0x14000dee8  lea     rax, [rsp+128h+arg_8]
0x14000def0  mov     [rsp+128h+var_F8], rax
0x14000def5  mov     byte ptr [rsp+128h+HandleInformation], 1
0x14000defa  lea     rax, [rsp+128h+var_E4]
0x14000deff  mov     [rsp+128h+Object], rax
0x14000df04  lea     r9, [rsp+128h+var_88]
0x14000df0c  mov     rdx, rbx
0x14000df0f  mov     rcx, rdi
0x14000df12  call    UdfLookupAllocation
0x14000df17  mov     ecx, [rsi+48h]
0x14000df1a  mov     r15d, [rsp+128h+var_E4]
0x14000df1f  shr     r15d, cl
0x14000df22  mov     [rsp+128h+var_E4], r15d
0x14000df27  mov     edx, dword ptr [rsp+128h+SectorCount]
0x14000df2b  cmp     r15d, edx
0x14000df2e  cmova   r15d, edx
0x14000df32  mov     [rsp+128h+var_E4], r15d
0x14000df37  cmp     [rsp+128h+arg_18], 0
0x14000df3f  jnz     short loc_14000DF5B
0x14000df41  sub     edx, r15d
0x14000df44  mov     dword ptr [rsp+128h+SectorCount], edx
0x14000df48  mov     [rsp+128h+var_C0], edx
0x14000df4c  add     [r12+8], r15d
0x14000df51  mov     r9d, [r12+8]
0x14000df56  jmp     loc_14000DEC2
0x14000df5b  cmp     [rsp+128h+arg_8], 0
0x14000df63  jz      short loc_14000DF76
0x14000df65  mov     eax, 20h ; ' '
0x14000df6a  cmp     r15d, eax
0x14000df6d  cmova   r15d, eax
0x14000df71  mov     [rsp+128h+var_E4], r15d
0x14000df76  cmp     [rsp+128h+arg_10], 0
0x14000df7e  jnz     short loc_14000DFA0
0x14000df80  mov     eax, [r12+8]
0x14000df85  mov     [rsp+128h+var_A4], eax
0x14000df8c  mov     [rsp+128h+var_70], eax
0x14000df93  mov     al, 1
0x14000df95  mov     [rsp+128h+arg_10], al
0x14000df9c  mov     [rsp+128h+var_CC], al
0x14000dfa0  mov     r9d, r15d
0x14000dfa3  xor     r8d, r8d
0x14000dfa6  mov     rdx, rsi
0x14000dfa9  mov     rcx, rdi
0x14000dfac  call    UdfPrepareForAllocationChange
0x14000dfb1  sub     [rsi+29Ch], r15d
0x14000dfb8  mov     [rsp+128h+var_D0], r15d
0x14000dfbd  mov     qword ptr [rsi+668h], 0
0x14000dfc8  lea     rcx, [rsi+630h]; FastMutex
0x14000dfcf  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000dfd6  nop     dword ptr [rax+rax+00h]
0x14000dfdb  lea     rdx, [rsi+228h]
0x14000dfe2  xor     r9d, r9d
0x14000dfe5  xor     r8d, r8d
0x14000dfe8  mov     rcx, rdi
0x14000dfeb  call    UdfAcquireResource
0x14000dff0  mov     [rsp+128h+var_E8], 1
0x14000dff5  mov     r9d, [r12+10h]
0x14000dffa  lea     eax, [r9-1]
0x14000dffe  add     eax, r15d
0x14000e001  lea     rcx, [rsp+128h+var_C8]
0x14000e006  mov     [rsp+128h+var_F8], rcx
0x14000e00b  lea     rcx, [rsp+128h+var_C4]
0x14000e010  mov     [rsp+128h+HandleInformation], rcx
0x14000e015  mov     dword ptr [rsp+128h+Object], eax
0x14000e019  mov     r8d, r15d
0x14000e01c  xor     edx, edx
0x14000e01e  mov     rcx, rdi
0x14000e021  call    UdfFindFreeBitmapBlocksInRange
0x14000e026  mov     r8d, [rsp+128h+var_C4]
0x14000e02b  cmp     r8d, [r12+10h]
0x14000e030  jz      short loc_14000E068
0x14000e032  xor     r8d, r8d
0x14000e035  mov     rdx, rsi
0x14000e038  call    UdfUnpinCurrentBitmapPage
0x14000e03d  lea     rcx, [rsi+228h]; Resource
0x14000e044  call    cs:__imp_ExReleaseResourceLite
0x14000e04b  nop     dword ptr [rax+rax+00h]
0x14000e050  mov     [rsp+128h+var_E8], 0
0x14000e055  mov     r14d, 0C000000Dh
0x14000e05b  mov     [rsp+128h+var_6C], r14d
0x14000e063  jmp     loc_14000E320
0x14000e068  mov     rax, [rdi+10h]
0x14000e06c  mov     eax, [rax+290h]
0x14000e072  add     eax, r8d
0x14000e075  mov     dword ptr [rsp+128h+Lbn], eax
0x14000e079  mov     r9d, [rsp+128h+var_C8]
0x14000e07e  cmp     r9d, r15d
0x14000e081  cmova   r9d, r15d
0x14000e085  mov     [rsp+128h+var_C8], r9d
0x14000e08a  lea     rax, [rsp+128h+var_A8]
0x14000e092  mov     [rsp+128h+var_F8], rax
0x14000e097  mov     byte ptr [rsp+128h+HandleInformation], 0
0x14000e09c  mov     byte ptr [rsp+128h+Object], 0
0x14000e0a1  xor     edx, edx
0x14000e0a3  mov     rcx, rdi
0x14000e0a6  call    UdfChangeOrVerifyBitmapRun
0x14000e0ab  xor     r8d, r8d
0x14000e0ae  mov     rdx, rsi
0x14000e0b1  call    UdfUnpinCurrentBitmapPage
0x14000e0b6  lea     rcx, [rsi+228h]; Resource
0x14000e0bd  call    cs:__imp_ExReleaseResourceLite
0x14000e0c4  nop     dword ptr [rax+rax+00h]
0x14000e0c9  mov     [rsp+128h+var_E8], 0
0x14000e0ce  mov     [rsp+128h+var_D0], 0
0x14000e0d6  mov     [rsp+128h+var_E7], 1
0x14000e0db  cmp     [rsp+128h+arg_8], 0
0x14000e0e3  jz      loc_14000E1C6
0x14000e0e9  mov     rdx, [rsp+128h+var_B8]
0x14000e0ee  test    rdx, rdx
0x14000e0f1  jnz     short loc_14000E153
0x14000e0f3  mov     ecx, [rsi+48h]
0x14000e0f6  lea     eax, [rdx+20h]
0x14000e0f9  shl     eax, cl
0x14000e0fb  mov     [rsp+128h+Size], rax
0x14000e103  mov     r8d, 62666455h; Tag
0x14000e109  mov     edx, eax; NumberOfBytes
0x14000e10b  mov     ecx, 610h; PoolType
0x14000e110  call    cs:__imp_ExAllocatePoolWithTag
0x14000e117  nop     dword ptr [rax+rax+00h]
0x14000e11c  mov     [rsp+128h+var_B8], rax
0x14000e121  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000e128  jnz     short loc_14000E146
0x14000e12a  test    rax, rax
0x14000e12d  jz      short loc_14000E146
0x14000e12f  mov     r8, [rsp+128h+Size]; Size
0x14000e137  xor     edx, edx; Val
0x14000e139  mov     rcx, rax; void *
0x14000e13c  call    memset
0x14000e141  mov     rax, [rsp+128h+var_B8]
0x14000e146  mov     [rsp+128h+var_98], rax
0x14000e14e  mov     rdx, [rsp+128h+var_B8]
0x14000e153  mov     ecx, [rsi+48h]
0x14000e156  mov     r8d, r15d
0x14000e159  shl     r8d, cl
  ... truncated ...
```
