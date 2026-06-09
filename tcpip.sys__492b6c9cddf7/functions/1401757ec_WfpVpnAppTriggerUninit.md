# WfpVpnAppTriggerUninit

- ea: `0x1401757ec`
- end: `0x140175b3a`
- name: `WfpVpnAppTriggerUninit`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14016ec74`
- `0x14016f254`

## callees

- `0x1400569e0`
- `0x140056a50`
- `0x1400eef40`
- `0x140119ea8`
- `0x140174a10`
- `0x140174a4c`
- `0x140174a88`
- `0x140174cd4`
- `0x1401757ec`
- `0x140175f24`
- `0x140176e54`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x140175880`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140175880`
- `ntoskrnl!KeCancelTimer` at `0x14017585b`
- `ntoskrnl!KeCancelTimer` at `0x14017585b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401759c2`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140175a84`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401759c2`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140175a84`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175974`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175a36`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175974`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175a36`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175994`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175a56`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175994`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175a56`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401758e1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401758e1`
- `NETIO!NetioShutdownWorkQueue` at `0x1401758f4`
- `NETIO!NetioShutdownWorkQueue` at `0x1401758f4`
- `NDIS!NdisFreeRWLock` at `0x14017593e`
- `NDIS!NdisFreeRWLock` at `0x140175a00`
- `NDIS!NdisFreeRWLock` at `0x140175ac2`
- `NDIS!NdisFreeRWLock` at `0x140175b0f`
- `NDIS!NdisFreeRWLock` at `0x14017593e`
- `NDIS!NdisFreeRWLock` at `0x140175a00`
- `NDIS!NdisFreeRWLock` at `0x140175ac2`
- `NDIS!NdisFreeRWLock` at `0x140175b0f`
- `fwpkclnt!FwpmEngineClose0` at `0x140175924`
- `fwpkclnt!FwpmEngineClose0` at `0x140175924`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x14017590c`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x14017590c`

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
    byte_140223454 = 1;
    _InterlockedDecrement(&dword_1402244EC);
    if ( byte_140223455 )
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
    WfpFreeSecurityDescriptorEntry(qword_140223498);
    qword_140223498 = 0;
    WfpReleaseFastWriteLock(&Lock, &v6);
    NdisFreeRWLock(Lock);
    Lock = 0;
    vpnAppTriggerModuleStarted = 0;
  }
}

```

## disassembly

