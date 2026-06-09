# UdfCompleteScbOpen

- ea: `0x140050ee0`
- end: `0x140051d6c`
- name: `UdfCompleteScbOpen`
- size: `3724`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, ULONG, int, ULONG, char)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002e4fc`
- `0x140042c40`
- `0x140050224`
- `0x140050ce0`

## callees

- `0x140008790`
- `0x14000c490`
- `0x14000cad4`
- `0x140011b54`
- `0x1400316e8`
- `0x140050ee0`
- `0x140051d74`
- `0x140052864`
- `0x140056780`
- `0x140057330`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140051816`
- `ntoskrnl!ExRaiseStatus` at `0x140051c48`
- `ntoskrnl!ExRaiseStatus` at `0x140051816`
- `ntoskrnl!ExRaiseStatus` at `0x140051c48`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051ce6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a9d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140051ce6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a9d9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400514ee`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400514ee`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005119e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005159c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400516c4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051d06`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005a9fa`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005119e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005159c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400516c4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140051d06`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005a9fa`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005128c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140051607`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005172c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140051d4c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005aa4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005128c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140051607`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005172c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140051d4c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005aa4e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400512ca`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400512ca`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005132a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005132a`
- `ntoskrnl!FsRtlCheckOplock` at `0x140051be0`
- `ntoskrnl!FsRtlCheckOplock` at `0x140051c9e`
- `ntoskrnl!FsRtlCheckOplock` at `0x140051be0`
- `ntoskrnl!FsRtlCheckOplock` at `0x140051c9e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14005144c`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14005144c`
- `ntoskrnl!MmFlushImageSection` at `0x14005162b`
- `ntoskrnl!MmFlushImageSection` at `0x14005162b`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140051b2d`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x140051b2d`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140051b78`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x140051b78`
- `ntoskrnl!IoCheckShareAccess` at `0x140051af7`
- `ntoskrnl!IoCheckShareAccess` at `0x140051ba3`
- `ntoskrnl!IoCheckShareAccess` at `0x140051af7`
- `ntoskrnl!IoCheckShareAccess` at `0x140051ba3`
- `ntoskrnl!IoSetShareAccess` at `0x14005116b`
- `ntoskrnl!IoSetShareAccess` at `0x14005116b`
- `ntoskrnl!IoUpdateShareAccess` at `0x14005142e`
- `ntoskrnl!IoUpdateShareAccess` at `0x14005142e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005103a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14005103a`

## pseudocode

