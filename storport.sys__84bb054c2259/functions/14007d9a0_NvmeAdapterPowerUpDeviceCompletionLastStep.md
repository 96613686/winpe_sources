# NvmeAdapterPowerUpDeviceCompletionLastStep

- ea: `0x14007d9a0`
- end: `0x14007df3d`
- name: `NvmeAdapterPowerUpDeviceCompletionLastStep`
- size: `1437`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14007d880`
- `0x14013a9b0`

## callees

- `0x1400331d0`
- `0x140048fac`
- `0x140067e24`
- `0x14006d1c0`
- `0x14006d298`
- `0x14007d9a0`
- `0x1400848c4`
- `0x1400fcdec`
- `0x140100b9c`
- `0x14013bea4`
- `0x14013bf44`
- `0x14013d7c8`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14007de8e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14007de8e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007dd9e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007de47`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007dd9e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007de47`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14007dad1`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14007dad1`
- `ntoskrnl!IofCompleteRequest` at `0x14007dd87`
- `ntoskrnl!IofCompleteRequest` at `0x14007dd87`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14007ddf5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14007df09`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14007ddf5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14007df09`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007da1f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007da1f`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14007dee2`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14007dee2`
- `ntoskrnl!IoReportInterruptActive` at `0x14007da85`
- `ntoskrnl!IoReportInterruptActive` at `0x14007da85`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007da44`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007da44`

## pseudocode

