# VmsTmCreateTeam

- ea: `0x14015b440`
- end: `0x14015b9e6`
- name: `VmsTmCreateTeam`
- size: `1446`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015cf30`

## callees

- `0x14002e0f0`
- `0x14003a450`
- `0x14003c378`
- `0x14003e9e4`
- `0x140046f1c`
- `0x14006a330`
- `0x14006a4ac`
- `0x14015b084`
- `0x14015b288`
- `0x14015b440`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14015b655`
- `ntoskrnl!RtlCreateHashTable` at `0x14015b672`
- `ntoskrnl!RtlCreateHashTable` at `0x14015b655`
- `ntoskrnl!RtlCreateHashTable` at `0x14015b672`
- `ntoskrnl!KeInitializeEvent` at `0x14015b6ca`
- `ntoskrnl!KeInitializeEvent` at `0x14015b6ca`
- `ntoskrnl!ExAllocatePool3` at `0x14015b49b`
- `ntoskrnl!ExAllocatePool3` at `0x14015b49b`
- `ntoskrnl!KeInitializeMutex` at `0x14015b6e2`
- `ntoskrnl!KeInitializeMutex` at `0x14015b6e2`
- `NDIS!NdisReleaseRWLock` at `0x14015b775`
- `NDIS!NdisReleaseRWLock` at `0x14015b775`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015b757`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015b757`
- `NDIS!NdisAllocateRWLock` at `0x14015b5ac`
- `NDIS!NdisAllocateRWLock` at `0x14015b5ff`
- `NDIS!NdisAllocateRWLock` at `0x14015b5ac`
- `NDIS!NdisAllocateRWLock` at `0x14015b5ff`

## pseudocode