```c
int __fastcall UdfCompleteScbOpen(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        signed int a7,
        int a8,
        ULONG a9,
        char a10)
{
  int v12; // r14d
  __int64 v13; // rdi
  int v14; // r12d
  __int64 v15; // rbx
  int v16; // ecx
  int v19; // eax
  int v20; // ecx
  int v21; // r12d
  int result; // eax
  unsigned __int64 v23; // rdi
  __int64 v24; // rdx
  char v25; // r12
  char v26; // r15
  __int64 v27; // r8
  char v28; // r12
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  char v33; // r12
  char v34; // di
  int v35; // r8d
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // ecx
  int v39; // edx
  int v40; // r8d
  unsigned __int16 v41; // dx
  __int16 i; // dx
  int v43; // ecx
  ULONG v44; // [rsp+28h] [rbp-A0h]
  char v45; // [rsp+40h] [rbp-88h]
  char v46; // [rsp+41h] [rbp-87h]
  __int16 v47; // [rsp+44h] [rbp-84h]
  int v48; // [rsp+50h] [rbp-78h]
  char v49; // [rsp+54h] [rbp-74h]
  NTSTATUS v50; // [rsp+58h] [rbp-70h]
  int v51[2]; // [rsp+60h] [rbp-68h]
  __int64 v52; // [rsp+68h] [rbp-60h]
  unsigned __int64 v53; // [rsp+70h] [rbp-58h]
  char v55; // [rsp+D8h] [rbp+10h]
  __int64 *v57; // [rsp+E8h] [rbp+20h]
  __int64 v58; // [rsp+E8h] [rbp+20h]
  ULONG v59; // [rsp+100h] [rbp+38h]
  int v60; // [rsp+110h] [rbp+48h]

  v57 = a4;
  v12 = 0;
  *(_QWORD *)v51 = *(_QWORD *)(a2 + 48);
  v55 = 0;
  v47 = *(_WORD *)(a2 + 24);
  v13 = *(_QWORD *)(a2 + 8);
  v52 = v13;
  v14 = *(_DWORD *)(a2 + 16);
  v49 = *(_BYTE *)(a2 + 2) & 4;
  v15 = *a4;
  v16 = *(_DWORD *)(v13 + 16);
  if ( v16 == 0x2000000 )
  {
    if ( (*(_DWORD *)(a3 + 48) & 0x10) != 0 )
    {
      v43 = 278;
      if ( a7 == 2 )
        v43 = 0;
      v16 = ~(v43 | 0x50040) & 0x1F01FF;
    }
    else
    {
      v16 = 1769967;
    }
    *(_DWORD *)(v13 + 16) = v16;
  }
  if ( !a9 )
  {
    v19 = ~v16 & 0x10000;
    v20 = v16 | 0x10000;
LABEL_4:
    *(_DWORD *)(v13 + 16) = v20;
    v48 = v19;
    goto LABEL_5;
  }
  if ( a9 == 4 || (v48 = 0, a9 == 5) )
  {
    v19 = ~(_WORD)v16 & 0x112;
    v20 = v16 | 0x112;
    goto LABEL_4;
  }
LABEL_5:
  if ( a7 != 2 || (*(_BYTE *)(a2 + 26) & 1) != 0 )
  {
LABEL_6:
    if ( (*(_DWORD *)(v13 + 16) & 0x10027) == 0
      || (*(_WORD *)(a2 + 26) & 2) != 0
      || !MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*a4 + 424) + 8LL)) )
    {
      v21 = v14 & 0x1000;
      if ( a9 == 2 )
      {
        if ( (v47 & 0x100) != 0 )
        {
          *(_DWORD *)(v15 + 212) |= 0x100u;
          *(_DWORD *)(v15 + 220) |= 0x100u;
        }
      }
      else
      {
        if ( (*(_DWORD *)(v15 + 220) & 1) != 0 && *(_WORD *)v15 != 2355 && (*(_DWORD *)(v13 + 16) & 6) != 0 )
          return -1073741790;
        if ( v21 && (*(_DWORD *)(v15 + 220) & 1) != 0 )
          return -1073741535;
      }
      v50 = 0;
      if ( *(_DWORD *)(v15 + 200) )
      {
        if ( a7 == 4 )
        {
          *(_QWORD *)(a1 + 40) = v57;
          v58 = 1;
          if ( FsRtlCurrentBatchOplock((POPLOCK)(v15 + 88)) )
          {
            v58 = 9;
            if ( FsRtlCheckOplock((POPLOCK)(v15 + 88), *(PIRP *)(a1 + 8), (PVOID)a1, UdfOplockComplete, UdfPrePostIrp) == 259 )
              return 259;
          }
          result = IoCheckShareAccess(
                     *(_DWORD *)(v13 + 16),
                     *(unsigned __int16 *)(a2 + 26),
                     *(PFILE_OBJECT *)(a2 + 48),
                     (PSHARE_ACCESS)(v15 + 432),
                     0);
          v12 = result;
          if ( result < 0 )
            return result;
          v50 = FsRtlCheckOplock((POPLOCK)(v15 + 88), *(PIRP *)(a1 + 8), (PVOID)a1, UdfOplockComplete, UdfPrePostIrp);
          if ( v50 == 259 )
            return 259;
          *(_QWORD *)(a1 + 40) = 0;
        }
        else
        {
          result = IoCheckShareAccess(
                     *(_DWORD *)(v13 + 16),
                     *(unsigned __int16 *)(a2 + 26),
                     *(PFILE_OBJECT *)(a2 + 48),
                     (PSHARE_ACCESS)(v15 + 432),
                     0);
          v12 = result;
          if ( result < 0 )
            return result;
          v58 = 1;
        }
      }
      else
      {
        v58 = 1;
      }
      v45 = 0;
      v46 = 0;
      v60 = 0;
      v59 = 0;
      v23 = (unsigned __int64)ExAllocateFromPagedLookasideList(&UdfCcbLookasideList);
      v53 = v23;
      *(_DWORD *)v23 = 4196662;
      *(_DWORD *)(v23 + 4) = a8;
      *(_QWORD *)(v23 + 8) = v15;
      *(_QWORD *)(v23 + 16) = a5;
      *(_QWORD *)(v23 + 24) = a6;
      *(_QWORD *)(v23 + 32) = 0;
      *(_DWORD *)(v23 + 56) = 0;
      *(_WORD *)(v23 + 42) = 0;
      *(_WORD *)(v23 + 40) = 0;
      *(_QWORD *)(v23 + 48) = 0;
      if ( v21 )
        *(_DWORD *)(v23 + 4) = a8 | 0x20;
      v24 = *(_QWORD *)(a2 + 48);
      if ( a7 )
      {
        *(_QWORD *)(v24 + 24) = v15;
        *(_QWORD *)(v24 + 32) = v23 | a7;
        if ( (*(_DWORD *)(v15 + 212) & 0x100) != 0 )
          *(_DWORD *)(v24 + 80) |= 0x8000u;
        *(_QWORD *)(v24 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL);
      }
      else
      {
        *(_QWORD *)(v24 + 32) = 0;
        *(_QWORD *)(v24 + 24) = 0;
      }
      if ( (*(_DWORD *)(v52 + 16) & 2) != 0 || v21 )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
        *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
        ++*(_DWORD *)(v15 + 204);
        *(_DWORD *)(v15 + 208) = *(_DWORD *)(v15 + 208);
        ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 256LL);
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 260LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136)
                                                                                               + 8LL)
                                                                                   + 260LL);
        *(_QWORD *)(a3 + 1640) = 0;
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
        v34 = 1;
        v45 = 1;
        if ( !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v15 + 424) + 8LL), MmFlushForWrite) )
        {
          v12 = -1073741535;
          if ( !v21 )
            v12 = -1073741757;
          v26 = 1;
          v33 = 0;
          goto LABEL_120;
        }
        LODWORD(v23) = v53;
      }
      *(_QWORD *)(*(_QWORD *)(a2 + 48) + 40LL) = *(_QWORD *)(v15 + 424) + 8LL;
      if ( (a9 & 0xFFFFFFFA) == 0 && a9 != 1 )
      {
        v35 = v47 & 0x27;
        v32 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            19,
            WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
          v35 = v47 & 0x27;
        }
        if ( a5 && (*(_BYTE *)(a5 + 72) & 2) != 0 && (v35 & 2) == 0
          || (LOBYTE(v32) = (*(_BYTE *)(v15 + 220) & 4) != 0, ((unsigned __int8)v32 & ((v35 & 4) == 0)) != 0) )
        {
          v32 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
          {
            WPP_SF_(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              20,
              WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
          }
          v12 = -1073741790;
          v26 = 1;
          v33 = 0;
          goto LABEL_54;
        }
        if ( v49 )
        {
          v12 = -1073741811;
          v26 = 1;
          v33 = 0;
LABEL_54:
          v34 = v45;
LABEL_120:
          if ( v33 )
            ExReleaseResourceLite(*(PERESOURCE *)(v15 + 16));
          if ( v34 )
          {
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
            *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
            --*(_DWORD *)(v15 + 204);
            --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 256LL);
            *(_QWORD *)(a3 + 1640) = 0;
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
          }
          if ( v26 )
            UdfDeleteCcb(v32, v53);
          if ( v12 >= 0 )
            return v50;
          return v12;
        }
        v25 = v45;
        if ( !v45 )
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
          *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
          ++*(_DWORD *)(v15 + 204);
          *(_DWORD *)(v15 + 208) = *(_DWORD *)(v15 + 208);
          ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 256LL);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 260LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136)
                                                                                                 + 8LL)
                                                                                     + 260LL);
          *(_QWORD *)(a3 + 1640) = 0;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
          v25 = 1;
          v45 = 1;
          LODWORD(v23) = v53;
          v35 = v47 & 0x27;
        }
        v12 = UdfSupersedeOrOverwriteFile(a1, v51[0], v15, v23, a5, a9 == 0, *(_QWORD *)(a1 + 8) + 88LL, v35);
        if ( v12 >= 0 )
        {
          v39 = 8;
          v58 = 3;
          if ( (*(_DWORD *)(v15 + 212) & 0x10) == 0 )
            v39 = 3;
          v59 = v39;
          v40 = 1024;
          if ( (*(_DWORD *)(v15 + 212) & 0x10) == 0 )
            v40 = 28;
          v60 = v40;
          if ( a9 )
          {
            v60 = v40;
            v59 = v39;
          }
          else
          {
            v58 = 0;
          }
          goto LABEL_27;
        }
        v33 = 0;
LABEL_104:
        v26 = 1;
        goto LABEL_54;
      }
      if ( a9 == 2 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL) && *(_WORD *)v15 != 2355 )
        {
          if ( !ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v15 + 16), (*(_DWORD *)(a1 + 28) & 4) != 0) )
          {
            *(_DWORD *)(a1 + 24) = -1073741608;
            ExRaiseStatus(-1073741608);
          }
          v33 = 1;
          v46 = 1;
          LOBYTE(v44) = 0;
          v12 = UdfSetFileAllocationSize(a1, *(_QWORD *)v51, v15, 0, *(_QWORD *)(a1 + 8) + 88LL, v44, 0);
          if ( v12 < 0 )
            goto LABEL_104;
        }
        if ( (*(_DWORD *)(v15 + 212) & 0x10) != 0 )
        {
          v59 = 6;
          v60 = 512;
        }
        else
        {
          v59 = 1;
          v60 = (*(_WORD *)v15 == 2355) + 1;
        }
        v58 = 2;
      }
      v25 = v45;
LABEL_27:
      v26 = 0;
      if ( v48 )
        *(_DWORD *)(v52 + 16) &= ~v48;
      if ( *(_DWORD *)(v15 + 200) )
        IoUpdateShareAccess(*(PFILE_OBJECT *)(a2 + 48), (PSHARE_ACCESS)(v15 + 432));
      else
        IoSetShareAccess(
          *(_DWORD *)(v52 + 16),
          *(unsigned __int16 *)(a2 + 26),
          *(PFILE_OBJECT *)(a2 + 48),
          (PSHARE_ACCESS)(v15 + 432));
      if ( a7 == 4 )
      {
        v37 = *(_QWORD *)(a2 + 48);
        v38 = *(_DWORD *)(v37 + 80);
        if ( (*(_DWORD *)(a2 + 16) & 8) != 0 )
          *(_DWORD *)(v37 + 80) = v38 | 8;
        else
          *(_DWORD *)(v37 + 80) = v38 | 0x40;
      }
      else if ( a7 == 2 )
      {
        *(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) |= 8u;
      }
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
      v27 = a3;
      *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
      ++*(_DWORD *)(v15 + 200);
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 252LL);
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
      {
        WPP_SF_qdddd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          21,
          WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
          v15,
          *(_DWORD *)(a3 + 256),
          *(_DWORD *)(a3 + 260),
          *(_DWORD *)(v15 + 204),
          *(_DWORD *)(v15 + 208));
        v27 = a3;
      }
      *(_DWORD *)(v15 + 204) += v25 == 0;
      ++*(_DWORD *)(v15 + 208);
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 256LL) += v25 == 0;
      ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 8LL) + 260LL);
      v45 = 0;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
      {
        WPP_SF_DDDD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          22,
          WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
          *(unsigned int *)(v27 + 256),
          *(_DWORD *)(v27 + 260),
          *(_DWORD *)(v15 + 204),
          *(_DWORD *)(v15 + 208));
        v27 = a3;
      }
      if ( v55 )
      {
        *(_QWORD *)(v27 + 56) = *(_QWORD *)(a2 + 48);
        *(_DWORD *)(v27 + 48) |= 1u;
      }
      if ( a5 )
      {
        ++*(_DWORD *)(a5 + 64);
        if ( a6 )
          ++*(_DWORD *)(a6 + 64);
      }
      *(_QWORD *)(v27 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v27 + 1584));
      if ( v49 )
      {
        v41 = *(_WORD *)(*(_QWORD *)v51 + 88LL);
        *(_WORD *)(*(_QWORD *)v51 + 90LL) = v41;
        if ( v41 == 2 && **(_WORD **)(*(_QWORD *)v51 + 96LL) == 92 )
        {
LABEL_115:
          v28 = 2;
        }
        else
        {
          for ( i = (v41 >> 1) - 2; ; --i )
          {
            if ( i < 0 )
            {
              *(_WORD *)(*(_QWORD *)v51 + 88LL) = 0;
              goto LABEL_115;
            }
            if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)v51 + 96LL) + 2LL * i) == 92 )
              break;
          }
          v28 = 2;
          if ( i )
            *(_WORD *)(*(_QWORD *)v51 + 88LL) = 2 * i;
          else
            *(_WORD *)(*(_QWORD *)v51 + 88LL) = 2;
        }
        v12 = 0;
        v58 = 5LL - (a10 != 0);
      }
      else
      {
        v28 = 2;
      }
      CurrentThread = KeGetCurrentThread();
      v30 = *(_QWORD *)(v15 + 136);
      if ( CurrentThread != *(struct _KTHREAD **)(v30 + 64) )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v30 + 80) + 216LL));
        *(_QWORD *)(*(_QWORD *)(v15 + 136) + 64LL) = CurrentThread;
      }
      ++*(_DWORD *)(*(_QWORD *)(v15 + 136) + 72LL);
      if ( a7 == 4 )
      {
        if ( *(_DWORD *)(v15 + 216) || !FsRtlOplockIsFastIoPossible((POPLOCK)(v15 + 88)) )
        {
          v28 = 0;
        }
        else
        {
          v36 = *(_QWORD *)(v15 + 504);
          if ( !v36 || !*(_BYTE *)(v36 + 16) )
            v28 = 1;
        }
        *(_BYTE *)(v15 + 5) = v28;
      }
      else
      {
        *(_BYTE *)(v15 + 5) = 0;
      }
      --*(_DWORD *)(*(_QWORD *)(v15 + 136) + 72LL);
      v31 = *(_QWORD *)(v15 + 136);
      if ( !*(_DWORD *)(v31 + 72) )
      {
        *(_QWORD *)(v31 + 64) = 0;
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v15 + 136) + 80LL) + 216LL));
      }
      if ( v59 )
        UdfNotifyReportChange(a1, v23, a5, v51[0], v15, v60, v59);
      v32 = v58;
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL) = v58;
      v33 = v46;
      goto LABEL_54;
    }
    return -1073741757;
  }
  if ( *(_DWORD *)(a3 + 252) )
    return -1073741757;
  if ( (*(_DWORD *)(a1 + 28) & 4) == 0 )
  {
    *(_DWORD *)(a1 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  result = UdfFlushVolume(a1, a3, 0, 1, 1, 0);
  v12 = result;
  if ( !result )
  {
    v55 = 1;
    UdfFspClose(a3);
    if ( *(_DWORD *)(a3 + 260) > *(_DWORD *)(a3 + 268) )
      return -1073741757;
    a4 = v57;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x140050ee0  mov     [rsp+arg_18], r9
0x140050ee5  mov     [rsp+arg_10], r8
0x140050eea  mov     [rsp+Context], rcx
0x140050eef  push    rbx
0x140050ef0  push    rsi
0x140050ef1  push    rdi
0x140050ef2  push    r12
0x140050ef4  push    r13
0x140050ef6  push    r14
0x140050ef8  push    r15
0x140050efa  sub     rsp, 90h
0x140050f01  mov     r10, r8
0x140050f04  mov     rsi, rdx
0x140050f07  mov     r11, rcx
0x140050f0a  xor     r14d, r14d
0x140050f0d  mov     rax, [rdx+30h]
0x140050f11  mov     qword ptr [rsp+0C8h+var_68], rax
0x140050f16  mov     [rsp+0C8h+arg_8], r14b
0x140050f1e  movzx   eax, word ptr [rdx+18h]
0x140050f22  mov     [rsp+0C8h+var_84], ax
0x140050f27  mov     rdi, [rdx+8]
0x140050f2b  mov     [rsp+0C8h+var_60], rdi
0x140050f30  mov     r12d, [rdx+10h]
0x140050f34  movzx   eax, byte ptr [rdx+2]
0x140050f38  and     al, 4
0x140050f3a  mov     [rsp+0C8h+var_74], al
0x140050f3e  mov     rbx, [r9]
0x140050f41  mov     ecx, [rdi+10h]
0x140050f44  mov     r13d, [rsp+0C8h+arg_30]
0x140050f4c  cmp     ecx, 2000000h
0x140050f52  jz      loc_140051C08
0x140050f58  mov     r15d, [rsp+0C8h+arg_40]
0x140050f60  test    r15d, r15d
0x140050f63  jnz     loc_140051A2C
0x140050f69  mov     eax, ecx
0x140050f6b  not     eax
0x140050f6d  and     eax, 10000h
0x140050f72  bts     ecx, 10h
0x140050f76  mov     [rdi+10h], ecx
0x140050f79  mov     [rsp+0C8h+var_78], eax
0x140050f7d  cmp     r13d, 2
0x140050f81  jz      loc_140051A55
0x140050f87  test    dword ptr [rdi+10h], 10027h
0x140050f8e  setnz   cl
0x140050f91  mov     edx, 1
0x140050f96  movzx   eax, word ptr [rsi+1Ah]
0x140050f9a  bt      ax, dx
0x140050f9e  setnb   al
0x140050fa1  test    al, cl
0x140050fa3  jnz     loc_140051B1F
0x140050fa9  and     r12d, 1000h
0x140050fb0  movzx   eax, [rsp+0C8h+var_84]
0x140050fb5  cmp     r15d, 2
0x140050fb9  jz      short loc_140050FED
0x140050fbb  mov     ecx, [rbx+0DCh]
0x140050fc1  and     ecx, 1
0x140050fc4  jz      loc_140051A14
0x140050fca  mov     eax, 933h
0x140050fcf  cmp     [rbx], ax
0x140050fd2  jz      loc_140051A14
0x140050fd8  mov     eax, [rdi+10h]
0x140050fdb  test    al, 6
0x140050fdd  jz      loc_140051A14
0x140050fe3  mov     eax, 0C0000022h
0x140050fe8  jmp     loc_140051A00
0x140050fed  bt      eax, 8
0x140050ff1  jb      loc_140051C5F
0x140050ff7  mov     [rsp+0C8h+var_70], 0
0x140050fff  cmp     dword ptr [rbx+0C8h], 0
0x140051006  jnz     loc_140051ADA
0x14005100c  mov     [rsp+0C8h+arg_18], rdx
0x140051014  mov     [rsp+0C8h+var_88], 0
0x140051019  mov     [rsp+0C8h+var_87], 0
0x14005101e  xor     edi, edi
0x140051020  mov     [rsp+0C8h+arg_40], edi
0x140051027  mov     [rsp+0C8h+arg_30], edi
0x14005102e  mov     [rsp+0C8h+var_50], rbx
0x140051033  lea     rcx, UdfCcbLookasideList; Lookaside
0x14005103a  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140051041  nop     dword ptr [rax+rax+00h]
0x140051046  mov     rdi, rax
0x140051049  mov     [rsp+0C8h+var_58], rax
0x14005104e  mov     dword ptr [rax], 400936h
0x140051054  mov     ecx, [rsp+0C8h+arg_38]
0x14005105b  mov     [rax+4], ecx
0x14005105e  mov     [rax+8], rbx
0x140051062  mov     r8, [rsp+0C8h+arg_20]
0x14005106a  mov     [rax+10h], r8
0x14005106e  mov     rax, [rsp+0C8h+arg_28]
0x140051076  mov     [rdi+18h], rax
0x14005107a  xor     r8d, r8d
0x14005107d  mov     [rdi+20h], r8
0x140051081  mov     [rdi+38h], r8d
0x140051085  mov     [rdi+2Ah], r8w
0x14005108a  mov     eax, r8d
0x14005108d  mov     [rdi+28h], ax
0x140051091  mov     [rdi+30h], r8
0x140051095  mov     [rsp+0C8h+var_48], rdi
0x14005109d  mov     [rsp+0C8h+var_86], 1
0x1400510a2  test    r12d, r12d
0x1400510a5  jnz     loc_140051CCB
0x1400510ab  mov     rdx, [rsi+30h]
0x1400510af  test    r13d, r13d
0x1400510b2  jz      loc_140051B4B
0x1400510b8  mov     [rdx+18h], rbx
0x1400510bc  movsxd  rax, r13d
0x1400510bf  or      rax, rdi
0x1400510c2  mov     [rdx+20h], rax
0x1400510c6  test    dword ptr [rbx+0D4h], 100h
0x1400510d0  jnz     loc_140051CD6
0x1400510d6  mov     rcx, [rsp+0C8h+Context]
0x1400510de  mov     rax, [rcx+10h]
0x1400510e2  mov     rcx, [rax+8]
0x1400510e6  mov     [rdx+10h], rcx
0x1400510ea  mov     rax, [rsp+0C8h+var_60]
0x1400510ef  mov     eax, [rax+10h]
0x1400510f2  test    al, 2
0x1400510f4  jnz     loc_14005158D
0x1400510fa  test    r12d, r12d
0x1400510fd  jnz     loc_14005158D
0x140051103  mov     rcx, [rbx+1A8h]
0x14005110a  add     rcx, 8
0x14005110e  mov     rax, [rsi+30h]
0x140051112  mov     [rax+28h], rcx
0x140051116  test    r15d, 0FFFFFFFAh
0x14005111d  jz      loc_14005136D
0x140051123  cmp     r15d, 2
0x140051127  jz      loc_1400514B9
0x14005112d  movzx   r12d, [rsp+0C8h+var_88]
0x140051133  xor     r15b, r15b
0x140051136  mov     [rsp+0C8h+var_86], r15b
0x14005113b  mov     ecx, [rsp+0C8h+var_78]
0x14005113f  mov     rax, [rsp+0C8h+var_60]
0x140051144  test    ecx, ecx
0x140051146  jnz     loc_14005184F
0x14005114c  mov     r8, [rsi+30h]; FileObject
0x140051150  cmp     dword ptr [rbx+0C8h], 0
0x140051157  jnz     loc_140051424
0x14005115d  movzx   edx, word ptr [rsi+1Ah]; DesiredShareAccess
0x140051161  lea     r9, [rbx+1B0h]; ShareAccess
0x140051168  mov     ecx, [rax+10h]; DesiredAccess
0x14005116b  call    cs:__imp_IoSetShareAccess
0x140051172  nop     dword ptr [rax+rax+00h]
0x140051177  cmp     r13d, 4
0x14005117b  jz      loc_140051497
0x140051181  cmp     r13d, 2
0x140051185  jnz     short loc_14005118F
0x140051187  mov     rax, [rsi+30h]
0x14005118b  or      dword ptr [rax+50h], 8
0x14005118f  mov     rcx, [rsp+0C8h+arg_10]
0x140051197  add     rcx, 630h; FastMutex
0x14005119e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400511a5  nop     dword ptr [rax+rax+00h]
0x1400511aa  mov     rax, gs:188h
0x1400511b3  mov     r8, [rsp+0C8h+arg_10]
0x1400511bb  mov     [r8+668h], rax
0x1400511c2  inc     dword ptr [rbx+0C8h]
0x1400511c8  mov     rax, [rbx+88h]
0x1400511cf  mov     rcx, [rax+8]
0x1400511d3  inc     dword ptr [rcx+0FCh]
0x1400511d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400511e0  lea     rax, WPP_GLOBAL_Control
0x1400511e7  cmp     rcx, rax
0x1400511ea  jz      short loc_1400511F7
0x1400511ec  mov     eax, [rcx+2Ch]
0x1400511ef  test    al, 10h
0x1400511f1  jnz     loc_140051859
0x1400511f7  xor     eax, eax
0x1400511f9  test    r12b, r12b
0x1400511fc  setz    al
0x1400511ff  add     [rbx+0CCh], eax
0x140051205  inc     dword ptr [rbx+0D0h]
0x14005120b  xor     edx, edx
0x14005120d  test    r12b, r12b
0x140051210  setz    dl
0x140051213  mov     rax, [rbx+88h]
0x14005121a  mov     rcx, [rax+8]
0x14005121e  add     [rcx+100h], edx
0x140051224  mov     rax, [rbx+88h]
0x14005122b  mov     rcx, [rax+8]
0x14005122f  inc     dword ptr [rcx+104h]
0x140051235  xor     r12b, r12b
0x140051238  mov     [rsp+0C8h+var_88], r12b
0x14005123d  mov     rcx, cs:WPP_GLOBAL_Control
0x140051244  lea     rax, WPP_GLOBAL_Control
0x14005124b  cmp     rcx, rax
0x14005124e  jz      short loc_14005125B
0x140051250  mov     eax, [rcx+2Ch]
0x140051253  test    al, 10h
0x140051255  jnz     loc_1400518A8
0x14005125b  cmp     [rsp+0C8h+arg_8], r12b
0x140051263  jnz     loc_1400518F0
0x140051269  mov     rax, [rsp+0C8h+arg_20]
0x140051271  test    rax, rax
0x140051274  jnz     loc_14005147B
0x14005127a  mov     qword ptr [r8+668h], 0
0x140051285  lea     rcx, [r8+630h]; FastMutex
0x14005128c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140051293  nop     dword ptr [rax+rax+00h]
0x140051298  cmp     [rsp+0C8h+var_74], r12b
0x14005129d  jnz     loc_140051902
0x1400512a3  mov     r12d, 2
0x1400512a9  mov     rsi, gs:188h
0x1400512b2  mov     rcx, [rbx+88h]
0x1400512b9  cmp     rsi, [rcx+40h]
0x1400512bd  jz      short loc_1400512E1
0x1400512bf  mov     rcx, [rcx+50h]
0x1400512c3  add     rcx, 0D8h; FastMutex
0x1400512ca  call    cs:__imp_ExAcquireFastMutex
0x1400512d1  nop     dword ptr [rax+rax+00h]
0x1400512d6  mov     rax, [rbx+88h]
0x1400512dd  mov     [rax+40h], rsi
0x1400512e1  mov     rax, [rbx+88h]
0x1400512e8  inc     dword ptr [rax+48h]
0x1400512eb  cmp     r13d, 4
0x1400512ef  jz      loc_14005143F
0x1400512f5  mov     [rbx+5], r15b
0x1400512f9  mov     rax, [rbx+88h]
0x140051300  dec     dword ptr [rax+48h]
0x140051303  mov     rax, [rbx+88h]
0x14005130a  cmp     dword ptr [rax+48h], 0
0x14005130e  jnz     short loc_140051336
0x140051310  mov     qword ptr [rax+40h], 0
0x140051318  mov     rax, [rbx+88h]
0x14005131f  mov     rcx, [rax+50h]
0x140051323  add     rcx, 0D8h; FastMutex
0x14005132a  call    cs:__imp_ExReleaseFastMutex
0x140051331  nop     dword ptr [rax+rax+00h]
0x140051336  mov     eax, [rsp+0C8h+arg_30]
0x14005133d  test    eax, eax
0x14005133f  jnz     loc_1400519A3
0x140051345  mov     rax, [rsp+0C8h+Context]
0x14005134d  mov     rax, [rax+8]
0x140051351  mov     rcx, [rsp+0C8h+arg_18]
0x140051359  mov     [rax+38h], rcx
0x14005135d  movzx   r12d, [rsp+0C8h+var_87]
0x140051363  movzx   edi, [rsp+0C8h+var_88]
0x140051368  jmp     loc_1400519D9
0x14005136d  cmp     r15d, 1
0x140051371  jz      loc_140051123
0x140051377  movzx   r8d, [rsp+0C8h+var_84]
0x14005137d  and     r8d, 27h
0x140051381  mov     [rsp+0C8h+arg_30], r8d
0x140051389  lea     rdx, WPP_GLOBAL_Control
0x140051390  mov     rcx, cs:WPP_GLOBAL_Control
0x140051397  cmp     rcx, rdx
0x14005139a  jz      short loc_1400513C7
0x14005139c  mov     eax, [rcx+2Ch]
0x14005139f  test    al, 10h
0x1400513a1  jz      short loc_1400513C7
0x1400513a3  mov     edx, 13h
0x1400513a8  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
0x1400513af  mov     rcx, [rcx+18h]
0x1400513b3  call    WPP_SF_
0x1400513b8  lea     rdx, WPP_GLOBAL_Control
0x1400513bf  mov     r8d, [rsp+0C8h+arg_30]
0x1400513c7  mov     rax, [rsp+0C8h+arg_20]
0x1400513cf  test    rax, rax
0x1400513d2  jz      short loc_1400513EA
0x1400513d4  test    byte ptr [rax+48h], 2
0x1400513d8  setnz   cl
0x1400513db  test    r8b, 2
0x1400513df  setz    al
0x1400513e2  test    al, cl
0x1400513e4  jnz     loc_140051668
0x1400513ea  test    byte ptr [rbx+0DCh], 4
0x1400513f1  setnz   cl
0x1400513f4  test    r8b, 4
0x1400513f8  setz    al
0x1400513fb  test    al, cl
0x1400513fd  jnz     loc_140051668
0x140051403  cmp     [rsp+0C8h+var_74], 0
0x140051408  jz      loc_1400516A6
0x14005140e  mov     r14d, 0C000000Dh
0x140051414  mov     [rsp+0C8h+var_80], r14d
0x140051419  mov     r15b, 1
0x14005141c  xor     r12b, r12b
0x14005141f  jmp     loc_140051363
0x140051424  lea     rdx, [rbx+1B0h]; ShareAccess
0x14005142b  mov     rcx, r8; FileObject
0x14005142e  call    cs:__imp_IoUpdateShareAccess
0x140051435  nop     dword ptr [rax+rax+00h]
0x14005143a  jmp     loc_140051177
0x14005143f  cmp     dword ptr [rbx+0D8h], 0
0x140051446  jnz     short loc_1400514B4
0x140051448  lea     rcx, [rbx+58h]; Oplock
0x14005144c  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140051453  nop     dword ptr [rax+rax+00h]
0x140051458  test    al, al
0x14005145a  jz      short loc_1400514B4
0x14005145c  mov     rax, [rbx+1F8h]
0x140051463  test    rax, rax
0x140051466  jnz     loc_140051994
0x14005146c  mov     r12d, 1
0x140051472  mov     [rbx+5], r12b
0x140051476  jmp     loc_1400512F9
0x14005147b  inc     dword ptr [rax+40h]
0x14005147e  mov     rax, [rsp+0C8h+arg_28]
0x140051486  test    rax, rax
0x140051489  jz      loc_14005127A
  ... truncated ...
```
