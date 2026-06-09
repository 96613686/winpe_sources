# DllUnload

- ea: `0x1400cef20`
- end: `0x1400cf017`
- name: `DllUnload`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140099e0c`
- `0x14009b1b0`
- `0x14009b22c`
- `0x14009c44c`
- `0x14009d244`
- `0x1400cef20`
- `0x1400e6714`
- `0x140134d00`
- `0x1401900c4`
- `0x140191430`
- `0x140197894`
- `0x140198a7c`
- `0x14019e928`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef49`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef61`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef79`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef91`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef49`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef61`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef79`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400cef91`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cefba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cefba`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x1400cefec`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x1400cefec`

## pseudocode

```c
__int64 DllUnload()
{
  if ( _InterlockedExchangeAdd(&NumDllInitialize, 0xFFFFFFFF) == 1 )
  {
    StorpUnregisterShim();
    RaidFreeEnclosureIdMappings();
    ExDeleteResourceLite(&EnclosureIdListLock);
    RaidFreeATADeviceIdMappings();
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceExtension);
    FreeNvmeIceList();
    ExDeleteResourceLite(&NvmeIceListLock);
    FreeNvmeAuthKeyTable();
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceQueue.32);
    if ( RegWatchContext )
    {
      StorpShutdownRegistryWatch();
      ExFreePoolWithTag(RegWatchContext, 0x57526152u);
      RegWatchContext = 0;
    }
    StorpWheaRemoveErrorSource();
    if ( _InterlockedCompareExchange(&PagingDeviceDumpCallbackRegistered, 0, 1) == 1 )
      KeDeregisterBugCheckReasonCallback(&StorPagingDeviceSecondaryCallbackRecord);
    UnloadExtensionDriver();
    StorKsrUninitialize();
    FreeCpuInformation();
    wil_UninitializeFeatureStaging();
  }
  return RaidSecondaryDumpDeregister();
}

```

## disassembly

```asm
0x1400cef20  sub     rsp, 28h
0x1400cef24  or      eax, 0FFFFFFFFh
0x1400cef27  lock xadd cs:NumDllInitialize, eax
0x1400cef2f  cmp     eax, 1
0x1400cef32  jnz     loc_1400CF00C
0x1400cef38  call    StorpUnregisterShim
0x1400cef3d  call    RaidFreeEnclosureIdMappings
0x1400cef42  lea     rcx, EnclosureIdListLock; Resource
0x1400cef49  call    cs:__imp_ExDeleteResourceLite
0x1400cef50  nop     dword ptr [rax+rax+00h]
0x1400cef55  call    RaidFreeATADeviceIdMappings
0x1400cef5a  lea     rcx, WPP_MAIN_CB.DeviceExtension; Resource
0x1400cef61  call    cs:__imp_ExDeleteResourceLite
0x1400cef68  nop     dword ptr [rax+rax+00h]
0x1400cef6d  call    FreeNvmeIceList
0x1400cef72  lea     rcx, NvmeIceListLock; Resource
0x1400cef79  call    cs:__imp_ExDeleteResourceLite
0x1400cef80  nop     dword ptr [rax+rax+00h]
0x1400cef85  call    FreeNvmeAuthKeyTable
0x1400cef8a  lea     rcx, WPP_MAIN_CB.DeviceQueue.___u4; Resource
0x1400cef91  call    cs:__imp_ExDeleteResourceLite
0x1400cef98  nop     dword ptr [rax+rax+00h]
0x1400cef9d  mov     rcx, cs:RegWatchContext
0x1400cefa4  test    rcx, rcx
0x1400cefa7  jz      short loc_1400CEFD1
0x1400cefa9  call    StorpShutdownRegistryWatch
0x1400cefae  mov     rcx, cs:RegWatchContext; P
0x1400cefb5  mov     edx, 57526152h; Tag
0x1400cefba  call    cs:__imp_ExFreePoolWithTag
0x1400cefc1  nop     dword ptr [rax+rax+00h]
0x1400cefc6  mov     cs:RegWatchContext, 0
0x1400cefd1  call    StorpWheaRemoveErrorSource
0x1400cefd6  xor     ecx, ecx
0x1400cefd8  lea     eax, [rcx+1]
0x1400cefdb  lock cmpxchg cs:PagingDeviceDumpCallbackRegistered, ecx
0x1400cefe3  jnz     short loc_1400CEFF8
0x1400cefe5  lea     rcx, StorPagingDeviceSecondaryCallbackRecord; CallbackRecord
0x1400cefec  call    cs:__imp_KeDeregisterBugCheckReasonCallback
0x1400ceff3  nop     dword ptr [rax+rax+00h]
0x1400ceff8  call    UnloadExtensionDriver
0x1400ceffd  call    StorKsrUninitialize
0x1400cf002  call    FreeCpuInformation
0x1400cf007  call    wil_UninitializeFeatureStaging
0x1400cf00c  call    RaidSecondaryDumpDeregister
0x1400cf011  add     rsp, 28h
0x1400cf015  retn
```
