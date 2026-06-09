# OutSendPacket

- ea: `0x1400037e0`
- end: `0x140003ea0`
- name: `OutSendPacket`
- size: `1728`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400035a0`
- `0x140003660`
- `0x140009ae8`
- `0x14000a3dc`
- `0x14000a810`

## callees

- `0x1400037e0`
- `0x140003ea0`
- `0x1400042b0`
- `0x140004790`
- `0x140004860`
- `0x140005230`
- `0x140005b90`
- `0x140005fe0`
- `0x140008f90`
- `0x1400097ec`
- `0x140009920`
- `0x14000a160`
- `0x14000a1cc`
- `0x14000a248`
- `0x14000a2f4`
- `0x14001172c`
- `0x140011f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000383f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000383f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003e33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003e33`
- `ntoskrnl!IoQueueWorkItem` at `0x14000391a`
- `ntoskrnl!IoQueueWorkItem` at `0x14000391a`
- `HAL!KeQueryPerformanceCounter` at `0x140003d00`
- `HAL!KeQueryPerformanceCounter` at `0x140003d00`

## pseudocode

```c
__int64 __fastcall OutSendPacket(__int64 a1, __int64 a2, int a3, char a4, char a5)
{
  __int64 v8; // rsi
  KSPIN_LOCK *v9; // r15
  KIRQL v10; // al
  signed __int64 *v11; // r8
  int v12; // ecx
  __int64 v13; // rbp
  signed __int64 v14; // rax
  signed __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rcx
  _QWORD *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  char v23; // al
  void *v24; // rcx
  size_t v25; // r10
  int v26; // eax
  __int64 v27; // r15
  int v28; // edi
  __int64 v29; // r14
  unsigned int v30; // r8d
  _DWORD *v31; // rdx
  int v32; // r12d
  unsigned int v33; // ecx
  int v34; // edx
  unsigned int v35; // r9d
  __int64 v36; // r11
  unsigned int v37; // edx
  unsigned int v38; // eax
  unsigned int v39; // ecx
  int v40; // edx
  unsigned int v41; // r9d
  unsigned int v42; // edx
  int v43; // eax
  int v44; // r9d
  _DWORD *v45; // rcx
  unsigned int v46; // edx
  unsigned int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // r8
  __int64 v51; // rdx
  LARGE_INTEGER PerformanceCounter; // rax
  bool v53; // zf
  int v54; // eax
  signed __int32 v55[8]; // [rsp+0h] [rbp-88h] BYREF
  __int64 v56; // [rsp+20h] [rbp-68h]
  __int64 v57; // [rsp+28h] [rbp-60h]
  int v58; // [rsp+38h] [rbp-50h]
  KIRQL v59[8]; // [rsp+40h] [rbp-48h] BYREF
  _DWORD *v60; // [rsp+48h] [rbp-40h]
  void *Src; // [rsp+50h] [rbp-38h]
  KIRQL v62; // [rsp+90h] [rbp+8h]

  if ( *(_DWORD *)(a1 + 24) != 1 )
    return 3221225488LL;
  v8 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 48) = a2;
  *(_DWORD *)(a1 + 56) = a3;
  *(_BYTE *)(a1 + 60) = a4;
  v9 = (KSPIN_LOCK *)(v8 + 256);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 256));
  v12 = *(_DWORD *)(v8 + 264);
  v62 = v10;
  v59[0] = v10;
  if ( v12 != 1 )
  {
    if ( !v12 )
    {
      ++*(_DWORD *)(v8 + 520);
      v18 = -1073741436;
      *(_DWORD *)(a1 + 24) = 1;
      *(_BYTE *)(a1 + 61) = 0;
      goto LABEL_91;
    }
    goto LABEL_16;
  }
  v13 = 0;
  if ( a4 )
  {
    v11 = *(signed __int64 **)(v8 + 712);
    _m_prefetchw(v11);
    v14 = *v11;
    while ( v14 )
    {
      v13 = (unsigned int)v14;
      v15 = v14;
      v16 = (unsigned int)v14;
      v14 = _InterlockedCompareExchange64(v11, v11[v16], v14);
      if ( v14 == v15 )
      {
        if ( (_DWORD)v13 )
        {
          v11[v16] = a1;
          *(_DWORD *)(a1 + 28) = v13;
          goto LABEL_10;
        }
        break;
      }
    }
    *(_DWORD *)(v8 + 264) = 4;
    OutpEnqueuePollingDpc(v8);
    goto LABEL_16;
  }
