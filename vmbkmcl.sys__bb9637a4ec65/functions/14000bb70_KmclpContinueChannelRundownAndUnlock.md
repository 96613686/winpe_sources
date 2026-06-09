# KmclpContinueChannelRundownAndUnlock

- ea: `0x14000bb70`
- end: `0x14000c82c`
- name: `KmclpContinueChannelRundownAndUnlock`
- size: `3260`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `16`
- tags: ``

## callers

- `0x14000d310`
- `0x14000d83c`
- `0x14000d9b0`
- `0x14000e9e0`

## callees

- `0x140006e00`
- `0x140007e30`
- `0x14000840c`
- `0x14000ab90`
- `0x14000ad30`
- `0x14000af84`
- `0x14000bb70`
- `0x14000c87c`
- `0x14000cbc8`
- `0x14000cdb0`
- `0x14000cfe4`
- `0x14000dec8`
- `0x14000e148`
- `0x14000f5c4`
- `0x14000f9dc`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000be61`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000c4e1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000be61`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000c4e1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000be4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c4ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000be4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c4ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000bf8d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000c612`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000bf8d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000c612`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf99`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c61e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf99`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c61e`
- `ntoskrnl!IoCancelIrp` at `0x14000be37`
- `ntoskrnl!IoCancelIrp` at `0x14000c34f`
- `ntoskrnl!IoCancelIrp` at `0x14000be37`
- `ntoskrnl!IoCancelIrp` at `0x14000c34f`

## pseudocode

```c
void __fastcall KmclpContinueChannelRundownAndUnlock(char *Context, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct _FAST_MUTEX *v12; // r12
  __int64 v13; // r8
  char *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rbp
  void *v27; // r15
  char v28; // al
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  char *i; // r14
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 98, a3, Context, *((_DWORD *)Context + 550));
  }
  switch ( *((_DWORD *)Context + 550) )
  {
    case 3:
      v37 = *((_DWORD *)Context + 551);
      if ( v37 != 1 )
      {
        if ( v37 == 4 || !Context[1728] )
        {
          Context[2344] &= ~2u;
          KmclpDisableClosedChannel((ULONG_PTR)Context);
        }
        else if ( v37 != 3 )
        {
          *((_DWORD *)Context + 550) = 5;
          v38 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
          v39 = v38 + 207;
          v38 *= 2;
          *(_QWORD *)&Context[8 * v38 + 3304] = MEMORY[0xFFFFF78000000008];
          Context[16 * v39] = Context[2200];
          Context[8 * v38 + 3313] = Context[2204];
          *(_WORD *)&Context[8 * v38 + 3314] = *((_DWORD *)Context + 554);
          *(_WORD *)&Context[8 * v38 + 3316] = 3924;
          KmclpStartWaitForAction(Context);
        }
      }
      goto LABEL_96;
    case 4:
      v25 = *((_DWORD *)Context + 551);
      if ( v25 != 1 )
      {
        v26 = 0;
        v27 = 0;
        if ( Context[1798] )
        {
          if ( v25 == 3 )
          {
            v28 = Context[2344];
            v26 = *((_QWORD *)Context + 276);
            *((_QWORD *)Context + 276) = 0;
            if ( (v28 & 0x40) != 0 )
            {
              v27 = (void *)*((_QWORD *)Context + 395);
              Context[2344] = v28 & 0xBF;
            }
          }
        }
        *((_DWORD *)Context + 550) = 11;
        v29 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
        v30 = v29 + 207;
        v29 *= 2;
        *(_QWORD *)&Context[8 * v29 + 3304] = MEMORY[0xFFFFF78000000008];
        Context[16 * v30] = Context[2200];
        Context[8 * v29 + 3313] = Context[2204];
        *(_WORD *)&Context[8 * v29 + 3314] = *((_DWORD *)Context + 554);
        *(_WORD *)&Context[8 * v29 + 3316] = 3755;
        _InterlockedExchange((volatile __int32 *)Context + 554, 1);
        v31 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
        v32 = v31 + 207;
        v31 *= 2;
        *(_QWORD *)&Context[8 * v31 + 3304] = MEMORY[0xFFFFF78000000008];
        Context[16 * v32] = Context[2200];
        Context[8 * v31 + 3313] = Context[2204];
        *(_WORD *)&Context[8 * v31 + 3314] = *((_DWORD *)Context + 554);
        *(_WORD *)&Context[8 * v31 + 3316] = 3757;
        Context[2344] &= ~2u;
        KmclUnlockChannel(Context);
        KeEnterCriticalRegion();
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(Context + 3176));
        for ( i = (char *)*((_QWORD *)Context + 404); i != Context + 3232; i = *(char **)i )
        {
          _InterlockedIncrement((volatile signed __int32 *)Context + 554);
          v35 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
          v36 = v35 + 207;
          v35 *= 2;
          *(_QWORD *)&Context[8 * v35 + 3304] = MEMORY[0xFFFFF78000000008];
          Context[16 * v36] = Context[2200];
          Context[8 * v35 + 3313] = Context[2204];
          *(_WORD *)&Context[8 * v35 + 3314] = *((_DWORD *)Context + 554);
          *(_WORD *)&Context[8 * v35 + 3316] = 3780;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 105, v33, Context, i - 3248);
          }
          KmclpDisableChannel(i - 3248);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 106, v33, Context, i - 3248);
          }
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(Context + 3176));
        KeLeaveCriticalRegion();
        if ( !Context[1729] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
          }
          InStopQueue(Context);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
          }
        }
        if ( !Context[1728] )
          KmclpClientCloseChannel(Context);
        if ( v26 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
          }
          KmclpSignalWaiters(v26);
        }
        if ( v27 )
          KmclDecrementRundownCount(v27);
        goto LABEL_48;
      }
