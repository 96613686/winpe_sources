# NvmeControllerPowerInitialize

- ea: `0x140113f70`
- end: `0x140114745`
- name: `NvmeControllerPowerInitialize`
- size: `2005`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14010bdc0`

## callees

- `0x1400290b0`
- `0x1400451f0`
- `0x14005285c`
- `0x1400babfc`
- `0x1400f2ba0`
- `0x1400f2fc4`
- `0x140103e74`
- `0x140113f70`
- `0x1401397b4`
- `0x14013c3f0`
- `0x14013c420`
- `0x14013c660`
- `0x14013ee34`

## import_xrefs

- `ntoskrnl!KeInitializeTimer` at `0x14011451d`
- `ntoskrnl!KeInitializeTimer` at `0x14011451d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401146da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401146f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011470e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140114728`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401146da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401146f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011470e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140114728`
- `ntoskrnl!PoFxSetComponentResidency` at `0x140114587`
- `ntoskrnl!PoFxSetComponentResidency` at `0x140114587`
- `ntoskrnl!PoFxSetComponentLatency` at `0x14011456f`
- `ntoskrnl!PoFxSetComponentLatency` at `0x14011456f`
- `ntoskrnl!KeInitializeDpc` at `0x140114557`
- `ntoskrnl!KeInitializeDpc` at `0x140114557`

## string_xrefs

- `0x140114133`: `Relative Read Throughput`
- `0x1401140f7`: `Relative Write Latency`
- `0x140114120`: `Relative Read Latency`
- `0x140114106`: `Relative Write Throughput`

## pseudocode

