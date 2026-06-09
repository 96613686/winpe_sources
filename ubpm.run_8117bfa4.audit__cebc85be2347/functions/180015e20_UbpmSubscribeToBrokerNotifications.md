# UbpmSubscribeToBrokerNotifications

- ea: `0x180015e20`
- end: `0x1800166a2`
- name: `UbpmSubscribeToBrokerNotifications`
- size: `2178`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fdc8`
- `0x180015b90`

## callees

- `0x180015e20`
- `0x1800166b0`
- `0x180016720`
- `0x180016b50`
- `0x180019220`
- `0x18001af64`
- `0x180035184`
- `0x1800351ec`
- `0x180036d44`
- `0x180040260`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180016101`
- `ntdll!NtCreateWnfStateName` at `0x180016101`
- `ntdll!RtlNtStatusToDosError` at `0x180016618`
- `ntdll!RtlNtStatusToDosError` at `0x180016618`
- `ntdll!NtDeleteWnfStateName` at `0x180016684`
- `ntdll!NtDeleteWnfStateName` at `0x180016684`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015e93`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180015e93`
- `RPCRT4!UuidEqual` at `0x18001653c`
- `RPCRT4!UuidEqual` at `0x18001653c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800161b0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016589`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800161b0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016589`
- `DABAPI!DabRegisterTriggerConsumer` at `0x180016396`
- `DABAPI!DabRegisterTriggerConsumer` at `0x180016396`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x180016136`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x180016136`

## pseudocode

```c
__int64 __fastcall UbpmSubscribeToBrokerNotifications(__int64 a1)
{
  __int64 v1; // r14
  __int64 v2; // rsi
  PVOID *v3; // rcx
  int i; // edx
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r13
  char v15; // si
  int v16; // r15d
  unsigned int j; // edi
  __int64 v18; // rbx
  _DWORD *v19; // rax
  __int64 v20; // rcx
  int IsCriticalAction; // eax
  __int64 v22; // rcx
  const WCHAR *v23; // rdi
  char v24; // r12
  const WCHAR *lpString2; // r14
  __int64 cchCount2; // rsi
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rax
  __int128 v30; // xmm6
  __int128 v31; // xmm7
  __int128 v32; // xmm8
  NTSTATUS v33; // eax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // r9
  char v37; // bl
  int v38; // eax
  __int64 v39; // rdx
  unsigned int AggEventWithConstraints; // ebx
  _QWORD *v41; // rcx
  int v43; // ecx
  _BYTE *v44; // rdx
  __int64 v45; // rdi
  __int64 v46; // rcx
  unsigned int v47; // eax
  __int64 v48; // rax
  __int64 v49; // rdi
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // r9
  int v53; // edx
  ULONG v54; // eax
  __int64 v55; // rcx
  int v56; // [rsp+48h] [rbp-C0h] BYREF
  int v57; // [rsp+4Ch] [rbp-BCh]
  __int64 v58; // [rsp+50h] [rbp-B8h]
  RPC_STATUS Status[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+60h] [rbp-A8h]
  _BYTE *v61; // [rsp+68h] [rbp-A0h]
  __int64 v62; // [rsp+70h] [rbp-98h]
  _OWORD v63[3]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-60h]
  __int64 v65; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v66; // [rsp+C0h] [rbp-48h]
  __int128 v67; // [rsp+D0h] [rbp-38h]
  __int128 v68; // [rsp+E0h] [rbp-28h]
  __int64 v69; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v70; // [rsp+100h] [rbp-8h] BYREF
  __int64 v71; // [rsp+108h] [rbp+0h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v2 = a1;
  v60 = a1;
  v62 = v1;
  v69 = 0;
  memset(v63, 0, sizeof(v63));
  v70 = 0;
  v71 = 0;
  LOBYTE(v56) = 0;
  if ( InitOnceExecuteOnce(&g_ioInitBrokers, UbpmpInitBrokers, 0, 0) )
  {
    v61 = (_BYTE *)(v2 + 40);
    if ( *(_QWORD *)(v1 + 48) )
    {
      *(_QWORD *)Status = 0;
      UbpmMaintenanceGetUrgencyLevel(v2, &v56, Status);
      *(_BYTE *)(v2 + 40) = v56;
    }
    else
    {
      v61 = (_BYTE *)(v2 + 40);
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
    for ( i = 0; ; LOWORD(i) = v58 + 1 )
    {
      LODWORD(v58) = i;
      if ( (unsigned int)(unsigned __int16)i >= *(_DWORD *)(v1 + 20) )
      {
        AggEventWithConstraints = 0;
        goto LABEL_54;
      }
      v5 = (unsigned __int16)i;
      v6 = *(_QWORD *)(v1 + 24);
      v7 = 48 * v5;
      v64 = 48 * v5;
      v8 = *(_DWORD *)(v6 + 48 * v5);
      if ( v8 == 3 )
      {
        v9 = *(unsigned __int8 *)(v2 + 40);
        if ( (unsigned __int8)v9 >= 5u )
          MicrosoftTelemetryAssertTriggeredNoArgs(v3);
        v10 = 2 * v9;
        v11 = 16 * v9;
        if ( !*(_DWORD *)((char *)&g_MaintenanceTriggers + v11 + 8)
          && !*((_DWORD *)&g_MaintenanceTriggers + 2 * v10 + 3) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v3);
        }
        v12 = *(__int64 *)((char *)&g_MaintenanceTriggers + v11 + 8);
        v13 = 40 * v5;
        *(_DWORD *)(v13 + *(_QWORD *)(v2 + 32) + 24) = 3;
        *(_QWORD *)(v13 + *(_QWORD *)(v2 + 32) + 16) = v12;
        goto LABEL_11;
      }
      v28 = v8 - 1;
      if ( !v28 )
        break;
      if ( v28 == 1 )
      {
        v29 = *(_QWORD *)(v6 + v7 + 8);
        v30 = *(_OWORD *)(v29 + 8);
        v31 = *(_OWORD *)(v29 + 24);
        v32 = *(_OWORD *)(v29 + 40);
        v33 = NtCreateWnfStateName(&v69, 3, 0, 0, 0, 4096, g_pSecurityDescriptor);
        if ( v33 < 0 )
        {
          v54 = RtlNtStatusToDosError(v33);
          AggEventWithConstraints = v54;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
              *(_QWORD *)(v1 + 8),
              v54);
          goto LABEL_54;
        }
        v65 = v69;
        v66 = v30;
        v67 = v31;
        v68 = v32;
        v34 = CSebCreatePrivateEvent(&v65, &v70);
        if ( v34 < 0 )
        {
          AggEventWithConstraints = (unsigned __int16)v34;
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_54;
          v52 = *(_QWORD *)(v1 + 8);
          v53 = 31;
LABEL_107:
          WPP_SF_Sd(
            v41[2],
            v53,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            v52,
            AggEventWithConstraints);
          goto LABEL_54;
        }
        v12 = 40 * v5;
        *(_QWORD *)(v12 + *(_QWORD *)(v2 + 32) + 32) = v69;
        v35 = *(_QWORD *)(v2 + 32);
        v69 = 0;
        *(_DWORD *)(v12 + v35 + 24) = 2;
        *(_QWORD *)(v12 + *(_QWORD *)(v2 + 32) + 16) = v70;
        goto LABEL_11;
      }
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      {
        WPP_SF_S(v3[2], 34, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, *(_QWORD *)(v1 + 8));
LABEL_51:
        v3 = (PVOID *)WPP_GLOBAL_Control;
      }
      HIWORD(i) = WORD1(v58);
    }
    v43 = v63[1];
    v63[0] = *(_OWORD *)v1;
    if ( (*(_BYTE *)(v1 + 16) & 0x40) != 0 )
    {
      v43 = LODWORD(v63[1]) | 1;
      LODWORD(v63[1]) |= 1u;
    }
    v44 = *(_BYTE **)(*(_QWORD *)(v1 + 40) + 32LL);
    if ( v44 )
    {
      if ( (*v44 & 0x10) != 0 )
      {
        LODWORD(v63[1]) = v43 | 2;
        if ( UbpmUtilsSearchMultiString(*(PCNZWCH *)(v1 + 8), g_CriticalTasks) )
          LODWORD(v63[1]) |= 0x20u;
      }
    }
    *(_OWORD *)((char *)&v63[1] + 4) = *(_OWORD *)(v1 + 60);
    *((_QWORD *)&v63[2] + 1) = *(_QWORD *)(*(_QWORD *)(v1 + 24) + v7 + 8);
    v45 = 40 * v5;
    v46 = *(_QWORD *)(v2 + 32) + 32LL;
    DWORD1(v63[2]) = 1;
    v47 = DabRegisterTriggerConsumer(0xFFFF, 1, v63, &v71, v45 + v46);
    AggEventWithConstraints = v47;
    if ( v47 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(v1 + 8),
          v47);
      goto LABEL_54;
    }
    *(_DWORD *)(v45 + *(_QWORD *)(v2 + 32) + 24) = 1;
    *(_QWORD *)(v45 + *(_QWORD *)(v2 + 32) + 16) = v71;
