# FlpCreateInterface

- ea: `0x140148940`
- end: `0x140148d8b`
- name: `FlpCreateInterface`
- size: `1099`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140147df0`
- `0x140149eb0`
- `0x1401bec3c`

## callees

- `0x14004e290`
- `0x140053e98`
- `0x1400c82f8`
- `0x140148940`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140148b80`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140148b80`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14014899c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14014899c`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148d00`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148d15`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148d2a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148d00`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148d15`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148d2a`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401489b2`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401489cc`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401489e6`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401489b2`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401489cc`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x1401489e6`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148b90`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148ba0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148bb0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148b90`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148ba0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148bb0`
- `ntoskrnl!IoAllocateWorkItem` at `0x140148a4a`
- `ntoskrnl!IoAllocateWorkItem` at `0x140148a4a`
- `ntoskrnl!IoFreeWorkItem` at `0x140148ceb`
- `ntoskrnl!IoFreeWorkItem` at `0x140148ceb`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148c99`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148cb1`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148c99`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148cb1`
- `ntoskrnl!RtlCreateHashTable` at `0x140148ad1`
- `ntoskrnl!RtlCreateHashTable` at `0x140148b10`
- `ntoskrnl!RtlCreateHashTable` at `0x140148ad1`
- `ntoskrnl!RtlCreateHashTable` at `0x140148b10`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140148962`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140148962`
- `ntoskrnl!KeInitializeEvent` at `0x140148be7`
- `ntoskrnl!KeInitializeEvent` at `0x140148bff`
- `ntoskrnl!KeInitializeEvent` at `0x140148be7`
- `ntoskrnl!KeInitializeEvent` at `0x140148bff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148d69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148d69`
- `NETIO!NetioInitializeWorkQueue` at `0x140148a8d`
- `NETIO!NetioInitializeWorkQueue` at `0x140148a8d`
- `NETIO!NetioShutdownWorkQueue` at `0x140148d3f`
- `NETIO!NetioShutdownWorkQueue` at `0x140148d3f`
- `NDIS!NdisFreeRWLock` at `0x140148d54`
- `NDIS!NdisFreeRWLock` at `0x140148d54`
- `NDIS!NdisAllocateRWLock` at `0x140148a15`
- `NDIS!NdisAllocateRWLock` at `0x140148a15`

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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
  if ( (int)NetioInitializeWorkQueue(&v4[15], FlIfProviderQuerySystemWorker, WPP_MAIN_CB.Queue.Wcb.DeviceObject, 0) < 0 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
0x140148940  mov     [rsp+arg_0], rbx
0x140148945  mov     [rsp+arg_10], rbp
0x14014894a  push    rsi
0x14014894b  push    rdi
0x14014894c  push    r12
0x14014894e  sub     rsp, 20h
0x140148952  mov     rsi, rcx
0x140148955  xor     r12d, r12d
0x140148958  mov     ecx, 0FFFFh; GroupNumber
0x14014895d  mov     [rsp+38h+HashTable], r12
0x140148962  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140148969  nop     dword ptr [rax+rax+00h]
0x14014896e  shl     eax, 5
0x140148971  lea     ecx, [rax+648h]
0x140148977  call    FlpAllocateMemory
0x14014897c  mov     rbx, rax
0x14014897f  test    rax, rax
0x140148982  jz      loc_140148D75
0x140148988  add     rax, 648h
0x14014898e  lea     rcx, [rbx+38h]; RunRef
0x140148992  mov     [rbx+3E0h], rax
0x140148999  mov     dil, r12b
0x14014899c  call    cs:__imp_ExInitializeRundownProtection
0x1401489a3  nop     dword ptr [rax+rax+00h]
0x1401489a8  mov     edx, 49706C46h; PoolTag
0x1401489ad  mov     ecx, 200h; PoolType
0x1401489b2  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401489b9  nop     dword ptr [rax+rax+00h]
0x1401489be  mov     edx, 49706C46h; PoolTag
0x1401489c3  mov     ecx, 200h; PoolType
0x1401489c8  mov     [rbx+40h], rax
0x1401489cc  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401489d3  nop     dword ptr [rax+rax+00h]
0x1401489d8  mov     edx, 49706C46h; PoolTag
0x1401489dd  mov     ecx, 200h; PoolType
0x1401489e2  mov     [rbx+48h], rax
0x1401489e6  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x1401489ed  nop     dword ptr [rax+rax+00h]
0x1401489f2  mov     [rbx+50h], rax
0x1401489f6  cmp     [rbx+40h], r12
0x1401489fa  jz      loc_140148CBF
0x140148a00  cmp     [rbx+48h], r12
0x140148a04  jz      loc_140148CBF
0x140148a0a  test    rax, rax
0x140148a0d  jz      loc_140148CBF
0x140148a13  xor     ecx, ecx; NdisHandle
0x140148a15  call    cs:__imp_NdisAllocateRWLock
0x140148a1c  nop     dword ptr [rax+rax+00h]
0x140148a21  mov     [rbx+28h], rax
0x140148a25  test    rax, rax
0x140148a28  jnz     short loc_140148A43
0x140148a2a  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148a31  jge     loc_140148CE2
0x140148a37  lea     r9, aNdislockFlng; "Ndislock (FLNG)"
0x140148a3e  jmp     loc_140148CCF
0x140148a43  mov     rcx, cs:FlpDeviceObject; DeviceObject
0x140148a4a  call    cs:__imp_IoAllocateWorkItem
0x140148a51  nop     dword ptr [rax+rax+00h]
0x140148a56  mov     [rbx+60h], rax
0x140148a5a  test    rax, rax
0x140148a5d  jnz     short loc_140148A78
0x140148a5f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148a66  jge     loc_140148CE2
0x140148a6c  lea     r9, aInterfaceWorkI; "interface work item (FLNG)"
0x140148a73  jmp     loc_140148CCF
0x140148a78  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140148a7f  lea     rcx, [rbx+78h]
0x140148a83  xor     r9d, r9d
0x140148a86  lea     rdx, FlIfProviderQuerySystemWorker
0x140148a8d  call    cs:__imp_NetioInitializeWorkQueue
0x140148a94  nop     dword ptr [rax+rax+00h]
0x140148a99  test    eax, eax
0x140148a9b  jns     short loc_140148AB6
0x140148a9d  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148aa4  jge     loc_140148CE2
0x140148aaa  lea     r9, aVirtualIfWorkQ; "Virtual If work queue (FLNG)"
0x140148ab1  jmp     loc_140148CCF
0x140148ab6  lea     rax, [rbx+0D0h]
0x140148abd  xor     r8d, r8d; Flags
0x140148ac0  xor     edx, edx; Shift
0x140148ac2  mov     [rsp+38h+HashTable], rax
0x140148ac7  lea     rcx, [rsp+38h+HashTable]; HashTable
0x140148acc  mov     edi, 1
0x140148ad1  call    cs:__imp_RtlCreateHashTable
0x140148ad8  nop     dword ptr [rax+rax+00h]
0x140148add  test    al, al
0x140148adf  jnz     short loc_140148AFA
0x140148ae1  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148ae8  jge     loc_140148CE2
0x140148aee  lea     r9, aIsolationidcli; "IsolationIdClientInterfaceTable (FLNG)"
0x140148af5  jmp     loc_140148CCF
0x140148afa  lea     rax, [rbx+0F8h]
0x140148b01  xor     r8d, r8d; Flags
0x140148b04  xor     edx, edx; Shift
0x140148b06  mov     [rsp+38h+HashTable], rax
0x140148b0b  lea     rcx, [rsp+38h+HashTable]; HashTable
0x140148b10  call    cs:__imp_RtlCreateHashTable
0x140148b17  nop     dword ptr [rax+rax+00h]
0x140148b1c  test    al, al
0x140148b1e  jnz     short loc_140148B4F
0x140148b20  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148b27  mov     sil, r12b
0x140148b2a  jge     loc_140148C92
0x140148b30  lea     r9, aIfindexclienti; "IfIndexClientInterfaceTable (FLNG)"
0x140148b37  lea     rdx, TCPIP_MEMORY_FAILURES
0x140148b3e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140148b45  call    McTemplateK0z_EtwWriteTransfer
0x140148b4a  jmp     loc_140148C92
0x140148b4f  mov     rcx, [rsi+0D8h]
0x140148b56  add     rcx, 20h ; ' '
0x140148b5a  call    RoReferenceEx
0x140148b5f  test    al, al
0x140148b61  jz      loc_140148C8F
0x140148b67  lea     rax, [rbx+10h]
0x140148b6b  mov     [rbx+20h], rsi
0x140148b6f  mov     [rax+8], rax
0x140148b73  lea     rcx, [rbx+38h]; RunRef
0x140148b77  mov     [rax], rax
0x140148b7a  mov     [rbx+30h], edi
0x140148b7d  mov     [rbx+58h], edi
0x140148b80  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140148b87  nop     dword ptr [rax+rax+00h]
0x140148b8c  mov     rcx, [rbx+40h]; RunRef
0x140148b90  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140148b97  nop     dword ptr [rax+rax+00h]
0x140148b9c  mov     rcx, [rbx+48h]; RunRef
0x140148ba0  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140148ba7  nop     dword ptr [rax+rax+00h]
0x140148bac  mov     rcx, [rbx+50h]; RunRef
0x140148bb0  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140148bb7  nop     dword ptr [rax+rax+00h]
0x140148bbc  lea     rax, [rbx+378h]
0x140148bc3  mov     [rbx+35Ch], edi
0x140148bc9  mov     [rax+8], rax
0x140148bcd  lea     rcx, [rbx+0A8h]; Event
0x140148bd4  mov     [rax], rax
0x140148bd7  xor     r8d, r8d; State
0x140148bda  lea     rax, [rbx+68h]
0x140148bde  mov     edx, edi; Type
0x140148be0  mov     [rax+8], rax
0x140148be4  mov     [rax], rax
0x140148be7  call    cs:__imp_KeInitializeEvent
0x140148bee  nop     dword ptr [rax+rax+00h]
0x140148bf3  lea     rcx, [rbx+360h]; Event
0x140148bfa  xor     r8d, r8d; State
0x140148bfd  mov     edx, edi; Type
0x140148bff  call    cs:__imp_KeInitializeEvent
0x140148c06  nop     dword ptr [rax+rax+00h]
0x140148c0b  mov     rdx, r12
0x140148c0e  mov     [rbx+0C0h], r12d
0x140148c15  mov     rcx, r12
0x140148c18  mov     dword ptr [rbx+140h], 0FFFFFFFFh
0x140148c22  mov     [rbx+148h], r12d
0x140148c29  lea     rax, [rbx+150h]
0x140148c30  add     rdx, rdi
0x140148c33  add     rax, rcx
0x140148c36  mov     [rbx+rcx+158h], rax
0x140148c3e  mov     [rbx+rcx+150h], rax
0x140148c46  add     rcx, 10h
0x140148c4a  cmp     rdx, 1Dh
0x140148c4e  jnz     short loc_140148C29
0x140148c50  mov     [rbx+4D9h], dil
0x140148c57  mov     rax, rbx
0x140148c5a  mov     byte ptr [rbx+4DBh], 40h ; '@'
0x140148c61  mov     cl, [rsi+180h]
0x140148c67  mov     [rbx+4DCh], cl
0x140148c6d  mov     ecx, [rbx+4F4h]
0x140148c73  btr     ecx, 0Ah
0x140148c77  mov     [rbx+4E8h], r12
0x140148c7e  or      ecx, 1FFh
0x140148c84  mov     [rbx+4F4h], ecx
0x140148c8a  jmp     loc_140148D77
0x140148c8f  mov     sil, dil
0x140148c92  lea     rcx, [rbx+0D0h]; HashTable
0x140148c99  call    cs:__imp_RtlDeleteHashTable
0x140148ca0  nop     dword ptr [rax+rax+00h]
0x140148ca5  test    sil, sil
0x140148ca8  jz      short loc_140148CE2
0x140148caa  lea     rcx, [rbx+0F8h]; HashTable
0x140148cb1  call    cs:__imp_RtlDeleteHashTable
0x140148cb8  nop     dword ptr [rax+rax+00h]
0x140148cbd  jmp     short loc_140148CE2
0x140148cbf  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148cc6  jge     short loc_140148CE2
0x140148cc8  lea     r9, aInterfaceLocks; "interface locks (FLNG)"
0x140148ccf  lea     rdx, TCPIP_MEMORY_FAILURES
0x140148cd6  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140148cdd  call    McTemplateK0z_EtwWriteTransfer
0x140148ce2  mov     rcx, [rbx+60h]; IoWorkItem
0x140148ce6  test    rcx, rcx
0x140148ce9  jz      short loc_140148CF7
0x140148ceb  call    cs:__imp_IoFreeWorkItem
0x140148cf2  nop     dword ptr [rax+rax+00h]
0x140148cf7  mov     rcx, [rbx+40h]; RunRefCacheAware
0x140148cfb  test    rcx, rcx
0x140148cfe  jz      short loc_140148D0C
0x140148d00  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140148d07  nop     dword ptr [rax+rax+00h]
0x140148d0c  mov     rcx, [rbx+48h]; RunRefCacheAware
0x140148d10  test    rcx, rcx
0x140148d13  jz      short loc_140148D21
0x140148d15  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140148d1c  nop     dword ptr [rax+rax+00h]
0x140148d21  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140148d25  test    rcx, rcx
0x140148d28  jz      short loc_140148D36
0x140148d2a  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140148d31  nop     dword ptr [rax+rax+00h]
0x140148d36  test    dil, dil
0x140148d39  jz      short loc_140148D4B
0x140148d3b  lea     rcx, [rbx+78h]
0x140148d3f  call    cs:__imp_NetioShutdownWorkQueue
0x140148d46  nop     dword ptr [rax+rax+00h]
0x140148d4b  mov     rcx, [rbx+28h]; Lock
0x140148d4f  test    rcx, rcx
0x140148d52  jz      short loc_140148D64
0x140148d54  call    cs:__imp_NdisFreeRWLock
0x140148d5b  nop     dword ptr [rax+rax+00h]
0x140148d60  mov     [rbx+28h], r12
0x140148d64  xor     edx, edx; Tag
0x140148d66  mov     rcx, rbx; P
0x140148d69  call    cs:__imp_ExFreePoolWithTag
0x140148d70  nop     dword ptr [rax+rax+00h]
0x140148d75  xor     eax, eax
0x140148d77  mov     rbx, [rsp+38h+arg_0]
0x140148d7c  mov     rbp, [rsp+38h+arg_10]
0x140148d81  add     rsp, 20h
0x140148d85  pop     r12
0x140148d87  pop     rdi
0x140148d88  pop     rsi
0x140148d89  retn
```
