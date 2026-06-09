# UdfDeleteVcb

- ea: `0x14002c008`
- end: `0x14002c15d`
- name: `UdfDeleteVcb`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140008594`
- `0x140018740`

## callees

- `0x140004340`
- `0x14000b200`
- `0x14001c080`
- `0x14002c008`
- `0x14002c164`
- `0x14002c250`
- `0x14002c2f8`
- `0x140030f44`
- `0x140058564`
- `0x140059004`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0b4`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0c7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0da`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0ed`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0b4`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0c7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0da`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002c0ed`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c07c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c07c`
- `ntoskrnl!IoDeleteDevice` at `0x14002c13e`
- `ntoskrnl!IoDeleteDevice` at `0x14002c13e`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x14002c11b`
- `ntoskrnl!FsRtlNotifyUninitializeSync` at `0x14002c11b`

## pseudocode

```c
void __fastcall UdfDeleteVcb(__int64 a1, __int64 a2)
{
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rdx

  UdfTearDownAllocationSupport(a1, a2);
  UdfPowTrackInfoDestroy((void *)(a2 + 888));
  UdfKillCleanVolumeTimer(a2);
  UdfSeqCacheTearDown(a1, a2);
  UdfFreePool(a2 + 1848);
  UdfFreePool(a2 + 8);
  UdfFreePool(a2 + 1424);
  v4 = *(void **)(a2 + 16);
  if ( v4 )
    UdfDeletePcb(v4);
  UdfTearDownRmwSupport(v4, a2);
  v5 = *(void **)(a2 + 24);
  if ( v5 )
    ObfDereferenceObject(v5);
  v6 = *(_QWORD *)(a2 + 32);
  if ( *(_QWORD *)(v6 + 8) != a2 + 32 || (v7 = *(_QWORD **)(a2 + 40), *v7 != a2 + 32) )
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  ExDeleteResourceLite((PERESOURCE)(a2 + 1480));
  ExDeleteResourceLite((PERESOURCE)(a2 + 2024));
  ExDeleteResourceLite((PERESOURCE)(a2 + 360));
  ExDeleteResourceLite((PERESOURCE)(a2 + 136));
  if ( (*(_DWORD *)(a2 + 48) & 0x400) != 0 )
    UdfUninitializeVmcb((void *)(a2 + 984));
  if ( *(_QWORD *)(a2 + 1712) )
    FsRtlNotifyUninitializeSync((PNOTIFY_SYNC *)(a2 + 1712));
  memset((void *)a2, 0, 0xA00u);
  IoDeleteDevice((PDEVICE_OBJECT)(a2 - 368));
}

```

## disassembly

```asm
0x14002c008  mov     [rsp+arg_0], rbx
0x14002c00d  push    rdi
0x14002c00e  sub     rsp, 20h
0x14002c012  mov     rdi, rdx
0x14002c015  mov     rbx, rcx
0x14002c018  call    UdfTearDownAllocationSupport
0x14002c01d  lea     rcx, [rdi+378h]; void *
0x14002c024  call    UdfPowTrackInfoDestroy
0x14002c029  mov     rcx, rdi
0x14002c02c  call    UdfKillCleanVolumeTimer
0x14002c031  mov     rdx, rdi
0x14002c034  mov     rcx, rbx
0x14002c037  call    UdfSeqCacheTearDown
0x14002c03c  lea     rcx, [rdi+738h]
0x14002c043  call    UdfFreePool
0x14002c048  lea     rcx, [rdi+8]
0x14002c04c  call    UdfFreePool
0x14002c051  lea     rcx, [rdi+590h]
0x14002c058  call    UdfFreePool
0x14002c05d  mov     rcx, [rdi+10h]; P
0x14002c061  test    rcx, rcx
0x14002c064  jz      short loc_14002C06B
0x14002c066  call    UdfDeletePcb
0x14002c06b  mov     rdx, rdi
0x14002c06e  call    UdfTearDownRmwSupport
0x14002c073  mov     rcx, [rdi+18h]; Object
0x14002c077  test    rcx, rcx
0x14002c07a  jz      short loc_14002C088
0x14002c07c  call    cs:__imp_ObfDereferenceObject
0x14002c083  nop     dword ptr [rax+rax+00h]
0x14002c088  lea     rax, [rdi+20h]
0x14002c08c  mov     rcx, [rax]
0x14002c08f  cmp     [rcx+8], rax
0x14002c093  jnz     loc_14002C156
0x14002c099  mov     rdx, [rax+8]
0x14002c09d  cmp     [rdx], rax
0x14002c0a0  jnz     loc_14002C156
0x14002c0a6  mov     [rdx], rcx
0x14002c0a9  mov     [rcx+8], rdx
0x14002c0ad  lea     rcx, [rdi+5C8h]; Resource
0x14002c0b4  call    cs:__imp_ExDeleteResourceLite
0x14002c0bb  nop     dword ptr [rax+rax+00h]
0x14002c0c0  lea     rcx, [rdi+7E8h]; Resource
0x14002c0c7  call    cs:__imp_ExDeleteResourceLite
0x14002c0ce  nop     dword ptr [rax+rax+00h]
0x14002c0d3  lea     rcx, [rdi+168h]; Resource
0x14002c0da  call    cs:__imp_ExDeleteResourceLite
0x14002c0e1  nop     dword ptr [rax+rax+00h]
0x14002c0e6  lea     rcx, [rdi+88h]; Resource
0x14002c0ed  call    cs:__imp_ExDeleteResourceLite
0x14002c0f4  nop     dword ptr [rax+rax+00h]
0x14002c0f9  test    dword ptr [rdi+30h], 400h
0x14002c100  jz      short loc_14002C10E
0x14002c102  lea     rcx, [rdi+3D8h]; void *
0x14002c109  call    UdfUninitializeVmcb
0x14002c10e  lea     rcx, [rdi+6B0h]; NotifySync
0x14002c115  cmp     qword ptr [rcx], 0
0x14002c119  jz      short loc_14002C127
0x14002c11b  call    cs:__imp_FsRtlNotifyUninitializeSync
0x14002c122  nop     dword ptr [rax+rax+00h]
0x14002c127  xor     edx, edx; Val
0x14002c129  mov     r8d, 0A00h; Size
0x14002c12f  mov     rcx, rdi; void *
0x14002c132  call    memset
0x14002c137  lea     rcx, [rdi-170h]; DeviceObject
0x14002c13e  call    cs:__imp_IoDeleteDevice
0x14002c145  nop     dword ptr [rax+rax+00h]
0x14002c14a  mov     rbx, [rsp+28h+arg_0]
0x14002c14f  add     rsp, 20h
0x14002c153  pop     rdi
0x14002c154  retn
0x14002c156  mov     ecx, 3
0x14002c15b  int     29h; Win8: RtlFailFast(ecx)
```
