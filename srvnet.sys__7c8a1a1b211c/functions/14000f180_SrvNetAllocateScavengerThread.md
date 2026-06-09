# SrvNetAllocateScavengerThread

- ea: `0x14000f180`
- end: `0x14000f366`
- name: `SrvNetAllocateScavengerThread`
- size: `486`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000f180`
- `0x140015790`
- `0x1400160d4`
- `0x1400161a4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000f31f`
- `ntoskrnl!KeSetEvent` at `0x14000f31f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f2b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f2b5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000f1eb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000f1eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f24f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f24f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f1cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f1cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f25e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f25e`
- `ntoskrnl!IoQueueWorkItem` at `0x14000f2a3`
- `ntoskrnl!IoQueueWorkItem` at `0x14000f2a3`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f2fc`
- `ntoskrnl!IoFreeWorkItem` at `0x14000f2fc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f243`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f243`

## pseudocode

```c
void __fastcall SrvNetAllocateScavengerThread(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  struct _LIST_ENTRY **p_Blink; // rdi
  PERESOURCE v3; // rcx
  PVOID *p_Reserved2; // rax
  PVOID *Reserved2; // rbx
  KIRQL v6; // al
  char v7; // bl
  KIRQL v8; // si
  struct _IO_WORKITEM *v9; // rcx
  struct _KEVENT *v10; // rcx

  p_Blink = &SrvNetDeviceExtension[6].SystemResourcesList.Blink;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
  v3 = SrvNetDeviceExtension;
  p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  Reserved2 = (PVOID *)SrvNetDeviceExtension[3].Reserved2;
  while ( Reserved2 != p_Reserved2 )
  {
    if ( !*((_DWORD *)Reserved2 + 31) )
      SrvNetEndpointReopenTdiConnections((__int64)Reserved2);
    if ( !*((_BYTE *)Reserved2 + 121) )
      SrvNetEndpointAllocateConnections(Reserved2);
    v3 = SrvNetDeviceExtension;
    Reserved2 = (PVOID *)*Reserved2;
    p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  }
  ExReleaseResourceLite((PERESOURCE)((char *)v3 + 288));
  KeLeaveCriticalRegion();
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)p_Blink);
  v7 = *((_BYTE *)p_Blink + 185);
  v8 = v6;
  *((_BYTE *)p_Blink + 145) = 0;
  if ( !v7 && *((_BYTE *)p_Blink + 144) )
  {
    v9 = (struct _IO_WORKITEM *)p_Blink[17];
    *((_WORD *)p_Blink + 72) = 256;
    IoQueueWorkItem(v9, SrvNetAllocateScavengerThread, CriticalWorkQueue, 0);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)p_Blink, v8);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
    }
    IoFreeWorkItem((PIO_WORKITEM)p_Blink[17]);
    v10 = (struct _KEVENT *)p_Blink[19];
    p_Blink[17] = 0;
    KeSetEvent(v10, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
}