LABEL_10:
  if ( *(_BYTE *)(a1 + 61) == 1
    && *(_BYTE *)(*(_QWORD *)v8 + 2897LL)
    && (*(_DWORD *)(a1 + 24) != 2 || !*(_QWORD *)(a1 + 80)) )
  {
    v17 = OutpPreparePacketForIsolation(v8, a1);
    v18 = v17;
    if ( v17 == -1073741801 )
    {
      v19 = *(_QWORD *)v8;
      *(_DWORD *)(v8 + 264) = 5;
      IoQueueWorkItem(*(PIO_WORKITEM *)(v19 + 2936), OutPacketAddMoreBounceWorkerRoutine, DelayedWorkQueue, (PVOID)v8);
      goto LABEL_16;
    }
    v21 = a1;
    v22 = v8;
    if ( v17 < 0 )
      goto LABEL_24;
    OutpPacketCopyToBouncePagesCycleLock(v8, a1, v59);
    v62 = v59[0];
    if ( ((*(_DWORD *)(v8 + 264) - 1) & 0xFFFFFFFB) != 0 )
    {
LABEL_16:
      if ( *(_BYTE *)(a1 + 61) == 1 )
      {
        v20 = *(_QWORD **)(a1 + 80);
        if ( v20 )
        {
          if ( *(_QWORD *)(v8 + 272) != v8 + 272 )
          {
            KmclpFreeBounceList(*(_QWORD *)v8, v20);
            *(_QWORD *)(a1 + 80) = 0;
          }
        }
      }
      if ( (a5 & 4) != 0 )
      {
        ++*(_DWORD *)(v8 + 516);
        v18 = -2147483643;
        v21 = a1;
        v22 = v8;
LABEL_24:
        OutpTransitionPacketToReadyToComplete(v22, v21);
        *(_DWORD *)(a1 + 24) = 1;
        *(_BYTE *)(a1 + 61) = 0;
        goto LABEL_91;
      }
      if ( (a5 & 1) != 0 )
      {
        if ( *(_DWORD *)(a1 + 172) < *(_DWORD *)(a1 + 56) )
        {
          ++*(_DWORD *)(v8 + 524);
          v18 = -1073741789;
          v21 = a1;
          v22 = v8;
          goto LABEL_24;
        }
        memmove((void *)(a1 + 240), *(const void **)(a1 + 48), *(unsigned int *)(a1 + 56));
        *(_QWORD *)(a1 + 48) = a1 + 240;
      }
      OutpEnqueuePacket(v8, a1 + 144);
      *(_DWORD *)(a1 + 24) = 2;
      if ( *(_DWORD *)(v8 + 264) == 2 )
        ++*(_DWORD *)(v8 + 460);
LABEL_90:
      v18 = 259;
      goto LABEL_91;
    }
  }
  v23 = *(_BYTE *)(a1 + 61);
  if ( v23 == 1 )
  {
    v48 = *(_QWORD *)(a1 + 80);
    v49 = v8 + 64;
    v50 = *(unsigned int *)(a1 + 56);
    v51 = *(_QWORD *)(a1 + 48);
    if ( v48 )
    {
      v26 = anonymous_namespace_::PkSendPacketGpaDirect__anonymous_namespace_::PacketLibListWrapper_(
              v49,
              v51,
              v50,
              v13,
              v48);
    }
    else
    {
      LOBYTE(v58) = *(_BYTE *)(a1 + 62) & 1;
      v26 = PkSendPacketGpaDirect(
              v49,
              v51,
              v50,
              v13,
              *(_QWORD *)(a1 + 64),
              *(_DWORD *)(a1 + 72),
              *(_DWORD *)(a1 + 76),
              v58);
    }
    goto LABEL_66;
  }
  v24 = *(void **)(a1 + 48);
  v25 = *(unsigned int *)(a1 + 56);
  Src = v24;
  if ( v23 )
  {
    v57 = *(_QWORD *)(a1 + 64);
    LOWORD(v56) = *(_WORD *)(a1 + 72);
    v26 = PkSendPacketTransferPage(v8 + 64, v24, (unsigned int)v25, v13, v56, v57);
LABEL_66:
    v28 = v26;
    goto LABEL_67;
  }
  v27 = (unsigned int)(v25 + 16);
  if ( (unsigned int)v27 > 0x7FFF8 )
  {
    v28 = -1073741811;
    v9 = (KSPIN_LOCK *)(v8 + 256);
    goto LABEL_67;
  }
  v29 = *(unsigned int *)(v8 + 192);
  v30 = *(_DWORD *)(v8 + 80);
  v31 = (_DWORD *)(v29 + *(_QWORD *)(v8 + 72));
  v32 = (v25 + 23) & 0xFFFFFFF8;
  v60 = v31;
  _m_prefetchw(v31);
  v33 = *(_DWORD *)(v8 + 196) - v29 - 8;
  if ( v33 >= v30 )
    v33 += v30;
  if ( v33 < v32 + 8 )
  {
    if ( !(unsigned __int8)PkpValidatePointer(v30, *(unsigned int *)(*(_QWORD *)(v8 + 64) + 4LL)) )
    {
      v9 = (KSPIN_LOCK *)(v8 + 256);
      v28 = -1073741566;
      goto LABEL_67;
    }
    *(_DWORD *)(v8 + 196) = v34;
    v37 = v34 - v29 - 8;
    if ( v37 >= (unsigned int)v11 )
      v37 += (unsigned int)v11;
    if ( v37 < v35 )
    {
      if ( v35 >= (unsigned int)v11 )
      {
        v9 = (KSPIN_LOCK *)(v8 + 256);
        v28 = -1073741811;
        goto LABEL_67;
      }
      if ( !*(_DWORD *)(v8 + 200)
        && (unsigned int)(*(_DWORD *)(v8 + 136) + *(_DWORD *)(v8 + 204) - *(_DWORD *)(v8 + 140)) < 0x40 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 204));
      }
      v38 = v29 - *(_DWORD *)(v8 + 192);
      if ( v38 >= (unsigned int)v11 )
        v38 += (unsigned int)v11;
      v39 = v35 + v38;
      if ( v35 + v38 >= (unsigned int)v11 )
        v39 = (_DWORD)v11 - 8;
      *(_DWORD *)(v36 + 12) = v39;
      *(_DWORD *)(v8 + 200) = v32;
      _InterlockedOr(v55, 0);
      if ( !(unsigned __int8)PkpValidatePointer((unsigned int)v11, *(unsigned int *)(v36 + 4)) )
      {
        v9 = (KSPIN_LOCK *)(v8 + 256);
        v28 = -1073741566;
        goto LABEL_67;
      }
      *(_DWORD *)(v8 + 196) = v40;
      v42 = v40 - v29 - 8;
      if ( v42 >= (unsigned int)v11 )
        v42 += (unsigned int)v11;
      if ( v42 < v41 )
      {
        v9 = (KSPIN_LOCK *)(v8 + 256);
        v28 = -2147483643;
        goto LABEL_67;
      }
    }
    v31 = v60;
  }
  *v31 = 131078;
  *((_WORD *)v31 + 2) = (unsigned __int64)(v27 + 7) >> 3;
  *((_WORD *)v31 + 3) = a4 != 0;
  *((_QWORD *)v31 + 1) = (unsigned int)v13;
  memmove(v31 + 4, Src, v25);
  v43 = PkWritePacketFooter(v8 + 64, (unsigned int)v29, (unsigned int)v27);
  v44 = *(_DWORD *)(v8 + 192);
  v45 = *(_DWORD **)(v8 + 64);
  v46 = *(_DWORD *)(v8 + 80);
  *(_DWORD *)(v8 + 192) = v43;
  *v45 = v43;
  _InterlockedOr(v55, 0);
  LODWORD(v11) = v45[2];
  v47 = v45[1];
  if ( v47 >= v46 || (v47 & 7) != 0 )
  {
    v28 = -1073741566;
    v9 = (KSPIN_LOCK *)(v8 + 256);
  }
  else
  {
    *(_DWORD *)(v8 + 196) = v47;
    if ( v44 == v47 )
    {
      if ( !(_DWORD)v11 )
      {
        v9 = (KSPIN_LOCK *)(v8 + 256);
        v28 = 532;
        goto LABEL_67;
      }
      ++**(_QWORD **)(v8 + 216);
    }
    v9 = (KSPIN_LOCK *)(v8 + 256);
    v28 = 0;
  }