```c
void __fastcall NvmeAdapterPowerUpDeviceCompletionLastStep(__int64 a1, __int64 a2)
{
  int *v2; // r14
  int v3; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  bool v8; // zf
  int v9; // r15d
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  int *v12; // rax
  int v13; // ecx
  __int64 *v14; // rdx
  _BYTE *v15; // rdx
  unsigned int v16; // r12d
  unsigned __int8 v17; // r10
  char *v18; // r11
  _BYTE *v19; // r9
  __int64 v20; // r15
  char v21; // r13
  unsigned __int64 v22; // rbx
  __int64 v23; // r8
  int v24; // ecx
  char v25; // r15
  char v26; // cl
  char v27; // bl
  char v28; // r8
  char v29; // r11
  _BYTE *v30; // rax
  unsigned int v31; // eax
  char v32; // al
  PSLIST_ENTRY v33; // rax
  __int64 v34; // r8
  PSLIST_ENTRY v35; // rbx
  _SLIST_ENTRY *Next; // rcx
  char v37; // al
  __int64 v38; // rdx
  __int64 v39; // rsi
  ULONGLONG *v40; // rbx
  char v41; // [rsp+60h] [rbp-19h]
  int v42; // [rsp+64h] [rbp-15h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-11h] BYREF
  __int128 v44; // [rsp+80h] [rbp+7h] BYREF

  v2 = (int *)(a2 + 48);
  v3 = *(_DWORD *)(a1 + 424);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (v3 & 0x40) != 0 && *v2 >= 0 )
    NvmeAdapterStorMQPowerUpDeviceLastStepA();
  NvmeAdapterUnlock(a1);
  NvmeAdapterRestart(a1);
  v6 = *(_DWORD *)(*(_QWORD *)(a2 + 184) + 24LL);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 168) + 120LL), &LockHandle);
  *(_DWORD *)(*(_QWORD *)(a1 + 168) + 68LL) = v6;
  StorSetDevicePowerState(*(_QWORD *)(a1 + 8), v6);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 168) + 176LL) & 0x200) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 608);
    DWORD2(v44) = 0;
    *(_QWORD *)&v44 = 0;
    LODWORD(v44) = *(_DWORD *)(v7 + 12);
    *((_QWORD *)&v44 + 1) = *(_QWORD *)v7;
    IoReportInterruptActive(&v44);
  }
  if ( *(_DWORD *)(a1 + 92) )
    NvmeUpdateCrashDumpPowerReady(a1);
  v8 = StorEtwLoggingEnabled == 0;
  v9 = *v2;
  v42 = *v2;
  *v2 = *v2;
  *(_BYTE *)(a2 + 141) = -84;
  if ( !v8 )
  {
    v44 = 0;
    IoGetActivityIdIrp(a2, &v44);
    v11 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v11 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_72;
      v14 = EventNonReadWriteRequestComplete;
      goto LABEL_21;
    }
    if ( *(_BYTE *)v11 != 15 )
    {
      if ( *(_BYTE *)v11 != 27 )
        goto LABEL_72;
      if ( *(_BYTE *)(v11 + 1) == 7 && !*(_DWORD *)(v11 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v12 = *(int **)(a2 + 56);
          if ( v12 )
            v13 = *v12;
          else
            v13 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v13, v11, (unsigned int)&v44, a2, v13, *v2);
        }
        goto LABEL_72;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_72;
      v14 = EventPnpRequestComplete;
LABEL_21:
      McTemplateK0pd_EtwWriteTransfer(v10, v14, &v44, a2, *v2);
      goto LABEL_72;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_72;
    v15 = *(_BYTE **)(v11 + 8);
    if ( v15[2] == 40 )
    {
      if ( *((_DWORD *)v15 + 5) )
        goto LABEL_72;
      v16 = *((_DWORD *)v15 + 14);
      if ( !v16 )
        goto LABEL_72;
      v17 = 0;
      v18 = 0;
      v41 = 0;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      do
      {
        v10 = *(unsigned int *)&v15[4 * v20 + 120];
        if ( (unsigned int)v10 >= 0x80 )
        {
          v22 = *((unsigned int *)v15 + 4);
          if ( (unsigned int)v10 < (unsigned int)v22 )
          {
            v23 = (unsigned int)v10;
            v24 = *(_DWORD *)&v15[v10] - 64;
            if ( v24 )
            {
              LODWORD(v10) = v24 - 1;
              if ( (_DWORD)v10 )
              {
                if ( (_DWORD)v10 == 1 )
                {
                  LODWORD(v10) = v23 + 40;
                  if ( v23 + 40 <= v22 )
                  {
                    if ( *(_DWORD *)&v15[v23 + 12] )
                      v18 = &v15[v23 + 32];
                    v19 = *(_BYTE **)&v15[v23 + 24];
LABEL_36:
                    v25 = v15[v23 + 8];
                    v17 = v15[v23 + 9];
                    goto LABEL_45;
                  }
                }
              }
              else
              {
                LODWORD(v10) = v23 + 56;
                if ( v23 + 56 <= v22 )
                {
                  v21 = 1;
                  if ( v15[v23 + 10] )
                    v18 = &v15[v23 + 24];
                  v19 = *(_BYTE **)&v15[v23 + 16];
                  v17 = v15[v23 + 9];
                  v41 = v15[v23 + 8];
                }
              }
            }
            else
            {
              LODWORD(v10) = v23 + 40;
              if ( v23 + 40 <= v22 )
              {
                if ( v15[v23 + 10] )
                  v18 = &v15[v23 + 24];
                v19 = *(_BYTE **)&v15[v23 + 16];
                goto LABEL_36;
              }
            }
            if ( v21 )
              break;
          }
        }
        v20 = (unsigned int)(v20 + 1);
      }
      while ( (unsigned int)v20 < v16 );
      v25 = v41;
LABEL_45:
      if ( !v18 )
        goto LABEL_71;
      v26 = *v18;
    }
    else
    {
      v26 = v15[72];
      v19 = (_BYTE *)*((_QWORD *)v15 + 4);
      v17 = v15[11];
      v25 = v15[4];
      if ( v15[2] )
        goto LABEL_71;
    }
    LOBYTE(v10) = v26 - 8;
    if ( (v10 & 0x5D) == 0 )
    {
      v27 = v15[3];
      if ( v27 == 1 || !v19 || !v17 )
        goto LABEL_69;
      v28 = 0;
      v29 = 0;
      LOBYTE(v15) = 0;
      v10 = (unsigned __int64)&v19[v17];
      v30 = v19 + 8;
      if ( (unsigned __int8)((*v19 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v30 <= v10 )
        {
          v29 = v19[2];
          v28 = v19[1] & 0xF;
          LOBYTE(v15) = v19[3];
LABEL_66:
          v32 = 1;
          goto LABEL_68;
        }
      }
      else if ( (unsigned __int64)v30 <= v10 )
      {
        v15 = v19 + 13;
        v28 = v19[2] & 0xF;
        v31 = v17;
        if ( (unsigned int)(unsigned __int8)v19[7] + 8 <= v17 )
          v31 = (unsigned __int8)v19[7] + 8;
        v10 = (unsigned __int64)&v19[v31];
        if ( (unsigned __int64)v15 <= v10 )
          v29 = v19[12];
        if ( (unsigned __int64)(v19 + 14) > v10 )
          LOBYTE(v15) = 0;
        else
          LOBYTE(v15) = *v15;
        goto LABEL_66;
      }
      v32 = 0;
LABEL_68:
      if ( v32 )
      {
LABEL_70:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v10,
          (_DWORD)v15,
          (unsigned int)&v44,
          a2,
          *v2,
          v27,
          v25,
          v28,
          v29,
          (char)v15,
          a2);
        goto LABEL_71;
      }
LABEL_69:
      v28 = 0;
      v29 = 0;
      LOBYTE(v15) = 0;
      goto LABEL_70;
    }
LABEL_71:
    v9 = v42;
  }
LABEL_72:
  IofCompleteRequest((PIRP)a2, 0);
  v33 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 168) + 96LL));
  if ( v33 )
  {
    do
    {
      v35 = v33 - 9;
      Next = v33[-1].Next;
      v37 = BYTE2(Next[3].Next);
      if ( (v37 & 2) != 0 )
      {
        v38 = *((_QWORD *)&Next[3].Next + 1);
        BYTE2(Next[3].Next) = v37 & 0xFD;
        LOBYTE(v34) = 1;
        *((_QWORD *)&v35[8].Next[3].Next + 1) = 0;
        NvmeNamespaceProcessSetDevicePowerIrp(v35, v38, v34);
        ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&v35[7].Next + 1));
      }
      else if ( (v37 & 1) != 0 )
      {
        BYTE2(Next[3].Next) = v37 & 0xFE;
        NvmeNamespaceIdleState(v35, 0, LOWORD(v35[8].Next[3].Next));
      }
      v33 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 168) + 96LL));
    }
    while ( v33 );
    v9 = v42;
  }
  if ( v9 >= 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 408) + 184LL) & 0x40000000) != 0 )
    {
      v39 = *(_QWORD *)(a1 + 1152);
      v40 = *(ULONGLONG **)(*(_QWORD *)(v39 + 1312) + 40LL);
      *v40 = KeQueryUnbiasedInterruptTime();
      if ( !_InterlockedCompareExchange(
              (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v39 + 1312) + 40LL) + 192LL),
              1,
              0) )
        KeSetCoalescableTimer(
          (PKTIMER)(*(_QWORD *)(*(_QWORD *)(v39 + 1312) + 40LL) + 128LL),
          (LARGE_INTEGER)-50000000LL,
          0x7D0u,
          0x12Cu,
          (PKDPC)(*(_QWORD *)(*(_QWORD *)(v39 + 1312) + 40LL) + 64LL));
    }
    else if ( (*(_DWORD *)(a1 + 424) & 0x40) != 0 )
    {
      NvmeAdapterStorMQPowerUpDeviceLastStepB(a1);
    }
  }
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 160));
}

```

