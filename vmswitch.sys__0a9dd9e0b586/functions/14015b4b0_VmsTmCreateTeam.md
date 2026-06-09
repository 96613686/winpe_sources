# VmsTmCreateTeam

- ea: `0x14015b4b0`
- end: `0x14015ba56`
- name: `VmsTmCreateTeam`
- size: `1446`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015cfa0`

## callees

- `0x14002e0f0`
- `0x14003a450`
- `0x14003c378`
- `0x14003e9e4`
- `0x140046f1c`
- `0x14006a330`
- `0x14006a4ac`
- `0x14015b0f4`
- `0x14015b2f8`
- `0x14015b4b0`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14015b6c5`
- `ntoskrnl!RtlCreateHashTable` at `0x14015b6e2`
- `ntoskrnl!RtlCreateHashTable` at `0x14015b6c5`
- `ntoskrnl!RtlCreateHashTable` at `0x14015b6e2`
- `ntoskrnl!KeInitializeEvent` at `0x14015b73a`
- `ntoskrnl!KeInitializeEvent` at `0x14015b73a`
- `ntoskrnl!ExAllocatePool3` at `0x14015b50b`
- `ntoskrnl!ExAllocatePool3` at `0x14015b50b`
- `ntoskrnl!KeInitializeMutex` at `0x14015b752`
- `ntoskrnl!KeInitializeMutex` at `0x14015b752`
- `NDIS!NdisReleaseRWLock` at `0x14015b7e5`
- `NDIS!NdisReleaseRWLock` at `0x14015b7e5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015b7c7`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015b7c7`
- `NDIS!NdisAllocateRWLock` at `0x14015b61c`
- `NDIS!NdisAllocateRWLock` at `0x14015b66f`
- `NDIS!NdisAllocateRWLock` at `0x14015b61c`
- `NDIS!NdisAllocateRWLock` at `0x14015b66f`

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
0x14015b4b0  mov     [rsp-38h+arg_0], rbx
0x14015b4b5  push    rbp
0x14015b4b6  push    rsi
0x14015b4b7  push    rdi
0x14015b4b8  push    r12
0x14015b4ba  push    r13
0x14015b4bc  push    r14
0x14015b4be  push    r15
0x14015b4c0  mov     rbp, rsp
0x14015b4c3  sub     rsp, 60h
0x14015b4c7  xor     eax, eax
0x14015b4c9  mov     [rbp+var_10], 10h
0x14015b4d1  xor     r12d, r12d
0x14015b4d4  mov     word ptr [rbp+LockState.OldIrql], ax
0x14015b4d8  mov     r14, rdx
0x14015b4db  mov     [rbp+var_20], r12
0x14015b4df  mov     r15, rcx
0x14015b4e2  mov     [rbp+HashTable], r12
0x14015b4e6  mov     esi, 0FB0h
0x14015b4eb  mov     [rbp+LockState.Flags], al
0x14015b4ee  lea     r13d, [r12+1]
0x14015b4f3  mov     r8d, 5463694Eh
0x14015b4f9  lea     r9, [rbp+var_18]
0x14015b4fd  mov     [rbp+var_18], r13
0x14015b501  mov     edx, esi
0x14015b503  mov     dword ptr [rsp+60h+var_40], r13d
0x14015b508  lea     ecx, [rax+40h]
0x14015b50b  call    cs:__imp_ExAllocatePool3
0x14015b512  nop     dword ptr [rax+rax+00h]
0x14015b517  mov     rbx, rax
0x14015b51a  test    rax, rax
0x14015b51d  jnz     short loc_14015B557
0x14015b51f  mov     eax, 0C000009Ah
0x14015b524  mov     edi, eax
0x14015b526  mov     rcx, cs:VmsIfrLog
0x14015b52d  lea     r9d, [r12+18h]
0x14015b532  mov     dword ptr [rsp+60h+var_30], eax
0x14015b536  lea     r8d, [r12+14h]
0x14015b53b  mov     dword ptr [rsp+60h+var_38], esi
0x14015b53f  mov     dl, 2
0x14015b541  lea     rsi, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015b548  mov     [rsp+60h+var_40], rsi
0x14015b54d  call    WPP_RECORDER_SF_ld
0x14015b552  jmp     loc_14015B9F0
0x14015b557  mov     [rax], r12d
0x14015b55a  lea     rdi, [rbx+0F80h]
0x14015b561  mov     eax, [r14]
0x14015b564  lea     rdx, [rbx+0F18h]
0x14015b56b  mov     [rbx+7Eh], eax
0x14015b56e  mov     r8, rdi
0x14015b571  movzx   eax, word ptr [r14+4]
0x14015b576  mov     [rbx+82h], ax
0x14015b57d  mov     eax, [r14]
0x14015b580  mov     [rbx+84h], eax
0x14015b586  movzx   eax, word ptr [r14+4]
0x14015b58b  mov     [rbx+88h], ax
0x14015b592  mov     [r15+10h], rbx
0x14015b596  mov     [rbx+8], r15
0x14015b59a  call    NvIoAllocateWorkerQueue
0x14015b59f  test    eax, eax
0x14015b5a1  jns     short loc_14015B5D7
0x14015b5a3  mov     eax, 0C000009Ah
0x14015b5a8  mov     edi, eax
0x14015b5aa  mov     rcx, cs:VmsIfrLog
0x14015b5b1  lea     rsi, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015b5b8  mov     r9d, 19h
0x14015b5be  mov     dword ptr [rsp+60h+var_38], eax
0x14015b5c2  mov     dl, 2
0x14015b5c4  mov     [rsp+60h+var_40], rsi
0x14015b5c9  lea     r8d, [r9-5]
0x14015b5cd  call    WPP_RECORDER_SF_d
0x14015b5d2  jmp     loc_14015B9F0
0x14015b5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14015b5de  lea     rsi, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015b5e5  mov     al, [rcx+29h]
0x14015b5e8  sub     al, r13b
0x14015b5eb  cmp     al, 2
0x14015b5ed  ja      short loc_14015B5F6
0x14015b5ef  cmp     [rcx+48h], r12w
0x14015b5f4  jz      short loc_14015B615
0x14015b5f6  mov     rcx, [rcx+40h]
0x14015b5fa  mov     r9d, 1Ah
0x14015b600  mov     [rsp+60h+var_38], rbx
0x14015b605  xor     edx, edx
0x14015b607  mov     [rsp+60h+var_40], rsi
0x14015b60c  lea     r8d, [r9-3]
0x14015b610  call    WPP_RECORDER_SF_I
0x14015b615  mov     rcx, [r15+130h]; NdisHandle
0x14015b61c  call    cs:__imp_NdisAllocateRWLock
0x14015b623  nop     dword ptr [rax+rax+00h]
0x14015b628  mov     [rbx+630h], rax
0x14015b62f  mov     rcx, [r15+130h]; NdisHandle
0x14015b636  test    rax, rax
0x14015b639  jnz     short loc_14015B66F
0x14015b63b  mov     eax, 0C000009Ah
0x14015b640  mov     edi, eax
0x14015b642  mov     dword ptr [rsp+60h+var_30], eax
0x14015b646  mov     r9d, 1Bh
0x14015b64c  mov     [rsp+60h+var_38], rcx
0x14015b651  mov     rcx, cs:VmsIfrLog
0x14015b658  mov     r8d, 14h
0x14015b65e  mov     dl, 2
0x14015b660  mov     [rsp+60h+var_40], rsi
0x14015b665  call    WPP_RECORDER_SF_id
0x14015b66a  jmp     loc_14015B9F0
0x14015b66f  call    cs:__imp_NdisAllocateRWLock
0x14015b676  nop     dword ptr [rax+rax+00h]
0x14015b67b  mov     [rbx+638h], rax
0x14015b682  test    rax, rax
0x14015b685  jnz     short loc_14015B6A6
0x14015b687  mov     eax, 0C000009Ah
0x14015b68c  mov     edi, eax
0x14015b68e  mov     dword ptr [rsp+60h+var_30], eax
0x14015b692  mov     r9d, 1Ch
0x14015b698  mov     rax, [r15+130h]
0x14015b69f  mov     [rsp+60h+var_38], rax
0x14015b6a4  jmp     short loc_14015B651
0x14015b6a6  lea     rax, [rbx+670h]
0x14015b6ad  xor     r8d, r8d; Flags
0x14015b6b0  mov     [rbp+var_20], rax
0x14015b6b4  lea     rcx, [rbp+HashTable]; HashTable
0x14015b6b8  lea     rax, [rbx+648h]
0x14015b6bf  xor     edx, edx; Shift
0x14015b6c1  mov     [rbp+HashTable], rax
0x14015b6c5  call    cs:__imp_RtlCreateHashTable
0x14015b6cc  nop     dword ptr [rax+rax+00h]
0x14015b6d1  test    al, al
0x14015b6d3  jz      loc_14015B9C8
0x14015b6d9  xor     r8d, r8d; Flags
0x14015b6dc  lea     rcx, [rbp+var_20]; HashTable
0x14015b6e0  xor     edx, edx; Shift
0x14015b6e2  call    cs:__imp_RtlCreateHashTable
0x14015b6e9  nop     dword ptr [rax+rax+00h]
0x14015b6ee  test    al, al
0x14015b6f0  jz      loc_14015B9C8
0x14015b6f6  lea     rax, [rbx+8F0h]
0x14015b6fd  xor     r8d, r8d; State
0x14015b700  mov     [rax+8], rax
0x14015b704  lea     rcx, [rbx+920h]; Event
0x14015b70b  mov     [rax], rax
0x14015b70e  xor     edx, edx; Type
0x14015b710  lea     rax, [rbx+8E0h]
0x14015b717  mov     [rax+8], rax
0x14015b71b  mov     [rax], rax
0x14015b71e  lea     rax, [rbx+908h]
0x14015b725  mov     [rax+8], rax
0x14015b729  mov     [rax], rax
0x14015b72c  lea     rax, [rbx+0F88h]
0x14015b733  mov     [rax+8], rax
0x14015b737  mov     [rax], rax
0x14015b73a  call    cs:__imp_KeInitializeEvent
0x14015b741  nop     dword ptr [rax+rax+00h]
0x14015b746  lea     rcx, [rbx+5F8h]; Mutex
0x14015b74d  mov     edx, 0FFFFh; Level
0x14015b752  call    cs:__imp_KeInitializeMutex
0x14015b759  nop     dword ptr [rax+rax+00h]
0x14015b75e  mov     rcx, [rdi]; Lookaside
0x14015b761  lea     rax, [rbx+0F98h]
0x14015b768  mov     [rsp+60h+var_38], rax; __int64
0x14015b76d  lea     r8, lbfoTMRemoveAggregatorWorkItem
0x14015b774  mov     r9, rbx
0x14015b777  mov     [rsp+60h+var_40], 7; __int64
0x14015b780  mov     edx, r13d
0x14015b783  call    NvIoAllocateWorkItem
0x14015b788  test    eax, eax
0x14015b78a  jns     short loc_14015B7B9
0x14015b78c  mov     eax, 0C000009Ah
0x14015b791  mov     edi, eax
0x14015b793  mov     rcx, cs:VmsIfrLog
0x14015b79a  mov     r9d, 1Eh
0x14015b7a0  mov     dword ptr [rsp+60h+var_38], eax
0x14015b7a4  mov     dl, 2
0x14015b7a6  mov     [rsp+60h+var_40], rsi
0x14015b7ab  lea     r8d, [r9-0Ah]
0x14015b7af  call    WPP_RECORDER_SF_d
0x14015b7b4  jmp     loc_14015B9F0
0x14015b7b9  mov     rcx, [rbx+630h]; Lock
0x14015b7c0  lea     rdx, [rbp+LockState]; LockState
0x14015b7c4  xor     r8d, r8d; Flags
0x14015b7c7  call    cs:__imp_NdisAcquireRWLockWrite
0x14015b7ce  nop     dword ptr [rax+rax+00h]
0x14015b7d3  mov     rcx, [rbx+630h]; Lock
0x14015b7da  lea     rdx, [rbp+LockState]; LockState
0x14015b7de  mov     [rbx+0FA8h], r12d
0x14015b7e5  call    cs:__imp_NdisReleaseRWLock
0x14015b7ec  nop     dword ptr [rax+rax+00h]
0x14015b7f1  mov     rcx, [rdi]; Lookaside
0x14015b7f4  lea     rax, [rbx+0FA0h]
0x14015b7fb  mov     [rsp+60h+var_38], rax; __int64
0x14015b800  lea     r8, lbfoPrimeSwitchIfNeededWorkItem
0x14015b807  mov     r9, rbx
0x14015b80a  mov     [rsp+60h+var_40], 1Eh; __int64
0x14015b813  mov     edx, r13d
0x14015b816  call    NvIoAllocateWorkItem
0x14015b81b  test    eax, eax
0x14015b81d  jns     short loc_14015B84C
0x14015b81f  mov     eax, 0C000009Ah
0x14015b824  mov     edi, eax
0x14015b826  mov     rcx, cs:VmsIfrLog
0x14015b82d  mov     r9d, 1Fh
0x14015b833  mov     dword ptr [rsp+60h+var_38], eax
0x14015b837  mov     dl, 2
0x14015b839  mov     [rsp+60h+var_40], rsi
0x14015b83e  lea     r8d, [r9-0Bh]
0x14015b842  call    WPP_RECORDER_SF_d
0x14015b847  jmp     loc_14015B9F0
0x14015b84c  mov     cl, byte ptr cs:WPP_MAIN_CB.Queue+34h
0x14015b852  mov     al, [rbx+644h]
0x14015b858  shr     cl, 5
0x14015b85b  xor     cl, al
0x14015b85d  and     cl, r13b
0x14015b860  xor     cl, al
0x14015b862  mov     [rbx+644h], cl
0x14015b868  mov     ecx, 5
0x14015b86d  mov     edx, [r14+0Ch]
0x14015b871  mov     [rbx+5E8h], edx
0x14015b877  cmp     edx, ecx
0x14015b879  jbe     short loc_14015B885
0x14015b87b  mov     [rbx+5E8h], ecx
0x14015b881  mov     edx, ecx
0x14015b883  jmp     short loc_14015B887
0x14015b885  mov     ecx, edx
0x14015b887  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 8
0x14015b88e  jz      short loc_14015B8A7
0x14015b890  cmp     ecx, 4
0x14015b893  jb      short loc_14015B8A2
0x14015b895  mov     [rbx+5E8h], r12d
0x14015b89c  mov     ecx, r12d
0x14015b89f  mov     edx, r12d
0x14015b8a2  mov     eax, r13d
0x14015b8a5  jmp     short loc_14015B8AB
0x14015b8a7  mov     eax, [r14+8]
0x14015b8ab  mov     [rbx+5F0h], eax
0x14015b8b1  cmp     eax, 2
0x14015b8b4  jbe     short loc_14015B8BD
0x14015b8b6  mov     [rbx+5F0h], r13d
0x14015b8bd  mov     eax, edx
0x14015b8bf  lea     rdx, cs:140000000h
0x14015b8c6  mov     [rbx+938h], r13w
0x14015b8ce  mov     eax, ds:rva LbAlgoConfigToLbAlgo[rdx+rax*4]
0x14015b8d5  mov     [rbx+5ECh], eax
0x14015b8db  mov     dword ptr [rsp+60h+var_30], ecx
0x14015b8df  mov     r9d, 20h ; ' '
0x14015b8e5  mov     rcx, cs:VmsIfrLog
0x14015b8ec  mov     dl, 4
0x14015b8ee  mov     [rsp+60h+var_38], rbx
0x14015b8f3  mov     [rsp+60h+var_40], rsi
0x14015b8f8  lea     edi, [r9-0Eh]
0x14015b8fc  mov     r8d, edi
0x14015b8ff  call    WPP_RECORDER_SF_id
0x14015b904  mov     eax, [rbx+5F0h]
0x14015b90a  lea     r9d, [rdi+0Fh]
0x14015b90e  mov     rcx, cs:VmsIfrLog
0x14015b915  mov     r8d, edi
0x14015b918  mov     dword ptr [rsp+60h+var_30], eax
0x14015b91c  mov     dl, 4
0x14015b91e  mov     [rsp+60h+var_38], rbx
0x14015b923  mov     [rsp+60h+var_40], rsi
0x14015b928  call    WPP_RECORDER_SF_id
0x14015b92d  movsxd  rax, dword ptr [rbx+5ECh]
0x14015b934  lea     r13, cs:140000000h
0x14015b93b  imul    rcx, rax, 70h ; 'p'
0x14015b93f  cmp     [rcx+r13+1F3B20h], r12
0x14015b947  jz      short loc_14015B973
0x14015b949  cmp     word ptr cs:WPP_MAIN_CB.Queue+1Eh, r12w
0x14015b951  jbe     short loc_14015B973
0x14015b953  mov     rcx, [r15+130h]
0x14015b95a  lea     r8, [rbx+918h]
0x14015b961  lea     rdx, VmsTmCfgMacRebalanceTimer
0x14015b968  call    VmsTmAllocateTimer
0x14015b96d  mov     edi, eax
0x14015b96f  test    eax, eax
0x14015b971  jnz     short loc_14015B9F0
0x14015b973  movsxd  rax, dword ptr [rbx+5F0h]
0x14015b97a  lea     rcx, [rax+rax*8]
0x14015b97e  mov     rax, rva TeamingModeOperations[r13+rcx*8]
0x14015b986  test    rax, rax
0x14015b989  jz      short loc_14015B99C
0x14015b98b  mov     rdx, r14
0x14015b98e  mov     rcx, rbx
0x14015b991  call    _guard_dispatch_icall
0x14015b996  mov     edi, eax
0x14015b998  test    eax, eax
0x14015b99a  jnz     short loc_14015B9F0
0x14015b99c  movsxd  rax, dword ptr [rbx+5ECh]
0x14015b9a3  imul    rcx, rax, 70h ; 'p'
0x14015b9a7  mov     rax, [rcx+r13+1F3AC0h]
0x14015b9af  test    rax, rax
0x14015b9b2  jz      short loc_14015B9C3
0x14015b9b4  mov     rdx, r14
0x14015b9b7  mov     rcx, rbx
0x14015b9ba  call    _guard_dispatch_icall
0x14015b9bf  mov     edi, eax
0x14015b9c1  jmp     short loc_14015B9F0
0x14015b9c3  mov     edi, r12d
0x14015b9c6  jmp     short loc_14015B9F0
0x14015b9c8  mov     eax, 0C000009Ah
0x14015b9cd  mov     edi, eax
0x14015b9cf  mov     rcx, cs:VmsIfrLog
0x14015b9d6  mov     r9d, 1Dh
  ... truncated ...
```
