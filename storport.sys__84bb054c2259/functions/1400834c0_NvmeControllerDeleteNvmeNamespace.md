# NvmeControllerDeleteNvmeNamespace

- ea: `0x1400834c0`
- end: `0x14008363f`
- name: `NvmeControllerDeleteNvmeNamespace`
- size: `383`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140082ca0`
- `0x1400f7af8`
- `0x140105da4`
- `0x14010a0dc`

## callees

- `0x140066d94`
- `0x1400834c0`
- `0x14011dbe0`
- `0x14011dc48`
- `0x14012a524`
- `0x14012b204`
- `0x14012b2e8`
- `0x14013d568`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140083625`
- `ntoskrnl!IoDeleteDevice` at `0x140083625`
- `ntoskrnl!IoFreeWorkItem` at `0x140083585`
- `ntoskrnl!IoFreeWorkItem` at `0x140083585`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083522`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400835b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400835e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083522`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400835b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400835e1`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140083607`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140083607`

## pseudocode

```c
void __fastcall NvmeControllerDeleteNvmeNamespace(_QWORD *a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  struct _IO_WORKITEM *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v7; // rcx

  NvmeNamespaceTerminateSystemThread(*a1);
  NvmeNamespaceDeleteIoQueue(*a1);
  NvmeNamespaceDeleteErrorRecoveryContext(*a1);
  NvmeNamespaceTelemetryDelete(*a1);
  v2 = *(_QWORD *)(*(_QWORD *)(*a1 + 16LL) + 128LL);
  if ( v2 && *a1 == *(_QWORD *)(v2 + 104) )
    *(_QWORD *)(v2 + 104) = 0;
  v3 = *(void **)(*(_QWORD *)(*a1 + 128LL) + 16LL);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x57506152u);
    *(_QWORD *)(*(_QWORD *)(*a1 + 128LL) + 16LL) = 0;
  }
  NvmeNamespaceUninitializeIoTracking(*a1);
  NvmeNamespacePowerUninitialize(*a1);
  if ( *(_QWORD *)(*a1 + 544LL) )
  {
    NvmeControllerFreeExtendedCommand(*(_QWORD *)(*a1 + 16LL));
    *(_QWORD *)(*a1 + 544LL) = 0;
  }
  v4 = *(struct _IO_WORKITEM **)(*a1 + 552LL);
  if ( v4 )
  {
    IoFreeWorkItem(v4);
    *(_QWORD *)(*a1 + 552LL) = 0;
  }
  v5 = *(void **)(*a1 + 184LL);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x52436152u);
    *(_QWORD *)(*a1 + 184LL) = 0;
  }
  v6 = *(void **)(*a1 + 176LL);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0x52436152u);
    *(_QWORD *)(*a1 + 176LL) = 0;
  }
  v7 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(*a1 + 120LL);
  if ( v7 )
  {
    ExFreeCacheAwareRundownProtection(v7);
    *(_QWORD *)(*a1 + 120LL) = 0;
  }
  IoDeleteDevice(*(PDEVICE_OBJECT *)(*a1 + 8LL));
  *a1 = 0;
}