LABEL_67:
  if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 2) != 0 )
    McTemplateK0jjxth_EtwWriteTransfer(
      *(_DWORD *)v8 + 2752,
      (unsigned int)VMBUS_SEND_PACKET,
      (_DWORD)v11,
      *(_DWORD *)v8 + 2768,
      *(_QWORD *)v8 + 2752LL,
      v13,
      0,
      *(_WORD *)(*(_QWORD *)v8 + 3280LL));
  if ( v28 >= 0 )
  {
    if ( a4 )
    {
      if ( KmclPerformanceCounterTimingCounters )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v53 = KmclPerformanceCounterTimingCounters == 0;
        *(LARGE_INTEGER *)(a1 + 128) = PerformanceCounter;
        if ( !v53 )
          ++*(_DWORD *)(v8 + 512);
      }
    }
  }
  v54 = OutpProcessRingResult(v8, (unsigned int)v28);
  v18 = v54;
  if ( v54 == -2147483643 )
    goto LABEL_16;
  if ( v54 < 0 )
  {
    v21 = a1;
    v22 = v8;
    goto LABEL_24;
  }
  if ( a4 )
  {
    *(_DWORD *)(a1 + 24) = 3;
    goto LABEL_90;
  }
  if ( (a5 & 2) == 0 )
  {
    OutpTransitionPacketToReadyToComplete(v8, a1);
    KeReleaseSpinLock(v9, v62);
    OutCompletePacketToClient(a1, 0, 0);
    return 259;
  }
  v18 = 0;
