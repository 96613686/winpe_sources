# RootDeviceAdd

- ea: `0x14002a790`
- end: `0x14002b1b4`
- name: `RootDeviceAdd`
- size: `2596`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400038cc`
- `0x140006ca0`
- `0x140006ea0`
- `0x140009718`
- `0x1400140fc`
- `0x140017000`
- `0x140017190`
- `0x140017540`
- `0x14002a790`
- `0x14002c488`
- `0x14002db44`
- `0x14002e700`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002ac33`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ac33`
- `ntoskrnl!KeInitializeEvent` at `0x14002add4`
- `ntoskrnl!KeInitializeEvent` at `0x14002add4`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002aebf`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002aebf`
- `ntoskrnl!ExRegisterCallback` at `0x14002ac97`
- `ntoskrnl!ExRegisterCallback` at `0x14002ac97`
- `ntoskrnl!ExCreateCallback` at `0x14002ac76`
- `ntoskrnl!ExCreateCallback` at `0x14002ac76`
- `ntoskrnl!ExAllocatePool2` at `0x14002aedd`
- `ntoskrnl!ExAllocatePool2` at `0x14002af16`
- `ntoskrnl!ExAllocatePool2` at `0x14002aedd`
- `ntoskrnl!ExAllocatePool2` at `0x14002af16`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002b00c`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002b00c`

## pseudocode

```c
__int64 __fastcall RootDeviceAdd(__int64 a1, __int64 a2)
{
  int v3; // ebx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdi
  __int64 MaximumProcessorCount; // rbx
  __int64 Pool2; // rax
  __int64 v10; // rax
  struct _DEVICE_OBJECT *v11; // rax
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  int Parameter; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+68h] [rbp-98h]
  __int128 v23; // [rsp+78h] [rbp-88h]
  __int64 *v24; // [rsp+88h] [rbp-78h]
  __int128 v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h]
  _OWORD v27[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v28[2]; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v31[12]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v32[18]; // [rsp+180h] [rbp+80h] BYREF
  GUID v33; // [rsp+210h] [rbp+110h] BYREF
  __int64 v34; // [rsp+220h] [rbp+120h]
  _OWORD v35[2]; // [rsp+228h] [rbp+128h] BYREF

  v19 = a2;
  memset(v32, 0, 0x8Cu);
  memset(v31, 0, sizeof(v31));
  v28[0] = 1835034;
  LODWORD(v24) = 0;
  v34 = 0;
  v18 = 0;
  LODWORD(v26) = 0;
  memset(v27, 0, 28);
  v28[1] = v35;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v33 = 0;
  v25 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v35[0] = *(_OWORD *)L"\\Device\\VMBus";
  *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)L"e\\VMBus";
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 528))(WdfDriverGlobals, a2, 42);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 488))(WdfDriverGlobals, v19, 3);
  memset(v27, 0, sizeof(v27));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x1B )
      LODWORD(v27[0]) = -1;
    else
      LODWORD(v27[0]) = *(_DWORD *)(WdfStructures + 216);
  }
  else
  {
    LODWORD(v27[0]) = 32;
  }
  *((_QWORD *)&v27[0] + 1) = RootFilterAddResourceRequirements;
  *((_QWORD *)&v27[1] + 1) = RootRemoveAddedResources;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 1024))(
    WdfDriverGlobals,
    v19,
    v27);
  memset(v32, 0, sizeof(v32));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x29 )
      LODWORD(v32[0]) = -1;
    else
      LODWORD(v32[0]) = *(_DWORD *)(WdfStructures + 328);
  }
  else
  {
    LODWORD(v32[0]) = 144;
  }
  v32[5] = RootDevicePrepareHardwareChild;
  v32[6] = RootDeviceReleaseHardwareChild;
  v32[9] = RootDeviceSelfManagedIoInit;
  v32[11] = RootDeviceSelfManagedIoRestart;
  v32[10] = RootDeviceSelfManagedIoSuspend;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 440))(
    WdfDriverGlobals,
    v19,
    v32);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 504))(WdfDriverGlobals, v19);
  memset(v31, 0, sizeof(v31));
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 2 )
      LODWORD(v31[0]) = -1;
    else
      LODWORD(v31[0]) = *(_DWORD *)(WdfStructures + 16);
  }
  else
  {
    LODWORD(v31[0]) = 96;
  }
  v31[2] = RootDeviceListCreatePdo;
  HIDWORD(v31[0]) = 208;
  v31[5] = InstanceDeviceListIdentificationDescriptionDuplicate;
  v31[7] = InstanceDeviceListIdentificationDescriptionCompare;
  v31[6] = InstanceDeviceListIdentificationDescriptionCleanup;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, _QWORD))(WdfFunctions_01033 + 1040))(
    WdfDriverGlobals,
    v19,
    v31,
    0);
  v21 = 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v21) = -1;
    else
      LODWORD(v21) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v21) = 56;
  }
  v24 = off_14001C0C8;
  *((_QWORD *)&v21 + 1) = RootDeviceContextCleanup;
  *(_QWORD *)&v22 = RootDeviceContextDestroy;
  *((_QWORD *)&v22 + 1) = 0x100000002LL;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 536))(
         WdfDriverGlobals,
         v19,
         v28);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01033 + 544))(
           WdfDriverGlobals,
           v19,
           &SDDL_DEVOBJ_KERNEL_ONLY);
    if ( v3 >= 0 )
    {
      LOBYTE(v6) = 14;
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, void *, __int64, _QWORD, _DWORD))(WdfFunctions_01033 + 584))(
             WdfDriverGlobals,
             v19,
             &RootFileRdmaIoctlPreprocess,
             v6,
             0,
             0);
      if ( v3 < 0 )
        return (unsigned int)v3;
      RtlInitUnicodeString(&DestinationString, L"\\Callback\\SoftRestart");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 80;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ExCreateCallback(&KsrCallbackObject, &ObjectAttributes, 0, 1u) >= 0 )
        ExRegisterCallback(KsrCallbackObject, RootDeviceKsrCallback, 0);
      v3 = RootFileInit(v19);
      if ( v3 >= 0 )
      {
        v3 = AddFdoSupportedInterfaces(v19);
        if ( v3 < 0 )
          return (unsigned int)v3;
        v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, __int64 *))(WdfFunctions_01033 + 600))(
               WdfDriverGlobals,
               &v19,
               &v21,
               &v18);
        if ( v3 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                 WdfDriverGlobals,
                 v18,
                 off_14001C0C8);
          *(_DWORD *)v7 = 1953460082;
          *(_QWORD *)(v7 + 88) = v7 + 80;
          *(_QWORD *)(v7 + 80) = v7 + 80;
          *(_QWORD *)(v7 + 104) = v7 + 96;
          *(_QWORD *)(v7 + 96) = v7 + 96;
          *(_QWORD *)(v7 + 136) = v7 + 128;
          *(_QWORD *)(v7 + 128) = v7 + 128;
          *(_DWORD *)(v7 + 24) = 1;
          *(_QWORD *)(v7 + 32) = 0;
          *(_DWORD *)(v7 + 40) = 0;
          KeInitializeEvent((PRKEVENT)(v7 + 48), SynchronizationEvent, 0);
          v26 = 0;
          v25 = 0;
          if ( WdfClientVersionHigherThanFramework )
          {
            if ( (unsigned int)WdfStructureCount <= 0x43 )
              LODWORD(v25) = -1;
            else
              LODWORD(v25) = *(_DWORD *)(WdfStructures + 536);
          }
          else
          {
            LODWORD(v25) = 24;
          }
          LOBYTE(v26) = 1;
          *((_QWORD *)&v25 + 1) = RootNotifyDeviceInterfaceArrival;
          v24 = 0;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          if ( WdfClientVersionHigherThanFramework )
          {
            if ( (unsigned int)WdfStructureCount <= 0x26 )
              LODWORD(v21) = -1;
            else
              LODWORD(v21) = *(_DWORD *)(WdfStructures + 304);
          }
          else
          {
            LODWORD(v21) = 56;
          }
          *(_QWORD *)&v23 = v18;
          *((_QWORD *)&v22 + 1) = 0x100000001LL;
          v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, __int64))(WdfFunctions_01033
                                                                                               + 3032))(
                 WdfDriverGlobals,
                 &v25,
                 &v21,
                 v7 + 160);
          if ( v3 >= 0 )
          {
            MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
            Pool2 = ExAllocatePool2(64, MaximumProcessorCount, 1937072726);
            *(_QWORD *)(v7 + 152) = Pool2;
            if ( !Pool2 )
              return (unsigned int)-1073741670;
            if ( !(unsigned int)IsInterruptEnlightenmentAvailable() )
            {
              v10 = ExAllocatePool2(64, 8 * MaximumProcessorCount, 1937072726);
              if ( (*(_QWORD *)(v7 + 144) = v10) == 0 )
                return (unsigned int)-1073741670;
            }
            v11 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 248))(
                                             WdfDriverGlobals,
                                             v18);
            ChVmContext = v18;
            ChRootDeviceObject = v11;
            v12 = ChOfferCacheInit();
            v3 = 0;
            if ( v12 < 0 )
              v3 = v12;
            if ( v3 >= 0 )
            {
              v3 = XPartInit(v18);
              if ( v3 >= 0 )
              {
                Parameter = -1073741823;
                if ( RtlRunOnceExecuteOnce(&RunOnce, AwpInitializeQueues, &Parameter, 0) >= 0
                  || (v3 = Parameter, Parameter >= 0) )
                {
                  v3 = UtilExportInit(v18, v7);
                  if ( v3 >= 0 )
                  {
                    LOBYTE(v13) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      1,
                      v13);
                    LOBYTE(v14) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      2,
                      v14);
                    LOBYTE(v15) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      3,
                      v15);
                    LOBYTE(v16) = 1;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                      WdfDriverGlobals,
                      v18,
                      6,
                      v16);
                    v3 = RootIoctlInit(v18);
                    if ( v3 >= 0 )
                    {
                      v33 = GUID_BUS_VMBUS;
                      v34 = 15;
                      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *))(WdfFunctions_01033 + 680))(
                        WdfDriverGlobals,
                        v18,
                        &v33);
                      return 0;
                    }
                  }
                  else
                  {
                    v4 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      v5 = 20;
                      goto LABEL_26;
                    }
                  }
                }
                else
                {
                  v4 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    v5 = 19;
                    goto LABEL_26;
                  }
                }
              }
              else
              {
                v4 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v5 = 16;
                  goto LABEL_26;
                }
              }
            }
            else
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v5 = 15;
                goto LABEL_26;
              }
            }
          }
        }
        else
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v5 = 14;
            goto LABEL_26;
          }
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v5 = 13;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v5 = 12;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v5 = 11;
LABEL_26:
      WPP_SF_d(v4->AttachedDevice, v5, WPP_1d82a8cff87b33874cd31050c50ab9c4_Traceguids, (unsigned int)v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002a790  push    rbp
0x14002a792  push    rbx
0x14002a793  push    rdi
0x14002a794  push    r12
0x14002a796  push    r14
0x14002a798  push    r15
0x14002a79a  lea     rbp, [rsp-158h]
0x14002a7a2  sub     rsp, 258h
0x14002a7a9  mov     rax, cs:__security_cookie
0x14002a7b0  xor     rax, rsp
0x14002a7b3  mov     [rbp+180h+var_38], rax
0x14002a7ba  mov     rbx, rdx
0x14002a7bd  mov     [rsp+280h+var_238], rdx
0x14002a7c2  xor     eax, eax
0x14002a7c4  lea     rcx, [rbp+180h+var_100]; void *
0x14002a7cb  xor     edx, edx; Val
0x14002a7cd  mov     [rbp+180h+var_FC], eax
0x14002a7d3  mov     r8d, 8Ch; Size
0x14002a7d9  call    memset
0x14002a7de  mov     edi, 60h ; '`'
0x14002a7e3  lea     rcx, [rbp+180h+var_160]; void *
0x14002a7e7  mov     r8d, edi; Size
0x14002a7ea  xor     edx, edx; Val
0x14002a7ec  call    memset
0x14002a7f1  movups  xmm1, xmmword ptr cs:aDeviceVmbus+0Ch; "e\\VMBus"
0x14002a7f8  mov     rcx, cs:WdfDriverGlobals
0x14002a7ff  lea     r8d, [rdi-36h]
0x14002a803  xorps   xmm0, xmm0
0x14002a806  mov     [rbp+180h+var_1B8], 1C001Ah
0x14002a80e  xor     eax, eax
0x14002a810  mov     rdx, rbx
0x14002a813  mov     dword ptr [rbp+180h+var_1F8], eax
0x14002a816  mov     [rbp+180h+var_60], rax
0x14002a81d  mov     [rsp+280h+var_240], rax
0x14002a822  mov     dword ptr [rbp+180h+var_1E0], eax
0x14002a825  lea     rax, [rbp+180h+var_58]
0x14002a82c  movups  [rbp+180h+var_1D8], xmm0
0x14002a830  mov     [rbp+180h+var_1B0], rax
0x14002a834  mov     rax, cs:WdfFunctions_01033
0x14002a83b  movups  xmmword ptr [rbp+180h+ObjectAttributes.ObjectName], xmm0
0x14002a83f  movups  [rsp+280h+var_228], xmm0
0x14002a844  movups  [rsp+280h+var_218], xmm0
0x14002a849  movups  [rsp+280h+var_208], xmm0
0x14002a84e  movups  [rbp+180h+var_70], xmm0
0x14002a855  movups  [rbp+180h+var_1F0], xmm0
0x14002a859  movups  [rbp+180h+var_1D8+0Ch], xmm0
0x14002a85d  movups  xmmword ptr [rbp+180h+DestinationString.Length], xmm0
0x14002a861  movups  xmmword ptr [rbp+180h+ObjectAttributes.Length], xmm0
0x14002a865  movups  xmmword ptr [rbp+180h+ObjectAttributes+1Ch], xmm0
0x14002a869  movups  xmm0, xmmword ptr cs:aDeviceVmbus; "\\Device\\VMBus"
0x14002a870  movups  xmmword ptr [rbp+180h+var_58], xmm0
0x14002a877  movups  xmmword ptr [rbp+180h+var_58+0Ch], xmm1
0x14002a87e  mov     rax, [rax+210h]
0x14002a885  call    _guard_dispatch_icall
0x14002a88a  mov     rax, cs:WdfFunctions_01033
0x14002a891  lea     r8d, [rdi-5Dh]
0x14002a895  mov     rdx, [rsp+280h+var_238]
0x14002a89a  mov     rcx, cs:WdfDriverGlobals
0x14002a8a1  mov     rax, [rax+1E8h]
0x14002a8a8  call    _guard_dispatch_icall
0x14002a8ad  xorps   xmm0, xmm0
0x14002a8b0  or      r12d, 0FFFFFFFFh
0x14002a8b4  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a8bb  movups  [rbp+180h+var_1D8], xmm0
0x14002a8bf  movups  [rbp+180h+var_1C8], xmm0
0x14002a8c3  jz      short loc_14002A8E6
0x14002a8c5  cmp     cs:WdfStructureCount, 1Bh
0x14002a8cc  jbe     short loc_14002A8E0
0x14002a8ce  mov     rax, cs:WdfStructures
0x14002a8d5  mov     ecx, [rax+0D8h]
0x14002a8db  mov     dword ptr [rbp+180h+var_1D8], ecx
0x14002a8de  jmp     short loc_14002A8ED
0x14002a8e0  mov     dword ptr [rbp+180h+var_1D8], r12d
0x14002a8e4  jmp     short loc_14002A8ED
0x14002a8e6  mov     dword ptr [rbp+180h+var_1D8], 20h ; ' '
0x14002a8ed  mov     rdx, [rsp+280h+var_238]
0x14002a8f2  lea     rax, RootFilterAddResourceRequirements
0x14002a8f9  mov     rcx, cs:WdfDriverGlobals
0x14002a900  lea     r8, [rbp+180h+var_1D8]
0x14002a904  mov     qword ptr [rbp+180h+var_1D8+8], rax
0x14002a908  lea     rax, RootRemoveAddedResources
0x14002a90f  mov     qword ptr [rbp+180h+var_1C8+8], rax
0x14002a913  mov     rax, cs:WdfFunctions_01033
0x14002a91a  mov     rax, [rax+400h]
0x14002a921  call    _guard_dispatch_icall
0x14002a926  mov     ebx, 90h
0x14002a92b  lea     rcx, [rbp+180h+var_100]; void *
0x14002a932  mov     r8d, ebx; Size
0x14002a935  xor     edx, edx; Val
0x14002a937  call    memset
0x14002a93c  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002a943  jz      short loc_14002A96C
0x14002a945  cmp     cs:WdfStructureCount, 29h ; ')'
0x14002a94c  jbe     short loc_14002A963
0x14002a94e  mov     rax, cs:WdfStructures
0x14002a955  mov     ecx, [rax+148h]
0x14002a95b  mov     [rbp+180h+var_100], ecx
0x14002a961  jmp     short loc_14002A972
0x14002a963  mov     [rbp+180h+var_100], r12d
0x14002a96a  jmp     short loc_14002A972
0x14002a96c  mov     [rbp+180h+var_100], ebx
0x14002a972  mov     rdx, [rsp+280h+var_238]
0x14002a977  lea     rax, RootDevicePrepareHardwareChild
0x14002a97e  mov     rcx, cs:WdfDriverGlobals
0x14002a985  lea     r8, [rbp+180h+var_100]
0x14002a98c  mov     [rbp+180h+var_D8], rax
0x14002a993  lea     rax, RootDeviceReleaseHardwareChild
0x14002a99a  mov     [rbp+180h+var_D0], rax
0x14002a9a1  lea     rax, RootDeviceSelfManagedIoInit
0x14002a9a8  mov     [rbp+180h+var_B8], rax
0x14002a9af  lea     rax, RootDeviceSelfManagedIoRestart
0x14002a9b6  mov     [rbp+180h+var_A8], rax
0x14002a9bd  lea     rax, RootDeviceSelfManagedIoSuspend
0x14002a9c4  mov     [rbp+180h+var_B0], rax
0x14002a9cb  mov     rax, cs:WdfFunctions_01033
0x14002a9d2  mov     rax, [rax+1B8h]
0x14002a9d9  call    _guard_dispatch_icall
0x14002a9de  mov     rax, cs:WdfFunctions_01033
0x14002a9e5  mov     rdx, [rsp+280h+var_238]
0x14002a9ea  mov     rcx, cs:WdfDriverGlobals
0x14002a9f1  mov     rax, [rax+1F8h]
0x14002a9f8  call    _guard_dispatch_icall
0x14002a9fd  mov     r8, rdi; Size
0x14002aa00  lea     rcx, [rbp+180h+var_160]; void *
0x14002aa04  xor     edx, edx; Val
0x14002aa06  call    memset
0x14002aa0b  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x14002aa12  mov     r15d, 2
0x14002aa18  jz      short loc_14002AA38
0x14002aa1a  cmp     cs:WdfStructureCount, r15d
0x14002aa21  jbe     short loc_14002AA32
0x14002aa23  mov     rax, cs:WdfStructures
0x14002aa2a  mov     ecx, [rax+10h]
0x14002aa2d  mov     [rbp+180h+var_160], ecx
0x14002aa30  jmp     short loc_14002AA3B
0x14002aa32  mov     [rbp+180h+var_160], r12d
0x14002aa36  jmp     short loc_14002AA3B
0x14002aa38  mov     [rbp+180h+var_160], edi
0x14002aa3b  mov     rdx, [rsp+280h+var_238]
0x14002aa40  lea     rax, RootDeviceListCreatePdo
0x14002aa47  mov     rcx, cs:WdfDriverGlobals
0x14002aa4e  lea     r8, [rbp+180h+var_160]
0x14002aa52  mov     [rbp+180h+var_150], rax
0x14002aa56  xor     r9d, r9d
0x14002aa59  lea     rax, InstanceDeviceListIdentificationDescriptionDuplicate
0x14002aa60  mov     [rbp+180h+var_15C], 0D0h
0x14002aa67  mov     [rbp+180h+var_138], rax
0x14002aa6b  lea     rax, InstanceDeviceListIdentificationDescriptionCompare
0x14002aa72  mov     [rbp+180h+var_128], rax
0x14002aa76  lea     rax, InstanceDeviceListIdentificationDescriptionCleanup
0x14002aa7d  mov     [rbp+180h+var_130], rax
0x14002aa81  mov     rax, cs:WdfFunctions_01033
0x14002aa88  mov     rax, [rax+410h]
0x14002aa8f  call    _guard_dispatch_icall
0x14002aa94  xorps   xmm0, xmm0
0x14002aa97  xor     eax, eax
0x14002aa99  cmp     cs:WdfClientVersionHigherThanFramework, al
0x14002aa9f  movups  [rsp+280h+var_228], xmm0
0x14002aaa4  mov     [rbp+180h+var_1F8], rax
0x14002aaa8  movups  [rsp+280h+var_218], xmm0
0x14002aaad  movups  [rsp+280h+var_208], xmm0
0x14002aab2  jz      short loc_14002AAD7
0x14002aab4  cmp     cs:WdfStructureCount, 26h ; '&'
0x14002aabb  jbe     short loc_14002AAD0
0x14002aabd  mov     rax, cs:WdfStructures
0x14002aac4  mov     ecx, [rax+130h]
0x14002aaca  mov     dword ptr [rsp+280h+var_228], ecx
0x14002aace  jmp     short loc_14002AADF
0x14002aad0  mov     dword ptr [rsp+280h+var_228], r12d
0x14002aad5  jmp     short loc_14002AADF
0x14002aad7  mov     dword ptr [rsp+280h+var_228], 38h ; '8'
0x14002aadf  mov     rax, cs:off_14001C0C8
0x14002aae6  lea     r8, [rbp+180h+var_1B8]
0x14002aaea  mov     rdx, [rsp+280h+var_238]
0x14002aaef  mov     r14d, 1
0x14002aaf5  mov     rcx, cs:WdfDriverGlobals
0x14002aafc  mov     [rbp+180h+var_1F8], rax
0x14002ab00  lea     rax, RootDeviceContextCleanup
0x14002ab07  mov     qword ptr [rsp+280h+var_228+8], rax
0x14002ab0c  lea     rax, RootDeviceContextDestroy
0x14002ab13  mov     qword ptr [rsp+280h+var_218], rax
0x14002ab18  mov     rax, cs:WdfFunctions_01033
0x14002ab1f  mov     dword ptr [rsp+280h+var_218+0Ch], r14d
0x14002ab24  mov     dword ptr [rsp+280h+var_218+8], r15d
0x14002ab29  mov     rax, [rax+218h]
0x14002ab30  call    _guard_dispatch_icall
0x14002ab35  mov     ebx, eax
0x14002ab37  test    eax, eax
0x14002ab39  jns     short loc_14002AB84
0x14002ab3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab42  lea     rax, WPP_GLOBAL_Control
0x14002ab49  cmp     rcx, rax
0x14002ab4c  jz      loc_14002B191
0x14002ab52  mov     edx, [rcx+2Ch]
0x14002ab55  test    r14b, dl
0x14002ab58  jz      loc_14002B191
0x14002ab5e  cmp     [rcx+29h], r15b
0x14002ab62  jb      loc_14002B191
0x14002ab68  lea     edx, [r14+0Ah]
0x14002ab6c  mov     rcx, [rcx+18h]
0x14002ab70  lea     r8, WPP_1d82a8cff87b33874cd31050c50ab9c4_Traceguids
0x14002ab77  mov     r9d, ebx
0x14002ab7a  call    WPP_SF_d
0x14002ab7f  jmp     loc_14002B191
0x14002ab84  mov     rax, cs:WdfFunctions_01033
0x14002ab8b  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x14002ab92  mov     rdx, [rsp+280h+var_238]
0x14002ab97  mov     rcx, cs:WdfDriverGlobals
0x14002ab9e  mov     rax, [rax+220h]
0x14002aba5  call    _guard_dispatch_icall
0x14002abaa  mov     ebx, eax
0x14002abac  test    eax, eax
0x14002abae  jns     short loc_14002ABE4
0x14002abb0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002abb7  lea     rax, WPP_GLOBAL_Control
0x14002abbe  cmp     rcx, rax
0x14002abc1  jz      loc_14002B191
0x14002abc7  mov     eax, [rcx+2Ch]
0x14002abca  test    r14b, al
0x14002abcd  jz      loc_14002B191
0x14002abd3  cmp     [rcx+29h], r15b
0x14002abd7  jb      loc_14002B191
0x14002abdd  mov     edx, 0Ch
0x14002abe2  jmp     short loc_14002AB6C
0x14002abe4  mov     rax, cs:WdfFunctions_01033
0x14002abeb  lea     r8, RootFileRdmaIoctlPreprocess
0x14002abf2  mov     rdx, [rsp+280h+var_238]
0x14002abf7  mov     r9b, 0Eh
0x14002abfa  mov     rcx, cs:WdfDriverGlobals
0x14002ac01  mov     [rsp+280h+var_258], 0
0x14002ac09  mov     rax, [rax+248h]
0x14002ac10  mov     [rsp+280h+var_260], 0
0x14002ac19  call    _guard_dispatch_icall
0x14002ac1e  mov     ebx, eax
0x14002ac20  test    eax, eax
0x14002ac22  js      loc_14002B191
0x14002ac28  lea     rdx, aCallbackSoftre; "\\Callback\\SoftRestart"
0x14002ac2f  lea     rcx, [rbp+180h+DestinationString]; DestinationString
0x14002ac33  call    cs:__imp_RtlInitUnicodeString
0x14002ac3a  nop     dword ptr [rax+rax+00h]
0x14002ac3f  lea     rax, [rbp+180h+DestinationString]
0x14002ac43  mov     [rbp+180h+ObjectAttributes.Length], 30h ; '0'
0x14002ac4a  xorps   xmm0, xmm0
0x14002ac4d  mov     [rbp+180h+ObjectAttributes.ObjectName], rax
0x14002ac51  mov     r9b, r14b; AllowMultipleCallbacks
0x14002ac54  mov     [rbp+180h+ObjectAttributes.RootDirectory], 0
0x14002ac5c  xor     r8d, r8d; Create
0x14002ac5f  mov     [rbp+180h+ObjectAttributes.Attributes], 50h ; 'P'
0x14002ac66  lea     rdx, [rbp+180h+ObjectAttributes]; ObjectAttributes
0x14002ac6a  lea     rcx, KsrCallbackObject; CallbackObject
0x14002ac71  movdqu  xmmword ptr [rbp+180h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002ac76  call    cs:__imp_ExCreateCallback
0x14002ac7d  nop     dword ptr [rax+rax+00h]
0x14002ac82  test    eax, eax
0x14002ac84  js      short loc_14002ACA3
0x14002ac86  mov     rcx, cs:KsrCallbackObject; CallbackObject
0x14002ac8d  lea     rdx, RootDeviceKsrCallback; CallbackFunction
0x14002ac94  xor     r8d, r8d; CallbackContext
0x14002ac97  call    cs:__imp_ExRegisterCallback
0x14002ac9e  nop     dword ptr [rax+rax+00h]
0x14002aca3  mov     rcx, [rsp+280h+var_238]
0x14002aca8  call    RootFileInit
0x14002acad  mov     ebx, eax
0x14002acaf  test    eax, eax
0x14002acb1  jns     short loc_14002ACEA
0x14002acb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002acba  lea     rax, WPP_GLOBAL_Control
0x14002acc1  cmp     rcx, rax
0x14002acc4  jz      loc_14002B191
0x14002acca  mov     eax, [rcx+2Ch]
0x14002accd  test    r14b, al
0x14002acd0  jz      loc_14002B191
0x14002acd6  cmp     [rcx+29h], r15b
0x14002acda  jb      loc_14002B191
0x14002ace0  mov     edx, 0Dh
0x14002ace5  jmp     loc_14002AB6C
0x14002acea  mov     rcx, [rsp+280h+var_238]
0x14002acef  call    AddFdoSupportedInterfaces
0x14002acf4  mov     ebx, eax
0x14002acf6  test    eax, eax
0x14002acf8  js      loc_14002B191
0x14002acfe  mov     rax, cs:WdfFunctions_01033
0x14002ad05  lea     r9, [rsp+280h+var_240]
0x14002ad0a  mov     rcx, cs:WdfDriverGlobals
0x14002ad11  lea     r8, [rsp+280h+var_228]
0x14002ad16  lea     rdx, [rsp+280h+var_238]
0x14002ad1b  mov     rax, [rax+258h]
0x14002ad22  call    _guard_dispatch_icall
0x14002ad27  mov     ebx, eax
0x14002ad29  test    eax, eax
0x14002ad2b  jns     short loc_14002AD64
0x14002ad2d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad34  lea     rax, WPP_GLOBAL_Control
0x14002ad3b  cmp     rcx, rax
0x14002ad3e  jz      loc_14002B191
0x14002ad44  mov     eax, [rcx+2Ch]
0x14002ad47  test    r14b, al
0x14002ad4a  jz      loc_14002B191
0x14002ad50  cmp     [rcx+29h], r15b
0x14002ad54  jb      loc_14002B191
  ... truncated ...
```