```

## disassembly

```asm
0x1400834c0  push    rbx
0x1400834c2  sub     rsp, 20h
0x1400834c6  mov     rbx, rcx
0x1400834c9  mov     rcx, [rcx]
0x1400834cc  call    NvmeNamespaceTerminateSystemThread
0x1400834d1  mov     rcx, [rbx]
0x1400834d4  call    NvmeNamespaceDeleteIoQueue
0x1400834d9  mov     rcx, [rbx]
0x1400834dc  call    NvmeNamespaceDeleteErrorRecoveryContext
0x1400834e1  mov     rcx, [rbx]
0x1400834e4  call    NvmeNamespaceTelemetryDelete
0x1400834e9  mov     rdx, [rbx]
0x1400834ec  mov     rax, [rdx+10h]
0x1400834f0  mov     rcx, [rax+80h]
0x1400834f7  test    rcx, rcx
0x1400834fa  jz      short loc_14008350A
0x1400834fc  cmp     rdx, [rcx+68h]
0x140083500  jnz     short loc_14008350A
0x140083502  mov     qword ptr [rcx+68h], 0
0x14008350a  mov     rax, [rbx]
0x14008350d  mov     rcx, [rax+80h]
0x140083514  mov     rcx, [rcx+10h]; P
0x140083518  test    rcx, rcx
0x14008351b  jz      short loc_140083540
0x14008351d  mov     edx, 57506152h; Tag
0x140083522  call    cs:__imp_ExFreePoolWithTag
0x140083529  nop     dword ptr [rax+rax+00h]
0x14008352e  mov     rax, [rbx]
0x140083531  mov     rcx, [rax+80h]
0x140083538  mov     qword ptr [rcx+10h], 0
0x140083540  mov     rcx, [rbx]
0x140083543  call    NvmeNamespaceUninitializeIoTracking
0x140083548  mov     rcx, [rbx]
0x14008354b  call    NvmeNamespacePowerUninitialize
0x140083550  mov     rcx, [rbx]
0x140083553  mov     rdx, [rcx+220h]
0x14008355a  test    rdx, rdx
0x14008355d  jz      short loc_140083576
0x14008355f  mov     rcx, [rcx+10h]
0x140083563  call    NvmeControllerFreeExtendedCommand
0x140083568  mov     rax, [rbx]
0x14008356b  mov     qword ptr [rax+220h], 0
0x140083576  mov     rax, [rbx]
0x140083579  mov     rcx, [rax+228h]; IoWorkItem
0x140083580  test    rcx, rcx
0x140083583  jz      short loc_14008359F
0x140083585  call    cs:__imp_IoFreeWorkItem
0x14008358c  nop     dword ptr [rax+rax+00h]
0x140083591  mov     rax, [rbx]
0x140083594  mov     qword ptr [rax+228h], 0
0x14008359f  mov     rax, [rbx]
0x1400835a2  mov     rcx, [rax+0B8h]; P
0x1400835a9  test    rcx, rcx
0x1400835ac  jz      short loc_1400835CD
0x1400835ae  mov     edx, 52436152h; Tag
0x1400835b3  call    cs:__imp_ExFreePoolWithTag
0x1400835ba  nop     dword ptr [rax+rax+00h]
0x1400835bf  mov     rax, [rbx]
0x1400835c2  mov     qword ptr [rax+0B8h], 0
0x1400835cd  mov     rax, [rbx]
0x1400835d0  mov     rcx, [rax+0B0h]; P
0x1400835d7  test    rcx, rcx
0x1400835da  jz      short loc_1400835FB
0x1400835dc  mov     edx, 52436152h; Tag
0x1400835e1  call    cs:__imp_ExFreePoolWithTag
0x1400835e8  nop     dword ptr [rax+rax+00h]
0x1400835ed  mov     rax, [rbx]
0x1400835f0  mov     qword ptr [rax+0B0h], 0
0x1400835fb  mov     rax, [rbx]
0x1400835fe  mov     rcx, [rax+78h]; RunRefCacheAware
0x140083602  test    rcx, rcx
0x140083605  jz      short loc_14008361E
0x140083607  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14008360e  nop     dword ptr [rax+rax+00h]
0x140083613  mov     rax, [rbx]
0x140083616  mov     qword ptr [rax+78h], 0
0x14008361e  mov     rcx, [rbx]
0x140083621  mov     rcx, [rcx+8]; DeviceObject
0x140083625  call    cs:__imp_IoDeleteDevice
0x14008362c  nop     dword ptr [rax+rax+00h]
0x140083631  mov     qword ptr [rbx], 0
0x140083638  add     rsp, 20h
0x14008363c  pop     rbx
0x14008363d  retn
```
