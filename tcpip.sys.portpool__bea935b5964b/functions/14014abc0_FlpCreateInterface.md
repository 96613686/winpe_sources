# FlpCreateInterface

- ea: `0x14014abc0`
- end: `0x14014b00b`
- name: `FlpCreateInterface`
- size: `1099`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14014a070`
- `0x14014bcc0`
- `0x1401c087c`

## callees

- `0x140014a08`
- `0x14007b0e8`
- `0x14007b590`
- `0x14014abc0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14014ae00`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14014ae00`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14014ac1c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14014ac1c`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014af80`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014af95`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014afaa`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014af80`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014af95`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014afaa`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14014ac32`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14014ac4c`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14014ac66`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14014ac32`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14014ac4c`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14014ac66`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14014ae10`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14014ae20`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14014ae30`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14014ae10`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14014ae20`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14014ae30`
- `ntoskrnl!IoAllocateWorkItem` at `0x14014acca`
- `ntoskrnl!IoAllocateWorkItem` at `0x14014acca`
- `ntoskrnl!IoFreeWorkItem` at `0x14014af6b`
- `ntoskrnl!IoFreeWorkItem` at `0x14014af6b`
- `ntoskrnl!RtlDeleteHashTable` at `0x14014af19`
- `ntoskrnl!RtlDeleteHashTable` at `0x14014af31`
- `ntoskrnl!RtlDeleteHashTable` at `0x14014af19`
- `ntoskrnl!RtlDeleteHashTable` at `0x14014af31`
- `ntoskrnl!RtlCreateHashTable` at `0x14014ad51`
- `ntoskrnl!RtlCreateHashTable` at `0x14014ad90`
- `ntoskrnl!RtlCreateHashTable` at `0x14014ad51`
- `ntoskrnl!RtlCreateHashTable` at `0x14014ad90`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14014abe2`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14014abe2`
- `ntoskrnl!KeInitializeEvent` at `0x14014ae67`
- `ntoskrnl!KeInitializeEvent` at `0x14014ae7f`
- `ntoskrnl!KeInitializeEvent` at `0x14014ae67`
- `ntoskrnl!KeInitializeEvent` at `0x14014ae7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014afe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014afe9`
- `NETIO!NetioInitializeWorkQueue` at `0x14014ad0d`
- `NETIO!NetioInitializeWorkQueue` at `0x14014ad0d`
- `NETIO!NetioShutdownWorkQueue` at `0x14014afbf`
- `NETIO!NetioShutdownWorkQueue` at `0x14014afbf`
- `NDIS!NdisFreeRWLock` at `0x14014afd4`
- `NDIS!NdisFreeRWLock` at `0x14014afd4`
- `NDIS!NdisAllocateRWLock` at `0x14014ac95`
- `NDIS!NdisAllocateRWLock` at `0x14014ac95`

## pseudocode

```c
struct _EX_RUNDOWN_REF *__fastcall FlpCreateInterface(ULONG_PTR a1)
{
  ULONG MaximumProcessorCount; // eax
  struct _EX_RUNDOWN_REF *Memory; // rax
  struct _EX_RUNDOWN_REF *v4; // rbx
  char v5; // di
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  __int64 v7; // r8
  PNDIS_RW_LOCK_EX RWLock; // rax
  const wchar_t *v9; // r9
  PIO_WORKITEM WorkItem; // rax
  __int64 v11; // r8
  char v12; // si
  __int64 v13; // rdx
  __int64 v14; // rcx
  struct _EX_RUNDOWN_REF *v15; // rax
  struct _EX_RUNDOWN_REF *result; // rax
  unsigned int v17; // ecx
  struct _IO_WORKITEM *Count; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v19; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v20; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v21; // rcx
  struct _NDIS_RW_LOCK_EX *v22; // rcx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+48h] [rbp+10h] BYREF

  HashTable = 0;
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  Memory = (struct _EX_RUNDOWN_REF *)FlpAllocateMemory(32 * MaximumProcessorCount + 1608);
  v4 = Memory;
  if ( !Memory )
    return 0;
  Memory[124].Count = (ULONG_PTR)&Memory[201];
  v5 = 0;
  ExInitializeRundownProtection(Memory + 7);
  v4[8].Count = (ULONG_PTR)ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x49706C46u);
  v4[9].Count = (ULONG_PTR)ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x49706C46u);
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x49706C46u);
  v4[10].Count = (ULONG_PTR)CacheAwareRundownProtection;
  if ( !v4[8].Count || !v4[9].Count || !CacheAwareRundownProtection )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      v9 = L"interface locks (FLNG)";
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  RWLock = NdisAllocateRWLock(0);
  v4[5].Count = (ULONG_PTR)RWLock;
  if ( !RWLock )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      v9 = L"Ndislock (FLNG)";