LABEL_11:
    v14 = *(_QWORD *)(v2 + 24);
    LOBYTE(v12) = 0;
    v15 = 0;
    Status[0] = 0;
    v16 = 0;
    v57 = v12;
    for ( j = 0; j < *(_DWORD *)(v14 + 32); ++j )
    {
      v18 = *(_QWORD *)(v14 + 40) + 40LL * j;
      v19 = *(_DWORD **)(v18 + 32);
      if ( v19 )
        v16 |= *v19;
      if ( *(_DWORD *)(v18 + 16) == 1 )
      {
        v20 = *(_QWORD *)(v18 + 24);
        if ( *(_DWORD *)v20 == 2 )
        {
          IsCriticalAction = UbpmpIsCriticalAction(*(UUID **)(v20 + 8));
          LOBYTE(v12) = v57;
          if ( IsCriticalAction )
            v15 = 1;
        }
        if ( *(_DWORD *)(v18 + 16) == 1 )
        {
          v22 = *(_QWORD *)(*(_QWORD *)(v18 + 24) + 32LL);
          if ( v22 )
          {
            LODWORD(v12) = (unsigned __int8)v12;
            if ( *(_DWORD *)(v22 + 32) == 2 )
              LODWORD(v12) = 1;
            v57 = v12;
          }
        }
      }
    }
    if ( v15 )
    {
LABEL_41:
      v24 = 1;
    }
    else
    {
      v23 = g_CriticalTasks;
      v24 = 0;
      if ( !g_CriticalTasks || (lpString2 = *(const WCHAR **)(v14 + 8)) == 0 )
      {
LABEL_43:
        v37 = v12;
        if ( (v16 & 0x40) != 0 )
          v37 = 0;
        if ( *(_QWORD *)(v14 + 48) )
        {
          switch ( *v61 )
          {
            case 0:
            case 1:
            case 2:
              v38 = 198;
              break;
            case 3:
              v38 = 49344;
              break;
            case 4:
              v38 = 49152;
              break;
            default:
              v38 = 0;
              break;
          }
          v2 = v60;
          v16 |= v38;
LABEL_49:
          v39 = *(_QWORD *)(v2 + 32) + 40LL * (unsigned __int16)v58;
          AggEventWithConstraints = UbpmCreateAggEventWithConstraints(
                                      v16,
                                      *(_QWORD *)(v39 + 16),
                                      (unsigned int)UbpmpTriggerArrived,
                                      (unsigned int)&UbpmpTriggerCancelled,
                                      v2,
                                      v39,
                                      v39 + 8,
                                      *(_QWORD *)(*(_QWORD *)(v2 + 24) + 8LL));
          if ( AggEventWithConstraints )
          {
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_54;
            v53 = 35;
            v52 = *(_QWORD *)(v62 + 8);
            goto LABEL_107;
          }
          v1 = v62;
          goto LABEL_51;
        }
        v48 = *(_QWORD *)(v14 + 24);
        v49 = v64;
        if ( *(_DWORD *)(v48 + v64) == 1
          && (v50 = *(_QWORD *)(v48 + v64 + 8), *(_DWORD *)(v50 + 56) == 1)
          && UuidEqual(**(UUID ***)(v50 + 64), (UUID *)&IDLE_TRIGGER_PROVIDER_GUID, Status)
          && !Status[0] )
        {
          v2 = v60;
        }
        else
        {
          v2 = v60;
          v51 = *(_QWORD *)(*(_QWORD *)(v60 + 24) + 24LL);
          if ( *(_DWORD *)(v51 + v49) != 2 || *(_DWORD *)(*(_QWORD *)(v51 + v49 + 8) + 12LL) != 4102 )
          {
LABEL_71:
            if ( !v24 )
            {
              if ( !v37 )
                v16 |= 0x4000u;
              v16 |= 0x800u;
            }
            goto LABEL_49;
          }
        }
        v16 |= 0x80u;
        goto LABEL_71;
      }
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( lpString2[cchCount2] );
      while ( *v23 )
      {
        v27 = -1;
        do
          ++v27;
        while ( v23[v27] );
        if ( (unsigned int)cchCount2 >= (unsigned int)v27 )
        {
          v36 = (unsigned int)(v27 - 1);
          if ( v23[v36] == 42 )
          {
            if ( CompareStringW(0x7Fu, 1u, v23, v36, lpString2, v27 - 1) == 2 )
              goto LABEL_41;
          }
          else if ( (_DWORD)cchCount2 == (_DWORD)v27 && CompareStringW(0x7Fu, 1u, v23, v27, lpString2, cchCount2) == 2 )
          {
            goto LABEL_41;
          }
        }
        v23 += (unsigned int)(v27 + 1);
      }
    }
    LOBYTE(v12) = v57;
    goto LABEL_43;
  }
  AggEventWithConstraints = 1359;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, 1359);
