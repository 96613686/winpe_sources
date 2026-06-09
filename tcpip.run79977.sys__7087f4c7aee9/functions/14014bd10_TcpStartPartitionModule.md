# TcpStartPartitionModule

- ea: `0x14014bd10`
- end: `0x14014c18e`
- name: `TcpStartPartitionModule`
- size: `1150`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140009470`
- `0x140054138`
- `0x140104384`
- `0x14014bd10`
- `0x14014c9b0`
- `0x14014ca08`
- `0x1401624f0`
- `0x1401626b4`
- `0x140169bb4`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x14014bd72`
- `ntoskrnl!KeInitializeSemaphore` at `0x14014bd72`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bf64`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bf8b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bfb2`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bfdc`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c00c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c041`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c06a`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c08f`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c0b4`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bf64`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bf8b`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bfb2`
- `ntoskrnl!RtlCreateHashTable` at `0x14014bfdc`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c00c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c041`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c06a`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c08f`
- `ntoskrnl!RtlCreateHashTable` at `0x14014c0b4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bd45`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bec9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bd45`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014bec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014c0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014c109`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014c0f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014c109`
- `ntoskrnl!ExAllocatePool2` at `0x14014bda6`
- `ntoskrnl!ExAllocatePool2` at `0x14014be65`
- `ntoskrnl!ExAllocatePool2` at `0x14014bea1`
- `ntoskrnl!ExAllocatePool2` at `0x14014bda6`
- `ntoskrnl!ExAllocatePool2` at `0x14014be65`
- `ntoskrnl!ExAllocatePool2` at `0x14014bea1`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14014bdcb`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14014bdcb`
- `NETIO!RtlInitializeTimerWheel` at `0x14014befd`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bf23`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bf49`
- `NETIO!RtlInitializeTimerWheel` at `0x14014befd`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bf23`
- `NETIO!RtlInitializeTimerWheel` at `0x14014bf49`

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
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, &TCPIP_MODULE_STARTED, v6, L"PartitionModule");
    return 0;
  }
  else
  {
LABEL_26:
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        &TCPIP_MEMORY_FAILURES,
        v2,
        L"connection partitions (TCP)");
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x14014bd10  mov     [rsp-38h+arg_10], rbx
0x14014bd15  push    rbp
0x14014bd16  push    rsi
0x14014bd17  push    rdi
0x14014bd18  push    r12
0x14014bd1a  push    r13
0x14014bd1c  push    r14
0x14014bd1e  push    r15
0x14014bd20  mov     rbp, rsp
0x14014bd23  sub     rsp, 30h
0x14014bd27  mov     [rbp+HashTable], 0
0x14014bd2f  lea     rcx, SynAttackLock; SpinLock
0x14014bd36  mov     ebx, gs:1A4h
0x14014bd3e  mov     [rbp+arg_0], 0
0x14014bd45  call    cs:__imp_KeInitializeSpinLock
0x14014bd4c  nop     dword ptr [rax+rax+00h]
0x14014bd51  xor     eax, eax
0x14014bd53  xor     ecx, ecx
0x14014bd55  xchg    eax, cs:SynAttackInProgress
0x14014bd5b  xchg    ecx, cs:SynDropRateNextExpirationTick
0x14014bd61  mov     eax, 1
0x14014bd66  lea     rcx, TcpRepartitionSemaphore; Semaphore
0x14014bd6d  mov     r8d, eax; Limit
0x14014bd70  mov     edx, eax; Count
0x14014bd72  call    cs:__imp_KeInitializeSemaphore
0x14014bd79  nop     dword ptr [rax+rax+00h]
0x14014bd7e  call    TcpPartitionsToAllocate
0x14014bd83  movzx   r12d, ax
0x14014bd87  call    TcpCurrentPartitionCount
0x14014bd8c  lea     rdx, [r12+r12*2]
0x14014bd90  mov     cs:PartitionCount, ax
0x14014bd97  shl     rdx, 6
0x14014bd9b  mov     ecx, 40h ; '@'
0x14014bda0  mov     r8d, 74506354h
0x14014bda6  call    cs:__imp_ExAllocatePool2
0x14014bdad  nop     dword ptr [rax+rax+00h]
0x14014bdb2  mov     cs:PartitionTable, rax
0x14014bdb9  test    rax, rax
0x14014bdbc  jz      loc_14014C11D
0x14014bdc2  call    Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline
0x14014bdc7  test    eax, eax
0x14014bdc9  jz      short loc_14014BDF2
0x14014bdcb  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14014bdd2  nop     dword ptr [rax+rax+00h]
0x14014bdd7  test    al, al
0x14014bdd9  jz      short loc_14014BDF2
0x14014bddb  call    TcpGetLowestEfficiencyClassMask
0x14014bde0  test    rax, rax
0x14014bde3  jz      short loc_14014BDF2
0x14014bde5  bsr     rdx, rax
0x14014bde9  jz      short loc_14014BDF2
0x14014bdeb  mov     cs:PowerEfficientPartitionIndex, dx
0x14014bdf2  xor     edx, edx
0x14014bdf4  mov     ecx, ebx
0x14014bdf6  call    TcpQueryMicrosecondCount
0x14014bdfb  mov     r14, rax
0x14014bdfe  mov     rax, 624DD2F1A9FBE77h
0x14014be08  mul     r14
0x14014be0b  sub     r14, rdx
0x14014be0e  shr     r14, 1
0x14014be11  add     r14, rdx
0x14014be14  shr     r14, 9
0x14014be18  xor     r15d, r15d
0x14014be1b  cmp     r15d, r12d
0x14014be1e  jnb     loc_14014C147
0x14014be24  mov     rax, cs:PartitionTable
0x14014be2b  lea     rdi, [r15+r15*2]
0x14014be2f  shl     rdi, 6
0x14014be33  mov     edx, 1C0h
0x14014be38  mov     ecx, 40h ; '@'
0x14014be3d  mov     r8d, 54486354h
0x14014be43  mov     qword ptr [rdi+rax+90h], 1000h
0x14014be4f  mov     dword ptr [rdi+rax+98h], 0
0x14014be5a  mov     dword ptr [rdi+rax+0A0h], 0
0x14014be65  call    cs:__imp_ExAllocatePool2
0x14014be6c  nop     dword ptr [rax+rax+00h]
0x14014be71  mov     rsi, rax
0x14014be74  test    rax, rax
0x14014be77  jz      loc_14014C115
0x14014be7d  mov     rcx, cs:PartitionTable
0x14014be84  lea     r13, [rax+40h]
0x14014be88  mov     edx, 18C0h
0x14014be8d  mov     r8d, 74706354h
0x14014be93  mov     [rdi+rcx], rax
0x14014be97  mov     [rdi+rcx+8], r13
0x14014be9c  mov     ecx, 40h ; '@'
0x14014bea1  call    cs:__imp_ExAllocatePool2
0x14014bea8  nop     dword ptr [rax+rax+00h]
0x14014bead  mov     rbx, cs:PartitionTable
0x14014beb4  mov     [rdi+rbx+40h], rax
0x14014beb9  test    rax, rax
0x14014bebc  jz      loc_14014C104
0x14014bec2  mov     rbx, [rdi+rbx]
0x14014bec6  mov     rcx, rbx; SpinLock
0x14014bec9  call    cs:__imp_KeInitializeSpinLock
0x14014bed0  nop     dword ptr [rax+rax+00h]
0x14014bed5  mov     rax, cs:PartitionTable
0x14014bedc  mov     edx, 40h ; '@'
0x14014bee1  mov     dword ptr [rbx+8], 0
0x14014bee8  mov     [rsp+30h+var_10], r14d
0x14014beed  mov     rbx, [rdi+rax+40h]
0x14014bef2  lea     r9d, [rdx-3Fh]
0x14014bef6  mov     rcx, rbx
0x14014bef9  lea     r8d, [rdx-3Ah]
0x14014befd  call    cs:__imp_RtlInitializeTimerWheel
0x14014bf04  nop     dword ptr [rax+rax+00h]
0x14014bf09  mov     eax, 1
0x14014bf0e  mov     [rsp+30h+var_10], r14d
0x14014bf13  mov     r9d, eax
0x14014bf16  lea     rcx, [rbx+638h]
0x14014bf1d  mov     r8d, eax
0x14014bf20  lea     edx, [rax+7Fh]
0x14014bf23  call    cs:__imp_RtlInitializeTimerWheel
0x14014bf2a  nop     dword ptr [rax+rax+00h]
0x14014bf2f  mov     eax, 1
0x14014bf34  mov     [rsp+30h+var_10], r14d
0x14014bf39  mov     r9d, eax
0x14014bf3c  lea     rcx, [rbx+1270h]
0x14014bf43  mov     r8d, eax
0x14014bf46  lea     edx, [rax+3Fh]
0x14014bf49  call    cs:__imp_RtlInitializeTimerWheel
0x14014bf50  nop     dword ptr [rax+rax+00h]
0x14014bf55  xor     r8d, r8d; Flags
0x14014bf58  mov     [rbp+HashTable], r13
0x14014bf5c  lea     rcx, [rbp+HashTable]; HashTable
0x14014bf60  lea     edx, [r8+6]; Shift
0x14014bf64  call    cs:__imp_RtlCreateHashTable
0x14014bf6b  nop     dword ptr [rax+rax+00h]
0x14014bf70  test    al, al
0x14014bf72  jz      loc_14014C0EE
0x14014bf78  xor     r8d, r8d; Flags
0x14014bf7b  lea     rax, [r13+78h]
0x14014bf7f  lea     rcx, [rbp+HashTable]; HashTable
0x14014bf83  mov     [rbp+HashTable], rax
0x14014bf87  lea     edx, [r8+6]; Shift
0x14014bf8b  call    cs:__imp_RtlCreateHashTable
0x14014bf92  nop     dword ptr [rax+rax+00h]
0x14014bf97  test    al, al
0x14014bf99  jz      loc_14014C0EE
0x14014bf9f  xor     r8d, r8d; Flags
0x14014bfa2  lea     rax, [r13+50h]
0x14014bfa6  lea     rcx, [rbp+HashTable]; HashTable
0x14014bfaa  mov     [rbp+HashTable], rax
0x14014bfae  lea     edx, [r8+6]; Shift
0x14014bfb2  call    cs:__imp_RtlCreateHashTable
0x14014bfb9  nop     dword ptr [rax+rax+00h]
0x14014bfbe  test    al, al
0x14014bfc0  jz      loc_14014C0EE
0x14014bfc6  lea     rax, [r13+28h]
0x14014bfca  xor     r8d, r8d; Flags
0x14014bfcd  lea     rcx, [rbp+HashTable]; HashTable
0x14014bfd1  mov     [rbp+HashTable], rax
0x14014bfd5  lea     r13d, [r8+6]
0x14014bfd9  mov     edx, r13d; Shift
0x14014bfdc  call    cs:__imp_RtlCreateHashTable
0x14014bfe3  nop     dword ptr [rax+rax+00h]
0x14014bfe8  test    al, al
0x14014bfea  jz      loc_14014C0EE
0x14014bff0  mov     rcx, cs:PartitionTable
0x14014bff7  xor     r8d, r8d; Flags
0x14014bffa  add     rcx, 18h
0x14014bffe  mov     edx, r13d; Shift
0x14014c001  add     rcx, rdi
0x14014c004  mov     [rbp+HashTable], rcx
0x14014c008  lea     rcx, [rbp+HashTable]; HashTable
0x14014c00c  call    cs:__imp_RtlCreateHashTable
0x14014c013  nop     dword ptr [rax+rax+00h]
0x14014c018  test    al, al
0x14014c01a  jz      loc_14014C0EE
0x14014c020  mov     rax, cs:PartitionTable
0x14014c027  lea     rcx, [rsi+100h]
0x14014c02e  xor     r8d, r8d; Flags
0x14014c031  mov     edx, r13d; Shift
0x14014c034  mov     [rdi+rax+10h], rcx
0x14014c039  mov     [rbp+HashTable], rcx
0x14014c03d  lea     rcx, [rbp+HashTable]; HashTable
0x14014c041  call    cs:__imp_RtlCreateHashTable
0x14014c048  nop     dword ptr [rax+rax+00h]
0x14014c04d  test    al, al
0x14014c04f  jz      loc_14014C0EE
0x14014c055  lea     rax, [rsi+178h]
0x14014c05c  xor     r8d, r8d; Flags
0x14014c05f  mov     edx, r13d; Shift
0x14014c062  mov     [rbp+HashTable], rax
0x14014c066  lea     rcx, [rbp+HashTable]; HashTable
0x14014c06a  call    cs:__imp_RtlCreateHashTable
0x14014c071  nop     dword ptr [rax+rax+00h]
0x14014c076  test    al, al
0x14014c078  jz      short loc_14014C0EE
0x14014c07a  lea     rax, [rsi+150h]
0x14014c081  xor     r8d, r8d; Flags
0x14014c084  mov     edx, r13d; Shift
0x14014c087  mov     [rbp+HashTable], rax
0x14014c08b  lea     rcx, [rbp+HashTable]; HashTable
0x14014c08f  call    cs:__imp_RtlCreateHashTable
0x14014c096  nop     dword ptr [rax+rax+00h]
0x14014c09b  test    al, al
0x14014c09d  jz      short loc_14014C0EE
0x14014c09f  lea     rax, [rsi+128h]
0x14014c0a6  xor     r8d, r8d; Flags
0x14014c0a9  mov     edx, r13d; Shift
0x14014c0ac  mov     [rbp+HashTable], rax
0x14014c0b0  lea     rcx, [rbp+HashTable]; HashTable
0x14014c0b4  call    cs:__imp_RtlCreateHashTable
0x14014c0bb  nop     dword ptr [rax+rax+00h]
0x14014c0c0  test    al, al
0x14014c0c2  jz      short loc_14014C0EE
0x14014c0c4  mov     rcx, cs:PartitionTable
0x14014c0cb  mov     edx, 1000h
0x14014c0d0  add     rcx, 50h ; 'P'
0x14014c0d4  mov     r8d, 4E526354h
0x14014c0da  add     rcx, rdi
0x14014c0dd  call    RngInitializeRngPool
0x14014c0e2  test    al, al
0x14014c0e4  jz      short loc_14014C0EE
0x14014c0e6  inc     r15d
0x14014c0e9  jmp     loc_14014BE1B
0x14014c0ee  xor     edx, edx; Tag
0x14014c0f0  mov     rcx, rsi; P
0x14014c0f3  call    cs:__imp_ExFreePoolWithTag
0x14014c0fa  nop     dword ptr [rax+rax+00h]
0x14014c0ff  mov     rcx, rbx
0x14014c102  jmp     short loc_14014C107
0x14014c104  mov     rcx, rsi; P
0x14014c107  xor     edx, edx; Tag
0x14014c109  call    cs:__imp_ExFreePoolWithTag
0x14014c110  nop     dword ptr [rax+rax+00h]
0x14014c115  mov     ecx, r15d
0x14014c118  call    TcpCleanupPartitionModule
0x14014c11d  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, 0
0x14014c124  jge     short loc_14014C140
0x14014c126  lea     r9, aConnectionPart; "connection partitions (TCP)"
0x14014c12d  lea     rdx, TCPIP_MEMORY_FAILURES
0x14014c134  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014c13b  call    McTemplateK0z_EtwWriteTransfer
0x14014c140  mov     eax, 0C0000017h
0x14014c145  jmp     short loc_14014C175
0x14014c147  bts     cs:TcpStartedModules, 15h
0x14014c150  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 10h
0x14014c157  jz      short loc_14014C173
0x14014c159  lea     r9, aPartitionmodul; "PartitionModule"
0x14014c160  lea     rdx, TCPIP_MODULE_STARTED
0x14014c167  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014c16e  call    McTemplateK0z_EtwWriteTransfer
0x14014c173  xor     eax, eax
0x14014c175  mov     rbx, [rsp+30h+arg_10]
0x14014c17d  add     rsp, 30h
0x14014c181  pop     r15
0x14014c183  pop     r14
0x14014c185  pop     r13
0x14014c187  pop     r12
0x14014c189  pop     rdi
0x14014c18a  pop     rsi
0x14014c18b  pop     rbp
0x14014c18c  retn
```
