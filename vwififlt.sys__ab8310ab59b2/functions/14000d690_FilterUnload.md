# FilterUnload

- ea: `0x14000d690`
- end: `0x14000d8ae`
- name: `FilterUnload`
- size: `542`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x140003fe8`
- `0x14000443c`
- `0x1400057f8`
- `0x140006960`
- `0x14000cd98`
- `0x14000d690`
- `0x14000d8b4`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000e0b4`
- `0x14000f500`
- `0x140017008`

## import_xrefs

- `ntoskrnl!IoUnregisterPlugPlayNotificationEx` at `0x14000d6d8`
- `ntoskrnl!IoUnregisterPlugPlayNotificationEx` at `0x14000d6d8`
- `ntoskrnl!ZwClose` at `0x14000d882`
- `ntoskrnl!ZwClose` at `0x14000d882`
- `NDIS!NdisFreeMemory` at `0x14000d7eb`
- `NDIS!NdisFreeMemory` at `0x14000d7ff`
- `NDIS!NdisFreeMemory` at `0x14000d7eb`
- `NDIS!NdisFreeMemory` at `0x14000d7ff`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14000d6fb`
- `NDIS!NdisFDeregisterFilterDriver` at `0x14000d6fb`

## string_xrefs

- `0x14000d724`: `IsListEmpty(&FilterModuleList)`

## pseudocode

```c
NTSTATUS FilterUnload()
{
  struct _DEVICE_OBJECT *Next; // rbx
  struct _DEVICE_OBJECT *v1; // rdi
  struct _DEVICE_OBJECT *v2; // rbp
  __int64 i; // rsi
  __int64 v4; // rax
  PKDEFERRED_ROUTINE *v5; // rcx
  PVOID *DeferredRoutine; // rbx
  NTSTATUS result; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  if ( PnPNotificationHandle )
  {
    IoUnregisterPlugPlayNotificationEx(PnPNotificationHandle);
    PnPNotificationHandle = 0;
  }
  FilterDeregisterDevice();
  NdisFDeregisterFilterDriver(WPP_MAIN_CB.DeviceExtension);
  if ( (BOOLEAN *)WPP_MAIN_CB.DeviceQueue.32 != &WPP_MAIN_CB.DeviceQueue.Busy )
    TraceAssert("IsListEmpty(&FilterModuleList)", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1252);
  g_fModuleInitialized = 0;
  FilterWaitForVariable(&g_lThreadCount);
  Next = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Dpc.DpcListEntry.Next;
  while ( Next != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Dpc.DpcListEntry )
  {
    v1 = Next;
    v2 = Next;
    if ( Next->Queue.Wcb.NumberOfMapRegisters != 6 )
      TraceAssert("pFilter->State == FilterDetaching", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1288);
    Next = *(struct _DEVICE_OBJECT **)&Next->Type;
    FilterAddRef(v1);
    for ( i = 0; (unsigned int)i < *((_DWORD *)&v1[7].Reserved + 3); i = (unsigned int)(i + 1) )
      FilterRemoveMpLink(*(_QWORD *)&v2[9].Queue.Wcb.NumberOfChannels + 144 * i);
    FilterDeRef(v1);
  }
  while ( 1 )
  {
    DeferredRoutine = (PVOID *)WPP_MAIN_CB.Dpc.DeferredRoutine;
    if ( (PKDEFERRED_ROUTINE *)WPP_MAIN_CB.Dpc.DeferredRoutine == &WPP_MAIN_CB.Dpc.DeferredRoutine )
      break;
    v4 = *(_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine;
    if ( *(PKDEFERRED_ROUTINE *)(*(_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 8LL) != WPP_MAIN_CB.Dpc.DeferredRoutine
      || (v5 = (PKDEFERRED_ROUTINE *)*((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 1),
          *v5 != WPP_MAIN_CB.Dpc.DeferredRoutine) )
    {
      __fastfail(3u);
    }
    *v5 = (PKDEFERRED_ROUTINE)v4;
    *(_QWORD *)(v4 + 8) = v5;
    NdisFreeMemory(DeferredRoutine[4], 0, 0);
    NdisFreeMemory(DeferredRoutine, 0, 0);
  }
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x60u);
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = 1319;
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = "FilterUnload";
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  WppCleanupKm();
  result = McGenEventUnregister_EtwUnregister();
  if ( Handle )
  {
    result = ZwClose(Handle);
    Handle = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000d690  push    rbx
0x14000d692  push    rbp
0x14000d693  push    rsi
0x14000d694  push    rdi
0x14000d695  push    r12
0x14000d697  push    r15
0x14000d699  sub     rsp, 28h
0x14000d69d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d6a4  lea     r12, WPP_GLOBAL_Control
0x14000d6ab  cmp     rcx, r12
0x14000d6ae  jz      short loc_14000D6CC
0x14000d6b0  mov     eax, [rcx+2Ch]
0x14000d6b3  test    al, 20h
0x14000d6b5  jz      short loc_14000D6CC
0x14000d6b7  mov     rcx, [rcx+18h]
0x14000d6bb  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000d6c2  mov     edx, 58h ; 'X'
0x14000d6c7  call    WPP_SF_
0x14000d6cc  mov     rcx, cs:PnPNotificationHandle; NotificationEntry
0x14000d6d3  test    rcx, rcx
0x14000d6d6  jz      short loc_14000D6EF
0x14000d6d8  call    cs:__imp_IoUnregisterPlugPlayNotificationEx
0x14000d6df  nop     dword ptr [rax+rax+00h]
0x14000d6e4  mov     cs:PnPNotificationHandle, 0
0x14000d6ef  call    FilterDeregisterDevice
0x14000d6f4  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; NdisFilterDriverHandle
0x14000d6fb  call    cs:__imp_NdisFDeregisterFilterDriver
0x14000d702  nop     dword ptr [rax+rax+00h]
0x14000d707  lea     rax, WPP_MAIN_CB.DeviceQueue.20h
0x14000d70e  cmp     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, rax
0x14000d715  jz      short loc_14000D730
0x14000d717  mov     r8d, 4E4h
0x14000d71d  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000d724  lea     rcx, aIslistemptyFil; "IsListEmpty(&FilterModuleList)"
0x14000d72b  call    TraceAssert
0x14000d730  lea     rcx, g_lThreadCount
0x14000d737  mov     cs:g_fModuleInitialized, 0
0x14000d73e  call    FilterWaitForVariable
0x14000d743  mov     rbx, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x14000d74a  lea     r15, WPP_MAIN_CB.Dpc.DpcListEntry
0x14000d751  jmp     short loc_14000D7B3
0x14000d753  cmp     dword ptr [rbx+78h], 6
0x14000d757  mov     rdi, rbx
0x14000d75a  mov     rbp, rbx
0x14000d75d  jz      short loc_14000D778
0x14000d75f  mov     r8d, 508h
0x14000d765  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000d76c  lea     rcx, aPfilterStateFi_0; "pFilter->State == FilterDetaching"
0x14000d773  call    TraceAssert
0x14000d778  mov     rbx, [rbx]
0x14000d77b  mov     rcx, rdi
0x14000d77e  call    FilterAddRef
0x14000d783  xor     esi, esi
0x14000d785  cmp     [rdi+0A7Ch], esi
0x14000d78b  jbe     short loc_14000D7AB
0x14000d78d  lea     rcx, [rsi+rsi*8]
0x14000d791  shl     rcx, 4
0x14000d795  add     rcx, [rbp+0C30h]
0x14000d79c  call    FilterRemoveMpLink
0x14000d7a1  inc     esi
0x14000d7a3  cmp     esi, [rdi+0A7Ch]
0x14000d7a9  jb      short loc_14000D78D
0x14000d7ab  mov     rcx, rdi; VirtualAddress
0x14000d7ae  call    FilterDeRef
0x14000d7b3  cmp     rbx, r15
0x14000d7b6  jnz     short loc_14000D753
0x14000d7b8  lea     rdi, WPP_MAIN_CB.Dpc.DeferredRoutine
0x14000d7bf  jmp     short loc_14000D80B
0x14000d7c1  mov     rax, [rbx]
0x14000d7c4  cmp     [rax+8], rbx
0x14000d7c8  jnz     loc_14000D8A7
0x14000d7ce  mov     rcx, [rbx+8]
0x14000d7d2  cmp     [rcx], rbx
0x14000d7d5  jnz     loc_14000D8A7
0x14000d7db  mov     [rcx], rax
0x14000d7de  xor     r8d, r8d; MemoryFlags
0x14000d7e1  mov     [rax+8], rcx
0x14000d7e5  xor     edx, edx; Length
0x14000d7e7  mov     rcx, [rbx+20h]; VirtualAddress
0x14000d7eb  call    cs:__imp_NdisFreeMemory
0x14000d7f2  nop     dword ptr [rax+rax+00h]
0x14000d7f7  xor     r8d, r8d; MemoryFlags
0x14000d7fa  xor     edx, edx; Length
0x14000d7fc  mov     rcx, rbx; VirtualAddress
0x14000d7ff  call    cs:__imp_NdisFreeMemory
0x14000d806  nop     dword ptr [rax+rax+00h]
0x14000d80b  mov     rbx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14000d812  cmp     rbx, rdi
0x14000d815  jnz     short loc_14000D7C1
0x14000d817  xor     edx, edx; Val
0x14000d819  lea     rcx, WPP_MAIN_CB.Queue+10h; void *
0x14000d820  lea     r8d, [rdx+60h]; Size
0x14000d824  call    memset
0x14000d829  lea     rax, aFilterunload; "FilterUnload"
0x14000d830  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, 527h
0x14000d83a  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, rax
0x14000d841  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d848  cmp     rcx, r12
0x14000d84b  jz      short loc_14000D86C
0x14000d84d  mov     eax, [rcx+2Ch]
0x14000d850  test    al, 20h
0x14000d852  jz      short loc_14000D86C
0x14000d854  mov     rcx, [rcx+18h]
0x14000d858  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000d85f  mov     edx, 59h ; 'Y'
0x14000d864  xor     r9d, r9d
0x14000d867  call    WPP_SF_d
0x14000d86c  call    WppCleanupKm
0x14000d871  call    McGenEventUnregister_EtwUnregister
0x14000d876  mov     rcx, cs:Handle; Handle
0x14000d87d  test    rcx, rcx
0x14000d880  jz      short loc_14000D899
0x14000d882  call    cs:__imp_ZwClose
0x14000d889  nop     dword ptr [rax+rax+00h]
0x14000d88e  mov     cs:Handle, 0
0x14000d899  add     rsp, 28h
0x14000d89d  pop     r15
0x14000d89f  pop     r12
0x14000d8a1  pop     rdi
0x14000d8a2  pop     rsi
0x14000d8a3  pop     rbp
0x14000d8a4  pop     rbx
0x14000d8a5  retn
0x14000d8a7  mov     ecx, 3
0x14000d8ac  int     29h; Win8: RtlFailFast(ecx)
```
