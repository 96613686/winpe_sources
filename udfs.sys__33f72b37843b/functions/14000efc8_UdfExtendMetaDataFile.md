# UdfExtendMetaDataFile

- ea: `0x14000efc8`
- end: `0x14000f8c3`
- name: `UdfExtendMetaDataFile`
- size: `2299`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update`

## callers

- `0x1400103d8`

## callees

- `0x1400050d8`
- `0x140009014`
- `0x140009450`
- `0x14000b128`
- `0x14000b2b0`
- `0x14000b648`
- `0x14000e438`
- `0x14000e5d8`
- `0x14000eb04`
- `0x14000ed4c`
- `0x14000efc8`
- `0x1400104f0`
- `0x140010990`
- `0x140010dd0`
- `0x140017498`
- `0x1400193f0`
- `0x14001bc30`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x14000f717`
- `ntoskrnl!CcUnpinData` at `0x14000f717`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14000f693`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14000f6d9`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14000f693`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14000f6d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f858`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f876`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f88d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f8af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d64f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d670`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d687`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d6a9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f858`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f876`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f88d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f8af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d64f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d670`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d687`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d6a9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000f3fe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000f59d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000f751`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000f3fe`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000f59d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000f751`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f461`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f5e4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f77d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f7e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d5d5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f461`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f5e4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f77d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000f7e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001d5d5`
- `ntoskrnl!CcSetFileSizes` at `0x14000f515`
- `ntoskrnl!CcSetFileSizes` at `0x14000f515`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f4c0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f4c0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f52c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d5b0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f52c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001d5b0`
- `ntoskrnl!CcPreparePinWrite` at `0x14000f634`
- `ntoskrnl!CcPreparePinWrite` at `0x14000f634`

## pseudocode