## disassembly

```asm
0x14007d9a0  mov     [rsp-8+arg_10], rbx
0x14007d9a5  push    rbp
0x14007d9a6  push    rsi
0x14007d9a7  push    rdi
0x14007d9a8  push    r12
0x14007d9aa  push    r13
0x14007d9ac  push    r14
0x14007d9ae  push    r15
0x14007d9b0  lea     rbp, [rsp-27h]
0x14007d9b5  sub     rsp, 0A0h
0x14007d9bc  mov     rax, cs:__security_cookie
0x14007d9c3  xor     rax, rsp
0x14007d9c6  mov     [rbp+57h+var_40], rax
0x14007d9ca  xor     eax, eax
0x14007d9cc  lea     r14, [rdx+30h]
0x14007d9d0  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14007d9d4  xorps   xmm0, xmm0
0x14007d9d7  mov     eax, [rcx+1A8h]
0x14007d9dd  mov     rsi, rdx
0x14007d9e0  mov     rdi, rcx
0x14007d9e3  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14007d9e7  test    al, 40h
0x14007d9e9  jz      short loc_14007D9F6
0x14007d9eb  cmp     dword ptr [r14], 0
0x14007d9ef  jl      short loc_14007D9F6
0x14007d9f1  call    NvmeAdapterStorMQPowerUpDeviceLastStepA
0x14007d9f6  mov     rcx, rdi
0x14007d9f9  call    NvmeAdapterUnlock
0x14007d9fe  mov     rcx, rdi
0x14007da01  call    NvmeAdapterRestart
0x14007da06  mov     rax, [rsi+0B8h]
0x14007da0d  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14007da11  mov     rcx, [rdi+0A8h]
0x14007da18  add     rcx, 78h ; 'x'; SpinLock
0x14007da1c  mov     ebx, [rax+18h]
0x14007da1f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14007da26  nop     dword ptr [rax+rax+00h]
0x14007da2b  mov     rax, [rdi+0A8h]
0x14007da32  mov     edx, ebx
0x14007da34  mov     [rax+44h], ebx
0x14007da37  mov     rcx, [rdi+8]
0x14007da3b  call    StorSetDevicePowerState
0x14007da40  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14007da44  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14007da4b  nop     dword ptr [rax+rax+00h]
0x14007da50  mov     rax, [rdi+0A8h]
0x14007da57  test    dword ptr [rax+0B0h], 200h
0x14007da61  jz      short loc_14007DA91
0x14007da63  mov     rcx, [rdi+260h]
0x14007da6a  xor     eax, eax
0x14007da6c  mov     qword ptr [rbp+57h+var_50+4], rax
0x14007da70  mov     [rbp+7], rax
0x14007da74  mov     eax, [rcx+0Ch]
0x14007da77  mov     dword ptr [rbp+57h+var_50], eax
0x14007da7a  mov     rax, [rcx]
0x14007da7d  lea     rcx, [rbp+57h+var_50]
0x14007da81  mov     qword ptr [rbp+57h+var_50+8], rax
0x14007da85  call    cs:__imp_IoReportInterruptActive
0x14007da8c  nop     dword ptr [rax+rax+00h]
0x14007da91  cmp     dword ptr [rdi+5Ch], 0
0x14007da95  jbe     short loc_14007DA9F
0x14007da97  mov     rcx, rdi
0x14007da9a  call    NvmeUpdateCrashDumpPowerReady
0x14007da9f  cmp     cs:StorEtwLoggingEnabled, 0
0x14007daa6  mov     r12d, 1
0x14007daac  mov     r15d, [r14]
0x14007daaf  mov     [rbp+57h+var_6C], r15d
0x14007dab3  mov     [r14], r15d
0x14007dab6  mov     byte ptr [rsi+8Dh], 0ACh
0x14007dabd  jz      loc_14007DD82
0x14007dac3  xorps   xmm0, xmm0
0x14007dac6  lea     rdx, [rbp+57h+var_50]
0x14007daca  mov     rcx, rsi
0x14007dacd  movups  [rbp+57h+var_50], xmm0
0x14007dad1  call    cs:__imp_IoGetActivityIdIrp
0x14007dad8  nop     dword ptr [rax+rax+00h]
0x14007dadd  mov     rdx, [rsi+0B8h]
0x14007dae4  movzx   eax, byte ptr [rdx]
0x14007dae7  sub     eax, 0Eh
0x14007daea  jz      loc_14007DE03
0x14007daf0  sub     eax, r12d
0x14007daf3  jz      short loc_14007DB6E
0x14007daf5  cmp     eax, 0Ch
0x14007daf8  jnz     loc_14007DD82
0x14007dafe  cmp     byte ptr [rdx+1], 7
0x14007db02  jnz     short loc_14007DB42
0x14007db04  cmp     dword ptr [rdx+8], 0
0x14007db08  jnz     short loc_14007DB42
0x14007db0a  test    cs:byte_140177432, 40h
0x14007db11  jz      loc_14007DD82
0x14007db17  mov     rax, [rsi+38h]
0x14007db1b  test    rax, rax
0x14007db1e  jz      short loc_14007DB24
0x14007db20  mov     ecx, [rax]
0x14007db22  jmp     short loc_14007DB26
0x14007db24  xor     ecx, ecx
0x14007db26  mov     eax, [r14]
0x14007db29  lea     r8, [rbp+57h+var_50]
0x14007db2d  mov     [rsp+0D0h+var_A8], eax
0x14007db31  mov     r9, rsi
0x14007db34  mov     dword ptr [rsp+0D0h+Dpc], ecx
0x14007db38  call    McTemplateK0pqd_EtwWriteTransfer
0x14007db3d  jmp     loc_14007DD82
0x14007db42  test    cs:byte_140177432, 20h
0x14007db49  jz      loc_14007DD82
0x14007db4f  lea     rdx, EventPnpRequestComplete
0x14007db56  mov     eax, [r14]
0x14007db59  lea     r8, [rbp+57h+var_50]
0x14007db5d  mov     r9, rsi
0x14007db60  mov     dword ptr [rsp+0D0h+Dpc], eax
0x14007db64  call    McTemplateK0pd_EtwWriteTransfer
0x14007db69  jmp     loc_14007DD82
0x14007db6e  cmp     cs:byte_140177431, 0
0x14007db75  jge     loc_14007DD82
0x14007db7b  mov     rdx, [rdx+8]
0x14007db7f  movzx   eax, byte ptr [rdx+2]
0x14007db83  cmp     al, 28h ; '('
0x14007db85  jnz     loc_14007DC86
0x14007db8b  cmp     dword ptr [rdx+14h], 0
0x14007db8f  jnz     loc_14007DD82
0x14007db95  mov     r12d, [rdx+38h]
0x14007db99  test    r12d, r12d
0x14007db9c  jz      loc_14007DD82
0x14007dba2  xor     al, al
0x14007dba4  xor     r10b, r10b
0x14007dba7  xor     r11d, r11d
0x14007dbaa  mov     [rbp+57h+var_70], al
0x14007dbad  xor     r9d, r9d
0x14007dbb0  xor     r15d, r15d
0x14007dbb3  xor     r13b, r13b
0x14007dbb6  mov     ecx, [rdx+r15*4+78h]
0x14007dbbb  cmp     ecx, 80h
0x14007dbc1  jb      loc_14007DC49
0x14007dbc7  mov     ebx, [rdx+10h]
0x14007dbca  cmp     ecx, ebx
0x14007dbcc  jnb     short loc_14007DC49
0x14007dbce  mov     r8d, ecx
0x14007dbd1  mov     ecx, [rcx+rdx]
0x14007dbd4  sub     ecx, 40h ; '@'
0x14007dbd7  jz      short loc_14007DC3B
0x14007dbd9  sub     ecx, 1
0x14007dbdc  jz      short loc_14007DC0C
0x14007dbde  cmp     ecx, 1
0x14007dbe1  jnz     short loc_14007DC44
0x14007dbe3  lea     rcx, [r8+28h]
0x14007dbe7  cmp     rcx, rbx
0x14007dbea  ja      short loc_14007DC44
0x14007dbec  cmp     dword ptr [r8+rdx+0Ch], 0
0x14007dbf2  jbe     short loc_14007DBFB
0x14007dbf4  lea     r11, [rdx+20h]
0x14007dbf8  add     r11, r8
0x14007dbfb  mov     r9, [r8+rdx+18h]
0x14007dc00  mov     r15b, [r8+rdx+8]
0x14007dc05  mov     r10b, [r8+rdx+9]
0x14007dc0a  jmp     short loc_14007DC59
0x14007dc0c  lea     rcx, [r8+38h]
0x14007dc10  cmp     rcx, rbx
0x14007dc13  ja      short loc_14007DC44
0x14007dc15  cmp     byte ptr [r8+rdx+0Ah], 0
0x14007dc1b  mov     r13b, 1
0x14007dc1e  jbe     short loc_14007DC27
0x14007dc20  lea     r11, [rdx+18h]
0x14007dc24  add     r11, r8
0x14007dc27  mov     al, [r8+rdx+8]
0x14007dc2c  mov     r9, [r8+rdx+10h]
0x14007dc31  mov     r10b, [r8+rdx+9]
0x14007dc36  mov     [rbp+57h+var_70], al
0x14007dc39  jmp     short loc_14007DC44
0x14007dc3b  lea     rcx, [r8+28h]
0x14007dc3f  cmp     rcx, rbx
0x14007dc42  jbe     short loc_14007DC6D
0x14007dc44  test    r13b, r13b
0x14007dc47  jnz     short loc_14007DC55
0x14007dc49  inc     r15d
0x14007dc4c  cmp     r15d, r12d
0x14007dc4f  jb      loc_14007DBB6
0x14007dc55  mov     r15b, [rbp+57h+var_70]
0x14007dc59  test    r11, r11
0x14007dc5c  jz      loc_14007DD7E
0x14007dc62  mov     cl, [r11]
0x14007dc65  mov     r12d, 1
0x14007dc6b  jmp     short loc_14007DC9D
0x14007dc6d  cmp     byte ptr [r8+rdx+0Ah], 0
0x14007dc73  jbe     short loc_14007DC7C
0x14007dc75  lea     r11, [rdx+18h]
0x14007dc79  add     r11, r8
0x14007dc7c  mov     r9, [r8+rdx+10h]
0x14007dc81  jmp     loc_14007DC00
0x14007dc86  mov     cl, [rdx+48h]
0x14007dc89  mov     r9, [rdx+20h]
0x14007dc8d  mov     r10b, [rdx+0Bh]
0x14007dc91  mov     r15b, [rdx+4]
0x14007dc95  test    eax, eax
0x14007dc97  jnz     loc_14007DD7E
0x14007dc9d  sub     cl, 8
0x14007dca0  test    cl, 5Dh
0x14007dca3  jnz     loc_14007DD7E
0x14007dca9  mov     bl, [rdx+3]
0x14007dcac  cmp     bl, r12b
0x14007dcaf  jz      loc_14007DD47
0x14007dcb5  test    r9, r9
0x14007dcb8  jz      loc_14007DD47
0x14007dcbe  test    r10b, r10b
0x14007dcc1  jz      loc_14007DD47
0x14007dcc7  mov     al, [r9]
0x14007dcca  xor     r8b, r8b
0x14007dccd  and     al, 7Fh
0x14007dccf  movzx   ecx, r10b
0x14007dcd3  sub     al, 72h ; 'r'
0x14007dcd5  xor     r11b, r11b
0x14007dcd8  xor     dl, dl
0x14007dcda  add     rcx, r9
0x14007dcdd  cmp     al, r12b
0x14007dce0  lea     rax, [r9+8]
0x14007dce4  jbe     short loc_14007DD27
0x14007dce6  cmp     rax, rcx
0x14007dce9  ja      short loc_14007DD41
0x14007dceb  movzx   ecx, byte ptr [r9+7]
0x14007dcf0  lea     rdx, [r9+0Dh]
0x14007dcf4  mov     r8b, [r9+2]
0x14007dcf8  add     ecx, 8
0x14007dcfb  and     r8b, 0Fh
0x14007dcff  movzx   eax, r10b
0x14007dd03  cmp     ecx, eax
0x14007dd05  cmovbe  eax, ecx
0x14007dd08  mov     ecx, eax
0x14007dd0a  add     rcx, r9
0x14007dd0d  cmp     rdx, rcx
0x14007dd10  ja      short loc_14007DD16
0x14007dd12  mov     r11b, [r9+0Ch]
0x14007dd16  lea     rax, [r9+0Eh]
0x14007dd1a  cmp     rax, rcx
0x14007dd1d  ja      short loc_14007DD23
0x14007dd1f  mov     dl, [rdx]
0x14007dd21  jmp     short loc_14007DD3C
0x14007dd23  xor     dl, dl
0x14007dd25  jmp     short loc_14007DD3C
0x14007dd27  cmp     rax, rcx
0x14007dd2a  ja      short loc_14007DD41
0x14007dd2c  mov     r8b, [r9+1]
0x14007dd30  mov     r11b, [r9+2]
0x14007dd34  and     r8b, 0Fh
0x14007dd38  mov     dl, [r9+3]
0x14007dd3c  mov     al, r12b
0x14007dd3f  jmp     short loc_14007DD43
0x14007dd41  xor     al, al
0x14007dd43  test    al, al
0x14007dd45  jnz     short loc_14007DD4F
0x14007dd47  xor     r8b, r8b
0x14007dd4a  xor     r11b, r11b
0x14007dd4d  xor     dl, dl
0x14007dd4f  mov     eax, [r14]
0x14007dd52  mov     r9, rsi
0x14007dd55  mov     [rsp+0D0h+var_80], rsi
0x14007dd5a  mov     [rsp+0D0h+var_88], dl
0x14007dd5e  mov     [rsp+0D0h+var_90], r11b
0x14007dd63  mov     [rsp+0D0h+var_98], r8b
0x14007dd68  lea     r8, [rbp+57h+var_50]
0x14007dd6c  mov     [rsp+0D0h+var_A0], r15b
0x14007dd71  mov     byte ptr [rsp+0D0h+var_A8], bl
0x14007dd75  mov     dword ptr [rsp+0D0h+Dpc], eax
0x14007dd79  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14007dd7e  mov     r15d, [rbp+57h+var_6C]
0x14007dd82  xor     edx, edx; PriorityBoost
0x14007dd84  mov     rcx, rsi; Irp
0x14007dd87  call    cs:__imp_IofCompleteRequest
0x14007dd8e  nop     dword ptr [rax+rax+00h]
0x14007dd93  mov     rcx, [rdi+0A8h]
0x14007dd9a  add     rcx, 60h ; '`'; ListHead
0x14007dd9e  call    cs:__imp_ExpInterlockedPopEntrySList
0x14007dda5  nop     dword ptr [rax+rax+00h]
0x14007ddaa  test    rax, rax
0x14007ddad  jz      loc_14007DE60
0x14007ddb3  mov     r15d, 1
0x14007ddb9  lea     rbx, [rax-90h]
0x14007ddc0  mov     rcx, [rbx+80h]
0x14007ddc7  mov     al, [rcx+32h]
0x14007ddca  test    al, 2
0x14007ddcc  jz      short loc_14007DE1C
0x14007ddce  mov     rdx, [rcx+38h]
0x14007ddd2  and     al, 0FDh
0x14007ddd4  mov     [rcx+32h], al
0x14007ddd7  mov     r8b, r15b
0x14007ddda  mov     rax, [rbx+80h]
0x14007dde1  mov     rcx, rbx
0x14007dde4  mov     qword ptr [rax+38h], 0
0x14007ddec  call    NvmeNamespaceProcessSetDevicePowerIrp
0x14007ddf1  mov     rcx, [rbx+78h]; RunRefCacheAware
0x14007ddf5  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14007ddfc  nop     dword ptr [rax+rax+00h]
0x14007de01  jmp     short loc_14007DE3C
0x14007de03  test    cs:byte_140177432, 8
0x14007de0a  jz      loc_14007DD82
0x14007de10  lea     rdx, EventNonReadWriteRequestComplete
0x14007de17  jmp     loc_14007DB56
0x14007de1c  test    r15b, al
0x14007de1f  jz      short loc_14007DE3C
0x14007de21  and     al, 0FEh
0x14007de23  xor     edx, edx
0x14007de25  mov     [rcx+32h], al
  ... truncated ...
```