LABEL_91:
  KeReleaseSpinLock(v9, v62);
  if ( *(_BYTE *)(*(_QWORD *)v8 + 2897LL) )
  {
    if ( *(_DWORD *)(v8 + 456) == 10000 * (*(_DWORD *)(v8 + 456) / 0x2710u) )
      KmclpFreeOldBounceBlocks(*(_QWORD *)v8);
  }
  return v18;
}

```

## disassembly

```asm
0x1400037e0  push    rbx
0x1400037e2  push    r13
0x1400037e4  sub     rsp, 78h
0x1400037e8  cmp     dword ptr [rcx+18h], 1
0x1400037ec  movzx   r13d, r9b
0x1400037f0  mov     rbx, rcx
0x1400037f3  jz      short loc_140003803
0x1400037f5  mov     eax, 0C0000010h
0x1400037fa  add     rsp, 78h
0x1400037fe  pop     r13
0x140003800  pop     rbx
0x140003801  retn
0x140003803  mov     [rsp+88h+arg_8], rbp
0x14000380b  mov     [rsp+88h+arg_10], rsi
0x140003813  mov     rsi, [rcx+10h]
0x140003817  mov     [rsp+88h+arg_18], rdi
0x14000381f  mov     [rcx+30h], rdx
0x140003823  mov     [rcx+38h], r8d
0x140003827  mov     [rcx+3Ch], r13b
0x14000382b  mov     [rsp+88h+var_20], r14
0x140003830  mov     [rsp+88h+var_28], r15
0x140003835  lea     r15, [rsi+100h]
0x14000383c  mov     rcx, r15; SpinLock
0x14000383f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003846  nop     dword ptr [rax+rax+00h]
0x14000384b  mov     ecx, [rsi+108h]
0x140003851  mov     ebp, 2
0x140003856  mov     [rsp+88h+arg_0], al
0x14000385d  mov     [rsp+88h+var_48], al
0x140003861  cmp     ecx, 1
0x140003864  jnz     loc_140003DA4
0x14000386a  xor     ebp, ebp
0x14000386c  test    r13b, r13b
0x14000386f  jz      short loc_1400038B3
0x140003871  mov     r8, [rsi+2C8h]
0x140003878  prefetchw byte ptr [r8]
0x14000387c  mov     rax, [r8]
0x14000387f  nop
0x140003880  test    rax, rax
0x140003883  jz      loc_140003978
0x140003889  mov     ebp, eax
0x14000388b  mov     rdx, rax
0x14000388e  lea     r9, ds:0[rbp*8]
0x140003896  mov     rcx, [r9+r8]
0x14000389a  lock cmpxchg [r8], rcx
0x14000389f  cmp     rax, rdx
0x1400038a2  jnz     short loc_140003880
0x1400038a4  test    ebp, ebp
0x1400038a6  jz      loc_140003978
0x1400038ac  mov     [r9+r8], rbx
0x1400038b0  mov     [rbx+1Ch], ebp
0x1400038b3  cmp     byte ptr [rbx+3Dh], 1
0x1400038b7  jnz     loc_1400039D4
0x1400038bd  mov     rax, [rsi]
0x1400038c0  cmp     byte ptr [rax+0B51h], 0
0x1400038c7  jz      loc_1400039D4
0x1400038cd  cmp     dword ptr [rbx+18h], 2
0x1400038d1  jnz     short loc_1400038DE
0x1400038d3  cmp     qword ptr [rbx+50h], 0
0x1400038d8  jnz     loc_1400039D4
0x1400038de  mov     rdx, rbx
0x1400038e1  mov     rcx, rsi
0x1400038e4  call    OutpPreparePacketForIsolation
0x1400038e9  mov     edi, eax
0x1400038eb  cmp     eax, 0C0000017h
0x1400038f0  jnz     loc_14000398C
0x1400038f6  mov     rcx, [rsi]
0x1400038f9  lea     rdx, OutPacketAddMoreBounceWorkerRoutine; WorkerRoutine
0x140003900  mov     dword ptr [rsi+108h], 5
0x14000390a  mov     r9, rsi; Context
0x14000390d  mov     r8d, 1; QueueType
0x140003913  mov     rcx, [rcx+0B78h]; IoWorkItem
0x14000391a  call    cs:__imp_IoQueueWorkItem
0x140003921  nop     dword ptr [rax+rax+00h]
0x140003926  mov     ebp, 2
0x14000392b  cmp     byte ptr [rbx+3Dh], 1
0x14000392f  jnz     short loc_140003956
0x140003931  mov     rdx, [rbx+50h]
0x140003935  test    rdx, rdx
0x140003938  jz      short loc_140003956
0x14000393a  lea     rax, [rsi+110h]
0x140003941  cmp     [rax], rax
0x140003944  jz      short loc_140003956
0x140003946  mov     rcx, [rsi]
0x140003949  call    KmclpFreeBounceList
0x14000394e  mov     qword ptr [rbx+50h], 0
0x140003956  mov     eax, [rsp+88h+arg_20]
0x14000395d  test    al, 4
0x14000395f  jz      loc_140003DC3
0x140003965  inc     dword ptr [rsi+204h]
0x14000396b  mov     edi, 80000005h
0x140003970  mov     rdx, rbx
0x140003973  mov     rcx, rsi
0x140003976  jmp     short loc_140003996
0x140003978  mov     rcx, rsi
0x14000397b  mov     dword ptr [rsi+108h], 4
0x140003985  call    OutpEnqueuePollingDpc
0x14000398a  jmp     short loc_140003926
0x14000398c  mov     rdx, rbx
0x14000398f  mov     rcx, rsi
0x140003992  test    eax, eax
0x140003994  jns     short loc_1400039AB
0x140003996  call    OutpTransitionPacketToReadyToComplete
0x14000399b  mov     dword ptr [rbx+18h], 1
0x1400039a2  mov     byte ptr [rbx+3Dh], 0
0x1400039a6  jmp     loc_140003E28
0x1400039ab  lea     r8, [rsp+88h+var_48]
0x1400039b0  call    OutpPacketCopyToBouncePagesCycleLock
0x1400039b5  mov     eax, [rsi+108h]
0x1400039bb  dec     eax
0x1400039bd  test    eax, 0FFFFFFFBh
0x1400039c2  movzx   eax, [rsp+88h+var_48]
0x1400039c7  mov     [rsp+88h+arg_0], al
0x1400039ce  jnz     loc_140003926
0x1400039d4  movzx   eax, byte ptr [rbx+3Dh]
0x1400039d8  cmp     al, 1
0x1400039da  jz      loc_140003C5B
0x1400039e0  mov     rcx, [rbx+30h]
0x1400039e4  mov     r10d, [rbx+38h]
0x1400039e8  mov     [rsp+88h+Src], rcx
0x1400039ed  test    al, al
0x1400039ef  jz      short loc_140003A1A
0x1400039f1  mov     rax, [rbx+40h]
0x1400039f5  mov     rdx, rcx
0x1400039f8  mov     [rsp+88h+var_60], rax
0x1400039fd  lea     rcx, [rsi+40h]
0x140003a01  movzx   eax, word ptr [rbx+48h]
0x140003a05  mov     r9, rbp
0x140003a08  mov     r8d, r10d
0x140003a0b  mov     word ptr [rsp+88h+var_68], ax
0x140003a10  call    PkSendPacketTransferPage
0x140003a15  jmp     loc_140003CA5
0x140003a1a  lea     r15d, [r10+10h]
0x140003a1e  cmp     r15d, 7FFF8h
0x140003a25  jbe     short loc_140003A38
0x140003a27  mov     edi, 0C000000Dh
0x140003a2c  lea     r15, [rsi+100h]
0x140003a33  jmp     loc_140003CA7
0x140003a38  mov     r14d, [rsi+0C0h]
0x140003a3f  lea     eax, [r15+7]
0x140003a43  mov     rdx, [rsi+48h]
0x140003a47  and     eax, 0FFFFFFF8h
0x140003a4a  mov     r8d, [rsi+50h]
0x140003a4e  add     rdx, r14
0x140003a51  mov     [rsp+88h+var_18], r12
0x140003a56  mov     r12d, eax
0x140003a59  mov     [rsp+88h+var_40], rdx
0x140003a5e  lea     r9d, [rax+8]
0x140003a62  prefetchw byte ptr [rdx]
0x140003a65  mov     ecx, [rsi+0C4h]
0x140003a6b  sub     ecx, r14d
0x140003a6e  add     ecx, 0FFFFFFF8h
0x140003a71  cmp     ecx, r8d
0x140003a74  lea     eax, [rcx+r8]
0x140003a78  cmovnb  ecx, eax
0x140003a7b  cmp     ecx, r9d
0x140003a7e  jnb     loc_140003B99
0x140003a84  mov     r11, [rsi+40h]
0x140003a88  mov     ecx, r8d
0x140003a8b  mov     edx, [r11+4]
0x140003a8f  call    PkpValidatePointer
0x140003a94  test    al, al
0x140003a96  jnz     short loc_140003AAE
0x140003a98  mov     r12, [rsp+88h+var_18]
0x140003a9d  lea     r15, [rsi+100h]
0x140003aa4  mov     edi, 0C0000102h
0x140003aa9  jmp     loc_140003CA7
0x140003aae  mov     [rsi+0C4h], edx
0x140003ab4  sub     edx, r14d
0x140003ab7  add     edx, 0FFFFFFF8h
0x140003aba  cmp     edx, r8d
0x140003abd  jb      short loc_140003AC2
0x140003abf  add     edx, r8d
0x140003ac2  cmp     edx, r9d
0x140003ac5  jnb     loc_140003B94
0x140003acb  cmp     r9d, r8d
0x140003ace  jb      short loc_140003AE6
0x140003ad0  mov     r12, [rsp+88h+var_18]
0x140003ad5  lea     r15, [rsi+100h]
0x140003adc  mov     edi, 0C000000Dh
0x140003ae1  jmp     loc_140003CA7
0x140003ae6  cmp     dword ptr [rsi+0C8h], 0
0x140003aed  jnz     short loc_140003B11
0x140003aef  mov     edx, [rsi+88h]
0x140003af5  mov     ecx, [rsi+0CCh]
0x140003afb  mov     eax, [rsi+8Ch]
0x140003b01  sub     ecx, eax
0x140003b03  add     ecx, edx
0x140003b05  cmp     ecx, 40h ; '@'
0x140003b08  jnb     short loc_140003B11
0x140003b0a  lock inc dword ptr [rsi+0CCh]
0x140003b11  mov     eax, r14d
0x140003b14  sub     eax, [rsi+0C0h]
0x140003b1a  cmp     eax, r8d
0x140003b1d  jb      short loc_140003B22
0x140003b1f  add     eax, r8d
0x140003b22  lea     ecx, [r9+rax]
0x140003b26  cmp     ecx, r8d
0x140003b29  jb      short loc_140003B2F
0x140003b2b  lea     ecx, [r8-8]
0x140003b2f  mov     [r11+0Ch], ecx
0x140003b33  mov     [rsi+0C8h], r12d
0x140003b3a  lock or [rsp+88h+var_88], 0
0x140003b3f  mov     edx, [r11+4]
0x140003b43  mov     ecx, r8d
0x140003b46  call    PkpValidatePointer
0x140003b4b  test    al, al
0x140003b4d  jnz     short loc_140003B65
0x140003b4f  mov     r12, [rsp+88h+var_18]
0x140003b54  lea     r15, [rsi+100h]
0x140003b5b  mov     edi, 0C0000102h
0x140003b60  jmp     loc_140003CA7
0x140003b65  mov     [rsi+0C4h], edx
0x140003b6b  sub     edx, r14d
0x140003b6e  add     edx, 0FFFFFFF8h
0x140003b71  cmp     edx, r8d
0x140003b74  jb      short loc_140003B79
0x140003b76  add     edx, r8d
0x140003b79  cmp     edx, r9d
0x140003b7c  jnb     short loc_140003B94
0x140003b7e  mov     r12, [rsp+88h+var_18]
0x140003b83  lea     r15, [rsi+100h]
0x140003b8a  mov     edi, 80000005h
0x140003b8f  jmp     loc_140003CA7
0x140003b94  mov     rdx, [rsp+88h+var_40]
0x140003b99  xor     ecx, ecx
0x140003b9b  lea     rax, [r15+7]
0x140003b9f  nop
0x140003ba0  test    r13b, r13b
0x140003ba3  mov     dword ptr [rdx], 20006h
0x140003ba9  mov     r8, r10; Size
0x140003bac  setnz   cl
0x140003baf  shr     rax, 3
0x140003bb3  mov     [rdx+4], ax
0x140003bb7  mov     [rdx+6], cx
0x140003bbb  lea     rcx, [rdx+10h]; void *
0x140003bbf  mov     eax, ebp
0x140003bc1  mov     [rdx+8], rax
0x140003bc5  mov     rdx, [rsp+88h+Src]; Src
0x140003bca  call    memmove
0x140003bcf  mov     r8d, r15d
0x140003bd2  lea     rcx, [rsi+40h]
0x140003bd6  mov     edx, r14d
0x140003bd9  call    PkWritePacketFooter
0x140003bde  mov     r9d, [rsi+0C0h]
0x140003be5  mov     rcx, [rsi+40h]
0x140003be9  mov     edx, [rsi+50h]
0x140003bec  mov     [rsi+0C0h], eax
0x140003bf2  mov     [rcx], eax
0x140003bf4  lock or [rsp+88h+var_88], 0
0x140003bf9  mov     r8d, [rcx+8]
0x140003bfd  mov     eax, [rcx+4]
0x140003c00  cmp     eax, edx
0x140003c02  jnb     short loc_140003C47
0x140003c04  test    al, 7
0x140003c06  jnz     short loc_140003C47
0x140003c08  mov     [rsi+0C4h], eax
0x140003c0e  cmp     r9d, eax
0x140003c11  jnz     short loc_140003C36
0x140003c13  test    r8d, r8d
0x140003c16  jnz     short loc_140003C2C
0x140003c18  mov     r12, [rsp+88h+var_18]
0x140003c1d  lea     r15, [rsi+100h]
0x140003c24  mov     edi, 214h
0x140003c29  nop
0x140003c2a  jmp     short loc_140003CA7
0x140003c2c  mov     rax, [rsi+0D8h]
0x140003c33  inc     qword ptr [rax]
0x140003c36  mov     r12, [rsp+88h+var_18]
0x140003c3b  lea     r15, [rsi+100h]
0x140003c42  xor     edi, edi
0x140003c44  nop
0x140003c45  jmp     short loc_140003CA7
0x140003c47  mov     r12, [rsp+88h+var_18]
0x140003c4c  mov     edi, 0C0000102h
0x140003c51  nop
0x140003c52  lea     r15, [rsi+100h]
0x140003c59  jmp     short loc_140003CA7
0x140003c5b  mov     rax, [rbx+50h]
0x140003c5f  lea     rcx, [rsi+40h]
0x140003c63  mov     r8d, [rbx+38h]
0x140003c67  mov     r9, rbp
0x140003c6a  mov     rdx, [rbx+30h]
0x140003c6e  test    rax, rax
0x140003c71  jz      short loc_140003C7F
0x140003c73  mov     [rsp+88h+var_68], rax
0x140003c78  call    _anonymous_namespace___PkSendPacketGpaDirect__anonymous_namespace___PacketLibListWrapper_
0x140003c7d  jmp     short loc_140003CA5
0x140003c7f  movzx   eax, byte ptr [rbx+3Eh]
0x140003c83  and     al, 1
0x140003c85  mov     byte ptr [rsp+88h+var_50], al
0x140003c89  mov     eax, [rbx+4Ch]
0x140003c8c  mov     [rsp+88h+var_58], eax
0x140003c90  mov     eax, [rbx+48h]
0x140003c93  mov     dword ptr [rsp+88h+var_60], eax
0x140003c97  mov     rax, [rbx+40h]
0x140003c9b  mov     [rsp+88h+var_68], rax
0x140003ca0  call    PkSendPacketGpaDirect
0x140003ca5  mov     edi, eax
0x140003ca7  test    cs:Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits, 2
  ... truncated ...
```
