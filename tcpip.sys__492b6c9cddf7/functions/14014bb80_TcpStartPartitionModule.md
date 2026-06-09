# TcpStartPartitionModule

- ea: `0x14014bb80`
- end: `0x14014bffe`
- name: `TcpStartPartitionModule`
- size: `1150`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140009470`
- `0x140053e98`
- `0x140104364`
- `0x14014bb80`
- `0x14014c820`
- `0x14014c878`
- `0x1401623b0`
- `0x140162574`
- `0x140169a74`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x14014bbe2`
- `ntoskrnl!KeInitializeSemaphore` at `0x14014bbe2`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bdd4`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bdfb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014be22`
- `ntoskrnl!RtlCreateHashTable` at `0x14014be4c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014be7c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014beb1`
- `ntoskrnl!RtlCreateHashTable` at `0x14014beda`
- `ntoskrnl!RtlCreateHashTable` at `0x14014beff`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bf24`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bdd4`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bdfb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014be22`
- `ntoskrnl!RtlCreateHashTable` at `0x14014be4c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014be7c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014beb1`
- `ntoskrnl!RtlCreateHashTable` at `0x14014beda`
- `ntoskrnl!RtlCreateHashTable` at `0x14014beff`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bf24`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bbb5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bd39`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bbb5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bd39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014bf63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014bf79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014bf63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014bf79`
- `ntoskrnl!ExAllocatePool2` at `0x14014bc16`
- `ntoskrnl!ExAllocatePool2` at `0x14014bcd5`
- `ntoskrnl!ExAllocatePool2` at `0x14014bd11`
- `ntoskrnl!ExAllocatePool2` at `0x14014bc16`
- `ntoskrnl!ExAllocatePool2` at `0x14014bcd5`
- `ntoskrnl!ExAllocatePool2` at `0x14014bd11`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14014bc3b`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14014bc3b`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bd6d`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bd93`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bdb9`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bd6d`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bd93`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bdb9`

## pseudocode

