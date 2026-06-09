# NvmeControllerCompleteAllPendingRequests

- ea: `0x14010d0cc`
- end: `0x14010d8ed`
- name: `NvmeControllerCompleteAllPendingRequests`
- size: `2081`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14010d8f4`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14010d0cc`
- `0x1401346e0`
- `0x14014b400`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14010d8bb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14010d8bb`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14010d1b4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14010d4e5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14010d1b4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14010d4e5`
- `ntoskrnl!IofCompleteRequest` at `0x14010d454`
- `ntoskrnl!IofCompleteRequest` at `0x14010d7c0`
- `ntoskrnl!IofCompleteRequest` at `0x14010d454`
- `ntoskrnl!IofCompleteRequest` at `0x14010d7c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14010d126`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14010d126`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14010d831`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14010d831`

## pseudocode

```c
PSLIST_ENTRY __fastcall NvmeControllerCompleteAllPendingRequests(union _SLIST_HEADER *a1, int a2)
{
  char *v2; // rdi
  int v3; // r15d
  union _SLIST_HEADER *v4; // rsi
  unsigned int *v5; // rdi
  union _SLIST_HEADER *Alignment; // r14
  union _SLIST_HEADER *v7; // rax
  unsigned int v8; // r13d
  __int64 v9; // rbx
  bool v10; // zf
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  int *v13; // rax
  int v14; // ecx
  __int64 *v15; // rdx
  _BYTE *v16; // rdx
  unsigned int v17; // r14d
  unsigned __int8 v18; // r11
  char *v19; // rdi
  char v20; // r12
  _BYTE *v21; // r9
  __int64 v22; // rsi
  char v23; // r15
  unsigned __int64 v24; // r10
  __int64 v25; // r8
  int v26; // ecx
  char v27; // cl
  char v28; // di
  char v29; // r8
  char v30; // r10
  _BYTE *v31; // rax
  unsigned int v32; // eax
  char v33; // al
  unsigned int v34; // r13d
  __int64 v35; // rbx
  unsigned __int64 v36; // rcx
  __int64 v37; // rdx
  int *v38; // rax
  int v39; // ecx
  __int64 *v40; // rdx
  _BYTE *v41; // rdx
  unsigned int v42; // r14d
  unsigned __int8 v43; // r11
  char *v44; // rdi
  char v45; // r12
  _BYTE *v46; // r9
  __int64 v47; // rsi
  char v48; // r15
  unsigned __int64 v49; // r10
  __int64 v50; // r8
  int v51; // ecx
  char v52; // cl
  char v53; // di
  char v54; // r8
  char v55; // r10
  _BYTE *v56; // rax
  unsigned int v57; // eax
  char v58; // al
  unsigned int v59; // ebx
  __int64 v60; // rax
  PSLIST_ENTRY v61; // rdx
  _SLIST_ENTRY *Next; // rax
  _SLIST_ENTRY *v63; // rax
  PSLIST_ENTRY result; // rax
  union _SLIST_HEADER *v66; // [rsp+68h] [rbp-51h]
  union _SLIST_HEADER *v67; // [rsp+70h] [rbp-49h]
  unsigned int *v68; // [rsp+78h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-31h] BYREF
  __int128 v71; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v72; // [rsp+B0h] [rbp-9h] BYREF

  v2 = (char *)g_CpuInfo;
  v3 = a2;
  v4 = a1;
  v72 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock(&a1[39].Region, &LockHandle);
  v5 = (unsigned int *)(v2 + 8);
  Alignment = (union _SLIST_HEADER *)v4[40].Alignment;
  v67 = v4 + 40;
  v66 = Alignment;
  v68 = v5;
  if ( Alignment != &v4[40] )
  {
    v7 = v4 + 40;
    while ( 1 )
    {
      v8 = 0;
      if ( !*v5 )
        goto LABEL_146;
      do
      {
        v9 = StorPopRequestFromDeviceQueue(Alignment[14].Region, v8);
        if ( !v9 )
          goto LABEL_70;
        do
        {
          v10 = StorEtwLoggingEnabled == 0;
          *(_QWORD *)(v9 + 56) = 0;
          *(_BYTE *)(v9 + 141) = -84;
          *(_DWORD *)(v9 + 48) = v3;
          if ( v10 )
            goto LABEL_68;
          v71 = 0;
          IoGetActivityIdIrp(v9, &v71);
          v12 = *(_QWORD *)(v9 + 184);
          if ( *(_BYTE *)v12 == 14 )
          {
            if ( (byte_140177432 & 8) == 0 )
              goto LABEL_68;
            v15 = EventNonReadWriteRequestComplete;
            goto LABEL_18;
          }
          if ( *(_BYTE *)v12 != 15 )
          {
            if ( *(_BYTE *)v12 != 27 )
              goto LABEL_68;
            if ( *(_BYTE *)(v12 + 1) == 7 && !*(_DWORD *)(v12 + 8) )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                v13 = *(int **)(v9 + 56);
                if ( v13 )
                  v14 = *v13;
                else
                  v14 = 0;
                McTemplateK0pqd_EtwWriteTransfer(v14, v12, (unsigned int)&v71, v9, v14, *(_DWORD *)(v9 + 48));
              }
              goto LABEL_68;
            }
            if ( (byte_140177432 & 0x20) == 0 )
              goto LABEL_68;
            v15 = EventPnpRequestComplete;
LABEL_18:
            McTemplateK0pd_EtwWriteTransfer(v11, v15, &v71, v9, *(_DWORD *)(v9 + 48));
            goto LABEL_68;
          }
          if ( byte_140177431 >= 0 )
            goto LABEL_68;
          v16 = *(_BYTE **)(v12 + 8);
          if ( v16[2] == 40 )
          {
            if ( *((_DWORD *)v16 + 5) )
              goto LABEL_68;
            v17 = *((_DWORD *)v16 + 14);
            if ( !v17 )
            {
              Alignment = v66;
              goto LABEL_68;
            }
            v18 = 0;
            v19 = 0;
            v20 = 0;
            v21 = 0;
            v22 = 0;
            v23 = 0;
            while ( 1 )
            {
              v11 = *(unsigned int *)&v16[4 * v22 + 120];
              if ( (unsigned int)v11 >= 0x80 )
              {
                v24 = *((unsigned int *)v16 + 4);
                if ( (unsigned int)v11 < (unsigned int)v24 )
                {
                  v25 = (unsigned int)v11;
                  v26 = *(_DWORD *)&v16[v11] - 64;
                  if ( v26 )
                  {
                    LODWORD(v11) = v26 - 1;
                    if ( (_DWORD)v11 )
                    {
                      if ( (_DWORD)v11 == 1 )
                      {
                        LODWORD(v11) = v25 + 40;
                        if ( v25 + 40 <= v24 )
                        {
                          if ( *(_DWORD *)&v16[v25 + 12] )
                            v19 = &v16[v25 + 32];
                          v21 = *(_BYTE **)&v16[v25 + 24];
LABEL_44:
                          v18 = v16[v25 + 9];
                          v20 = v16[v25 + 8];
LABEL_45:
                          Alignment = v66;
                          if ( v19 )
                          {
                            v27 = *v19;
                            goto LABEL_48;
                          }
                          goto LABEL_68;
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v11) = v25 + 56;
                      if ( v25 + 56 <= v24 )
                      {
                        v23 = 1;
                        if ( v16[v25 + 10] )
                          v19 = &v16[v25 + 24];
                        v20 = v16[v25 + 8];
                        v21 = *(_BYTE **)&v16[v25 + 16];
                        v18 = v16[v25 + 9];
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v11) = v25 + 40;
                    if ( v25 + 40 <= v24 )
                    {
                      if ( v16[v25 + 10] )
                        v19 = &v16[v25 + 24];
                      v21 = *(_BYTE **)&v16[v25 + 16];
                      goto LABEL_44;
                    }
                  }
                  if ( v23 )
                    goto LABEL_45;
                }
              }
              v22 = (unsigned int)(v22 + 1);
              if ( (unsigned int)v22 >= v17 )
                goto LABEL_45;
            }
          }
          v27 = v16[72];
          v21 = (_BYTE *)*((_QWORD *)v16 + 4);
          v18 = v16[11];
          v20 = v16[4];
          if ( v16[2] )
            goto LABEL_68;
LABEL_48:
          LOBYTE(v11) = v27 - 8;
          if ( (v11 & 0x5D) == 0 )
          {
            v28 = v16[3];
            if ( v28 == 1 || !v21 || !v18 )
              goto LABEL_66;
            v29 = 0;
            v30 = 0;
            LOBYTE(v16) = 0;
            v11 = (unsigned __int64)&v21[v18];
            v31 = v21 + 8;
            if ( (unsigned __int8)((*v21 & 0x7F) - 114) <= 1u )
            {
              if ( (unsigned __int64)v31 <= v11 )
              {
                v30 = v21[2];
                v29 = v21[1] & 0xF;
                LOBYTE(v16) = v21[3];
                goto LABEL_63;
              }
            }
            else if ( (unsigned __int64)v31 <= v11 )
            {
              v16 = v21 + 13;
              v29 = v21[2] & 0xF;
              v32 = v18;
              if ( (unsigned int)(unsigned __int8)v21[7] + 8 <= v18 )
                v32 = (unsigned __int8)v21[7] + 8;
              v11 = (unsigned __int64)&v21[v32];
              if ( (unsigned __int64)v16 <= v11 )
                v30 = v21[12];
              if ( (unsigned __int64)(v21 + 14) > v11 )
                LOBYTE(v16) = 0;
              else
                LOBYTE(v16) = *v16;
LABEL_63:
              v33 = 1;
LABEL_65:
              if ( !v33 )
              {
LABEL_66:
                v29 = 0;
                v30 = 0;
                LOBYTE(v16) = 0;
              }
              McTemplateK0pduuuuup_EtwWriteTransfer(
                v11,
                (_DWORD)v16,
                (unsigned int)&v71,
                v9,
                *(_DWORD *)(v9 + 48),
                v28,
                v20,
                v29,
                v30,
                (char)v16,
                v9);
              goto LABEL_68;
            }
            v33 = 0;
            goto LABEL_65;
          }
LABEL_68:
          IofCompleteRequest((PIRP)v9, 0);
          v3 = a2;
          v9 = StorPopRequestFromDeviceQueue(Alignment[14].Region, v8);
        }
        while ( v9 );
        v5 = v68;
LABEL_70:
        ++v8;
      }
      while ( v8 < *v5 );
      v34 = 0;
      if ( !*v5 )
        goto LABEL_145;
      while ( 2 )
      {
        v35 = StorPopRequestFromDeviceQueue(Alignment[15].Alignment, v34);
        if ( !v35 )
          goto LABEL_144;
        while ( 2 )
        {
          v10 = StorEtwLoggingEnabled == 0;
          *(_QWORD *)(v35 + 56) = 0;
          *(_BYTE *)(v35 + 141) = -84;
          *(_DWORD *)(v35 + 48) = v3;
          if ( v10 )
            goto LABEL_142;
          v71 = 0;
          IoGetActivityIdIrp(v35, &v71);
          v37 = *(_QWORD *)(v35 + 184);
          if ( *(_BYTE *)v37 == 14 )
          {
            if ( (byte_140177432 & 8) == 0 )
              goto LABEL_142;
            v40 = EventNonReadWriteRequestComplete;
            goto LABEL_89;
          }
          if ( *(_BYTE *)v37 != 15 )
          {
            if ( *(_BYTE *)v37 != 27 )
              goto LABEL_142;
            if ( *(_BYTE *)(v37 + 1) == 7 && !*(_DWORD *)(v37 + 8) )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                v38 = *(int **)(v35 + 56);
                if ( v38 )
                  v39 = *v38;
                else
                  v39 = 0;
                McTemplateK0pqd_EtwWriteTransfer(v39, v37, (unsigned int)&v71, v35, v39, *(_DWORD *)(v35 + 48));
              }
              goto LABEL_142;
            }
            if ( (byte_140177432 & 0x20) == 0 )
              goto LABEL_142;
            v40 = EventPnpRequestComplete;
LABEL_89:
            McTemplateK0pd_EtwWriteTransfer(v36, v40, &v71, v35, *(_DWORD *)(v35 + 48));
            goto LABEL_142;
          }
          if ( byte_140177431 >= 0 )
            goto LABEL_142;
          v41 = *(_BYTE **)(v37 + 8);
          if ( v41[2] == 40 )
          {
            if ( *((_DWORD *)v41 + 5) )
              goto LABEL_142;
            v42 = *((_DWORD *)v41 + 14);
            if ( !v42 )
            {
              Alignment = v66;
              goto LABEL_142;
            }
            v43 = 0;
            v44 = 0;
            v45 = 0;
            v46 = 0;
            v47 = 0;
            v48 = 0;
            while ( 1 )
            {
              v36 = *(unsigned int *)&v41[4 * v47 + 120];
              if ( (unsigned int)v36 >= 0x80 )
              {
                v49 = *((unsigned int *)v41 + 4);
                if ( (unsigned int)v36 < (unsigned int)v49 )
                {
                  v50 = (unsigned int)v36;
                  v51 = *(_DWORD *)&v41[v36] - 64;
                  if ( v51 )
                  {
                    LODWORD(v36) = v51 - 1;
                    if ( (_DWORD)v36 )
                    {
                      if ( (_DWORD)v36 == 1 )
                      {
                        LODWORD(v36) = v50 + 40;
                        if ( v50 + 40 <= v49 )
                        {
                          if ( *(_DWORD *)&v41[v50 + 12] )
                            v44 = &v41[v50 + 32];
                          v46 = *(_BYTE **)&v41[v50 + 24];
                          goto LABEL_115;
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v36) = v50 + 56;
                      if ( v50 + 56 <= v49 )
                      {
                        v48 = 1;
                        if ( v41[v50 + 10] )
                          v44 = &v41[v50 + 24];
                        v45 = v41[v50 + 8];
                        v46 = *(_BYTE **)&v41[v50 + 16];
                        v43 = v41[v50 + 9];
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v36) = v50 + 40;
                    if ( v50 + 40 <= v49 )
                    {
                      if ( v41[v50 + 10] )
                        v44 = &v41[v50 + 24];
                      v46 = *(_BYTE **)&v41[v50 + 16];
LABEL_115:
                      v43 = v41[v50 + 9];
                      v45 = v41[v50 + 8];
LABEL_116:
                      Alignment = v66;
                      if ( v44 )
                      {
                        v52 = *v44;
                        goto LABEL_119;
                      }
                      goto LABEL_142;
                    }
                  }
                  if ( v48 )
                    goto LABEL_116;
                }
              }
              v47 = (unsigned int)(v47 + 1);
              if ( (unsigned int)v47 >= v42 )
                goto LABEL_116;
            }
          }
          v52 = v41[72];
          v46 = (_BYTE *)*((_QWORD *)v41 + 4);
          v43 = v41[11];
          v45 = v41[4];
          if ( v41[2] )
            goto LABEL_142;
LABEL_119:
          LOBYTE(v36) = v52 - 8;
          if ( (v36 & 0x5D) == 0 )
          {
            v53 = v41[3];
            if ( v53 == 1 || !v46 || !v43 )
              goto LABEL_137;
            v54 = 0;
            v55 = 0;
            LOBYTE(v41) = 0;
            v36 = (unsigned __int64)&v46[v43];
            v56 = v46 + 8;
            if ( (unsigned __int8)((*v46 & 0x7F) - 114) <= 1u )
            {
              if ( (unsigned __int64)v56 <= v36 )
              {
                v55 = v46[2];
                v54 = v46[1] & 0xF;
                LOBYTE(v41) = v46[3];
                goto LABEL_134;
              }
            }
            else if ( (unsigned __int64)v56 <= v36 )
            {
              v41 = v46 + 13;
              v54 = v46[2] & 0xF;
              v57 = v43;
              if ( (unsigned int)(unsigned __int8)v46[7] + 8 <= v43 )
                v57 = (unsigned __int8)v46[7] + 8;
              v36 = (unsigned __int64)&v46[v57];
              if ( (unsigned __int64)v41 <= v36 )
                v55 = v46[12];
              if ( (unsigned __int64)(v46 + 14) > v36 )
                LOBYTE(v41) = 0;
              else
                LOBYTE(v41) = *v41;
LABEL_134:
              v58 = 1;
LABEL_136:
              if ( !v58 )
              {
LABEL_137:
                v54 = 0;
                v55 = 0;
                LOBYTE(v41) = 0;
              }
              McTemplateK0pduuuuup_EtwWriteTransfer(
                v36,
                (_DWORD)v41,
                (unsigned int)&v71,
                v35,
                *(_DWORD *)(v35 + 48),
                v53,
                v45,
                v54,
                v55,
                (char)v41,
                v35);
              goto LABEL_142;
            }
            v58 = 0;
            goto LABEL_136;
          }
LABEL_142:
          IofCompleteRequest((PIRP)v35, 0);
          v3 = a2;
          v35 = StorPopRequestFromDeviceQueue(Alignment[15].Alignment, v34);
          if ( v35 )
            continue;
          break;
        }
        v5 = v68;
LABEL_144:
        v3 = a2;
        if ( ++v34 < *v5 )
          continue;
        break;
      }
LABEL_145:
      v7 = v67;
LABEL_146:
      Alignment = (union _SLIST_HEADER *)Alignment->Alignment;
      v3 = a2;
      v66 = Alignment;
      if ( Alignment == v7 )
      {
        v4 = a1;
        break;
      }
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v59 = 0;
  for ( HIWORD(v72) = HIWORD(v72) & 0xF001 | 0xE; v59 < *v5; ++v59 )
  {
    while ( 1 )
    {
      v60 = StorPopRequestFromDeviceQueue(v4[64].Alignment, v59);
      if ( !v60 )
        break;
      (*(void (__fastcall **)(union _SLIST_HEADER *, __int64, __int128 *))(*(_QWORD *)v60 + 4192LL))(v4, v60, &v72);
    }
  }
  while ( 1 )
  {
    result = ExpInterlockedPopEntrySList(v4 + 75);
    if ( !result )
      break;
    v61 = result - 3;
    Next = result[-3].Next;
    if ( Next )
    {
      v63 = Next[262].Next;
      if ( v63 )
        ((void (__fastcall *)(union _SLIST_HEADER *, PSLIST_ENTRY, __int128 *))v63)(v4, v61, &v72);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14010d0cc  push    rbp
0x14010d0ce  push    rbx
0x14010d0cf  push    rsi
0x14010d0d0  push    rdi
0x14010d0d1  push    r12
0x14010d0d3  push    r13
0x14010d0d5  push    r14
0x14010d0d7  push    r15
0x14010d0d9  lea     rbp, [rsp-1Fh]
0x14010d0de  sub     rsp, 0D8h
0x14010d0e5  mov     rax, cs:__security_cookie
0x14010d0ec  xor     rax, rsp
0x14010d0ef  mov     [rbp+57h+var_50], rax
0x14010d0f3  mov     rdi, cs:g_CpuInfo
0x14010d0fa  mov     r15d, edx
0x14010d0fd  mov     [rbp+57h+var_B0], edx
0x14010d100  mov     rsi, rcx
0x14010d103  mov     [rbp+57h+var_90], rcx
0x14010d107  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14010d10b  xorps   xmm0, xmm0
0x14010d10e  xorps   xmm1, xmm1
0x14010d111  xor     eax, eax
0x14010d113  add     rcx, 278h; SpinLock
0x14010d11a  movups  [rbp+57h+var_60], xmm0
0x14010d11e  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14010d122  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm1
0x14010d126  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14010d12d  nop     dword ptr [rax+rax+00h]
0x14010d132  lea     r13, [rsi+280h]
0x14010d139  add     rdi, 8
0x14010d13d  mov     r14, [r13+0]
0x14010d141  mov     r12d, 0Eh
0x14010d147  mov     [rbp+57h+var_A0], r13
0x14010d14b  mov     [rbp+57h+var_A8], r14
0x14010d14f  mov     [rbp+57h+var_98], rdi
0x14010d153  cmp     r14, r13
0x14010d156  jz      loc_14010D82D
0x14010d15c  mov     rax, r13
0x14010d15f  xor     r13d, r13d
0x14010d162  cmp     [rdi], r13d
0x14010d165  jbe     loc_14010D80F
0x14010d16b  mov     rcx, [r14+0E8h]
0x14010d172  mov     edx, r13d
0x14010d175  call    StorPopRequestFromDeviceQueue
0x14010d17a  mov     rbx, rax
0x14010d17d  test    rax, rax
0x14010d180  jz      loc_14010D483
0x14010d186  cmp     cs:StorEtwLoggingEnabled, 0
0x14010d18d  mov     qword ptr [rbx+38h], 0
0x14010d195  mov     byte ptr [rbx+8Dh], 0ACh
0x14010d19c  mov     [rbx+30h], r15d
0x14010d1a0  jz      loc_14010D44F
0x14010d1a6  xorps   xmm0, xmm0
0x14010d1a9  lea     rdx, [rbp+57h+var_70]
0x14010d1ad  mov     rcx, rbx
0x14010d1b0  movups  [rbp+57h+var_70], xmm0
0x14010d1b4  call    cs:__imp_IoGetActivityIdIrp
0x14010d1bb  nop     dword ptr [rax+rax+00h]
0x14010d1c0  mov     rdx, [rbx+0B8h]
0x14010d1c7  movzx   eax, byte ptr [rdx]
0x14010d1ca  sub     eax, r12d
0x14010d1cd  jz      loc_14010D53C
0x14010d1d3  sub     eax, 1
0x14010d1d6  jz      short loc_14010D251
0x14010d1d8  cmp     eax, 0Ch
0x14010d1db  jnz     loc_14010D44F
0x14010d1e1  cmp     byte ptr [rdx+1], 7
0x14010d1e5  jnz     short loc_14010D225
0x14010d1e7  cmp     dword ptr [rdx+8], 0
0x14010d1eb  jnz     short loc_14010D225
0x14010d1ed  test    cs:byte_140177432, 40h
0x14010d1f4  jz      loc_14010D44F
0x14010d1fa  mov     rax, [rbx+38h]
0x14010d1fe  test    rax, rax
0x14010d201  jz      short loc_14010D207
0x14010d203  mov     ecx, [rax]
0x14010d205  jmp     short loc_14010D209
0x14010d207  xor     ecx, ecx
0x14010d209  mov     eax, [rbx+30h]
0x14010d20c  lea     r8, [rbp+57h+var_70]
0x14010d210  mov     [rsp+110h+var_E8], eax
0x14010d214  mov     r9, rbx
0x14010d217  mov     [rsp+110h+var_F0], ecx
0x14010d21b  call    McTemplateK0pqd_EtwWriteTransfer
0x14010d220  jmp     loc_14010D44F
0x14010d225  test    cs:byte_140177432, 20h
0x14010d22c  jz      loc_14010D44F
0x14010d232  lea     rdx, EventPnpRequestComplete
0x14010d239  mov     eax, [rbx+30h]
0x14010d23c  lea     r8, [rbp+57h+var_70]
0x14010d240  mov     r9, rbx
0x14010d243  mov     [rsp+110h+var_F0], eax
0x14010d247  call    McTemplateK0pd_EtwWriteTransfer
0x14010d24c  jmp     loc_14010D44F
0x14010d251  cmp     cs:byte_140177431, 0
0x14010d258  jge     loc_14010D44F
0x14010d25e  mov     rdx, [rdx+8]
0x14010d262  movzx   eax, byte ptr [rdx+2]
0x14010d266  cmp     al, 28h ; '('
0x14010d268  jnz     loc_14010D354
0x14010d26e  cmp     dword ptr [rdx+14h], 0
0x14010d272  jnz     loc_14010D44F
0x14010d278  mov     r14d, [rdx+38h]
0x14010d27c  test    r14d, r14d
0x14010d27f  jz      loc_14010D555
0x14010d285  xor     r11b, r11b
0x14010d288  xor     edi, edi
0x14010d28a  xor     r12b, r12b
0x14010d28d  xor     r9d, r9d
0x14010d290  xor     esi, esi
0x14010d292  xor     r15b, r15b
0x14010d295  mov     ecx, [rdx+rsi*4+78h]
0x14010d299  cmp     ecx, 80h
0x14010d29f  jb      short loc_14010D318
0x14010d2a1  mov     r10d, [rdx+10h]
0x14010d2a5  cmp     ecx, r10d
0x14010d2a8  jnb     short loc_14010D318
0x14010d2aa  mov     r8d, ecx
0x14010d2ad  mov     ecx, [rcx+rdx]
0x14010d2b0  sub     ecx, 40h ; '@'
0x14010d2b3  jz      short loc_14010D30A
0x14010d2b5  sub     ecx, 1
0x14010d2b8  jz      short loc_14010D2DE
0x14010d2ba  cmp     ecx, 1
0x14010d2bd  jnz     short loc_14010D313
0x14010d2bf  lea     rcx, [r8+28h]
0x14010d2c3  cmp     rcx, r10
0x14010d2c6  ja      short loc_14010D313
0x14010d2c8  cmp     dword ptr [r8+rdx+0Ch], 0
0x14010d2ce  jbe     short loc_14010D2D7
0x14010d2d0  lea     rdi, [rdx+20h]
0x14010d2d4  add     rdi, r8
0x14010d2d7  mov     r9, [r8+rdx+18h]
0x14010d2dc  jmp     short loc_14010D339
0x14010d2de  lea     rcx, [r8+38h]
0x14010d2e2  cmp     rcx, r10
0x14010d2e5  ja      short loc_14010D313
0x14010d2e7  cmp     byte ptr [r8+rdx+0Ah], 0
0x14010d2ed  mov     r15b, 1
0x14010d2f0  jbe     short loc_14010D2F9
0x14010d2f2  lea     rdi, [rdx+18h]
0x14010d2f6  add     rdi, r8
0x14010d2f9  mov     r12b, [r8+rdx+8]
0x14010d2fe  mov     r9, [r8+rdx+10h]
0x14010d303  mov     r11b, [r8+rdx+9]
0x14010d308  jmp     short loc_14010D313
0x14010d30a  lea     rcx, [r8+28h]
0x14010d30e  cmp     rcx, r10
0x14010d311  jbe     short loc_14010D325
0x14010d313  test    r15b, r15b
0x14010d316  jnz     short loc_14010D343
0x14010d318  inc     esi
0x14010d31a  cmp     esi, r14d
0x14010d31d  jb      loc_14010D295
0x14010d323  jmp     short loc_14010D343
0x14010d325  cmp     byte ptr [r8+rdx+0Ah], 0
0x14010d32b  jbe     short loc_14010D334
0x14010d32d  lea     rdi, [rdx+18h]
0x14010d331  add     rdi, r8
0x14010d334  mov     r9, [r8+rdx+10h]
0x14010d339  mov     r11b, [r8+rdx+9]
0x14010d33e  mov     r12b, [r8+rdx+8]
0x14010d343  mov     r14, [rbp+57h+var_A8]
0x14010d347  test    rdi, rdi
0x14010d34a  jz      loc_14010D449
0x14010d350  mov     cl, [rdi]
0x14010d352  jmp     short loc_14010D36B
0x14010d354  mov     cl, [rdx+48h]
0x14010d357  mov     r9, [rdx+20h]
0x14010d35b  mov     r11b, [rdx+0Bh]
0x14010d35f  mov     r12b, [rdx+4]
0x14010d363  test    eax, eax
0x14010d365  jnz     loc_14010D449
0x14010d36b  sub     cl, 8
0x14010d36e  test    cl, 5Dh
0x14010d371  jnz     loc_14010D449
0x14010d377  mov     dil, [rdx+3]
0x14010d37b  cmp     dil, 1
0x14010d37f  jz      loc_14010D411
0x14010d385  test    r9, r9
0x14010d388  jz      loc_14010D411
0x14010d38e  test    r11b, r11b
0x14010d391  jz      short loc_14010D411
0x14010d393  mov     al, [r9]
0x14010d396  xor     r8b, r8b
0x14010d399  and     al, 7Fh
0x14010d39b  movzx   ecx, r11b
0x14010d39f  sub     al, 72h ; 'r'
0x14010d3a1  xor     r10b, r10b
0x14010d3a4  xor     dl, dl
0x14010d3a6  add     rcx, r9
0x14010d3a9  cmp     al, 1
0x14010d3ab  lea     rax, [r9+8]
0x14010d3af  jbe     short loc_14010D3F2
0x14010d3b1  cmp     rax, rcx
0x14010d3b4  ja      short loc_14010D40B
0x14010d3b6  movzx   ecx, byte ptr [r9+7]
0x14010d3bb  lea     rdx, [r9+0Dh]
0x14010d3bf  mov     r8b, [r9+2]
0x14010d3c3  add     ecx, 8
0x14010d3c6  and     r8b, 0Fh
0x14010d3ca  movzx   eax, r11b
0x14010d3ce  cmp     ecx, eax
0x14010d3d0  cmovbe  eax, ecx
0x14010d3d3  mov     ecx, eax
0x14010d3d5  add     rcx, r9
0x14010d3d8  cmp     rdx, rcx
0x14010d3db  ja      short loc_14010D3E1
0x14010d3dd  mov     r10b, [r9+0Ch]
0x14010d3e1  lea     rax, [r9+0Eh]
0x14010d3e5  cmp     rax, rcx
0x14010d3e8  ja      short loc_14010D3EE
0x14010d3ea  mov     dl, [rdx]
0x14010d3ec  jmp     short loc_14010D407
0x14010d3ee  xor     dl, dl
0x14010d3f0  jmp     short loc_14010D407
0x14010d3f2  cmp     rax, rcx
0x14010d3f5  ja      short loc_14010D40B
0x14010d3f7  mov     r8b, [r9+1]
0x14010d3fb  mov     r10b, [r9+2]
0x14010d3ff  and     r8b, 0Fh
0x14010d403  mov     dl, [r9+3]
0x14010d407  mov     al, 1
0x14010d409  jmp     short loc_14010D40D
0x14010d40b  xor     al, al
0x14010d40d  test    al, al
0x14010d40f  jnz     short loc_14010D419
0x14010d411  xor     r8b, r8b
0x14010d414  xor     r10b, r10b
0x14010d417  xor     dl, dl
0x14010d419  mov     eax, [rbx+30h]
0x14010d41c  mov     r9, rbx
0x14010d41f  mov     [rsp+110h+var_C0], rbx
0x14010d424  mov     [rsp+110h+var_C8], dl
0x14010d428  mov     [rsp+110h+var_D0], r10b
0x14010d42d  mov     [rsp+110h+var_D8], r8b
0x14010d432  lea     r8, [rbp+57h+var_70]
0x14010d436  mov     [rsp+110h+var_E0], r12b
0x14010d43b  mov     byte ptr [rsp+110h+var_E8], dil
0x14010d440  mov     [rsp+110h+var_F0], eax
0x14010d444  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x14010d449  mov     r12d, 0Eh
0x14010d44f  xor     edx, edx; PriorityBoost
0x14010d451  mov     rcx, rbx; Irp
0x14010d454  call    cs:__imp_IofCompleteRequest
0x14010d45b  nop     dword ptr [rax+rax+00h]
0x14010d460  mov     rcx, [r14+0E8h]
0x14010d467  mov     edx, r13d
0x14010d46a  call    StorPopRequestFromDeviceQueue
0x14010d46f  mov     r15d, [rbp+57h+var_B0]
0x14010d473  mov     rbx, rax
0x14010d476  test    rax, rax
0x14010d479  jnz     loc_14010D186
0x14010d47f  mov     rdi, [rbp+57h+var_98]
0x14010d483  mov     eax, [rdi]
0x14010d485  inc     r13d
0x14010d488  cmp     r13d, eax
0x14010d48b  jb      loc_14010D16B
0x14010d491  xor     r13d, r13d
0x14010d494  test    eax, eax
0x14010d496  jz      loc_14010D80B
0x14010d49c  mov     rcx, [r14+0F0h]
0x14010d4a3  mov     edx, r13d
0x14010d4a6  call    StorPopRequestFromDeviceQueue
0x14010d4ab  mov     rbx, rax
0x14010d4ae  test    rax, rax
0x14010d4b1  jz      loc_14010D7F5
0x14010d4b7  cmp     cs:StorEtwLoggingEnabled, 0
0x14010d4be  mov     qword ptr [rbx+38h], 0
0x14010d4c6  mov     byte ptr [rbx+8Dh], 0ACh
0x14010d4cd  mov     [rbx+30h], r15d
0x14010d4d1  jz      loc_14010D7BB
0x14010d4d7  xorps   xmm0, xmm0
0x14010d4da  lea     rdx, [rbp+57h+var_70]
0x14010d4de  mov     rcx, rbx
0x14010d4e1  movups  [rbp+57h+var_70], xmm0
0x14010d4e5  call    cs:__imp_IoGetActivityIdIrp
0x14010d4ec  nop     dword ptr [rax+rax+00h]
0x14010d4f1  mov     rdx, [rbx+0B8h]
0x14010d4f8  movzx   eax, byte ptr [rdx]
0x14010d4fb  sub     eax, r12d
0x14010d4fe  jz      loc_14010D7A2
0x14010d504  sub     eax, 1
0x14010d507  jz      loc_14010D5A8
0x14010d50d  cmp     eax, 0Ch
0x14010d510  jnz     loc_14010D7BB
0x14010d516  cmp     byte ptr [rdx+1], 7
0x14010d51a  jnz     short loc_14010D57C
0x14010d51c  cmp     dword ptr [rdx+8], 0
0x14010d520  jnz     short loc_14010D57C
0x14010d522  test    cs:byte_140177432, 40h
0x14010d529  jz      loc_14010D7BB
0x14010d52f  mov     rax, [rbx+38h]
0x14010d533  test    rax, rax
0x14010d536  jz      short loc_14010D55E
0x14010d538  mov     ecx, [rax]
0x14010d53a  jmp     short loc_14010D560
0x14010d53c  test    cs:byte_140177432, 8
0x14010d543  jz      loc_14010D44F
0x14010d549  lea     rdx, EventNonReadWriteRequestComplete
  ... truncated ...
```
