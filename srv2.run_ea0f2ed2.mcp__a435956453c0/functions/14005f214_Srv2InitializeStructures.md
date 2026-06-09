# Srv2InitializeStructures

- ea: `0x14005f214`
- end: `0x14005f438`
- name: `Srv2InitializeStructures`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14005f538`

## callees

- `0x14001fbec`
- `0x1400224b8`
- `0x140038980`
- `0x14005d648`
- `0x14005dbf8`
- `0x14005efec`
- `0x14005f178`
- `0x14005f214`
- `0x140060740`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14005f3e9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005f3e9`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005f328`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005f328`
- `ntoskrnl!RtlGetVersion` at `0x14005f284`
- `ntoskrnl!RtlGetVersion` at `0x14005f284`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14005f401`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14005f401`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005f359`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005f359`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005f308`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14005f308`
- `ntoskrnl!KeInitializeEvent` at `0x14005f37b`
- `ntoskrnl!KeInitializeEvent` at `0x14005f37b`
- `srvnet!SrvNetGetStatisticsAndLock` at `0x14005f231`
- `srvnet!SrvNetGetStatisticsAndLock` at `0x14005f231`

## pseudocode

```c
__int64 Srv2InitializeStructures()
{
  char v0; // si
  char v1; // di
  NTSTATUS Version; // ebx
  int v3; // r8d
  int v4; // r9d

  SrvNetGetStatisticsAndLock(&Srv2Statistics, &Srv2StatisticsLock);
  if ( Srv2Statistics && Srv2StatisticsLock )
  {
    v0 = 0;
    v1 = 0;
    memset(&Srv2OsInfo.dwMajorVersion, 0, 0x118u);
    Srv2OsInfo.dwOSVersionInfoSize = 284;
    Version = RtlGetVersion(&Srv2OsInfo);
    if ( Version < 0 )
      goto LABEL_16;
    qword_140058148 = (PVOID)PplCreateLookasideList(
                               (unsigned int)Srv2AllocateLookasideWorkItem,
                               (unsigned int)Srv2FreeLookasideWorkItem,
                               v3,
                               v4);
    if ( qword_140058148 )
    {
      Version = ExInitializeLookasideListEx(
                  &Srv2PagedBlockTypeBuffer8K,
                  0,
                  0,
                  PagedPool,
                  0,
                  0x2000u,
                  0x6232534Cu,
                  0x100u);
      if ( Version >= 0 )
      {
        v0 = 1;
        Version = ExInitializeResourceLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
        if ( Version >= 0 )
        {
          Version = Srv2InitializeCryptoSupport();
          if ( Version >= 0 )
          {
            Srv2InitializeProviderList();
            KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
            Srv2DriverReferenceCount = 1;
            KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.Dpc.DeferredRoutine, NotificationEvent, 0);
            Version = Srv2InitializeInstances();
            if ( Version >= 0 )
              return 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                10,
                &WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids,
                (unsigned int)Version);
            }
            Srv2DeinitializeCryptoSupport();
LABEL_17:
            ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
LABEL_18:
            if ( v0 )
              ExDeleteLookasideListEx(&Srv2PagedBlockTypeBuffer8K);
            goto LABEL_23;
          }
          v1 = 1;
        }
      }
LABEL_16:
      Srv2DeinitializeCryptoSupport();
      if ( !v1 )
        goto LABEL_18;
      goto LABEL_17;
    }
    Version = -1073741670;
  }
  else
  {
    Version = -1073741595;
  }
  Srv2DeinitializeCryptoSupport();
LABEL_23:
  Srv2DeinitializeWorkItemLookasides();
  return (unsigned int)Version;
}

```

## disassembly