LABEL_29:
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v7, v9);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  WorkItem = IoAllocateWorkItem(FlpDeviceObject);
  v4[12].Count = (ULONG_PTR)WorkItem;
  if ( !WorkItem )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      v9 = L"interface work item (FLNG)";
      goto LABEL_29;
    }
LABEL_30:
    Count = (struct _IO_WORKITEM *)v4[12].Count;
    if ( Count )
      IoFreeWorkItem(Count);
    v19 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v4[8].Count;
    if ( v19 )
      ExFreeCacheAwareRundownProtection(v19);
    v20 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v4[9].Count;
    if ( v20 )
      ExFreeCacheAwareRundownProtection(v20);
    v21 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v4[10].Count;
    if ( v21 )
      ExFreeCacheAwareRundownProtection(v21);
    if ( v5 )
      NetioShutdownWorkQueue(&v4[15]);
    v22 = (struct _NDIS_RW_LOCK_EX *)v4[5].Count;
    if ( v22 )
    {
      NdisFreeRWLock(v22);
      v4[5].Count = 0;
    }
    ExFreePoolWithTag(v4, 0);
    return 0;
  }
  if ( (int)NetioInitializeWorkQueue(
              &v4[15],
              FlIfProviderQuerySystemWorker,
              *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters,
              0) < 0 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      v9 = L"Virtual If work queue (FLNG)";
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)&v4[26];
  v5 = 1;
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
    {
      v9 = L"IsolationIdClientInterfaceTable (FLNG)";
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)&v4[31];
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    v12 = 0;
    if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v11,
        L"IfIndexClientInterfaceTable (FLNG)");
    goto LABEL_25;
  }
  if ( !(unsigned __int8)RoReferenceEx(*(_QWORD *)(a1 + 216) + 32LL) )
  {
    v12 = 1;
LABEL_25:
    RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)&v4[26]);
    if ( v12 )
      RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)&v4[31]);
    goto LABEL_30;
  }
  v4[4].Count = a1;
  v4[3].Count = (ULONG_PTR)&v4[2];
  v4[2].Count = (ULONG_PTR)&v4[2];
  LODWORD(v4[6].Count) = 1;
  LODWORD(v4[11].Count) = 1;
  ExWaitForRundownProtectionRelease(v4 + 7);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[8].Count);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[9].Count);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[10].Count);
  HIDWORD(v4[107].Ptr) = 1;
  v4[112].Count = (ULONG_PTR)&v4[111];
  v4[111].Count = (ULONG_PTR)&v4[111];
  v4[14].Count = (ULONG_PTR)&v4[13];
  v4[13].Count = (ULONG_PTR)&v4[13];
  KeInitializeEvent((PRKEVENT)&v4[21], SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)&v4[108], SynchronizationEvent, 0);
  v13 = 0;
  LODWORD(v4[24].Count) = 0;
  v14 = 0;
  LODWORD(v4[40].Count) = -1;
  LODWORD(v4[41].Count) = 0;
  do
  {
    ++v13;
    v15 = &v4[v14 + 42];
    v4[v14 + 43].Count = (ULONG_PTR)v15;
    v4[v14 + 42].Count = (ULONG_PTR)v15;
    v14 += 2;
  }
  while ( v13 != 29 );
  BYTE1(v4[155].Count) = 1;
  result = v4;
  BYTE3(v4[155].Ptr) = 64;
  BYTE4(v4[155].Ptr) = *(_BYTE *)(a1 + 384);
  v17 = HIDWORD(v4[158].Ptr) & 0xFFFFFBFF;
  v4[157].Count = 0;
  HIDWORD(v4[158].Ptr) = v17 | 0x1FF;
  return result;
}

