# SrvNetFreeScavengerThread

- ea: `0x14000ae00`
- end: `0x14000b10c`
- name: `SrvNetFreeScavengerThread`
- size: `780`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x14000ae00`
- `0x14000b120`
- `0x14000b298`
- `0x14000b480`
- `0x14000b4a4`
- `0x14000b830`
- `0x140012a70`
- `0x140015790`
- `0x1400550bc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002bd44`
- `ntoskrnl!KeSetEvent` at `0x14002bd44`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aedf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aedf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000ae4b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000af33`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000afaa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000ae4b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000af33`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000afaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ae84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000aff4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ae84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000aff4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ae2f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000af17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000af8e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ae2f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000af17`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000af8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aeb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aeb0`
- `ntoskrnl!IoQueueWorkItem` at `0x14000b055`
- `ntoskrnl!IoQueueWorkItem` at `0x14000b055`
- `ntoskrnl!IoFreeWorkItem` at `0x14002bd21`
- `ntoskrnl!IoFreeWorkItem` at `0x14002bd21`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ae78`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000afe8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ae78`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af6e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000afe8`

## pseudocode

```c
void __fastcall SrvNetFreeScavengerThread(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  struct _LIST_ENTRY **p_Blink; // rdi
  PERESOURCE v3; // rcx
  PVOID *p_Reserved2; // rax
  volatile signed __int32 *Reserved2; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  KIRQL v8; // al
  bool v9; // zf
  KIRQL v10; // si
  char v11; // bl
  PERESOURCE v12; // rcx
  PVOID *v13; // rax
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rsi
  struct _IO_WORKITEM *v16; // rcx
  volatile signed __int32 *v17; // rbx
  struct _KEVENT *v18; // rcx

  p_Blink = &SrvNetDeviceExtension[6].SystemResourcesList.Blink;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
  v3 = SrvNetDeviceExtension;
  p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  Reserved2 = (volatile signed __int32 *)SrvNetDeviceExtension[3].Reserved2;
  while ( Reserved2 != (volatile signed __int32 *)p_Reserved2 )
  {
    v17 = Reserved2;
    _InterlockedIncrement(Reserved2 + 4);
    SrvNetEndpointProcessDisconnects(Reserved2);
    Reserved2 = *(volatile signed __int32 **)Reserved2;
    SrvNetDereferenceEndpoint(v17);
    v3 = SrvNetDeviceExtension;
    p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
  }
  ExReleaseResourceLite((PERESOURCE)((char *)v3 + 288));
  KeLeaveCriticalRegion();
  SrvNetDereferenceConnectionsInDereferenceList();
  SrvNetCloseConnectionsInClosingList();
  SrvNetNotifyClientsOfEndpoints();
  SrvNetNotifyClientsUpdateNetname(v7, v6);
  if ( SrvNetIsAoAc )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
    v12 = SrvNetDeviceExtension;
    v13 = &SrvNetDeviceExtension[3].Reserved2;
    v14 = (volatile signed __int32 *)SrvNetDeviceExtension[3].Reserved2;
    while ( v14 != (volatile signed __int32 *)v13 )
    {
      v15 = v14;
      _InterlockedIncrement(v14 + 4);
      ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288));
      KeLeaveCriticalRegion();
      SrvNetEndpointProcessPdcActivation(v14);
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
      if ( *((_BYTE *)v14 + 146) )
        v14 = (volatile signed __int32 *)&SrvNetDeviceExtension[3].Reserved2;
      v14 = *(volatile signed __int32 **)v14;
      SrvNetDereferenceEndpoint(v15);
      v12 = SrvNetDeviceExtension;
      v13 = &SrvNetDeviceExtension[3].Reserved2;
    }
    ExReleaseResourceLite((PERESOURCE)((char *)v12 + 288));
    KeLeaveCriticalRegion();
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)p_Blink);
  v9 = *((_BYTE *)p_Blink + 169) == 0;
  v10 = v8;
  *((_BYTE *)p_Blink + 168) = 0;
  if ( v9 )
  {
    v11 = *((_BYTE *)p_Blink + 185);
  }
  else
  {
    v16 = (struct _IO_WORKITEM *)p_Blink[20];
    v11 = 0;
    *((_WORD *)p_Blink + 84) = 1;
    IoQueueWorkItem(v16, SrvNetFreeScavengerThread, CriticalWorkQueue, 0);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)p_Blink, v10);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
    }
    IoFreeWorkItem((PIO_WORKITEM)p_Blink[20]);
    v18 = (struct _KEVENT *)p_Blink[22];
    p_Blink[20] = 0;
    KeSetEvent(v18, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
}

```

## disassembly

