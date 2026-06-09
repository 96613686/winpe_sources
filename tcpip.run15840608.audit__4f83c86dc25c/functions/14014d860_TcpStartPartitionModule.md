# TcpStartPartitionModule

- ea: `0x14014d860`
- end: `0x14014dcde`
- name: `TcpStartPartitionModule`
- size: `1150`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140014a08`
- `0x140044880`
- `0x1400ef0b8`
- `0x14014d860`
- `0x14014e500`
- `0x14014e558`
- `0x140164170`
- `0x140164334`
- `0x14016b6b4`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x14014d8c2`
- `ntoskrnl!KeInitializeSemaphore` at `0x14014d8c2`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dab4`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dadb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db02`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db2c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db5c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db91`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dbba`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dbdf`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dc04`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dab4`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dadb`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db02`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db2c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db5c`
- `ntoskrnl!RtlCreateHashTable` at `0x14014db91`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dbba`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dbdf`
- `ntoskrnl!RtlCreateHashTable` at `0x14014dc04`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014d895`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014da19`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014d895`
- `ntoskrnl!KeInitializeSpinLock` at `0x14014da19`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014dc43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014dc59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014dc43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014dc59`
- `ntoskrnl!ExAllocatePool2` at `0x14014d8f6`
- `ntoskrnl!ExAllocatePool2` at `0x14014d9b5`
- `ntoskrnl!ExAllocatePool2` at `0x14014d9f1`
- `ntoskrnl!ExAllocatePool2` at `0x14014d8f6`
- `ntoskrnl!ExAllocatePool2` at `0x14014d9b5`
- `ntoskrnl!ExAllocatePool2` at `0x14014d9f1`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14014d91b`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14014d91b`
- `NETIO!RtlInitializeTimerWheel` at `0x14014da4d`
- `NETIO!RtlInitializeTimerWheel` at `0x14014da73`
- `NETIO!RtlInitializeTimerWheel` at `0x14014da99`
- `NETIO!RtlInitializeTimerWheel` at `0x14014da4d`
- `NETIO!RtlInitializeTimerWheel` at `0x14014da73`
- `NETIO!RtlInitializeTimerWheel` at `0x14014da99`

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
    if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MODULE_STARTED, v6, L"PartitionModule");
    return 0;
  }
  else
  {
LABEL_26:
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
0x14014d860  mov     [rsp-38h+arg_10], rbx
0x14014d865  push    rbp
0x14014d866  push    rsi
0x14014d867  push    rdi
0x14014d868  push    r12
0x14014d86a  push    r13
0x14014d86c  push    r14
0x14014d86e  push    r15
0x14014d870  mov     rbp, rsp
0x14014d873  sub     rsp, 30h
0x14014d877  mov     [rbp+HashTable], 0
0x14014d87f  lea     rcx, SynAttackLock; SpinLock
0x14014d886  mov     ebx, gs:1A4h
0x14014d88e  mov     [rbp+arg_0], 0
0x14014d895  call    cs:__imp_KeInitializeSpinLock
0x14014d89c  nop     dword ptr [rax+rax+00h]
0x14014d8a1  xor     eax, eax
0x14014d8a3  xor     ecx, ecx
0x14014d8a5  xchg    eax, cs:SynAttackInProgress
0x14014d8ab  xchg    ecx, cs:SynDropRateNextExpirationTick
0x14014d8b1  mov     eax, 1
0x14014d8b6  lea     rcx, TcpRepartitionSemaphore; Semaphore
0x14014d8bd  mov     r8d, eax; Limit
0x14014d8c0  mov     edx, eax; Count
0x14014d8c2  call    cs:__imp_KeInitializeSemaphore
0x14014d8c9  nop     dword ptr [rax+rax+00h]
0x14014d8ce  call    TcpPartitionsToAllocate
0x14014d8d3  movzx   r12d, ax
0x14014d8d7  call    TcpCurrentPartitionCount
0x14014d8dc  lea     rdx, [r12+r12*2]
0x14014d8e0  mov     cs:PartitionCount, ax
0x14014d8e7  shl     rdx, 6
0x14014d8eb  mov     ecx, 40h ; '@'
0x14014d8f0  mov     r8d, 74506354h
0x14014d8f6  call    cs:__imp_ExAllocatePool2
0x14014d8fd  nop     dword ptr [rax+rax+00h]
0x14014d902  mov     cs:PartitionTable, rax
0x14014d909  test    rax, rax
0x14014d90c  jz      loc_14014DC6D
0x14014d912  call    Feature_TCPIP_DPC_EfficientCore__private_IsEnabledDeviceUsageInline
0x14014d917  test    eax, eax
0x14014d919  jz      short loc_14014D942
0x14014d91b  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14014d922  nop     dword ptr [rax+rax+00h]
0x14014d927  test    al, al
0x14014d929  jz      short loc_14014D942
0x14014d92b  call    TcpGetLowestEfficiencyClassMask
0x14014d930  test    rax, rax
0x14014d933  jz      short loc_14014D942
0x14014d935  bsr     rdx, rax
0x14014d939  jz      short loc_14014D942
0x14014d93b  mov     cs:PowerEfficientPartitionIndex, dx
0x14014d942  xor     edx, edx
0x14014d944  mov     ecx, ebx
0x14014d946  call    TcpQueryMicrosecondCount
0x14014d94b  mov     r14, rax
0x14014d94e  mov     rax, 624DD2F1A9FBE77h
0x14014d958  mul     r14
0x14014d95b  sub     r14, rdx
0x14014d95e  shr     r14, 1
0x14014d961  add     r14, rdx
0x14014d964  shr     r14, 9
0x14014d968  xor     r15d, r15d
0x14014d96b  cmp     r15d, r12d
0x14014d96e  jnb     loc_14014DC97
0x14014d974  mov     rax, cs:PartitionTable
0x14014d97b  lea     rdi, [r15+r15*2]
0x14014d97f  shl     rdi, 6
0x14014d983  mov     edx, 1C0h
0x14014d988  mov     ecx, 40h ; '@'
0x14014d98d  mov     r8d, 54486354h
0x14014d993  mov     qword ptr [rdi+rax+90h], 1000h
0x14014d99f  mov     dword ptr [rdi+rax+98h], 0
0x14014d9aa  mov     dword ptr [rdi+rax+0A0h], 0
0x14014d9b5  call    cs:__imp_ExAllocatePool2
0x14014d9bc  nop     dword ptr [rax+rax+00h]
0x14014d9c1  mov     rsi, rax
0x14014d9c4  test    rax, rax
0x14014d9c7  jz      loc_14014DC65
0x14014d9cd  mov     rcx, cs:PartitionTable
0x14014d9d4  lea     r13, [rax+40h]
0x14014d9d8  mov     edx, 18C0h
0x14014d9dd  mov     r8d, 74706354h
0x14014d9e3  mov     [rdi+rcx], rax
0x14014d9e7  mov     [rdi+rcx+8], r13
0x14014d9ec  mov     ecx, 40h ; '@'
0x14014d9f1  call    cs:__imp_ExAllocatePool2
0x14014d9f8  nop     dword ptr [rax+rax+00h]
0x14014d9fd  mov     rbx, cs:PartitionTable
0x14014da04  mov     [rdi+rbx+40h], rax
0x14014da09  test    rax, rax
0x14014da0c  jz      loc_14014DC54
0x14014da12  mov     rbx, [rdi+rbx]
0x14014da16  mov     rcx, rbx; SpinLock
0x14014da19  call    cs:__imp_KeInitializeSpinLock
0x14014da20  nop     dword ptr [rax+rax+00h]
0x14014da25  mov     rax, cs:PartitionTable
0x14014da2c  mov     edx, 40h ; '@'
0x14014da31  mov     dword ptr [rbx+8], 0
0x14014da38  mov     [rsp+30h+var_10], r14d
0x14014da3d  mov     rbx, [rdi+rax+40h]
0x14014da42  lea     r9d, [rdx-3Fh]
0x14014da46  mov     rcx, rbx
0x14014da49  lea     r8d, [rdx-3Ah]
0x14014da4d  call    cs:__imp_RtlInitializeTimerWheel
0x14014da54  nop     dword ptr [rax+rax+00h]
0x14014da59  mov     eax, 1
0x14014da5e  mov     [rsp+30h+var_10], r14d
0x14014da63  mov     r9d, eax
0x14014da66  lea     rcx, [rbx+638h]
0x14014da6d  mov     r8d, eax
0x14014da70  lea     edx, [rax+7Fh]
0x14014da73  call    cs:__imp_RtlInitializeTimerWheel
0x14014da7a  nop     dword ptr [rax+rax+00h]
0x14014da7f  mov     eax, 1
0x14014da84  mov     [rsp+30h+var_10], r14d
0x14014da89  mov     r9d, eax
0x14014da8c  lea     rcx, [rbx+1270h]
0x14014da93  mov     r8d, eax
0x14014da96  lea     edx, [rax+3Fh]
0x14014da99  call    cs:__imp_RtlInitializeTimerWheel
0x14014daa0  nop     dword ptr [rax+rax+00h]
0x14014daa5  xor     r8d, r8d; Flags
0x14014daa8  mov     [rbp+HashTable], r13
0x14014daac  lea     rcx, [rbp+HashTable]; HashTable
0x14014dab0  lea     edx, [r8+6]; Shift
0x14014dab4  call    cs:__imp_RtlCreateHashTable
0x14014dabb  nop     dword ptr [rax+rax+00h]
0x14014dac0  test    al, al
0x14014dac2  jz      loc_14014DC3E
0x14014dac8  xor     r8d, r8d; Flags
0x14014dacb  lea     rax, [r13+78h]
0x14014dacf  lea     rcx, [rbp+HashTable]; HashTable
0x14014dad3  mov     [rbp+HashTable], rax
0x14014dad7  lea     edx, [r8+6]; Shift
0x14014dadb  call    cs:__imp_RtlCreateHashTable
0x14014dae2  nop     dword ptr [rax+rax+00h]
0x14014dae7  test    al, al
0x14014dae9  jz      loc_14014DC3E
0x14014daef  xor     r8d, r8d; Flags
0x14014daf2  lea     rax, [r13+50h]
0x14014daf6  lea     rcx, [rbp+HashTable]; HashTable
0x14014dafa  mov     [rbp+HashTable], rax
0x14014dafe  lea     edx, [r8+6]; Shift
0x14014db02  call    cs:__imp_RtlCreateHashTable
0x14014db09  nop     dword ptr [rax+rax+00h]
0x14014db0e  test    al, al
0x14014db10  jz      loc_14014DC3E
0x14014db16  lea     rax, [r13+28h]
0x14014db1a  xor     r8d, r8d; Flags
0x14014db1d  lea     rcx, [rbp+HashTable]; HashTable
0x14014db21  mov     [rbp+HashTable], rax
0x14014db25  lea     r13d, [r8+6]
0x14014db29  mov     edx, r13d; Shift
0x14014db2c  call    cs:__imp_RtlCreateHashTable
0x14014db33  nop     dword ptr [rax+rax+00h]
0x14014db38  test    al, al
0x14014db3a  jz      loc_14014DC3E
0x14014db40  mov     rcx, cs:PartitionTable
0x14014db47  xor     r8d, r8d; Flags
0x14014db4a  add     rcx, 18h
0x14014db4e  mov     edx, r13d; Shift
0x14014db51  add     rcx, rdi
0x14014db54  mov     [rbp+HashTable], rcx
0x14014db58  lea     rcx, [rbp+HashTable]; HashTable
0x14014db5c  call    cs:__imp_RtlCreateHashTable
0x14014db63  nop     dword ptr [rax+rax+00h]
0x14014db68  test    al, al
0x14014db6a  jz      loc_14014DC3E
0x14014db70  mov     rax, cs:PartitionTable
0x14014db77  lea     rcx, [rsi+100h]
0x14014db7e  xor     r8d, r8d; Flags
0x14014db81  mov     edx, r13d; Shift
0x14014db84  mov     [rdi+rax+10h], rcx
0x14014db89  mov     [rbp+HashTable], rcx
0x14014db8d  lea     rcx, [rbp+HashTable]; HashTable
0x14014db91  call    cs:__imp_RtlCreateHashTable
0x14014db98  nop     dword ptr [rax+rax+00h]
0x14014db9d  test    al, al
0x14014db9f  jz      loc_14014DC3E
0x14014dba5  lea     rax, [rsi+178h]
0x14014dbac  xor     r8d, r8d; Flags
0x14014dbaf  mov     edx, r13d; Shift
0x14014dbb2  mov     [rbp+HashTable], rax
0x14014dbb6  lea     rcx, [rbp+HashTable]; HashTable
0x14014dbba  call    cs:__imp_RtlCreateHashTable
0x14014dbc1  nop     dword ptr [rax+rax+00h]
0x14014dbc6  test    al, al
0x14014dbc8  jz      short loc_14014DC3E
0x14014dbca  lea     rax, [rsi+150h]
0x14014dbd1  xor     r8d, r8d; Flags
0x14014dbd4  mov     edx, r13d; Shift
0x14014dbd7  mov     [rbp+HashTable], rax
0x14014dbdb  lea     rcx, [rbp+HashTable]; HashTable
0x14014dbdf  call    cs:__imp_RtlCreateHashTable
0x14014dbe6  nop     dword ptr [rax+rax+00h]
0x14014dbeb  test    al, al
0x14014dbed  jz      short loc_14014DC3E
0x14014dbef  lea     rax, [rsi+128h]
0x14014dbf6  xor     r8d, r8d; Flags
0x14014dbf9  mov     edx, r13d; Shift
0x14014dbfc  mov     [rbp+HashTable], rax
0x14014dc00  lea     rcx, [rbp+HashTable]; HashTable
0x14014dc04  call    cs:__imp_RtlCreateHashTable
0x14014dc0b  nop     dword ptr [rax+rax+00h]
0x14014dc10  test    al, al
0x14014dc12  jz      short loc_14014DC3E
0x14014dc14  mov     rcx, cs:PartitionTable
0x14014dc1b  mov     edx, 1000h
0x14014dc20  add     rcx, 50h ; 'P'
0x14014dc24  mov     r8d, 4E526354h
0x14014dc2a  add     rcx, rdi
0x14014dc2d  call    RngInitializeRngPool
0x14014dc32  test    al, al
0x14014dc34  jz      short loc_14014DC3E
0x14014dc36  inc     r15d
0x14014dc39  jmp     loc_14014D96B
0x14014dc3e  xor     edx, edx; Tag
0x14014dc40  mov     rcx, rsi; P
0x14014dc43  call    cs:__imp_ExFreePoolWithTag
0x14014dc4a  nop     dword ptr [rax+rax+00h]
0x14014dc4f  mov     rcx, rbx
0x14014dc52  jmp     short loc_14014DC57
0x14014dc54  mov     rcx, rsi; P
0x14014dc57  xor     edx, edx; Tag
0x14014dc59  call    cs:__imp_ExFreePoolWithTag
0x14014dc60  nop     dword ptr [rax+rax+00h]
0x14014dc65  mov     ecx, r15d
0x14014dc68  call    TcpCleanupPartitionModule
0x14014dc6d  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 0
0x14014dc74  jge     short loc_14014DC90
0x14014dc76  lea     r9, aConnectionPart; "connection partitions (TCP)"
0x14014dc7d  lea     rdx, TCPIP_MEMORY_FAILURES
0x14014dc84  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014dc8b  call    McTemplateK0z_EtwWriteTransfer
0x14014dc90  mov     eax, 0C0000017h
0x14014dc95  jmp     short loc_14014DCC5
0x14014dc97  bts     cs:TcpStartedModules, 15h
0x14014dca0  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 10h
0x14014dca7  jz      short loc_14014DCC3
0x14014dca9  lea     r9, aPartitionmodul; "PartitionModule"
0x14014dcb0  lea     rdx, TCPIP_MODULE_STARTED
0x14014dcb7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014dcbe  call    McTemplateK0z_EtwWriteTransfer
0x14014dcc3  xor     eax, eax
0x14014dcc5  mov     rbx, [rsp+30h+arg_10]
0x14014dccd  add     rsp, 30h
0x14014dcd1  pop     r15
0x14014dcd3  pop     r14
0x14014dcd5  pop     r13
0x14014dcd7  pop     r12
0x14014dcd9  pop     rdi
0x14014dcda  pop     rsi
0x14014dcdb  pop     rbp
0x14014dcdc  retn
```