```c
__int64 TcpStartPartitionModule()
{
  unsigned int LockArray_high; // ebx
  __int64 v1; // r12
  __int64 v2; // r8
  unsigned __int64 LowestEfficiencyClassMask; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int64 v7; // r14
  __int64 i; // r15
  char *v9; // rax
  __int64 v10; // rdi
  __int64 Pool2; // rax
  __int64 v12; // rsi
  char *v13; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v14; // r13
  __int64 v15; // rax
  char *v16; // rbx
  __int64 v17; // rbx
  char *v18; // rax
  char *v19; // rbx
  void *v20; // rcx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+78h] [rbp+48h] BYREF

  HashTable = 0;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  KeInitializeSpinLock(&SynAttackLock);
  _InterlockedExchange(&SynAttackInProgress, 0);
  _InterlockedExchange(&SynDropRateNextExpirationTick, 0);
  KeInitializeSemaphore(&TcpRepartitionSemaphore, 1, 1);
  v1 = (unsigned __int16)TcpPartitionsToAllocate();
  PartitionCount = TcpCurrentPartitionCount();
  PartitionTable = (PVOID)ExAllocatePool2(64, 192 * v1, 1951425364);
  if ( PartitionTable )
  {
    if ( (unsigned int)Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline() )
    {
      if ( (unsigned __int8)NetioNcmFastCheckIsAoAcCapable() )
      {
        LowestEfficiencyClassMask = TcpGetLowestEfficiencyClassMask();
        if ( LowestEfficiencyClassMask )
        {
          if ( _BitScanReverse64((unsigned __int64 *)&v5, LowestEfficiencyClassMask) )
            PowerEfficientPartitionIndex = v5;
        }
      }
    }
    v7 = TcpQueryMicrosecondCount(LockArray_high, 0) / 0x3E8uLL;
    for ( i = 0; (unsigned int)i < (unsigned int)v1; i = (unsigned int)(i + 1) )
    {
      v9 = (char *)PartitionTable;
      v10 = 192 * i;
      *(_QWORD *)((char *)PartitionTable + v10 + 144) = 4096;
      *(_DWORD *)&v9[v10 + 152] = 0;
      *(_DWORD *)&v9[v10 + 160] = 0;
      Pool2 = ExAllocatePool2(64, 448, 1414030164);
      v12 = Pool2;
      if ( !Pool2 )
        goto LABEL_25;
      v13 = (char *)PartitionTable;
      v14 = (struct _RTL_DYNAMIC_HASH_TABLE *)(Pool2 + 64);
      *(_QWORD *)((char *)PartitionTable + v10) = Pool2;
      *(_QWORD *)&v13[v10 + 8] = Pool2 + 64;
      v15 = ExAllocatePool2(64, 6336, 1953522516);
      v16 = (char *)PartitionTable;
      *(_QWORD *)((char *)PartitionTable + v10 + 64) = v15;
      if ( !v15 )
      {
        v20 = (void *)v12;
        goto LABEL_24;
      }
      v17 = *(_QWORD *)&v16[v10];
      KeInitializeSpinLock((PKSPIN_LOCK)v17);
      v18 = (char *)PartitionTable;
      *(_DWORD *)(v17 + 8) = 0;
      v19 = *(char **)&v18[v10 + 64];
      RtlInitializeTimerWheel(v19, 64, 6, 1, v7);
      RtlInitializeTimerWheel(v19 + 1592, 128, 1, 1, v7);
      RtlInitializeTimerWheel(v19 + 4720, 64, 1, 1, v7);
      HashTable = v14;
      if ( !RtlCreateHashTable(&HashTable, 6u, 0) )
        goto LABEL_22;
      HashTable = v14 + 3;
      if ( !RtlCreateHashTable(&HashTable, 6u, 0) )
        goto LABEL_22;
      HashTable = v14 + 2;
      if ( RtlCreateHashTable(&HashTable, 6u, 0) )
      {
        HashTable = v14 + 1;
        if ( RtlCreateHashTable(&HashTable, 6u, 0) )
        {
          HashTable = (PRTL_DYNAMIC_HASH_TABLE)((char *)PartitionTable + v10 + 24);
          if ( RtlCreateHashTable(&HashTable, 6u, 0) )
          {
            *(_QWORD *)((char *)PartitionTable + v10 + 16) = v12 + 256;
            HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v12 + 256);
            if ( RtlCreateHashTable(&HashTable, 6u, 0) )
            {
              HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v12 + 376);
              if ( RtlCreateHashTable(&HashTable, 6u, 0) )
              {
                HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v12 + 336);
                if ( RtlCreateHashTable(&HashTable, 6u, 0) )
                {
                  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(v12 + 296);
                  if ( RtlCreateHashTable(&HashTable, 6u, 0) )
                  {
                    if ( (unsigned __int8)RngInitializeRngPool((char *)PartitionTable + v10 + 80, 4096, 1314022228) )
                      continue;
                  }
                }
              }
            }
          }
        }
      }
LABEL_22:
      ExFreePoolWithTag((PVOID)v12, 0);
      v20 = v19;
LABEL_24:
      ExFreePoolWithTag(v20, 0);
LABEL_25:
      TcpCleanupPartitionModule((unsigned int)i);
      goto LABEL_26;
    }
    TcpStartedModules |= 0x200000uLL;
    if ( (BYTE3(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MODULE_STARTED, v6, L"PartitionModule");
    return 0;
  }
  else
  {
LABEL_26:
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v2,
        L"connection partitions (TCP)");
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x14014bb80  mov     [rsp-38h+arg_10], rbx
0x14014bb85  push    rbp
0x14014bb86  push    rsi
0x14014bb87  push    rdi
0x14014bb88  push    r12
0x14014bb8a  push    r13
0x14014bb8c  push    r14
0x14014bb8e  push    r15
0x14014bb90  mov     rbp, rsp
0x14014bb93  sub     rsp, 30h
0x14014bb97  mov     [rbp+HashTable], 0
0x14014bb9f  lea     rcx, SynAttackLock; SpinLock
0x14014bba6  mov     ebx, gs:1A4h
0x14014bbae  mov     [rbp+arg_0], 0
0x14014bbb5  call    cs:__imp_KeInitializeSpinLock
0x14014bbbc  nop     dword ptr [rax+rax+00h]
0x14014bbc1  xor     eax, eax
0x14014bbc3  xor     ecx, ecx
0x14014bbc5  xchg    eax, cs:SynAttackInProgress
0x14014bbcb  xchg    ecx, cs:SynDropRateNextExpirationTick
0x14014bbd1  mov     eax, 1
0x14014bbd6  lea     rcx, TcpRepartitionSemaphore; Semaphore
0x14014bbdd  mov     r8d, eax; Limit
0x14014bbe0  mov     edx, eax; Count
0x14014bbe2  call    cs:__imp_KeInitializeSemaphore
0x14014bbe9  nop     dword ptr [rax+rax+00h]
0x14014bbee  call    TcpPartitionsToAllocate
0x14014bbf3  movzx   r12d, ax
0x14014bbf7  call    TcpCurrentPartitionCount
0x14014bbfc  lea     rdx, [r12+r12*2]
0x14014bc00  mov     cs:PartitionCount, ax
0x14014bc07  shl     rdx, 6
0x14014bc0b  mov     ecx, 40h ; '@'
0x14014bc10  mov     r8d, 74506354h
0x14014bc16  call    cs:__imp_ExAllocatePool2
0x14014bc1d  nop     dword ptr [rax+rax+00h]
0x14014bc22  mov     cs:PartitionTable, rax
0x14014bc29  test    rax, rax
0x14014bc2c  jz      loc_14014BF8D
0x14014bc32  call    Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline
0x14014bc37  test    eax, eax
0x14014bc39  jz      short loc_14014BC62
0x14014bc3b  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14014bc42  nop     dword ptr [rax+rax+00h]
0x14014bc47  test    al, al
0x14014bc49  jz      short loc_14014BC62
0x14014bc4b  call    TcpGetLowestEfficiencyClassMask
0x14014bc50  test    rax, rax
0x14014bc53  jz      short loc_14014BC62
0x14014bc55  bsr     rdx, rax
0x14014bc59  jz      short loc_14014BC62
0x14014bc5b  mov     cs:PowerEfficientPartitionIndex, dx
0x14014bc62  xor     edx, edx
0x14014bc64  mov     ecx, ebx
0x14014bc66  call    TcpQueryMicrosecondCount
0x14014bc6b  mov     r14, rax
0x14014bc6e  mov     rax, 624DD2F1A9FBE77h
0x14014bc78  mul     r14
0x14014bc7b  sub     r14, rdx
0x14014bc7e  shr     r14, 1
0x14014bc81  add     r14, rdx
0x14014bc84  shr     r14, 9
0x14014bc88  xor     r15d, r15d
0x14014bc8b  cmp     r15d, r12d
0x14014bc8e  jnb     loc_14014BFB7
0x14014bc94  mov     rax, cs:PartitionTable
0x14014bc9b  lea     rdi, [r15+r15*2]
0x14014bc9f  shl     rdi, 6
0x14014bca3  mov     edx, 1C0h
0x14014bca8  mov     ecx, 40h ; '@'
0x14014bcad  mov     r8d, 54486354h
0x14014bcb3  mov     qword ptr [rdi+rax+90h], 1000h
0x14014bcbf  mov     dword ptr [rdi+rax+98h], 0
0x14014bcca  mov     dword ptr [rdi+rax+0A0h], 0
0x14014bcd5  call    cs:__imp_ExAllocatePool2
0x14014bcdc  nop     dword ptr [rax+rax+00h]
0x14014bce1  mov     rsi, rax
0x14014bce4  test    rax, rax
0x14014bce7  jz      loc_14014BF85
0x14014bced  mov     rcx, cs:PartitionTable
0x14014bcf4  lea     r13, [rax+40h]
0x14014bcf8  mov     edx, 18C0h
0x14014bcfd  mov     r8d, 74706354h
0x14014bd03  mov     [rdi+rcx], rax
0x14014bd07  mov     [rdi+rcx+8], r13
0x14014bd0c  mov     ecx, 40h ; '@'
0x14014bd11  call    cs:__imp_ExAllocatePool2
0x14014bd18  nop     dword ptr [rax+rax+00h]
0x14014bd1d  mov     rbx, cs:PartitionTable
0x14014bd24  mov     [rdi+rbx+40h], rax
0x14014bd29  test    rax, rax
0x14014bd2c  jz      loc_14014BF74
0x14014bd32  mov     rbx, [rdi+rbx]
0x14014bd36  mov     rcx, rbx; SpinLock
0x14014bd39  call    cs:__imp_KeInitializeSpinLock
0x14014bd40  nop     dword ptr [rax+rax+00h]
0x14014bd45  mov     rax, cs:PartitionTable
0x14014bd4c  mov     edx, 40h ; '@'
0x14014bd51  mov     dword ptr [rbx+8], 0
0x14014bd58  mov     [rsp+30h+var_10], r14d
0x14014bd5d  mov     rbx, [rdi+rax+40h]
0x14014bd62  lea     r9d, [rdx-3Fh]
0x14014bd66  mov     rcx, rbx
0x14014bd69  lea     r8d, [rdx-3Ah]
0x14014bd6d  call    cs:__imp_RtlInitializeTimerWheel
0x14014bd74  nop     dword ptr [rax+rax+00h]
0x14014bd79  mov     eax, 1
0x14014bd7e  mov     [rsp+30h+var_10], r14d
0x14014bd83  mov     r9d, eax
0x14014bd86  lea     rcx, [rbx+638h]
0x14014bd8d  mov     r8d, eax
0x14014bd90  lea     edx, [rax+7Fh]
0x14014bd93  call    cs:__imp_RtlInitializeTimerWheel
0x14014bd9a  nop     dword ptr [rax+rax+00h]
0x14014bd9f  mov     eax, 1
0x14014bda4  mov     [rsp+30h+var_10], r14d
0x14014bda9  mov     r9d, eax
0x14014bdac  lea     rcx, [rbx+1270h]
0x14014bdb3  mov     r8d, eax
0x14014bdb6  lea     edx, [rax+3Fh]
0x14014bdb9  call    cs:__imp_RtlInitializeTimerWheel
0x14014bdc0  nop     dword ptr [rax+rax+00h]
0x14014bdc5  xor     r8d, r8d; Flags
0x14014bdc8  mov     [rbp+HashTable], r13
0x14014bdcc  lea     rcx, [rbp+HashTable]; HashTable
0x14014bdd0  lea     edx, [r8+6]; Shift
0x14014bdd4  call    cs:__imp_RtlCreateHashTable
0x14014bddb  nop     dword ptr [rax+rax+00h]
0x14014bde0  test    al, al
0x14014bde2  jz      loc_14014BF5E
0x14014bde8  xor     r8d, r8d; Flags
0x14014bdeb  lea     rax, [r13+78h]
0x14014bdef  lea     rcx, [rbp+HashTable]; HashTable
0x14014bdf3  mov     [rbp+HashTable], rax
0x14014bdf7  lea     edx, [r8+6]; Shift
0x14014bdfb  call    cs:__imp_RtlCreateHashTable
0x14014be02  nop     dword ptr [rax+rax+00h]
0x14014be07  test    al, al
0x14014be09  jz      loc_14014BF5E
0x14014be0f  xor     r8d, r8d; Flags
0x14014be12  lea     rax, [r13+50h]
0x14014be16  lea     rcx, [rbp+HashTable]; HashTable
0x14014be1a  mov     [rbp+HashTable], rax
0x14014be1e  lea     edx, [r8+6]; Shift
0x14014be22  call    cs:__imp_RtlCreateHashTable
0x14014be29  nop     dword ptr [rax+rax+00h]
0x14014be2e  test    al, al
0x14014be30  jz      loc_14014BF5E
0x14014be36  lea     rax, [r13+28h]
0x14014be3a  xor     r8d, r8d; Flags
0x14014be3d  lea     rcx, [rbp+HashTable]; HashTable
0x14014be41  mov     [rbp+HashTable], rax
0x14014be45  lea     r13d, [r8+6]
0x14014be49  mov     edx, r13d; Shift
0x14014be4c  call    cs:__imp_RtlCreateHashTable
0x14014be53  nop     dword ptr [rax+rax+00h]
0x14014be58  test    al, al
0x14014be5a  jz      loc_14014BF5E
0x14014be60  mov     rcx, cs:PartitionTable
0x14014be67  xor     r8d, r8d; Flags
0x14014be6a  add     rcx, 18h
0x14014be6e  mov     edx, r13d; Shift
0x14014be71  add     rcx, rdi
0x14014be74  mov     [rbp+HashTable], rcx
0x14014be78  lea     rcx, [rbp+HashTable]; HashTable
0x14014be7c  call    cs:__imp_RtlCreateHashTable
0x14014be83  nop     dword ptr [rax+rax+00h]
0x14014be88  test    al, al
0x14014be8a  jz      loc_14014BF5E
0x14014be90  mov     rax, cs:PartitionTable
0x14014be97  lea     rcx, [rsi+100h]
0x14014be9e  xor     r8d, r8d; Flags
0x14014bea1  mov     edx, r13d; Shift
0x14014bea4  mov     [rdi+rax+10h], rcx
0x14014bea9  mov     [rbp+HashTable], rcx
0x14014bead  lea     rcx, [rbp+HashTable]; HashTable
0x14014beb1  call    cs:__imp_RtlCreateHashTable
0x14014beb8  nop     dword ptr [rax+rax+00h]
0x14014bebd  test    al, al
0x14014bebf  jz      loc_14014BF5E
0x14014bec5  lea     rax, [rsi+178h]
0x14014becc  xor     r8d, r8d; Flags
0x14014becf  mov     edx, r13d; Shift
0x14014bed2  mov     [rbp+HashTable], rax
0x14014bed6  lea     rcx, [rbp+HashTable]; HashTable
0x14014beda  call    cs:__imp_RtlCreateHashTable
0x14014bee1  nop     dword ptr [rax+rax+00h]
0x14014bee6  test    al, al
0x14014bee8  jz      short loc_14014BF5E
0x14014beea  lea     rax, [rsi+150h]
0x14014bef1  xor     r8d, r8d; Flags
0x14014bef4  mov     edx, r13d; Shift
0x14014bef7  mov     [rbp+HashTable], rax
0x14014befb  lea     rcx, [rbp+HashTable]; HashTable
0x14014beff  call    cs:__imp_RtlCreateHashTable
0x14014bf06  nop     dword ptr [rax+rax+00h]
0x14014bf0b  test    al, al
0x14014bf0d  jz      short loc_14014BF5E
0x14014bf0f  lea     rax, [rsi+128h]
0x14014bf16  xor     r8d, r8d; Flags
0x14014bf19  mov     edx, r13d; Shift
0x14014bf1c  mov     [rbp+HashTable], rax
0x14014bf20  lea     rcx, [rbp+HashTable]; HashTable
0x14014bf24  call    cs:__imp_RtlCreateHashTable
0x14014bf2b  nop     dword ptr [rax+rax+00h]
0x14014bf30  test    al, al
0x14014bf32  jz      short loc_14014BF5E
0x14014bf34  mov     rcx, cs:PartitionTable
0x14014bf3b  mov     edx, 1000h
0x14014bf40  add     rcx, 50h ; 'P'
0x14014bf44  mov     r8d, 4E526354h
0x14014bf4a  add     rcx, rdi
0x14014bf4d  call    RngInitializeRngPool
0x14014bf52  test    al, al
0x14014bf54  jz      short loc_14014BF5E
0x14014bf56  inc     r15d
0x14014bf59  jmp     loc_14014BC8B
0x14014bf5e  xor     edx, edx; Tag
0x14014bf60  mov     rcx, rsi; P
0x14014bf63  call    cs:__imp_ExFreePoolWithTag
0x14014bf6a  nop     dword ptr [rax+rax+00h]
0x14014bf6f  mov     rcx, rbx
0x14014bf72  jmp     short loc_14014BF77
0x14014bf74  mov     rcx, rsi; P
0x14014bf77  xor     edx, edx; Tag
0x14014bf79  call    cs:__imp_ExFreePoolWithTag
0x14014bf80  nop     dword ptr [rax+rax+00h]
0x14014bf85  mov     ecx, r15d
0x14014bf88  call    TcpCleanupPartitionModule
0x14014bf8d  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x14014bf94  jge     short loc_14014BFB0
0x14014bf96  lea     r9, aConnectionPart; "connection partitions (TCP)"
0x14014bf9d  lea     rdx, TCPIP_MEMORY_FAILURES
0x14014bfa4  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014bfab  call    McTemplateK0z_EtwWriteTransfer
0x14014bfb0  mov     eax, 0C0000017h
0x14014bfb5  jmp     short loc_14014BFE5
0x14014bfb7  bts     cs:TcpStartedModules, 15h
0x14014bfc0  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 10h
0x14014bfc7  jz      short loc_14014BFE3
0x14014bfc9  lea     r9, aPartitionmodul; "PartitionModule"
0x14014bfd0  lea     rdx, TCPIP_MODULE_STARTED
0x14014bfd7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014bfde  call    McTemplateK0z_EtwWriteTransfer
0x14014bfe3  xor     eax, eax
0x14014bfe5  mov     rbx, [rsp+30h+arg_10]
0x14014bfed  add     rsp, 30h
0x14014bff1  pop     r15
0x14014bff3  pop     r14
0x14014bff5  pop     r13
0x14014bff7  pop     r12
0x14014bff9  pop     rdi
0x14014bffa  pop     rsi
0x14014bffb  pop     rbp
0x14014bffc  retn
```