LABEL_54:
  if ( v69 && (int)NtDeleteWnfStateName(&v69) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v55);
  return AggEventWithConstraints;
}

```

## disassembly

```asm
0x180015e20  mov     r11, rsp
0x180015e23  push    rbp
0x180015e24  push    rbx
0x180015e25  lea     rbp, [r11-68h]
0x180015e29  sub     rsp, 158h
0x180015e30  mov     rax, cs:__security_cookie
0x180015e37  xor     rax, rsp
0x180015e3a  mov     qword ptr [rbp+60h+var_58], rax
0x180015e3e  mov     [r11+10h], rsi
0x180015e42  lea     rdx, ?UbpmpInitBrokers@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180015e49  xorps   xmm0, xmm0
0x180015e4c  mov     [r11+20h], r12
0x180015e50  xor     r12d, r12d
0x180015e53  mov     [r11-20h], r14
0x180015e57  mov     r14, [rcx+18h]
0x180015e5b  mov     rsi, rcx
0x180015e5e  mov     [rsp+160h+var_108], rcx
0x180015e63  xor     r9d, r9d; Context
0x180015e66  lea     rcx, ?g_ioInitBrokers@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180015e6d  mov     qword ptr [rsp+160h+var_F8], r14
0x180015e72  xor     r8d, r8d; Parameter
0x180015e75  mov     [rbp+60h+var_70], r12
0x180015e79  movups  xmmword ptr [rsp+160h+var_F8+8], xmm0
0x180015e7e  mov     [rbp+60h+var_68], r12
0x180015e82  movups  [rbp+60h+var_E0], xmm0
0x180015e86  mov     [rbp+60h+var_60], r12
0x180015e8a  movups  [rbp+60h+var_D0], xmm0
0x180015e8e  mov     byte ptr [rsp+160h+var_120], r12b
0x180015e93  call    cs:__imp_InitOnceExecuteOnce
0x180015e9a  nop     dword ptr [rax+rax+00h]
0x180015e9f  test    eax, eax
0x180015ea1  jz      loc_1800163CD
0x180015ea7  lea     rbx, [rsi+28h]
0x180015eab  mov     [rsp+160h+arg_10], rdi
0x180015eb3  mov     [rsp+150h], r13
0x180015ebb  mov     [rsp+160h+var_20], r15
0x180015ec3  mov     [rsp+160h+var_100], rbx
0x180015ec8  cmp     [r14+30h], r12
0x180015ecc  jz      loc_180016418
0x180015ed2  lea     r8, [rsp+160h+Status]
0x180015ed7  mov     qword ptr [rsp+160h+Status], r12
0x180015edc  lea     rdx, [rsp+160h+var_120]
0x180015ee1  mov     rcx, rsi
0x180015ee4  call    UbpmMaintenanceGetUrgencyLevel
0x180015ee9  movzx   eax, byte ptr [rsp+160h+var_120]
0x180015eee  mov     [rbx], al
0x180015ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ef7  lea     r15, WPP_GLOBAL_Control
0x180015efe  movaps  [rsp+160h+var_38+8], xmm6
0x180015f06  lea     r13, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x180015f0d  movaps  [rsp+160h+var_48+8], xmm7
0x180015f15  mov     edx, r12d
0x180015f18  movaps  [rsp+160h+var_58+8], xmm8
0x180015f21  mov     r10d, 1
0x180015f27  movzx   eax, dx
0x180015f2a  mov     dword ptr [rsp+160h+var_118], edx
0x180015f2e  cmp     eax, [r14+14h]
0x180015f32  jnb     loc_180016410
0x180015f38  movzx   edi, dx
0x180015f3b  mov     rdx, [r14+18h]
0x180015f3f  lea     rbx, [rdi+rdi*2]
0x180015f43  shl     rbx, 4
0x180015f47  mov     [rbp+60h+var_C0], rbx
0x180015f4b  mov     eax, [rdx+rbx]
0x180015f4e  cmp     eax, 3
0x180015f51  jnz     loc_1800160B5
0x180015f57  movzx   ebx, byte ptr [rsi+28h]
0x180015f5b  cmp     bl, 5
0x180015f5e  jnb     loc_1800165D4
0x180015f64  mov     rax, rbx
0x180015f67  add     rax, rax
0x180015f6a  lea     rbx, ds:0[rax*8]
0x180015f72  cmp     dword ptr [rbx+r13+8], 0
0x180015f78  jz      loc_1800165E4
0x180015f7e  mov     rdx, [rbx+r13+8]
0x180015f83  lea     rax, [rdi+rdi*4]
0x180015f87  lea     rcx, ds:0[rax*8]
0x180015f8f  mov     rax, [rsi+20h]
0x180015f93  mov     dword ptr [rcx+rax+18h], 3
0x180015f9b  mov     rax, [rsi+20h]
0x180015f9f  mov     [rcx+rax+10h], rdx
0x180015fa4  mov     r13, [rsi+18h]
0x180015fa8  xor     dl, dl
0x180015faa  xor     sil, sil
0x180015fad  mov     [rsp+160h+Status], r12d
0x180015fb2  mov     r15d, r12d
0x180015fb5  mov     [rsp+160h+var_11C], edx
0x180015fb9  mov     edi, r12d
0x180015fbc  cmp     dword ptr [r13+20h], 0
0x180015fc1  jbe     short loc_180016032
0x180015fc3  nop     dword ptr [rax+00h]
0x180015fc7  nop     word ptr [rax+rax+00000000h]
0x180015fd0  mov     eax, edi
0x180015fd2  lea     rcx, [rax+rax*4]
0x180015fd6  mov     rax, [r13+28h]
0x180015fda  lea     rbx, [rax+rcx*8]
0x180015fde  mov     rax, [rax+rcx*8+20h]
0x180015fe3  test    rax, rax
0x180015fe6  jz      short loc_180015FEB
0x180015fe8  or      r15d, [rax]
0x180015feb  cmp     dword ptr [rbx+10h], 1
0x180015fef  jnz     short loc_18001602A
0x180015ff1  mov     rcx, [rbx+18h]
0x180015ff5  cmp     dword ptr [rcx], 2
0x180015ff8  jnz     short loc_180016017
0x180015ffa  mov     rcx, [rcx+8]; Uuid2
0x180015ffe  call    ?UbpmpIsCriticalAction@@YAHPEAU_GUID@@@Z; UbpmpIsCriticalAction(_GUID *)
0x180016003  mov     edx, [rsp+160h+var_11C]
0x180016007  test    eax, eax
0x180016009  movzx   esi, sil
0x18001600d  mov     r10d, 1
0x180016013  cmovnz  esi, r10d
0x180016017  cmp     dword ptr [rbx+10h], 1
0x18001601b  jnz     short loc_18001602A
0x18001601d  mov     rax, [rbx+18h]
0x180016021  mov     rcx, [rax+20h]
0x180016025  test    rcx, rcx
0x180016028  jnz     short loc_1800160A1
0x18001602a  inc     edi
0x18001602c  cmp     edi, [r13+20h]
0x180016030  jb      short loc_180015FD0
0x180016032  test    sil, sil
0x180016035  jnz     loc_1800161C5
0x18001603b  mov     rdi, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x180016042  xor     r12b, r12b
0x180016045  test    rdi, rdi
0x180016048  jz      loc_1800161CC
0x18001604e  mov     r14, [r13+8]
0x180016052  test    r14, r14
0x180016055  jz      loc_1800161CC
0x18001605b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180016062  inc     rsi
0x180016065  cmp     word ptr [r14+rsi*2], 0
0x18001606b  jnz     short loc_180016062
0x18001606d  nop     dword ptr [rax]
0x180016070  cmp     word ptr [rdi], 0
0x180016074  jz      loc_1800161C8
0x18001607a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180016081  inc     rbx
0x180016084  cmp     word ptr [rdi+rbx*2], 0
0x180016089  jnz     short loc_180016081
0x18001608b  cmp     esi, ebx
0x18001608d  jnb     loc_18001618B
0x180016093  inc     ebx
0x180016095  mov     r10d, 1
0x18001609b  lea     rdi, [rdi+rbx*2]
0x18001609f  jmp     short loc_180016070
0x1800160a1  cmp     dword ptr [rcx+20h], 2
0x1800160a5  movzx   edx, dl
0x1800160a8  cmovz   edx, r10d
0x1800160ac  mov     [rsp+160h+var_11C], edx
0x1800160b0  jmp     loc_18001602A
0x1800160b5  sub     eax, 1
0x1800160b8  jz      loc_180016311
0x1800160be  cmp     eax, 1
0x1800160c1  jnz     loc_1800165A3
0x1800160c7  mov     rax, [rdx+rbx+8]
0x1800160cc  lea     rcx, [rbp+60h+var_70]
0x1800160d0  xor     r9d, r9d
0x1800160d3  xor     r8d, r8d
0x1800160d6  mov     edx, 3
0x1800160db  movups  xmm6, xmmword ptr [rax+8]
0x1800160df  movups  xmm7, xmmword ptr [rax+18h]
0x1800160e3  movups  xmm8, xmmword ptr [rax+28h]
0x1800160e8  mov     rax, cs:?g_pSecurityDescriptor@@3PEAXEA; void * g_pSecurityDescriptor
0x1800160ef  mov     [rsp+160h+var_130], rax
0x1800160f4  mov     [rsp+160h+cchCount2], 1000h
0x1800160fc  mov     [rsp+160h+lpString2], r12
0x180016101  call    cs:__imp_NtCreateWnfStateName
0x180016108  nop     dword ptr [rax+rax+00h]
0x18001610d  test    eax, eax
0x18001610f  js      loc_180016616
0x180016115  mov     ecx, dword ptr [rbp+60h+var_70+4]
0x180016118  lea     rdx, [rbp+60h+var_68]
0x18001611c  mov     eax, dword ptr [rbp+60h+var_70]
0x18001611f  mov     dword ptr [rbp+60h+var_B0+4], ecx
0x180016122  lea     rcx, [rbp+60h+var_B0]
0x180016126  mov     dword ptr [rbp+60h+var_B0], eax
0x180016129  movups  [rbp+60h+var_A8], xmm6
0x18001612d  movups  [rbp+60h+var_98], xmm7
0x180016131  movups  [rbp+60h+var_88], xmm8
0x180016136  call    cs:__imp_CSebCreatePrivateEvent
0x18001613d  nop     dword ptr [rax+rax+00h]
0x180016142  test    eax, eax
0x180016144  js      loc_1800164D2
0x18001614a  mov     rcx, [rsi+20h]
0x18001614e  lea     rax, [rdi+rdi*4]
0x180016152  lea     rdx, ds:0[rax*8]
0x18001615a  mov     r10d, 1
0x180016160  mov     rax, [rbp+60h+var_70]
0x180016164  mov     [rdx+rcx+20h], rax
0x180016169  mov     rax, [rsi+20h]
0x18001616d  mov     [rbp+60h+var_70], r12
0x180016171  mov     dword ptr [rdx+rax+18h], 2
0x180016179  mov     rcx, [rsi+20h]
0x18001617d  mov     rax, [rbp+60h+var_68]
0x180016181  mov     [rdx+rcx+10h], rax
0x180016186  jmp     loc_180015FA4
0x18001618b  lea     r9d, [rbx-1]; cchCount1
0x18001618f  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180016195  jnz     loc_18001656A
0x18001619b  mov     [rsp+160h+cchCount2], r9d; cchCount2
0x1800161a0  mov     r8, rdi; lpString1
0x1800161a3  mov     edx, r10d; dwCmpFlags
0x1800161a6  mov     [rsp+160h+lpString2], r14; lpString2
0x1800161ab  mov     ecx, 7Fh; Locale
0x1800161b0  call    cs:__imp_CompareStringW
0x1800161b7  nop     dword ptr [rax+rax+00h]
0x1800161bc  cmp     eax, 2
0x1800161bf  jnz     loc_180016093
0x1800161c5  mov     r12b, 1
0x1800161c8  mov     edx, [rsp+160h+var_11C]
0x1800161cc  test    r15b, 40h
0x1800161d0  movzx   ebx, dl
0x1800161d3  mov     eax, 0
0x1800161d8  cmovnz  ebx, eax
0x1800161db  cmp     [r13+30h], rax
0x1800161df  jz      loc_180016422
0x1800161e5  mov     rax, [rsp+160h+var_100]
0x1800161ea  movzx   ecx, byte ptr [rax]
0x1800161ed  test    ecx, ecx
0x1800161ef  jnz     loc_180016480
0x1800161f5  mov     eax, 0C6h
0x1800161fa  mov     rsi, [rsp+160h+var_108]
0x1800161ff  or      r15d, eax
0x180016202  mov     ecx, dword ptr [rsp+160h+var_118]
0x180016206  lea     r9, UbpmpTriggerCancelled
0x18001620d  movzx   eax, cx
0x180016210  mov     ecx, r15d
0x180016213  lea     rdx, [rax+rax*4]
0x180016217  mov     rax, [rsi+20h]
0x18001621b  lea     rdx, [rax+rdx*8]
0x18001621f  mov     rax, [rsi+18h]
0x180016223  lea     r8, [rdx+8]
0x180016227  mov     rax, [rax+8]
0x18001622b  mov     qword ptr [rsp+160h+var_128], rax
0x180016230  mov     [rsp+160h+var_130], r8
0x180016235  lea     r8, UbpmpTriggerArrived
0x18001623c  mov     qword ptr [rsp+160h+cchCount2], rdx
0x180016241  mov     rdx, [rdx+10h]
0x180016245  mov     [rsp+160h+lpString2], rsi
0x18001624a  call    UbpmCreateAggEventWithConstraints
0x18001624f  mov     ebx, eax
0x180016251  test    eax, eax
0x180016253  jnz     short loc_180016284
0x180016255  mov     r14, qword ptr [rsp+160h+var_F8]
0x18001625a  lea     r15, WPP_GLOBAL_Control
0x180016261  xor     r12d, r12d
0x180016264  lea     r13, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x18001626b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016272  mov     r10d, 1
0x180016278  mov     edx, dword ptr [rsp+160h+var_118]
0x18001627c  inc     dx
0x18001627f  jmp     loc_180015F27
0x180016284  mov     rcx, cs:WPP_GLOBAL_Control
0x18001628b  lea     rax, WPP_GLOBAL_Control
0x180016292  cmp     rcx, rax
0x180016295  jnz     loc_18001664F
0x18001629b  movaps  xmm7, [rsp+160h+var_48+8]
0x1800162a3  movaps  xmm6, [rsp+160h+var_38+8]
0x1800162ab  movaps  xmm8, [rsp+160h+var_58+8]
0x1800162b4  mov     r13, [rsp+150h]
0x1800162bc  mov     rdi, [rsp+160h+arg_10]
0x1800162c4  mov     r15, [rsp+160h+var_20]
0x1800162cc  cmp     dword ptr [rbp+60h+var_70], 0
0x1800162d0  mov     r14, [rsp+160h+var_18]
0x1800162d8  mov     r12, [rsp+160h+arg_18]
0x1800162e0  mov     rsi, [rsp+160h+arg_8]
0x1800162e8  jnz     loc_180016680
0x1800162ee  cmp     dword ptr [rbp+60h+var_70+4], 0
0x1800162f2  jnz     loc_180016680
0x1800162f8  mov     eax, ebx
0x1800162fa  mov     rcx, qword ptr [rbp+60h+var_58]
0x1800162fe  xor     rcx, rsp; StackCookie
0x180016301  call    __security_check_cookie
0x180016306  add     rsp, 158h
0x18001630d  pop     rbx
0x18001630e  pop     rbp
0x18001630f  retn
0x180016311  mov     rax, [r14]
0x180016314  mov     ecx, dword ptr [rbp+60h+var_E0]
0x180016317  mov     qword ptr [rsp+160h+var_F8+8], rax
0x18001631c  mov     rax, [r14+8]
0x180016320  mov     qword ptr [rsp+160h+var_F8+10h], rax
0x180016325  test    byte ptr [r14+10h], 40h
0x18001632a  jz      short loc_180016332
0x18001632c  or      ecx, 1
0x18001632f  mov     dword ptr [rbp+60h+var_E0], ecx
0x180016332  mov     rax, [r14+28h]
0x180016336  mov     rdx, [rax+20h]
0x18001633a  test    rdx, rdx
0x18001633d  jz      short loc_180016348
0x18001633f  test    byte ptr [rdx], 10h
0x180016342  jnz     loc_1800164A5
0x180016348  mov     rax, [r14+44h]
0x18001634c  lea     r9, [rbp+60h+var_60]
0x180016350  mov     qword ptr [rbp+60h+var_E0+0Ch], rax
0x180016354  lea     r8, [rsp+160h+var_F8+8]
0x180016359  mov     rax, [r14+3Ch]
0x18001635d  mov     edx, r10d
  ... truncated ...
```
