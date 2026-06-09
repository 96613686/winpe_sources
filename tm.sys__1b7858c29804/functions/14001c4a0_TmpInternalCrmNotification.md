# TmpInternalCrmNotification

- ea: `0x14001c4a0`
- end: `0x14001ca50`
- name: `TmpInternalCrmNotification`
- size: `1456`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT EnlistmentObject, PVOID RMContext, PVOID TransactionContext, ULONG TransactionNotification, PLARGE_INTEGER TmVirtualClock, ULONG ArgumentLength, PVOID Argument)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001cfc`
- `0x140002158`
- `0x14000c718`
- `0x14000fed0`
- `0x140010140`
- `0x140010220`
- `0x140010330`
- `0x140010500`
- `0x140019a30`
- `0x140019a5c`
- `0x140019da0`
- `0x140019f00`
- `0x14001a000`
- `0x14001c4a0`
- `0x140020250`
- `0x140020a6c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001c80d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001c80d`
- `ntoskrnl!KeReleaseMutex` at `0x14001c8d1`
- `ntoskrnl!KeReleaseMutex` at `0x14001c8f9`
- `ntoskrnl!KeReleaseMutex` at `0x14001c8d1`
- `ntoskrnl!KeReleaseMutex` at `0x14001c8f9`
- `ntoskrnl!ObfReferenceObject` at `0x14001c8a9`
- `ntoskrnl!ObfReferenceObject` at `0x14001c8bf`
- `ntoskrnl!ObfReferenceObject` at `0x14001c993`
- `ntoskrnl!ObfReferenceObject` at `0x14001c9b2`
- `ntoskrnl!ObfReferenceObject` at `0x14001c8a9`
- `ntoskrnl!ObfReferenceObject` at `0x14001c8bf`
- `ntoskrnl!ObfReferenceObject` at `0x14001c993`
- `ntoskrnl!ObfReferenceObject` at `0x14001c9b2`
- `ntoskrnl!RtlCompareMemory` at `0x14001c82a`
- `ntoskrnl!RtlCompareMemory` at `0x14001c858`
- `ntoskrnl!RtlCompareMemory` at `0x14001c88d`
- `ntoskrnl!RtlCompareMemory` at `0x14001c82a`
- `ntoskrnl!RtlCompareMemory` at `0x14001c858`
- `ntoskrnl!RtlCompareMemory` at `0x14001c88d`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001c943`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca03`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca17`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca2b`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca3f`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001c943`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca03`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca17`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca2b`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14001ca3f`

## pseudocode

```c
__int64 __fastcall TmpInternalCrmNotification(
        PKENLISTMENT *EnlistmentObject,
        PVOID RMContext,
        PVOID TransactionContext,
        ULONG TransactionNotification,
        PLARGE_INTEGER TmVirtualClock)
{
  NTSTATUS v7; // edi
  PKENLISTMENT v8; // r15
  PKENLISTMENT v9; // rcx
  NTSTATUS v10; // eax
  PKENLISTMENT v11; // rcx
  PKENLISTMENT v13; // rcx
  __int64 v14; // [rsp+40h] [rbp-68h]
  int v15; // [rsp+48h] [rbp-60h] BYREF
  __int64 v16; // [rsp+4Ch] [rbp-5Ch] BYREF
  __int64 v17; // [rsp+54h] [rbp-54h] BYREF
  int v18; // [rsp+5Ch] [rbp-4Ch] BYREF
  __int64 v19; // [rsp+60h] [rbp-48h]
  __int64 (__fastcall *v20)(int); // [rsp+68h] [rbp-40h] BYREF
  __int64 v21[2]; // [rsp+70h] [rbp-38h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+8h] BYREF

  v7 = 0;
  v14 = 0;
  Object = 0;
  v8 = 0;
  if ( EnlistmentObject )
  {
    ObfReferenceObject(EnlistmentObject);
    v13 = EnlistmentObject[30];
    if ( v13 )
    {
      v8 = EnlistmentObject[30];
      ObfReferenceObject(v13);
    }
  }
  if ( TransactionNotification != 0x2000
    && (TransactionNotification != 256 && TransactionNotification != 2048 || !EnlistmentObject[30])
    && (TransactionNotification == 256
     || TransactionNotification == 2048
     || TransactionNotification == 0x2000000
     || EnlistmentObject[30]) )
  {
    if ( TransactionNotification <= 0x80 )
    {
      if ( TransactionNotification != 128 )
      {
        switch ( TransactionNotification )
        {
          case 1u:
            v7 = TmPrePrepareEnlistmentExt(EnlistmentObject[30], TmVirtualClock);
            break;
          case 2u:
            v7 = TmPrepareEnlistmentExt(EnlistmentObject[30], TmVirtualClock);
            if ( v7 < 0 )
              TmRollbackEnlistmentExt((PKENLISTMENT)EnlistmentObject, 0);
            break;
          case 4u:
            goto LABEL_30;
          case 8u:
            v7 = TmRollbackEnlistmentExt(EnlistmentObject[30], TmVirtualClock);
            break;
          case 0x10u:
            v11 = EnlistmentObject[30];
            LODWORD(v14) = 266;
            v18 = 273;
            v21[0] = (__int64)TmpTxActionDoPrePrepareComplete;
            v17 = 0x800000002LL;
            v10 = TmpProcessNotificationResponse(v11, (__int64)&v18, (__int64)&v17 + 4, (__int64)v21, (__int64)&v17);
            goto LABEL_21;
          case 0x20u:
            v9 = EnlistmentObject[30];
            v16 = 0x10100000102LL;
            v15 = 2;
            v20 = TmpTxActionDoPrepareComplete;
            LODWORD(Object) = 0;
            v10 = TmpProcessNotificationResponse(v9, (__int64)&v16, (__int64)&v15, (__int64)&v20, (__int64)&Object);
            goto LABEL_21;
          case 0x40u:
            v10 = TmCommitCompleteExt(EnlistmentObject[30], 0);
            goto LABEL_21;
          default:
            goto LABEL_33;
        }
        goto LABEL_35;
      }
      v10 = TmRollbackCompleteExt(EnlistmentObject[30], 0);
LABEL_21:
      v7 = v10;
      goto LABEL_35;
    }
    if ( TransactionNotification > 0x4000 )
    {
      if ( TransactionNotification == 0x1000000 )
      {
        TmpRmDisconnectTransaction(EnlistmentObject[30]);
        goto LABEL_35;
      }
      if ( TransactionNotification == 0x20000000 )
      {
        v10 = TmRequestOutcomeEnlistmentExt(EnlistmentObject[30], 0);
        goto LABEL_21;
      }
    }
    else
    {
      switch ( TransactionNotification )
      {
        case 0x4000u:
          goto LABEL_35;
        case 0x100u:
          goto LABEL_29;
        case 0x200u:
LABEL_30:
          v7 = TmCommitEnlistmentExt(EnlistmentObject[30], 0);
          goto LABEL_35;
        case 0x800u:
LABEL_29:
          v19 = 0;
          TmpNamespaceLookup(&TmpTmNamespace, EnlistmentObject + 35);
          v21[1] = 0;
          TmpTransactionManagerNeededForRecovery(EnlistmentObject + 35);
          goto LABEL_35;
      }
    }
LABEL_33:
    v7 = -1073741823;
  }
LABEL_35:
  if ( v7 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
  {
    WPP_SF_DDq(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      RMContext,
      TransactionContext,
      (unsigned int)v7,
      TransactionNotification,
      EnlistmentObject);
  }
  if ( v8 )
    ObDereferenceObjectDeferDelete(v8);
  if ( EnlistmentObject )
    ObDereferenceObjectDeferDelete(EnlistmentObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001c4a0  mov     rax, rsp
0x14001c4a3  mov     [rax+10h], rbx
0x14001c4a7  mov     [rax+18h], rsi
0x14001c4ab  push    rdi
0x14001c4ac  push    r12
0x14001c4ae  push    r13
0x14001c4b0  push    r14
0x14001c4b2  push    r15
0x14001c4b4  sub     rsp, 80h
0x14001c4bb  mov     r13d, r9d
0x14001c4be  mov     rbx, rcx
0x14001c4c1  xor     edi, edi
0x14001c4c3  xor     r12d, r12d
0x14001c4c6  xor     esi, esi
0x14001c4c8  mov     [rax-68h], rsi
0x14001c4cc  xor     r14d, r14d
0x14001c4cf  mov     [rax+8], r14
0x14001c4d3  xor     r15d, r15d
0x14001c4d6  test    rcx, rcx
0x14001c4d9  jnz     loc_14001C993
0x14001c4df  cmp     r13d, 2000h
0x14001c4e6  jz      loc_14001C933
0x14001c4ec  cmp     r13d, 100h
0x14001c4f3  jz      short loc_14001C4FE
0x14001c4f5  cmp     r13d, 800h
0x14001c4fc  jnz     short loc_14001C50C
0x14001c4fe  cmp     qword ptr [rbx+0F0h], 0
0x14001c506  jnz     loc_14001C933
0x14001c50c  cmp     r13d, 100h
0x14001c513  jz      short loc_14001C535
0x14001c515  cmp     r13d, 800h
0x14001c51c  jz      short loc_14001C535
0x14001c51e  cmp     r13d, 2000000h
0x14001c525  jz      short loc_14001C535
0x14001c527  cmp     qword ptr [rbx+0F0h], 0
0x14001c52f  jz      loc_14001C933
0x14001c535  cmp     r13d, 80h
0x14001c53c  ja      loc_14001C6DE
0x14001c542  jz      loc_14001C6CE
0x14001c548  lea     eax, [r13-1]; switch 64 cases
0x14001c54c  cmp     eax, 3Fh
0x14001c54f  ja      def_14001C56E; jumptable 000000014001C56E default case, cases 3,5-7,9-15,17-31,33-63
0x14001c555  lea     rdx, cs:140000000h
0x14001c55c  movzx   eax, ds:(byte_1400048A0 - 140000000h)[rdx+rax]
0x14001c564  mov     ecx, ds:(jpt_14001C56E - 140000000h)[rdx+rax*4]
0x14001c56b  add     rcx, rdx
0x14001c56e  jmp     rcx; switch jump
0x14001c574  mov     rdx, [rsp+0A8h+TmVirtualClock]; jumptable 000000014001C56E case 8
0x14001c57c  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c583  call    TmRollbackEnlistmentExt
0x14001c588  mov     edi, eax
0x14001c58a  jmp     loc_14001C933
0x14001c58f  mov     rdx, [rsp+0A8h+TmVirtualClock]; jumptable 000000014001C56E case 2
0x14001c597  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c59e  call    TmPrepareEnlistmentExt
0x14001c5a3  mov     edi, eax
0x14001c5a5  test    eax, eax
0x14001c5a7  jns     loc_14001C933
0x14001c5ad  xor     edx, edx; TmVirtualClock
0x14001c5af  mov     rcx, rbx; Enlistment
0x14001c5b2  call    TmRollbackEnlistmentExt
0x14001c5b7  jmp     loc_14001C933
0x14001c5bc  mov     rdx, [rsp+0A8h+TmVirtualClock]; jumptable 000000014001C56E case 1
0x14001c5c4  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c5cb  call    TmPrePrepareEnlistmentExt
0x14001c5d0  mov     edi, eax
0x14001c5d2  jmp     loc_14001C933
0x14001c5d7  mov     rcx, [rbx+0F0h]; jumptable 000000014001C56E case 32
0x14001c5de  mov     dword ptr [rsp+0A8h+var_5C+4], 101h
0x14001c5e6  mov     dword ptr [rsp+0A8h+var_5C], 102h
0x14001c5ee  mov     [rsp+0A8h+var_60], 2
0x14001c5f6  lea     rax, TmpTxActionDoPrepareComplete
0x14001c5fd  mov     [rsp+0A8h+var_40], rax
0x14001c602  mov     dword ptr [rsp+0A8h+Object], 0
0x14001c60d  lea     rax, [rsp+0A8h+Object]
0x14001c615  mov     [rsp+0A8h+var_70], rax
0x14001c61a  lea     rax, [rsp+0A8h+var_40]
0x14001c61f  mov     [rsp+0A8h+var_78], rax
0x14001c624  lea     rax, [rsp+0A8h+var_60]
0x14001c629  mov     [rsp+0A8h+var_80], rax
0x14001c62e  lea     rax, [rsp+0A8h+var_5C]
0x14001c633  lea     r9, [rsp+0A8h+var_5C+4]
0x14001c638  jmp     short loc_14001C695
0x14001c63a  mov     rcx, [rbx+0F0h]; jumptable 000000014001C56E case 16
0x14001c641  mov     dword ptr [rsp+0A8h+var_68], 10Ah
0x14001c649  mov     [rsp+0A8h+var_4C], 111h
0x14001c651  mov     dword ptr [rsp+0A8h+var_54+4], 8
0x14001c659  lea     rax, TmpTxActionDoPrePrepareComplete
0x14001c660  mov     [rsp+0A8h+var_38], rax
0x14001c665  mov     dword ptr [rsp+0A8h+var_54], 2
0x14001c66d  lea     rax, [rsp+0A8h+var_54]
0x14001c672  mov     [rsp+0A8h+var_70], rax; __int64
0x14001c677  lea     rax, [rsp+0A8h+var_38]
0x14001c67c  mov     [rsp+0A8h+var_78], rax; __int64
0x14001c681  lea     rax, [rsp+0A8h+var_54+4]
0x14001c686  mov     [rsp+0A8h+var_80], rax; __int64
0x14001c68b  lea     rax, [rsp+0A8h+var_4C]
0x14001c690  lea     r9, [rsp+0A8h+var_68]
0x14001c695  mov     [rsp+0A8h+Timeout], rax; __int64
0x14001c69a  xor     edx, edx
0x14001c69c  mov     r8d, 1
0x14001c6a2  call    TmpProcessNotificationResponse
0x14001c6a7  jmp     short loc_14001C6B7
0x14001c6a9  xor     edx, edx; TmVirtualClock
0x14001c6ab  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c6b2  call    TmRequestOutcomeEnlistmentExt
0x14001c6b7  mov     edi, eax
0x14001c6b9  jmp     loc_14001C933
0x14001c6be  xor     edx, edx; jumptable 000000014001C56E case 64
0x14001c6c0  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c6c7  call    TmCommitCompleteExt
0x14001c6cc  jmp     short loc_14001C6B7
0x14001c6ce  xor     edx, edx; TmVirtualClock
0x14001c6d0  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c6d7  call    TmRollbackCompleteExt
0x14001c6dc  jmp     short loc_14001C6B7
0x14001c6de  cmp     r13d, 4000h
0x14001c6e5  ja      loc_14001C909
0x14001c6eb  jz      loc_14001C933
0x14001c6f1  cmp     r13d, 100h
0x14001c6f8  jz      short loc_14001C710
0x14001c6fa  cmp     r13d, 200h
0x14001c701  jz      short loc_14001C754; jumptable 000000014001C56E case 4
0x14001c703  cmp     r13d, 800h
0x14001c70a  jnz     def_14001C56E; jumptable 000000014001C56E default case, cases 3,5-7,9-15,17-31,33-63
0x14001c710  mov     [rsp+0A8h+var_48], 0
0x14001c719  lea     rax, [rbx+118h]
0x14001c720  lea     r8, [rsp+0A8h+var_48]
0x14001c725  mov     rdx, rax; Buffer
0x14001c728  lea     rcx, TmpTmNamespace; Table
0x14001c72f  call    TmpNamespaceLookup
0x14001c734  mov     r12, [rsp+0A8h+var_48]
0x14001c739  mov     [rsp+0A8h+var_30], r12
0x14001c73e  test    r12, r12
0x14001c741  jnz     short loc_14001C769
0x14001c743  lea     rcx, [rbx+118h]; Source1
0x14001c74a  call    TmpTransactionManagerNeededForRecovery
0x14001c74f  jmp     loc_14001C933
0x14001c754  xor     edx, edx; jumptable 000000014001C56E case 4
0x14001c756  mov     rcx, [rbx+0F0h]; Enlistment
0x14001c75d  call    TmCommitEnlistmentExt
0x14001c762  mov     edi, eax
0x14001c764  jmp     loc_14001C933
0x14001c769  lea     rdx, [rbx+128h]
0x14001c770  lea     r8, [rsp+0A8h+var_68]
0x14001c775  mov     rcx, r12
0x14001c778  call    TmpFindResourceManagerTm
0x14001c77d  mov     edi, eax
0x14001c77f  mov     rsi, [rsp+0A8h+var_68]
0x14001c784  test    eax, eax
0x14001c786  js      loc_14001C933
0x14001c78c  lea     rdx, [rbx+108h]
0x14001c793  lea     r8, [rsp+0A8h+Object]
0x14001c79b  mov     rcx, rsi
0x14001c79e  call    TmpFindEnlistmentResourceManager
0x14001c7a3  mov     edi, eax
0x14001c7a5  cmp     eax, 0C0190050h
0x14001c7aa  jnz     short loc_14001C7E8
0x14001c7ac  xor     edx, edx; EnlistmentKey
0x14001c7ae  mov     rcx, rbx; Enlistment
0x14001c7b1  call    TmRecoverEnlistmentExt
0x14001c7b6  xor     edx, edx; TmVirtualClock
0x14001c7b8  mov     rcx, rbx; Enlistment
0x14001c7bb  cmp     r13d, 100h
0x14001c7c2  jnz     short loc_14001C7D6
0x14001c7c4  call    TmCommitCompleteExt
0x14001c7c9  mov     r14, [rsp+0A8h+Object]
0x14001c7d1  jmp     loc_14001C905
0x14001c7d6  call    TmRollbackEnlistmentExt
0x14001c7db  mov     r14, [rsp+0A8h+Object]
0x14001c7e3  jmp     loc_14001C905
0x14001c7e8  mov     r14, [rsp+0A8h+Object]
0x14001c7f0  test    eax, eax
0x14001c7f2  js      loc_14001C933
0x14001c7f8  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14001c801  xor     r9d, r9d; Alertable
0x14001c804  xor     r8d, r8d; WaitMode
0x14001c807  xor     edx, edx; WaitReason
0x14001c809  lea     rcx, [r14+40h]; Object
0x14001c80d  call    cs:__imp_KeWaitForSingleObject
0x14001c814  nop     dword ptr [rax+rax+00h]
0x14001c819  lea     rdx, [rbx+30h]; Source2
0x14001c81d  lea     rcx, [r14+108h]; Source1
0x14001c824  mov     r8d, 10h; Length
0x14001c82a  call    cs:__imp_RtlCompareMemory
0x14001c831  nop     dword ptr [rax+rax+00h]
0x14001c836  cmp     rax, 10h
0x14001c83a  jnz     loc_14001C8F3
0x14001c840  mov     rdx, [rbx+98h]
0x14001c847  add     rdx, 88h; Source2
0x14001c84e  lea     rcx, [r14+128h]; Source1
0x14001c855  mov     r8, rax; Length
0x14001c858  call    cs:__imp_RtlCompareMemory
0x14001c85f  nop     dword ptr [rax+rax+00h]
0x14001c864  cmp     rax, 10h
0x14001c868  jnz     loc_14001C8F3
0x14001c86e  mov     rax, [rbx+98h]
0x14001c875  mov     rdx, [rax+168h]
0x14001c87c  add     rdx, 70h ; 'p'; Source2
0x14001c880  lea     rcx, [r14+118h]; Source1
0x14001c887  mov     r8d, 10h; Length
0x14001c88d  call    cs:__imp_RtlCompareMemory
0x14001c894  nop     dword ptr [rax+rax+00h]
0x14001c899  cmp     rax, 10h
0x14001c89d  jnz     short loc_14001C8F3
0x14001c89f  mov     [rbx+0F0h], r14
0x14001c8a6  mov     rcx, r14; Object
0x14001c8a9  call    cs:__imp_ObfReferenceObject
0x14001c8b0  nop     dword ptr [rax+rax+00h]
0x14001c8b5  mov     [r14+0F0h], rbx
0x14001c8bc  mov     rcx, rbx; Object
0x14001c8bf  call    cs:__imp_ObfReferenceObject
0x14001c8c6  nop     dword ptr [rax+rax+00h]
0x14001c8cb  xor     edx, edx; Wait
0x14001c8cd  lea     rcx, [r14+40h]; Mutex
0x14001c8d1  call    cs:__imp_KeReleaseMutex
0x14001c8d8  nop     dword ptr [rax+rax+00h]
0x14001c8dd  xor     edx, edx; EnlistmentKey
0x14001c8df  mov     rcx, rbx; Enlistment
0x14001c8e2  call    TmRecoverEnlistmentExt
0x14001c8e7  xor     edx, edx; EnlistmentKey
0x14001c8e9  mov     rcx, r14; Enlistment
0x14001c8ec  call    TmRecoverEnlistmentExt
0x14001c8f1  jmp     short loc_14001C905
0x14001c8f3  xor     edx, edx; Wait
0x14001c8f5  lea     rcx, [r14+40h]; Mutex
0x14001c8f9  call    cs:__imp_KeReleaseMutex
0x14001c900  nop     dword ptr [rax+rax+00h]
0x14001c905  xor     edi, edi
0x14001c907  jmp     short loc_14001C933
0x14001c909  cmp     r13d, 1000000h
0x14001c910  jz      short loc_14001C926
0x14001c912  cmp     r13d, 20000000h
0x14001c919  jz      loc_14001C6A9
0x14001c91f  mov     edi, 0C0000001h; jumptable 000000014001C56E default case, cases 3,5-7,9-15,17-31,33-63
0x14001c924  jmp     short loc_14001C933
0x14001c926  mov     rcx, [rbx+0F0h]; Object
0x14001c92d  call    TmpRmDisconnectTransaction
0x14001c932  nop
0x14001c933  test    edi, edi
0x14001c935  js      loc_14001C9C3
0x14001c93b  test    r15, r15
0x14001c93e  jz      short loc_14001C94F
0x14001c940  mov     rcx, r15; Object
0x14001c943  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14001c94a  nop     dword ptr [rax+rax+00h]
0x14001c94f  test    rbx, rbx
0x14001c952  jnz     loc_14001CA00
0x14001c958  test    r14, r14
0x14001c95b  jnz     loc_14001CA14
0x14001c961  test    r12, r12
0x14001c964  jnz     loc_14001CA28
0x14001c96a  test    rsi, rsi
0x14001c96d  jnz     loc_14001CA3C
0x14001c973  mov     eax, edi
0x14001c975  lea     r11, [rsp+0A8h+var_28]
0x14001c97d  mov     rbx, [r11+38h]
0x14001c981  mov     rsi, [r11+40h]
0x14001c985  mov     rsp, r11
0x14001c988  pop     r15
0x14001c98a  pop     r14
0x14001c98c  pop     r13
0x14001c98e  pop     r12
0x14001c990  pop     rdi
0x14001c991  retn
0x14001c993  call    cs:__imp_ObfReferenceObject
0x14001c99a  nop     dword ptr [rax+rax+00h]
0x14001c99f  mov     rcx, [rbx+0F0h]; Object
0x14001c9a6  test    rcx, rcx
0x14001c9a9  jz      loc_14001C4DF
0x14001c9af  mov     r15, rcx
0x14001c9b2  call    cs:__imp_ObfReferenceObject
0x14001c9b9  nop     dword ptr [rax+rax+00h]
0x14001c9be  jmp     loc_14001C4DF
0x14001c9c3  lea     rax, WPP_GLOBAL_Control
0x14001c9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c9d1  cmp     rcx, rax
0x14001c9d4  jz      loc_14001C93B
0x14001c9da  mov     eax, [rcx+2Ch]
0x14001c9dd  test    al, 8
0x14001c9df  jz      loc_14001C93B
0x14001c9e5  mov     [rsp+0A8h+var_80], rbx
0x14001c9ea  mov     dword ptr [rsp+0A8h+Timeout], r13d
0x14001c9ef  mov     r9d, edi
0x14001c9f2  mov     rcx, [rcx+18h]
0x14001c9f6  call    WPP_SF_DDq
0x14001c9fb  jmp     loc_14001C93B
0x14001ca00  mov     rcx, rbx; Object
0x14001ca03  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14001ca0a  nop     dword ptr [rax+rax+00h]
0x14001ca0f  jmp     loc_14001C958
0x14001ca14  mov     rcx, r14; Object
0x14001ca17  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14001ca1e  nop     dword ptr [rax+rax+00h]
0x14001ca23  jmp     loc_14001C961
0x14001ca28  mov     rcx, r12; Object
0x14001ca2b  call    cs:__imp_ObDereferenceObjectDeferDelete
0x14001ca32  nop     dword ptr [rax+rax+00h]
0x14001ca37  jmp     loc_14001C96A
0x14001ca3c  mov     rcx, rsi; Object
  ... truncated ...
```