```

## disassembly

```asm
0x14000f180  push    rbx
0x14000f182  push    rsi
0x14000f183  push    rdi
0x14000f184  push    r12
0x14000f186  sub     rsp, 28h
0x14000f18a  mov     rdi, cs:SrvNetDeviceExtension
0x14000f191  add     rdi, 278h
0x14000f198  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f19f  lea     r12, WPP_GLOBAL_Control
0x14000f1a6  cmp     rcx, r12
0x14000f1a9  jz      short loc_14000F1CF
0x14000f1ab  test    dword ptr [rcx+2Ch], 800h
0x14000f1b2  jz      short loc_14000F1CF
0x14000f1b4  cmp     byte ptr [rcx+29h], 2
0x14000f1b8  jb      short loc_14000F1CF
0x14000f1ba  mov     rcx, [rcx+18h]
0x14000f1be  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14000f1c5  mov     edx, 23h ; '#'
0x14000f1ca  call    WPP_SF_
0x14000f1cf  call    cs:__imp_KeEnterCriticalRegion
0x14000f1d6  nop     dword ptr [rax+rax+00h]
0x14000f1db  mov     rcx, cs:SrvNetDeviceExtension
0x14000f1e2  mov     dl, 1; Wait
0x14000f1e4  add     rcx, 120h; Resource
0x14000f1eb  call    cs:__imp_ExAcquireResourceSharedLite
0x14000f1f2  nop     dword ptr [rax+rax+00h]
0x14000f1f7  mov     rcx, cs:SrvNetDeviceExtension
0x14000f1fe  lea     rax, [rcx+188h]
0x14000f205  mov     rbx, [rax]
0x14000f208  jmp     short loc_14000F237
0x14000f20a  cmp     dword ptr [rbx+7Ch], 0
0x14000f20e  jnz     short loc_14000F218
0x14000f210  mov     rcx, rbx
0x14000f213  call    SrvNetEndpointReopenTdiConnections
0x14000f218  cmp     byte ptr [rbx+79h], 0
0x14000f21c  jnz     short loc_14000F226
0x14000f21e  mov     rcx, rbx
0x14000f221  call    SrvNetEndpointAllocateConnections
0x14000f226  mov     rcx, cs:SrvNetDeviceExtension
0x14000f22d  mov     rbx, [rbx]
0x14000f230  lea     rax, [rcx+188h]
0x14000f237  cmp     rbx, rax
0x14000f23a  jnz     short loc_14000F20A
0x14000f23c  add     rcx, 120h; Resource
0x14000f243  call    cs:__imp_ExReleaseResourceLite
0x14000f24a  nop     dword ptr [rax+rax+00h]
0x14000f24f  call    cs:__imp_KeLeaveCriticalRegion
0x14000f256  nop     dword ptr [rax+rax+00h]
0x14000f25b  mov     rcx, rdi; SpinLock
0x14000f25e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f265  nop     dword ptr [rax+rax+00h]
0x14000f26a  mov     bl, [rdi+0B9h]
0x14000f270  mov     sil, al
0x14000f273  mov     byte ptr [rdi+91h], 0
0x14000f27a  test    bl, bl
0x14000f27c  jnz     short loc_14000F2AF
0x14000f27e  cmp     [rdi+90h], bl
0x14000f284  jz      short loc_14000F2AF
0x14000f286  mov     rcx, [rdi+88h]; IoWorkItem
0x14000f28d  lea     rdx, SrvNetAllocateScavengerThread; WorkerRoutine
0x14000f294  xor     r9d, r9d; Context
0x14000f297  mov     word ptr [rdi+90h], 100h
0x14000f2a0  xor     r8d, r8d; QueueType
0x14000f2a3  call    cs:__imp_IoQueueWorkItem
0x14000f2aa  nop     dword ptr [rax+rax+00h]
0x14000f2af  mov     dl, sil; NewIrql
0x14000f2b2  mov     rcx, rdi; SpinLock
0x14000f2b5  call    cs:__imp_KeReleaseSpinLock
0x14000f2bc  nop     dword ptr [rax+rax+00h]
0x14000f2c1  test    bl, bl
0x14000f2c3  jz      short loc_14000F32B
0x14000f2c5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f2cc  cmp     rcx, r12
0x14000f2cf  jz      short loc_14000F2F5
0x14000f2d1  test    dword ptr [rcx+2Ch], 800h
0x14000f2d8  jz      short loc_14000F2F5
0x14000f2da  cmp     byte ptr [rcx+29h], 2
0x14000f2de  jb      short loc_14000F2F5
0x14000f2e0  mov     rcx, [rcx+18h]
0x14000f2e4  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14000f2eb  mov     edx, 24h ; '$'
0x14000f2f0  call    WPP_SF_
0x14000f2f5  mov     rcx, [rdi+88h]; IoWorkItem
0x14000f2fc  call    cs:__imp_IoFreeWorkItem
0x14000f303  nop     dword ptr [rax+rax+00h]
0x14000f308  mov     rcx, [rdi+98h]; Event
0x14000f30f  xor     r8d, r8d; Wait
0x14000f312  xor     edx, edx; Increment
0x14000f314  mov     qword ptr [rdi+88h], 0
0x14000f31f  call    cs:__imp_KeSetEvent
0x14000f326  nop     dword ptr [rax+rax+00h]
0x14000f32b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000f332  cmp     rcx, r12
0x14000f335  jz      short loc_14000F35B
0x14000f337  test    dword ptr [rcx+2Ch], 800h
0x14000f33e  jz      short loc_14000F35B
0x14000f340  cmp     byte ptr [rcx+29h], 2
0x14000f344  jb      short loc_14000F35B
0x14000f346  mov     rcx, [rcx+18h]
0x14000f34a  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14000f351  mov     edx, 25h ; '%'
0x14000f356  call    WPP_SF_
0x14000f35b  add     rsp, 28h
0x14000f35f  pop     r12
0x14000f361  pop     rdi
0x14000f362  pop     rsi
0x14000f363  pop     rbx
0x14000f364  retn
```