LABEL_96:
      KmclpFinishSuspendProcessAndUnlock(Context);
      break;
    case 5:
      *((_DWORD *)Context + 550) = 8;
      v19 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v20 = v19 + 207;
      v19 *= 2;
      *(_QWORD *)&Context[8 * v19 + 3304] = MEMORY[0xFFFFF78000000008];
      Context[16 * v20] = Context[2200];
      Context[8 * v19 + 3313] = Context[2204];
      *(_WORD *)&Context[8 * v19 + 3314] = *((_DWORD *)Context + 554);
      *(_WORD *)&Context[8 * v19 + 3316] = 3863;
      _InterlockedExchange((volatile __int32 *)Context + 554, 1);
      v21 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v22 = v21 + 207;
      v21 *= 2;
      *(_QWORD *)&Context[8 * v21 + 3304] = MEMORY[0xFFFFF78000000008];
      Context[16 * v22] = Context[2200];
      Context[8 * v21 + 3313] = Context[2204];
      *(_WORD *)&Context[8 * v21 + 3314] = *((_DWORD *)Context + 554);
      *(_WORD *)&Context[8 * v21 + 3316] = 3865;
      if ( Context[2804] )
      {
        if ( Context[2824] )
        {
          (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD))Context + 358))(*((_QWORD *)Context + 355), 0, 0);
          Context[2804] = 0;
        }
        else
        {
          _InterlockedAdd((volatile signed __int32 *)Context + 554, 1u);
          v23 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
          v24 = v23 + 207;
          v23 *= 2;
          *(_QWORD *)&Context[8 * v23 + 3304] = MEMORY[0xFFFFF78000000008];
          Context[16 * v24] = Context[2200];
          Context[8 * v23 + 3313] = Context[2204];
          *(_WORD *)&Context[8 * v23 + 3314] = *((_DWORD *)Context + 554);
          *(_WORD *)&Context[8 * v23 + 3316] = 3881;
          IoCancelIrp(*((PIRP *)Context + 348));
        }
      }
      KmclUnlockChannel(Context);
      goto LABEL_48;
    case 6:
      *((_DWORD *)Context + 550) = 9;
      v17 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v18 = v17 + 207;
      v17 *= 2;
      *(_QWORD *)&Context[8 * v17 + 3304] = MEMORY[0xFFFFF78000000008];
      Context[16 * v18] = Context[2200];
      Context[8 * v17 + 3313] = Context[2204];
      *(_WORD *)&Context[8 * v17 + 3314] = *((_DWORD *)Context + 554);
      *(_WORD *)&Context[8 * v17 + 3316] = 3562;
      KmclUnlockChannel(Context);
      break;
    case 7:
      v4 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v5 = v4 + 207;
      v4 *= 2;
      *(_QWORD *)&Context[8 * v4 + 3304] = MEMORY[0xFFFFF78000000008];
      Context[16 * v5] = Context[2200];
      Context[8 * v4 + 3313] = Context[2204];
      *(_WORD *)&Context[8 * v4 + 3314] = *((_DWORD *)Context + 554);
      *(_WORD *)&Context[8 * v4 + 3316] = 3576;
      _InterlockedExchange((volatile __int32 *)Context + 554, 1);
      v6 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v7 = v6 + 207;
      v6 *= 2;
      *(_QWORD *)&Context[8 * v6 + 3304] = MEMORY[0xFFFFF78000000008];
      Context[16 * v7] = Context[2200];
      Context[8 * v6 + 3313] = Context[2204];
      *(_WORD *)&Context[8 * v6 + 3314] = *((_DWORD *)Context + 554);
      *(_WORD *)&Context[8 * v6 + 3316] = 3578;
      *((_DWORD *)Context + 550) = 10;
      v8 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
      v9 = v8 + 207;
      v8 *= 2;
      *(_QWORD *)&Context[8 * v8 + 3304] = MEMORY[0xFFFFF78000000008];
      Context[16 * v9] = Context[2200];
      Context[8 * v8 + 3313] = Context[2204];
      *(_WORD *)&Context[8 * v8 + 3314] = *((_DWORD *)Context + 554);
      *(_WORD *)&Context[8 * v8 + 3316] = 3586;
      if ( Context[2804] )
      {
        if ( Context[2824] )
        {
          (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD))Context + 358))(*((_QWORD *)Context + 355), 0, 0);
          Context[2804] = 0;
        }
        else
        {
          _InterlockedAdd((volatile signed __int32 *)Context + 554, 1u);
          v10 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
          v11 = v10 + 207;
          v10 *= 2;
          *(_QWORD *)&Context[8 * v10 + 3304] = MEMORY[0xFFFFF78000000008];
          Context[16 * v11] = Context[2200];
          Context[8 * v10 + 3313] = Context[2204];
          *(_WORD *)&Context[8 * v10 + 3314] = *((_DWORD *)Context + 554);
          *(_WORD *)&Context[8 * v10 + 3316] = 3606;
          IoCancelIrp(*((PIRP *)Context + 348));
        }
      }
      KmclUnlockChannel(Context);
      KeEnterCriticalRegion();
      v12 = (struct _FAST_MUTEX *)(Context + 3176);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(Context + 3176));
      v14 = (char *)*((_QWORD *)Context + 404);
      if ( v14 != Context + 3232 )
      {
        do
        {
          _InterlockedAdd((volatile signed __int32 *)Context + 554, 1u);
          v15 = _InterlockedIncrement((volatile signed __int32 *)Context + 824) % 24;
          v16 = v15 + 207;
          v15 *= 2;
          *(_QWORD *)&Context[8 * v15 + 3304] = MEMORY[0xFFFFF78000000008];
          Context[16 * v16] = Context[2200];
          Context[8 * v15 + 3313] = Context[2204];
          *(_WORD *)&Context[8 * v15 + 3314] = *((_DWORD *)Context + 554);
          *(_WORD *)&Context[8 * v15 + 3316] = 3628;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 99, v13, Context, v14 - 3248);
          }
          KmclpPauseChannel(v14 - 3248);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 100, v13, Context, v14 - 3248);
          }
          v14 = *(char **)v14;
        }
        while ( v14 != Context + 3232 );
        v12 = (struct _FAST_MUTEX *)(Context + 3176);
      }
      ExReleaseFastMutexUnsafe(v12);
      KeLeaveCriticalRegion();
      if ( !Context[1729] || *((_QWORD *)Context + 266) )
        (*((void (__fastcall **)(_QWORD))Context + 313))(*((_QWORD *)Context + 296));
      if ( !Context[1729] )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
        }
        InPauseQueue(Context);
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_41;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
      }
