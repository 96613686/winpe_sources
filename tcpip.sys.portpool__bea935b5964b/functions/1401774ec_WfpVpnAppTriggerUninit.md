# WfpVpnAppTriggerUninit

- ea: `0x1401774ec`
- end: `0x14017783a`
- name: `WfpVpnAppTriggerUninit`
- size: `846`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401708b4`
- `0x140170e94`

## callees

- `0x140017630`
- `0x1400176a0`
- `0x1400f64c0`
- `0x140124128`
- `0x140176710`
- `0x14017674c`
- `0x140176788`
- `0x1401769d4`
- `0x1401774ec`
- `0x140177c24`
- `0x140178b54`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x140177580`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140177580`
- `ntoskrnl!KeCancelTimer` at `0x14017755b`
- `ntoskrnl!KeCancelTimer` at `0x14017755b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401776c2`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140177784`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401776c2`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140177784`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140177674`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140177736`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140177674`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140177736`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140177694`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140177756`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140177694`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140177756`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401775e1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401775e1`
- `NETIO!NetioShutdownWorkQueue` at `0x1401775f4`
- `NETIO!NetioShutdownWorkQueue` at `0x1401775f4`
- `NDIS!NdisFreeRWLock` at `0x14017763e`
- `NDIS!NdisFreeRWLock` at `0x140177700`
- `NDIS!NdisFreeRWLock` at `0x1401777c2`
- `NDIS!NdisFreeRWLock` at `0x14017780f`
- `NDIS!NdisFreeRWLock` at `0x14017763e`
- `NDIS!NdisFreeRWLock` at `0x140177700`
- `NDIS!NdisFreeRWLock` at `0x1401777c2`
- `NDIS!NdisFreeRWLock` at `0x14017780f`
- `fwpkclnt!FwpmEngineClose0` at `0x140177624`
- `fwpkclnt!FwpmEngineClose0` at `0x140177624`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x14017760c`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x14017760c`

## pseudocode

```c
void WfpVpnAppTriggerUninit()
{
  bool v0; // bl
  __int64 v1; // rdx
  __int64 v2; // r8
  struct _RTL_DYNAMIC_HASH_TABLE *v3; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v4; // rbx
  PRTL_DYNAMIC_HASH_TABLE Enumerator[6]; // [rsp+30h] [rbp-30h] BYREF
  __int16 v6; // [rsp+80h] [rbp+20h] BYREF
  char v7; // [rsp+82h] [rbp+22h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+88h] [rbp+28h] BYREF

  v6 = 0;
  v7 = 0;
  memset(Enumerator, 0, sizeof(Enumerator));
  Entry = 0;
  if ( vpnAppTriggerModuleStarted )
  {
    v0 = 0;
    WfpAcquireFastWriteLock(&vpnTriggerLock, &v6);
    byte_140227475 = 1;
    _InterlockedDecrement(&dword_14022852C);
    if ( byte_140227474 )
      v0 = KeCancelTimer(&Timer) == 0;
    WfpReleaseFastWriteLock(&vpnTriggerLock, &v6);
    if ( v0 )
      KeFlushQueuedDpcs();
    if ( nrptTriggerContext )
    {
      LOBYTE(v1) = 1;
      WfpVpnUninitNrptTriggers(0, v1, v2);
    }
    WfpVpnCalloutUninit();
    if ( nrptEventSecurity )
    {
      WfpNrptSDFree();
      nrptEventSecurity = 0;
    }
    if ( _InterlockedDecrement(&workItemRef) != 1 )
      KeWaitForSingleObject(&shutDownEvent, Executive, 0, 0, 0);
    NetioShutdownWorkQueue(appTriggerWorkQueue);
    if ( bfeChangeHandle )
      FwpmBfeStateUnsubscribeChanges0(bfeChangeHandle);
    if ( bfeSessionHandle )
    {
      FwpmEngineClose0(bfeSessionHandle);
      bfeSessionHandle = 0;
    }
    NdisFreeRWLock(vpnTriggerLock);
    vpnTriggerLock = 0;
    WfpAcquireFastWriteLock(&filePathTableLock, &v6);
    v3 = filePathTable;
    if ( filePathTable )
    {
      RtlInitEnumerationHashTable(filePathTable, (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      Enumerator[0] = v3;
      while ( (unsigned int)WfpHashtableIteratorGetNext(Enumerator, &Entry) )
      {
        RtlRemoveEntryHashTable(filePathTable, Entry, 0);
        WfpFreeFilePathEntry(Entry);
      }
      RtlEndEnumerationHashTable(Enumerator[0], (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      WfpHashtableDestroy(filePathTable, 0);
      filePathTable = 0;
      numFilePathTableEntries = 0;
    }
    WfpReleaseFastWriteLock(&filePathTableLock, &v6);
    NdisFreeRWLock(filePathTableLock);
    filePathTableLock = 0;
    WfpAcquireFastWriteLock(&appSidTableLock, &v6);
    v4 = appSidTable;
    if ( appSidTable )
    {
      RtlInitEnumerationHashTable(appSidTable, (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      Enumerator[0] = v4;
      while ( (unsigned int)WfpHashtableIteratorGetNext(Enumerator, &Entry) )
      {
        RtlRemoveEntryHashTable(appSidTable, Entry, 0);
        WfpFreeAppSidEntry(Entry);
      }
      RtlEndEnumerationHashTable(Enumerator[0], (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      WfpHashtableDestroy(appSidTable, 0);
      appSidTable = 0;
      numAppSidTableEntries = 0;
    }
    WfpReleaseFastWriteLock(&appSidTableLock, &v6);
    NdisFreeRWLock(appSidTableLock);
    appSidTableLock = 0;
    WfpAcquireFastWriteLock(&Lock, &v6);
    WfpFreeSecurityDescriptorEntry(qword_1402274D0);
    qword_1402274D0 = 0;
    WfpReleaseFastWriteLock(&Lock, &v6);
    NdisFreeRWLock(Lock);
    Lock = 0;
    vpnAppTriggerModuleStarted = 0;
  }
}

```

## disassembly

```asm
0x1401774ec  mov     [rsp-18h+arg_10], rbx
0x1401774f1  push    rbp
0x1401774f2  push    rsi
0x1401774f3  push    rdi
0x1401774f4  mov     rbp, rsp
0x1401774f7  sub     rsp, 60h
0x1401774fb  xor     eax, eax
0x1401774fd  xorps   xmm0, xmm0
0x140177500  xor     edi, edi
0x140177502  mov     [rbp+arg_0], ax
0x140177506  cmp     cs:vpnAppTriggerModuleStarted, dil
0x14017750d  mov     [rbp+arg_2], al
0x140177510  movups  xmmword ptr [rbp+Enumerator], xmm0
0x140177514  mov     [rbp+Entry], rdi
0x140177518  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14017751c  movups  xmmword ptr [rbp+Enumerator+20h], xmm0
0x140177520  jz      loc_140177829
0x140177526  lea     rdx, [rbp+arg_0]
0x14017752a  movzx   ebx, dil
0x14017752e  lea     rcx, vpnTriggerLock
0x140177535  call    WfpAcquireFastWriteLock
0x14017753a  lea     esi, [rdi+1]
0x14017753d  mov     cs:byte_140227475, sil
0x140177544  lock dec cs:dword_14022852C
0x14017754b  cmp     cs:byte_140227474, dil
0x140177552  jz      short loc_14017756C
0x140177554  lea     rcx, Timer; PKTIMER
0x14017755b  call    cs:__imp_KeCancelTimer
0x140177562  nop     dword ptr [rax+rax+00h]
0x140177567  test    al, al
0x140177569  cmovz   ebx, esi
0x14017756c  lea     rdx, [rbp+arg_0]
0x140177570  lea     rcx, vpnTriggerLock
0x140177577  call    WfpReleaseFastWriteLock
0x14017757c  test    bl, bl
0x14017757e  jz      short loc_14017758C
0x140177580  call    cs:__imp_KeFlushQueuedDpcs
0x140177587  nop     dword ptr [rax+rax+00h]
0x14017758c  cmp     cs:nrptTriggerContext, rdi
0x140177593  jz      short loc_14017759F
0x140177595  mov     dl, sil
0x140177598  xor     ecx, ecx
0x14017759a  call    WfpVpnUninitNrptTriggers
0x14017759f  call    WfpVpnCalloutUninit
0x1401775a4  mov     rcx, cs:nrptEventSecurity
0x1401775ab  test    rcx, rcx
0x1401775ae  jz      short loc_1401775BC
0x1401775b0  call    WfpNrptSDFree
0x1401775b5  mov     cs:nrptEventSecurity, rdi
0x1401775bc  or      eax, 0FFFFFFFFh
0x1401775bf  lock xadd cs:workItemRef, eax
0x1401775c7  dec     eax
0x1401775c9  cmp     eax, esi
0x1401775cb  jz      short loc_1401775ED
0x1401775cd  xor     r9d, r9d; Alertable
0x1401775d0  mov     [rsp+60h+Timeout], rdi; Timeout
0x1401775d5  xor     r8d, r8d; WaitMode
0x1401775d8  lea     rcx, shutDownEvent; Object
0x1401775df  xor     edx, edx; WaitReason
0x1401775e1  call    cs:__imp_KeWaitForSingleObject
0x1401775e8  nop     dword ptr [rax+rax+00h]
0x1401775ed  lea     rcx, appTriggerWorkQueue
0x1401775f4  call    cs:__imp_NetioShutdownWorkQueue
0x1401775fb  nop     dword ptr [rax+rax+00h]
0x140177600  mov     rcx, cs:bfeChangeHandle; changeHandle
0x140177607  test    rcx, rcx
0x14017760a  jz      short loc_140177618
0x14017760c  call    cs:__imp_FwpmBfeStateUnsubscribeChanges0
0x140177613  nop     dword ptr [rax+rax+00h]
0x140177618  mov     rcx, cs:bfeSessionHandle; engineHandle
0x14017761f  test    rcx, rcx
0x140177622  jz      short loc_140177637
0x140177624  call    cs:__imp_FwpmEngineClose0
0x14017762b  nop     dword ptr [rax+rax+00h]
0x140177630  mov     cs:bfeSessionHandle, rdi
0x140177637  mov     rcx, cs:vpnTriggerLock; Lock
0x14017763e  call    cs:__imp_NdisFreeRWLock
0x140177645  nop     dword ptr [rax+rax+00h]
0x14017764a  lea     rdx, [rbp+arg_0]
0x14017764e  mov     cs:vpnTriggerLock, rdi
0x140177655  lea     rcx, filePathTableLock
0x14017765c  call    WfpAcquireFastWriteLock
0x140177661  mov     rbx, cs:filePathTable
0x140177668  test    rbx, rbx
0x14017766b  jz      short loc_1401776E9
0x14017766d  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140177671  mov     rcx, rbx; HashTable
0x140177674  call    cs:__imp_RtlInitEnumerationHashTable
0x14017767b  nop     dword ptr [rax+rax+00h]
0x140177680  mov     qword ptr [rbp+Enumerator], rbx
0x140177684  jmp     short loc_1401776A9
0x140177686  mov     rdx, [rbp+Entry]; Entry
0x14017768a  xor     r8d, r8d; Context
0x14017768d  mov     rcx, cs:filePathTable; HashTable
0x140177694  call    cs:__imp_RtlRemoveEntryHashTable
0x14017769b  nop     dword ptr [rax+rax+00h]
0x1401776a0  mov     rcx, [rbp+Entry]
0x1401776a4  call    WfpFreeFilePathEntry
0x1401776a9  lea     rdx, [rbp+Entry]
0x1401776ad  lea     rcx, [rbp+Enumerator]
0x1401776b1  call    WfpHashtableIteratorGetNext
0x1401776b6  test    eax, eax
0x1401776b8  jnz     short loc_140177686
0x1401776ba  mov     rcx, qword ptr [rbp+Enumerator]; HashTable
0x1401776be  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x1401776c2  call    cs:__imp_RtlEndEnumerationHashTable
0x1401776c9  nop     dword ptr [rax+rax+00h]
0x1401776ce  mov     rcx, cs:filePathTable; HashTable
0x1401776d5  xor     edx, edx
0x1401776d7  call    WfpHashtableDestroy
0x1401776dc  mov     cs:filePathTable, rdi
0x1401776e3  mov     cs:numFilePathTableEntries, edi
0x1401776e9  lea     rdx, [rbp+arg_0]
0x1401776ed  lea     rcx, filePathTableLock
0x1401776f4  call    WfpReleaseFastWriteLock
0x1401776f9  mov     rcx, cs:filePathTableLock; Lock
0x140177700  call    cs:__imp_NdisFreeRWLock
0x140177707  nop     dword ptr [rax+rax+00h]
0x14017770c  lea     rdx, [rbp+arg_0]
0x140177710  mov     cs:filePathTableLock, rdi
0x140177717  lea     rcx, appSidTableLock
0x14017771e  call    WfpAcquireFastWriteLock
0x140177723  mov     rbx, cs:appSidTable
0x14017772a  test    rbx, rbx
0x14017772d  jz      short loc_1401777AB
0x14017772f  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140177733  mov     rcx, rbx; HashTable
0x140177736  call    cs:__imp_RtlInitEnumerationHashTable
0x14017773d  nop     dword ptr [rax+rax+00h]
0x140177742  mov     qword ptr [rbp+Enumerator], rbx
0x140177746  jmp     short loc_14017776B
0x140177748  mov     rdx, [rbp+Entry]; Entry
0x14017774c  xor     r8d, r8d; Context
0x14017774f  mov     rcx, cs:appSidTable; HashTable
0x140177756  call    cs:__imp_RtlRemoveEntryHashTable
0x14017775d  nop     dword ptr [rax+rax+00h]
0x140177762  mov     rcx, [rbp+Entry]
0x140177766  call    WfpFreeAppSidEntry
0x14017776b  lea     rdx, [rbp+Entry]
0x14017776f  lea     rcx, [rbp+Enumerator]
0x140177773  call    WfpHashtableIteratorGetNext
0x140177778  test    eax, eax
0x14017777a  jnz     short loc_140177748
0x14017777c  mov     rcx, qword ptr [rbp+Enumerator]; HashTable
0x140177780  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140177784  call    cs:__imp_RtlEndEnumerationHashTable
0x14017778b  nop     dword ptr [rax+rax+00h]
0x140177790  mov     rcx, cs:appSidTable; HashTable
0x140177797  xor     edx, edx
0x140177799  call    WfpHashtableDestroy
0x14017779e  mov     cs:appSidTable, rdi
0x1401777a5  mov     cs:numAppSidTableEntries, edi
0x1401777ab  lea     rdx, [rbp+arg_0]
0x1401777af  lea     rcx, appSidTableLock
0x1401777b6  call    WfpReleaseFastWriteLock
0x1401777bb  mov     rcx, cs:appSidTableLock; Lock
0x1401777c2  call    cs:__imp_NdisFreeRWLock
0x1401777c9  nop     dword ptr [rax+rax+00h]
0x1401777ce  lea     rdx, [rbp+arg_0]
0x1401777d2  mov     cs:appSidTableLock, rdi
0x1401777d9  lea     rcx, Lock
0x1401777e0  call    WfpAcquireFastWriteLock
0x1401777e5  mov     rcx, cs:qword_1402274D0
0x1401777ec  call    WfpFreeSecurityDescriptorEntry
0x1401777f1  lea     rdx, [rbp+arg_0]
0x1401777f5  mov     cs:qword_1402274D0, rdi
0x1401777fc  lea     rcx, Lock
0x140177803  call    WfpReleaseFastWriteLock
0x140177808  mov     rcx, cs:Lock; Lock
0x14017780f  call    cs:__imp_NdisFreeRWLock
0x140177816  nop     dword ptr [rax+rax+00h]
0x14017781b  mov     cs:Lock, rdi
0x140177822  mov     cs:vpnAppTriggerModuleStarted, dil
0x140177829  mov     rbx, [rsp+60h+arg_10]
0x140177831  add     rsp, 60h
0x140177835  pop     rdi
0x140177836  pop     rsi
0x140177837  pop     rbp
0x140177838  retn
```