```c
__int64 __fastcall VmsTmCreateTeam(__int64 a1, __int64 a2)
{
  __int64 Pool3; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned int Timer; // edi
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // r8
  PNPAGED_LOOKASIDE_LIST *v12; // rdi
  int v13; // edx
  PNDIS_RW_LOCK_EX RWLock; // rax
  int v15; // edx
  int v16; // r9d
  PNDIS_RW_LOCK_EX v17; // rax
  int v18; // edx
  int v19; // edx
  struct _NDIS_RW_LOCK_EX *v20; // rcx
  int v21; // edx
  unsigned int v22; // ecx
  unsigned int v23; // edx
  unsigned int v24; // eax
  __int64 v25; // rax
  unsigned __int64 v26; // rdx
  int v27; // edx
  __int64 (__fastcall *v28)(__int64, __int64); // rax
  __int64 (__fastcall *v29)(__int64, __int64); // rax
  __int64 v31; // [rsp+28h] [rbp-38h]
  PRTL_DYNAMIC_HASH_TABLE v32; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v33[3]; // [rsp+48h] [rbp-18h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+B0h] [rbp+50h] BYREF
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+B8h] [rbp+58h] BYREF

  v33[1] = 16;
  *(_WORD *)&LockState.OldIrql = 0;
  v32 = 0;
  HashTable = 0;
  LockState.Flags = 0;
  v33[0] = 1;
  Pool3 = ExAllocatePool3(64, 4016, 1415801166, v33, 1);
  v7 = Pool3;
  if ( !Pool3 )
  {
    Timer = -1073741670;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v5, 20, 24, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 176, 154);
    goto LABEL_38;
  }
  *(_DWORD *)Pool3 = 0;
  v12 = (PNPAGED_LOOKASIDE_LIST *)(Pool3 + 3968);
  *(_DWORD *)(Pool3 + 126) = *(_DWORD *)a2;
  *(_WORD *)(Pool3 + 130) = *(_WORD *)(a2 + 4);
  *(_DWORD *)(Pool3 + 132) = *(_DWORD *)a2;
  *(_WORD *)(Pool3 + 136) = *(_WORD *)(a2 + 4);
  *(_QWORD *)(a1 + 16) = Pool3;
  *(_QWORD *)(Pool3 + 8) = a1;
  if ( (int)NvIoAllocateWorkerQueue(v6, Pool3 + 3864, Pool3 + 3968) < 0 )
  {
    Timer = -1073741670;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v13, 20, 25, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 154);
    goto LABEL_38;
  }
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_I(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      23,
      26,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      v7);
  RWLock = NdisAllocateRWLock(*(NDIS_HANDLE *)(a1 + 304));
  *(_QWORD *)(v7 + 1584) = RWLock;
  if ( !RWLock )
  {
    Timer = -1073741670;
    v16 = 27;
    LOBYTE(v31) = *(_QWORD *)(a1 + 304);
LABEL_10:
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_id(VmsIfrLog, v15, 20, v16, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, v31, 154);
    goto LABEL_38;
  }
  v17 = NdisAllocateRWLock(*(NDIS_HANDLE *)(a1 + 304));
  *(_QWORD *)(v7 + 1592) = v17;
  if ( !v17 )
  {
    Timer = -1073741670;
    v16 = 28;
    v31 = *(_QWORD *)(a1 + 304);
    goto LABEL_10;
  }
  v32 = (PRTL_DYNAMIC_HASH_TABLE)(v7 + 1648);
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v7 + 1608);
  if ( RtlCreateHashTable(&HashTable, 0, 0) && RtlCreateHashTable(&v32, 0, 0) )
  {
    *(_QWORD *)(v7 + 2296) = v7 + 2288;
    *(_QWORD *)(v7 + 2288) = v7 + 2288;
    *(_QWORD *)(v7 + 2280) = v7 + 2272;
    *(_QWORD *)(v7 + 2272) = v7 + 2272;
    *(_QWORD *)(v7 + 2320) = v7 + 2312;
    *(_QWORD *)(v7 + 2312) = v7 + 2312;
    *(_QWORD *)(v7 + 3984) = v7 + 3976;
    *(_QWORD *)(v7 + 3976) = v7 + 3976;
    KeInitializeEvent((PRKEVENT)(v7 + 2336), NotificationEvent, 0);
    KeInitializeMutex((PRKMUTEX)(v7 + 1528), 0xFFFFu);
    if ( (int)NvIoAllocateWorkItem(*v12, 7, v7 + 3992) >= 0 )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v7 + 1584), &LockState, 0);
      v20 = *(struct _NDIS_RW_LOCK_EX **)(v7 + 1584);
      *(_DWORD *)(v7 + 4008) = 0;
      NdisReleaseRWLock(v20, &LockState);
      if ( (int)NvIoAllocateWorkItem(*v12, 30, v7 + 4000) >= 0 )
      {
        *(_BYTE *)(v7 + 1604) ^= (*(_BYTE *)(v7 + 1604) ^ (BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) >> 5)) & 1;
        v22 = 5;
        v23 = *(_DWORD *)(a2 + 12);
        *(_DWORD *)(v7 + 1512) = v23;
        if ( v23 <= 5 )
        {
          v22 = v23;
        }
        else
        {
          *(_DWORD *)(v7 + 1512) = 5;
          v23 = 5;
        }
        if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) & 8) != 0 )
        {
          if ( v22 >= 4 )
          {
            *(_DWORD *)(v7 + 1512) = 0;
            LOBYTE(v22) = 0;
            v23 = 0;
          }
          v24 = 1;
        }
        else
        {
          v24 = *(_DWORD *)(a2 + 8);
        }
        *(_DWORD *)(v7 + 1520) = v24;
        if ( v24 > 2 )
          *(_DWORD *)(v7 + 1520) = 1;
        v25 = v23;
        v26 = 0x140000000uLL;
        *(_WORD *)(v7 + 2360) = 1;
        *(_DWORD *)(v7 + 1516) = LbAlgoConfigToLbAlgo[v25];
        LOBYTE(v26) = 4;
        WPP_RECORDER_SF_id(VmsIfrLog, v26, 18, 32, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, v7, v22);
        LOBYTE(v27) = 4;
        WPP_RECORDER_SF_id(
          VmsIfrLog,
          v27,
          18,
          33,
          (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
          v7,
          *(_DWORD *)(v7 + 1520));
        if ( !qword_1401F3B20[14 * *(int *)(v7 + 1516)]
          || !HIWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine)
          || (Timer = VmsTmAllocateTimer(*(_QWORD *)(a1 + 304), VmsTmCfgMacRebalanceTimer, v7 + 2328)) == 0 )
        {
          v28 = (__int64 (__fastcall *)(__int64, __int64))TeamingModeOperations[9 * *(int *)(v7 + 1520)];
          if ( !v28 || (Timer = v28(v7, a2)) == 0 )
          {
            v10 = 112LL * *(int *)(v7 + 1516);
            v29 = *(__int64 (__fastcall **)(__int64, __int64))((char *)&LBAlgoOperations + v10);
            if ( v29 )
              Timer = v29(v7, a2);
            else
              Timer = 0;
          }
        }
      }
      else
      {
        Timer = -1073741670;
        LOBYTE(v21) = 2;
        WPP_RECORDER_SF_d(VmsIfrLog, v21, 20, 31, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 154);
      }
    }
    else
    {
      Timer = -1073741670;
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v19, 20, 30, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 154);
    }
  }
  else
  {
    Timer = -1073741670;
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v18, 20, 29, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 154);
  }
LABEL_38:
  if ( (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 0x200000) != 0 )
    McTemplateK0pd_EtwWriteTransfer(v10, InitializingTNicInfo, v11, a1, Timer);
  if ( Timer )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_qqd(VmsIfrLog, v9, 20, 34, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, a1, a2, Timer);
  }
  return Timer;
}

```