```c
bool __fastcall UdfExtendMetaDataFile(_QWORD *a1, __int64 a2)
{
  __int64 v5; // rcx
  unsigned int v6; // r12d
  unsigned int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // r15d
  _DWORD *v10; // rax
  unsigned int v11; // r9d
  __int64 v12; // rcx
  unsigned int *v13; // r14
  __int64 v14; // r11
  unsigned int v15; // r9d
  _DWORD *v16; // r8
  int v17; // r10d
  unsigned int v18; // edx
  unsigned int v19; // r9d
  unsigned int v20; // ecx
  int v21; // esi
  unsigned int j; // edx
  __int64 v23; // rdx
  unsigned __int64 v24; // r14
  char v25; // r12
  unsigned int v26; // eax
  int v27; // edx
  __int64 v28; // rcx
  char v29; // si
  __int64 v30; // rdx
  unsigned __int64 v31; // r12
  unsigned __int64 v32; // r12
  __int64 v33; // rdx
  int v34; // ecx
  int v35; // esi
  char v36; // r14
  unsigned int k; // esi
  __int64 v38; // rcx
  char v39; // [rsp+78h] [rbp-C8h]
  char v40; // [rsp+7Bh] [rbp-C5h]
  char v41; // [rsp+7Ch] [rbp-C4h] BYREF
  BOOLEAN v42; // [rsp+7Dh] [rbp-C3h]
  unsigned int v43; // [rsp+80h] [rbp-C0h]
  int v44; // [rsp+84h] [rbp-BCh] BYREF
  __int64 Lbn; // [rsp+88h] [rbp-B8h] BYREF
  unsigned int v46; // [rsp+90h] [rbp-B0h]
  __int64 v47; // [rsp+98h] [rbp-A8h] BYREF
  unsigned int i; // [rsp+A0h] [rbp-A0h]
  int v49; // [rsp+A4h] [rbp-9Ch] BYREF
  PVOID Buffer[2]; // [rsp+A8h] [rbp-98h] BYREF
  unsigned int v51; // [rsp+B8h] [rbp-88h]
  unsigned int v52; // [rsp+BCh] [rbp-84h]
  int v53; // [rsp+C0h] [rbp-80h]
  _DWORD *v54; // [rsp+C8h] [rbp-78h]
  union _LARGE_INTEGER FileOffset; // [rsp+D0h] [rbp-70h] BYREF
  PVOID Bcb[2]; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v57; // [rsp+E8h] [rbp-58h]
  __int128 v58; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+100h] [rbp-40h]

  Buffer[1] = a1;
  Bcb[1] = (PVOID)a2;
  v41 = 0;
  Buffer[0] = 0;
  Bcb[0] = 0;
  v44 = 0;
  v49 = 0;
  LODWORD(Lbn) = 0;
  FileOffset.QuadPart = 0;
  if ( (*(_DWORD *)(a2 + 48) & 0x20000000) != 0 )
    return (int)UdfPowReserveMetaDataBlocks((_DWORD)a1, a2, 0, 1, 0) >= 0;
  v39 = 0;
  UdfAcquireResource(a1, a2 + 752, 0, 0);
  UdfUnpinCurrentBitmapPage(v5, a2, 1);
  UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 336) + 136LL) + 80LL) + 8LL, 0, 0);
  UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(a2 + 336) + 16LL), 0, 0);
  UdfAcquireResource(a1, a2 + 552, 0, 0);
  v58 = 0;
  v59 = 0;
  v40 = 1;
  v57 = *(_QWORD *)(a2 + 16) + 56LL * *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 84LL);
  v6 = *(_DWORD *)(v57 + 128);
  v52 = v6;
  v7 = 0x100000u >> *(_DWORD *)(a2 + 72);
  v46 = v7;
  if ( v7 >= v6 )
  {
    v8 = v6 + v7 - 1 - (v6 + v7 - 1) % v6;
    v46 = v8;
  }
  else
  {
    v8 = v6;
    v46 = v6;
  }
  v9 = 0;
  v43 = 0;
  v10 = (_DWORD *)(a2 + 664);
LABEL_7:
  if ( v9 < 2 )
  {
    if ( v9 )
    {
      if ( (*(_DWORD *)(a2 + 48) & 0x8000000) == 0 )
      {
        v10 = (_DWORD *)(a2 + 664);
        goto LABEL_34;
      }
      v10 = (_DWORD *)(a2 + 664);
      v11 = *(_DWORD *)(a2 + 664) >> 1;
    }
    else
    {
      v11 = 0;
    }
    v54 = v10;
    v12 = (unsigned int)(*v10 - 1);
    for ( i = *v10 - 1; ; v12 = i )
    {
      if ( v11 > (unsigned int)v12 )
        goto LABEL_54;
      v47 = 3LL * v9;
      v13 = (unsigned int *)&v58 + 3 * v9 + 1;
      UdfFindFreeBitmapBlocksInRange((_DWORD)a1, 0, v8, v11, v12, (__int64)&v58 + 12 * v9, (__int64)v13);
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_DDD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          85,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          *v13,
          *((_DWORD *)&v58 + v47),
          0);
      }
      v12 = *v13;
      if ( !(_DWORD)v12 || (unsigned int)v12 < v6 )
      {
LABEL_54:
        v25 = 0;
        goto LABEL_55;
      }
      v14 = v57;
      v15 = *(_DWORD *)(v57 + 132);
      v16 = (_DWORD *)&v58 + v47;
      v17 = *v16;
      v18 = *v16 % v15;
      v51 = v18;
      if ( v18 && (v18 = v15 - v18, v51 = v18, v18 >= (unsigned int)v12) )
      {
        v11 = v17 + v12;
      }
      else
      {
        *v16 = v17 + v18;
        *v13 -= v18;
        v19 = *(_DWORD *)(v14 + 128);
        v20 = *v13 - *v13 % v19;
        *v13 = v20;
        if ( v20 >= v6 )
        {
          if ( v9 == 1 )
          {
            while ( v20 - v8 >= v19 )
            {
              *v16 += v19;
              *v13 -= v19;
              v20 = *v13;
            }
          }
          else if ( v20 > v8 )
          {
            *v13 = v8;
          }
          UdfChangeOrVerifyBitmapRun((_DWORD)a1, 0, *v16, *v13, 0, 0, (__int64)&v44);
          *((_BYTE *)&v58 + 4 * v47 + 8) = 1;
          if ( !v9 )
          {
            v6 = *v13;
            v8 = v6;
            v46 = *v13;
            v52 = v6;
          }
          v10 = v54;
LABEL_34:
          v43 = ++v9;
          goto LABEL_7;
        }
        v11 = v20 + *v16;
      }
    }
  }
  v21 = 0;
  v53 = 0;
  for ( j = 0; ; ++j )
  {
    v43 = j;
    if ( j >= 2 )
      break;
    v21 += *((_DWORD *)&v58 + 3 * j + 1);
    v53 = v21;
  }
  v23 = *(_QWORD *)(a2 + 336);
  v24 = *(_QWORD *)(v23 + 32) + ((unsigned __int64)DWORD1(v58) >> 3);
  v47 = v24;
  UdfGetBlocksNeeded(a2, v23, (unsigned int)&v47, (unsigned int)&Lbn, (__int64)&v49, 0, 0, (__int64)&v41);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
  v25 = 1;
  v26 = UdfAvailableFreeBlocks(a2, 0);
  v27 = v49;
  v12 = (unsigned int)(v49 + v21);
  if ( (unsigned int)v12 > v26 )
  {
LABEL_55:
    v36 = 0;
  }
  else
  {
    *(_DWORD *)(a2 + 672) += v49;
    *(_DWORD *)(*(_QWORD *)(a2 + 336) + 328LL) += v27;
    *(_DWORD *)(a2 + 668) -= v21;
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
    v40 = 0;
    v29 = v41;
    if ( v41 )
      UdfDeEmbedFileData(
        v28,
        *(struct _CC_FILE_SIZES **)(a2 + 336),
        *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 336) + 504LL),
        1);
    if ( (_DWORD)Lbn )
      UdfAllocateAtFileTail(a1, *(_QWORD *)(a2 + 336), (unsigned int)Lbn, &v47);
    ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(a2 + 336) + 48LL));
    *(_QWORD *)(*(_QWORD *)(a2 + 336) + 32LL) = v24;
    *(_QWORD *)(*(_QWORD *)(a2 + 336) + 40LL) = v24;
    *(_QWORD *)(*(_QWORD *)(a2 + 336) + 24LL) = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(a2 + 68) - 1)
                                              & ((unsigned int)(*(_DWORD *)(a2 + 68) - 1) + v24);
    CcSetFileSizes(*(PFILE_OBJECT *)(*(_QWORD *)(a2 + 336) + 504LL), (PCC_FILE_SIZES)(*(_QWORD *)(a2 + 336) + 24LL));
    ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(a2 + 336) + 48LL));
    v30 = *(_QWORD *)(a2 + 336);
    if ( (*(_DWORD *)(v30 + 212) & 2) == 0 )
      UdfUpdateAdsFromScb(a1, v30, 0, *(_QWORD *)(v30 + 24) >> *(_DWORD *)(a2 + 72));
    v31 = *(_QWORD *)(*(_QWORD *)(a2 + 320) + 24LL);
    LODWORD(Lbn) = *(_DWORD *)(a2 + 72);
    if ( UdfUpdateMetadataAllocation((__int64)a1, a2, &v58, 0) )
    {
      v32 = v31 >> Lbn;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
      *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
      v33 = *(_QWORD *)(*(_QWORD *)(a2 + 320) + 32LL) >> *(_DWORD *)(a2 + 72);
      *(_DWORD *)(a2 + 864) = v33;
      *(_DWORD *)(a2 + 860) = v33;
      *(_QWORD *)(a2 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
      FileOffset.QuadPart = 0;
      CcPreparePinWrite(*(PFILE_OBJECT *)(*(_QWORD *)(a2 + 336) + 504LL), &FileOffset, 0x18u, 0, 1u, Bcb, Buffer);
      *((_DWORD *)Buffer[0] + 4) = 8 * (v24 - 24);
      *((_DWORD *)Buffer[0] + 5) = v24 - 24;
      if ( v29 )
      {
        Lbn = 0;
        v42 = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(*(_QWORD *)(a2 + 336) + 264LL), 0, &Lbn, 0, 0, 0, 0);
        if ( !v42 || (v34 = Lbn, Lbn == -1) )
        {
          v42 = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(*(_QWORD *)(a2 + 336) + 232LL), 0, &Lbn, 0, 0, 0, 0);
          v34 = Lbn;
        }
        *((_DWORD *)Buffer[0] + 3) = v34 - *(_DWORD *)(a1[2] + 656LL);
      }
      UdfUpdateChecksumAndCrc(Buffer[0], 24);
      CcUnpinData(Bcb[0]);
      v35 = DWORD1(v58);
      UdfChangeOrVerifyBitmapRun((_DWORD)a1, 1, v32, DWORD1(v58), 1, 0, (__int64)&v44);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
      *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
      *(_DWORD *)(a2 + 868) += v35;
      *(_QWORD *)(a2 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
      v36 = 1;
      v39 = 1;
      v42 = 1;
    }
    else
    {
      v36 = 0;
    }
    v25 = 0;
  }
  if ( v25 )
  {
    *(_QWORD *)(a2 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  }
  if ( v40 )
  {
    for ( k = 0; k < 2; ++k )
    {
      if ( *((_BYTE *)&v58 + 12 * k + 8) )
        UdfChangeOrVerifyBitmapRun(
          (_DWORD)a1,
          0,
          *((_DWORD *)&v58 + 3 * k),
          *((_DWORD *)&v58 + 3 * k + 1),
          1,
          0,
          (__int64)&v44);
    }
    v36 = v39;
  }
  UdfUnpinCurrentBitmapPage(v12, a2, 0);
  ExReleaseResourceLite((PERESOURCE)(a2 + 552));
  UdfUnpinCurrentBitmapPage(v38, a2, 1);
  ExReleaseResourceLite((PERESOURCE)(a2 + 752));
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a2 + 336) + 16LL));
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 336) + 136LL) + 80LL) + 8LL));
  return v36;
}

```

