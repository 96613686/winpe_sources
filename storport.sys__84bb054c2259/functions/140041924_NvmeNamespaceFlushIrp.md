# NvmeNamespaceFlushIrp

- ea: `0x140041924`
- end: `0x1400421ec`
- name: `NvmeNamespaceFlushIrp`
- size: `2248`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400411d0`

## callees

- `0x140041924`
- `0x1400421f4`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400419c7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140041f3e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140041fc2`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400419c7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140041f3e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140041fc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140041a80`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400420cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140041a80`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400420cb`
- `ntoskrnl!IofCompleteRequest` at `0x1400419ff`
- `ntoskrnl!IofCompleteRequest` at `0x140041e4e`
- `ntoskrnl!IofCompleteRequest` at `0x1400419ff`
- `ntoskrnl!IofCompleteRequest` at `0x140041e4e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14004199b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14004199b`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140041aa0`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140041aa0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140041a5b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140041a5b`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceFlushIrp(char *Context, PIRP Irp)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  char v7; // si
  bool v8; // zf
  unsigned __int64 v9; // rcx
  _IO_STACK_LOCATION *v10; // rdx
  KSPIN_LOCK *v12; // r15
  KIRQL v13; // dl
  __int64 *v14; // rdx
  int *v15; // rax
  char v16; // r13
  unsigned __int8 v17; // r10
  _ACCESS_STATE *v18; // r9
  char SecurityQos; // cl
  unsigned __int64 v20; // rcx
  char v21; // r14
  char LowPart_high; // r8
  char Flags; // r11
  unsigned __int8 *p_SecurityEvaluated; // rax
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  char *v26; // r8
  unsigned int v27; // eax
  char v28; // cl
  _ACCESS_STATE *v29; // r9
  unsigned __int8 v30; // r10
  char v31; // r15
  char v32; // r14
  _IO_SECURITY_CONTEXT *v33; // rdx
  char v34; // r11
  unsigned __int8 *v35; // rax
  char v36; // r8
  char *v37; // r8
  unsigned int v38; // eax
  __int64 *v39; // rdx
  int *Information; // rax
  __int64 v41; // r8
  int v42; // ecx
  unsigned int v43; // r15d
  unsigned __int64 DesiredAccess; // r14
  char *v45; // r11
  int v46; // ecx
  unsigned int v47; // r15d
  __int64 v48; // r8
  int v49; // ecx
  unsigned int v50; // r12d
  char *v51; // r11
  _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  int v53; // eax
  char v54; // si
  int v55; // eax
  unsigned int AccessState; // r12d
  unsigned int v57; // r12d
  unsigned __int64 v58; // r14
  _LIST_ENTRY *v59; // r14
  _LIST_ENTRY *Blink; // rcx
  unsigned int v61; // r13d
  unsigned __int64 v62; // r14
  char v63; // [rsp+60h] [rbp-20h]
  char v64; // [rsp+60h] [rbp-20h]
  char v65; // [rsp+60h] [rbp-20h]
  unsigned int v66; // [rsp+64h] [rbp-1Ch]
  __int128 v67; // [rsp+68h] [rbp-18h] BYREF

  if ( (*(_BYTE *)(*((_QWORD *)Context + 2) + 136LL) & 2) != 0 )
  {
    *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
    LOBYTE(v5) = 0;
    v66 = -1073741637;
    v8 = StorEtwLoggingEnabled == 0;
    Irp->IoStatus.Status = -1073741637;
    if ( v8 )
      goto LABEL_95;
    v67 = 0;
    IoGetActivityIdIrp(Irp, &v67);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->MajorFunction != 14 )
    {
      v53 = CurrentStackLocation->MajorFunction - 15;
      if ( CurrentStackLocation->MajorFunction == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_95;
        SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
        v54 = 1;
        v55 = BYTE2(SecurityContext->SecurityQos);
        if ( (_BYTE)v55 == 40 )
        {
          if ( SecurityContext->FullCreateOptions )
            goto LABEL_95;
          AccessState = (unsigned int)SecurityContext[2].AccessState;
          if ( !AccessState )
            goto LABEL_95;
          v17 = 0;
          v63 = 0;
          v45 = 0;
          v16 = 0;
          v18 = 0;
          v43 = 0;
          while ( 1 )
          {
            v20 = *((unsigned int *)&SecurityContext[5].SecurityQos + v43);
            if ( (unsigned int)v20 >= 0x80 )
            {
              DesiredAccess = SecurityContext->DesiredAccess;
              if ( (unsigned int)v20 < (unsigned int)DesiredAccess )
              {
                v41 = *((unsigned int *)&SecurityContext[5].SecurityQos + v43);
                v42 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v20) - 64;
                if ( v42 )
                {
                  LODWORD(v20) = v42 - 1;
                  if ( (_DWORD)v20 )
                  {
                    if ( (_DWORD)v20 == 1 )
                    {
                      LODWORD(v20) = v41 + 40;
                      if ( v41 + 40 <= DesiredAccess )
                      {
LABEL_69:
                        if ( *(_DWORD *)((char *)&SecurityContext->AccessState + v41 + 4) )
                          v45 = (char *)&SecurityContext[1].AccessState + v41;
                        v18 = *(_ACCESS_STATE **)((char *)&SecurityContext[1].SecurityQos + v41);
LABEL_38:
                        v17 = *((_BYTE *)&SecurityContext->AccessState + v41 + 1);
                        v16 = *((_BYTE *)&SecurityContext->AccessState + v41);
LABEL_85:
                        if ( !v45 )
                          goto LABEL_95;
                        SecurityQos = *v45;
LABEL_25:
                        LOBYTE(v20) = SecurityQos - 8;
                        if ( (v20 & 0x5D) != 0 )
                          goto LABEL_95;
                        v21 = BYTE3(SecurityContext->SecurityQos);
                        if ( v21 == 1 || !v18 || !v17 )
                          goto LABEL_93;
                        LowPart_high = 0;
                        v20 = (unsigned __int64)v18 + v17;
                        Flags = 0;
                        p_SecurityEvaluated = &v18->SecurityEvaluated;
                        LOBYTE(SecurityContext) = 0;
                        if ( (unsigned __int8)((v18->OperationID.LowPart & 0x7F) - 114) <= 1u )
                        {
                          if ( (unsigned __int64)p_SecurityEvaluated <= v20 )
                          {
                            Flags = BYTE2(v18->OperationID.LowPart);
                            LOBYTE(SecurityContext) = BYTE1(v18->OperationID.LowPart) & 0xF;
                            LowPart_high = HIBYTE(v18->OperationID.LowPart);
                            goto LABEL_156;
                          }
                        }
                        else if ( (unsigned __int64)p_SecurityEvaluated <= v20 )
                        {
                          v26 = (char *)&v18->Flags + 1;
                          LOBYTE(SecurityContext) = BYTE2(v18->OperationID.LowPart) & 0xF;
                          v27 = v17;
                          if ( (unsigned int)HIBYTE(v18->OperationID.HighPart) + 8 <= v17 )
                            v27 = HIBYTE(v18->OperationID.HighPart) + 8;
                          v20 = (unsigned __int64)v18 + v27;
                          if ( (unsigned __int64)v26 <= v20 )
                            Flags = v18->Flags;
                          if ( (unsigned __int64)&v18->Flags + 2 > v20 )
                            LowPart_high = 0;
                          else
                            LowPart_high = *v26;
LABEL_156:
                          if ( !v54 )
                          {
LABEL_93:
                            LOBYTE(SecurityContext) = 0;
                            LowPart_high = 0;
                            Flags = 0;
                          }
                          McTemplateK0pduuuuup_EtwWriteTransfer(
                            v20,
                            (_DWORD)SecurityContext,
                            (unsigned int)&v67,
                            (_DWORD)Irp,
                            Irp->IoStatus.Status,
                            v21,
                            v16,
                            (char)SecurityContext,
                            Flags,
                            LowPart_high,
                            (char)Irp);
                          goto LABEL_95;
                        }
                        v54 = 0;
                        goto LABEL_156;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v20) = v41 + 56;
                    if ( v41 + 56 <= DesiredAccess )
                    {
                      v63 = 1;
                      if ( *((_BYTE *)&SecurityContext->AccessState + v41 + 2) )
                        v45 = (char *)&SecurityContext[1] + v41;
                      v16 = *((_BYTE *)&SecurityContext->AccessState + v41);
                      v18 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v41);
                      v17 = *((_BYTE *)&SecurityContext->AccessState + v41 + 1);
                    }
                  }
                }
                else
                {
                  LODWORD(v20) = v41 + 40;
                  if ( v41 + 40 <= DesiredAccess )
                  {
LABEL_76:
                    if ( *((_BYTE *)&SecurityContext->AccessState + v41 + 2) )
                      v45 = (char *)&SecurityContext[1] + v41;
                    v18 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v41);
                    goto LABEL_38;
                  }
                }
                if ( v63 )
                  goto LABEL_85;
              }
            }
            if ( ++v43 >= AccessState )
              goto LABEL_85;
          }
        }
LABEL_24:
        v16 = BYTE4(SecurityContext->SecurityQos);
        v17 = BYTE3(SecurityContext->AccessState);
        v18 = SecurityContext[1].AccessState;
        SecurityQos = (char)SecurityContext[3].SecurityQos;
        if ( !v55 )
          goto LABEL_25;
        goto LABEL_95;
      }
      goto LABEL_52;
    }
LABEL_96:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_95;
    v39 = EventNonReadWriteRequestComplete;
    goto LABEL_98;
  }
  v4 = NvmeNamespaceAcquireRemoveLock(Context, Irp);
  LOBYTE(v5) = 0;
  v66 = v4;
  if ( v4 < 0 )
  {
    v8 = StorEtwLoggingEnabled == 0;
    Irp->IoStatus.Information = 0;
    *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
    Irp->IoStatus.Status = v4;
    if ( v8 )
      goto LABEL_95;
    v67 = 0;
    IoGetActivityIdIrp(Irp, &v67);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    if ( CurrentStackLocation->MajorFunction != 14 )
    {
      v53 = CurrentStackLocation->MajorFunction - 15;
      if ( CurrentStackLocation->MajorFunction == 15 )
      {
        if ( byte_140177431 >= 0 )
          goto LABEL_95;
        SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
        v54 = 1;
        v55 = BYTE2(SecurityContext->SecurityQos);
        if ( (_BYTE)v55 == 40 )
        {
          if ( !SecurityContext->FullCreateOptions )
          {
            v57 = (unsigned int)SecurityContext[2].AccessState;
            if ( v57 )
            {
              v17 = 0;
              v64 = 0;
              v45 = 0;
              v16 = 0;
              v18 = 0;
              v47 = 0;
              while ( 1 )
              {
                v20 = *((unsigned int *)&SecurityContext[5].SecurityQos + v47);
                if ( (unsigned int)v20 >= 0x80 )
                {
                  v58 = SecurityContext->DesiredAccess;
                  if ( (unsigned int)v20 < (unsigned int)v58 )
                  {
                    v41 = *((unsigned int *)&SecurityContext[5].SecurityQos + v47);
                    v46 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v20) - 64;
                    if ( v46 )
                    {
                      LODWORD(v20) = v46 - 1;
                      if ( (_DWORD)v20 )
                      {
                        if ( (_DWORD)v20 == 1 )
                        {
                          LODWORD(v20) = v41 + 40;
                          if ( v41 + 40 <= v58 )
                            goto LABEL_69;
                        }
                      }
                      else
                      {
                        LODWORD(v20) = v41 + 56;
                        if ( v41 + 56 <= v58 )
                        {
                          v64 = 1;
                          if ( *((_BYTE *)&SecurityContext->AccessState + v41 + 2) )
                            v45 = (char *)&SecurityContext[1] + v41;
                          v16 = *((_BYTE *)&SecurityContext->AccessState + v41);
                          v18 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v41);
                          v17 = *((_BYTE *)&SecurityContext->AccessState + v41 + 1);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v20) = v41 + 40;
                      if ( v41 + 40 <= v58 )
                        goto LABEL_76;
                    }
                    if ( v64 )
                      goto LABEL_85;
                  }
                }
                if ( ++v47 >= v57 )
                  goto LABEL_85;
              }
            }
          }
          goto LABEL_95;
        }
        goto LABEL_24;
      }
LABEL_52:
      if ( v53 != 12 )
        goto LABEL_95;
      if ( CurrentStackLocation->MinorFunction == 7 && !CurrentStackLocation->Parameters.Read.Length )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          Information = (int *)Irp->IoStatus.Information;
          if ( Information )
            v5 = *Information;
          McTemplateK0pqd_EtwWriteTransfer(
            v20,
            (_DWORD)CurrentStackLocation,
            (unsigned int)&v67,
            (_DWORD)Irp,
            v5,
            Irp->IoStatus.Status);
        }
        goto LABEL_95;
      }
      if ( (byte_140177432 & 0x20) == 0 )
      {
LABEL_95:
        IofCompleteRequest(Irp, 0);
        return v66;
      }
      v39 = EventPnpRequestComplete;
LABEL_98:
      McTemplateK0pd_EtwWriteTransfer(v20, v39, &v67, Irp, Irp->IoStatus.Status);
      goto LABEL_95;
    }
    goto LABEL_96;
  }
  v6 = *((_QWORD *)Context + 2);
  v7 = 1;
  if ( (*(_BYTE *)(*(_QWORD *)(v6 + 592) + 525LL) & 1) != 0 && (*(_DWORD *)(v6 + 136) & 0x80000) != 0 )
  {
    v12 = (KSPIN_LOCK *)(Context + 560);
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 70);
    if ( *((_QWORD *)Context + 71) )
    {
      if ( *((_QWORD *)Context + 74) )
      {
        v59 = (_LIST_ENTRY *)(Context + 600);
        Blink = v59->Blink;
        if ( Blink->Flink != v59 )
          __fastfail(3u);
        Irp->Tail.Overlay.ListEntry.Flink = v59;
        Irp->Tail.Overlay.ListEntry.Blink = Blink;
        Blink->Flink = &Irp->Tail.Overlay.ListEntry;
        v59->Blink = &Irp->Tail.Overlay.ListEntry;
      }
      else
      {
        *((_QWORD *)Context + 74) = Irp;
      }
      KeReleaseSpinLock(v12, v13);
    }
    else
    {
      *((_QWORD *)Context + 71) = Irp;
      KeReleaseSpinLock((PKSPIN_LOCK)Context + 70, v13);
      IoQueueWorkItemEx(*((PIO_WORKITEM *)Context + 69), NvmeNamespaceFlushWorker, DelayedWorkQueue, Context);
    }
    return 259;
  }
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 15));
  v8 = StorEtwLoggingEnabled == 0;
  *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
  Irp->IoStatus.Status = 0;
  if ( v8 )
    goto LABEL_8;
  v67 = 0;
  IoGetActivityIdIrp(Irp, &v67);
  v10 = Irp->Tail.Overlay.CurrentStackLocation;
  if ( v10->MajorFunction == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_8;
    v14 = EventNonReadWriteRequestComplete;
    goto LABEL_15;
  }
  if ( v10->MajorFunction != 15 )
  {
    if ( v10->MajorFunction != 27 )
      goto LABEL_8;
    if ( v10->MinorFunction == 7 && !v10->Parameters.Read.Length )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v15 = (int *)Irp->IoStatus.Information;
        if ( v15 )
          v5 = *v15;
        McTemplateK0pqd_EtwWriteTransfer(v9, (_DWORD)v10, (unsigned int)&v67, (_DWORD)Irp, v5, Irp->IoStatus.Status);
      }
      goto LABEL_8;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_8;
    v14 = EventPnpRequestComplete;
LABEL_15:
    McTemplateK0pd_EtwWriteTransfer(v9, v14, &v67, Irp, Irp->IoStatus.Status);
    goto LABEL_8;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_8;
  v33 = v10->Parameters.Create.SecurityContext;
  if ( BYTE2(v33->SecurityQos) != 40 )
  {
    v28 = (char)v33[3].SecurityQos;
    v29 = v33[1].AccessState;
    v30 = BYTE3(v33->AccessState);
    v31 = BYTE4(v33->SecurityQos);
    if ( !BYTE2(v33->SecurityQos) )
      goto LABEL_40;
    goto LABEL_8;
  }
  if ( v33->FullCreateOptions )
    goto LABEL_8;
  v61 = (unsigned int)v33[2].AccessState;
  if ( !v61 )
    goto LABEL_8;
  v30 = 0;
  v65 = 0;
  v51 = 0;
  v31 = 0;
  v29 = 0;
  v50 = 0;
  while ( 1 )
  {
    v9 = *((unsigned int *)&v33[5].SecurityQos + v50);
    if ( (unsigned int)v9 >= 0x80 )
    {
      v62 = v33->DesiredAccess;
      if ( (unsigned int)v9 < (unsigned int)v62 )
        break;
    }
LABEL_104:
    if ( ++v50 >= v61 )
      goto LABEL_105;
  }
  v48 = *((unsigned int *)&v33[5].SecurityQos + v50);
  v49 = *(_DWORD *)((char *)&v33->SecurityQos + v9) - 64;
  if ( v49 )
  {
    LODWORD(v9) = v49 - 1;
    if ( (_DWORD)v9 )
    {
      if ( (_DWORD)v9 == 1 )
      {
        LODWORD(v9) = v48 + 40;
        if ( v48 + 40 <= v62 )
        {
          if ( *(_DWORD *)((char *)&v33->AccessState + v48 + 4) )
            v51 = (char *)&v33[1].AccessState + v48;
          v29 = *(_ACCESS_STATE **)((char *)&v33[1].SecurityQos + v48);
          goto LABEL_116;
        }
      }
    }
    else
    {
      LODWORD(v9) = v48 + 56;
      if ( v48 + 56 <= v62 )
      {
        v65 = 1;
        if ( *((_BYTE *)&v33->AccessState + v48 + 2) )
          v51 = (char *)&v33[1] + v48;
        v31 = *((_BYTE *)&v33->AccessState + v48);
        v29 = *(_ACCESS_STATE **)((char *)&v33->DesiredAccess + v48);
        v30 = *((_BYTE *)&v33->AccessState + v48 + 1);
      }
    }
    goto LABEL_103;
  }
  LODWORD(v9) = v48 + 40;
  if ( v48 + 40 > v62 )
  {
LABEL_103:
    if ( v65 )
      goto LABEL_105;
    goto LABEL_104;
  }
  if ( *((_BYTE *)&v33->AccessState + v48 + 2) )
    v51 = (char *)&v33[1] + v48;
  v29 = *(_ACCESS_STATE **)((char *)&v33->DesiredAccess + v48);
LABEL_116:
  v30 = *((_BYTE *)&v33->AccessState + v48 + 1);
  v31 = *((_BYTE *)&v33->AccessState + v48);
LABEL_105:
  if ( !v51 )
    goto LABEL_8;
  v28 = *v51;
LABEL_40:
  LOBYTE(v9) = v28 - 8;
  if ( (v9 & 0x5D) != 0 )
    goto LABEL_8;
  v32 = BYTE3(v33->SecurityQos);
  if ( v32 == 1 || !v29 || !v30 )
    goto LABEL_150;
  LOBYTE(v33) = 0;
  v9 = (unsigned __int64)v29 + v30;
  v34 = 0;
  v35 = &v29->SecurityEvaluated;
  v36 = 0;
  if ( (unsigned __int8)((v29->OperationID.LowPart & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v35 <= v9 )
    {
      v34 = BYTE2(v29->OperationID.LowPart);
      LOBYTE(v33) = BYTE1(v29->OperationID.LowPart) & 0xF;
      v36 = HIBYTE(v29->OperationID.LowPart);
      goto LABEL_166;
    }
    goto LABEL_165;
  }
  if ( (unsigned __int64)v35 > v9 )
  {
LABEL_165:
    v7 = 0;
    goto LABEL_166;
  }
  v37 = (char *)&v29->Flags + 1;
  LOBYTE(v33) = BYTE2(v29->OperationID.LowPart) & 0xF;
  v38 = v30;
  if ( (unsigned int)HIBYTE(v29->OperationID.HighPart) + 8 <= v30 )
    v38 = HIBYTE(v29->OperationID.HighPart) + 8;
  v9 = (unsigned __int64)v29 + v38;
  if ( (unsigned __int64)v37 <= v9 )
    v34 = v29->Flags;
  if ( (unsigned __int64)&v29->Flags + 2 > v9 )
    v36 = 0;
  else
    v36 = *v37;
LABEL_166:
  if ( !v7 )
  {
LABEL_150:
    LOBYTE(v33) = 0;
    v34 = 0;
    v36 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v9,
    (_DWORD)v33,
    (unsigned int)&v67,
    (_DWORD)Irp,
    Irp->IoStatus.Status,
    v32,
    v31,
    (char)v33,
    v34,
    v36,
    (char)Irp);
LABEL_8:
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x140041924  mov     [rsp-38h+arg_10], rbx
0x140041929  push    rbp
0x14004192a  push    rsi
0x14004192b  push    rdi
0x14004192c  push    r12
0x14004192e  push    r13
0x140041930  push    r14
0x140041932  push    r15
0x140041934  mov     rbp, rsp
0x140041937  sub     rsp, 80h
0x14004193e  mov     rax, cs:__security_cookie
0x140041945  xor     rax, rsp
0x140041948  mov     [rbp+var_8], rax
0x14004194c  mov     rax, [rcx+10h]
0x140041950  mov     rdi, rdx
0x140041953  mov     r14, rcx
0x140041956  test    byte ptr [rax+88h], 2
0x14004195d  jnz     loc_140042058
0x140041963  call    NvmeNamespaceAcquireRemoveLock
0x140041968  xor     ebx, ebx
0x14004196a  mov     [rbp+var_1C], eax
0x14004196d  test    eax, eax
0x14004196f  js      loc_14004207D
0x140041975  mov     rdx, [r14+10h]
0x140041979  lea     esi, [rbx+1]
0x14004197c  mov     rax, [rdx+250h]
0x140041983  test    [rax+20Dh], sil
0x14004198a  jnz     loc_140041A35
0x140041990  mov     [rdi+30h], ebx
0x140041993  mov     [rdi+38h], rbx
0x140041997  mov     rcx, [r14+78h]; RunRefCacheAware
0x14004199b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400419a2  nop     dword ptr [rax+rax+00h]
0x1400419a7  cmp     cs:StorEtwLoggingEnabled, bl
0x1400419ad  mov     byte ptr [rdi+8Dh], 0ACh
0x1400419b4  mov     [rdi+30h], ebx
0x1400419b7  jz      short loc_1400419FA
0x1400419b9  xorps   xmm0, xmm0
0x1400419bc  lea     rdx, [rbp+var_18]
0x1400419c0  mov     rcx, rdi
0x1400419c3  movups  [rbp+var_18], xmm0
0x1400419c7  call    cs:__imp_IoGetActivityIdIrp
0x1400419ce  nop     dword ptr [rax+rax+00h]
0x1400419d3  mov     rdx, [rdi+0B8h]
0x1400419da  movzx   eax, byte ptr [rdx]
0x1400419dd  sub     eax, 0Eh
0x1400419e0  jz      loc_140041AB6
0x1400419e6  sub     eax, esi
0x1400419e8  jnz     loc_140041AE2
0x1400419ee  cmp     cs:byte_140177431, bl
0x1400419f4  jl      loc_1400421AB
0x1400419fa  xor     edx, edx; PriorityBoost
0x1400419fc  mov     rcx, rdi; Irp
0x1400419ff  call    cs:__imp_IofCompleteRequest
0x140041a06  nop     dword ptr [rax+rax+00h]
0x140041a0b  xor     eax, eax
0x140041a0d  mov     rcx, [rbp+var_8]
0x140041a11  xor     rcx, rsp; StackCookie
0x140041a14  call    __security_check_cookie
0x140041a19  mov     rbx, [rsp+80h+arg_10]
0x140041a21  add     rsp, 80h
0x140041a28  pop     r15
0x140041a2a  pop     r14
0x140041a2c  pop     r13
0x140041a2e  pop     r12
0x140041a30  pop     rdi
0x140041a31  pop     rsi
0x140041a32  pop     rbp
0x140041a33  retn
0x140041a35  mov     eax, [rdx+88h]
0x140041a3b  bt      rax, 13h
0x140041a40  jnb     loc_140041990
0x140041a46  mov     rax, [rdi+0B8h]
0x140041a4d  lea     r15, [r14+230h]
0x140041a54  mov     rcx, r15; SpinLock
0x140041a57  or      [rax+3], sil
0x140041a5b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140041a62  nop     dword ptr [rax+rax+00h]
0x140041a67  mov     dl, al; NewIrql
0x140041a69  cmp     [r14+238h], rbx
0x140041a70  jnz     loc_140042192
0x140041a76  mov     rcx, r15; SpinLock
0x140041a79  mov     [r14+238h], rdi
0x140041a80  call    cs:__imp_KeReleaseSpinLock
0x140041a87  nop     dword ptr [rax+rax+00h]
0x140041a8c  mov     rcx, [r14+228h]; IoWorkItem
0x140041a93  lea     rdx, NvmeNamespaceFlushWorker; WorkerRoutine
0x140041a9a  mov     r9, r14; Context
0x140041a9d  mov     r8d, esi; QueueType
0x140041aa0  call    cs:__imp_IoQueueWorkItemEx
0x140041aa7  nop     dword ptr [rax+rax+00h]
0x140041aac  mov     eax, 103h
0x140041ab1  jmp     loc_140041A0D
0x140041ab6  test    cs:byte_140177432, 8
0x140041abd  jz      loc_1400419FA
0x140041ac3  lea     rdx, EventNonReadWriteRequestComplete
0x140041aca  mov     eax, [rdi+30h]
0x140041acd  lea     r8, [rbp+var_18]
0x140041ad1  mov     r9, rdi
0x140041ad4  mov     [rsp+80h+var_60], eax
0x140041ad8  call    McTemplateK0pd_EtwWriteTransfer
0x140041add  jmp     loc_1400419FA
0x140041ae2  cmp     eax, 0Ch
0x140041ae5  jnz     loc_1400419FA
0x140041aeb  cmp     byte ptr [rdx+1], 7
0x140041aef  jz      short loc_140041B07
0x140041af1  test    cs:byte_140177432, 20h
0x140041af8  jz      loc_1400419FA
0x140041afe  lea     rdx, EventPnpRequestComplete
0x140041b05  jmp     short loc_140041ACA
0x140041b07  cmp     [rdx+8], ebx
0x140041b0a  jnz     short loc_140041AF1
0x140041b0c  test    cs:byte_140177432, 40h
0x140041b13  jz      loc_1400419FA
0x140041b19  mov     rax, [rdi+38h]
0x140041b1d  test    rax, rax
0x140041b20  jz      loc_1401520BD
0x140041b26  mov     ebx, [rax]
0x140041b28  jmp     loc_1401520BD
0x140041b2d  mov     r13b, [rdx+4]
0x140041b31  mov     r10b, [rdx+0Bh]
0x140041b35  mov     r9, [rdx+20h]
0x140041b39  mov     cl, [rdx+48h]
0x140041b3c  test    eax, eax
0x140041b3e  jnz     loc_140041E49
0x140041b44  sub     cl, 8
0x140041b47  test    cl, 5Dh
0x140041b4a  jnz     loc_140041E49
0x140041b50  mov     r14b, [rdx+3]
0x140041b54  cmp     r14b, sil
0x140041b57  jz      loc_140041E11
0x140041b5d  test    r9, r9
0x140041b60  jz      loc_140041E11
0x140041b66  test    r10b, r10b
0x140041b69  jz      loc_140041E11
0x140041b6f  mov     al, [r9]
0x140041b72  mov     r8b, bl
0x140041b75  and     al, 7Fh
0x140041b77  movzx   ecx, r10b
0x140041b7b  sub     al, 72h ; 'r'
0x140041b7d  add     rcx, r9
0x140041b80  cmp     al, sil
0x140041b83  mov     r11b, bl
0x140041b86  lea     rax, [r9+8]
0x140041b8a  mov     dl, bl
0x140041b8c  jbe     loc_14004216B
0x140041b92  cmp     rax, rcx
0x140041b95  ja      loc_140042181
0x140041b9b  movzx   ecx, byte ptr [r9+7]
0x140041ba0  lea     r8, [r9+0Dh]
0x140041ba4  mov     dl, [r9+2]
0x140041ba8  add     ecx, 8
0x140041bab  and     dl, 0Fh
0x140041bae  movzx   eax, r10b
0x140041bb2  cmp     ecx, eax
0x140041bb4  cmovbe  eax, ecx
0x140041bb7  mov     ecx, eax
0x140041bb9  add     rcx, r9
0x140041bbc  cmp     r8, rcx
0x140041bbf  ja      short loc_140041BC5
0x140041bc1  mov     r11b, [r9+0Ch]
0x140041bc5  lea     rax, [r9+0Eh]
0x140041bc9  cmp     rax, rcx
0x140041bcc  ja      loc_140042166
0x140041bd2  mov     r8b, [r8]
0x140041bd5  jmp     loc_140042184
0x140041bda  mov     r9, [r8+rdx+18h]
0x140041bdf  mov     r10b, [r8+rdx+9]
0x140041be4  mov     r13b, [r8+rdx+8]
0x140041be9  jmp     loc_140041DC9
0x140041bee  mov     cl, [rdx+48h]
0x140041bf1  mov     r9, [rdx+20h]
0x140041bf5  mov     r10b, [rdx+0Bh]
0x140041bf9  mov     r15b, [rdx+4]
0x140041bfd  test    eax, eax
0x140041bff  jnz     loc_1400419FA
0x140041c05  sub     cl, 8
0x140041c08  test    cl, 5Dh
0x140041c0b  jnz     loc_1400419FA
0x140041c11  mov     r14b, [rdx+3]
0x140041c15  cmp     r14b, sil
0x140041c18  jz      loc_140042129
0x140041c1e  test    r9, r9
0x140041c21  jz      loc_140042129
0x140041c27  test    r10b, r10b
0x140041c2a  jz      loc_140042129
0x140041c30  mov     al, [r9]
0x140041c33  mov     dl, bl
0x140041c35  and     al, 7Fh
0x140041c37  movzx   ecx, r10b
0x140041c3b  sub     al, 72h ; 'r'
0x140041c3d  add     rcx, r9
0x140041c40  cmp     al, sil
0x140041c43  mov     r11b, bl
0x140041c46  lea     rax, [r9+8]
0x140041c4a  mov     r8b, bl
0x140041c4d  jbe     loc_1400421C5
0x140041c53  cmp     rax, rcx
0x140041c56  ja      loc_1400421DB
0x140041c5c  movzx   ecx, byte ptr [r9+7]
0x140041c61  lea     r8, [r9+0Dh]
0x140041c65  mov     dl, [r9+2]
0x140041c69  add     ecx, 8
0x140041c6c  and     dl, 0Fh
0x140041c6f  movzx   eax, r10b
0x140041c73  cmp     ecx, eax
0x140041c75  cmovbe  eax, ecx
0x140041c78  mov     ecx, eax
0x140041c7a  add     rcx, r9
0x140041c7d  cmp     r8, rcx
0x140041c80  ja      short loc_140041C86
0x140041c82  mov     r11b, [r9+0Ch]
0x140041c86  lea     rax, [r9+0Eh]
0x140041c8a  cmp     rax, rcx
0x140041c8d  ja      loc_1400421C0
0x140041c93  mov     r8b, [r8]
0x140041c96  jmp     loc_1400421DE
0x140041c9b  cmp     eax, 0Ch
0x140041c9e  jnz     loc_140041E49
0x140041ca4  cmp     byte ptr [rdx+1], 7
0x140041ca8  jnz     short loc_140041CAF
0x140041caa  cmp     [rdx+8], ebx
0x140041cad  jz      short loc_140041CC8
0x140041caf  test    cs:byte_140177432, 20h
0x140041cb6  jz      loc_140041E49
0x140041cbc  lea     rdx, EventPnpRequestComplete
0x140041cc3  jmp     loc_140041E72
0x140041cc8  test    cs:byte_140177432, 40h
0x140041ccf  jz      loc_140041E49
0x140041cd5  mov     rax, [rdi+38h]
0x140041cd9  test    rax, rax
0x140041cdc  jz      loc_1401520A0
0x140041ce2  mov     ebx, [rax]
0x140041ce4  jmp     loc_1401520A0
0x140041ce9  mov     r8, rcx
0x140041cec  mov     ecx, [rcx+rdx]
0x140041cef  sub     ecx, 40h ; '@'
0x140041cf2  jz      loc_140041D7B
0x140041cf8  sub     ecx, esi
0x140041cfa  jz      short loc_140041D4F
0x140041cfc  cmp     ecx, esi
0x140041cfe  jnz     short loc_140041D09
0x140041d00  lea     rcx, [r8+28h]
0x140041d04  cmp     rcx, r14
0x140041d07  jbe     short loc_140041D38
0x140041d09  cmp     [rbp+var_20], bl
0x140041d0c  jnz     loc_140041DC9
0x140041d12  add     r15d, esi
0x140041d15  cmp     r15d, r12d
0x140041d18  jnb     loc_140041DC9
0x140041d1e  mov     eax, r15d
0x140041d21  mov     ecx, [rdx+rax*4+78h]
0x140041d25  cmp     ecx, 80h
0x140041d2b  jb      short loc_140041D12
0x140041d2d  mov     r14d, [rdx+10h]
0x140041d31  cmp     ecx, r14d
0x140041d34  jnb     short loc_140041D12
0x140041d36  jmp     short loc_140041CE9
0x140041d38  cmp     [r8+rdx+0Ch], ebx
0x140041d3d  jbe     loc_140041BDA
0x140041d43  lea     r11, [rdx+20h]
0x140041d47  add     r11, r8
0x140041d4a  jmp     loc_140041BDA
0x140041d4f  lea     rcx, [r8+38h]
0x140041d53  cmp     rcx, r14
0x140041d56  ja      short loc_140041D09
0x140041d58  mov     [rbp+var_20], sil
0x140041d5c  cmp     [r8+rdx+0Ah], bl
0x140041d61  jbe     short loc_140041D6A
0x140041d63  lea     r11, [rdx+18h]
0x140041d67  add     r11, r8
0x140041d6a  mov     r13b, [r8+rdx+8]
0x140041d6f  mov     r9, [r8+rdx+10h]
0x140041d74  mov     r10b, [r8+rdx+9]
0x140041d79  jmp     short loc_140041D09
0x140041d7b  lea     rcx, [r8+28h]
0x140041d7f  cmp     rcx, r14
0x140041d82  ja      short loc_140041D09
0x140041d84  cmp     [r8+rdx+0Ah], bl
0x140041d89  jbe     short loc_140041D92
0x140041d8b  lea     r11, [rdx+18h]
0x140041d8f  add     r11, r8
0x140041d92  mov     r9, [r8+rdx+10h]
0x140041d97  jmp     loc_140041BDF
0x140041d9c  mov     r8, rcx
0x140041d9f  mov     ecx, [rcx+rdx]
0x140041da2  sub     ecx, 40h ; '@'
0x140041da5  jz      short loc_140041E02
0x140041da7  sub     ecx, esi
0x140041da9  jz      short loc_140041DD6
0x140041dab  cmp     ecx, esi
0x140041dad  jnz     short loc_140041DB8
0x140041daf  lea     rcx, [r8+28h]
0x140041db3  cmp     rcx, r14
0x140041db6  jbe     short loc_140041D38
0x140041db8  cmp     [rbp+var_20], bl
0x140041dbb  jnz     short loc_140041DC9
0x140041dbd  add     r15d, esi
0x140041dc0  cmp     r15d, r12d
0x140041dc3  jb      loc_140042033
  ... truncated ...
```