## disassembly

```asm
0x14015b440  mov     [rsp-38h+arg_0], rbx
0x14015b445  push    rbp
0x14015b446  push    rsi
0x14015b447  push    rdi
0x14015b448  push    r12
0x14015b44a  push    r13
0x14015b44c  push    r14
0x14015b44e  push    r15
0x14015b450  mov     rbp, rsp
0x14015b453  sub     rsp, 60h
0x14015b457  xor     eax, eax
0x14015b459  mov     [rbp+var_10], 10h
0x14015b461  xor     r12d, r12d
0x14015b464  mov     word ptr [rbp+LockState.OldIrql], ax
0x14015b468  mov     r14, rdx
0x14015b46b  mov     [rbp+var_20], r12
0x14015b46f  mov     r15, rcx
0x14015b472  mov     [rbp+HashTable], r12
0x14015b476  mov     esi, 0FB0h
0x14015b47b  mov     [rbp+LockState.Flags], al
0x14015b47e  lea     r13d, [r12+1]
0x14015b483  mov     r8d, 5463694Eh
0x14015b489  lea     r9, [rbp+var_18]
0x14015b48d  mov     [rbp+var_18], r13
0x14015b491  mov     edx, esi
0x14015b493  mov     dword ptr [rsp+60h+var_40], r13d
0x14015b498  lea     ecx, [rax+40h]
0x14015b49b  call    cs:__imp_ExAllocatePool3
0x14015b4a2  nop     dword ptr [rax+rax+00h]
0x14015b4a7  mov     rbx, rax
0x14015b4aa  test    rax, rax
0x14015b4ad  jnz     short loc_14015B4E7
0x14015b4af  mov     eax, 0C000009Ah
0x14015b4b4  mov     edi, eax
0x14015b4b6  mov     rcx, cs:VmsIfrLog
0x14015b4bd  lea     r9d, [r12+18h]
0x14015b4c2  mov     dword ptr [rsp+60h+var_30], eax
0x14015b4c6  lea     r8d, [r12+14h]
0x14015b4cb  mov     dword ptr [rsp+60h+var_38], esi
0x14015b4cf  mov     dl, 2
0x14015b4d1  lea     rsi, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015b4d8  mov     [rsp+60h+var_40], rsi
0x14015b4dd  call    WPP_RECORDER_SF_ld
0x14015b4e2  jmp     loc_14015B980
0x14015b4e7  mov     [rax], r12d
0x14015b4ea  lea     rdi, [rbx+0F80h]
0x14015b4f1  mov     eax, [r14]
0x14015b4f4  lea     rdx, [rbx+0F18h]
0x14015b4fb  mov     [rbx+7Eh], eax
0x14015b4fe  mov     r8, rdi
0x14015b501  movzx   eax, word ptr [r14+4]
0x14015b506  mov     [rbx+82h], ax
0x14015b50d  mov     eax, [r14]
0x14015b510  mov     [rbx+84h], eax
0x14015b516  movzx   eax, word ptr [r14+4]
0x14015b51b  mov     [rbx+88h], ax
0x14015b522  mov     [r15+10h], rbx
0x14015b526  mov     [rbx+8], r15
0x14015b52a  call    NvIoAllocateWorkerQueue
0x14015b52f  test    eax, eax
0x14015b531  jns     short loc_14015B567
0x14015b533  mov     eax, 0C000009Ah
0x14015b538  mov     edi, eax
0x14015b53a  mov     rcx, cs:VmsIfrLog
0x14015b541  lea     rsi, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015b548  mov     r9d, 19h
0x14015b54e  mov     dword ptr [rsp+60h+var_38], eax
0x14015b552  mov     dl, 2
0x14015b554  mov     [rsp+60h+var_40], rsi
0x14015b559  lea     r8d, [r9-5]
0x14015b55d  call    WPP_RECORDER_SF_d
0x14015b562  jmp     loc_14015B980
0x14015b567  mov     rcx, cs:WPP_GLOBAL_Control
0x14015b56e  lea     rsi, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015b575  mov     al, [rcx+29h]
0x14015b578  sub     al, r13b
0x14015b57b  cmp     al, 2
0x14015b57d  ja      short loc_14015B586
0x14015b57f  cmp     [rcx+48h], r12w
0x14015b584  jz      short loc_14015B5A5
0x14015b586  mov     rcx, [rcx+40h]
0x14015b58a  mov     r9d, 1Ah
0x14015b590  mov     [rsp+60h+var_38], rbx
0x14015b595  xor     edx, edx
0x14015b597  mov     [rsp+60h+var_40], rsi
0x14015b59c  lea     r8d, [r9-3]
0x14015b5a0  call    WPP_RECORDER_SF_I
0x14015b5a5  mov     rcx, [r15+130h]; NdisHandle
0x14015b5ac  call    cs:__imp_NdisAllocateRWLock
0x14015b5b3  nop     dword ptr [rax+rax+00h]
0x14015b5b8  mov     [rbx+630h], rax
0x14015b5bf  mov     rcx, [r15+130h]; NdisHandle
0x14015b5c6  test    rax, rax
0x14015b5c9  jnz     short loc_14015B5FF
0x14015b5cb  mov     eax, 0C000009Ah
0x14015b5d0  mov     edi, eax
0x14015b5d2  mov     dword ptr [rsp+60h+var_30], eax
0x14015b5d6  mov     r9d, 1Bh
0x14015b5dc  mov     [rsp+60h+var_38], rcx
0x14015b5e1  mov     rcx, cs:VmsIfrLog
0x14015b5e8  mov     r8d, 14h
0x14015b5ee  mov     dl, 2
0x14015b5f0  mov     [rsp+60h+var_40], rsi
0x14015b5f5  call    WPP_RECORDER_SF_id
0x14015b5fa  jmp     loc_14015B980
0x14015b5ff  call    cs:__imp_NdisAllocateRWLock
0x14015b606  nop     dword ptr [rax+rax+00h]
0x14015b60b  mov     [rbx+638h], rax
0x14015b612  test    rax, rax
0x14015b615  jnz     short loc_14015B636
0x14015b617  mov     eax, 0C000009Ah
0x14015b61c  mov     edi, eax
0x14015b61e  mov     dword ptr [rsp+60h+var_30], eax
0x14015b622  mov     r9d, 1Ch
0x14015b628  mov     rax, [r15+130h]
0x14015b62f  mov     [rsp+60h+var_38], rax
0x14015b634  jmp     short loc_14015B5E1
0x14015b636  lea     rax, [rbx+670h]
0x14015b63d  xor     r8d, r8d; Flags
0x14015b640  mov     [rbp+var_20], rax
0x14015b644  lea     rcx, [rbp+HashTable]; HashTable
0x14015b648  lea     rax, [rbx+648h]
0x14015b64f  xor     edx, edx; Shift
0x14015b651  mov     [rbp+HashTable], rax
0x14015b655  call    cs:__imp_RtlCreateHashTable
0x14015b65c  nop     dword ptr [rax+rax+00h]
0x14015b661  test    al, al
0x14015b663  jz      loc_14015B958
0x14015b669  xor     r8d, r8d; Flags
0x14015b66c  lea     rcx, [rbp+var_20]; HashTable
0x14015b670  xor     edx, edx; Shift
0x14015b672  call    cs:__imp_RtlCreateHashTable
0x14015b679  nop     dword ptr [rax+rax+00h]
0x14015b67e  test    al, al
0x14015b680  jz      loc_14015B958
0x14015b686  lea     rax, [rbx+8F0h]
0x14015b68d  xor     r8d, r8d; State
0x14015b690  mov     [rax+8], rax
0x14015b694  lea     rcx, [rbx+920h]; Event
0x14015b69b  mov     [rax], rax
0x14015b69e  xor     edx, edx; Type
0x14015b6a0  lea     rax, [rbx+8E0h]
0x14015b6a7  mov     [rax+8], rax
0x14015b6ab  mov     [rax], rax
0x14015b6ae  lea     rax, [rbx+908h]
0x14015b6b5  mov     [rax+8], rax
0x14015b6b9  mov     [rax], rax
0x14015b6bc  lea     rax, [rbx+0F88h]
0x14015b6c3  mov     [rax+8], rax
0x14015b6c7  mov     [rax], rax
0x14015b6ca  call    cs:__imp_KeInitializeEvent
0x14015b6d1  nop     dword ptr [rax+rax+00h]
0x14015b6d6  lea     rcx, [rbx+5F8h]; Mutex
0x14015b6dd  mov     edx, 0FFFFh; Level
0x14015b6e2  call    cs:__imp_KeInitializeMutex
0x14015b6e9  nop     dword ptr [rax+rax+00h]
0x14015b6ee  mov     rcx, [rdi]; Lookaside
0x14015b6f1  lea     rax, [rbx+0F98h]
0x14015b6f8  mov     [rsp+60h+var_38], rax; __int64
0x14015b6fd  lea     r8, lbfoTMRemoveAggregatorWorkItem
0x14015b704  mov     r9, rbx
0x14015b707  mov     [rsp+60h+var_40], 7; __int64
0x14015b710  mov     edx, r13d
0x14015b713  call    NvIoAllocateWorkItem
0x14015b718  test    eax, eax
0x14015b71a  jns     short loc_14015B749
0x14015b71c  mov     eax, 0C000009Ah
0x14015b721  mov     edi, eax
0x14015b723  mov     rcx, cs:VmsIfrLog
0x14015b72a  mov     r9d, 1Eh
0x14015b730  mov     dword ptr [rsp+60h+var_38], eax
0x14015b734  mov     dl, 2
0x14015b736  mov     [rsp+60h+var_40], rsi
0x14015b73b  lea     r8d, [r9-0Ah]
0x14015b73f  call    WPP_RECORDER_SF_d
0x14015b744  jmp     loc_14015B980
0x14015b749  mov     rcx, [rbx+630h]; Lock
0x14015b750  lea     rdx, [rbp+LockState]; LockState
0x14015b754  xor     r8d, r8d; Flags
0x14015b757  call    cs:__imp_NdisAcquireRWLockWrite
0x14015b75e  nop     dword ptr [rax+rax+00h]
0x14015b763  mov     rcx, [rbx+630h]; Lock
0x14015b76a  lea     rdx, [rbp+LockState]; LockState
0x14015b76e  mov     [rbx+0FA8h], r12d
0x14015b775  call    cs:__imp_NdisReleaseRWLock
0x14015b77c  nop     dword ptr [rax+rax+00h]
0x14015b781  mov     rcx, [rdi]; Lookaside
0x14015b784  lea     rax, [rbx+0FA0h]
0x14015b78b  mov     [rsp+60h+var_38], rax; __int64
0x14015b790  lea     r8, lbfoPrimeSwitchIfNeededWorkItem
0x14015b797  mov     r9, rbx
0x14015b79a  mov     [rsp+60h+var_40], 1Eh; __int64
0x14015b7a3  mov     edx, r13d
0x14015b7a6  call    NvIoAllocateWorkItem
0x14015b7ab  test    eax, eax
0x14015b7ad  jns     short loc_14015B7DC
0x14015b7af  mov     eax, 0C000009Ah
0x14015b7b4  mov     edi, eax
0x14015b7b6  mov     rcx, cs:VmsIfrLog
0x14015b7bd  mov     r9d, 1Fh
0x14015b7c3  mov     dword ptr [rsp+60h+var_38], eax
0x14015b7c7  mov     dl, 2
0x14015b7c9  mov     [rsp+60h+var_40], rsi
0x14015b7ce  lea     r8d, [r9-0Bh]
0x14015b7d2  call    WPP_RECORDER_SF_d
0x14015b7d7  jmp     loc_14015B980
0x14015b7dc  mov     cl, byte ptr cs:WPP_MAIN_CB.Queue+34h
0x14015b7e2  mov     al, [rbx+644h]
0x14015b7e8  shr     cl, 5
0x14015b7eb  xor     cl, al
0x14015b7ed  and     cl, r13b
0x14015b7f0  xor     cl, al
0x14015b7f2  mov     [rbx+644h], cl
0x14015b7f8  mov     ecx, 5
0x14015b7fd  mov     edx, [r14+0Ch]
0x14015b801  mov     [rbx+5E8h], edx
0x14015b807  cmp     edx, ecx
0x14015b809  jbe     short loc_14015B815
0x14015b80b  mov     [rbx+5E8h], ecx
0x14015b811  mov     edx, ecx
0x14015b813  jmp     short loc_14015B817
0x14015b815  mov     ecx, edx
0x14015b817  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x14015b81e  jz      short loc_14015B837
0x14015b820  cmp     ecx, 4
0x14015b823  jb      short loc_14015B832
0x14015b825  mov     [rbx+5E8h], r12d
0x14015b82c  mov     ecx, r12d
0x14015b82f  mov     edx, r12d
0x14015b832  mov     eax, r13d
0x14015b835  jmp     short loc_14015B83B
0x14015b837  mov     eax, [r14+8]
0x14015b83b  mov     [rbx+5F0h], eax
0x14015b841  cmp     eax, 2
0x14015b844  jbe     short loc_14015B84D
0x14015b846  mov     [rbx+5F0h], r13d
0x14015b84d  mov     eax, edx
0x14015b84f  lea     rdx, cs:140000000h
0x14015b856  mov     [rbx+938h], r13w
0x14015b85e  mov     eax, ds:rva LbAlgoConfigToLbAlgo[rdx+rax*4]
0x14015b865  mov     [rbx+5ECh], eax
0x14015b86b  mov     dword ptr [rsp+60h+var_30], ecx
0x14015b86f  mov     r9d, 20h ; ' '
0x14015b875  mov     rcx, cs:VmsIfrLog
0x14015b87c  mov     dl, 4
0x14015b87e  mov     [rsp+60h+var_38], rbx
0x14015b883  mov     [rsp+60h+var_40], rsi
0x14015b888  lea     edi, [r9-0Eh]
0x14015b88c  mov     r8d, edi
0x14015b88f  call    WPP_RECORDER_SF_id
0x14015b894  mov     eax, [rbx+5F0h]
0x14015b89a  lea     r9d, [rdi+0Fh]
0x14015b89e  mov     rcx, cs:VmsIfrLog
0x14015b8a5  mov     r8d, edi
0x14015b8a8  mov     dword ptr [rsp+60h+var_30], eax
0x14015b8ac  mov     dl, 4
0x14015b8ae  mov     [rsp+60h+var_38], rbx
0x14015b8b3  mov     [rsp+60h+var_40], rsi
0x14015b8b8  call    WPP_RECORDER_SF_id
0x14015b8bd  movsxd  rax, dword ptr [rbx+5ECh]
0x14015b8c4  lea     r13, cs:140000000h
0x14015b8cb  imul    rcx, rax, 70h ; 'p'
0x14015b8cf  cmp     [rcx+r13+1F3B20h], r12
0x14015b8d7  jz      short loc_14015B903
0x14015b8d9  cmp     word ptr cs:WPP_MAIN_CB.Queue+1Eh, r12w
0x14015b8e1  jbe     short loc_14015B903
0x14015b8e3  mov     rcx, [r15+130h]
0x14015b8ea  lea     r8, [rbx+918h]
0x14015b8f1  lea     rdx, VmsTmCfgMacRebalanceTimer
0x14015b8f8  call    VmsTmAllocateTimer
0x14015b8fd  mov     edi, eax
0x14015b8ff  test    eax, eax
0x14015b901  jnz     short loc_14015B980
0x14015b903  movsxd  rax, dword ptr [rbx+5F0h]
0x14015b90a  lea     rcx, [rax+rax*8]
0x14015b90e  mov     rax, rva TeamingModeOperations[r13+rcx*8]
0x14015b916  test    rax, rax
0x14015b919  jz      short loc_14015B92C
0x14015b91b  mov     rdx, r14
0x14015b91e  mov     rcx, rbx
0x14015b921  call    _guard_dispatch_icall
0x14015b926  mov     edi, eax
0x14015b928  test    eax, eax
0x14015b92a  jnz     short loc_14015B980
0x14015b92c  movsxd  rax, dword ptr [rbx+5ECh]
0x14015b933  imul    rcx, rax, 70h ; 'p'
0x14015b937  mov     rax, [rcx+r13+1F3AC0h]
0x14015b93f  test    rax, rax
0x14015b942  jz      short loc_14015B953
0x14015b944  mov     rdx, r14
0x14015b947  mov     rcx, rbx
0x14015b94a  call    _guard_dispatch_icall
0x14015b94f  mov     edi, eax
0x14015b951  jmp     short loc_14015B980
0x14015b953  mov     edi, r12d
0x14015b956  jmp     short loc_14015B980
0x14015b958  mov     eax, 0C000009Ah
0x14015b95d  mov     edi, eax
0x14015b95f  mov     rcx, cs:VmsIfrLog
0x14015b966  mov     r9d, 1Dh
  ... truncated ...
```