LABEL_41:
      if ( Context[2024] )
        (*((void (__fastcall **)(char *, _QWORD))Context + 258))(Context, *((_QWORD *)Context + 255));
      else
        (*((void (__fastcall **)(char *))Context + 257))(Context);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
      }
LABEL_48:
      KmclDecrementRundownCount(Context);
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, Context);
  }
}

```

## disassembly

```asm
0x14000bb70  push    rbx
0x14000bb72  push    rbp
0x14000bb73  push    rsi
0x14000bb74  push    rdi
0x14000bb75  push    r12
0x14000bb77  push    r13
0x14000bb79  push    r14
0x14000bb7b  push    r15
0x14000bb7d  sub     rsp, 38h
0x14000bb81  mov     rbx, rcx
0x14000bb84  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb8b  lea     r12, WPP_GLOBAL_Control
0x14000bb92  mov     r13d, 1
0x14000bb98  cmp     rcx, r12
0x14000bb9b  jz      short loc_14000BBC5
0x14000bb9d  mov     eax, [rcx+2Ch]
0x14000bba0  test    r13b, al
0x14000bba3  jz      short loc_14000BBC5
0x14000bba5  cmp     byte ptr [rcx+29h], 4
0x14000bba9  jb      short loc_14000BBC5
0x14000bbab  mov     eax, [rbx+898h]
0x14000bbb1  lea     edx, [r13+61h]
0x14000bbb5  mov     rcx, [rcx+18h]
0x14000bbb9  mov     r9, rbx
0x14000bbbc  mov     dword ptr [rsp+78h+var_58], eax
0x14000bbc0  call    WPP_SF_qd
0x14000bbc5  mov     ecx, [rbx+898h]
0x14000bbcb  sub     ecx, 3
0x14000bbce  jz      loc_14000C713
0x14000bbd4  sub     ecx, r13d
0x14000bbd7  jz      loc_14000C36E
0x14000bbdd  sub     ecx, r13d
0x14000bbe0  jz      loc_14000C187
0x14000bbe6  sub     ecx, r13d
0x14000bbe9  jz      loc_14000C0F6
0x14000bbef  cmp     ecx, r13d
0x14000bbf2  jnz     loc_14000C7E8
0x14000bbf8  mov     ecx, r13d
0x14000bbfb  lock xadd [rbx+0CE0h], ecx
0x14000bc03  add     ecx, r13d
0x14000bc06  mov     esi, 2AAAAAABh
0x14000bc0b  mov     eax, esi
0x14000bc0d  imul    ecx
0x14000bc0f  sar     edx, 2
0x14000bc12  mov     eax, edx
0x14000bc14  shr     eax, 1Fh
0x14000bc17  add     edx, eax
0x14000bc19  lea     eax, [rdx+rdx*2]
0x14000bc1c  shl     eax, 3
0x14000bc1f  sub     ecx, eax
0x14000bc21  mov     rax, ds:0FFFFF78000000008h
0x14000bc2b  movsxd  rcx, ecx
0x14000bc2e  mov     rdx, rcx
0x14000bc31  add     rcx, 0CFh
0x14000bc38  add     rdx, rdx
0x14000bc3b  add     rcx, rcx
0x14000bc3e  mov     [rbx+rdx*8+0CE8h], rax
0x14000bc46  mov     al, [rbx+898h]
0x14000bc4c  mov     [rbx+rcx*8], al
0x14000bc4f  mov     ecx, r13d
0x14000bc52  mov     al, [rbx+89Ch]
0x14000bc58  mov     [rbx+rdx*8+0CF1h], al
0x14000bc5f  mov     eax, [rbx+8A8h]
0x14000bc65  mov     [rbx+rdx*8+0CF2h], ax
0x14000bc6d  mov     eax, r13d
0x14000bc70  mov     word ptr [rbx+rdx*8+0CF4h], 0DF8h
0x14000bc7a  xchg    eax, [rbx+8A8h]
0x14000bc80  lock xadd [rbx+0CE0h], ecx
0x14000bc88  add     ecx, r13d
0x14000bc8b  mov     eax, esi
0x14000bc8d  imul    ecx
0x14000bc8f  sar     edx, 2
0x14000bc92  mov     eax, edx
0x14000bc94  shr     eax, 1Fh
0x14000bc97  add     edx, eax
0x14000bc99  lea     eax, [rdx+rdx*2]
0x14000bc9c  shl     eax, 3
0x14000bc9f  sub     ecx, eax
0x14000bca1  mov     rax, ds:0FFFFF78000000008h
0x14000bcab  movsxd  rcx, ecx
0x14000bcae  mov     rdx, rcx
0x14000bcb1  add     rcx, 0CFh
0x14000bcb8  add     rdx, rdx
0x14000bcbb  add     rcx, rcx
0x14000bcbe  mov     [rbx+rdx*8+0CE8h], rax
0x14000bcc6  mov     al, [rbx+898h]
0x14000bccc  mov     [rbx+rcx*8], al
0x14000bccf  mov     ecx, r13d
0x14000bcd2  mov     al, [rbx+89Ch]
0x14000bcd8  mov     [rbx+rdx*8+0CF1h], al
0x14000bcdf  mov     eax, [rbx+8A8h]
0x14000bce5  mov     [rbx+rdx*8+0CF2h], ax
0x14000bced  mov     word ptr [rbx+rdx*8+0CF4h], 0DFAh
0x14000bcf7  mov     dword ptr [rbx+898h], 0Ah
0x14000bd01  lock xadd [rbx+0CE0h], ecx
0x14000bd09  add     ecx, r13d
0x14000bd0c  mov     eax, esi
0x14000bd0e  imul    ecx
0x14000bd10  xor     edi, edi
0x14000bd12  sar     edx, 2
0x14000bd15  mov     eax, edx
0x14000bd17  shr     eax, 1Fh
0x14000bd1a  add     edx, eax
0x14000bd1c  lea     eax, [rdx+rdx*2]
0x14000bd1f  shl     eax, 3
0x14000bd22  sub     ecx, eax
0x14000bd24  mov     rax, ds:0FFFFF78000000008h
0x14000bd2e  movsxd  rcx, ecx
0x14000bd31  mov     rdx, rcx
0x14000bd34  add     rcx, 0CFh
0x14000bd3b  add     rdx, rdx
0x14000bd3e  add     rcx, rcx
0x14000bd41  mov     [rbx+rdx*8+0CE8h], rax
0x14000bd49  mov     al, [rbx+898h]
0x14000bd4f  mov     [rbx+rcx*8], al
0x14000bd52  mov     al, [rbx+89Ch]
0x14000bd58  mov     [rbx+rdx*8+0CF1h], al
0x14000bd5f  mov     eax, [rbx+8A8h]
0x14000bd65  mov     [rbx+rdx*8+0CF2h], ax
0x14000bd6d  mov     word ptr [rbx+rdx*8+0CF4h], 0E02h
0x14000bd77  cmp     [rbx+0AF4h], dil
0x14000bd7e  jz      loc_14000BE43
0x14000bd84  cmp     [rbx+0B08h], dil
0x14000bd8b  jz      short loc_14000BDB1
0x14000bd8d  mov     rax, [rbx+0B30h]
0x14000bd94  xor     r8d, r8d
0x14000bd97  mov     rcx, [rbx+0B18h]
0x14000bd9e  xor     edx, edx
0x14000bda0  call    _guard_dispatch_icall
0x14000bda5  mov     [rbx+0AF4h], dil
0x14000bdac  jmp     loc_14000BE43
0x14000bdb1  lock add [rbx+8A8h], r13d
0x14000bdb9  mov     ecx, r13d
0x14000bdbc  lock xadd [rbx+0CE0h], ecx
0x14000bdc4  add     ecx, r13d
0x14000bdc7  mov     eax, esi
0x14000bdc9  imul    ecx
0x14000bdcb  sar     edx, 2
0x14000bdce  mov     eax, edx
0x14000bdd0  shr     eax, 1Fh
0x14000bdd3  add     edx, eax
0x14000bdd5  lea     eax, [rdx+rdx*2]
0x14000bdd8  shl     eax, 3
0x14000bddb  sub     ecx, eax
0x14000bddd  mov     rax, ds:0FFFFF78000000008h
0x14000bde7  movsxd  rcx, ecx
0x14000bdea  mov     rdx, rcx
0x14000bded  add     rcx, 0CFh
0x14000bdf4  add     rdx, rdx
0x14000bdf7  add     rcx, rcx
0x14000bdfa  mov     [rbx+rdx*8+0CE8h], rax
0x14000be02  mov     al, [rbx+898h]
0x14000be08  mov     [rbx+rcx*8], al
0x14000be0b  mov     al, [rbx+89Ch]
0x14000be11  mov     [rbx+rdx*8+0CF1h], al
0x14000be18  mov     eax, [rbx+8A8h]
0x14000be1e  mov     [rbx+rdx*8+0CF2h], ax
0x14000be26  mov     word ptr [rbx+rdx*8+0CF4h], 0E16h
0x14000be30  mov     rcx, [rbx+0AE0h]; Irp
0x14000be37  call    cs:__imp_IoCancelIrp
0x14000be3e  nop     dword ptr [rax+rax+00h]
0x14000be43  mov     rcx, rbx
0x14000be46  call    KmclUnlockChannel
0x14000be4b  call    cs:__imp_KeEnterCriticalRegion
0x14000be52  nop     dword ptr [rax+rax+00h]
0x14000be57  lea     r12, [rbx+0C68h]
0x14000be5e  mov     rcx, r12; FastMutex
0x14000be61  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000be68  nop     dword ptr [rax+rax+00h]
0x14000be6d  lea     r15, [rbx+0CA0h]
0x14000be74  mov     r14, [r15]
0x14000be77  cmp     r14, r15
0x14000be7a  jz      loc_14000BF8A
0x14000be80  lea     r12, WPP_GLOBAL_Control
0x14000be87  lea     rbp, [r14-0CB0h]
0x14000be8e  lock add [rbx+8A8h], r13d
0x14000be96  mov     ecx, r13d
0x14000be99  lock xadd [rbx+0CE0h], ecx
0x14000bea1  add     ecx, r13d
0x14000bea4  mov     eax, esi
0x14000bea6  imul    ecx
0x14000bea8  sar     edx, 2
0x14000beab  mov     eax, edx
0x14000bead  shr     eax, 1Fh
0x14000beb0  add     edx, eax
0x14000beb2  lea     eax, [rdx+rdx*2]
0x14000beb5  shl     eax, 3
0x14000beb8  sub     ecx, eax
0x14000beba  mov     rax, ds:0FFFFF78000000008h
0x14000bec4  movsxd  rcx, ecx
0x14000bec7  mov     rdx, rcx
0x14000beca  add     rcx, 0CFh
0x14000bed1  add     rdx, rdx
0x14000bed4  add     rcx, rcx
0x14000bed7  mov     [rbx+rdx*8+0CE8h], rax
0x14000bedf  mov     al, [rbx+898h]
0x14000bee5  mov     [rbx+rcx*8], al
0x14000bee8  mov     al, [rbx+89Ch]
0x14000beee  mov     [rbx+rdx*8+0CF1h], al
0x14000bef5  mov     eax, [rbx+8A8h]
0x14000befb  mov     [rbx+rdx*8+0CF2h], ax
0x14000bf03  mov     word ptr [rbx+rdx*8+0CF4h], 0E2Ch
0x14000bf0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf14  cmp     rcx, r12
0x14000bf17  jz      short loc_14000BF3D
0x14000bf19  mov     eax, [rcx+2Ch]
0x14000bf1c  test    r13b, al
0x14000bf1f  jz      short loc_14000BF3D
0x14000bf21  cmp     byte ptr [rcx+29h], 4
0x14000bf25  jb      short loc_14000BF3D
0x14000bf27  mov     rcx, [rcx+18h]
0x14000bf2b  mov     edx, 63h ; 'c'
0x14000bf30  mov     r9, rbx
0x14000bf33  mov     [rsp+78h+var_58], rbp
0x14000bf38  call    WPP_SF_qq
0x14000bf3d  xor     edx, edx
0x14000bf3f  mov     rcx, rbp
0x14000bf42  call    KmclpPauseChannel
0x14000bf47  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf4e  cmp     rcx, r12
0x14000bf51  jz      short loc_14000BF77
0x14000bf53  mov     eax, [rcx+2Ch]
0x14000bf56  test    r13b, al
0x14000bf59  jz      short loc_14000BF77
0x14000bf5b  cmp     byte ptr [rcx+29h], 4
0x14000bf5f  jb      short loc_14000BF77
0x14000bf61  mov     rcx, [rcx+18h]
0x14000bf65  mov     edx, 64h ; 'd'
0x14000bf6a  mov     r9, rbx
0x14000bf6d  mov     [rsp+78h+var_58], rbp
0x14000bf72  call    WPP_SF_qq
0x14000bf77  mov     r14, [r14]
0x14000bf7a  cmp     r14, r15
0x14000bf7d  jnz     loc_14000BE87
0x14000bf83  lea     r12, [rbx+0C68h]
0x14000bf8a  mov     rcx, r12; FastMutex
0x14000bf8d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000bf94  nop     dword ptr [rax+rax+00h]
0x14000bf99  call    cs:__imp_KeLeaveCriticalRegion
0x14000bfa0  nop     dword ptr [rax+rax+00h]
0x14000bfa5  cmp     [rbx+6C1h], dil
0x14000bfac  jz      short loc_14000BFB7
0x14000bfae  cmp     [rbx+850h], rdi
0x14000bfb5  jz      short loc_14000BFCA
0x14000bfb7  mov     rax, [rbx+9C8h]
0x14000bfbe  mov     rcx, [rbx+940h]
0x14000bfc5  call    _guard_dispatch_icall
0x14000bfca  cmp     [rbx+6C1h], dil
0x14000bfd1  jnz     short loc_14000C048
0x14000bfd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfda  lea     r12, WPP_GLOBAL_Control
0x14000bfe1  cmp     rcx, r12
0x14000bfe4  jz      short loc_14000C00C
0x14000bfe6  mov     eax, [rcx+2Ch]
0x14000bfe9  test    r13b, al
0x14000bfec  jz      short loc_14000C00C
0x14000bfee  cmp     byte ptr [rcx+29h], 4
0x14000bff2  jb      short loc_14000C00C
0x14000bff4  mov     rcx, [rcx+18h]
0x14000bff8  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000bfff  mov     edx, 65h ; 'e'
0x14000c004  mov     r9, rbx
0x14000c007  call    WPP_SF_q
0x14000c00c  mov     rcx, rbx
0x14000c00f  call    InPauseQueue
0x14000c014  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c01b  cmp     rcx, r12
0x14000c01e  jz      short loc_14000C081
0x14000c020  mov     eax, [rcx+2Ch]
0x14000c023  test    r13b, al
0x14000c026  jz      short loc_14000C04F
0x14000c028  cmp     byte ptr [rcx+29h], 4
0x14000c02c  jb      short loc_14000C04F
0x14000c02e  mov     rcx, [rcx+18h]
0x14000c032  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000c039  mov     edx, 66h ; 'f'
0x14000c03e  mov     r9, rbx
0x14000c041  call    WPP_SF_q
0x14000c046  jmp     short loc_14000C04F
0x14000c048  lea     r12, WPP_GLOBAL_Control
0x14000c04f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c056  cmp     rcx, r12
0x14000c059  jz      short loc_14000C081
0x14000c05b  mov     eax, [rcx+2Ch]
0x14000c05e  test    r13b, al
0x14000c061  jz      short loc_14000C081
0x14000c063  cmp     byte ptr [rcx+29h], 4
0x14000c067  jb      short loc_14000C081
0x14000c069  mov     rcx, [rcx+18h]
0x14000c06d  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000c074  mov     edx, 67h ; 'g'
0x14000c079  mov     r9, rbx
0x14000c07c  call    WPP_SF_q
0x14000c081  mov     rcx, rbx
0x14000c084  cmp     [rbx+7E8h], dil
0x14000c08b  jz      short loc_14000C0A2
0x14000c08d  mov     rax, [rbx+810h]
0x14000c094  mov     rdx, [rbx+7F8h]
0x14000c09b  call    _guard_dispatch_icall
0x14000c0a0  jmp     short loc_14000C0AE
  ... truncated ...
```