```c
__int64 __fastcall NvmeControllerPowerInitialize(__int64 *a1)
{
  __int64 v2; // r14
  int v3; // ecx
  __int64 v4; // r14
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // rax
  char v9; // bl
  unsigned int v10; // r12d
  int v11; // r13d
  unsigned int v12; // esi
  __int64 PowerState; // rax
  char MaxPower; // al
  __int64 v15; // r10
  char v16; // r11
  __int64 Pool; // rsi
  void *v18; // r12
  unsigned int *v19; // r15
  unsigned int v20; // edx
  char v21; // cl
  int v22; // ecx
  __int64 v23; // rdx
  unsigned int v24; // eax
  char v25; // r9
  unsigned int v26; // ecx
  __int64 v27; // rax
  char v28; // r9
  unsigned int v29; // r8d
  int v30; // r11d
  int v31; // r10d
  __int64 v32; // rcx
  unsigned __int8 v33; // cl
  int v34; // ecx
  __int64 v35; // rax
  bool v36; // cf
  char v37; // cl
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rax
  int v41; // ecx
  PVOID v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  unsigned int v45; // r8d
  unsigned int v46; // r11d
  __int64 v47; // r9
  __int64 v48; // rax
  __int64 v49; // r9
  __int64 v50; // r10
  int v51; // r11d
  __int64 *v52; // rax
  __int64 v53; // rcx
  __int64 i; // rcx
  int v55; // [rsp+28h] [rbp-C0h]
  unsigned int v56; // [rsp+A0h] [rbp-48h]
  PVOID P; // [rsp+A8h] [rbp-40h]
  unsigned int v58; // [rsp+F8h] [rbp+10h] BYREF
  bool v59; // [rsp+100h] [rbp+18h] BYREF
  unsigned int v60; // [rsp+108h] [rbp+20h]

  v59 = 0;
  if ( RuntimePowerDisabled )
    return 0;
  v2 = a1[16];
  if ( (*(_DWORD *)(*(_QWORD *)(v2 + 408) + 184LL) & 0x40000000) != 0 )
  {
    v3 = *(_DWORD *)(a1[132] + 48);
    if ( v3 == 4 )
      return 0;
    v4 = *(_QWORD *)(v2 + 168);
    if ( v3 == 3 )
    {
      NvmeGetAutoPowerStateTransition(a1);
      if ( (*(_DWORD *)(v4 + 176) & 0x800) == 0 )
      {
        NvmeSetAutoPowerStateTransition(a1, 1);
        NvmeGetAutoPowerStateTransition(a1);
      }
      return 0;
    }
    if ( *(_BYTE *)v4 == 1 )
      return 0;
    NvmeGetAutoPowerStateTransition(a1);
    if ( (*(_DWORD *)(v4 + 176) & 0x800) != 0 )
    {
      NvmeSetAutoPowerStateTransition(a1, 0);
      NvmeGetAutoPowerStateTransition(a1);
    }
    if ( !(unsigned __int8)NvmeControllerValidatePowerStates(a1) )
      return (unsigned int)-1073741436;
    v8 = a1[74];
    v9 = 0;
    v10 = 0;
    v60 = 0;
    v11 = 0;
    v56 = 0;
    v12 = 0;
    if ( *(unsigned __int8 *)(v8 + 263) != -1 )
    {
      do
      {
        LOBYTE(v6) = v12;
        PowerState = NvmeControllerGetPowerState(a1, v6);
        MaxPower = NvmeControllerPowerStateGetMaxPower(PowerState);
        v16 = *(_BYTE *)(v15 + 3);
        if ( (v16 & 2) != 0 )
        {
          ++v11;
        }
        else
        {
          ++v10;
          v60 = v12;
        }
        StorEtwNvmeControllerEvent(
          (_DWORD)a1,
          1,
          4,
          (unsigned int)L"NVMe Power State",
          (__int64)L"Max Power (uW)",
          MaxPower,
          (__int64)L"Non-Operational",
          (v16 & 2) != 0,
          (__int64)L"Entry Latency (us)",
          *(_DWORD *)(v15 + 4),
          (__int64)L"Exit Latency (us)",
          *(_DWORD *)(v15 + 8),
          (__int64)L"Relative Read Throughput",
          *(_BYTE *)(v15 + 12) & 0x1F,
          (__int64)L"Relative Read Latency",
          *(_BYTE *)(v15 + 13) & 0x1F,
          (__int64)L"Relative Write Throughput",
          *(_BYTE *)(v15 + 14) & 0x1F,
          (__int64)L"Relative Write Latency",
          *(_BYTE *)(v15 + 15) & 0x1F);
        ++v12;
      }
      while ( v12 < (unsigned int)*(unsigned __int8 *)(a1[74] + 263) + 1 );
      v9 = v60;
      v56 = v10;
    }
    Pool = RaidAllocatePool(64, (unsigned int)(32 * (v11 + 3)), 1330667858, *(_QWORD *)(a1[16] + 8));
    if ( !Pool )
      return (unsigned int)-1073741670;
    v18 = 0;
    v19 = 0;
    P = 0;
    if ( v11 )
    {
      v18 = (void *)RaidAllocatePool(72, 64, 1414095186, *(_QWORD *)(a1[16] + 8));
      if ( !v18 )
        goto LABEL_23;
      P = (PVOID)RaidAllocatePool(72, 64, 1414095186, *(_QWORD *)(a1[16] + 8));
      if ( !P )
        goto LABEL_23;
    }
    *(_DWORD *)(Pool + 12) |= 0x40u;
    v20 = 1;
    *(_DWORD *)Pool = 3;
    *(_DWORD *)(Pool + 4) = 24;
    *(_DWORD *)(Pool + 8) = 1;
    *(_DWORD *)(Pool + 24) = 2;
    *(_DWORD *)(Pool + 28) = 40;
    LOBYTE(v58) = 0;
    *(_OWORD *)(Pool + 40) = xmmword_140161450;
    if ( *(_DWORD *)(a1[132] + 48) != 5 )
      v20 = v11 + 1;
    *(_DWORD *)(Pool + 32) = v20;
    v21 = *(_BYTE *)(a1[132] + 111) & 3;
    if ( v21 )
    {
      if ( v21 == 2 )
      {
LABEL_32:
        LOBYTE(v58) = 1;
        goto LABEL_36;
      }
      if ( v21 != 1 || v20 <= 1 )
      {
LABEL_36:
        if ( *(_DWORD *)(Pool + 32) > 8u )
          *(_DWORD *)(Pool + 32) = 8;
        *(_DWORD *)(Pool + 12) |= 0x10u;
        v22 = *(_DWORD *)(Pool + 12);
        *(_DWORD *)(Pool + 16) = -1;
        v23 = *(unsigned int *)(a1[132] + 48);
        switch ( (_DWORD)v23 )
        {
          case 2:
            *(_DWORD *)(Pool + 12) = v22 | 4;
            *(_DWORD *)(v4 + 176) |= 2u;
LABEL_45:
            v24 = *(_DWORD *)(a1[132] + 48);
            if ( v24 <= 1 || v24 - 3 <= 1 )
              *(_DWORD *)(Pool + 12) |= 2u;
            *(_DWORD *)(Pool + 12) |= 8u;
            v25 = v9 + 1;
            v26 = *(_DWORD *)(Pool + 32);
            *(_DWORD *)(Pool + 64) = 1;
            *(_DWORD *)(Pool + 68) = 32;
            *(_QWORD *)(Pool + 72) = 0;
            *(_QWORD *)(Pool + 80) = 0;
            *(_DWORD *)(Pool + 60) = v26 - 1;
            *(_DWORD *)(Pool + 88) = -1;
            if ( v26 > 1 )
            {
              do
              {
                LOBYTE(v23) = v25;
                v27 = NvmeControllerGetPowerState(a1, v23);
                v25 = v28 + 1;
                v23 = 32LL * v29;
                *(_DWORD *)(32 * (v29 + 2LL) + Pool + 24) = v30;
                *(_DWORD *)(v23 + Pool + 64) = 1;
                *(_DWORD *)(v23 + Pool + 68) = v31;
                v32 = (unsigned int)(*(_DWORD *)(v27 + 4) + *(_DWORD *)(v27 + 8));
                *(_QWORD *)(v23 + Pool + 80) = 0;
                *(_QWORD *)(v23 + Pool + 72) = 10 * v32;
              }
              while ( v29 + 1 < *(_DWORD *)(Pool + 32) );
            }
            v7 = NvmeAdapterInitializePoFx(a1[16], (const signed __int32 *)Pool, &v59);
            if ( v7 < 0 )
              goto LABEL_66;
            v33 = 8 * v59;
            *(_BYTE *)(*(_QWORD *)(v4 + 8) + 64LL) = 1;
            v34 = *(_DWORD *)(v4 + 176) ^ ((unsigned __int8)*(_DWORD *)(v4 + 176) ^ v33) & 8;
            v35 = *(_QWORD *)(v4 + 8);
            v36 = (_BYTE)v58 != 0;
            LOBYTE(v58) = -(char)v58;
            *(_DWORD *)(v4 + 176) = v34;
            *(_DWORD *)(v35 + 16) = *(unsigned __int8 *)(Pool + 32);
            v37 = v60;
            *(_DWORD *)(*(_QWORD *)(v4 + 8) + 68LL) = 0;
            v38 = *(_QWORD *)(v4 + 8);
            *(_WORD *)(v4 + 181) = 0;
            *(_DWORD *)(v4 + 200) = v36 ? 10 : 200;
            *(_DWORD *)(v4 + 196) = 15;
            *(_DWORD *)(v4 + 188) = 15;
            *(_BYTE *)(v4 + 1) = v37;
            *(_DWORD *)(v4 + 208) = 2000;
            *(_DWORD *)(v4 + 204) = 100;
            v39 = *(unsigned int *)(v38 + 16);
            if ( (unsigned int)v39 > 1 )
            {
              LOBYTE(v39) = v37 + v39 - 1;
              v40 = NvmeControllerGetPowerState(a1, v39);
              if ( v40 )
                *(_DWORD *)(v4 + 4) = (*(unsigned int *)(v40 + 8) + (unsigned __int64)*(unsigned int *)(v40 + 4) + 999)
                                    / 0x3E8;
            }
            v41 = *(_DWORD *)(a1[132] + 68);
            if ( v41 != -1 )
              *(_DWORD *)(v4 + 188) = v41;
            if ( v11 )
            {
              *(_QWORD *)(v38 + 120) = v18;
              v18 = 0;
              KeInitializeTimer(*(PKTIMER *)(*(_QWORD *)(v4 + 8) + 120LL));
              v42 = P;
              P = 0;
              *(_QWORD *)(*(_QWORD *)(v4 + 8) + 112LL) = v42;
              KeInitializeDpc(*(PRKDPC *)(*(_QWORD *)(v4 + 8) + 112LL), NvmeFStateTimerDpcRoutine, (PVOID)a1[16]);
              PoFxSetComponentLatency(**(_QWORD **)(v4 + 8), 0, 0);
              PoFxSetComponentResidency(**(_QWORD **)(v4 + 8), 0, 0);
            }
            v43 = RaidAllocatePool(64, 24 * v56 + 40, 1330667858, *(_QWORD *)(a1[16] + 8));
            v19 = (unsigned int *)v43;
            if ( v43 )
            {
              *(_DWORD *)v43 = 1;
              *(_DWORD *)(v43 + 4) = 40;
              v46 = 0;
              *(_DWORD *)(v43 + 28) = 40;
              *(_QWORD *)(v43 + 16) = 3;
              for ( *(_DWORD *)(v43 + 24) = v56; v46 < v56; *(_QWORD *)((char *)v19 + v49 + 8) = v44 )
              {
                LOBYTE(v44) = v46;
                v47 = v19[7] + 24LL * v46;
                *(unsigned int *)((char *)v19 + v47) = 1;
                *(unsigned int *)((char *)v19 + v47 + 4) = 24;
                v48 = NvmeControllerGetPowerState(a1, v44);
                v45 = NvmeControllerPowerStateGetMaxPower(v48);
                *(_QWORD *)((char *)v19 + v49 + 16) = v50;
                v46 = v51 + 1;
                v44 = v45 / 0x3E8;
              }
              v52 = *(__int64 **)(v4 + 8);
              v53 = a1[16];
              v58 = 1;
              v7 = NvmeRegisterPerfStates(*(_QWORD *)(v53 + 8), v44, v45, (unsigned int)&v58, (__int64)v19, v55, *v52);
              if ( v7 >= 0 )
              {
                if ( (unsigned __int8)NvmeAdapterCacheOperationalPowerRange(*(_QWORD *)(v4 + 8), v58, v19) )
                {
                  for ( i = 0; i != 3; ++i )
                    *(_QWORD *)(*(_QWORD *)(v4 + 8) + 8 * i + 40) = -1;
                }
                *(_DWORD *)(v4 + 176) |= 4u;
                *(_QWORD *)(v4 + 48) = v19;
                *(_WORD *)(v4 + 181) = (unsigned __int8)v56;
                NvmeControllerRegisterPowerSettingChangeNotification(a1);
              }
              goto LABEL_66;
            }
LABEL_23:
            v7 = -1073741670;
LABEL_66:
            ExFreePoolWithTag((PVOID)Pool, 0x4F506152u);
            if ( P )
              ExFreePoolWithTag(P, 0x4F506152u);
            if ( v18 )
              ExFreePoolWithTag(v18, 0x4F506152u);
            if ( v7 < 0 && v19 )
              ExFreePoolWithTag(v19, 0x4F506152u);
            return (unsigned int)v7;
          case 6:
            *(_DWORD *)(Pool + 12) = v22 | 4;
            *(_DWORD *)(v4 + 176) |= 2u;
            break;
          case 5:
            *(_DWORD *)(Pool + 12) = v22 | 4;
            break;
          default:
            goto LABEL_45;
        }
        *(_DWORD *)(Pool + 16) = *(_DWORD *)(a1[132] + 60);
        goto LABEL_45;
      }
    }
    else if ( !(unsigned __int8)StorIsSystemBatteryPresent() || *(_DWORD *)(Pool + 32) <= 1u )
    {
      goto LABEL_32;
    }
    *(_DWORD *)(Pool + 12) |= 0x100u;
    goto LABEL_36;
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x140113f70  mov     rax, rsp
0x140113f73  mov     [rax+8], rbx
0x140113f77  push    rbp
0x140113f78  push    rsi
0x140113f79  push    rdi
0x140113f7a  push    r12
0x140113f7c  push    r13
0x140113f7e  push    r14
0x140113f80  push    r15
0x140113f82  sub     rsp, 0B0h
0x140113f89  cmp     cs:RuntimePowerDisabled, 0
0x140113f90  mov     rdi, rcx
0x140113f93  mov     byte ptr [rax+18h], 0
0x140113f97  jnz     short loc_140113FFC
0x140113f99  mov     r14, [rcx+80h]
0x140113fa0  mov     rax, [r14+198h]
0x140113fa7  test    dword ptr [rax+0B8h], 40000000h
0x140113fb1  jz      loc_14011473B
0x140113fb7  mov     rax, [rcx+420h]
0x140113fbe  mov     ecx, [rax+30h]
0x140113fc1  cmp     ecx, 4
0x140113fc4  jz      short loc_140113FFC
0x140113fc6  mov     r14, [r14+0A8h]
0x140113fcd  cmp     ecx, 3
0x140113fd0  jnz     short loc_14011401A
0x140113fd2  mov     rcx, rdi
0x140113fd5  call    NvmeGetAutoPowerStateTransition
0x140113fda  test    dword ptr [r14+0B0h], 800h
0x140113fe5  jnz     short loc_140113FFC
0x140113fe7  mov     edx, 1
0x140113fec  mov     rcx, rdi
0x140113fef  call    NvmeSetAutoPowerStateTransition
0x140113ff4  mov     rcx, rdi
0x140113ff7  call    NvmeGetAutoPowerStateTransition
0x140113ffc  xor     eax, eax
0x140113ffe  mov     rbx, [rsp+0E8h+arg_0]
0x140114006  add     rsp, 0B0h
0x14011400d  pop     r15
0x14011400f  pop     r14
0x140114011  pop     r13
0x140114013  pop     r12
0x140114015  pop     rdi
0x140114016  pop     rsi
0x140114017  pop     rbp
0x140114018  retn
0x14011401a  mov     ebp, 1
0x14011401f  cmp     [r14], bpl
0x140114022  jz      short loc_140113FFC
0x140114024  mov     rcx, rdi
0x140114027  call    NvmeGetAutoPowerStateTransition
0x14011402c  test    dword ptr [r14+0B0h], 800h
0x140114037  jz      short loc_14011404B
0x140114039  xor     edx, edx
0x14011403b  mov     rcx, rdi
0x14011403e  call    NvmeSetAutoPowerStateTransition
0x140114043  mov     rcx, rdi
0x140114046  call    NvmeGetAutoPowerStateTransition
0x14011404b  mov     rcx, rdi
0x14011404e  call    NvmeControllerValidatePowerStates
0x140114053  test    al, al
0x140114055  jnz     short loc_140114061
0x140114057  mov     ebx, 0C0000184h
0x14011405c  jmp     loc_140114734
0x140114061  mov     rax, [rdi+250h]
0x140114068  xor     ebx, ebx
0x14011406a  xor     r12d, r12d
0x14011406d  mov     [rsp+0E8h+arg_18], ebx
0x140114074  xor     r13d, r13d
0x140114077  mov     [rsp+0E8h+var_48], r12d
0x14011407f  xor     esi, esi
0x140114081  movzx   ecx, byte ptr [rax+107h]
0x140114088  add     ecx, ebp
0x14011408a  jz      loc_1401141C9
0x140114090  mov     dl, sil
0x140114093  mov     rcx, rdi
0x140114096  call    NvmeControllerGetPowerState
0x14011409b  mov     rcx, rax
0x14011409e  mov     r10, rax
0x1401140a1  call    NvmeControllerPowerStateGetMaxPower
0x1401140a6  movzx   r11d, byte ptr [r10+3]
0x1401140ab  mov     r15d, eax
0x1401140ae  test    r11b, 2
0x1401140b2  jnz     short loc_1401140C0
0x1401140b4  add     r12d, ebp
0x1401140b7  mov     [rsp+0E8h+arg_18], esi
0x1401140be  jmp     short loc_1401140C3
0x1401140c0  add     r13d, ebp
0x1401140c3  movzx   eax, byte ptr [r10+0Fh]
0x1401140c8  mov     rbx, r11
0x1401140cb  movzx   ecx, byte ptr [r10+0Eh]
0x1401140d0  and     eax, 1Fh
0x1401140d3  movzx   edx, byte ptr [r10+0Dh]
0x1401140d8  and     ecx, 1Fh
0x1401140db  movzx   r8d, byte ptr [r10+0Ch]
0x1401140e0  and     edx, 1Fh
0x1401140e3  mov     r9d, [r10+8]
0x1401140e7  and     r8d, 1Fh
0x1401140eb  mov     r10d, [r10+4]
0x1401140ef  mov     [rsp+0E8h+var_50], rax
0x1401140f7  lea     rax, aRelativeWriteL; "Relative Write Latency"
0x1401140fe  mov     [rsp+0E8h+var_58], rax
0x140114106  lea     rax, aRelativeWriteT; "Relative Write Throughput"
0x14011410d  mov     [rsp+0E8h+var_60], rcx
0x140114115  mov     rcx, rdi
0x140114118  mov     [rsp+0E8h+var_68], rax
0x140114120  lea     rax, aRelativeReadLa; "Relative Read Latency"
0x140114127  mov     [rsp+0E8h+var_70], rdx
0x14011412c  mov     edx, ebp
0x14011412e  mov     [rsp+0E8h+var_78], rax
0x140114133  lea     rax, aRelativeReadTh; "Relative Read Throughput"
0x14011413a  mov     [rsp+0E8h+var_80], r8
0x14011413f  mov     r8d, 4
0x140114145  mov     [rsp+0E8h+var_88], rax
0x14011414a  lea     rax, aExitLatencyUs; "Exit Latency (us)"
0x140114151  mov     [rsp+0E8h+var_90], r9
0x140114156  lea     r9, aNvmePowerState; "NVMe Power State"
0x14011415d  mov     [rsp+0E8h+var_98], rax
0x140114162  lea     rax, aEntryLatencyUs; "Entry Latency (us)"
0x140114169  mov     [rsp+0E8h+var_A0], r10
0x14011416e  mov     [rsp+0E8h+var_A8], rax
0x140114173  lea     rax, aNonOperational; "Non-Operational"
0x14011417a  shr     rbx, 1
0x14011417d  and     rbx, rbp
0x140114180  mov     [rsp+0E8h+var_B0], rbx
0x140114185  mov     [rsp+0E8h+var_B8], rax
0x14011418a  lea     rax, aMaxPowerUw; "Max Power (uW)"
0x140114191  mov     [rsp+0E8h+var_C0], r15
0x140114196  mov     [rsp+0E8h+var_C8], rax
0x14011419b  call    StorEtwNvmeControllerEvent
0x1401141a0  mov     rax, [rdi+250h]
0x1401141a7  add     esi, ebp
0x1401141a9  movzx   ecx, byte ptr [rax+107h]
0x1401141b0  add     ecx, ebp
0x1401141b2  cmp     esi, ecx
0x1401141b4  jb      loc_140114090
0x1401141ba  mov     ebx, [rsp+0E8h+arg_18]
0x1401141c1  mov     [rsp+0E8h+var_48], r12d
0x1401141c9  mov     r9, [rdi+80h]
0x1401141d0  lea     edx, [r13+3]
0x1401141d4  shl     edx, 5
0x1401141d7  mov     ecx, 40h ; '@'
0x1401141dc  mov     r8d, 4F506152h
0x1401141e2  mov     r9, [r9+8]
0x1401141e6  call    RaidAllocatePool
0x1401141eb  mov     rsi, rax
0x1401141ee  test    rax, rax
0x1401141f1  jnz     short loc_1401141FD
0x1401141f3  mov     ebx, 0C000009Ah
0x1401141f8  jmp     loc_140114734
0x1401141fd  xor     r12d, r12d
0x140114200  xor     r15d, r15d
0x140114203  mov     [rsp+0E8h+P], r12
0x14011420b  test    r13d, r13d
0x14011420e  jz      short loc_14011426A
0x140114210  mov     r9, [rdi+80h]
0x140114217  lea     edx, [r15+40h]
0x14011421b  lea     ecx, [rdx+8]
0x14011421e  mov     r8d, 54496152h
0x140114224  mov     r9, [r9+8]
0x140114228  call    RaidAllocatePool
0x14011422d  mov     r12, rax
0x140114230  test    rax, rax
0x140114233  jnz     short loc_14011423F
0x140114235  mov     ebx, 0C000009Ah
0x14011423a  jmp     loc_1401146D0
0x14011423f  mov     r9, [rdi+80h]
0x140114246  mov     edx, 40h ; '@'
0x14011424b  mov     r8d, 54496152h
0x140114251  mov     r9, [r9+8]
0x140114255  lea     ecx, [rdx+8]
0x140114258  call    RaidAllocatePool
0x14011425d  mov     [rsp+0E8h+P], rax
0x140114265  test    rax, rax
0x140114268  jz      short loc_140114235
0x14011426a  or      dword ptr [rsi+0Ch], 40h
0x14011426e  mov     edx, ebp
0x140114270  mov     dword ptr [rsi], 3
0x140114276  mov     dword ptr [rsi+4], 18h
0x14011427d  mov     [rsi+8], ebp
0x140114280  mov     dword ptr [rsi+18h], 2
0x140114287  mov     dword ptr [rsi+1Ch], 28h ; '('
0x14011428e  movups  xmm0, cs:xmmword_140161450
0x140114295  mov     byte ptr [rsp+0E8h+arg_8], r15b
0x14011429d  movdqu  xmmword ptr [rsi+28h], xmm0
0x1401142a2  mov     rax, [rdi+420h]
0x1401142a9  cmp     dword ptr [rax+30h], 5
0x1401142ad  jz      short loc_1401142B3
0x1401142af  lea     edx, [r13+1]
0x1401142b3  mov     [rsi+20h], edx
0x1401142b6  mov     rax, [rdi+420h]
0x1401142bd  mov     cl, [rax+6Fh]
0x1401142c0  and     cl, 3
0x1401142c3  jnz     short loc_1401142D5
0x1401142c5  call    StorIsSystemBatteryPresent
0x1401142ca  test    al, al
0x1401142cc  jz      short loc_1401142DA
0x1401142ce  cmp     [rsi+20h], ebp
0x1401142d1  ja      short loc_1401142ED
0x1401142d3  jmp     short loc_1401142DA
0x1401142d5  cmp     cl, 2
0x1401142d8  jnz     short loc_1401142E4
0x1401142da  mov     byte ptr [rsp+0E8h+arg_8], bpl
0x1401142e2  jmp     short loc_1401142F2
0x1401142e4  cmp     cl, bpl
0x1401142e7  jnz     short loc_1401142F2
0x1401142e9  cmp     edx, ebp
0x1401142eb  jbe     short loc_1401142F2
0x1401142ed  bts     dword ptr [rsi+0Ch], 8
0x1401142f2  cmp     dword ptr [rsi+20h], 8
0x1401142f6  jbe     short loc_1401142FF
0x1401142f8  mov     dword ptr [rsi+20h], 8
0x1401142ff  or      dword ptr [rsi+0Ch], 10h
0x140114303  or      r11d, 0FFFFFFFFh
0x140114307  mov     ecx, [rsi+0Ch]
0x14011430a  mov     [rsi+10h], r11d
0x14011430e  mov     rax, [rdi+420h]
0x140114315  mov     edx, [rax+30h]
0x140114318  cmp     edx, 2
0x14011431b  jnz     short loc_14011432C
0x14011431d  or      ecx, 4
0x140114320  mov     [rsi+0Ch], ecx
0x140114323  or      [r14+0B0h], edx
0x14011432a  jmp     short loc_140114359
0x14011432c  cmp     edx, 6
0x14011432f  jnz     short loc_140114341
0x140114331  or      ecx, 4
0x140114334  mov     [rsi+0Ch], ecx
0x140114337  or      dword ptr [r14+0B0h], 2
0x14011433f  jmp     short loc_14011434C
0x140114341  cmp     edx, 5
0x140114344  jnz     short loc_140114359
0x140114346  or      ecx, 4
0x140114349  mov     [rsi+0Ch], ecx
0x14011434c  mov     rax, [rdi+420h]
0x140114353  mov     ecx, [rax+3Ch]
0x140114356  mov     [rsi+10h], ecx
0x140114359  mov     rax, [rdi+420h]
0x140114360  mov     eax, [rax+30h]
0x140114363  cmp     eax, ebp
0x140114365  jbe     short loc_14011436E
0x140114367  add     eax, 0FFFFFFFDh
0x14011436a  cmp     eax, ebp
0x14011436c  ja      short loc_140114372
0x14011436e  or      dword ptr [rsi+0Ch], 2
0x140114372  or      dword ptr [rsi+0Ch], 8
0x140114376  lea     r9d, [rbx+1]
0x14011437a  mov     ecx, [rsi+20h]
0x14011437d  mov     r10d, 20h ; ' '
0x140114383  mov     [rsi+40h], ebp
0x140114386  mov     r8d, ebp
0x140114389  mov     [rsi+44h], r10d
0x14011438d  mov     [rsi+48h], r15
0x140114391  mov     [rsi+50h], r15
0x140114395  lea     eax, [rcx-1]
0x140114398  mov     [rsi+3Ch], eax
0x14011439b  mov     [rsi+58h], r11d
0x14011439f  cmp     ecx, ebp
0x1401143a1  jbe     short loc_1401143F1
0x1401143a3  mov     dl, r9b
0x1401143a6  mov     rcx, rdi
0x1401143a9  call    NvmeControllerGetPowerState
0x1401143ae  mov     ecx, r8d
0x1401143b1  add     r9d, ebp
0x1401143b4  add     rcx, 2
0x1401143b8  mov     edx, r8d
0x1401143bb  shl     rcx, 5
0x1401143bf  add     r8d, ebp
0x1401143c2  shl     rdx, 5
0x1401143c6  mov     [rcx+rsi+18h], r11d
0x1401143cb  mov     [rdx+rsi+40h], ebp
0x1401143cf  mov     [rdx+rsi+44h], r10d
0x1401143d4  mov     ecx, [rax+8]
0x1401143d7  add     ecx, [rax+4]
0x1401143da  mov     [rdx+rsi+50h], r15
0x1401143df  lea     rcx, [rcx+rcx*4]
0x1401143e3  add     rcx, rcx
0x1401143e6  mov     [rdx+rsi+48h], rcx
0x1401143eb  cmp     r8d, [rsi+20h]
0x1401143ef  jb      short loc_1401143A3
0x1401143f1  mov     rcx, [rdi+80h]
0x1401143f8  lea     r8, [rsp+0E8h+arg_10]
0x140114400  mov     rdx, rsi
0x140114403  call    NvmeAdapterInitializePoFx
0x140114408  mov     ebx, eax
0x14011440a  test    eax, eax
0x14011440c  js      loc_1401146D0
0x140114412  mov     rax, [r14+8]
0x140114416  xor     ebx, ebx
0x140114418  movzx   ecx, [rsp+0E8h+arg_10]
0x140114420  shl     ecx, 3
0x140114423  mov     [rax+40h], bpl
0x140114427  mov     eax, [r14+0B0h]
0x14011442e  xor     ecx, eax
0x140114430  and     ecx, 8
0x140114433  xor     ecx, eax
0x140114435  mov     rax, [r14+8]
0x140114439  neg     byte ptr [rsp+0E8h+arg_8]
0x140114440  mov     [r14+0B0h], ecx
0x140114447  movzx   ecx, byte ptr [rsi+20h]
0x14011444b  mov     [rax+10h], ecx
  ... truncated ...
```