```asm
0x14000ae00  push    rbx
0x14000ae02  push    rsi
0x14000ae03  push    rdi
0x14000ae04  push    r12
0x14000ae06  sub     rsp, 28h
0x14000ae0a  mov     rdi, cs:SrvNetDeviceExtension
0x14000ae11  add     rdi, 278h
0x14000ae18  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae1f  lea     r12, WPP_GLOBAL_Control
0x14000ae26  cmp     rcx, r12
0x14000ae29  jnz     loc_14000B005
0x14000ae2f  call    cs:__imp_KeEnterCriticalRegion
0x14000ae36  nop     dword ptr [rax+rax+00h]
0x14000ae3b  mov     rcx, cs:SrvNetDeviceExtension
0x14000ae42  mov     dl, 1; Wait
0x14000ae44  add     rcx, 120h; Resource
0x14000ae4b  call    cs:__imp_ExAcquireResourceSharedLite
0x14000ae52  nop     dword ptr [rax+rax+00h]
0x14000ae57  mov     rcx, cs:SrvNetDeviceExtension
0x14000ae5e  lea     rax, [rcx+188h]
0x14000ae65  mov     rsi, [rax]
0x14000ae68  cmp     rsi, rax
0x14000ae6b  jnz     loc_14000B066
0x14000ae71  add     rcx, 120h; Resource
0x14000ae78  call    cs:__imp_ExReleaseResourceLite
0x14000ae7f  nop     dword ptr [rax+rax+00h]
0x14000ae84  call    cs:__imp_KeLeaveCriticalRegion
0x14000ae8b  nop     dword ptr [rax+rax+00h]
0x14000ae90  call    SrvNetDereferenceConnectionsInDereferenceList
0x14000ae95  call    SrvNetCloseConnectionsInClosingList
0x14000ae9a  call    SrvNetNotifyClientsOfEndpoints
0x14000ae9f  call    SrvNetNotifyClientsUpdateNetname
0x14000aea4  cmp     cs:SrvNetIsAoAc, 0
0x14000aeab  jnz     short loc_14000AF17
0x14000aead  mov     rcx, rdi; SpinLock
0x14000aeb0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000aeb7  nop     dword ptr [rax+rax+00h]
0x14000aebc  cmp     byte ptr [rdi+0A9h], 0
0x14000aec3  mov     sil, al
0x14000aec6  mov     byte ptr [rdi+0A8h], 0
0x14000aecd  jnz     loc_14000B036
0x14000aed3  mov     bl, [rdi+0B9h]
0x14000aed9  mov     dl, sil; NewIrql
0x14000aedc  mov     rcx, rdi; SpinLock
0x14000aedf  call    cs:__imp_KeReleaseSpinLock
0x14000aee6  nop     dword ptr [rax+rax+00h]
0x14000aeeb  test    bl, bl
0x14000aeed  jnz     loc_14000B0A6
0x14000aef3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aefa  cmp     rcx, r12
0x14000aefd  jz      short loc_14000AF0C
0x14000aeff  test    dword ptr [rcx+2Ch], 800h
0x14000af06  jnz     loc_14000B0E8
0x14000af0c  add     rsp, 28h
0x14000af10  pop     r12
0x14000af12  pop     rdi
0x14000af13  pop     rsi
0x14000af14  pop     rbx
0x14000af15  retn
0x14000af17  call    cs:__imp_KeEnterCriticalRegion
0x14000af1e  nop     dword ptr [rax+rax+00h]
0x14000af23  mov     rcx, cs:SrvNetDeviceExtension
0x14000af2a  mov     dl, 1; Wait
0x14000af2c  add     rcx, 120h; Resource
0x14000af33  call    cs:__imp_ExAcquireResourceSharedLite
0x14000af3a  nop     dword ptr [rax+rax+00h]
0x14000af3f  mov     rcx, cs:SrvNetDeviceExtension
0x14000af46  lea     rax, [rcx+188h]
0x14000af4d  mov     rbx, [rax]
0x14000af50  cmp     rbx, rax
0x14000af53  jz      loc_14000AFE1
0x14000af59  mov     rsi, rbx
0x14000af5c  lock inc dword ptr [rbx+10h]
0x14000af60  mov     rcx, cs:SrvNetDeviceExtension
0x14000af67  add     rcx, 120h; Resource
0x14000af6e  call    cs:__imp_ExReleaseResourceLite
0x14000af75  nop     dword ptr [rax+rax+00h]
0x14000af7a  call    cs:__imp_KeLeaveCriticalRegion
0x14000af81  nop     dword ptr [rax+rax+00h]
0x14000af86  mov     rcx, rbx
0x14000af89  call    SrvNetEndpointProcessPdcActivation
0x14000af8e  call    cs:__imp_KeEnterCriticalRegion
0x14000af95  nop     dword ptr [rax+rax+00h]
0x14000af9a  mov     rcx, cs:SrvNetDeviceExtension
0x14000afa1  mov     dl, 1; Wait
0x14000afa3  add     rcx, 120h; Resource
0x14000afaa  call    cs:__imp_ExAcquireResourceSharedLite
0x14000afb1  nop     dword ptr [rax+rax+00h]
0x14000afb6  cmp     byte ptr [rbx+92h], 0
0x14000afbd  jnz     loc_14000B093
0x14000afc3  mov     rbx, [rbx]
0x14000afc6  mov     rcx, rsi
0x14000afc9  call    SrvNetDereferenceEndpoint
0x14000afce  mov     rcx, cs:SrvNetDeviceExtension
0x14000afd5  lea     rax, [rcx+188h]
0x14000afdc  jmp     loc_14000AF50
0x14000afe1  add     rcx, 120h; Resource
0x14000afe8  call    cs:__imp_ExReleaseResourceLite
0x14000afef  nop     dword ptr [rax+rax+00h]
0x14000aff4  call    cs:__imp_KeLeaveCriticalRegion
0x14000affb  nop     dword ptr [rax+rax+00h]
0x14000b000  jmp     loc_14000AEAD
0x14000b005  test    dword ptr [rcx+2Ch], 800h
0x14000b00c  jz      loc_14000AE2F
0x14000b012  cmp     byte ptr [rcx+29h], 2
0x14000b016  jb      loc_14000AE2F
0x14000b01c  mov     rcx, [rcx+18h]
0x14000b020  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14000b027  mov     edx, 20h ; ' '
0x14000b02c  call    WPP_SF_
0x14000b031  jmp     loc_14000AE2F
0x14000b036  mov     rcx, [rdi+0A0h]; IoWorkItem
0x14000b03d  lea     rdx, SrvNetFreeScavengerThread; WorkerRoutine
0x14000b044  xor     bl, bl
0x14000b046  mov     word ptr [rdi+0A8h], 1
0x14000b04f  xor     r9d, r9d; Context
0x14000b052  xor     r8d, r8d; QueueType
0x14000b055  call    cs:__imp_IoQueueWorkItem
0x14000b05c  nop     dword ptr [rax+rax+00h]
0x14000b061  jmp     loc_14000AED9
0x14000b066  mov     rbx, rsi
0x14000b069  lock inc dword ptr [rsi+10h]
0x14000b06d  mov     rcx, rsi
0x14000b070  call    SrvNetEndpointProcessDisconnects
0x14000b075  mov     rsi, [rsi]
0x14000b078  mov     rcx, rbx
0x14000b07b  call    SrvNetDereferenceEndpoint
0x14000b080  mov     rcx, cs:SrvNetDeviceExtension
0x14000b087  lea     rax, [rcx+188h]
0x14000b08e  jmp     loc_14000AE68
0x14000b093  mov     rbx, cs:SrvNetDeviceExtension
0x14000b09a  add     rbx, 188h
0x14000b0a1  jmp     loc_14000AFC3
0x14000b0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0ad  cmp     rcx, r12
0x14000b0b0  jz      loc_14002BD1A
0x14000b0b6  test    dword ptr [rcx+2Ch], 800h
0x14000b0bd  jz      loc_14002BD1A
0x14000b0c3  cmp     byte ptr [rcx+29h], 2
0x14000b0c7  jb      loc_14002BD1A
0x14000b0cd  mov     rcx, [rcx+18h]
0x14000b0d1  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14000b0d8  mov     edx, 21h ; '!'
0x14000b0dd  call    WPP_SF_
0x14000b0e2  nop
0x14000b0e3  jmp     loc_14002BD1A
0x14000b0e8  cmp     byte ptr [rcx+29h], 2
0x14000b0ec  jb      loc_14000AF0C
0x14000b0f2  mov     rcx, [rcx+18h]
0x14000b0f6  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x14000b0fd  mov     edx, 22h ; '"'
0x14000b102  call    WPP_SF_
0x14000b107  jmp     loc_14000AF0C
0x14002bd1a  mov     rcx, [rdi+0A0h]; IoWorkItem
0x14002bd21  call    cs:__imp_IoFreeWorkItem
0x14002bd28  nop     dword ptr [rax+rax+00h]
0x14002bd2d  mov     rcx, [rdi+0B0h]; Event
0x14002bd34  xor     r8d, r8d; Wait
0x14002bd37  xor     edx, edx; Increment
0x14002bd39  mov     qword ptr [rdi+0A0h], 0
0x14002bd44  call    cs:__imp_KeSetEvent
0x14002bd4b  nop     dword ptr [rax+rax+00h]
0x14002bd50  nop
0x14002bd51  jmp     loc_14000AEF3
```