```

## disassembly

```asm
0x14014abc0  mov     [rsp+arg_0], rbx
0x14014abc5  mov     [rsp+arg_10], rbp
0x14014abca  push    rsi
0x14014abcb  push    rdi
0x14014abcc  push    r12
0x14014abce  sub     rsp, 20h
0x14014abd2  mov     rsi, rcx
0x14014abd5  xor     r12d, r12d
0x14014abd8  mov     ecx, 0FFFFh; GroupNumber
0x14014abdd  mov     [rsp+38h+HashTable], r12
0x14014abe2  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14014abe9  nop     dword ptr [rax+rax+00h]
0x14014abee  shl     eax, 5
0x14014abf1  lea     ecx, [rax+648h]
0x14014abf7  call    FlpAllocateMemory
0x14014abfc  mov     rbx, rax
0x14014abff  test    rax, rax
0x14014ac02  jz      loc_14014AFF5
0x14014ac08  add     rax, 648h
0x14014ac0e  lea     rcx, [rbx+38h]; RunRef
0x14014ac12  mov     [rbx+3E0h], rax
0x14014ac19  mov     dil, r12b
0x14014ac1c  call    cs:__imp_ExInitializeRundownProtection
0x14014ac23  nop     dword ptr [rax+rax+00h]
0x14014ac28  mov     edx, 49706C46h; PoolTag
0x14014ac2d  mov     ecx, 200h; PoolType
0x14014ac32  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14014ac39  nop     dword ptr [rax+rax+00h]
0x14014ac3e  mov     edx, 49706C46h; PoolTag
0x14014ac43  mov     ecx, 200h; PoolType
0x14014ac48  mov     [rbx+40h], rax
0x14014ac4c  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14014ac53  nop     dword ptr [rax+rax+00h]
0x14014ac58  mov     edx, 49706C46h; PoolTag
0x14014ac5d  mov     ecx, 200h; PoolType
0x14014ac62  mov     [rbx+48h], rax
0x14014ac66  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14014ac6d  nop     dword ptr [rax+rax+00h]
0x14014ac72  mov     [rbx+50h], rax
0x14014ac76  cmp     [rbx+40h], r12
0x14014ac7a  jz      loc_14014AF3F
0x14014ac80  cmp     [rbx+48h], r12
0x14014ac84  jz      loc_14014AF3F
0x14014ac8a  test    rax, rax
0x14014ac8d  jz      loc_14014AF3F
0x14014ac93  xor     ecx, ecx; NdisHandle
0x14014ac95  call    cs:__imp_NdisAllocateRWLock
0x14014ac9c  nop     dword ptr [rax+rax+00h]
0x14014aca1  mov     [rbx+28h], rax
0x14014aca5  test    rax, rax
0x14014aca8  jnz     short loc_14014ACC3
0x14014acaa  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r12b
0x14014acb1  jge     loc_14014AF62
0x14014acb7  lea     r9, aNdislockFlng; "Ndislock (FLNG)"
0x14014acbe  jmp     loc_14014AF4F
0x14014acc3  mov     rcx, cs:FlpDeviceObject; DeviceObject
0x14014acca  call    cs:__imp_IoAllocateWorkItem
0x14014acd1  nop     dword ptr [rax+rax+00h]
0x14014acd6  mov     [rbx+60h], rax
0x14014acda  test    rax, rax
0x14014acdd  jnz     short loc_14014ACF8
0x14014acdf  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r12b
0x14014ace6  jge     loc_14014AF62
0x14014acec  lea     r9, aInterfaceWorkI; "interface work item (FLNG)"
0x14014acf3  jmp     loc_14014AF4F
0x14014acf8  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14014acff  lea     rcx, [rbx+78h]
0x14014ad03  xor     r9d, r9d
0x14014ad06  lea     rdx, FlIfProviderQuerySystemWorker
0x14014ad0d  call    cs:__imp_NetioInitializeWorkQueue
0x14014ad14  nop     dword ptr [rax+rax+00h]
0x14014ad19  test    eax, eax
0x14014ad1b  jns     short loc_14014AD36
0x14014ad1d  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r12b
0x14014ad24  jge     loc_14014AF62
0x14014ad2a  lea     r9, aVirtualIfWorkQ; "Virtual If work queue (FLNG)"
0x14014ad31  jmp     loc_14014AF4F
0x14014ad36  lea     rax, [rbx+0D0h]
0x14014ad3d  xor     r8d, r8d; Flags
0x14014ad40  xor     edx, edx; Shift
0x14014ad42  mov     [rsp+38h+HashTable], rax
0x14014ad47  lea     rcx, [rsp+38h+HashTable]; HashTable
0x14014ad4c  mov     edi, 1
0x14014ad51  call    cs:__imp_RtlCreateHashTable
0x14014ad58  nop     dword ptr [rax+rax+00h]
0x14014ad5d  test    al, al
0x14014ad5f  jnz     short loc_14014AD7A
0x14014ad61  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r12b
0x14014ad68  jge     loc_14014AF62
0x14014ad6e  lea     r9, aIsolationidcli; "IsolationIdClientInterfaceTable (FLNG)"
0x14014ad75  jmp     loc_14014AF4F
0x14014ad7a  lea     rax, [rbx+0F8h]
0x14014ad81  xor     r8d, r8d; Flags
0x14014ad84  xor     edx, edx; Shift
0x14014ad86  mov     [rsp+38h+HashTable], rax
0x14014ad8b  lea     rcx, [rsp+38h+HashTable]; HashTable
0x14014ad90  call    cs:__imp_RtlCreateHashTable
0x14014ad97  nop     dword ptr [rax+rax+00h]
0x14014ad9c  test    al, al
0x14014ad9e  jnz     short loc_14014ADCF
0x14014ada0  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r12b
0x14014ada7  mov     sil, r12b
0x14014adaa  jge     loc_14014AF12
0x14014adb0  lea     r9, aIfindexclienti; "IfIndexClientInterfaceTable (FLNG)"
0x14014adb7  lea     rdx, TCPIP_MEMORY_FAILURES
0x14014adbe  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014adc5  call    McTemplateK0z_EtwWriteTransfer
0x14014adca  jmp     loc_14014AF12
0x14014adcf  mov     rcx, [rsi+0D8h]
0x14014add6  add     rcx, 20h ; ' '
0x14014adda  call    RoReferenceEx
0x14014addf  test    al, al
0x14014ade1  jz      loc_14014AF0F
0x14014ade7  lea     rax, [rbx+10h]
0x14014adeb  mov     [rbx+20h], rsi
0x14014adef  mov     [rax+8], rax
0x14014adf3  lea     rcx, [rbx+38h]; RunRef
0x14014adf7  mov     [rax], rax
0x14014adfa  mov     [rbx+30h], edi
0x14014adfd  mov     [rbx+58h], edi
0x14014ae00  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14014ae07  nop     dword ptr [rax+rax+00h]
0x14014ae0c  mov     rcx, [rbx+40h]; RunRef
0x14014ae10  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14014ae17  nop     dword ptr [rax+rax+00h]
0x14014ae1c  mov     rcx, [rbx+48h]; RunRef
0x14014ae20  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14014ae27  nop     dword ptr [rax+rax+00h]
0x14014ae2c  mov     rcx, [rbx+50h]; RunRef
0x14014ae30  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14014ae37  nop     dword ptr [rax+rax+00h]
0x14014ae3c  lea     rax, [rbx+378h]
0x14014ae43  mov     [rbx+35Ch], edi
0x14014ae49  mov     [rax+8], rax
0x14014ae4d  lea     rcx, [rbx+0A8h]; Event
0x14014ae54  mov     [rax], rax
0x14014ae57  xor     r8d, r8d; State
0x14014ae5a  lea     rax, [rbx+68h]
0x14014ae5e  mov     edx, edi; Type
0x14014ae60  mov     [rax+8], rax
0x14014ae64  mov     [rax], rax
0x14014ae67  call    cs:__imp_KeInitializeEvent
0x14014ae6e  nop     dword ptr [rax+rax+00h]
0x14014ae73  lea     rcx, [rbx+360h]; Event
0x14014ae7a  xor     r8d, r8d; State
0x14014ae7d  mov     edx, edi; Type
0x14014ae7f  call    cs:__imp_KeInitializeEvent
0x14014ae86  nop     dword ptr [rax+rax+00h]
0x14014ae8b  mov     rdx, r12
0x14014ae8e  mov     [rbx+0C0h], r12d
0x14014ae95  mov     rcx, r12
0x14014ae98  mov     dword ptr [rbx+140h], 0FFFFFFFFh
0x14014aea2  mov     [rbx+148h], r12d
0x14014aea9  lea     rax, [rbx+150h]
0x14014aeb0  add     rdx, rdi
0x14014aeb3  add     rax, rcx
0x14014aeb6  mov     [rbx+rcx+158h], rax
0x14014aebe  mov     [rbx+rcx+150h], rax
0x14014aec6  add     rcx, 10h
0x14014aeca  cmp     rdx, 1Dh
0x14014aece  jnz     short loc_14014AEA9
0x14014aed0  mov     [rbx+4D9h], dil
0x14014aed7  mov     rax, rbx
0x14014aeda  mov     byte ptr [rbx+4DBh], 40h ; '@'
0x14014aee1  mov     cl, [rsi+180h]
0x14014aee7  mov     [rbx+4DCh], cl
0x14014aeed  mov     ecx, [rbx+4F4h]
0x14014aef3  btr     ecx, 0Ah
0x14014aef7  mov     [rbx+4E8h], r12
0x14014aefe  or      ecx, 1FFh
0x14014af04  mov     [rbx+4F4h], ecx
0x14014af0a  jmp     loc_14014AFF7
0x14014af0f  mov     sil, dil
0x14014af12  lea     rcx, [rbx+0D0h]; HashTable
0x14014af19  call    cs:__imp_RtlDeleteHashTable
0x14014af20  nop     dword ptr [rax+rax+00h]
0x14014af25  test    sil, sil
0x14014af28  jz      short loc_14014AF62
0x14014af2a  lea     rcx, [rbx+0F8h]; HashTable
0x14014af31  call    cs:__imp_RtlDeleteHashTable
0x14014af38  nop     dword ptr [rax+rax+00h]
0x14014af3d  jmp     short loc_14014AF62
0x14014af3f  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, r12b
0x14014af46  jge     short loc_14014AF62
0x14014af48  lea     r9, aInterfaceLocks; "interface locks (FLNG)"
0x14014af4f  lea     rdx, TCPIP_MEMORY_FAILURES
0x14014af56  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14014af5d  call    McTemplateK0z_EtwWriteTransfer
0x14014af62  mov     rcx, [rbx+60h]; IoWorkItem
0x14014af66  test    rcx, rcx
0x14014af69  jz      short loc_14014AF77
0x14014af6b  call    cs:__imp_IoFreeWorkItem
0x14014af72  nop     dword ptr [rax+rax+00h]
0x14014af77  mov     rcx, [rbx+40h]; RunRefCacheAware
0x14014af7b  test    rcx, rcx
0x14014af7e  jz      short loc_14014AF8C
0x14014af80  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14014af87  nop     dword ptr [rax+rax+00h]
0x14014af8c  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14014af90  test    rcx, rcx
0x14014af93  jz      short loc_14014AFA1
0x14014af95  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14014af9c  nop     dword ptr [rax+rax+00h]
0x14014afa1  mov     rcx, [rbx+50h]; RunRefCacheAware
0x14014afa5  test    rcx, rcx
0x14014afa8  jz      short loc_14014AFB6
0x14014afaa  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14014afb1  nop     dword ptr [rax+rax+00h]
0x14014afb6  test    dil, dil
0x14014afb9  jz      short loc_14014AFCB
0x14014afbb  lea     rcx, [rbx+78h]
0x14014afbf  call    cs:__imp_NetioShutdownWorkQueue
0x14014afc6  nop     dword ptr [rax+rax+00h]
0x14014afcb  mov     rcx, [rbx+28h]; Lock
0x14014afcf  test    rcx, rcx
0x14014afd2  jz      short loc_14014AFE4
0x14014afd4  call    cs:__imp_NdisFreeRWLock
0x14014afdb  nop     dword ptr [rax+rax+00h]
0x14014afe0  mov     [rbx+28h], r12
0x14014afe4  xor     edx, edx; Tag
0x14014afe6  mov     rcx, rbx; P
0x14014afe9  call    cs:__imp_ExFreePoolWithTag
0x14014aff0  nop     dword ptr [rax+rax+00h]
0x14014aff5  xor     eax, eax
0x14014aff7  mov     rbx, [rsp+38h+arg_0]
0x14014affc  mov     rbp, [rsp+38h+arg_10]
0x14014b001  add     rsp, 20h
0x14014b005  pop     r12
0x14014b007  pop     rdi
0x14014b008  pop     rsi
0x14014b009  retn
```
