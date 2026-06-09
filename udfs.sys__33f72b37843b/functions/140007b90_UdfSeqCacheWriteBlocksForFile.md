# UdfSeqCacheWriteBlocksForFile

- ea: `0x140007b90`
- end: `0x14000858c`
- name: `UdfSeqCacheWriteBlocksForFile`
- size: `2556`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x1400010f0`
- `0x140017fa8`
- `0x14003aa44`
- `0x14003b79c`

## callees

- `0x1400062c0`
- `0x140007b90`
- `0x140009014`
- `0x14000a6c4`
- `0x14000ed4c`
- `0x140018f2c`
- `0x14001b37c`
- `0x14001bd80`
- `0x14001c080`
- `0x14004ce50`
- `0x140056cb8`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400083d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400083ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400084ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000851f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008537`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ce9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ceb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400083d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400083ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400084ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000851f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140008537`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ce9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ceb6`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400080c1`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400080c1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140007cf5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400081d8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008554`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ced8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140007cf5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400081d8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008554`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ced8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140007d7e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008264`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008579`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001cf0d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140007d7e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008264`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008579`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001cf0d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000843a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000843a`
- `ntoskrnl!KeSetEvent` at `0x1400082e0`
- `ntoskrnl!KeSetEvent` at `0x1400082e0`
- `ntoskrnl!KeInitializeEvent` at `0x140008358`
- `ntoskrnl!KeInitializeEvent` at `0x140008358`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140007de3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140007de3`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheWriteBlocksForFile(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 *a5,
        __int64 a6)
{
  unsigned int v6; // r13d
  __int64 v8; // rdi
  __int64 v9; // r12
  __int64 v10; // r14
  __int64 v11; // rbx
  unsigned int v12; // r11d
  __int64 v13; // rax
  _DWORD *v14; // rcx
  unsigned int v15; // r9d
  unsigned int v16; // ecx
  int v17; // eax
  unsigned int v18; // edi
  int v19; // eax
  int v21; // r10d
  char v22; // r15
  char v23; // si
  int v24; // ecx
  char v25; // di
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // r15d
  __int64 v29; // r9
  __int64 v30; // r12
  unsigned int v31; // r8d
  unsigned int v32; // edi
  int v33; // ecx
  unsigned int v34; // eax
  unsigned int v35; // r8d
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // ecx
  size_t v39; // r8
  void *v40; // r9
  int v41; // ecx
  int v42; // r8d
  __int64 v43; // rdx
  struct _KEVENT *v44; // rcx
  int v45; // ecx
  __int64 v46; // rdi
  __int16 v47; // ax
  __int64 v48; // rcx
  unsigned int v49; // r15d
  __int64 v50; // rdx
  int v51; // [rsp+28h] [rbp-160h]
  char v52; // [rsp+40h] [rbp-148h]
  int v53; // [rsp+44h] [rbp-144h]
  char v54; // [rsp+48h] [rbp-140h]
  char v55; // [rsp+49h] [rbp-13Fh]
  unsigned int v56; // [rsp+4Ch] [rbp-13Ch]
  char v57; // [rsp+50h] [rbp-138h] BYREF
  char v58; // [rsp+51h] [rbp-137h]
  unsigned int v59; // [rsp+54h] [rbp-134h]
  unsigned int v60; // [rsp+58h] [rbp-130h] BYREF
  unsigned int v61; // [rsp+5Ch] [rbp-12Ch] BYREF
  unsigned int v62; // [rsp+60h] [rbp-128h]
  unsigned int v63; // [rsp+64h] [rbp-124h] BYREF
  int v64; // [rsp+68h] [rbp-120h]
  unsigned int v65; // [rsp+6Ch] [rbp-11Ch]
  unsigned int v66; // [rsp+70h] [rbp-118h]
  __int64 v67; // [rsp+78h] [rbp-110h]
  __int64 v68; // [rsp+80h] [rbp-108h]
  struct _KEVENT *v69; // [rsp+88h] [rbp-100h]
  __int64 v70; // [rsp+90h] [rbp-F8h]
  _OWORD v71[5]; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v72; // [rsp+F0h] [rbp-98h]
  int v73; // [rsp+FCh] [rbp-8Ch]
  char v79; // [rsp+1C0h] [rbp+38h]

  v6 = a4;
  v8 = a2;
  v9 = a1;
  v10 = *(_QWORD *)(a1 + 16);
  v70 = v10;
  v11 = *(_QWORD *)(v10 + 104);
  memset(v71, 0, 0x40u);
  v12 = 0;
  v56 = 0;
  v60 = 0;
  v62 = 0;
  v79 = 0;
  v57 = 0;
  if ( (*(_DWORD *)(v10 + 48) & 0x20000000) == 0 )
  {
    v69 = (struct _KEVENT *)(v11 + 592);
    goto LABEL_8;
  }
  v11 = *(_QWORD *)(v10 + 104);
  v69 = (struct _KEVENT *)(v11 + 592);
  if ( v8 == *(_QWORD *)(v10 + 320) || v8 == *(_QWORD *)(v10 + 272) )
  {
    v11 = *(_QWORD *)(v10 + 112);
    v79 = 1;
    goto LABEL_8;
  }
  v67 = v11;
  if ( v8 == *(_QWORD *)(v10 + 328) )
  {
    v11 = *(_QWORD *)(v10 + 120);
    v79 = 1;
LABEL_8:
    v67 = v11;
  }
  v13 = *(_QWORD *)(v9 + 64);
  if ( v13 && *(_QWORD *)(v13 + 8) == 3 )
  {
    v54 = 1;
    v14 = (_DWORD *)(v9 + 28);
  }
  else
  {
    v54 = 0;
    v14 = (_DWORD *)(v9 + 28);
    v55 = 0;
    if ( (*(_DWORD *)(v9 + 28) & 4) != 0 )
      goto LABEL_14;
  }
  v55 = 1;
LABEL_14:
  *v14 |= 4u;
  if ( *(_QWORD *)(v10 + 344) != v8 && v8 != -1 )
  {
    v12 = UdfSeqCacheUnReserveFileRegion(v9, v8, a3, v6, 0);
    v56 = v12;
    v60 = v12;
    if ( v12 < v6 )
    {
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 1584));
      *(_QWORD *)(v10 + 1640) = KeGetCurrentThread();
      if ( *(_QWORD *)(v10 + 352) == v8 )
        v15 = *(_DWORD *)(v10 + 668) - *(_DWORD *)(v10 + 672);
      else
        v15 = UdfAvailableFreeBlocks(v10, 0);
      v16 = v6 - v56;
      v17 = *(_DWORD *)(v10 + 672);
      if ( v15 < v6 - v56 )
      {
        v18 = v56;
        v19 = v17 - v56;
      }
      else
      {
        v56 = v6;
        v60 = v6;
        v18 = v6;
        v19 = v16 + v17;
      }
      *(_DWORD *)(v10 + 672) = v19;
      *(_QWORD *)(v10 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 1584));
      if ( v18 < v6 )
        return 3221225599LL;
      v8 = a2;
      v12 = v56;
    }
  }
  v21 = 0;
  v53 = 0;
  v66 = 0;
  v22 = 0;
  v52 = 0;
  v23 = 0;
  if ( (*(_DWORD *)(v10 + 2128) & 4) == 0 && v8 != -1 )
  {
    if ( IoGetTopLevelIrp() != (PIRP)2 )
      UdfMarkVolumeOpenAndQueueCloseDpc(v9);
    v12 = v56;
    v21 = 0;
  }
  while ( v6 )
  {
    if ( !v23 )
    {
      UdfAcquireResource(v9, v11 + 344, 0, 0);
      v23 = 1;
      v21 = v53;
      v12 = v56;
    }
    v24 = *(_DWORD *)(*(_QWORD *)(v10 + 104) + 4LL) & 0x10;
    if ( (*(_DWORD *)(v10 + 48) & 0x20000000) != 0 )
    {
      if ( v24 )
      {
LABEL_47:
        v32 = -1073741248;
        goto LABEL_111;
      }
    }
    else if ( v24 )
    {
      goto LABEL_47;
    }
    if ( !v22 )
    {
      UdfAcquireResource(v9, v11 + 448, 0, 0);
      v22 = 1;
      v52 = 1;
      v21 = v53;
      v12 = v56;
    }
    v59 = 0;
    v25 = 0;
    v58 = 0;
    v26 = v11 + 40LL * *(unsigned int *)(v11 + 16);
    v27 = *(unsigned int *)(v26 + 28);
    if ( !(_DWORD)v27 || *(_WORD *)(v26 + 24) )
    {
LABEL_77:
      v43 = v11 + 40LL * *(unsigned int *)(v11 + 16);
      if ( !*(_DWORD *)(v43 + 28) || *(_WORD *)(v43 + 24) )
      {
        if ( v25 )
        {
          *(_WORD *)(v43 + 24) = 1;
          if ( _InterlockedIncrement((volatile signed __int32 *)(v11 + 708)) == 1 )
          {
            v44 = v69;
            if ( !v69 )
              v44 = (struct _KEVENT *)(v11 + 592);
            KeSetEvent(v44, 1, 0);
          }
        }
        if ( !v6 )
          break;
        v45 = ((unsigned __int8)*(_DWORD *)(v11 + 16) + 1) & 7;
        v46 = v11 + 40LL * (((unsigned __int8)*(_DWORD *)(v11 + 16) + 1) & 7);
        v47 = *(_WORD *)(v46 + 24);
        if ( (v47 & 0xB) != 0 )
        {
          if ( !v54 && (!v55 || a4 != v6) )
          {
            memset(v71, 0, 0x40u);
            KeInitializeEvent((PRKEVENT)&v71[1], SynchronizationEvent, 0);
            *(_QWORD *)&v71[3] = KeGetCurrentThread();
            DWORD2(v71[2]) = *(_DWORD *)(v46 + 36);
            v48 = *(_QWORD *)(v11 + 624);
            if ( *(_QWORD *)(v48 + 8) != v11 + 624 )
              __fastfail(3u);
            *(_QWORD *)&v71[0] = *(_QWORD *)(v11 + 624);
            *((_QWORD *)&v71[0] + 1) = v11 + 624;
            *(_QWORD *)(v48 + 8) = v71;
            *(_QWORD *)(v11 + 624) = v71;
          }
          ExReleaseResourceLite((PERESOURCE)(v11 + 448));
          ExReleaseResourceLite((PERESOURCE)(v11 + 344));
          v23 = 0;
          v22 = 0;
          v52 = 0;
          if ( v54 || v55 && a4 == v6 )
          {
            v49 = v56;
            if ( v56 )
            {
              if ( v6 < v56 )
                v49 = v6;
              LOBYTE(v51) = 1;
              UdfSeqCacheReserveFileRegion(v9, a2, a3 + v53, v49, &v60, v51, 1);
            }
            v50 = 3221225556LL;
            if ( !v54 )
              v50 = 3221225688LL;
            UdfRaiseStatusEx(v9, v50, 0);
          }
          KeWaitForSingleObject(&v71[1], Executive, 0, 0, 0);
          if ( HIDWORD(v71[2]) )
          {
            v32 = HIDWORD(v71[2]);
            goto LABEL_111;
          }
        }
        else
        {
          if ( (v47 & 4) != 0 )
          {
            *(_WORD *)(v46 + 24) = 0;
            *(_QWORD *)(v46 + 28) = *(unsigned int *)(v11 + 8);
          }
          *(_DWORD *)(v46 + 36) = ++*(_DWORD *)(v11 + 644);
          *(_DWORD *)(v11 + 16) = v45;
          ExReleaseResourceLite((PERESOURCE)(v11 + 448));
          v22 = 0;
          v52 = 0;
        }
        v21 = v53;
      }
      v12 = v56;
    }
    else
    {
      v28 = v6;
      if ( (unsigned int)v27 < v6 )
        v28 = *(_DWORD *)(v26 + 28);
      v59 = v28;
      v29 = (unsigned int)(*(_DWORD *)(v11 + 8) - v27);
      v68 = v29;
      v30 = *(_QWORD *)(v26 + 56) + 32 * v29;
      v31 = v21 + a3;
      *(_QWORD *)(v30 + 16) = v21 + a3;
      *(_WORD *)(v30 + 26) = 0;
      if ( !v79 )
      {
        v35 = v28;
        goto LABEL_59;
      }
      v61 = v28;
      if ( (*(_DWORD *)(a2 + 212) & 0x80u) == 0 )
        goto LABEL_51;
      v63 = v21 + a3;
      if ( (unsigned __int8)UdfVmcbContigDirtyBlocksAtVbn(v27, v10 + 984, &v63, &v61) )
      {
        v33 = *(_DWORD *)(v30 + 16);
        v31 = v63;
        if ( v63 == v33 )
        {
          v31 = *(_DWORD *)(v30 + 16);
        }
        else
        {
          v53 += v63 - v33;
          v64 = v53;
          v6 += v33 - v63;
          v65 = v6;
          *(_DWORD *)(v30 + 16) = v63;
        }
LABEL_51:
        if ( !UdfSeqCacheWriteCheckPOW(v10, a2, v31, (_DWORD *)(v30 + 20), &v61, &v57) )
        {
          v32 = -1073741697;
          v22 = v52;
          goto LABEL_111;
        }
        v62 = v61;
        v34 = v61;
        if ( v28 < v61 )
          v34 = v28;
        v28 = v34;
        v59 = v34;
        v35 = v34;
        LODWORD(v29) = v68;
        if ( v57 )
          *(_BYTE *)(v30 + 26) = 1;
        v21 = v53;
        v12 = v56;
LABEL_59:
        v59 = v35;
        *(_QWORD *)(v30 + 8) = a2;
        *(_WORD *)(v30 + 24) = v28;
        if ( a2 == -1 )
          v36 = 0;
        else
          v36 = *a5;
        *(_QWORD *)v30 = v36;
        *(_DWORD *)(v11 + 40LL * *(unsigned int *)(v11 + 16) + 28) -= v35;
        if ( v12 )
        {
          *(_DWORD *)(v11 + 40LL * *(unsigned int *)(v11 + 16) + 32) += v35;
          v56 = v12 - v35;
          v60 = v12 - v35;
        }
        v37 = *(unsigned int *)(v11 + 16);
        if ( *(_DWORD *)(v11 + 40 * v37 + 28) )
        {
          if ( v35 == v6 )
          {
            ExConvertExclusiveToSharedLite((PERESOURCE)(v11 + 448));
            LODWORD(v37) = *(_DWORD *)(v11 + 16);
            v35 = v59;
            LODWORD(v29) = v68;
            v21 = v53;
          }
        }
        else
        {
          v25 = 1;
          v58 = 1;
        }
        v38 = *(_DWORD *)(v10 + 72);
        v39 = v35 << v38;
        v40 = (void *)((unsigned int)((_DWORD)v29 << v38) + *(_QWORD *)(v11 + 40 * ((unsigned int)v37 + 1LL)));
        if ( a6 )
          memmove(v40, (const void *)(a6 + (unsigned int)(v21 << v38)), v39);
        else
          memset(v40, 0, v39);
        if ( v79 && (*(_DWORD *)(a2 + 212) & 0x80u) != 0 )
        {
          v42 = *(_DWORD *)(v30 + 16);
          v72 = v10;
          v73 = 4;
          UdfVmcbSetSectorState(v41, v10 + 984, v42, v62, 0);
        }
        v21 = v28 + v53;
        v53 = v21;
        v64 = v21;
        v6 -= v28;
        v65 = v6;
        if ( a2 == -1 || _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 376), 1u) )
        {
          v22 = v52;
          v9 = a1;
        }
        else
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1584LL));
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1640LL) = KeGetCurrentThread();
          ++*(_DWORD *)(a2 + 204);
          *(_DWORD *)(a2 + 208) = *(_DWORD *)(a2 + 208);
          ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 256LL);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 260LL) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136)
                                                                                                + 8LL)
                                                                                    + 260LL);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1640LL) = 0;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL) + 1584LL));
          v22 = v52;
          v9 = a1;
          v21 = v53;
        }
        goto LABEL_77;
      }
      v6 -= v28;
      v65 = v6;
      v21 = v28 + v53;
      v53 = v21;
      v64 = v21;
      v62 = v61;
      v22 = v52;
      v9 = a1;
      v12 = v56;
    }
  }
  v32 = v66;
LABEL_111:
  if ( v22 )
    ExReleaseResourceLite((PERESOURCE)(v11 + 448));
  if ( v23 )
    ExReleaseResourceLite((PERESOURCE)(v11 + 344));
  if ( v56 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 1584));
    *(_DWORD *)(v10 + 672) -= v56;
    *(_QWORD *)(v10 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 1584));
  }
  return v32;
}

```

