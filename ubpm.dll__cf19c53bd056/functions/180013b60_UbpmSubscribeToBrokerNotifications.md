# UbpmSubscribeToBrokerNotifications

- ea: `0x180013b60`
- end: `0x1800143a1`
- name: `UbpmSubscribeToBrokerNotifications`
- size: `2113`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800136f4`
- `0x1800138e0`

## callees

- `0x180013180`
- `0x180013b60`
- `0x1800143b0`
- `0x180014420`
- `0x180014840`
- `0x18001e9f4`
- `0x180032dd8`
- `0x180032e38`
- `0x18003488c`
- `0x18003d810`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180013e31`
- `ntdll!NtCreateWnfStateName` at `0x180013e31`
- `ntdll!RtlNtStatusToDosError` at `0x180014323`
- `ntdll!RtlNtStatusToDosError` at `0x180014323`
- `ntdll!NtDeleteWnfStateName` at `0x180014389`
- `ntdll!NtDeleteWnfStateName` at `0x180014389`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013bd3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180013bd3`
- `RPCRT4!UuidEqual` at `0x180014253`
- `RPCRT4!UuidEqual` at `0x180014253`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013ed4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001429a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013ed4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001429a`
- `DABAPI!DabRegisterTriggerConsumer` at `0x1800140b3`
- `DABAPI!DabRegisterTriggerConsumer` at `0x1800140b3`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x180013e60`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x180013e60`

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
0x180013b60  mov     r11, rsp
0x180013b63  push    rbp
0x180013b64  push    rbx
0x180013b65  lea     rbp, [r11-68h]
0x180013b69  sub     rsp, 158h
0x180013b70  mov     rax, cs:__security_cookie
0x180013b77  xor     rax, rsp
0x180013b7a  mov     qword ptr [rbp+60h+var_58], rax
0x180013b7e  mov     [r11+10h], rsi
0x180013b82  lea     rdx, ?UbpmpInitBrokers@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180013b89  xorps   xmm0, xmm0
0x180013b8c  mov     [r11+20h], r12
0x180013b90  xor     r12d, r12d
0x180013b93  mov     [r11-20h], r14
0x180013b97  mov     r14, [rcx+18h]
0x180013b9b  mov     rsi, rcx
0x180013b9e  mov     [rsp+160h+var_108], rcx
0x180013ba3  xor     r9d, r9d; Context
0x180013ba6  lea     rcx, ?g_ioInitBrokers@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180013bad  mov     qword ptr [rsp+160h+var_F8], r14
0x180013bb2  xor     r8d, r8d; Parameter
0x180013bb5  mov     [rbp+60h+var_70], r12
0x180013bb9  movups  xmmword ptr [rsp+160h+var_F8+8], xmm0
0x180013bbe  mov     [rbp+60h+var_68], r12
0x180013bc2  movups  [rbp+60h+var_E0], xmm0
0x180013bc6  mov     [rbp+60h+var_60], r12
0x180013bca  movups  [rbp+60h+var_D0], xmm0
0x180013bce  mov     byte ptr [rsp+160h+var_120], r12b
0x180013bd3  call    cs:__imp_InitOnceExecuteOnce
0x180013bd9  test    eax, eax
0x180013bdb  jz      loc_1800140E4
0x180013be1  lea     rbx, [rsi+28h]
0x180013be5  mov     [rsp+160h+arg_10], rdi
0x180013bed  mov     [rsp+150h], r13
0x180013bf5  mov     [rsp+160h+var_20], r15
0x180013bfd  mov     [rsp+160h+var_100], rbx
0x180013c02  cmp     [r14+30h], r12
0x180013c06  jz      loc_18001412F
0x180013c0c  lea     r8, [rsp+160h+Status]
0x180013c11  mov     qword ptr [rsp+160h+Status], r12
0x180013c16  lea     rdx, [rsp+160h+var_120]
0x180013c1b  mov     rcx, rsi
0x180013c1e  call    UbpmMaintenanceGetUrgencyLevel
0x180013c23  movzx   eax, byte ptr [rsp+160h+var_120]
0x180013c28  mov     [rbx], al
0x180013c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c31  lea     r15, WPP_GLOBAL_Control
0x180013c38  movaps  [rsp+160h+var_38+8], xmm6
0x180013c40  lea     r13, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x180013c47  movaps  [rsp+160h+var_48+8], xmm7
0x180013c4f  mov     edx, r12d
0x180013c52  movaps  [rsp+160h+var_58+8], xmm8
0x180013c5b  mov     r10d, 1
0x180013c61  movzx   eax, dx
0x180013c64  mov     dword ptr [rsp+160h+var_118], edx
0x180013c68  cmp     eax, [r14+14h]
0x180013c6c  jnb     loc_180014127
0x180013c72  movzx   edi, dx
0x180013c75  mov     rdx, [r14+18h]
0x180013c79  lea     rbx, [rdi+rdi*2]
0x180013c7d  shl     rbx, 4
0x180013c81  mov     [rbp+60h+var_C0], rbx
0x180013c85  mov     eax, [rdx+rbx]
0x180013c88  cmp     eax, 3
0x180013c8b  jnz     loc_180013DE5
0x180013c91  movzx   ebx, byte ptr [rsi+28h]
0x180013c95  cmp     bl, 5
0x180013c98  jnb     loc_1800142DF
0x180013c9e  mov     rax, rbx
0x180013ca1  add     rax, rax
0x180013ca4  lea     rbx, ds:0[rax*8]
0x180013cac  cmp     dword ptr [rbx+r13+8], 0
0x180013cb2  jz      loc_1800142EF
0x180013cb8  mov     rdx, [rbx+r13+8]
0x180013cbd  lea     rax, [rdi+rdi*4]
0x180013cc1  lea     rcx, ds:0[rax*8]
0x180013cc9  mov     rax, [rsi+20h]
0x180013ccd  mov     dword ptr [rcx+rax+18h], 3
0x180013cd5  mov     rax, [rsi+20h]
0x180013cd9  mov     [rcx+rax+10h], rdx
0x180013cde  mov     r13, [rsi+18h]
0x180013ce2  xor     dl, dl
0x180013ce4  xor     sil, sil
0x180013ce7  mov     [rsp+160h+Status], r12d
0x180013cec  mov     r15d, r12d
0x180013cef  mov     [rsp+160h+var_11C], edx
0x180013cf3  mov     edi, r12d
0x180013cf6  cmp     dword ptr [r13+20h], 0
0x180013cfb  jbe     short loc_180013D62
0x180013cfd  nop     dword ptr [rax]
0x180013d00  mov     eax, edi
0x180013d02  lea     rcx, [rax+rax*4]
0x180013d06  mov     rax, [r13+28h]
0x180013d0a  lea     rbx, [rax+rcx*8]
0x180013d0e  mov     rax, [rax+rcx*8+20h]
0x180013d13  test    rax, rax
0x180013d16  jz      short loc_180013D1B
0x180013d18  or      r15d, [rax]
0x180013d1b  cmp     dword ptr [rbx+10h], 1
0x180013d1f  jnz     short loc_180013D5A
0x180013d21  mov     rcx, [rbx+18h]
0x180013d25  cmp     dword ptr [rcx], 2
0x180013d28  jnz     short loc_180013D47
0x180013d2a  mov     rcx, [rcx+8]; Uuid2
0x180013d2e  call    ?UbpmpIsCriticalAction@@YAHPEAU_GUID@@@Z; UbpmpIsCriticalAction(_GUID *)
0x180013d33  mov     edx, [rsp+160h+var_11C]
0x180013d37  test    eax, eax
0x180013d39  movzx   esi, sil
0x180013d3d  mov     r10d, 1
0x180013d43  cmovnz  esi, r10d
0x180013d47  cmp     dword ptr [rbx+10h], 1
0x180013d4b  jnz     short loc_180013D5A
0x180013d4d  mov     rax, [rbx+18h]
0x180013d51  mov     rcx, [rax+20h]
0x180013d55  test    rcx, rcx
0x180013d58  jnz     short loc_180013DD1
0x180013d5a  inc     edi
0x180013d5c  cmp     edi, [r13+20h]
0x180013d60  jb      short loc_180013D00
0x180013d62  test    sil, sil
0x180013d65  jnz     loc_180013EE3
0x180013d6b  mov     rdi, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x180013d72  xor     r12b, r12b
0x180013d75  test    rdi, rdi
0x180013d78  jz      loc_180013EEA
0x180013d7e  mov     r14, [r13+8]
0x180013d82  test    r14, r14
0x180013d85  jz      loc_180013EEA
0x180013d8b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180013d92  inc     rsi
0x180013d95  cmp     word ptr [r14+rsi*2], 0
0x180013d9b  jnz     short loc_180013D92
0x180013d9d  nop     dword ptr [rax]
0x180013da0  cmp     word ptr [rdi], 0
0x180013da4  jz      loc_180013EE6
0x180013daa  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180013db1  inc     rbx
0x180013db4  cmp     word ptr [rdi+rbx*2], 0
0x180013db9  jnz     short loc_180013DB1
0x180013dbb  cmp     esi, ebx
0x180013dbd  jnb     loc_180013EAF
0x180013dc3  inc     ebx
0x180013dc5  mov     r10d, 1
0x180013dcb  lea     rdi, [rdi+rbx*2]
0x180013dcf  jmp     short loc_180013DA0
0x180013dd1  cmp     dword ptr [rcx+20h], 2
0x180013dd5  movzx   edx, dl
0x180013dd8  cmovz   edx, r10d
0x180013ddc  mov     [rsp+160h+var_11C], edx
0x180013de0  jmp     loc_180013D5A
0x180013de5  sub     eax, 1
0x180013de8  jz      loc_18001402E
0x180013dee  cmp     eax, 1
0x180013df1  jnz     loc_1800142AE
0x180013df7  mov     rax, [rdx+rbx+8]
0x180013dfc  lea     rcx, [rbp+60h+var_70]
0x180013e00  xor     r9d, r9d
0x180013e03  xor     r8d, r8d
0x180013e06  mov     edx, 3
0x180013e0b  movups  xmm6, xmmword ptr [rax+8]
0x180013e0f  movups  xmm7, xmmword ptr [rax+18h]
0x180013e13  movups  xmm8, xmmword ptr [rax+28h]
0x180013e18  mov     rax, cs:?g_pSecurityDescriptor@@3PEAXEA; void * g_pSecurityDescriptor
0x180013e1f  mov     [rsp+160h+var_130], rax
0x180013e24  mov     [rsp+160h+cchCount2], 1000h
0x180013e2c  mov     [rsp+160h+lpString2], r12
0x180013e31  call    cs:__imp_NtCreateWnfStateName
0x180013e37  test    eax, eax
0x180013e39  js      loc_180014321
0x180013e3f  mov     ecx, dword ptr [rbp+60h+var_70+4]
0x180013e42  lea     rdx, [rbp+60h+var_68]
0x180013e46  mov     eax, dword ptr [rbp+60h+var_70]
0x180013e49  mov     dword ptr [rbp+60h+var_B0+4], ecx
0x180013e4c  lea     rcx, [rbp+60h+var_B0]
0x180013e50  mov     dword ptr [rbp+60h+var_B0], eax
0x180013e53  movups  [rbp+60h+var_A8], xmm6
0x180013e57  movups  [rbp+60h+var_98], xmm7
0x180013e5b  movups  [rbp+60h+var_88], xmm8
0x180013e60  call    cs:__imp_CSebCreatePrivateEvent
0x180013e66  test    eax, eax
0x180013e68  js      loc_1800141E9
0x180013e6e  mov     rcx, [rsi+20h]
0x180013e72  lea     rax, [rdi+rdi*4]
0x180013e76  lea     rdx, ds:0[rax*8]
0x180013e7e  mov     r10d, 1
0x180013e84  mov     rax, [rbp+60h+var_70]
0x180013e88  mov     [rdx+rcx+20h], rax
0x180013e8d  mov     rax, [rsi+20h]
0x180013e91  mov     [rbp+60h+var_70], r12
0x180013e95  mov     dword ptr [rdx+rax+18h], 2
0x180013e9d  mov     rcx, [rsi+20h]
0x180013ea1  mov     rax, [rbp+60h+var_68]
0x180013ea5  mov     [rdx+rcx+10h], rax
0x180013eaa  jmp     loc_180013CDE
0x180013eaf  lea     r9d, [rbx-1]; cchCount1
0x180013eb3  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180013eb9  jnz     loc_18001427B
0x180013ebf  mov     [rsp+160h+cchCount2], r9d; cchCount2
0x180013ec4  mov     r8, rdi; lpString1
0x180013ec7  mov     edx, r10d; dwCmpFlags
0x180013eca  mov     [rsp+160h+lpString2], r14; lpString2
0x180013ecf  mov     ecx, 7Fh; Locale
0x180013ed4  call    cs:__imp_CompareStringW
0x180013eda  cmp     eax, 2
0x180013edd  jnz     loc_180013DC3
0x180013ee3  mov     r12b, 1
0x180013ee6  mov     edx, [rsp+160h+var_11C]
0x180013eea  test    r15b, 40h
0x180013eee  movzx   ebx, dl
0x180013ef1  mov     eax, 0
0x180013ef6  cmovnz  ebx, eax
0x180013ef9  cmp     [r13+30h], rax
0x180013efd  jz      loc_180014139
0x180013f03  mov     rax, [rsp+160h+var_100]
0x180013f08  movzx   ecx, byte ptr [rax]
0x180013f0b  test    ecx, ecx
0x180013f0d  jnz     loc_180014197
0x180013f13  mov     eax, 0C6h
0x180013f18  mov     rsi, [rsp+160h+var_108]
0x180013f1d  or      r15d, eax
0x180013f20  mov     ecx, dword ptr [rsp+160h+var_118]
0x180013f24  lea     r9, UbpmpTriggerCancelled
0x180013f2b  movzx   eax, cx
0x180013f2e  mov     ecx, r15d
0x180013f31  lea     rdx, [rax+rax*4]
0x180013f35  mov     rax, [rsi+20h]
0x180013f39  lea     rdx, [rax+rdx*8]
0x180013f3d  mov     rax, [rsi+18h]
0x180013f41  lea     r8, [rdx+8]
0x180013f45  mov     rax, [rax+8]
0x180013f49  mov     qword ptr [rsp+160h+var_128], rax
0x180013f4e  mov     [rsp+160h+var_130], r8
0x180013f53  lea     r8, UbpmpTriggerArrived
0x180013f5a  mov     qword ptr [rsp+160h+cchCount2], rdx
0x180013f5f  mov     rdx, [rdx+10h]
0x180013f63  mov     [rsp+160h+lpString2], rsi
0x180013f68  call    UbpmCreateAggEventWithConstraints
0x180013f6d  mov     ebx, eax
0x180013f6f  test    eax, eax
0x180013f71  jnz     short loc_180013FA2
0x180013f73  mov     r14, qword ptr [rsp+160h+var_F8]
0x180013f78  lea     r15, WPP_GLOBAL_Control
0x180013f7f  xor     r12d, r12d
0x180013f82  lea     r13, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x180013f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f90  mov     r10d, 1
0x180013f96  mov     edx, dword ptr [rsp+160h+var_118]
0x180013f9a  inc     dx
0x180013f9d  jmp     loc_180013C61
0x180013fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fa9  lea     rax, WPP_GLOBAL_Control
0x180013fb0  cmp     rcx, rax
0x180013fb3  jnz     loc_180014354
0x180013fb9  movaps  xmm7, [rsp+160h+var_48+8]
0x180013fc1  movaps  xmm6, [rsp+160h+var_38+8]
0x180013fc9  movaps  xmm8, [rsp+160h+var_58+8]
0x180013fd2  mov     r13, [rsp+150h]
0x180013fda  mov     rdi, [rsp+160h+arg_10]
0x180013fe2  mov     r15, [rsp+160h+var_20]
0x180013fea  cmp     dword ptr [rbp+60h+var_70], 0
0x180013fee  mov     r14, [rsp+160h+var_18]
0x180013ff6  mov     r12, [rsp+160h+arg_18]
0x180013ffe  mov     rsi, [rsp+160h+arg_8]
0x180014006  jnz     loc_180014385
0x18001400c  cmp     dword ptr [rbp+60h+var_70+4], 0
0x180014010  jnz     loc_180014385
0x180014016  mov     eax, ebx
0x180014018  mov     rcx, qword ptr [rbp+60h+var_58]
0x18001401c  xor     rcx, rsp; StackCookie
0x18001401f  call    __security_check_cookie
0x180014024  add     rsp, 158h
0x18001402b  pop     rbx
0x18001402c  pop     rbp
0x18001402d  retn
0x18001402e  mov     rax, [r14]
0x180014031  mov     ecx, dword ptr [rbp+60h+var_E0]
0x180014034  mov     qword ptr [rsp+160h+var_F8+8], rax
0x180014039  mov     rax, [r14+8]
0x18001403d  mov     qword ptr [rsp+160h+var_F8+10h], rax
0x180014042  test    byte ptr [r14+10h], 40h
0x180014047  jz      short loc_18001404F
0x180014049  or      ecx, 1
0x18001404c  mov     dword ptr [rbp+60h+var_E0], ecx
0x18001404f  mov     rax, [r14+28h]
0x180014053  mov     rdx, [rax+20h]
0x180014057  test    rdx, rdx
0x18001405a  jz      short loc_180014065
0x18001405c  test    byte ptr [rdx], 10h
0x18001405f  jnz     loc_1800141BC
0x180014065  mov     rax, [r14+44h]
0x180014069  lea     r9, [rbp+60h+var_60]
0x18001406d  mov     qword ptr [rbp+60h+var_E0+0Ch], rax
0x180014071  lea     r8, [rsp+160h+var_F8+8]
0x180014076  mov     rax, [r14+3Ch]
0x18001407a  mov     edx, r10d
0x18001407d  mov     qword ptr [rbp+60h+var_E0+4], rax
0x180014081  mov     rax, [r14+18h]
0x180014085  mov     rcx, [rax+rbx+8]
0x18001408a  lea     rax, [rdi+rdi*4]
0x18001408e  mov     qword ptr [rbp+60h+var_D0+8], rcx
  ... truncated ...
```