```asm
0x1401757ec  mov     [rsp-18h+arg_10], rbx
0x1401757f1  push    rbp
0x1401757f2  push    rsi
0x1401757f3  push    rdi
0x1401757f4  mov     rbp, rsp
0x1401757f7  sub     rsp, 60h
0x1401757fb  xor     eax, eax
0x1401757fd  xorps   xmm0, xmm0
0x140175800  xor     edi, edi
0x140175802  mov     [rbp+arg_0], ax
0x140175806  cmp     cs:vpnAppTriggerModuleStarted, dil
0x14017580d  mov     [rbp+arg_2], al
0x140175810  movups  xmmword ptr [rbp+Enumerator], xmm0
0x140175814  mov     [rbp+Entry], rdi
0x140175818  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14017581c  movups  xmmword ptr [rbp+Enumerator+20h], xmm0
0x140175820  jz      loc_140175B29
0x140175826  lea     rdx, [rbp+arg_0]
0x14017582a  movzx   ebx, dil
0x14017582e  lea     rcx, vpnTriggerLock
0x140175835  call    WfpAcquireFastWriteLock
0x14017583a  lea     esi, [rdi+1]
0x14017583d  mov     cs:byte_140223454, sil
0x140175844  lock dec cs:dword_1402244EC
0x14017584b  cmp     cs:byte_140223455, dil
0x140175852  jz      short loc_14017586C
0x140175854  lea     rcx, Timer; PKTIMER
0x14017585b  call    cs:__imp_KeCancelTimer
0x140175862  nop     dword ptr [rax+rax+00h]
0x140175867  test    al, al
0x140175869  cmovz   ebx, esi
0x14017586c  lea     rdx, [rbp+arg_0]
0x140175870  lea     rcx, vpnTriggerLock
0x140175877  call    WfpReleaseFastWriteLock
0x14017587c  test    bl, bl
0x14017587e  jz      short loc_14017588C
0x140175880  call    cs:__imp_KeFlushQueuedDpcs
0x140175887  nop     dword ptr [rax+rax+00h]
0x14017588c  cmp     cs:nrptTriggerContext, rdi
0x140175893  jz      short loc_14017589F
0x140175895  mov     dl, sil
0x140175898  xor     ecx, ecx
0x14017589a  call    WfpVpnUninitNrptTriggers
0x14017589f  call    WfpVpnCalloutUninit
0x1401758a4  mov     rcx, cs:nrptEventSecurity
0x1401758ab  test    rcx, rcx
0x1401758ae  jz      short loc_1401758BC
0x1401758b0  call    WfpNrptSDFree
0x1401758b5  mov     cs:nrptEventSecurity, rdi
0x1401758bc  or      eax, 0FFFFFFFFh
0x1401758bf  lock xadd cs:workItemRef, eax
0x1401758c7  dec     eax
0x1401758c9  cmp     eax, esi
0x1401758cb  jz      short loc_1401758ED
0x1401758cd  xor     r9d, r9d; Alertable
0x1401758d0  mov     [rsp+60h+Timeout], rdi; Timeout
0x1401758d5  xor     r8d, r8d; WaitMode
0x1401758d8  lea     rcx, shutDownEvent; Object
0x1401758df  xor     edx, edx; WaitReason
0x1401758e1  call    cs:__imp_KeWaitForSingleObject
0x1401758e8  nop     dword ptr [rax+rax+00h]
0x1401758ed  lea     rcx, appTriggerWorkQueue
0x1401758f4  call    cs:__imp_NetioShutdownWorkQueue
0x1401758fb  nop     dword ptr [rax+rax+00h]
0x140175900  mov     rcx, cs:bfeChangeHandle; changeHandle
0x140175907  test    rcx, rcx
0x14017590a  jz      short loc_140175918
0x14017590c  call    cs:__imp_FwpmBfeStateUnsubscribeChanges0
0x140175913  nop     dword ptr [rax+rax+00h]
0x140175918  mov     rcx, cs:bfeSessionHandle; engineHandle
0x14017591f  test    rcx, rcx
0x140175922  jz      short loc_140175937
0x140175924  call    cs:__imp_FwpmEngineClose0
0x14017592b  nop     dword ptr [rax+rax+00h]
0x140175930  mov     cs:bfeSessionHandle, rdi
0x140175937  mov     rcx, cs:vpnTriggerLock; Lock
0x14017593e  call    cs:__imp_NdisFreeRWLock
0x140175945  nop     dword ptr [rax+rax+00h]
0x14017594a  lea     rdx, [rbp+arg_0]
0x14017594e  mov     cs:vpnTriggerLock, rdi
0x140175955  lea     rcx, filePathTableLock
0x14017595c  call    WfpAcquireFastWriteLock
0x140175961  mov     rbx, cs:filePathTable
0x140175968  test    rbx, rbx
0x14017596b  jz      short loc_1401759E9
0x14017596d  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175971  mov     rcx, rbx; HashTable
0x140175974  call    cs:__imp_RtlInitEnumerationHashTable
0x14017597b  nop     dword ptr [rax+rax+00h]
0x140175980  mov     qword ptr [rbp+Enumerator], rbx
0x140175984  jmp     short loc_1401759A9
0x140175986  mov     rdx, [rbp+Entry]; Entry
0x14017598a  xor     r8d, r8d; Context
0x14017598d  mov     rcx, cs:filePathTable; HashTable
0x140175994  call    cs:__imp_RtlRemoveEntryHashTable
0x14017599b  nop     dword ptr [rax+rax+00h]
0x1401759a0  mov     rcx, [rbp+Entry]
0x1401759a4  call    WfpFreeFilePathEntry
0x1401759a9  lea     rdx, [rbp+Entry]
0x1401759ad  lea     rcx, [rbp+Enumerator]
0x1401759b1  call    WfpHashtableIteratorGetNext
0x1401759b6  test    eax, eax
0x1401759b8  jnz     short loc_140175986
0x1401759ba  mov     rcx, qword ptr [rbp+Enumerator]; HashTable
0x1401759be  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x1401759c2  call    cs:__imp_RtlEndEnumerationHashTable
0x1401759c9  nop     dword ptr [rax+rax+00h]
0x1401759ce  mov     rcx, cs:filePathTable; HashTable
0x1401759d5  xor     edx, edx
0x1401759d7  call    WfpHashtableDestroy
0x1401759dc  mov     cs:filePathTable, rdi
0x1401759e3  mov     cs:numFilePathTableEntries, edi
0x1401759e9  lea     rdx, [rbp+arg_0]
0x1401759ed  lea     rcx, filePathTableLock
0x1401759f4  call    WfpReleaseFastWriteLock
0x1401759f9  mov     rcx, cs:filePathTableLock; Lock
0x140175a00  call    cs:__imp_NdisFreeRWLock
0x140175a07  nop     dword ptr [rax+rax+00h]
0x140175a0c  lea     rdx, [rbp+arg_0]
0x140175a10  mov     cs:filePathTableLock, rdi
0x140175a17  lea     rcx, appSidTableLock
0x140175a1e  call    WfpAcquireFastWriteLock
0x140175a23  mov     rbx, cs:appSidTable
0x140175a2a  test    rbx, rbx
0x140175a2d  jz      short loc_140175AAB
0x140175a2f  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175a33  mov     rcx, rbx; HashTable
0x140175a36  call    cs:__imp_RtlInitEnumerationHashTable
0x140175a3d  nop     dword ptr [rax+rax+00h]
0x140175a42  mov     qword ptr [rbp+Enumerator], rbx
0x140175a46  jmp     short loc_140175A6B
0x140175a48  mov     rdx, [rbp+Entry]; Entry
0x140175a4c  xor     r8d, r8d; Context
0x140175a4f  mov     rcx, cs:appSidTable; HashTable
0x140175a56  call    cs:__imp_RtlRemoveEntryHashTable
0x140175a5d  nop     dword ptr [rax+rax+00h]
0x140175a62  mov     rcx, [rbp+Entry]
0x140175a66  call    WfpFreeAppSidEntry
0x140175a6b  lea     rdx, [rbp+Entry]
0x140175a6f  lea     rcx, [rbp+Enumerator]
0x140175a73  call    WfpHashtableIteratorGetNext
0x140175a78  test    eax, eax
0x140175a7a  jnz     short loc_140175A48
0x140175a7c  mov     rcx, qword ptr [rbp+Enumerator]; HashTable
0x140175a80  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175a84  call    cs:__imp_RtlEndEnumerationHashTable
0x140175a8b  nop     dword ptr [rax+rax+00h]
0x140175a90  mov     rcx, cs:appSidTable; HashTable
0x140175a97  xor     edx, edx
0x140175a99  call    WfpHashtableDestroy
0x140175a9e  mov     cs:appSidTable, rdi
0x140175aa5  mov     cs:numAppSidTableEntries, edi
0x140175aab  lea     rdx, [rbp+arg_0]
0x140175aaf  lea     rcx, appSidTableLock
0x140175ab6  call    WfpReleaseFastWriteLock
0x140175abb  mov     rcx, cs:appSidTableLock; Lock
0x140175ac2  call    cs:__imp_NdisFreeRWLock
0x140175ac9  nop     dword ptr [rax+rax+00h]
0x140175ace  lea     rdx, [rbp+arg_0]
0x140175ad2  mov     cs:appSidTableLock, rdi
0x140175ad9  lea     rcx, Lock
0x140175ae0  call    WfpAcquireFastWriteLock
0x140175ae5  mov     rcx, cs:qword_140223498
0x140175aec  call    WfpFreeSecurityDescriptorEntry
0x140175af1  lea     rdx, [rbp+arg_0]
0x140175af5  mov     cs:qword_140223498, rdi
0x140175afc  lea     rcx, Lock
0x140175b03  call    WfpReleaseFastWriteLock
0x140175b08  mov     rcx, cs:Lock; Lock
0x140175b0f  call    cs:__imp_NdisFreeRWLock
0x140175b16  nop     dword ptr [rax+rax+00h]
0x140175b1b  mov     cs:Lock, rdi
0x140175b22  mov     cs:vpnAppTriggerModuleStarted, dil
0x140175b29  mov     rbx, [rsp+60h+arg_10]
0x140175b31  add     rsp, 60h
0x140175b35  pop     rdi
0x140175b36  pop     rsi
0x140175b37  pop     rbp
0x140175b38  retn
```