## disassembly

```asm
0x140007b90  mov     [rsp+arg_18], r9d
0x140007b95  mov     [rsp+arg_10], r8d
0x140007b9a  mov     [rsp+arg_8], rdx
0x140007b9f  mov     [rsp+arg_0], rcx
0x140007ba4  push    rbx
0x140007ba5  push    rsi
0x140007ba6  push    rdi
0x140007ba7  push    r12
0x140007ba9  push    r13
0x140007bab  push    r14
0x140007bad  push    r15
0x140007baf  sub     rsp, 150h
0x140007bb6  mov     r13d, r9d
0x140007bb9  mov     esi, r8d
0x140007bbc  mov     rdi, rdx
0x140007bbf  mov     r12, rcx
0x140007bc2  mov     r14, [rcx+10h]
0x140007bc6  mov     [rsp+188h+var_F8], r14
0x140007bce  mov     rbx, [r14+68h]
0x140007bd2  xor     edx, edx; Val
0x140007bd4  mov     r8d, 40h ; '@'; Size
0x140007bda  lea     rcx, [rsp+188h+var_E8]; void *
0x140007be2  call    memset
0x140007be7  xor     r11d, r11d
0x140007bea  mov     [rsp+188h+var_13C], r11d
0x140007bef  mov     [rsp+188h+var_130], r11d
0x140007bf4  mov     [rsp+188h+var_128], r11d
0x140007bf9  mov     [rsp+188h+arg_30], r11b
0x140007c01  mov     [rsp+188h+var_138], r11b
0x140007c06  test    dword ptr [r14+30h], 20000000h
0x140007c0e  jz      short loc_140007C5F
0x140007c10  mov     rbx, [r14+68h]
0x140007c14  lea     rax, [rbx+250h]
0x140007c1b  mov     [rsp+188h+var_100], rax
0x140007c23  cmp     rdi, [r14+140h]
0x140007c2a  jz      short loc_140007C51
0x140007c2c  cmp     rdi, [r14+110h]
0x140007c33  jz      short loc_140007C51
0x140007c35  mov     [rsp+188h+var_110], rbx
0x140007c3a  cmp     rdi, [r14+148h]
0x140007c41  jnz     short loc_140007C73
0x140007c43  mov     rbx, [r14+78h]
0x140007c47  mov     [rsp+188h+arg_30], 1
0x140007c4f  jmp     short loc_140007C6E
0x140007c51  mov     rbx, [r14+70h]
0x140007c55  mov     [rsp+188h+arg_30], 1
0x140007c5d  jmp     short loc_140007C6E
0x140007c5f  lea     rcx, [rbx+250h]
0x140007c66  mov     [rsp+188h+var_100], rcx
0x140007c6e  mov     [rsp+188h+var_110], rbx
0x140007c73  mov     rax, [r12+40h]
0x140007c78  test    rax, rax
0x140007c7b  jz      short loc_140007C90
0x140007c7d  cmp     qword ptr [rax+8], 3
0x140007c82  jnz     short loc_140007C90
0x140007c84  mov     [rsp+188h+var_140], 1
0x140007c89  lea     rcx, [r12+1Ch]
0x140007c8e  jmp     short loc_140007CA5
0x140007c90  mov     [rsp+188h+var_140], r11b
0x140007c95  lea     rcx, [r12+1Ch]
0x140007c9a  mov     eax, [rcx]
0x140007c9c  test    al, 4
0x140007c9e  mov     [rsp+188h+var_13F], r11b
0x140007ca3  jnz     short loc_140007CAA
0x140007ca5  mov     [rsp+188h+var_13F], 1
0x140007caa  or      dword ptr [rcx], 4
0x140007cad  cmp     [r14+158h], rdi
0x140007cb4  jz      loc_140007DB5
0x140007cba  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140007cbe  jz      loc_140007DB5
0x140007cc4  mov     byte ptr [rsp+188h+Timeout], r11b
0x140007cc9  mov     r9d, r13d
0x140007ccc  mov     r8d, esi
0x140007ccf  mov     rdx, rdi
0x140007cd2  mov     rcx, r12
0x140007cd5  call    UdfSeqCacheUnReserveFileRegion
0x140007cda  mov     r11d, eax
0x140007cdd  mov     [rsp+188h+var_13C], eax
0x140007ce1  mov     [rsp+188h+var_130], eax
0x140007ce5  cmp     eax, r13d
0x140007ce8  jnb     loc_140007DB5
0x140007cee  lea     rcx, [r14+630h]; FastMutex
0x140007cf5  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140007cfc  nop     dword ptr [rax+rax+00h]
0x140007d01  mov     rcx, gs:188h
0x140007d0a  mov     [r14+668h], rcx
0x140007d11  cmp     [r14+160h], rdi
0x140007d18  jz      short loc_140007D29
0x140007d1a  xor     edx, edx
0x140007d1c  mov     rcx, r14
0x140007d1f  call    UdfAvailableFreeBlocks
0x140007d24  mov     r9d, eax
0x140007d27  jmp     short loc_140007D37
0x140007d29  mov     r9d, [r14+29Ch]
0x140007d30  sub     r9d, [r14+2A0h]
0x140007d37  mov     ecx, r13d
0x140007d3a  mov     r15d, [rsp+188h+var_13C]
0x140007d3f  sub     ecx, r15d
0x140007d42  mov     eax, [r14+2A0h]
0x140007d49  cmp     r9d, ecx
0x140007d4c  jb      short loc_140007D5F
0x140007d4e  mov     [rsp+188h+var_13C], r13d
0x140007d53  mov     [rsp+188h+var_130], r13d
0x140007d58  mov     edi, r13d
0x140007d5b  add     eax, ecx
0x140007d5d  jmp     short loc_140007D65
0x140007d5f  mov     edi, r15d
0x140007d62  sub     eax, r15d
0x140007d65  mov     [r14+2A0h], eax
0x140007d6c  mov     qword ptr [r14+668h], 0
0x140007d77  lea     rcx, [r14+630h]; FastMutex
0x140007d7e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140007d85  nop     dword ptr [rax+rax+00h]
0x140007d8a  cmp     edi, r13d
0x140007d8d  jnb     short loc_140007DA8
0x140007d8f  mov     eax, 0C000007Fh
0x140007d94  add     rsp, 150h
0x140007d9b  pop     r15
0x140007d9d  pop     r14
0x140007d9f  pop     r13
0x140007da1  pop     r12
0x140007da3  pop     rdi
0x140007da4  pop     rsi
0x140007da5  pop     rbx
0x140007da6  retn
0x140007da8  mov     rdi, [rsp+188h+arg_8]
0x140007db0  mov     r11d, [rsp+188h+var_13C]
0x140007db5  xor     r10d, r10d
0x140007db8  mov     [rsp+188h+var_144], r10d
0x140007dbd  mov     [rsp+188h+var_118], r10d
0x140007dc2  xor     r15b, r15b
0x140007dc5  mov     [rsp+188h+var_148], r15b
0x140007dca  xor     sil, sil
0x140007dcd  mov     [rsp+188h+var_13E], sil
0x140007dd2  mov     eax, [r14+850h]
0x140007dd9  test    al, 4
0x140007ddb  jnz     short loc_140007E07
0x140007ddd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140007de1  jz      short loc_140007E07
0x140007de3  call    cs:__imp_IoGetTopLevelIrp
0x140007dea  nop     dword ptr [rax+rax+00h]
0x140007def  cmp     rax, 2
0x140007df3  jz      short loc_140007DFD
0x140007df5  mov     rcx, r12
0x140007df8  call    UdfMarkVolumeOpenAndQueueCloseDpc
0x140007dfd  mov     r11d, [rsp+188h+var_13C]
0x140007e02  mov     r10d, [rsp+188h+var_144]
0x140007e07  test    r13d, r13d
0x140007e0a  jz      loc_14000850F
0x140007e10  test    sil, sil
0x140007e13  jnz     short loc_140007E3C
0x140007e15  lea     rdx, [rbx+158h]
0x140007e1c  xor     r9d, r9d
0x140007e1f  xor     r8d, r8d
0x140007e22  mov     rcx, r12
0x140007e25  call    UdfAcquireResource
0x140007e2a  mov     sil, 1
0x140007e2d  mov     [rsp+188h+var_13E], sil
0x140007e32  mov     r10d, [rsp+188h+var_144]
0x140007e37  mov     r11d, [rsp+188h+var_13C]
0x140007e3c  mov     rax, [r14+68h]
0x140007e40  mov     ecx, [rax+4]
0x140007e43  and     ecx, 10h
0x140007e46  mov     eax, [r14+30h]
0x140007e4a  bt      eax, 1Dh
0x140007e4e  jb      loc_140007F87
0x140007e54  test    ecx, ecx
0x140007e56  jnz     loc_140007F8F
0x140007e5c  test    r15b, r15b
0x140007e5f  jnz     short loc_140007E88
0x140007e61  lea     rdx, [rbx+1C0h]
0x140007e68  xor     r9d, r9d
0x140007e6b  xor     r8d, r8d
0x140007e6e  mov     rcx, r12
0x140007e71  call    UdfAcquireResource
0x140007e76  mov     r15b, 1
0x140007e79  mov     [rsp+188h+var_148], r15b
0x140007e7e  mov     r10d, [rsp+188h+var_144]
0x140007e83  mov     r11d, [rsp+188h+var_13C]
0x140007e88  mov     [rsp+188h+var_134], 0
0x140007e90  xor     dil, dil
0x140007e93  mov     [rsp+188h+var_137], dil
0x140007e98  mov     eax, [rbx+10h]
0x140007e9b  lea     rcx, [rax+rax*4]
0x140007e9f  lea     rdx, [rbx+rcx*8]
0x140007ea3  mov     ecx, [rdx+1Ch]
0x140007ea6  test    ecx, ecx
0x140007ea8  jz      loc_140008283
0x140007eae  xor     eax, eax
0x140007eb0  cmp     ax, [rdx+18h]
0x140007eb4  jnz     loc_140008283
0x140007eba  mov     r15d, r13d
0x140007ebd  cmp     ecx, r13d
0x140007ec0  cmovb   r15d, ecx
0x140007ec4  mov     [rsp+188h+var_134], r15d
0x140007ec9  mov     eax, [rbx+8]
0x140007ecc  sub     eax, ecx
0x140007ece  mov     r9d, eax
0x140007ed1  mov     [rsp+188h+var_108], r9
0x140007ed9  mov     r12d, eax
0x140007edc  shl     r12, 5
0x140007ee0  add     r12, [rdx+38h]
0x140007ee4  mov     r8d, [rsp+188h+arg_10]
0x140007eec  add     r8d, r10d
0x140007eef  mov     [r12+10h], r8d
0x140007ef4  mov     dword ptr [r12+14h], 0
0x140007efd  mov     word ptr [r12+1Ah], 0
0x140007f05  cmp     [rsp+188h+arg_30], dil
0x140007f0d  jz      loc_140008049
0x140007f13  mov     [rsp+188h+var_12C], r15d
0x140007f18  mov     rax, [rsp+188h+arg_8]
0x140007f20  mov     eax, [rax+0D4h]
0x140007f26  test    al, al
0x140007f28  jns     loc_140007FD0
0x140007f2e  mov     [rsp+188h+var_124], r8d
0x140007f33  lea     rdx, [r14+3D8h]
0x140007f3a  lea     r9, [rsp+188h+var_12C]
0x140007f3f  lea     r8, [rsp+188h+var_124]
0x140007f44  call    UdfVmcbContigDirtyBlocksAtVbn
0x140007f49  test    al, al
0x140007f4b  jnz     short loc_140007F99
0x140007f4d  sub     r13d, r15d
0x140007f50  mov     [rsp+188h+var_11C], r13d
0x140007f55  mov     r10d, [rsp+188h+var_144]
0x140007f5a  add     r10d, r15d
0x140007f5d  mov     [rsp+188h+var_144], r10d
0x140007f62  mov     [rsp+188h+var_120], r10d
0x140007f67  mov     eax, [rsp+188h+var_12C]
0x140007f6b  mov     [rsp+188h+var_128], eax
0x140007f6f  movzx   r15d, [rsp+188h+var_148]
0x140007f75  mov     r12, [rsp+188h+arg_0]
0x140007f7d  mov     r11d, [rsp+188h+var_13C]
0x140007f82  jmp     loc_140007E07
0x140007f87  test    ecx, ecx
0x140007f89  jz      loc_140007E5C
0x140007f8f  mov     edi, 0C0000240h
0x140007f94  jmp     loc_140008513
0x140007f99  mov     ecx, [r12+10h]
0x140007f9e  mov     r8d, [rsp+188h+var_124]
0x140007fa3  cmp     r8d, ecx
0x140007fa6  jz      short loc_140007FCD
0x140007fa8  mov     eax, r8d
0x140007fab  sub     eax, ecx
0x140007fad  mov     edx, [rsp+188h+var_144]
0x140007fb1  add     edx, eax
0x140007fb3  mov     [rsp+188h+var_144], edx
0x140007fb7  mov     [rsp+188h+var_120], edx
0x140007fbb  sub     ecx, r8d
0x140007fbe  add     r13d, ecx
0x140007fc1  mov     [rsp+188h+var_11C], r13d
0x140007fc6  mov     [r12+10h], r8d
0x140007fcb  jmp     short loc_140007FD0
0x140007fcd  mov     r8d, ecx
0x140007fd0  lea     rax, [rsp+188h+var_138]
0x140007fd5  mov     [rsp+188h+var_160], rax
0x140007fda  lea     rax, [rsp+188h+var_12C]
0x140007fdf  mov     [rsp+188h+Timeout], rax
0x140007fe4  lea     r9, [r12+14h]
0x140007fe9  mov     rdx, [rsp+188h+arg_8]
0x140007ff1  mov     rcx, r14
0x140007ff4  call    UdfSeqCacheWriteCheckPOW
0x140007ff9  test    al, al
0x140007ffb  jnz     short loc_14000800D
0x140007ffd  mov     edi, 0C000007Fh
0x140008002  movzx   r15d, [rsp+188h+var_148]
0x140008008  jmp     loc_140008513
0x14000800d  mov     ecx, [rsp+188h+var_12C]
0x140008011  mov     [rsp+188h+var_128], ecx
0x140008015  mov     eax, ecx
0x140008017  cmp     r15d, ecx
0x14000801a  cmovb   eax, r15d
0x14000801e  mov     r15d, eax
0x140008021  mov     [rsp+188h+var_134], eax
0x140008025  mov     r8d, eax
0x140008028  mov     r9, [rsp+188h+var_108]
0x140008030  cmp     [rsp+188h+var_138], dil
0x140008035  jz      short loc_14000803D
0x140008037  mov     byte ptr [r12+1Ah], 1
0x14000803d  mov     r10d, [rsp+188h+var_144]
0x140008042  mov     r11d, [rsp+188h+var_13C]
0x140008047  jmp     short loc_14000804C
0x140008049  mov     r8d, r15d
0x14000804c  mov     [rsp+188h+var_134], r8d
0x140008051  mov     rax, [rsp+188h+arg_8]
0x140008059  mov     [r12+8], rax
0x14000805e  mov     [r12+18h], r15w
0x140008064  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140008068  jz      short loc_140008077
0x14000806a  mov     rax, [rsp+188h+arg_20]
0x140008072  mov     rax, [rax]
0x140008075  jmp     short loc_140008079
0x140008077  xor     eax, eax
0x140008079  mov     [r12], rax
0x14000807d  mov     eax, [rbx+10h]
0x140008080  lea     rcx, [rax+rax*4]
0x140008084  sub     [rbx+rcx*8+1Ch], r8d
0x140008089  test    r11d, r11d
0x14000808c  jz      short loc_1400080A7
0x14000808e  mov     eax, [rbx+10h]
0x140008091  lea     rcx, [rax+rax*4]
  ... truncated ...
```