## disassembly

```asm
0x14000efc8  mov     r11, rsp
0x14000efcb  mov     [r11+18h], rbx
0x14000efcf  mov     [r11+20h], rsi
0x14000efd3  push    rdi
0x14000efd4  push    r12
0x14000efd6  push    r13
0x14000efd8  push    r14
0x14000efda  push    r15
0x14000efdc  sub     rsp, 0E0h
0x14000efe3  mov     rax, cs:__security_cookie
0x14000efea  xor     rax, rsp
0x14000efed  mov     [rsp+108h+var_38], rax
0x14000eff5  mov     rbx, rdx
0x14000eff8  mov     r13, rcx
0x14000effb  mov     [rsp+108h+var_90], rcx
0x14000f000  mov     [rsp+108h+var_60], rdx
0x14000f008  xor     r14d, r14d
0x14000f00b  mov     [rsp+108h+var_C4], r14b
0x14000f010  mov     [rsp+108h+var_98], r14
0x14000f015  mov     [r11-68h], r14
0x14000f019  mov     [rsp+108h+var_BC], r14d
0x14000f01e  mov     [rsp+108h+var_9C], r14d
0x14000f023  mov     dword ptr [rsp+108h+Lbn], r14d
0x14000f028  mov     [r11-70h], r14
0x14000f02c  xor     r8d, r8d
0x14000f02f  test    dword ptr [rdx+30h], 20000000h
0x14000f036  jz      short loc_14000F07D
0x14000f038  mov     qword ptr [rsp+108h+Flags], r14
0x14000f03d  lea     edi, [r14+1]
0x14000f041  mov     r9d, edi
0x14000f044  call    UdfPowReserveMetaDataBlocks
0x14000f049  shr     eax, 1Fh
0x14000f04c  xor     al, dil
0x14000f04f  mov     rcx, [rsp+108h+var_38]
0x14000f057  xor     rcx, rsp; StackCookie
0x14000f05a  call    __security_check_cookie
0x14000f05f  lea     r11, [rsp+108h+var_28]
0x14000f067  mov     rbx, [r11+40h]
0x14000f06b  mov     rsi, [r11+48h]
0x14000f06f  mov     rsp, r11
0x14000f072  pop     r15
0x14000f074  pop     r14
0x14000f076  pop     r13
0x14000f078  pop     r12
0x14000f07a  pop     rdi
0x14000f07b  retn
0x14000f07d  mov     [rsp+108h+var_C8], r14b
0x14000f082  add     rdx, 2F0h
0x14000f089  xor     r9d, r9d
0x14000f08c  call    UdfAcquireResource
0x14000f091  mov     edi, 1
0x14000f096  mov     r8d, edi
0x14000f099  mov     rdx, rbx
0x14000f09c  call    UdfUnpinCurrentBitmapPage
0x14000f0a1  mov     rax, [rbx+150h]
0x14000f0a8  mov     rcx, [rax+88h]
0x14000f0af  mov     rdx, [rcx+50h]
0x14000f0b3  add     rdx, 8
0x14000f0b7  xor     r9d, r9d
0x14000f0ba  xor     r8d, r8d
0x14000f0bd  mov     rcx, r13
0x14000f0c0  call    UdfAcquireResource
0x14000f0c5  mov     rdx, [rbx+150h]
0x14000f0cc  xor     r9d, r9d
0x14000f0cf  xor     r8d, r8d
0x14000f0d2  mov     rdx, [rdx+10h]
0x14000f0d6  mov     rcx, r13
0x14000f0d9  call    UdfAcquireResource
0x14000f0de  lea     rdx, [rbx+228h]
0x14000f0e5  xor     r9d, r9d
0x14000f0e8  xor     r8d, r8d
0x14000f0eb  mov     rcx, r13
0x14000f0ee  call    UdfAcquireResource
0x14000f0f3  xorps   xmm0, xmm0
0x14000f0f6  xor     eax, eax
0x14000f0f8  movups  [rsp+108h+var_50], xmm0
0x14000f100  mov     [rsp+108h+var_40], rax
0x14000f108  mov     [rsp+108h+var_C7], r14b
0x14000f10d  mov     [rsp+108h+var_C5], dil
0x14000f112  mov     [rsp+108h+var_C6], al
0x14000f116  mov     rcx, [rbx+10h]
0x14000f11a  movzx   eax, word ptr [rcx+54h]
0x14000f11e  imul    r11, rax, 38h ; '8'
0x14000f122  add     r11, rcx
0x14000f125  mov     [rsp+108h+var_58], r11
0x14000f12d  mov     r12d, [r11+80h]
0x14000f134  mov     [rsp+108h+var_84], r12d
0x14000f13c  mov     ecx, [rbx+48h]
0x14000f13f  mov     eax, 100000h
0x14000f144  shr     eax, cl
0x14000f146  mov     [rsp+108h+var_B0], eax
0x14000f14a  cmp     eax, r12d
0x14000f14d  jnb     short loc_14000F159
0x14000f14f  mov     esi, r12d
0x14000f152  mov     [rsp+108h+var_B0], r12d
0x14000f157  jmp     short loc_14000F16C
0x14000f159  lea     esi, [rax-1]
0x14000f15c  add     esi, r12d
0x14000f15f  xor     edx, edx
0x14000f161  mov     eax, esi
0x14000f163  div     r12d
0x14000f166  sub     esi, edx
0x14000f168  mov     [rsp+108h+var_B0], esi
0x14000f16c  mov     r15d, r14d
0x14000f16f  mov     [rsp+108h+var_C0], r14d
0x14000f174  lea     rax, [rbx+298h]
0x14000f17b  cmp     r15d, 2
0x14000f17f  jnb     loc_14000F369
0x14000f185  test    r15d, r15d
0x14000f188  jnz     short loc_14000F18F
0x14000f18a  mov     r9d, r14d
0x14000f18d  jmp     short loc_14000F1B1
0x14000f18f  test    dword ptr [rbx+30h], 8000000h
0x14000f196  jnz     short loc_14000F1A4
0x14000f198  lea     rax, [rbx+298h]
0x14000f19f  jmp     loc_14000F35C
0x14000f1a4  lea     rax, [rbx+298h]
0x14000f1ab  mov     r9d, [rax]
0x14000f1ae  shr     r9d, 1
0x14000f1b1  mov     [rsp+108h+var_78], rax
0x14000f1b9  mov     ecx, [rax]
0x14000f1bb  sub     ecx, edi
0x14000f1bd  mov     [rsp+108h+var_A0], ecx
0x14000f1c1  cmp     r9d, ecx
0x14000f1c4  ja      loc_14000F7C3
0x14000f1ca  mov     eax, r15d
0x14000f1cd  lea     rax, [rax+rax*2]
0x14000f1d1  mov     [rsp+108h+var_A8], rax
0x14000f1d6  lea     r14, [rsp+108h+var_50+4]
0x14000f1de  lea     r14, [r14+rax*4]
0x14000f1e2  lea     r10, [rsp+108h+var_50]
0x14000f1ea  lea     rax, [r10+rax*4]
0x14000f1ee  mov     [rsp+108h+Buffer], r14
0x14000f1f3  mov     [rsp+108h+Bcb], rax
0x14000f1f8  mov     [rsp+108h+Flags], ecx
0x14000f1fc  mov     r8d, esi
0x14000f1ff  xor     edx, edx
0x14000f201  mov     rcx, r13
0x14000f204  call    UdfFindFreeBitmapBlocksInRange
0x14000f209  lea     rax, WPP_GLOBAL_Control
0x14000f210  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f217  cmp     rcx, rax
0x14000f21a  jz      short loc_14000F254
0x14000f21c  mov     eax, [rcx+2Ch]
0x14000f21f  test    dil, al
0x14000f222  jz      short loc_14000F254
0x14000f224  mov     edx, 55h ; 'U'
0x14000f229  mov     dword ptr [rsp+108h+Bcb], 0
0x14000f231  mov     rax, [rsp+108h+var_A8]
0x14000f236  mov     eax, dword ptr [rsp+rax*4+108h+var_50]
0x14000f23d  mov     [rsp+108h+Flags], eax
0x14000f241  mov     r9d, [r14]
0x14000f244  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14000f24b  mov     rcx, [rcx+18h]
0x14000f24f  call    WPP_SF_DDD
0x14000f254  mov     ecx, [r14]
0x14000f257  test    ecx, ecx
0x14000f259  jz      loc_14000F7C3
0x14000f25f  cmp     ecx, r12d
0x14000f262  jb      loc_14000F7C3
0x14000f268  mov     r11, [rsp+108h+var_58]
0x14000f270  mov     r9d, [r11+84h]
0x14000f277  mov     rax, [rsp+108h+var_A8]
0x14000f27c  lea     r8, [rsp+108h+var_50]
0x14000f284  lea     r8, [r8+rax*4]
0x14000f288  mov     r10d, [r8]
0x14000f28b  xor     edx, edx
0x14000f28d  mov     eax, r10d
0x14000f290  div     r9d
0x14000f293  mov     [rsp+108h+var_88], edx
0x14000f29a  test    edx, edx
0x14000f29c  jz      short loc_14000F2BD
0x14000f29e  sub     r9d, edx
0x14000f2a1  mov     edx, r9d
0x14000f2a4  mov     [rsp+108h+var_88], edx
0x14000f2ab  cmp     r9d, ecx
0x14000f2ae  jb      short loc_14000F2BD
0x14000f2b0  lea     r9d, [r10+rcx]
0x14000f2b4  mov     ecx, [rsp+108h+var_A0]
0x14000f2b8  jmp     loc_14000F1C1
0x14000f2bd  lea     eax, [r10+rdx]
0x14000f2c1  mov     [r8], eax
0x14000f2c4  sub     [r14], edx
0x14000f2c7  mov     ecx, [r14]
0x14000f2ca  mov     r9d, [r11+80h]
0x14000f2d1  xor     edx, edx
0x14000f2d3  mov     eax, ecx
0x14000f2d5  div     r9d
0x14000f2d8  sub     ecx, edx
0x14000f2da  mov     [r14], ecx
0x14000f2dd  cmp     ecx, r12d
0x14000f2e0  jnb     short loc_14000F2EA
0x14000f2e2  mov     r9d, [r8]
0x14000f2e5  add     r9d, ecx
0x14000f2e8  jmp     short loc_14000F2B4
0x14000f2ea  cmp     r15d, edi
0x14000f2ed  jnz     short loc_14000F301
0x14000f2ef  sub     ecx, esi
0x14000f2f1  cmp     ecx, r9d
0x14000f2f4  jb      short loc_14000F308
0x14000f2f6  add     [r8], r9d
0x14000f2f9  sub     [r14], r9d
0x14000f2fc  mov     ecx, [r14]
0x14000f2ff  jmp     short loc_14000F2EF
0x14000f301  cmp     ecx, esi
0x14000f303  jbe     short loc_14000F308
0x14000f305  mov     [r14], esi
0x14000f308  lea     rax, [rsp+108h+var_BC]
0x14000f30d  mov     [rsp+108h+Buffer], rax
0x14000f312  mov     byte ptr [rsp+108h+Bcb], 0
0x14000f317  mov     byte ptr [rsp+108h+Flags], 0
0x14000f31c  mov     r9d, [r14]
0x14000f31f  mov     r8d, [r8]
0x14000f322  xor     edx, edx
0x14000f324  mov     rcx, r13
0x14000f327  call    UdfChangeOrVerifyBitmapRun
0x14000f32c  mov     rax, [rsp+108h+var_A8]
0x14000f331  mov     byte ptr [rsp+rax*4+108h+var_50+8], dil
0x14000f339  test    r15d, r15d
0x14000f33c  jnz     short loc_14000F351
0x14000f33e  mov     r12d, [r14]
0x14000f341  mov     esi, r12d
0x14000f344  mov     [rsp+108h+var_B0], r12d
0x14000f349  mov     [rsp+108h+var_84], r12d
0x14000f351  mov     rax, [rsp+108h+var_78]
0x14000f359  xor     r14d, r14d
0x14000f35c  add     r15d, edi
0x14000f35f  mov     [rsp+108h+var_C0], r15d
0x14000f364  jmp     loc_14000F17B
0x14000f369  mov     esi, r14d
0x14000f36c  mov     [rsp+108h+var_80], r14d
0x14000f374  mov     edx, r14d
0x14000f377  mov     [rsp+108h+var_C0], edx
0x14000f37b  cmp     edx, 2
0x14000f37e  jnb     short loc_14000F398
0x14000f380  mov     eax, edx
0x14000f382  lea     rcx, [rax+rax*2]
0x14000f386  add     esi, dword ptr [rsp+rcx*4+108h+var_50+4]
0x14000f38d  mov     [rsp+108h+var_80], esi
0x14000f394  add     edx, edi
0x14000f396  jmp     short loc_14000F377
0x14000f398  mov     rdx, [rbx+150h]
0x14000f39f  mov     rax, [rdx+20h]
0x14000f3a3  mov     [rsp+108h+var_A8], rax
0x14000f3a8  mov     r14d, dword ptr [rsp+108h+var_50+4]
0x14000f3b0  shr     r14, 3
0x14000f3b4  add     r14, rax
0x14000f3b7  mov     [rsp+108h+var_A8], r14
0x14000f3bc  lea     rax, [rsp+108h+var_C4]
0x14000f3c1  mov     [rsp+108h+var_D0], rax
0x14000f3c6  mov     [rsp+108h+Buffer], 0
0x14000f3cf  mov     [rsp+108h+Bcb], 0
0x14000f3d8  lea     rax, [rsp+108h+var_9C]
0x14000f3dd  mov     qword ptr [rsp+108h+Flags], rax
0x14000f3e2  lea     r9, [rsp+108h+Lbn]
0x14000f3e7  lea     r8, [rsp+108h+var_A8]
0x14000f3ec  mov     rcx, rbx
0x14000f3ef  call    UdfGetBlocksNeeded
0x14000f3f4  lea     r15, [rbx+630h]
0x14000f3fb  mov     rcx, r15; FastMutex
0x14000f3fe  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000f405  nop     dword ptr [rax+rax+00h]
0x14000f40a  mov     rax, gs:188h
0x14000f413  mov     [rbx+668h], rax
0x14000f41a  mov     r12b, dil
0x14000f41d  mov     [rsp+108h+var_C7], dil
0x14000f422  xor     edx, edx
0x14000f424  mov     rcx, rbx
0x14000f427  call    UdfAvailableFreeBlocks
0x14000f42c  mov     edx, [rsp+108h+var_9C]
0x14000f430  lea     ecx, [rdx+rsi]
0x14000f433  cmp     ecx, eax
0x14000f435  ja      loc_14000F7C8
0x14000f43b  add     [rbx+2A0h], edx
0x14000f441  mov     rax, [rbx+150h]
0x14000f448  add     [rax+148h], edx
0x14000f44e  sub     [rbx+29Ch], esi
0x14000f454  xor     r12d, r12d
0x14000f457  mov     [rbx+668h], r12
0x14000f45e  mov     rcx, r15; FastMutex
0x14000f461  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000f468  nop     dword ptr [rax+rax+00h]
0x14000f46d  mov     [rsp+108h+var_C7], r12b
0x14000f472  mov     [rsp+108h+var_C5], r12b
0x14000f477  mov     sil, [rsp+108h+var_C4]
0x14000f47c  test    sil, sil
0x14000f47f  jz      short loc_14000F497
0x14000f481  mov     rdx, [rbx+150h]
0x14000f488  mov     r9b, dil
0x14000f48b  mov     r8, [rdx+1F8h]
0x14000f492  call    UdfDeEmbedFileData
0x14000f497  mov     r8d, dword ptr [rsp+108h+Lbn]
0x14000f49c  test    r8d, r8d
0x14000f49f  jz      short loc_14000F4B5
0x14000f4a1  lea     r9, [rsp+108h+var_A8]
0x14000f4a6  mov     rdx, [rbx+150h]
0x14000f4ad  mov     rcx, r13
0x14000f4b0  call    UdfAllocateAtFileTail
0x14000f4b5  mov     rcx, [rbx+150h]
0x14000f4bc  mov     rcx, [rcx+30h]; FastMutex
  ... truncated ...
```