```asm
0x14005f214  mov     [rsp+arg_0], rbx
0x14005f219  mov     [rsp+arg_8], rsi
0x14005f21e  push    rdi
0x14005f21f  sub     rsp, 50h
0x14005f223  lea     rdx, Srv2StatisticsLock
0x14005f22a  lea     rcx, Srv2Statistics
0x14005f231  call    cs:__imp_SrvNetGetStatisticsAndLock
0x14005f238  nop     dword ptr [rax+rax+00h]
0x14005f23d  cmp     cs:Srv2Statistics, 0
0x14005f245  jz      loc_14005F416
0x14005f24b  cmp     cs:Srv2StatisticsLock, 0
0x14005f253  jz      loc_14005F416
0x14005f259  xor     edx, edx; Val
0x14005f25b  lea     rcx, Srv2OsInfo.dwMajorVersion; void *
0x14005f262  mov     r8d, 118h; Size
0x14005f268  xor     sil, sil
0x14005f26b  xor     dil, dil
0x14005f26e  call    memset
0x14005f273  lea     rcx, Srv2OsInfo; lpVersionInformation
0x14005f27a  mov     cs:Srv2OsInfo.dwOSVersionInfoSize, 11Ch
0x14005f284  call    cs:__imp_RtlGetVersion
0x14005f28b  nop     dword ptr [rax+rax+00h]
0x14005f290  mov     ebx, eax
0x14005f292  test    eax, eax
0x14005f294  js      loc_14005F3D8
0x14005f29a  mov     [rsp+58h+var_18], 2432534Ch
0x14005f2a2  lea     rdx, Srv2FreeLookasideWorkItem
0x14005f2a9  mov     [rsp+58h+Tag], 7732534Ch
0x14005f2b1  lea     rcx, Srv2AllocateLookasideWorkItem
0x14005f2b8  mov     [rsp+58h+Size], 760h
0x14005f2c1  call    PplCreateLookasideList
0x14005f2c6  mov     cs:qword_140058148, rax
0x14005f2cd  test    rax, rax
0x14005f2d0  jz      loc_14005F40F
0x14005f2d6  mov     [rsp+58h+Depth], 100h; Depth
0x14005f2dd  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x14005f2e4  mov     [rsp+58h+Tag], 6232534Ch; Tag
0x14005f2ec  mov     r9d, 1; PoolType
0x14005f2f2  mov     [rsp+58h+Size], 2000h; Size
0x14005f2fb  xor     r8d, r8d; Free
0x14005f2fe  xor     edx, edx; Allocate
0x14005f300  mov     [rsp+58h+Flags], 0; Flags
0x14005f308  call    cs:__imp_ExInitializeLookasideListEx
0x14005f30f  nop     dword ptr [rax+rax+00h]
0x14005f314  mov     ebx, eax
0x14005f316  test    eax, eax
0x14005f318  js      loc_14005F3D8
0x14005f31e  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x14005f325  mov     sil, 1
0x14005f328  call    cs:__imp_ExInitializeResourceLite
0x14005f32f  nop     dword ptr [rax+rax+00h]
0x14005f334  mov     ebx, eax
0x14005f336  test    eax, eax
0x14005f338  js      loc_14005F3D8
0x14005f33e  call    Srv2InitializeCryptoSupport
0x14005f343  mov     ebx, eax
0x14005f345  test    eax, eax
0x14005f347  js      loc_14005F3D5
0x14005f34d  call    Srv2InitializeProviderList
0x14005f352  lea     rcx, WPP_MAIN_CB.DeviceExtension; SpinLock
0x14005f359  call    cs:__imp_KeInitializeSpinLock
0x14005f360  nop     dword ptr [rax+rax+00h]
0x14005f365  xor     r8d, r8d; State
0x14005f368  mov     cs:Srv2DriverReferenceCount, 1
0x14005f372  xor     edx, edx; Type
0x14005f374  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; Event
0x14005f37b  call    cs:__imp_KeInitializeEvent
0x14005f382  nop     dword ptr [rax+rax+00h]
0x14005f387  call    Srv2InitializeInstances
0x14005f38c  mov     ebx, eax
0x14005f38e  test    eax, eax
0x14005f390  jns     short loc_14005F3D1
0x14005f392  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005f399  lea     rax, WPP_GLOBAL_Control
0x14005f3a0  cmp     rcx, rax
0x14005f3a3  jz      short loc_14005F3CA
0x14005f3a5  mov     eax, [rcx+2Ch]
0x14005f3a8  test    al, 8
0x14005f3aa  jz      short loc_14005F3CA
0x14005f3ac  cmp     [rcx+29h], sil
0x14005f3b0  jb      short loc_14005F3CA
0x14005f3b2  mov     rcx, [rcx+18h]
0x14005f3b6  lea     r8, WPP_5bb5acbc86b838dd4009309de35c075e_Traceguids
0x14005f3bd  mov     edx, 0Ah
0x14005f3c2  mov     r9d, ebx
0x14005f3c5  call    WPP_SF_d
0x14005f3ca  call    Srv2DeinitializeCryptoSupport
0x14005f3cf  jmp     short loc_14005F3E2
0x14005f3d1  xor     eax, eax
0x14005f3d3  jmp     short loc_14005F427
0x14005f3d5  mov     dil, sil
0x14005f3d8  call    Srv2DeinitializeCryptoSupport
0x14005f3dd  test    dil, dil
0x14005f3e0  jz      short loc_14005F3F5
0x14005f3e2  lea     rcx, WPP_MAIN_CB.Queue+10h; Resource
0x14005f3e9  call    cs:__imp_ExDeleteResourceLite
0x14005f3f0  nop     dword ptr [rax+rax+00h]
0x14005f3f5  test    sil, sil
0x14005f3f8  jz      short loc_14005F420
0x14005f3fa  lea     rcx, Srv2PagedBlockTypeBuffer8K; Lookaside
0x14005f401  call    cs:__imp_ExDeleteLookasideListEx
0x14005f408  nop     dword ptr [rax+rax+00h]
0x14005f40d  jmp     short loc_14005F420
0x14005f40f  mov     ebx, 0C000009Ah
0x14005f414  jmp     short loc_14005F41B
0x14005f416  mov     ebx, 0C00000E5h
0x14005f41b  call    Srv2DeinitializeCryptoSupport
0x14005f420  call    Srv2DeinitializeWorkItemLookasides
0x14005f425  mov     eax, ebx
0x14005f427  mov     rbx, [rsp+58h+arg_0]
0x14005f42c  mov     rsi, [rsp+58h+arg_8]
0x14005f431  add     rsp, 50h
0x14005f435  pop     rdi
0x14005f436  retn
```
